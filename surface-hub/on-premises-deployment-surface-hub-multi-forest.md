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
# <span data-ttu-id="297b6-104">Implantação local do Surface Hub em um ambiente de várias florestas</span><span class="sxs-lookup"><span data-stu-id="297b6-104">On-premises deployment for Surface Hub in a multi-forest environment</span></span>


<span data-ttu-id="297b6-105">Este tópico explica como adicionar uma conta de dispositivo ao Microsoft Surface Hub quando você tiver uma implantação local de várias florestas.</span><span class="sxs-lookup"><span data-stu-id="297b6-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a multi-forest, on-premises deployment.</span></span>

<span data-ttu-id="297b6-106">Se você tiver uma implantação local de várias florestas com o Microsoft Exchange 2013 ou posterior e o Skype for Business 2013 ou posterior, poderá [usar os scripts do PowerShell fornecidos](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) para criar contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="297b6-106">If you have a multi-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="297b6-107">Se você estiver usando uma implantação de floresta única, consulte [Implantação local do Surface Hub em um ambiente de floresta única](on-premises-deployment-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="297b6-107">If you’re using a single-forest deployment, see [On-premises deployment for Surface Hub in a single-forest environment](on-premises-deployment-surface-hub-device-accounts.md).</span></span>

1.  <span data-ttu-id="297b6-108">Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="297b6-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

    <span data-ttu-id="297b6-109">Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="297b6-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

    <span data-ttu-id="297b6-110">Observe aqui que `$strExchangeServer` é o nome de domínio totalmente qualificado (FQDN) do servidor do Exchange e `$strLyncFQDN` é o FQDN do servidor do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="297b6-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  <span data-ttu-id="297b6-111">Depois de estabelecer uma sessão, crie uma nova caixa de correio na Floresta de Recursos.</span><span class="sxs-lookup"><span data-stu-id="297b6-111">After establishing a session, create a new mailbox in the Resource Forest.</span></span> <span data-ttu-id="297b6-112">Isso permitirá que a conta seja autenticada no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="297b6-112">This will allow the account to authenticate into the Surface Hub.</span></span>

    <span data-ttu-id="297b6-113">Se você estiver alterando uma caixa de correio de recurso existente:</span><span class="sxs-lookup"><span data-stu-id="297b6-113">If you're changing an existing resource mailbox:</span></span>

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  <span data-ttu-id="297b6-114">Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.</span><span class="sxs-lookup"><span data-stu-id="297b6-114">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

    <span data-ttu-id="297b6-115">Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como **False**.</span><span class="sxs-lookup"><span data-stu-id="297b6-115">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="297b6-116">Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="297b6-116">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

    <span data-ttu-id="297b6-117">Se você não criou uma política compatível ainda, use o seguinte cmdlet-—este cria uma política chamada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="297b6-117">If you haven’t created a compatible policy yet, use the following cmdlet-—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="297b6-118">Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="297b6-118">Once it’s created, you can apply the same policy to other device accounts.</span></span>

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    <span data-ttu-id="297b6-119">Quando você tiver uma política compatível, precisará aplicar a política à conta de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="297b6-119">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  <span data-ttu-id="297b6-120">Várias propriedades do Exchange podem ser definidas na conta de dispositivo para melhorar a experiência de reunião para com as pessoas.</span><span class="sxs-lookup"><span data-stu-id="297b6-120">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="297b6-121">Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="297b6-121">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="297b6-122">Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também.</span><span class="sxs-lookup"><span data-stu-id="297b6-122">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="297b6-123">Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="297b6-123">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span> <span data-ttu-id="297b6-124">Isso deve ser definido na Floresta de Usuário.</span><span class="sxs-lookup"><span data-stu-id="297b6-124">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  <span data-ttu-id="297b6-125">Habilite a conta no Active Directory para que ela seja autenticada no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="297b6-125">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span> <span data-ttu-id="297b6-126">Isso deve ser definido na Floresta de Usuário.</span><span class="sxs-lookup"><span data-stu-id="297b6-126">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. <span data-ttu-id="297b6-127">Agora, você precisa alterar a caixa de correio de sala para uma caixa de correio vinculada:</span><span class="sxs-lookup"><span data-stu-id="297b6-127">You now need to change the room mailbox to a linked mailbox:</span></span>

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  <span data-ttu-id="297b6-128">Habilite a conta de dispositivo com o Skype for Business, habilitando sua conta do Surface Hub AD em um pool do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="297b6-128">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    <span data-ttu-id="297b6-129">Você precisará usar o endereço Session Initiation Protocol (SIP) e o controlador de domínio do Surface Hub, juntamente com seu próprio identificador do pool do Skype for Business Server e identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="297b6-129">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>


## <span data-ttu-id="297b6-130">Desabilitar email anônimo e mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="297b6-130">Disable anonymous email and IM</span></span>



<span data-ttu-id="297b6-131">O Surface Hub usa uma conta de dispositivo para fornecer serviços de email e colaboração (IM, vídeo, voz).</span><span class="sxs-lookup"><span data-stu-id="297b6-131">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="297b6-132">Esta conta de dispositivo é usada como a identidade de origem (a parte "de") ao enviar emails, mensagens instantâneas e chamadas.</span><span class="sxs-lookup"><span data-stu-id="297b6-132">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="297b6-133">Como essa conta não vem de um usuário individual, identificável, ela é considerada "Anonymous" porque ela se originou da conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="297b6-133">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="297b6-134">Suponha que você tenha uma política de cliente por usuário atribuída a cada dispositivo de sala de reunião com uma identidade de **SurfaceHubPolicy**.</span><span class="sxs-lookup"><span data-stu-id="297b6-134">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="297b6-135">Para desabilitar o email anônimo e as mensagens, adicione um clientPolicyEntry a essa política de cliente usando os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="297b6-135">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="297b6-136">Para verificar se a política foi definida:</span><span class="sxs-lookup"><span data-stu-id="297b6-136">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="297b6-137">A saída deve ser:</span><span class="sxs-lookup"><span data-stu-id="297b6-137">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="297b6-138">Para alterar a entrada de política:</span><span class="sxs-lookup"><span data-stu-id="297b6-138">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="297b6-139">Para remover a entrada de política:</span><span class="sxs-lookup"><span data-stu-id="297b6-139">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





