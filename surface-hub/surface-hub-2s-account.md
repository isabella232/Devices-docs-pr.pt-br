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
# <span data-ttu-id="3f826-104">Criar conta de dispositivo do Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="3f826-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="3f826-105">A criação de uma conta de dispositivo do Surface Hub (também conhecida como caixa de correio da sala) permite que o Surface Hub 2S receba, aprove ou recuse solicitações de reunião e ingresse em reuniões usando o Microsoft Teams ou o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3f826-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="3f826-106">Configure a conta do dispositivo durante a configuração do OOBE (configuração inicial pelo período).</span><span class="sxs-lookup"><span data-stu-id="3f826-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="3f826-107">Se necessário, você poderá alterá-la mais tarde (sem passar pela configuração do OOBE).</span><span class="sxs-lookup"><span data-stu-id="3f826-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="3f826-108">Ao contrário das caixas de correio de sala padrão que permanecem desabilitadas por padrão, você precisa habilitar a conta do Surface Hub 2S para se conectar ao Microsoft Teams e ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3f826-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="3f826-109">O Surface Hub 2S depende do Exchange ActiveSync, que exige uma política de caixa de correio do ActiveSync na conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f826-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="3f826-110">Aplique a política de caixa de correio padrão do ActiveSync que vem com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3f826-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="3f826-111">Crie a conta usando o centro de administração do Microsoft 365 ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f826-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="3f826-112">Você pode usar o PowerShell do Exchange Online para configurar recursos específicos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="3f826-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="3f826-113">Processamento de calendário para cada conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="3f826-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="3f826-114">Respostas automáticas personalizadas para solicitações de agendamento.</span><span class="sxs-lookup"><span data-stu-id="3f826-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="3f826-115">Se a política de caixa de correio padrão do ActiveSync já tiver sido modificada por outra pessoa ou por outro processo, é provável que você precise criar e atribuir uma nova política de caixa de correio do ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="3f826-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="3f826-116">A conta de dispositivo Hub Surface não oferece suporte a provedores de identidade federada (FIPs) de terceiros e deve ser uma conta padrão do Active Directory ou do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f826-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="3f826-117">Criar conta usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f826-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="3f826-118">No centro de administração do Microsoft 365, vá para **recursos** e escolha **salas & equipamento** e selecione **+ sala**.</span><span class="sxs-lookup"><span data-stu-id="3f826-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="3f826-119">Forneça um nome e um endereço de email para a conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f826-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="3f826-120">Deixe as configurações restantes inalteradas no estado padrão.</span><span class="sxs-lookup"><span data-stu-id="3f826-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Fornecer um nome e endereço de email](images/sh2-account2.png)

   ![Deixar as configurações restantes inalteradas no estado padrão](images/sh2-account3.png)

3. <span data-ttu-id="3f826-123">Defina a senha da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f826-123">Set the password for the device account.</span></span> <span data-ttu-id="3f826-124">Para definir a senha, escolha **usuários** e, em seguida, selecione **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="3f826-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="3f826-125">Agora, procure o usuário recém-criado para definir a senha.</span><span class="sxs-lookup"><span data-stu-id="3f826-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="3f826-126">Certifique-se de que você **não** selecionou a opção fazer com que **este usuário altere a senha quando entrarem pela primeira vez.**</span><span class="sxs-lookup"><span data-stu-id="3f826-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Definir a senha da conta do dispositivo](images/sh2-account4.png)

4. <span data-ttu-id="3f826-128">Atribua a sala com uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f826-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="3f826-129">É recomendável atribuir a licença da **sala de reunião** do Office 365, uma nova opção que habilita automaticamente a conta do Skype for Business Online e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f826-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Atribuir licença do Office 365](images/sh2-account5.png)

### <span data-ttu-id="3f826-131">Finalizar a configuração via PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f826-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="3f826-132">**Skype for Business:** Somente para o Skype for Business (no local ou online), você pode habilitar o objeto do Skype for Business executando **Enable-CsMeetingRoom** para habilitar recursos como solicitação de sala de reunião e isenção de áudio e lobby.</span><span class="sxs-lookup"><span data-stu-id="3f826-132">**Skype for Business:** For Skype for Business only (on-premises or online), you can enable the Skype for Business object by running **Enable-CsMeetingRoom** to enable features such as Meeting room prompt for audio and Lobby hold.</span></span>

- <span data-ttu-id="3f826-133">**Calendário do Microsoft Teams e do Skype for Business:** Definir o [**processamento automático do calendário**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta conta.</span><span class="sxs-lookup"><span data-stu-id="3f826-133">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="3f826-134">Criar conta usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f826-134">Create account using PowerShell</span></span>

<span data-ttu-id="3f826-135">Em vez de usar o portal do centro de administração da Microsoft, você pode criar a conta usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f826-135">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="3f826-136">Conectar-se ao Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f826-136">Connect to Exchange Online PowerShell</span></span>

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### <span data-ttu-id="3f826-137">Criar uma nova caixa de correio de sala</span><span class="sxs-lookup"><span data-stu-id="3f826-137">Create a new Room mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### <span data-ttu-id="3f826-138">Definir o processamento automático do calendário</span><span class="sxs-lookup"><span data-stu-id="3f826-138">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### <span data-ttu-id="3f826-139">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="3f826-139">Assign a license</span></span>

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## <span data-ttu-id="3f826-140">Conectar-se ao Skype for Business online usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f826-140">Connect to Skype for Business Online using PowerShell</span></span>

### <span data-ttu-id="3f826-141">Instalar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3f826-141">Install pre-requisites</span></span>

- [<span data-ttu-id="3f826-142">Visual C++ 2017 redistribuível</span><span class="sxs-lookup"><span data-stu-id="3f826-142">Visual C++ 2017 Redistributable</span></span>](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [<span data-ttu-id="3f826-143">Módulo do PowerShell do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f826-143">Skype for Business Online PowerShell Module</span></span>](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
