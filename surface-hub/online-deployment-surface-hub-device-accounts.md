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
# <span data-ttu-id="22f5b-104">Implantação online com o Office 365 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="22f5b-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="22f5b-105">Este tópico contém instruções para adicionar uma conta de dispositivo para seu Microsoft Surface Hub quando você tiver uma implantação online pura.</span><span class="sxs-lookup"><span data-stu-id="22f5b-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="22f5b-106">Se você tiver uma implantação pura on-line (O365), poderá [usar os scripts do PowerShell fornecidos](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) para criar contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22f5b-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="22f5b-107">Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="22f5b-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="22f5b-108">Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="22f5b-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="22f5b-109">Depois de estabelecer uma sessão, você criará uma nova caixa de correio e irá habilitá-la como um RoomMailboxAccount, ou alterará as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="22f5b-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="22f5b-110">Isso permitirá que a conta seja autenticada no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="22f5b-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="22f5b-111">Se você estiver alterando uma caixa de correio de recurso existente:</span><span class="sxs-lookup"><span data-stu-id="22f5b-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="22f5b-112">Se você estiver criando uma nova caixa de correio de recurso:</span><span class="sxs-lookup"><span data-stu-id="22f5b-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="22f5b-113">Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.</span><span class="sxs-lookup"><span data-stu-id="22f5b-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="22f5b-114">Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como False.</span><span class="sxs-lookup"><span data-stu-id="22f5b-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="22f5b-115">Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="22f5b-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="22f5b-116">Se você não criou uma política compatível ainda, use o seguinte cmdlet — este cria uma política chamada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="22f5b-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="22f5b-117">Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22f5b-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="22f5b-118">Quando você tiver uma política compatível, precisará aplicar a política à conta de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22f5b-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="22f5b-119">Várias propriedades do Exchange devem ser definidas na conta de dispositivo para melhorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="22f5b-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="22f5b-120">Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="22f5b-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="22f5b-121">Conecte-se ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="22f5b-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="22f5b-122">Primeiro você precisa instalar o módulo do Azure AD para PowerShell versão 2.</span><span class="sxs-lookup"><span data-stu-id="22f5b-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="22f5b-123">Em um prompt do powershell com privilégios elevados, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22f5b-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="22f5b-124">Você precisa conectar-se ao Azure AD para aplicar algumas configurações de conta.</span><span class="sxs-lookup"><span data-stu-id="22f5b-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="22f5b-125">Você pode executar este cmdlet para se conectar.</span><span class="sxs-lookup"><span data-stu-id="22f5b-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="22f5b-126">Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também.</span><span class="sxs-lookup"><span data-stu-id="22f5b-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="22f5b-127">Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="22f5b-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="22f5b-128">O Surface Hub requer uma licença para a funcionalidade do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="22f5b-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="22f5b-129">Para habilitar o Skype for Business, seu ambiente deverá atender aos seguintes [pré-requisitos do Skype for Business Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="22f5b-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="22f5b-130">Em seguida, você pode usar `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para seu locatário do O365.</span><span class="sxs-lookup"><span data-stu-id="22f5b-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="22f5b-131">Depois de listar as SKUs, você precisará atribuir a SkuId que deseja para a variável `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="22f5b-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

8. <span data-ttu-id="22f5b-132">Habilite a conta de dispositivo com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="22f5b-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="22f5b-133">Se o módulo do PowerShell do Skype for Business não estiver instalado, [baixe o Módulo do Windows PowerShell do Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="22f5b-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="22f5b-134">Comece criando uma sessão remota do PowerShell de um computador.</span><span class="sxs-lookup"><span data-stu-id="22f5b-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="22f5b-135">Em seguida, Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet (por exemplo, <em>alice@contoso.com</em>):</span><span class="sxs-lookup"><span data-stu-id="22f5b-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="22f5b-136">OU definindo uma variável</span><span class="sxs-lookup"><span data-stu-id="22f5b-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="22f5b-137">Habilite a conta do Surface Hub usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="22f5b-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="22f5b-138">OU usando a variável $strRegistarPool acima</span><span class="sxs-lookup"><span data-stu-id="22f5b-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="22f5b-139">Para validação, você deve poder usar qualquer cliente do Skype for Business (PC, Android, etc) para entrar nessa conta.</span><span class="sxs-lookup"><span data-stu-id="22f5b-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>





