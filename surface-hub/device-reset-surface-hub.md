---
title: Redefinir ou recuperar um Surface Hub
description: Descreve os processos de restauração e recuperação do Surface Hub e fornece instruções.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: redefinir o Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: c5cf643d0f4a68344bb098916a909dd66e1dac9b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830673"
---
# <span data-ttu-id="607bc-104">Redefinir ou recuperar um Surface Hub</span><span class="sxs-lookup"><span data-stu-id="607bc-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="607bc-105">Este artigo descreve como redefinir ou recuperar um hub Surface Hub da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="607bc-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="607bc-106">[Redefinir o Surface Hub](#reset-a-surface-hub) retorna o sistema operacional para a última atualização cumulativa do Windows e remove todos os arquivos de usuários locais e informações de configuração.</span><span class="sxs-lookup"><span data-stu-id="607bc-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="607bc-107">As informações que são removidas incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="607bc-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="607bc-108">A conta do dispositivo</span><span class="sxs-lookup"><span data-stu-id="607bc-108">The device account</span></span>
- <span data-ttu-id="607bc-109">Informações da conta para administradores locais do dispositivo</span><span class="sxs-lookup"><span data-stu-id="607bc-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="607bc-110">Informações de ingresso em domínio ou ingressar no Azure AD</span><span class="sxs-lookup"><span data-stu-id="607bc-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="607bc-111">Informações de inscrição no gerenciamento de dispositivo móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="607bc-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="607bc-112">Informações de configuração que foram definidas usando o MDM ou o aplicativo configurações</span><span class="sxs-lookup"><span data-stu-id="607bc-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="607bc-113">[Recuperar um Surface Hub da nuvem](#recover-a-surface-hub-from-the-cloud) também remove essas informações.</span><span class="sxs-lookup"><span data-stu-id="607bc-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="607bc-114">Além disso, o Surface Hub baixa uma nova imagem do sistema operacional e a instala.</span><span class="sxs-lookup"><span data-stu-id="607bc-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="607bc-115">Você pode especificar se o processo de recuperação preserva outras informações armazenadas no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="607bc-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span>

## <span data-ttu-id="607bc-116">Redefinir um Surface Hub</span><span class="sxs-lookup"><span data-stu-id="607bc-116">Reset a Surface Hub</span></span>

<span data-ttu-id="607bc-117">Pode ser necessário redefinir o Surface Hub por motivos como os seguintes:</span><span class="sxs-lookup"><span data-stu-id="607bc-117">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="607bc-118">Você está redirecionando o dispositivo para um novo espaço de reunião e deseja reconfigurá-lo.</span><span class="sxs-lookup"><span data-stu-id="607bc-118">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="607bc-119">Você deseja alterar como gerencia o dispositivo localmente.</span><span class="sxs-lookup"><span data-stu-id="607bc-119">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="607bc-120">O nome de usuário ou a senha da conta do dispositivo ou da conta de administrador foi perdida.</span><span class="sxs-lookup"><span data-stu-id="607bc-120">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="607bc-121">Após a instalação de uma atualização, o desempenho do dispositivo diminui.</span><span class="sxs-lookup"><span data-stu-id="607bc-121">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="607bc-122">Durante o processo de redefinição, se você vir uma tela em branco por longos períodos de tempo, aguarde e não execute nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="607bc-122">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="607bc-123">O processo de redefinição do dispositivo pode levar até seis horas.</span><span class="sxs-lookup"><span data-stu-id="607bc-123">The device reset process may take up to six hours.</span></span> <span data-ttu-id="607bc-124">Não desligue ou desconecte o Surface Hub até que o processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="607bc-124">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="607bc-125">Se você interromper o processo, o dispositivo se torna inoperante.</span><span class="sxs-lookup"><span data-stu-id="607bc-125">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="607bc-126">O dispositivo requer serviço de garantia para se tornar funcional novamente.</span><span class="sxs-lookup"><span data-stu-id="607bc-126">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="607bc-127">No Surface Hub, abra **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="607bc-127">On your Surface Hub, open **Settings**.</span></span>

   ![Imagem que mostra o aplicativo configurações para Surface Hub.](images/sh-settings.png)

1. <span data-ttu-id="607bc-129">Selecione **atualizar & segurança**.</span><span class="sxs-lookup"><span data-stu-id="607bc-129">Select **Update & Security**.</span></span>

   ![Imagem que mostra a atualização & grupo de segurança no aplicativo configurações para Surface Hub.](images/sh-settings-update-security.png)

1. <span data-ttu-id="607bc-131">Selecione **recuperação**e, em seguida, em **Redefinir dispositivo**, selecione **introdução**.</span><span class="sxs-lookup"><span data-stu-id="607bc-131">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   ![Imagem que mostra a opção redefinir dispositivo no aplicativo configurações para Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="607bc-133">Após a conclusão do processo de redefinição, o Surface Hub iniciará o [programa de primeira execução](first-run-program-surface-hub.md) novamente.</span><span class="sxs-lookup"><span data-stu-id="607bc-133">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="607bc-134">Se o processo de redefinição encontrar um problema, ele volta ao Surface Hub para a imagem do sistema operacional existente e, em seguida, exibe a tela de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="607bc-134">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="607bc-135">Recuperar um Surface Hub da nuvem</span><span class="sxs-lookup"><span data-stu-id="607bc-135">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="607bc-136">Se, por algum motivo, o Surface Hub se tornar inutilizável, você ainda poderá recuperá-lo da nuvem sem assistência do suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="607bc-136">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="607bc-137">O Surface Hub pode baixar uma imagem do sistema operacional nova da nuvem e usar essa imagem para reinstalar o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="607bc-137">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="607bc-138">Talvez seja necessário usar esse tipo de processo de recuperação nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="607bc-138">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="607bc-139">O Surface Hub ou suas contas relacionadas digitaram um estado instável</span><span class="sxs-lookup"><span data-stu-id="607bc-139">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="607bc-140">O Surface Hub está bloqueado</span><span class="sxs-lookup"><span data-stu-id="607bc-140">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="607bc-141">A **recuperação do** processo na nuvem requer uma conexão com a Internet aberta (sem proxy ou outras autenticação).</span><span class="sxs-lookup"><span data-stu-id="607bc-141">The **Recover from the cloud** process requires an open internet connection (no proxy or other authentications).</span></span> <span data-ttu-id="607bc-142">É recomendável uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="607bc-142">An ethernet connection is recommended.</span></span>

### <span data-ttu-id="607bc-143">Recuperar um Surface Hub de um estado inválido</span><span class="sxs-lookup"><span data-stu-id="607bc-143">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="607bc-144">Se a conta do dispositivo ficar em um estado instável ou se a conta de administrador encontrar problemas, você poderá usar o aplicativo configurações para iniciar o processo de recuperação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="607bc-144">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="607bc-145">Você só deve usar o processo de recuperação na nuvem quando o processo de [redefinição do dispositivo](#reset-a-surface-hub) não corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="607bc-145">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="607bc-146">Em seu Surface Hub, selecione **Settings** &gt; **Atualizar configurações &** &gt; **recuperação**de segurança.</span><span class="sxs-lookup"><span data-stu-id="607bc-146">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

1. <span data-ttu-id="607bc-147">Em **recuperar da nuvem**, selecione **reiniciar agora**.</span><span class="sxs-lookup"><span data-stu-id="607bc-147">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![recuperar da nuvem](images/recover-from-the-cloud.png)

### <span data-ttu-id="607bc-149">Recuperar um Surface Hub bloqueado</span><span class="sxs-lookup"><span data-stu-id="607bc-149">Recover a locked Surface Hub</span></span>

<span data-ttu-id="607bc-150">Em raras ocasiões, o Surface Hub pode encontrar um erro durante a limpeza dos dados do usuário e do aplicativo no final de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="607bc-150">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="607bc-151">Quando isso acontece, o dispositivo é reiniciado automaticamente e tenta a operação novamente.</span><span class="sxs-lookup"><span data-stu-id="607bc-151">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="607bc-152">Mas se essa operação falhar repetidamente, o dispositivo será bloqueado automaticamente para proteger os dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="607bc-152">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="607bc-153">Para desbloqueá-lo, você deve [redefinir o dispositivo](#reset-a-surface-hub) ou, se isso não funcionar, recuperá-lo da nuvem.</span><span class="sxs-lookup"><span data-stu-id="607bc-153">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="607bc-154">Localize a chave de energia na parte inferior do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="607bc-154">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="607bc-155">O botão liga/desliga está ao lado da conexão do cabo de alimentação.</span><span class="sxs-lookup"><span data-stu-id="607bc-155">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="607bc-156">Para obter mais informações sobre o botão de ligar, consulte o [Guia de preparação de site do Surface Hub (PDF)](surface-hub-site-readiness-guide.md).</span><span class="sxs-lookup"><span data-stu-id="607bc-156">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

1. <span data-ttu-id="607bc-157">Enquanto o Surface Hub exibe a tela de boas-vindas, use o botão de energia para desativar o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="607bc-157">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

1. <span data-ttu-id="607bc-158">Use o botão de ligar para ligar o Surface Hub novamente.</span><span class="sxs-lookup"><span data-stu-id="607bc-158">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="607bc-159">O dispositivo é iniciado e exibe a tela do logotipo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="607bc-159">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="607bc-160">Quando você vir os pontos de rotação sob o logotipo do Surface Hub, use o botão de ligar para desligar o Surface Hub novamente.</span><span class="sxs-lookup"><span data-stu-id="607bc-160">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

1. <span data-ttu-id="607bc-161">Repita a etapa 3 3 vezes, ou até que o Surface Hub exiba a mensagem "preparando reparo automático".</span><span class="sxs-lookup"><span data-stu-id="607bc-161">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="607bc-162">Depois de exibir essa mensagem, o Surface Hub exibe a tela do Windows RE.</span><span class="sxs-lookup"><span data-stu-id="607bc-162">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

1. <span data-ttu-id="607bc-163">Selecione **Opções avançadas**.</span><span class="sxs-lookup"><span data-stu-id="607bc-163">Select **Advanced Options**.</span></span>

1. <span data-ttu-id="607bc-164">Selecione **recuperar na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="607bc-164">Select **Recover from the cloud**.</span></span> <span data-ttu-id="607bc-165">(Opcionalmente, você pode selecionar **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="607bc-165">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="607bc-166">No entanto, a **recuperação da nuvem** é a abordagem recomendada.)</span><span class="sxs-lookup"><span data-stu-id="607bc-166">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Recuperar da nuvem](images/recover-from-cloud.png)
1. <span data-ttu-id="607bc-168">Se for solicitado a inserir a chave do BitLocker, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="607bc-168">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="607bc-169">Para preservar as informações que o BitLocker protege no Surface Hub, insira a chave do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="607bc-169">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="607bc-170">Para descartar as informações protegidas, selecione **ignorar esta unidade**</span><span class="sxs-lookup"><span data-stu-id="607bc-170">To discard the protected information, select **Skip this drive**</span></span>  

1. <span data-ttu-id="607bc-171">Quando solicitado, selecione **reinstalar**.</span><span class="sxs-lookup"><span data-stu-id="607bc-171">When you are prompted, select **Reinstall**.</span></span>

    ![Reinstalar](images/reinstall.png)

1. <span data-ttu-id="607bc-173">Para reparticionar o disco, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="607bc-173">To repartition the disk, select **Yes**.</span></span>

   ![Reparticionar](images/repartition.png)

   <span data-ttu-id="607bc-175">Primeiro, o processo de recuperação baixa a imagem do sistema operacional da nuvem.</span><span class="sxs-lookup"><span data-stu-id="607bc-175">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![baixando 97&](images/recover-progress.png)

   <span data-ttu-id="607bc-177">Quando o download terminar, o processo de recuperação restaura o Surface Hub de acordo com as opções que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="607bc-177">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="607bc-178">Contatar o Suporte</span><span class="sxs-lookup"><span data-stu-id="607bc-178">Contact Support</span></span>

<span data-ttu-id="607bc-179">Se tiver dúvidas ou precisar de ajuda, você pode [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="607bc-179">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="607bc-180">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="607bc-180">Related topics</span></span>

[<span data-ttu-id="607bc-181">Gerenciar o Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="607bc-181">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="607bc-182">Guia do administrador do Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="607bc-182">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
