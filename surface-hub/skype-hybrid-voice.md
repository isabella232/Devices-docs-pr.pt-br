---
title: Implantação online ou híbrida usando o ambiente Skype Hybrid Voice (Surface Hub)
description: Este tópico explica como habilitar o Cloud PBX do Skype for Business com a conectividade PSTN local por meio do pool do Cloud Connector Edition ou do Skype for Business 2015.
keywords: Implantação híbrida, Skype Hybrid Voice
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831042"
---
# <span data-ttu-id="334e1-104">Implantação online ou híbrida usando o ambiente Skype Hybrid Voice (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="334e1-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="334e1-105">Este tópico explica como habilitar o Cloud PBX do Skype for Business com a conectividade PSTN (Rede Telefônica Pública Comutada) local por meio do pool do Cloud Connector Edition ou do Skype for Business 2015.</span><span class="sxs-lookup"><span data-stu-id="334e1-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="334e1-106">Nesta opção.</span><span class="sxs-lookup"><span data-stu-id="334e1-106">In this option.</span></span> <span data-ttu-id="334e1-107">O pools domésticos do Skype for Business e os servidores Exchange estão na nuvem e são conectados por PSTN por meio de um pool local que executa o Skype for Business 2015 ou o Cloud Connector edition.</span><span class="sxs-lookup"><span data-stu-id="334e1-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="334e1-108">[Saiba mais sobre as diferentes opções de Cloud PBX](https://technet.microsoft.com/library/mt612869.aspx).</span><span class="sxs-lookup"><span data-stu-id="334e1-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="334e1-109">Se você tiver implantado o Cloud PBX do Skype for Business com uma das opções de voz híbrida, siga as etapas abaixo para habilitar a conta com mais espaço para o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="334e1-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="334e1-110">É importante criar uma conta de usuário normal primeiro, atribuir todas as opções de voz híbrida e números de telefone e, em seguida, converter a conta em uma conta com mais espaço.</span><span class="sxs-lookup"><span data-stu-id="334e1-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="334e1-111">Se você não seguir essa ordem, não poderá atribuir um número de telefone híbrido.</span><span class="sxs-lookup"><span data-stu-id="334e1-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="334e1-112">Se você criar uma conta antes da configuração de voz híbrida (executar o comando Enable-CSMeetingRoom), não conseguirá configurar os parâmetros de voz híbrida necessários.</span><span class="sxs-lookup"><span data-stu-id="334e1-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="334e1-113">Para configurar os parâmetros de voz híbrida para uma conta configurada anteriormente ou para reconfigurar um número de telefone, exclua a licença de complemento do E5 ou E3 + Cloud PBX e siga as etapas abaixo, a partir da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="334e1-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="334e1-114">Crie uma nova conta de usuário para o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="334e1-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="334e1-115">Este exemplo usa <strong> surfacehub2@adatum.com </strong> .</span><span class="sxs-lookup"><span data-stu-id="334e1-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="334e1-116">A conta pode ser criada no Active Directory local e sincronizada com a nuvem, ou criada diretamente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="334e1-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![novo usuário do objeto](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="334e1-118">Selecione **A Senha Nunca Expira**.</span><span class="sxs-lookup"><span data-stu-id="334e1-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="334e1-119">Isso é importante para um dispositivo Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="334e1-119">This is important for a Surface Hub device.</span></span>

   ![A senha nunca expira](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="334e1-121">No Office 365, adicione a licença **E5** ou o complemento **E3 e Cloud PBX** à conta de usuário criada para o espaço.</span><span class="sxs-lookup"><span data-stu-id="334e1-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="334e1-122">Isso é necessário para que o Hybrid Voice funcione.</span><span class="sxs-lookup"><span data-stu-id="334e1-122">This is required for Hybrid Voice to work.</span></span>

   ![Adicionar licença de produto](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="334e1-124">Aguarde aproximadamente 15 minutos até que a conta de usuário do espaço apareça no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="334e1-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="334e1-125">Depois que a conta de usuário do espaço for criada no Skype for Business Online, habilite-o para Hybrid Voice no PowerShell Remoto do Skype for Business executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="334e1-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="334e1-126">Valide o fluxo de chamadas do Hybrid Voice inserindo chamadas de teste do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="334e1-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="334e1-127">Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange executando os cmdlets a seguir.</span><span class="sxs-lookup"><span data-stu-id="334e1-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="334e1-128">Após estabelecer uma sessão, modifique a conta de usuário do espaço para habilitá-lo como **RoomMailboxAccount** executando os cmdlets a seguir.</span><span class="sxs-lookup"><span data-stu-id="334e1-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="334e1-129">Isso permite que a conta seja autenticada com o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="334e1-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="334e1-130">Após configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.</span><span class="sxs-lookup"><span data-stu-id="334e1-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="334e1-131">Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como **False**.</span><span class="sxs-lookup"><span data-stu-id="334e1-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="334e1-132">Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="334e1-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="334e1-133">Se você não criou uma política compatível ainda, use o cmdlet a seguir (este cria uma política chamada "Surface Hubs").</span><span class="sxs-lookup"><span data-stu-id="334e1-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="334e1-134">Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="334e1-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="334e1-135">Quando você tiver uma política compatível, precisará aplicar a política à conta de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="334e1-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="334e1-136">No entanto, as políticas só podem ser aplicadas a contas de usuário, e não a caixas de correio de recurso.</span><span class="sxs-lookup"><span data-stu-id="334e1-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="334e1-137">Execute os cmdlets a seguir para converter a caixa de correio em um tipo de usuário, aplicar a política e, em seguida, convertê-la novamente em uma caixa de correio (talvez você precise reabilitar a conta e definir a senha novamente).</span><span class="sxs-lookup"><span data-stu-id="334e1-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="334e1-138">Várias propriedades do Exchange devem ser definidas na conta de dispositivo para melhorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="334e1-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="334e1-139">Você pode ver quais propriedades podem ser definidas em [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="334e1-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="334e1-140">Os cmdlets a seguir fornecem um exemplo de como definir propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="334e1-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="334e1-141">Habilite a caixa de correio como dispositivo de reunião no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="334e1-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="334e1-142">Execute o seguinte cmdlet que habilita a conta como um dispositivo de reunião.</span><span class="sxs-lookup"><span data-stu-id="334e1-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="334e1-143">Como resultado da execução desse cmdlet, os usuários serão perguntados se eles estão em uma sala de reunião, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="334e1-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="334e1-144">**Sim** ativará o mudo do microfone e do alto-falante.</span><span class="sxs-lookup"><span data-stu-id="334e1-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="334e1-145">Nesse momento, a conta com mais espaço será totalmente configurada, incluindo o Hybrid Voice.</span><span class="sxs-lookup"><span data-stu-id="334e1-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="334e1-146">Se você usar o Skype no local, poderá configurar atributos adicionais, como descrição, localização etc., no local.</span><span class="sxs-lookup"><span data-stu-id="334e1-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="334e1-147">Se você criar um espaço no Skype Online, esses parâmetros poderão ser definidos online.</span><span class="sxs-lookup"><span data-stu-id="334e1-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="334e1-148">Na imagem a seguir, veja como o dispositivo é exibido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="334e1-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)
