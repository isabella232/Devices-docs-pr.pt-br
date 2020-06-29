---
title: Implantação online com o Office 365 (Surface Hub)
description: Este tópico contém instruções para adicionar uma conta de dispositivo para seu Microsoft Surface Hub quando você tiver uma implantação online pura.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: conta de dispositivo para o Surface Hub, implantação online
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830635"
---
# Implantação online com o Office 365 (Surface Hub)


Este tópico contém instruções para adicionar uma conta de dispositivo para seu Microsoft Surface Hub quando você tiver uma implantação online pura.

Se você tiver uma implantação pura on-line (O365), poderá [usar os scripts do PowerShell fornecidos](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) para criar contas de dispositivo. 

1. Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange.

   Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e irá habilitá-la como um RoomMailboxAccount, ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta seja autenticada no Surface Hub.

   Se você estiver alterando uma caixa de correio de recurso existente:

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Se você estiver criando uma nova caixa de correio de recurso:

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.

   Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como False. Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.

   Se você não criou uma política compatível ainda, use o seguinte cmdlet — este cria uma política chamada "Surface Hubs". Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   Quando você tiver uma política compatível, precisará aplicar a política à conta de dispositivo.

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. Várias propriedades do Exchange devem ser definidas na conta de dispositivo para melhorar a experiência de reunião. Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Conecte-se ao Azure AD.
    
   Primeiro você precisa instalar o módulo do Azure AD para PowerShell versão 2. Em um prompt do powershell com privilégios elevados, execute o seguinte comando:
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   Você precisa conectar-se ao Azure AD para aplicar algumas configurações de conta. Você pode executar este cmdlet para se conectar.

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também. Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. O Surface Hub requer uma licença para a funcionalidade do Skype for Business. Para habilitar o Skype for Business, seu ambiente deverá atender aos seguintes [pré-requisitos do Skype for Business Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).
   
   Em seguida, você pode usar `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para seu locatário do O365.

   Depois de listar as SKUs, você precisará atribuir a SkuId que deseja para a variável `$License.SkuId`.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. Habilite a conta de dispositivo com o Skype for Business.
   Se o módulo do PowerShell do Skype for Business não estiver instalado, [baixe o Módulo do Windows PowerShell do Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366). 

   - Comece criando uma sessão remota do PowerShell de um computador.

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - Em seguida, Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet (por exemplo, <em>alice@contoso.com</em>):

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       OU definindo uma variável
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - Habilite a conta do Surface Hub usando o seguinte cmdlet:
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       OU usando a variável $strRegistarPool acima
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

Para validação, você deve poder usar qualquer cliente do Skype for Business (PC, Android, etc) para entrar nessa conta.





