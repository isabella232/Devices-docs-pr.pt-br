---
title: Criar conta de dispositivo do Surface Hub 2S
description: Esta página descreve o procedimento para criar a conta de dispositivo do Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196724"
---
# Criar conta de dispositivo do Surface Hub 2S

A criação de uma conta de dispositivo do Surface Hub (também conhecida como caixa de correio da sala) permite que o Surface Hub 2S receba, aprove ou recuse solicitações de reunião e ingresse em reuniões usando o Microsoft Teams ou o Skype for Business. Configure a conta do dispositivo durante a configuração do OOBE (configuração inicial pelo período). Se necessário, você poderá alterá-la mais tarde (sem passar pela configuração do OOBE).

Ao contrário das caixas de correio de sala padrão que permanecem desabilitadas por padrão, você precisa habilitar a conta do Surface Hub 2S para se conectar ao Microsoft Teams e ao Skype for Business. O Surface Hub 2S depende do Exchange ActiveSync, que exige uma política de caixa de correio do ActiveSync na conta do dispositivo. Aplique a política de caixa de correio padrão do ActiveSync que vem com o Exchange Online.

Crie a conta usando o centro de administração do Microsoft 365 ou usando o PowerShell. Você pode usar o PowerShell do Exchange Online para configurar recursos específicos, incluindo:

- Processamento de calendário para cada conta de dispositivo do Surface Hub.
- Respostas automáticas personalizadas para solicitações de agendamento.
- Se a política de caixa de correio padrão do ActiveSync já tiver sido modificada por outra pessoa ou por outro processo, é provável que você precise criar e atribuir uma nova política de caixa de correio do ActiveSync.

> [!NOTE]  
> A conta de dispositivo Hub Surface não oferece suporte a provedores de identidade federada (FIPs) de terceiros e deve ser uma conta padrão do Active Directory ou do Azure Active Directory.

## Criar conta usando o centro de administração do Microsoft 365

1. No centro de administração do Microsoft 365, vá para **recursos** e escolha **salas & equipamento** e selecione **+ sala**.

2. Forneça um nome e um endereço de email para a conta do dispositivo. Deixe as configurações restantes inalteradas no estado padrão.

   ![Fornecer um nome e endereço de email](images/sh2-account2.png)

   ![Deixar as configurações restantes inalteradas no estado padrão](images/sh2-account3.png)

3. Defina a senha da conta do dispositivo. Para definir a senha, escolha **usuários** e, em seguida, selecione **usuários ativos**. Agora, procure o usuário recém-criado para definir a senha. Certifique-se de que você **não** selecionou a opção fazer com que **este usuário altere a senha quando entrarem pela primeira vez.**

   ![Definir a senha da conta do dispositivo](images/sh2-account4.png)

4. Atribua a sala com uma licença do Office 365. É recomendável atribuir a licença da **sala de reunião** do Office 365, uma nova opção que habilita automaticamente a conta do Skype for Business Online e do Microsoft Teams.

   ![Atribuir licença do Office 365](images/sh2-account5.png)

### Finalizar a configuração via PowerShell

- **Calendário do Microsoft Teams e do Skype for Business:** Definir o [**processamento automático do calendário**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta conta.

## Criar conta usando o PowerShell

Em vez de usar o portal do centro de administração da Microsoft, você pode criar a conta usando o PowerShell.

### Conectar-se ao Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### Criar caixa de correio

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### Definir o processamento automático do calendário

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### Habilitar o ActiveSync se for necessário usar o aplicativo de email

 A política padrão do ActiveSync funcionará se unchnaged. Caso contrário, crie uma nova política e atribua.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### Conecte-se ao Azure AD

```powershell
Connect-AzureAD
```

### Atribuir uma licença

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### Verificar se há licenças disponíveis

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```