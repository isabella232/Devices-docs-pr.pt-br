---
title: Windows 10 para a configuração pós-instalação do Surface Hub 2
description: Windows 10 para a configuração pós-instalação do Surface Hub 2
keywords: Surface Hub, Windows 10, área de trabalho, instalar, configuração
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: d6a1cdb2cac01b48c80e0fa4b7ccb6d3bcdb76ac
ms.sourcegitcommit: 6618e8fe05628aa8b17654584657eff0f784dbfd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986344"
---
# <span data-ttu-id="ec1b1-104">Windows 10 para a configuração pós-instalação do Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="ec1b1-104">Windows 10 for Surface Hub 2 post-install configuration</span></span>

**<span data-ttu-id="ec1b1-105">Aplica-se a: Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="ec1b1-105">Applies to: Surface Hub 2S</span></span>** 

<span data-ttu-id="ec1b1-106">Depois de concluir o processo de instalação da migração para o Windows 10 pro ou Enterprise, você pode executar as seguintes etapas para definir aplicativos e configurações no Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-106">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="ec1b1-107">Essas etapas são recomendadas para garantir a melhor experiência ao usar esse computador de tela e o toque de tela grandes personalizados.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-107">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="ec1b1-108">Ao executar essas etapas, talvez seja útil usar um mouse e um teclado com fio ou sem fio.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-108">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="ec1b1-109">Definir configurações do sistema</span><span class="sxs-lookup"><span data-stu-id="ec1b1-109">Configure system settings</span></span>

1. <span data-ttu-id="ec1b1-110">Entre com uma conta que tenha privilégios de administrador local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-110">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="ec1b1-111">Nos dispositivos associados ao Azure AD, o usuário que executa a junção do Azure AD é automaticamente adicionado ao grupo administrador local.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-111">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="ec1b1-112">Os administradores globais do Azure AD e os administradores de dispositivos do Azure AD [também são administradores locais](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-112">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="ec1b1-113">Você pode digitar **net localgroup Administrators** em um prompt de comando para listar as contas que têm direitos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-113">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="ec1b1-114">Renomeie o dispositivo usando um nome amigável, por exemplo: **nome_do_usuário-SHub-área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-114">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="ec1b1-115">Selecione **Iniciar**  >  **configurações**  >  **contas**  >  **sincronizar suas configurações** e desativar **as configurações de sincronização** .</span><span class="sxs-lookup"><span data-stu-id="ec1b1-115">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="ec1b1-116">As configurações usadas aqui se destinam a habilitar a melhor experiência de toque em tela grande e, portanto, talvez você não queira sincronizar outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-116">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="ec1b1-117">Reinicialize o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-117">Reboot the device.</span></span>

## <span data-ttu-id="ec1b1-118">Habilitar o teclado virtual e o touchpad</span><span class="sxs-lookup"><span data-stu-id="ec1b1-118">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="ec1b1-119">Toque e segure ou clique com o botão direito do mouse na barra de tarefas e selecione **Mostrar botão do teclado virtual** e **botão Mostrar Touchpad**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="ec1b1-120">O teclado virtual é útil para entrada direta do usuário, e o touchpad virtual ajuda com seleções precisas, dicas de tela focalizadas ou como uma alternativa de tocar e segurar para clique com o botão direito do mouse.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="ec1b1-121">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-121">See the following example.</span></span>

     ![Configurações de toque](images/touch.png)

2. <span data-ttu-id="ec1b1-123">Configurar o teclado de toque para QWERTY e flutuante.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-123">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="ec1b1-124">Selecione o ícone de teclado na barra de tarefas para mostrar o teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-124">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="ec1b1-125">No teclado virtual, selecione o ícone de teclado no canto superior esquerdo para abrir as configurações de teclado.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="ec1b1-126">Selecione o próximo ao último tipo de teclado na linha superior para habilitar a QWERTY e a última opção na segunda linha para habilitar a flutuante, o que é muito útil nesta tela grande.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="ec1b1-127">Consulte os exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-127">See the following examples.</span></span>

     ![Configurações do teclado](images/kbd.png)

3. <span data-ttu-id="ec1b1-129">Defina as configurações do teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-129">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="ec1b1-130">Pesquisar e abrir **configurações de digitação**</span><span class="sxs-lookup"><span data-stu-id="ec1b1-130">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="ec1b1-131">Habilite todas as opções em ortografia, digitação e toque do teclado.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="ec1b1-132">O exemplo a seguir mostra o trackpad, que é útil para navegar e selecionar opções.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="ec1b1-133">O teclado na tela está sendo usado para pesquisar a Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Usando o trackpad](images/store.png)

## <span data-ttu-id="ec1b1-135">Configurar mouse e teclado Bluetooth (opcional)</span><span class="sxs-lookup"><span data-stu-id="ec1b1-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="ec1b1-136">Conecte um teclado e um mouse se estiver usando o dispositivo como seu dispositivo principal do Windows ou use-o com frequência para a digitação ou a precisão do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="ec1b1-137">Se o dispositivo do Surface Hub estiver próximo a um computador, você pode usar o [mouse sem bordas](https://aka.ms/mm) para se mover diretamente entre o Surface Hub e o computador.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-137">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="ec1b1-138">Para obter mais informações, consulte [o download da Microsoft na garagem: mouse sem bordas](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-138">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="ec1b1-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ec1b1-139">OneDrive for Business</span></span>

<span data-ttu-id="ec1b1-140">Use o [onedrive for Business](https://docs.microsoft.com/onedrive/onedrive) para compartilhar facilmente ferramentas, logs e outros arquivos entre todos os seus dispositivos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-140">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="ec1b1-141">O OneDrive permite que você compartilhe seus arquivos de trabalho entre seus laptops, a área de trabalho do Surface Hub e seus dispositivos móveis gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="ec1b1-142">Os arquivos podem ser editados em qualquer dispositivo, e todos os dispositivos conectados à rede serão atualizados com as alterações.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="ec1b1-143">Considerando o tamanho da SSD do Surface Hub (128 GB), se você configurar o OneDrive em seu dispositivo de área de trabalho do Surface Hub, verifique se a configuração padrão é manter os arquivos online e baixar os arquivos conforme você os usa.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="ec1b1-144">Para configurar o OneDrive para baixar arquivos somente quando necessário, defina a configuração de **arquivos sob demanda** para **economizar espaço e baixar arquivos conforme você os usa**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="ec1b1-145">Para obter mais informações, consulte [consultar e definir os Estados de arquivos sob demanda no Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-145">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![Configurações do OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="ec1b1-147">Você também pode repetir essas etapas para configurar um OneDrive pessoal, mas lembre-se de conservar o espaço da unidade e apenas baixar arquivos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="ec1b1-148">SharePoint e Teams</span><span class="sxs-lookup"><span data-stu-id="ec1b1-148">SharePoint and Teams</span></span>

<span data-ttu-id="ec1b1-149">Os arquivos de canal do SharePoint e do teams também podem ser sincronizados localmente com seus dispositivos de área de trabalho, como laptops e Surface Hub, usando o mecanismo de sincronização do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="ec1b1-150">Para sincronizar arquivos corporativos internos para sua unidade local com o aplicativo de sincronização do OneDrive:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="ec1b1-151">Vá para um site do SharePoint e navegue até o diretório de documentos de nível superior dos arquivos nos quais você está interessado em exibir ou editar a partir do seu dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="ec1b1-152">Selecione o botão **sincronizar** na parte superior da faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="ec1b1-153">Selecionar ao **abrir** no pop-up **este site está tentando abrir o Microsoft onedrive**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="ec1b1-154">Verifique se os arquivos do SharePoint estão sincronizando com a unidade local selecionando no ícone do OneDrive na parte inferior direita da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="ec1b1-155">Verifique se a configuração está definida para manter os arquivos online e baixe os arquivos somente quando você os usa:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="ec1b1-156">Abra o explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-156">Open file explorer.</span></span>
    2. <span data-ttu-id="ec1b1-157">Navegue para a direita e selecione na guia \*\*Microsoft \<SharePoint Document Folder Name\> \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-157">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="ec1b1-158">Selecione **liberar espaço**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-158">Select **Free up space**.</span></span>
    4. <span data-ttu-id="ec1b1-159">A coluna status mostrará o status de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="ec1b1-160">Para obter mais informações, consulte [sincronizar arquivos do SharePoint com o cliente de sincronização do onedrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-160">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="ec1b1-161">Os arquivos de canal de equipe são armazenados nos sites do SharePoint, com todas as mesmas funcionalidades de documentos do SharePoint, incluindo histórico de versão e sincronização para seus dispositivos de área de trabalho locais.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="ec1b1-162">Para sincronizar arquivos de canais de equipe:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-162">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="ec1b1-163">Navegue até o canal de interesse do Teams e selecione na guia **arquivos** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-163">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="ec1b1-164">Em seguida, selecione **sincronizar**. Os arquivos começarão a ser sincronizados e ficarão visíveis no explorador de arquivos da \*\*área \<name of the Teams Channel\> de trabalho \ Microsoft \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="ec1b1-165">Use o mesmo procedimento usado para sincronizar os sites do SharePoint para manter os arquivos na nuvem e apenas baixá-los quando forem usados, toque e segure ou clique com o botão direito do mouse no explorador de arquivos no nome do canal do Teams e, em seguida, selecione **liberar espaço**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="ec1b1-166">Emparelhar a caneta do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ec1b1-166">Pair the Surface Hub pen</span></span>

<span data-ttu-id="ec1b1-167">Para emparelhar o dispositivo de caneta:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-167">To pair the pen device:</span></span>

1. <span data-ttu-id="ec1b1-168">Selecione **Iniciar**  >  **configurações**de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-168">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="ec1b1-169">Selecione **Adicionar Bluetooth ou outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-169">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="ec1b1-170">Escolha **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-170">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="ec1b1-171">Remova o botão de cauda da caneta e agite para desconectar a conexão da bateria.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-171">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="ec1b1-172">Recoloque a tampa e pressione e segure a tampa até que o LED de emparelhamento pisque.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-172">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="ec1b1-173">Nas configurações de Bluetooth do Surface Hub, escolha **Surface Hub 2 caneta**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-173">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="ec1b1-174">Concluir a operação de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-174">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="ec1b1-175">Se o emparelhamento não for bem-sucedido, tente emparelhar a caneta novamente.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-175">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="ec1b1-176">Se necessário, reinicie o dispositivo e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-176">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="ec1b1-177">Configuração da câmera</span><span class="sxs-lookup"><span data-stu-id="ec1b1-177">Camera configuration</span></span>

<span data-ttu-id="ec1b1-178">Você pode montar a câmera na parte superior ou em qualquer um dos lados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-178">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="ec1b1-179">Monte a câmera em uma posição para otimizar o ângulo da câmera se você estiver usando o Hub com um suporte de área de trabalho em vez de um carrinho ou se estiver próximo ao Hub.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-179">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="ec1b1-180">A câmera não gira automaticamente, portanto você precisa ter uma chave hex 2mm para girar manualmente a câmera.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-180">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="ec1b1-181">Para saber mais sobre como montar a câmera lado a lado e girar a câmera manualmente, consulte [orientação do Surface Hub 2s orientação da lente da câmera](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-181">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="ec1b1-182">Configuração do Windows Hello</span><span class="sxs-lookup"><span data-stu-id="ec1b1-182">Windows Hello configuration</span></span>

<span data-ttu-id="ec1b1-183">O Surface Hub 2S executando o Windows 10 Enterprise permite o pacote completo de aplicativos da área de trabalho Win32, bem como as opções biométricas do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-183">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="ec1b1-184">O acessório de leitor de impressão digital Surface Hub 2 pode ser conectado a qualquer porta USB-C do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-184">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

> <i><span data-ttu-id="ec1b1-185">O leitor de impressão digital Surface Hub 2 estará disponível para compra em breve.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-185">The Surface Hub 2 Fingerprint Reader will be available for purchase soon.</span></span> <span data-ttu-id="ec1b1-186">Verifique novamente esta página para obter mais informações, incluindo como comprar.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-186">Please check back on this page for more information including how to purchase.</span></span></i>

<span data-ttu-id="ec1b1-187">Depois de inserir o leitor de impressão digital, selecione **Iniciar**  >  **configurações**  >  **conta**  >  **Opções de entrada**e  >  **impressão digital do Windows Hello** para registrar sua impressão digital.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-187">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="ec1b1-188">Use um dispositivo certificado com Windows Hello para o reconhecimento de rosto.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-188">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="ec1b1-189">A câmera Surface Hub 2S não dá suporte ao reconhecimento facial do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-189">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="ec1b1-190">Habilitar um ícone de atalho da tela de bloqueio na barra de tarefas</span><span class="sxs-lookup"><span data-stu-id="ec1b1-190">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="ec1b1-191">Para adicionar um ícone à barra de tarefas que permite o bloqueio de tela com um toque semelhante ao atalho de teclado do Windows-L:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-191">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="ec1b1-192">Toque e segure ou clique com o botão direito do mouse na área de trabalho, selecione **novo**  >  **atalho**  >  **navegar**na  >  **área de trabalho**  >  **OK**  >  **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-192">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>
2.  <span data-ttu-id="ec1b1-193">Forneça um nome para o atalho, como **bloquear meu PC**e, em seguida, selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-193">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>
3.  <span data-ttu-id="ec1b1-194">Clique com o botão direito do mouse ou toque e mantenha pressionado o atalho recém-criado na área de trabalho e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-194">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="ec1b1-195">Na guia **atalho** , insira o seguinte no campo de **destino** : **Rundll32.exe User32.dll, LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="ec1b1-195">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>
4.  <span data-ttu-id="ec1b1-196">Selecione o botão **Alterar ícone** e navegue até **C:\Windows\System32\imageres.dll** e selecione um ícone para usar.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-196">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 
5. <span data-ttu-id="ec1b1-197">Veja o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-197">See the following example:</span></span>

    ![Escolher um ícone](images/lock.png)
6.  <span data-ttu-id="ec1b1-199">Selecione **OK** para salvar o atalho.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-199">Select **OK** to save the shortcut.</span></span>
7.  <span data-ttu-id="ec1b1-200">Clique com o botão direito do mouse ou toque e segure o atalho e selecione **fixar na barra de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-200">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

## <span data-ttu-id="ec1b1-201">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="ec1b1-201">Applications</span></span>

### <span data-ttu-id="ec1b1-202">Atualizar aplicativos instalados</span><span class="sxs-lookup"><span data-stu-id="ec1b1-202">Update installed apps</span></span>

<span data-ttu-id="ec1b1-203">Para atualizar todos os aplicativos da loja instalados:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-203">To update all installed Store apps:</span></span>

1. <span data-ttu-id="ec1b1-204">Abra o aplicativo da Microsoft Store e selecione **Ver mais** reticências no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-204">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="ec1b1-205">Selecione **downloads e atualizações**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-205">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="ec1b1-206">Selecione **obter atualizações**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-206">Select **Get updates**.</span></span>

### <span data-ttu-id="ec1b1-207">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="ec1b1-207">Microsoft Whiteboard</span></span>

<span data-ttu-id="ec1b1-208">Para instalar o Microsoft whiteboard:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-208">To install the Microsoft Whiteboard:</span></span>

1. <span data-ttu-id="ec1b1-209">Selecione o ícone do **espaço de trabalho do Windows Ink** ![ espaço de trabalho ](images/ink.png) de tinta no canto inferior direito da barra de tarefas e baixe o **quadro de comunicações**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-209">Select the **Windows Ink Workspace** icon ![Ink workspace](images/ink.png) on the lower right of the taskbar and download **Whiteboard**.</span></span>

<span data-ttu-id="ec1b1-210">Você também pode instalar o whiteboard na Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-210">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="ec1b1-211">Abra o aplicativo da Microsoft Store e pesquise por **whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-211">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="ec1b1-212">Escolha **não graças** para entrar e usar entre dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-212">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="ec1b1-213">Fixar quadro de comunicações na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-213">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="ec1b1-214">Aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="ec1b1-214">Surface app</span></span>

1. <span data-ttu-id="ec1b1-215">Na Microsoft Store, procure por **Surface**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-215">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="ec1b1-216">Defina o filtro **disponível em** **todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-216">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="ec1b1-217">Instale o aplicativo **Surface** .</span><span class="sxs-lookup"><span data-stu-id="ec1b1-217">Install the **Surface** app.</span></span> <span data-ttu-id="ec1b1-218">Este deve ser o primeiro aplicativo listado.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-218">This should be the first app listed.</span></span> <span data-ttu-id="ec1b1-219">Talvez seja necessário associar o MSA à loja para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-219">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="ec1b1-220">Fixar o aplicativo **Surface** à barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-220">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="ec1b1-221">Esboço de recorte &</span><span class="sxs-lookup"><span data-stu-id="ec1b1-221">Snip & Sketch</span></span>

1. <span data-ttu-id="ec1b1-222">Abra o aplicativo **corte & esboço** e fixe-o na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-222">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="ec1b1-223">Selecione as reticências no canto superior direito e selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-223">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="ec1b1-224">Em **configurações**, ative **a cópia automática para a área de transferência**, **salve recortes**e **várias janelas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-224">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="ec1b1-225">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="ec1b1-225">Microsoft Office</span></span>

1. <span data-ttu-id="ec1b1-226">Abra o [portal do Office](https://portal.office.com/account#installs) e instale os aplicativos desejados.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-226">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="ec1b1-227">Fixar aplicativos do Office desejados na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-227">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="ec1b1-228">Se o Outlook estiver instalado, certifique-se de definir o OST do Outlook para salvar somente as últimas duas últimas semanas do cache.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-228">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="ec1b1-229">Isso reduzirá consideravelmente o uso do disco e o tempo de configuração.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-229">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="ec1b1-230">Selecione **File**  >  **configurações de conta** de arquivo e selecione sua conta.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-230">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="ec1b1-231">Selecione **alterar** e defina o controle deslizante para **usar o modo cache do Exchange** como 14 dias.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-231">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="ec1b1-232">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec1b1-232">Microsoft Teams</span></span>

1. <span data-ttu-id="ec1b1-233">Baixe e instale [o Microsoft Teams](https://teams.microsoft.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-233">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="ec1b1-234">Definir configurações para iniciar o aplicativo automaticamente (opcional).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-234">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="ec1b1-235">Fixar equipes na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-235">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="ec1b1-236">Considere reduzir as notificações do Microsoft Teams no dispositivo para evitar distrações (opcional).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-236">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![Notificações do teams](images/teams.png)

### <span data-ttu-id="ec1b1-238">Conectar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="ec1b1-238">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec1b1-239">No Windows 10, versão 2004 e posterior, a projeção conectar aplicativo para conexão sem fio que usa Miracast não é instalada por padrão, mas está disponível como um recurso opcional.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-239">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="ec1b1-240">Para instalar o aplicativo, selecione **configurações**  >  **aplicativos aplicativos**  >  **opcionais**  >  **adicione um recurso** e instale o aplicativo de **exibição sem fio** .</span><span class="sxs-lookup"><span data-stu-id="ec1b1-240">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="ec1b1-241">Procure **conexão**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-241">Search for **Connect**.</span></span>
2. <span data-ttu-id="ec1b1-242">Abra o aplicativo e feche-o (o**Project para este computador** pode não funcionar, a menos que o aplicativo tenha sido executado pelo menos uma vez).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-242">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="ec1b1-243">Toque e segure ou clique com o botão direito do mouse para fixar à barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-243">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="ec1b1-244">Pesquisar **configurações de projeção**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-244">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="ec1b1-245">Em **alguns dispositivos Windows e Android podem projetar neste computador quando você disser que está ok**, escolha **disponível em qualquer lugar** se o dispositivo não estiver em uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-245">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="ec1b1-246">Caso contrário, você pode escolher **disponível em todos os lugares em redes seguras**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-246">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="ec1b1-247">Em **pedir projeto para este PC**, escolha **primeira vez apenas**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-247">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="ec1b1-248">Em **exigir PIN para emparelhamento**, escolha **nunca**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-248">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="ec1b1-249">Configuração recomendada quando não estiver na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-249">Recommended configuration when not on the corporate network:</span></span>

  ![Configurações em casa](images/project1.png)

<span data-ttu-id="ec1b1-251">Configuração recomendada na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-251">Recommended configuration on the corporate network:</span></span>

  ![Configurações no trabalho](images/project2.png)

### <span data-ttu-id="ec1b1-253">Seu Telefone</span><span class="sxs-lookup"><span data-stu-id="ec1b1-253">Your Phone</span></span>

<span data-ttu-id="ec1b1-254">O aplicativo de **telefone** é instalado por padrão no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-254">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="ec1b1-255">Se não estiver presente, você também poderá instalá-lo na Windows Store.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-255">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="ec1b1-256">Para obter informações sobre como configurar o aplicativo, consulte [como configurar seu telefone no Windows 10 e sincronizar dados entre seu PC e telefone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-256">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="ec1b1-257">Veja também [como corrigir problemas comuns com o aplicativo de telefone no Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-257">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="ec1b1-258">Zonas super sofisticadas</span><span class="sxs-lookup"><span data-stu-id="ec1b1-258">Super Fancy Zones</span></span>

<span data-ttu-id="ec1b1-259">As **zonas Supersofisticadas** ajudam os usuários a organizar o Windows para maximizar o estado real da tela.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-259">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="ec1b1-260">Agora ele está incluído em [PowerToys](https://github.com/microsoft/PowerToys/releases) no github.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-260">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="ec1b1-261">Navegador do Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="ec1b1-261">Edge Chromium browser</span></span>

<span data-ttu-id="ec1b1-262">Baixe e instale o novo [navegador Chromium do Edge](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-262">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="ec1b1-263">Configurações adicionais</span><span class="sxs-lookup"><span data-stu-id="ec1b1-263">Additional settings</span></span>

### <span data-ttu-id="ec1b1-264">Cauda da caneta selecione para iniciar o quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="ec1b1-264">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="ec1b1-265">Procure **caneta** e selecione **caneta & configurações de tinta do Windows**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-265">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="ec1b1-266">Próximo à parte inferior da página, em **atalhos de caneta** , defina **selecionar uma vez** para o **Microsoft whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-266">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="ec1b1-267">Configurações de energia e suspensão</span><span class="sxs-lookup"><span data-stu-id="ec1b1-267">Power and sleep settings</span></span>

1. <span data-ttu-id="ec1b1-268">Selecione **Iniciar**  >  **configurações**  >  **sistema**  >  **alimentação & suspender**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-268">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="ec1b1-269">Defina o controle deslizante do modo de energia para **obter o melhor desempenho**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-269">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="ec1b1-270">Configure os valores de tela e de repouso para sua preferência.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-270">Configure screen and sleep values to your preference.</span></span>

### <span data-ttu-id="ec1b1-271">Proteção de tela</span><span class="sxs-lookup"><span data-stu-id="ec1b1-271">Screen saver</span></span>

1. <span data-ttu-id="ec1b1-272">Pesquisar a **tela de bloqueio** e abrir **as configurações da tela de bloqueio**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-272">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="ec1b1-273">Defina **as configurações de tempo limite de tela** e **as configurações de proteção de tela** para sua preferência.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-273">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="ec1b1-274">Sensor de armazenamento</span><span class="sxs-lookup"><span data-stu-id="ec1b1-274">Storage Sense</span></span>

<span data-ttu-id="ec1b1-275">O Surface Hub 2 tem uma SSD de 128 GB para armazenamento local, portanto, é necessário considerar o uso das medidas de salvamento de armazenamento durante o uso normal.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-275">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="ec1b1-276">Para configurar o sensor de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-276">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="ec1b1-277">Procure **configurações de armazenamento**, que se encontra em **configurações do sistema**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-277">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="ec1b1-278">Em **configurações**, selecione **ativar o sensor de armazenamento** para abrir a página Configurações de **armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="ec1b1-278">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="ec1b1-279">Mude o sensor de armazenamento para **ligado**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-279">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="ec1b1-280">Selecione **Configurar o sensor de armazenamento ou executá-lo agora** e defina as configurações para manter os arquivos online o máximo possível (devido a espaço limitado na unidade).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-280">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="ec1b1-281">Configurações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="ec1b1-281">Recommended settings:</span></span>
- <span data-ttu-id="ec1b1-282">Executar detecção de armazenamento = todos os dias.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-282">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="ec1b1-283">Exclua os arquivos temporários que os meus aplicativos não estão usando = a cada 14 dias (pelo menos).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-283">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="ec1b1-284">Exclua os arquivos na pasta Meus downloads se eles estiverem lá por mais de = 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-284">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="ec1b1-285">OneDrive: o conteúdo ficará online apenas se não for aberto por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-285">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="ec1b1-286">Modo tablet</span><span class="sxs-lookup"><span data-stu-id="ec1b1-286">Tablet mode</span></span>

<span data-ttu-id="ec1b1-287">Ative o modo tablet, se quiser, para atender às necessidades de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-287">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="ec1b1-288">Gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="ec1b1-288">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="ec1b1-289">Antes de executar o procedimento a seguir, verifique com seu departamento de ti para aprovação para excluir um dispositivo Surface Hub 2S da política global de gerenciamento de energia.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-289">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="ec1b1-290">Algumas configurações de gerenciamento de energia podem desabilitar a função de detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-290">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="ec1b1-291">Procure pela **central de software** e abra-a.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-291">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="ec1b1-292">Selecione **Opções** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-292">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="ec1b1-293">Expanda a seção **Gerenciamento de energia** e marque a caixa de seleção **não aplicar configurações de energia do meu departamento de ti a este computador**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-293">Expand the **Power management** section and select the checkbox **Do not apply power settings from my IT department to this computer**.</span></span>

  ![Configurações de software](images/soft-cntr.png)

### <span data-ttu-id="ec1b1-295">Configurações de som</span><span class="sxs-lookup"><span data-stu-id="ec1b1-295">Sound settings</span></span>

1. <span data-ttu-id="ec1b1-296">Procure **configurações de sons** e abra esta página.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-296">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="ec1b1-297">Selecione o **painel de controle de som** à direita e selecione a guia **sons** .</span><span class="sxs-lookup"><span data-stu-id="ec1b1-297">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="ec1b1-298">Em **eventos do programa** , defina **conexão do dispositivo** e **dispositivo desconectar** para **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-298">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="ec1b1-299">Notificações de silêncio</span><span class="sxs-lookup"><span data-stu-id="ec1b1-299">Silence notifications</span></span>

1. <span data-ttu-id="ec1b1-300">Pesquise o **Assistente de foco** e abra esta página.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-300">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="ec1b1-301">Selecione **apenas alarmes**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-301">Select **Alarms Only**.</span></span> <span data-ttu-id="ec1b1-302">Isso evitará submenus de notificação constante.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-302">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="ec1b1-303">Limpeza de Disco</span><span class="sxs-lookup"><span data-stu-id="ec1b1-303">Disk Cleanup</span></span>

1. <span data-ttu-id="ec1b1-304">Procure por **limpeza de disco** e abra este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-304">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="ec1b1-305">Em **arquivos a serem excluídos**, selecione os arquivos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-305">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="ec1b1-306">Além disso, selecione **limpar arquivos do sistema**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-306">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="ec1b1-307">Concluir e verificar</span><span class="sxs-lookup"><span data-stu-id="ec1b1-307">Complete and verify</span></span>

1. <span data-ttu-id="ec1b1-308">Procure e instale todas as atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-308">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="ec1b1-309">Atualizar política de grupo</span><span class="sxs-lookup"><span data-stu-id="ec1b1-309">Update Group Policy</span></span>
    1. <span data-ttu-id="ec1b1-310">Em um prompt de comando elevado, digite **gpupdate/force/boot/Wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-310">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="ec1b1-311">Reinicialize o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-311">Reboot the device.</span></span>
4. <span data-ttu-id="ec1b1-312">Verifique os aplicativos da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-312">Verify taskbar apps.</span></span>
    - <span data-ttu-id="ec1b1-313">Conectar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="ec1b1-313">Connect App</span></span>
    - <span data-ttu-id="ec1b1-314">Ícone de cadeado</span><span class="sxs-lookup"><span data-stu-id="ec1b1-314">Lock Icon</span></span>
    - <span data-ttu-id="ec1b1-315">Esboço de recorte &</span><span class="sxs-lookup"><span data-stu-id="ec1b1-315">Snip & Sketch</span></span>
    - <span data-ttu-id="ec1b1-316">Equipes (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="ec1b1-316">Teams (if applicable)</span></span>
    - <span data-ttu-id="ec1b1-317">Aplicativos do Office (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="ec1b1-317">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="ec1b1-318">Aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="ec1b1-318">Surface App</span></span>
    - <span data-ttu-id="ec1b1-319">Quadro de Comunicações</span><span class="sxs-lookup"><span data-stu-id="ec1b1-319">Whiteboard</span></span>
5. <span data-ttu-id="ec1b1-320">Verificar a detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-320">Verify presence detection.</span></span>
    - <span data-ttu-id="ec1b1-321">A detecção de presença será um ícone verde na bandeja do sistema</span><span class="sxs-lookup"><span data-stu-id="ec1b1-321">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="ec1b1-322">Verifique se a projeção neste computador está habilitada com o aplicativo conectar (o aplicativo não precisa estar em execução antes de conectar).</span><span class="sxs-lookup"><span data-stu-id="ec1b1-322">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="ec1b1-323">Verifique as configurações de energia e suspensão.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-323">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="ec1b1-324">Proteção de tela: 15 minutos, definir como (nenhum), polígonos ou ficar em branco; a caixa de seleção para exigir a senha está marcada</span><span class="sxs-lookup"><span data-stu-id="ec1b1-324">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="ec1b1-325">Tela: 2 horas</span><span class="sxs-lookup"><span data-stu-id="ec1b1-325">Screen: 2 hours</span></span>
    - <span data-ttu-id="ec1b1-326">PC: 4 horas</span><span class="sxs-lookup"><span data-stu-id="ec1b1-326">PC: 4 hours</span></span>
8. <span data-ttu-id="ec1b1-327">Verifique se o Windows Hello está funcionando.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-327">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="ec1b1-328">Verifique as configurações de energia.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-328">Verify power settings.</span></span>
10. <span data-ttu-id="ec1b1-329">Verifique se a sincronização suas configurações está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-329">Verify sync your settings is disabled.</span></span>
11. <span data-ttu-id="ec1b1-330">Verifique os aplicativos de inicialização.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-330">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="ec1b1-331">Após a instalação e a configuração do Windows 10, o Surface Hub 2S pode ser gerenciado assim como qualquer outro dispositivo com o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ec1b1-331">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="ec1b1-332">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ec1b1-332">Related topics</span></span>

[<span data-ttu-id="ec1b1-333">Migrar para o Windows 10 pro ou Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="ec1b1-333">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
