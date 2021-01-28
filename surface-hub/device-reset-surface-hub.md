---
title: Redefinir ou recuperar um Surface Hub
description: Descreve os processos de redefinição e recuperação para o Surface Hub e fornece instruções.
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
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304814"
---
# <span data-ttu-id="9b1e1-104">Redefinir ou recuperar um Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9b1e1-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="9b1e1-105">Este artigo descreve como redefinir ou recuperar um Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="9b1e1-106">[A redefinição do Surface Hub](#reset-a-surface-hub) retorna seu sistema operacional para a última atualização cumulativa do Windows e remove todos os arquivos do usuário local e informações de configuração.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="9b1e1-107">As informações removidas incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b1e1-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="9b1e1-108">A conta do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9b1e1-108">The device account</span></span>
- <span data-ttu-id="9b1e1-109">Informações da conta dos administradores locais do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9b1e1-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="9b1e1-110">Informações de ingressar no domínio ou ingressar no Azure AD</span><span class="sxs-lookup"><span data-stu-id="9b1e1-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="9b1e1-111">Informações de registro do Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="9b1e1-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="9b1e1-112">Informações de configuração que foram definidas usando o MDM ou o aplicativo Configurações</span><span class="sxs-lookup"><span data-stu-id="9b1e1-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="9b1e1-113">[A recuperação de um Surface Hub da nuvem](#recover-a-surface-hub-from-the-cloud) também remove essas informações.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="9b1e1-114">Além disso, o Surface Hub baixa uma nova imagem do sistema operacional e a instala.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="9b1e1-115">Você pode especificar se o processo de recuperação preserva outras informações armazenadas no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="9b1e1-116">A mesma imagem do sistema operacional é usada pela Ferramenta de Recuperação do [Surface Hub](surface-hub-recovery-tool.md) se você precisar recuperar um Surface Hub para o qual nenhuma dessas opções pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <span data-ttu-id="9b1e1-117">Redefinir um Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9b1e1-117">Reset a Surface Hub</span></span>

<span data-ttu-id="9b1e1-118">Talvez seja preciso redefinir o Surface Hub por motivos como os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9b1e1-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="9b1e1-119">Você está reconfigurando o dispositivo para um novo espaço de reunião e deseja reconfigurá-lo.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="9b1e1-120">Você deseja alterar como gerencia o dispositivo localmente.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="9b1e1-121">O nome de usuário ou senha da conta de dispositivo ou da conta de Administrador foi perdido.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="9b1e1-122">Depois de instalar uma atualização, o desempenho do dispositivo diminui.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="9b1e1-123">Durante o processo de redefinição, se você vir uma tela em branco por longos períodos de tempo, aguarde e não tome nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="9b1e1-124">O processo de redefinição do dispositivo pode levar até seis horas.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="9b1e1-125">Não desligue ou desconecta o Surface Hub até que o processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="9b1e1-126">Se você interromper o processo, o dispositivo se tornará inoperante.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="9b1e1-127">O dispositivo requer o serviço de garantia para se tornar funcional novamente.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="9b1e1-128">No Surface Hub, abra **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-128">On your Surface Hub, open **Settings**.</span></span>

   ![Imagem que mostra o aplicativo Configurações do Surface Hub.](images/sh-settings.png)

2. <span data-ttu-id="9b1e1-130">Selecione **Atualizar & Segurança.**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-130">Select **Update & Security**.</span></span>

   ![Imagem que mostra o grupo & Segurança no aplicativo Configurações do Surface Hub.](images/sh-settings-update-security.png)

3. <span data-ttu-id="9b1e1-132">Selecione **Recuperação**e, em **Redefinir dispositivo,** selecione **Começar.**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="9b1e1-133">Verifique se sua chave do BitLocker está disponível antes de redefinir o dispositivo, pois ela será solicitado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="9b1e1-134">Para saber mais, consulte [Salvar sua chave do BitLocker.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="9b1e1-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="9b1e1-135">Quando o Hub for reiniciado para a partição de recuperação, ele solicitará que você insira a chave do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="9b1e1-136">Ignorar esse prompt causará falha na redefinição.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![Imagem que mostra a opção Redefinir dispositivo no aplicativo Configurações do Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="9b1e1-138">Depois que o processo de redefinição terminar, o Surface Hub iniciará [o programa de primeira duração](first-run-program-surface-hub.md) novamente.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="9b1e1-139">Se o processo de redefinição encontrar um problema, ele rola o Surface Hub de volta para a imagem do sistema operacional existente anteriormente e exibe a tela de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="9b1e1-140">Recuperar um Surface Hub da nuvem</span><span class="sxs-lookup"><span data-stu-id="9b1e1-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="9b1e1-141">Se, por algum motivo, o Surface Hub se tornar inutilizável, você ainda poderá recuperá-lo da nuvem sem assistência do Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="9b1e1-142">O Surface Hub pode baixar uma imagem nova do sistema operacional da nuvem e usar essa imagem para reinstalar seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="9b1e1-143">Talvez seja preciso usar esse tipo de processo de recuperação nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="9b1e1-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="9b1e1-144">O Surface Hub ou suas contas relacionadas entraram em um estado instável</span><span class="sxs-lookup"><span data-stu-id="9b1e1-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="9b1e1-145">O Surface Hub está bloqueado</span><span class="sxs-lookup"><span data-stu-id="9b1e1-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="9b1e1-146">A **recuperação do processo de nuvem** requer uma conexão com fio que fornece conectividade aberta à Internet (sem proxy ou outros prompts de autenticação).</span><span class="sxs-lookup"><span data-stu-id="9b1e1-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="9b1e1-147">Recuperar um Surface Hub de um estado inválido</span><span class="sxs-lookup"><span data-stu-id="9b1e1-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="9b1e1-148">Se a conta do dispositivo entrar em um estado instável ou se a conta de administrador encontrar problemas, você poderá usar o aplicativo Configurações para iniciar o processo de recuperação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="9b1e1-149">Você só deve usar o processo de recuperação na nuvem quando o [processo de redefinição](#reset-a-surface-hub) do dispositivo não corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="9b1e1-150">No Surface Hub, selecione **Atualização de Configurações** &gt; **& recuperação de** &gt; **segurança.**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="9b1e1-151">Em **Recuperar da nuvem,** selecione **Reiniciar agora.**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![recuperar da nuvem](images/recover-from-the-cloud.png)

### <span data-ttu-id="9b1e1-153">Recuperar um Surface Hub bloqueado</span><span class="sxs-lookup"><span data-stu-id="9b1e1-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="9b1e1-154">Em raras ocasiões, o Surface Hub pode encontrar um erro durante a limpeza dos dados do usuário e do aplicativo no final de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="9b1e1-155">Quando isso acontece, o dispositivo reinicia automaticamente e tenta a operação novamente.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="9b1e1-156">Mas se essa operação falhar repetidamente, o dispositivo será automaticamente protegido para proteger os dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="9b1e1-157">Para desbloqueá-lo, [você deve redefinir o](#reset-a-surface-hub) dispositivo ou, se isso não funcionar, recuperá-lo da nuvem.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="9b1e1-158">Localize o switch de energia na parte inferior do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="9b1e1-159">O botão de energia fica ao lado da conexão do cabo de alimentação.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="9b1e1-160">Para obter mais informações sobre a opção de energia, consulte o Guia de Preparação do Site do [Surface Hub (PDF).](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="9b1e1-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="9b1e1-161">Enquanto o Surface Hub exibe a tela de boas-vindas, use o botão de energia para desligar o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="9b1e1-162">Use o botão ligar/desligar para rea ligar o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="9b1e1-163">O dispositivo é iniciado e exibe a tela de logotipo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="9b1e1-164">Quando você vir pontos giratórios sob o Logotipo do Surface Hub, use o botão de energia para desligar o Surface Hub novamente.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="9b1e1-165">Repita a etapa 3 três vezes ou até que o Surface Hub exibe a mensagem "Preparando o reparo automático".</span><span class="sxs-lookup"><span data-stu-id="9b1e1-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="9b1e1-166">Depois de exibir essa mensagem, o Surface Hub exibe a tela do Windows RE.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

5. <span data-ttu-id="9b1e1-167">Selecione **Opções Avançadas.**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-167">Select **Advanced Options**.</span></span>

6. <span data-ttu-id="9b1e1-168">Selecione **Recuperar da nuvem.**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-168">Select **Recover from the cloud**.</span></span> <span data-ttu-id="9b1e1-169">(Opcionalmente, você pode selecionar **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-169">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="9b1e1-170">No entanto, **recuperar da nuvem** é a abordagem recomendada.)</span><span class="sxs-lookup"><span data-stu-id="9b1e1-170">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Recuperar da nuvem](images/recover-from-cloud.png)
7. <span data-ttu-id="9b1e1-172">Se você for solicitado a inserir a chave do Bitlocker, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b1e1-172">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="9b1e1-173">Para preservar as informações que o Bitlocker protege no Surface Hub, insira a chave do Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-173">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="9b1e1-174">Para descartar as informações protegidas, selecione **Ignorar esta unidade**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-174">To discard the protected information, select **Skip this drive**</span></span>  

8. <span data-ttu-id="9b1e1-175">Quando você for solicitado, selecione **Reinstalar.**</span><span class="sxs-lookup"><span data-stu-id="9b1e1-175">When you are prompted, select **Reinstall**.</span></span>

    ![Reinstalar](images/reinstall.png)

9. <span data-ttu-id="9b1e1-177">Para reparticionar o disco, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-177">To repartition the disk, select **Yes**.</span></span>

   ![Reparticionar](images/repartition.png)

   <span data-ttu-id="9b1e1-179">Primeiro, o processo de recuperação baixa a imagem do sistema operacional da nuvem.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-179">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![baixando 97&](images/recover-progress.png)

   <span data-ttu-id="9b1e1-181">Quando o download terminar, o processo de recuperação restaura o Surface Hub de acordo com as opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="9b1e1-181">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="9b1e1-182">Contate o Suporte</span><span class="sxs-lookup"><span data-stu-id="9b1e1-182">Contact Support</span></span>

<span data-ttu-id="9b1e1-183">Se você tiver dúvidas ou precisar de ajuda, poderá [criar uma solicitação de suporte.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="9b1e1-183">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="9b1e1-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9b1e1-184">Related topics</span></span>

[<span data-ttu-id="9b1e1-185">Gerenciar o Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9b1e1-185">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="9b1e1-186">Guia do administrador do Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9b1e1-186">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
