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
# <span data-ttu-id="487dc-104">Criar conta de dispositivo do Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="487dc-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="487dc-105">A criação de uma conta de dispositivo do Surface Hub (também conhecida como caixa de correio da sala) permite que o Surface Hub 2S receba, aprove ou recuse solicitações de reunião e ingresse em reuniões usando o Microsoft Teams ou o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="487dc-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="487dc-106">Configure a conta do dispositivo durante a configuração do OOBE (configuração inicial pelo período).</span><span class="sxs-lookup"><span data-stu-id="487dc-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="487dc-107">Se necessário, você poderá alterá-la mais tarde (sem passar pela configuração do OOBE).</span><span class="sxs-lookup"><span data-stu-id="487dc-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="487dc-108">Ao contrário das caixas de correio de sala padrão que permanecem desabilitadas por padrão, você precisa habilitar a conta do Surface Hub 2S para se conectar ao Microsoft Teams e ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="487dc-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="487dc-109">O Surface Hub 2S depende do Exchange ActiveSync, que exige uma política de caixa de correio do ActiveSync na conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="487dc-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="487dc-110">Aplique a política de caixa de correio padrão do ActiveSync que vem com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="487dc-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="487dc-111">Crie a conta usando o centro de administração do Microsoft 365 ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="487dc-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="487dc-112">Você pode usar o PowerShell do Exchange Online para configurar recursos específicos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="487dc-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="487dc-113">Processamento de calendário para cada conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="487dc-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="487dc-114">Respostas automáticas personalizadas para solicitações de agendamento.</span><span class="sxs-lookup"><span data-stu-id="487dc-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="487dc-115">Se a política de caixa de correio padrão do ActiveSync já tiver sido modificada por outra pessoa ou por outro processo, é provável que você precise criar e atribuir uma nova política de caixa de correio do ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="487dc-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="487dc-116">A conta de dispositivo Hub Surface não oferece suporte a provedores de identidade federada (FIPs) de terceiros e deve ser uma conta padrão do Active Directory ou do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="487dc-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="487dc-117">Criar conta usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="487dc-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="487dc-118">No centro de administração do Microsoft 365, vá para **recursos** e escolha **salas & equipamento** e selecione **+ sala**.</span><span class="sxs-lookup"><span data-stu-id="487dc-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="487dc-119">Forneça um nome e um endereço de email para a conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="487dc-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="487dc-120">Deixe as configurações restantes inalteradas no estado padrão.</span><span class="sxs-lookup"><span data-stu-id="487dc-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Fornecer um nome e endereço de email](images/sh2-account2.png)

   ![Deixar as configurações restantes inalteradas no estado padrão](images/sh2-account3.png)

3. <span data-ttu-id="487dc-123">Defina a senha da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="487dc-123">Set the password for the device account.</span></span> <span data-ttu-id="487dc-124">Para definir a senha, escolha **usuários** e, em seguida, selecione **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="487dc-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="487dc-125">Agora, procure o usuário recém-criado para definir a senha.</span><span class="sxs-lookup"><span data-stu-id="487dc-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="487dc-126">Certifique-se de que você **não** selecionou a opção fazer com que **este usuário altere a senha quando entrarem pela primeira vez.**</span><span class="sxs-lookup"><span data-stu-id="487dc-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Definir a senha da conta do dispositivo](images/sh2-account4.png)

4. <span data-ttu-id="487dc-128">Atribua a sala com uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="487dc-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="487dc-129">É recomendável atribuir a licença da **sala de reunião** do Office 365, uma nova opção que habilita automaticamente a conta do Skype for Business Online e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="487dc-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Atribuir licença do Office 365](images/sh2-account5.png)

### <span data-ttu-id="487dc-131">Finalizar a configuração via PowerShell</span><span class="sxs-lookup"><span data-stu-id="487dc-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="487dc-132">**Calendário do Microsoft Teams e do Skype for Business:** Definir o [**processamento automático do calendário**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta conta.</span><span class="sxs-lookup"><span data-stu-id="487dc-132">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="487dc-133">Criar conta usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="487dc-133">Create account using PowerShell</span></span>

<span data-ttu-id="487dc-134">Em vez de usar o portal do centro de administração da Microsoft, você pode criar a conta usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="487dc-134">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="487dc-135">Conectar-se ao Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="487dc-135">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="487dc-136">Criar caixa de correio</span><span class="sxs-lookup"><span data-stu-id="487dc-136">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="487dc-137">Definir o processamento automático do calendário</span><span class="sxs-lookup"><span data-stu-id="487dc-137">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="487dc-138">Habilitar o ActiveSync se for necessário usar o aplicativo de email</span><span class="sxs-lookup"><span data-stu-id="487dc-138">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="487dc-139">A política padrão do ActiveSync funcionará se unchnaged.</span><span class="sxs-lookup"><span data-stu-id="487dc-139">The default ActiveSync Policy will work if unchnaged.</span></span> <span data-ttu-id="487dc-140">Caso contrário, crie uma nova política e atribua.</span><span class="sxs-lookup"><span data-stu-id="487dc-140">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### <span data-ttu-id="487dc-141">Conecte-se ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="487dc-141">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="487dc-142">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="487dc-142">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="487dc-143">Verificar se há licenças disponíveis</span><span class="sxs-lookup"><span data-stu-id="487dc-143">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```