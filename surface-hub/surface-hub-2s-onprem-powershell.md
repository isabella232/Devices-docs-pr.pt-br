---
title: Configurar contas no local 2S do Surface Hub com o PowerShell
description: Saiba como configurar contas locais do Surface Hub 2S com o PowerShell
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831095"
---
# <span data-ttu-id="f2a8a-104">Configurar contas no local 2S do Surface Hub com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2a8a-104">Configure Surface Hub 2S on-premises accounts with PowerShell</span></span>

## <span data-ttu-id="f2a8a-105">Conectar-se ao Exchange Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2a8a-105">Connect to Exchange Server PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2a8a-106">Você precisará do FQDN (nome de domínio totalmente qualificado) para o serviço de acesso para cliente do servidor Exchange local para alguns desses cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f2a8a-106">You'll need the Fully Qualified Domain Name (FQDN) for the Client Access service of the on-premises Exchange server for some of these cmdlets.</span></span>

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## <span data-ttu-id="f2a8a-107">Criar a conta do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f2a8a-107">Create the device account</span></span>

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## <span data-ttu-id="f2a8a-108">Definir o processamento automático do calendário</span><span class="sxs-lookup"><span data-stu-id="f2a8a-108">Set automatic calendar processing</span></span>

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## <span data-ttu-id="f2a8a-109">Habilitar o objeto Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f2a8a-109">Enable the Skype for Business object</span></span>

> [!NOTE]
> <span data-ttu-id="f2a8a-110">É importante que você saiba o FQDN do pool de registradores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f2a8a-110">It is important that you know the FQDN of the Skype for Business Registrar Pool.</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## <span data-ttu-id="f2a8a-111">Política de caixa de correio de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="f2a8a-111">Mobile Device Mailbox Policy</span></span>

<span data-ttu-id="f2a8a-112">Talvez seja necessário criar uma política de caixa de correio de dispositivo móvel (também conhecida como política do ActiveSync) para permitir que o Surface Hub se conecte ao seu ambiente online ou local.</span><span class="sxs-lookup"><span data-stu-id="f2a8a-112">You may need to create a Mobile Device Mailbox Policy (also known as ActiveSync Policy) to allow your Surface Hub to connect to your online or on-premises environment.</span></span>

## <span data-ttu-id="f2a8a-113">Criar uma política de caixa de correio de dispositivo móvel do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f2a8a-113">Create a Surface Hub mobile device mailbox policy</span></span>

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## <span data-ttu-id="f2a8a-114">Configurações adicionais</span><span class="sxs-lookup"><span data-stu-id="f2a8a-114">Additional settings</span></span>

<span data-ttu-id="f2a8a-115">É recomendável adicionar uma dica de usuário às salas do Surface Hub para que os usuários se lembrem de transformar a reunião em uma reunião do Skype for Business ou do teams:</span><span class="sxs-lookup"><span data-stu-id="f2a8a-115">It is recommended to add a MailTip to Surface Hub rooms so users remember to make the meeting a Skype for Business or Teams meeting:</span></span>

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
