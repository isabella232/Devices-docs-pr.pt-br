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
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831029"
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

- **Skype for Business:** Somente para o Skype for Business (no local ou online), você pode habilitar o objeto do Skype for Business executando **Enable-CsMeetingRoom** para habilitar recursos como solicitação de sala de reunião e isenção de áudio e lobby.

- **Calendário do Microsoft Teams e do Skype for Business:** Definir o [**processamento automático do calendário**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta conta.

## Criar conta usando o PowerShell

Em vez de usar o portal do centro de administração da Microsoft, você pode criar a conta usando o PowerShell.

### Conectar-se ao Exchange Online PowerShell

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### Criar uma nova caixa de correio de sala

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### Definir o processamento automático do calendário

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### Atribuir uma licença

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## Conectar-se ao Skype for Business online usando o PowerShell

### Instalar pré-requisitos

- [Visual C++ 2017 redistribuível](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [Módulo do PowerShell do Skype for Business Online](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
