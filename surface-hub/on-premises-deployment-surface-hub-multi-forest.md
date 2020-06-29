---
title: Implantação local de várias florestas (Surface Hub)
description: Este tópico explica como adicionar uma conta de dispositivo ao Microsoft Surface Hub quando você tiver uma implantação local de várias florestas.
keywords: implantação de várias florestas, implantação local, conta de dispositivo, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830636"
---
# Implantação local do Surface Hub em um ambiente de várias florestas


Este tópico explica como adicionar uma conta de dispositivo ao Microsoft Surface Hub quando você tiver uma implantação local de várias florestas.

Se você tiver uma implantação local de várias florestas com o Microsoft Exchange 2013 ou posterior e o Skype for Business 2013 ou posterior, poderá [usar os scripts do PowerShell fornecidos](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) para criar contas de dispositivo. Se você estiver usando uma implantação de floresta única, consulte [Implantação local do Surface Hub em um ambiente de floresta única](on-premises-deployment-surface-hub-device-accounts.md).

1.  Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange.

    Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.

    Observe aqui que `$strExchangeServer` é o nome de domínio totalmente qualificado (FQDN) do servidor do Exchange e `$strLyncFQDN` é o FQDN do servidor do Skype for Business.

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  Depois de estabelecer uma sessão, crie uma nova caixa de correio na Floresta de Recursos. Isso permitirá que a conta seja autenticada no Surface Hub.

    Se você estiver alterando uma caixa de correio de recurso existente:

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.

    Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como **False**. Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.

    Se você não criou uma política compatível ainda, use o seguinte cmdlet-—este cria uma política chamada "Surface Hubs". Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    Quando você tiver uma política compatível, precisará aplicar a política à conta de dispositivo. 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  Várias propriedades do Exchange podem ser definidas na conta de dispositivo para melhorar a experiência de reunião para com as pessoas. Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também. Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações. Isso deve ser definido na Floresta de Usuário.

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  Habilite a conta no Active Directory para que ela seja autenticada no Surface Hub. Isso deve ser definido na Floresta de Usuário.

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. Agora, você precisa alterar a caixa de correio de sala para uma caixa de correio vinculada:

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  Habilite a conta de dispositivo com o Skype for Business, habilitando sua conta do Surface Hub AD em um pool do Skype for Business Server:

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    Você precisará usar o endereço Session Initiation Protocol (SIP) e o controlador de domínio do Surface Hub, juntamente com seu próprio identificador do pool do Skype for Business Server e identidade do usuário.


## Desabilitar email anônimo e mensagens instantâneas



O Surface Hub usa uma conta de dispositivo para fornecer serviços de email e colaboração (IM, vídeo, voz). Esta conta de dispositivo é usada como a identidade de origem (a parte "de") ao enviar emails, mensagens instantâneas e chamadas. Como essa conta não vem de um usuário individual, identificável, ela é considerada "Anonymous" porque ela se originou da conta de dispositivo do Surface Hub.  

Suponha que você tenha uma política de cliente por usuário atribuída a cada dispositivo de sala de reunião com uma identidade de **SurfaceHubPolicy**. Para desabilitar o email anônimo e as mensagens, adicione um clientPolicyEntry a essa política de cliente usando os comandos a seguir.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

Para verificar se a política foi definida:

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

A saída deve ser:

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
Para alterar a entrada de política:

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
Para remover a entrada de política:

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





