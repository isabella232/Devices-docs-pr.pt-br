---
title: Implantação híbrida (Surface Hub)
description: Uma implantação híbrida exige processamento especial para configurar uma conta de dispositivo para seu Microsoft Surface Hub.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: implantação híbrida, conta de dispositivo para o Surface Hub, Exchange hospedado no local, Exchange hospedado online
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830653"
---
# <span data-ttu-id="98e9d-104">Implantação híbrida (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="98e9d-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="98e9d-105">Uma implantação híbrida exige processamento especial para configurar uma conta de dispositivo para seu Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="98e9d-106">Se você estiver usando uma implantação híbrida, em que sua organização possui uma combinação de serviços, com alguns hospedados no local e alguns hospedados online, sua configuração dependerá de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="98e9d-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="98e9d-107">Este tópico aborda implantações híbridas para [Exchange hospedado no local](#exchange-on-premises), [Exchange hospedado online](#exchange-online), Skype for Business local, Skype for Business online e Skype for Business híbrido.</span><span class="sxs-lookup"><span data-stu-id="98e9d-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="98e9d-108">Como existem muitas variações diferentes nesse tipo de implantação, não é possível fornecer instruções detalhadas para todos eles.</span><span class="sxs-lookup"><span data-stu-id="98e9d-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="98e9d-109">O seguinte processo funciona para muitas configurações.</span><span class="sxs-lookup"><span data-stu-id="98e9d-109">The following process will work for many configurations.</span></span> <span data-ttu-id="98e9d-110">Se o processo não estiver correto para sua instalação, recomendamos que você use o PowerShell (veja [Apêndice: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) para obter o mesmo resultado final documentado aqui e para outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="98e9d-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="98e9d-111">Em seguida, você deve usar o script de PowerShell fornecido para verificar a configuração do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="98e9d-112">(Veja [Script de verificação da conta](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span><span class="sxs-lookup"><span data-stu-id="98e9d-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="98e9d-113">Em um ambiente híbrido do Exchange, siga as etapas para [Exchange local](#exchange-on-premises).</span><span class="sxs-lookup"><span data-stu-id="98e9d-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="98e9d-114">Para mover objetos do Exchange para o Office 365, use o cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="98e9d-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="98e9d-115">Exchange no local</span><span class="sxs-lookup"><span data-stu-id="98e9d-115">Exchange on-premises</span></span>

<span data-ttu-id="98e9d-116">Use este procedimento se você usar o Exchange no local.</span><span class="sxs-lookup"><span data-stu-id="98e9d-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="98e9d-117">Para este procedimento, você usará as ferramentas de administração do AD para adicionar um endereço de email à sua conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="98e9d-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="98e9d-118">Essa conta será sincronizada com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="98e9d-119">Na ferramenta do AD **Usuários e computadores do Active Directory** , clique com o botão direito do mouse na pasta ou unidade organizacional que suas contas do Surface Hub serão criadas e clique em **Nova**e **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="98e9d-120">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário** .</span><span class="sxs-lookup"><span data-stu-id="98e9d-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="98e9d-121">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-121">Click **Next**.</span></span><p>

![Caixa Novo objeto para criar um novo usuário no Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="98e9d-123">Digite a senha dessa conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-123">Type the password for this account.</span></span> <span data-ttu-id="98e9d-124">Você precisará digitá-la novamente para verificação.</span><span class="sxs-lookup"><span data-stu-id="98e9d-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="98e9d-125">Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="98e9d-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="98e9d-126">**Importante** Selecionar **A senha nunca expira** é um requisito para o Skype for Business no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="98e9d-127">As regras de domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="98e9d-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="98e9d-128">Nesse caso, você precisará criar uma exceção para cada conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Imagem mostrando caixa de diálogo de senha.](images/hybriddeployment-02a.png)

-   <span data-ttu-id="98e9d-130">Clique em **Concluir** para criar a conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-130">Click **Finish** to create the account.</span></span>

![Imagem com nome da conta, nome de logon e opções de senha para o novo usuário.](images/hybriddeployment-03a.png)

2. <span data-ttu-id="98e9d-132">Habilite a caixa de correio remota.</span><span class="sxs-lookup"><span data-stu-id="98e9d-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="98e9d-133">Abra o Shell de gerenciamento do Exchange local com permissões de administrador e execute este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="98e9d-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="98e9d-134">Se você não tiver um ambiente do Exchange no local para executar este cmdlet, você pode fazer as mesmas alterações diretamente para o objeto do Active Directory para a conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="98e9d-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="98e9d-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="98e9d-136">msExchRecipientDisplayType = -2147481850</span><span class="sxs-lookup"><span data-stu-id="98e9d-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="98e9d-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="98e9d-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="98e9d-138">Depois que você criar a conta, execute uma sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="98e9d-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="98e9d-139">Quando ele estiver concluído, vá para a página usuários no centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi mesclada para online.</span><span class="sxs-lookup"><span data-stu-id="98e9d-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="98e9d-140">Conecte-se ao Microsoft Exchange Online e defina algumas propriedades para a conta no Office 365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="98e9d-141">Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="98e9d-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="98e9d-142">Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="98e9d-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="98e9d-143">As próximas etapas serão executadas em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="98e9d-144">Crie uma nova política do Exchange ActiveSync ou use uma política existente compatível.</span><span class="sxs-lookup"><span data-stu-id="98e9d-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="98e9d-145">Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.</span><span class="sxs-lookup"><span data-stu-id="98e9d-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="98e9d-146">Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como False.</span><span class="sxs-lookup"><span data-stu-id="98e9d-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="98e9d-147">Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="98e9d-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="98e9d-148">Se você não criou uma política compatível ainda, use o seguinte cmdlet — este cria uma política chamada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="98e9d-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="98e9d-149">Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98e9d-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="98e9d-150">Depois que você tiver uma política compatível, será necessário aplicar a política à conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98e9d-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="98e9d-151">Defina as propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="98e9d-151">Set Exchange properties.</span></span>

<span data-ttu-id="98e9d-152">Definindo propriedades do Exchange na conta de dispositivo para melhorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="98e9d-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="98e9d-153">Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="98e9d-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="98e9d-154">Conecte-se ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="98e9d-154">Connect to Azure AD.</span></span>

<span data-ttu-id="98e9d-155">Primeiro você precisa instalar o módulo do Azure AD para PowerShell versão 2.</span><span class="sxs-lookup"><span data-stu-id="98e9d-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="98e9d-156">Em um prompt elevado do PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="98e9d-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="98e9d-157">Você precisa conectar-se ao Azure AD para aplicar algumas configurações de conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="98e9d-158">Você pode executar este cmdlet para se conectar.</span><span class="sxs-lookup"><span data-stu-id="98e9d-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="98e9d-159">Atribua uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="98e9d-160">A conta de dispositivo precisa ter uma licença válida do Office 365 (O365), ou o Exchange e o Skype for Business não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="98e9d-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="98e9d-161">Se você tiver a licença, deverá atribuir um local de uso à sua conta de dispositivo. Isso determina quais SKUs de licença estão disponíveis para sua conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="98e9d-162">Você pode usar `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para seu locatário do O365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="98e9d-163">Depois de listar as SKUs, você precisará atribuir a SkuId que deseja para a variável `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="98e9d-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="98e9d-164">Em seguida, você pode habilitar a conta de dispositivo com [Skype for Business Online](#skype-for-business-online), [Skype for Business local](#skype-for-business-on-premises) ou [Skype for Business híbrido](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="98e9d-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="98e9d-165">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="98e9d-165">Skype for Business Online</span></span>

<span data-ttu-id="98e9d-166">Para habilitar o Skype for Business online, os usuários de locatário devem ter caixas de entrada do Exchange (pelo menos uma caixa de entrada do Exchange no locatário é necessária).</span><span class="sxs-lookup"><span data-stu-id="98e9d-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="98e9d-167">A tabela a seguir explica quais planos ou serviços adicionais você precisa.</span><span class="sxs-lookup"><span data-stu-id="98e9d-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="98e9d-168">Cenário de sistema da sala Skype</span><span class="sxs-lookup"><span data-stu-id="98e9d-168">Skype room system scenario</span></span> | <span data-ttu-id="98e9d-169">Se você tiver o Office 365 Premium, os aplicativos da Microsoft 365 para empresas ou o plano autônomo 2 do Skype for Business, você precisará:</span><span class="sxs-lookup"><span data-stu-id="98e9d-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="98e9d-170">Se você tiver um plano baseado em empresa, você precisa:</span><span class="sxs-lookup"><span data-stu-id="98e9d-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="98e9d-171">Se você tiver o Skype for Business Server 2015 (local ou híbrido), precisará:</span><span class="sxs-lookup"><span data-stu-id="98e9d-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="98e9d-172">Ingressar em uma reunião agendada</span><span class="sxs-lookup"><span data-stu-id="98e9d-172">Join a scheduled meeting</span></span> | <span data-ttu-id="98e9d-173">Plano 1 autônomo do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="98e9d-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="98e9d-174">E1, 3, 4 ou 5</span><span class="sxs-lookup"><span data-stu-id="98e9d-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="98e9d-175">CAL do Skype for Business Server padrão</span><span class="sxs-lookup"><span data-stu-id="98e9d-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="98e9d-176">Iniciar uma reunião ad-hoc</span><span class="sxs-lookup"><span data-stu-id="98e9d-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="98e9d-177">Plano 2 autônomo do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="98e9d-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="98e9d-178">E 1, 3, 4 ou 5</span><span class="sxs-lookup"><span data-stu-id="98e9d-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="98e9d-179">CAL do Skype for Business Server Padrão ou CAL empresarial</span><span class="sxs-lookup"><span data-stu-id="98e9d-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="98e9d-180">Iniciar uma reunião ad hoc e discar de uma reunião para números de telefone</span><span class="sxs-lookup"><span data-stu-id="98e9d-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="98e9d-181">Plano autônomo 2 do Skype for Business para conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="98e9d-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="98e9d-182">**Observação** a cobrança de consumo PSTN é opcional</span><span class="sxs-lookup"><span data-stu-id="98e9d-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="98e9d-183">E1 ou E3 com conferência de áudio ou e5</span><span class="sxs-lookup"><span data-stu-id="98e9d-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="98e9d-184">CAL do Skype for Business Server Padrão ou CAL empresarial</span><span class="sxs-lookup"><span data-stu-id="98e9d-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="98e9d-185">Dê ao grupo um número de telefone e faça ou receba chamadas do grupo ou ingresse em uma conferência de discagem rápida usando um número de telefone</span><span class="sxs-lookup"><span data-stu-id="98e9d-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="98e9d-186">Plano autônomo 2 do Skype for Business para o sistema telefônico e um plano de chamada de voz PSTN</span><span class="sxs-lookup"><span data-stu-id="98e9d-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="98e9d-187">E1 ou E3 com o sistema telefônico e um plano de chamada de voz PSTN ou e5</span><span class="sxs-lookup"><span data-stu-id="98e9d-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="98e9d-188">CAL do Skype for Business Server Padrão ou Plus CAL</span><span class="sxs-lookup"><span data-stu-id="98e9d-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="98e9d-189">A tabela a seguir lista as opções dos planos do Office 365 e do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="98e9d-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="98e9d-190">Plano O365</span><span class="sxs-lookup"><span data-stu-id="98e9d-190">O365 Plan</span></span> | <span data-ttu-id="98e9d-191">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="98e9d-191">Skype for Business</span></span> | <span data-ttu-id="98e9d-192">Sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="98e9d-192">Phone System</span></span> | <span data-ttu-id="98e9d-193">Conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="98e9d-193">Audio Conferencing</span></span> | <span data-ttu-id="98e9d-194">Planos de chamada</span><span class="sxs-lookup"><span data-stu-id="98e9d-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="98e9d-195">O365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="98e9d-195">O365 Business Essentials</span></span> | <span data-ttu-id="98e9d-196">Incluído</span><span class="sxs-lookup"><span data-stu-id="98e9d-196">Included</span></span> |  |  |  |
| <span data-ttu-id="98e9d-197">O365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="98e9d-197">O365 Business Premium</span></span> | <span data-ttu-id="98e9d-198">Incluído</span><span class="sxs-lookup"><span data-stu-id="98e9d-198">Included</span></span> |  |  |  |
| <span data-ttu-id="98e9d-199">E1</span><span class="sxs-lookup"><span data-stu-id="98e9d-199">E1</span></span> | <span data-ttu-id="98e9d-200">Incluído</span><span class="sxs-lookup"><span data-stu-id="98e9d-200">Included</span></span> | <span data-ttu-id="98e9d-201">Complemento</span><span class="sxs-lookup"><span data-stu-id="98e9d-201">Add-on</span></span> | <span data-ttu-id="98e9d-202">Complemento</span><span class="sxs-lookup"><span data-stu-id="98e9d-202">Add-on</span></span> | <span data-ttu-id="98e9d-203">Complemento (requer complemento do sistema de telefonia)</span><span class="sxs-lookup"><span data-stu-id="98e9d-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="98e9d-204">E3</span><span class="sxs-lookup"><span data-stu-id="98e9d-204">E3</span></span> | <span data-ttu-id="98e9d-205">Incluído</span><span class="sxs-lookup"><span data-stu-id="98e9d-205">Included</span></span> | <span data-ttu-id="98e9d-206">Complemento</span><span class="sxs-lookup"><span data-stu-id="98e9d-206">Add-on</span></span> | <span data-ttu-id="98e9d-207">Complemento</span><span class="sxs-lookup"><span data-stu-id="98e9d-207">Add-on</span></span> | <span data-ttu-id="98e9d-208">Complemento (requer complemento do sistema de telefonia)</span><span class="sxs-lookup"><span data-stu-id="98e9d-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="98e9d-209">E5</span><span class="sxs-lookup"><span data-stu-id="98e9d-209">E5</span></span> | <span data-ttu-id="98e9d-210">Incluído</span><span class="sxs-lookup"><span data-stu-id="98e9d-210">Included</span></span> | <span data-ttu-id="98e9d-211">Incluído</span><span class="sxs-lookup"><span data-stu-id="98e9d-211">Included</span></span> | <span data-ttu-id="98e9d-212">Incluído</span><span class="sxs-lookup"><span data-stu-id="98e9d-212">Included</span></span> | <span data-ttu-id="98e9d-213">Complemento</span><span class="sxs-lookup"><span data-stu-id="98e9d-213">Add-on</span></span>  |

1. <span data-ttu-id="98e9d-214">Comece criando uma sessão remota do PowerShell de um computador para o ambiente do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="98e9d-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="98e9d-215">Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="98e9d-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="98e9d-216">Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="98e9d-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="98e9d-217">Atribua a licença do Skype for Business à sua conta do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="98e9d-218">Depois de concluir as etapas anteriores para ativar sua conta do Surface Hub no Skype for Business Online, você deverá atribuir uma licença ao Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="98e9d-219">Usando o portal administrativo do O365, atribua uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98e9d-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="98e9d-220">Entre como um administrador de locatário, abra o Portal Administrativo do O365 e clique no aplicativo de administração.</span><span class="sxs-lookup"><span data-stu-id="98e9d-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="98e9d-221">Clique em **Usuários e grupos** e em **Adicionar usuários, redefinir senhas e mais**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="98e9d-222">Clique na conta do Surface Hub e, em seguida, clique no ícone de caneta para editar as informações da conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="98e9d-223">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-223">Click **Licenses**.</span></span>

- <span data-ttu-id="98e9d-224">Em **atribuir licenças**, selecione Skype for Business (plano 1) ou Skype for Business (plano 2), dependendo dos requisitos de licenciamento e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="98e9d-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="98e9d-225">Você terá que usar uma licença do plano 2 se quiser usar o Enterprise Voice em seu Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="98e9d-226">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="98e9d-227">Você também pode usar o módulo Active Directory do Microsoft Azure para Windows Powershell para executar os cmdlets necessários para atribuir uma dessas licenças, mas isso não é abordado aqui.</span><span class="sxs-lookup"><span data-stu-id="98e9d-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="98e9d-228">Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business (PC, Android, etc.) para entrar nessa conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="98e9d-229">Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="98e9d-229">Skype for Business on-premises</span></span>

<span data-ttu-id="98e9d-230">Para executar este cmdlet, você precisará se conectar a um dos front-ends do Skype.</span><span class="sxs-lookup"><span data-stu-id="98e9d-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="98e9d-231">Abra o Skype PowerShell e execute:</span><span class="sxs-lookup"><span data-stu-id="98e9d-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="98e9d-232">Skype for Business híbrido</span><span class="sxs-lookup"><span data-stu-id="98e9d-232">Skype for Business hybrid</span></span>

<span data-ttu-id="98e9d-233">Se sua organização tiver configurado [conectividade híbrida entre Skype for Business Server e Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), as diretrizes para a criação de contas serão diferentes de uma implantação padrão do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="98e9d-234">O Surface Hub requer uma conta do Skype do tipo `meetingroom`, enquanto um usuário normal usaria uma conta de tipo de usuário no Skype.</span><span class="sxs-lookup"><span data-stu-id="98e9d-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="98e9d-235">Se o servidor do Skype estiver configurado para híbrido onde você pode ter usuários no servidor do Skype local, bem como usuários hospedados no Office 365, você pode ter alguns problemas ao tentar criar uma conta do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="98e9d-236">No ambiente híbrido do Skype for Business Server 2015, todos os usuários que você quiser no Skype for Business online devem ser criados primeiro na implantação local, para que a conta do usuário seja criada nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98e9d-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="98e9d-237">Em seguida, você pode mover o usuário para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="98e9d-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="98e9d-238">A mudança de uma conta de usuário no local para online é feita por meio do cmdlet [move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="98e9d-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="98e9d-239">Para mover um objeto Csmeetingroom, use o cmdlet [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="98e9d-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="98e9d-240">Para usar o cmdlet Move-CsMeetingRoom, você deve ter instalado [o 6.0.9319.281 de atualização cumulativa de maio de 2017 para o Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [a atualização cumulativa de julho de 2017 5.0.8308.992 para o Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="98e9d-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="98e9d-241">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="98e9d-241">Exchange online</span></span>

<span data-ttu-id="98e9d-242">Use este procedimento se você usar o Exchange online.</span><span class="sxs-lookup"><span data-stu-id="98e9d-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="98e9d-243">Crie uma conta de email no Office 365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="98e9d-244">Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="98e9d-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="98e9d-245">Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="98e9d-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="98e9d-246">Configurar uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="98e9d-246">Set up a mailbox.</span></span>

<span data-ttu-id="98e9d-247">Depois de estabelecer uma sessão, você criará uma nova caixa de correio e irá habilitá-la como um RoomMailboxAccount, ou alterará as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="98e9d-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="98e9d-248">Isso permitirá que a conta seja autenticada no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="98e9d-249">Se você estiver alterando uma caixa de correio de recurso existente:</span><span class="sxs-lookup"><span data-stu-id="98e9d-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="98e9d-250">Se você estiver criando uma nova caixa de correio de recurso:</span><span class="sxs-lookup"><span data-stu-id="98e9d-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="98e9d-251">Crie a política do Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="98e9d-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="98e9d-252">Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.</span><span class="sxs-lookup"><span data-stu-id="98e9d-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="98e9d-253">Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como False.</span><span class="sxs-lookup"><span data-stu-id="98e9d-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="98e9d-254">Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingressar em reuniões) não serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="98e9d-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="98e9d-255">Se você não criou uma política compatível ainda, use o seguinte cmdlet — este cria uma política chamada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="98e9d-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="98e9d-256">Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98e9d-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="98e9d-257">Depois que você tiver uma política compatível, será necessário aplicar a política à conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98e9d-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="98e9d-258">No entanto, políticas só podem ser aplicadas a contas de usuário e não a caixas de correio de recurso.</span><span class="sxs-lookup"><span data-stu-id="98e9d-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="98e9d-259">Você precisa converter a caixa de correio em um tipo de usuário, aplicar a política e, em seguida, convertê-la novamente em uma caixa de correio. Talvez você precise reativá-la e definir a senha novamente também.</span><span class="sxs-lookup"><span data-stu-id="98e9d-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="98e9d-260">Defina as propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="98e9d-260">Set Exchange properties.</span></span>

<span data-ttu-id="98e9d-261">Várias propriedades do Exchange devem ser definidas na conta de dispositivo para melhorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="98e9d-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="98e9d-262">Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="98e9d-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="98e9d-263">Adicione um endereço de email para a sua conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="98e9d-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="98e9d-264">Para este procedimento, você usará as ferramentas de administração do AD para adicionar um endereço de email à sua conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="98e9d-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="98e9d-265">Na ferramenta do AD **Usuários e computadores do Active Directory** , clique com o botão direito do mouse na pasta ou unidade organizacional que suas contas do Surface Hub serão criadas e clique em **Nova**e **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="98e9d-266">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário** .</span><span class="sxs-lookup"><span data-stu-id="98e9d-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="98e9d-267">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-267">Click **Next**.</span></span>

![Caixa Novo objeto para criar um novo usuário no Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="98e9d-269">Digite a senha dessa conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-269">Type the password for this account.</span></span> <span data-ttu-id="98e9d-270">Você precisará digitá-la novamente para verificação.</span><span class="sxs-lookup"><span data-stu-id="98e9d-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="98e9d-271">Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="98e9d-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98e9d-272">A seleção da **senha nunca expira** é um requisito para o Skype for Business no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="98e9d-273">As regras de domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="98e9d-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="98e9d-274">Nesse caso, você precisará criar uma exceção para cada conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Imagem mostrando caixa de diálogo de senha.](images/hybriddeployment-02a.png)

- <span data-ttu-id="98e9d-276">Clique em **Concluir** para criar a conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-276">Click **Finish** to create the account.</span></span>

![Imagem com nome da conta, nome de logon e opções de senha para o novo usuário.](images/hybriddeployment-03a.png)

6. <span data-ttu-id="98e9d-278">Executar sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="98e9d-278">Run directory synchronization.</span></span>

<span data-ttu-id="98e9d-279">Depois que você criar a conta, execute uma sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="98e9d-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="98e9d-280">Quando terminar, vá para a página de usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.</span><span class="sxs-lookup"><span data-stu-id="98e9d-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="98e9d-281">Conecte-se ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="98e9d-281">Connect to Azure AD.</span></span>

<span data-ttu-id="98e9d-282">Primeiro você precisa instalar o módulo do Azure AD para PowerShell versão 2.</span><span class="sxs-lookup"><span data-stu-id="98e9d-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="98e9d-283">Em um prompt elevado do PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="98e9d-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="98e9d-284">Você precisa conectar-se ao Azure AD para aplicar algumas configurações de conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="98e9d-285">Você pode executar esse cmdlet para se conectar:</span><span class="sxs-lookup"><span data-stu-id="98e9d-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="98e9d-286">Atribua uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="98e9d-287">A conta de dispositivo precisa ter uma licença válida do Office 365 (O365), ou o Exchange e o Skype for Business não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="98e9d-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="98e9d-288">Se você tiver a licença, deverá atribuir um local de uso à sua conta de dispositivo. Isso determina quais SKUs de licença estão disponíveis para sua conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="98e9d-289">Em seguida, você pode usar `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para seu locatário do O365.</span><span class="sxs-lookup"><span data-stu-id="98e9d-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="98e9d-290">Depois de listar as SKUs, você precisará atribuir a SkuId que deseja para a variável `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="98e9d-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="98e9d-291">Em seguida, você pode habilitar a conta de dispositivo com [Skype for Business Online](#skype-for-business-online), [Skype for Business local](#skype-for-business-on-premises) ou [Skype for Business híbrido](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="98e9d-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="98e9d-292">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="98e9d-292">Skype for Business Online</span></span>

<span data-ttu-id="98e9d-293">Para habilitar o Skype for Business, seu ambiente deverá atender aos seguintes [pré-requisitos do Skype for Business Online](#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="98e9d-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="98e9d-294">Comece criando uma sessão remota do PowerShell para o ambiente do Skype for Business online de um computador.</span><span class="sxs-lookup"><span data-stu-id="98e9d-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="98e9d-295">Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="98e9d-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="98e9d-296">Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="98e9d-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="98e9d-297">Atribuir a licença do Skype for Business à sua conta do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="98e9d-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="98e9d-298">Depois de concluir as etapas anteriores para ativar sua conta do Surface Hub no Skype for Business Online, você deverá atribuir uma licença ao Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="98e9d-299">Usando o portal administrativo do O365, atribua uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98e9d-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="98e9d-300">Conecte-se como um administrador de locatário, abra o Portal Administrativo do O365 e clique no aplicativo de administração.</span><span class="sxs-lookup"><span data-stu-id="98e9d-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="98e9d-301">Clique em **Usuários e grupos** e em **Adicionar usuários, redefinir senhas e mais**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="98e9d-302">Clique na conta do Surface Hub e, em seguida, clique no ícone de caneta para editar as informações da conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="98e9d-303">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-303">Click **Licenses**.</span></span>

- <span data-ttu-id="98e9d-304">Em **Atribuir licenças**, selecione Skype for Business (Plano 2) ou o Skype for Business (Plano 3), dependendo de seus requisitos de licenciamento e de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="98e9d-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="98e9d-305">Você terá que usar uma licença de Plano 3 se quiser usar Enterprise Voice no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="98e9d-306">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="98e9d-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="98e9d-307">Você também pode usar o módulo Active Directory do Microsoft Azure para Windows PowerShell para executar os cmdlets necessários para atribuir uma dessas licenças, mas isso não é abordado aqui.</span><span class="sxs-lookup"><span data-stu-id="98e9d-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="98e9d-308">Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business (PC, Android, etc) para entrar nessa conta.</span><span class="sxs-lookup"><span data-stu-id="98e9d-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="98e9d-309">Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="98e9d-309">Skype for Business on-premises</span></span>

<span data-ttu-id="98e9d-310">Para executar este cmdlet, você precisará se conectar a um dos front-ends do Skype.</span><span class="sxs-lookup"><span data-stu-id="98e9d-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="98e9d-311">Abra o Skype PowerShell e execute:</span><span class="sxs-lookup"><span data-stu-id="98e9d-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="98e9d-312">Skype for Business híbrido</span><span class="sxs-lookup"><span data-stu-id="98e9d-312">Skype for Business hybrid</span></span>

<span data-ttu-id="98e9d-313">Se sua organização tiver configurado [conectividade híbrida entre Skype for Business Server e Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), as diretrizes para a criação de contas serão diferentes de uma implantação padrão do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="98e9d-314">O Surface Hub requer uma conta do Skype do tipo *meetingroom*, enquanto um usuário normal usaria uma conta de tipo de *usuário* no Skype.</span><span class="sxs-lookup"><span data-stu-id="98e9d-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="98e9d-315">Se o servidor do Skype estiver configurado para híbrido onde você pode ter usuários no servidor do Skype local, bem como usuários hospedados no Office 365, você pode ter alguns problemas ao tentar criar uma conta do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="98e9d-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="98e9d-316">No ambiente híbrido do Skype for Business Server 2015, todos os usuários que você quiser no Skype for Business online devem ser criados primeiro na implantação local, para que a conta do usuário seja criada nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98e9d-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="98e9d-317">Em seguida, você pode mover o usuário para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="98e9d-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="98e9d-318">A mudança de uma conta de usuário no local para online é feita por meio do cmdlet [move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="98e9d-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="98e9d-319">Para mover um objeto Csmeetingroom, use o cmdlet [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="98e9d-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="98e9d-320">Para usar o cmdlet Move-CsMeetingRoom, você deve ter instalado [o 6.0.9319.281 de atualização cumulativa de maio de 2017 para o Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [a atualização cumulativa de julho de 2017 5.0.8308.992 para o Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="98e9d-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>
