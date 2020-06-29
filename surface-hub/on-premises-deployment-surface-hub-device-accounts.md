---
title: Implantação local de floresta única (Surface Hub)
description: Este tópico explica como adicionar uma conta de dispositivo ao Microsoft Surface Hub quando você tiver uma implantação local de floresta única.
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: implantação de floresta única, implantação local, conta de dispositivo, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830644"
---
# <span data-ttu-id="7bc65-104">Implantação local do Surface Hub em um ambiente de floresta única</span><span class="sxs-lookup"><span data-stu-id="7bc65-104">On-premises deployment for Surface Hub in a single-forest environment</span></span>


<span data-ttu-id="7bc65-105">Este tópico explica como adicionar uma conta de dispositivo ao Microsoft Surface Hub quando você tiver uma implantação local de floresta única.</span><span class="sxs-lookup"><span data-stu-id="7bc65-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a single-forest, on-premises deployment.</span></span>

<span data-ttu-id="7bc65-106">Se você tiver uma implantação local de floresta única com o Microsoft Exchange 2013 ou posterior e o Skype for Business 2013 ou posterior, poderá [usar os scripts do PowerShell fornecidos](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) para criar contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7bc65-106">If you have a single-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="7bc65-107">Se você estiver usando uma implantação de várias florestas, consulte [Implantação local do Surface Hub em um ambiente de várias florestas](on-premises-deployment-surface-hub-multi-forest.md).</span><span class="sxs-lookup"><span data-stu-id="7bc65-107">If you’re using a multi-forest deployment, see [On-premises deployment for Surface Hub in a multi-forest environment](on-premises-deployment-surface-hub-multi-forest.md).</span></span>

1. <span data-ttu-id="7bc65-108">Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="7bc65-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

   <span data-ttu-id="7bc65-109">Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="7bc65-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   <span data-ttu-id="7bc65-110">Observe aqui que `$strExchangeServer` é o nome de domínio totalmente qualificado (FQDN) do servidor do Exchange e `$strLyncFQDN` é o FQDN do servidor do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7bc65-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. <span data-ttu-id="7bc65-111">Depois de estabelecer uma sessão, você criará uma nova caixa de correio e irá habilitá-la como um RoomMailboxAccount, ou alterará as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="7bc65-111">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="7bc65-112">Isso permitirá que a conta seja autenticada no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7bc65-112">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="7bc65-113">Se você estiver alterando uma caixa de correio de recurso existente:</span><span class="sxs-lookup"><span data-stu-id="7bc65-113">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="7bc65-114">Se você estiver criando uma nova caixa de correio de recurso:</span><span class="sxs-lookup"><span data-stu-id="7bc65-114">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> <span data-ttu-id="7bc65-115">A autenticação básica do diretório virtual do ActiveSync é necessária para ser habilitada, pois o Surface Hub não pode autenticar usando outros métodos de autenticação.</span><span class="sxs-lookup"><span data-stu-id="7bc65-115">ActiveSync Virtual Directory Basic Authentication is required to be enabled as the Surface Hub is unable to authenticate using other authentication methods.</span></span>

3. <span data-ttu-id="7bc65-116">Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.</span><span class="sxs-lookup"><span data-stu-id="7bc65-116">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="7bc65-117">Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como False.</span><span class="sxs-lookup"><span data-stu-id="7bc65-117">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="7bc65-118">Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="7bc65-118">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="7bc65-119">Se você não criou uma política compatível ainda, use o seguinte cmdlet — este cria uma política chamada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="7bc65-119">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="7bc65-120">Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7bc65-120">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   <span data-ttu-id="7bc65-121">Quando você tiver uma política compatível, precisará aplicar a política à conta de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7bc65-121">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="7bc65-122">No entanto, políticas só podem ser aplicadas a contas de usuário e não a caixas de correio de recurso.</span><span class="sxs-lookup"><span data-stu-id="7bc65-122">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="7bc65-123">Você precisa converter a caixa de correio em um tipo de usuário, aplicar a política e, em seguida, convertê-la novamente em uma caixa de correio. Talvez você precise reativá-la e definir a senha novamente também.</span><span class="sxs-lookup"><span data-stu-id="7bc65-123">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. <span data-ttu-id="7bc65-124">Várias propriedades do Exchange podem ser definidas na conta de dispositivo para melhorar a experiência de reunião para com as pessoas.</span><span class="sxs-lookup"><span data-stu-id="7bc65-124">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="7bc65-125">Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="7bc65-125">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="7bc65-126">Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também.</span><span class="sxs-lookup"><span data-stu-id="7bc65-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="7bc65-127">Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7bc65-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. <span data-ttu-id="7bc65-128">Habilite a conta no Active Directory para que ela seja autenticada no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7bc65-128">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. <span data-ttu-id="7bc65-129">Habilite a conta de dispositivo com o Skype for Business, habilitando sua conta do Surface Hub AD em um pool do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="7bc65-129">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   <span data-ttu-id="7bc65-130">Você precisará usar o endereço Session Initiation Protocol (SIP) e o controlador de domínio do Surface Hub, juntamente com seu próprio identificador do pool do Skype for Business Server e identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="7bc65-130">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>

8. <span data-ttu-id="7bc65-131">OPCIONAL: você também pode permitir que o Surface Hub faça e receba chamadas de rede pública de telefones (PSTN) habilitando Enterprise Voice para sua conta.</span><span class="sxs-lookup"><span data-stu-id="7bc65-131">OPTIONAL: You can also allow your Surface Hub to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="7bc65-132">O Enterprise Voice não é um requisito para o Surface Hub, mas se você quiser a funcionalidade de discagem PSTN para o cliente de Surface Hub, veja como habilitá-la:</span><span class="sxs-lookup"><span data-stu-id="7bc65-132">Enterprise Voice isn't a requirement for Surface Hub, but if you want PSTN dialing functionality for the Surface Hub client, here's how to enable it:</span></span>

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   <span data-ttu-id="7bc65-133">Novamente, você precisa substituir os exemplos de número de telefone e controlador de domínio fornecidos por suas próprias informações.</span><span class="sxs-lookup"><span data-stu-id="7bc65-133">Again, you need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="7bc65-134">O valor do parâmetro `$true` permanece o mesmo.</span><span class="sxs-lookup"><span data-stu-id="7bc65-134">The parameter value `$true` stays the same.</span></span>
    

 ## <span data-ttu-id="7bc65-135">Desabilitar email anônimo e mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="7bc65-135">Disable anonymous email and IM</span></span>




<span data-ttu-id="7bc65-136">O Surface Hub usa uma conta de dispositivo para fornecer serviços de email e colaboração (IM, vídeo, voz).</span><span class="sxs-lookup"><span data-stu-id="7bc65-136">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="7bc65-137">Esta conta de dispositivo é usada como a identidade de origem (a parte "de") ao enviar emails, mensagens instantâneas e chamadas.</span><span class="sxs-lookup"><span data-stu-id="7bc65-137">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="7bc65-138">Como essa conta não vem de um usuário individual, identificável, ela é considerada "Anonymous" porque ela se originou da conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7bc65-138">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="7bc65-139">Suponha que você tenha uma política de cliente por usuário atribuída a cada dispositivo de sala de reunião com uma identidade de **SurfaceHubPolicy**.</span><span class="sxs-lookup"><span data-stu-id="7bc65-139">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="7bc65-140">Para desabilitar o email anônimo e as mensagens, adicione um clientPolicyEntry a essa política de cliente usando os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bc65-140">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="7bc65-141">Para verificar se a política foi definida:</span><span class="sxs-lookup"><span data-stu-id="7bc65-141">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="7bc65-142">A saída deve ser:</span><span class="sxs-lookup"><span data-stu-id="7bc65-142">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="7bc65-143">Para alterar a entrada de política:</span><span class="sxs-lookup"><span data-stu-id="7bc65-143">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="7bc65-144">Para remover a entrada de política:</span><span class="sxs-lookup"><span data-stu-id="7bc65-144">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 





