---
title: Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2
description: Este artigo inclui recomendações para garantir a melhor experiência ao usar um computador com tela e um toque de tela grande personalizado.
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
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 10/01/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 68f3fe1eb2fba0673444510fc77d3f41e09144af
ms.sourcegitcommit: e0047f07c42b1e3cbd074b66a4704ea72e9d7bae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "11093891"
---
# <span data-ttu-id="12491-104">Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="12491-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="12491-105">Depois de concluir o processo de instalação da migração para o Windows 10 pro ou Enterprise, você pode executar as seguintes etapas para definir aplicativos e configurações no Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="12491-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="12491-106">Essas etapas são recomendadas para garantir a melhor experiência ao usar esse computador de tela e o toque de tela grandes personalizados.</span><span class="sxs-lookup"><span data-stu-id="12491-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="12491-107">Ao executar essas etapas, talvez seja útil usar um mouse e um teclado com fio ou sem fio.</span><span class="sxs-lookup"><span data-stu-id="12491-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="12491-108">Definir configurações do sistema</span><span class="sxs-lookup"><span data-stu-id="12491-108">Configure system settings</span></span>

1. <span data-ttu-id="12491-109">Entre com uma conta que tenha privilégios de administrador local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12491-109">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="12491-110">Nos dispositivos associados ao Azure AD, o usuário que executa a junção do Azure AD é automaticamente adicionado ao grupo administrador local.</span><span class="sxs-lookup"><span data-stu-id="12491-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="12491-111">Os administradores globais do Azure AD e os administradores de dispositivos do Azure AD [também são administradores locais](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="12491-111">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="12491-112">Você pode digitar **net localgroup Administrators** em um prompt de comando para listar as contas que têm direitos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="12491-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="12491-113">Renomeie o dispositivo usando um nome amigável, por exemplo: **nome_do_usuário-SHub-área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="12491-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="12491-114">Selecione **Iniciar**  >  **configurações**  >  **contas**  >  **sincronizar suas configurações** e desativar **as configurações de sincronização** .</span><span class="sxs-lookup"><span data-stu-id="12491-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="12491-115">As configurações usadas aqui se destinam a habilitar a melhor experiência de toque em tela grande e, portanto, talvez você não queira sincronizar outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="12491-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="12491-116">Reinicialize o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12491-116">Reboot the device.</span></span>

## <span data-ttu-id="12491-117">Habilitar o teclado virtual e o touchpad</span><span class="sxs-lookup"><span data-stu-id="12491-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="12491-118">Toque e segure ou clique com o botão direito do mouse na barra de tarefas e selecione **Mostrar botão do teclado virtual** e **botão Mostrar Touchpad**.</span><span class="sxs-lookup"><span data-stu-id="12491-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="12491-119">O teclado virtual é útil para entrada direta do usuário, e o touchpad virtual ajuda com seleções precisas, dicas de tela focalizadas ou como uma alternativa de tocar e segurar para clique com o botão direito do mouse.</span><span class="sxs-lookup"><span data-stu-id="12491-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="12491-120">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="12491-120">See the following example.</span></span>

     ![Configurações de toque](images/touch.png)

2. <span data-ttu-id="12491-122">Configurar o teclado de toque para QWERTY e flutuante.</span><span class="sxs-lookup"><span data-stu-id="12491-122">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="12491-123">Selecione o ícone de teclado na barra de tarefas para mostrar o teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="12491-123">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="12491-124">No teclado virtual, selecione o ícone de teclado no canto superior esquerdo para abrir as configurações de teclado.</span><span class="sxs-lookup"><span data-stu-id="12491-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="12491-125">Selecione o próximo ao último tipo de teclado na linha superior para habilitar a QWERTY e a última opção na segunda linha para habilitar a flutuante, o que é muito útil nesta tela grande.</span><span class="sxs-lookup"><span data-stu-id="12491-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="12491-126">Consulte os exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="12491-126">See the following examples.</span></span>

     ![Configurações do teclado](images/kbd.png)

3. <span data-ttu-id="12491-128">Defina as configurações do teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="12491-128">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="12491-129">Pesquisar e abrir **configurações de digitação**</span><span class="sxs-lookup"><span data-stu-id="12491-129">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="12491-130">Habilite todas as opções em ortografia, digitação e toque do teclado.</span><span class="sxs-lookup"><span data-stu-id="12491-130">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="12491-131">O exemplo a seguir mostra o trackpad, que é útil para navegar e selecionar opções.</span><span class="sxs-lookup"><span data-stu-id="12491-131">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="12491-132">O teclado na tela está sendo usado para pesquisar a Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="12491-132">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Usando o trackpad](images/store.png)

## <span data-ttu-id="12491-134">Configurar mouse e teclado Bluetooth (opcional)</span><span class="sxs-lookup"><span data-stu-id="12491-134">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="12491-135">Conecte um teclado e um mouse se estiver usando o dispositivo como seu dispositivo principal do Windows ou use-o com frequência para a digitação ou a precisão do trabalho.</span><span class="sxs-lookup"><span data-stu-id="12491-135">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="12491-136">Se o dispositivo do Surface Hub estiver próximo a um computador, você pode usar o [mouse sem bordas](https://aka.ms/mm) para se mover diretamente entre o Surface Hub e o computador.</span><span class="sxs-lookup"><span data-stu-id="12491-136">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="12491-137">Para obter mais informações, consulte [o download da Microsoft na garagem: mouse sem bordas](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span><span class="sxs-lookup"><span data-stu-id="12491-137">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="12491-138">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="12491-138">OneDrive for Business</span></span>

<span data-ttu-id="12491-139">Use o [onedrive for Business](https://docs.microsoft.com/onedrive/onedrive) para compartilhar facilmente ferramentas, logs e outros arquivos entre todos os seus dispositivos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="12491-139">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="12491-140">O OneDrive permite que você compartilhe seus arquivos de trabalho entre seus laptops, a área de trabalho do Surface Hub e seus dispositivos móveis gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="12491-140">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="12491-141">Os arquivos podem ser editados em qualquer dispositivo, e todos os dispositivos conectados à rede serão atualizados com as alterações.</span><span class="sxs-lookup"><span data-stu-id="12491-141">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="12491-142">Considerando o tamanho da SSD do Surface Hub (128 GB), se você configurar o OneDrive em seu dispositivo de área de trabalho do Surface Hub, verifique se a configuração padrão é manter os arquivos online e baixar os arquivos conforme você os usa.</span><span class="sxs-lookup"><span data-stu-id="12491-142">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="12491-143">Para configurar o OneDrive para baixar arquivos somente quando necessário, defina a configuração de **arquivos sob demanda** para **economizar espaço e baixar arquivos conforme você os usa**.</span><span class="sxs-lookup"><span data-stu-id="12491-143">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="12491-144">Para obter mais informações, consulte [consultar e definir os Estados de arquivos sob demanda no Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="12491-144">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![Configurações do OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="12491-146">Você também pode repetir essas etapas para configurar um OneDrive pessoal, mas lembre-se de conservar o espaço da unidade e apenas baixar arquivos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="12491-146">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="12491-147">SharePoint e Teams</span><span class="sxs-lookup"><span data-stu-id="12491-147">SharePoint and Teams</span></span>

<span data-ttu-id="12491-148">Os arquivos de canal do SharePoint e do teams também podem ser sincronizados localmente com seus dispositivos de área de trabalho, como laptops e Surface Hub, usando o mecanismo de sincronização do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="12491-148">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="12491-149">Para sincronizar arquivos corporativos internos para sua unidade local com o aplicativo de sincronização do OneDrive:</span><span class="sxs-lookup"><span data-stu-id="12491-149">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="12491-150">Vá para um site do SharePoint e navegue até o diretório de documentos de nível superior dos arquivos nos quais você está interessado em exibir ou editar a partir do seu dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="12491-150">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="12491-151">Selecione o botão **sincronizar** na parte superior da faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12491-151">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="12491-152">Selecionar ao **abrir** no pop-up **este site está tentando abrir o Microsoft onedrive**.</span><span class="sxs-lookup"><span data-stu-id="12491-152">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="12491-153">Verifique se os arquivos do SharePoint estão sincronizando com a unidade local selecionando no ícone do OneDrive na parte inferior direita da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-153">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="12491-154">Verifique se a configuração está definida para manter os arquivos online e baixe os arquivos somente quando você os usa:</span><span class="sxs-lookup"><span data-stu-id="12491-154">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="12491-155">Abra o explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="12491-155">Open file explorer.</span></span>
    2. <span data-ttu-id="12491-156">Navegue para a direita e selecione na guia \*\*Microsoft \<SharePoint Document Folder Name\> \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="12491-156">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="12491-157">Selecione **liberar espaço**.</span><span class="sxs-lookup"><span data-stu-id="12491-157">Select **Free up space**.</span></span>
    4. <span data-ttu-id="12491-158">A coluna status mostrará o status de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="12491-158">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="12491-159">Para obter mais informações, consulte [sincronizar arquivos do SharePoint com o cliente de sincronização do onedrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="12491-159">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="12491-160">Os arquivos de canal de equipe são armazenados nos sites do SharePoint, com todas as mesmas funcionalidades de documentos do SharePoint, incluindo histórico de versão e sincronização para seus dispositivos de área de trabalho locais.</span><span class="sxs-lookup"><span data-stu-id="12491-160">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="12491-161">Para sincronizar arquivos de canais de equipe:</span><span class="sxs-lookup"><span data-stu-id="12491-161">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="12491-162">Navegue até o canal de interesse do Teams e selecione na guia **arquivos** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="12491-162">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="12491-163">Em seguida, selecione **sincronizar**. Os arquivos começarão a ser sincronizados e ficarão visíveis no explorador de arquivos da \*\*área \<name of the Teams Channel\> de trabalho \ Microsoft \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="12491-163">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="12491-164">Use o mesmo procedimento usado para sincronizar os sites do SharePoint para manter os arquivos na nuvem e apenas baixá-los quando forem usados, toque e segure ou clique com o botão direito do mouse no explorador de arquivos no nome do canal do Teams e, em seguida, selecione **liberar espaço**.</span><span class="sxs-lookup"><span data-stu-id="12491-164">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="12491-165">Configurações da caneta do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="12491-165">Surface Hub pen settings</span></span>

**<span data-ttu-id="12491-166">Emparelhar a caneta do Hub da superfície Bluetooth</span><span class="sxs-lookup"><span data-stu-id="12491-166">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="12491-167">Emparelhe a caneta para manter o firmware da caneta atualizado e obter informações sobre a carga da bateria na página de configurações do dispositivo Bluetooth ou no aplicativo Surface:</span><span class="sxs-lookup"><span data-stu-id="12491-167">Pair the pen to keep the pen firmware up to date and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="12491-168">Selecione **Iniciar**  >  **configurações**de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="12491-168">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="12491-169">Selecione **Adicionar Bluetooth ou outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="12491-169">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="12491-170">Escolha **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="12491-170">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="12491-171">Remova o botão de cauda da caneta e agite para desconectar a conexão da bateria.</span><span class="sxs-lookup"><span data-stu-id="12491-171">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="12491-172">Recoloque a tampa e pressione e segure a tampa até que o LED de emparelhamento pisque.</span><span class="sxs-lookup"><span data-stu-id="12491-172">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="12491-173">Nas configurações de Bluetooth do Surface Hub, escolha **Surface Hub 2 caneta**.</span><span class="sxs-lookup"><span data-stu-id="12491-173">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="12491-174">Concluir a operação de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="12491-174">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="12491-175">Se o emparelhamento não for bem-sucedido, tente emparelhar a caneta novamente.</span><span class="sxs-lookup"><span data-stu-id="12491-175">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="12491-176">Se necessário, reinicie o dispositivo e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="12491-176">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="12491-177">Configuração da câmera</span><span class="sxs-lookup"><span data-stu-id="12491-177">Camera configuration</span></span>

<span data-ttu-id="12491-178">Você pode montar a câmera na parte superior ou em qualquer um dos lados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12491-178">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="12491-179">Monte a câmera em uma posição para otimizar o ângulo da câmera se você estiver usando o Hub com um suporte de área de trabalho em vez de um carrinho ou se estiver próximo ao Hub.</span><span class="sxs-lookup"><span data-stu-id="12491-179">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="12491-180">A câmera não gira automaticamente, portanto você precisa ter uma chave hex 2mm para girar manualmente a câmera.</span><span class="sxs-lookup"><span data-stu-id="12491-180">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="12491-181">Para saber mais sobre como montar a câmera lado a lado e girar a câmera manualmente, consulte [orientação do Surface Hub 2s orientação da lente da câmera](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span><span class="sxs-lookup"><span data-stu-id="12491-181">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="12491-182">Configuração do Windows Hello</span><span class="sxs-lookup"><span data-stu-id="12491-182">Windows Hello configuration</span></span>

<span data-ttu-id="12491-183">O Surface Hub 2S executando o Windows 10 Enterprise permite o pacote completo de aplicativos da área de trabalho Win32, bem como as opções biométricas do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="12491-183">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="12491-184">O acessório de leitor de impressão digital Surface Hub 2 pode ser conectado a qualquer porta USB-C do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12491-184">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="12491-185">Para solicitar um leitor de Surface Hub 2 ou exibir especificações técnicas, consulte [Complementos essenciais para o Windows 10 pro e Enterprise no Surface Hub 2](surface-hub-2-essential-add-ons.md).</span><span class="sxs-lookup"><span data-stu-id="12491-185">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see [Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2](surface-hub-2-essential-add-ons.md).</span></span> 

<span data-ttu-id="12491-186">Depois de inserir o leitor de impressão digital, selecione **Iniciar**  >  **configurações**  >  **conta**  >  **Opções de entrada**e  >  **impressão digital do Windows Hello** para registrar sua impressão digital.</span><span class="sxs-lookup"><span data-stu-id="12491-186">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="12491-187">Use um dispositivo certificado com Windows Hello para o reconhecimento de rosto.</span><span class="sxs-lookup"><span data-stu-id="12491-187">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="12491-188">A câmera Surface Hub 2S não dá suporte ao reconhecimento facial do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="12491-188">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="12491-189">Habilitar um ícone de atalho da tela de bloqueio na barra de tarefas</span><span class="sxs-lookup"><span data-stu-id="12491-189">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="12491-190">Para adicionar um ícone à barra de tarefas que permite o bloqueio de tela com um toque semelhante ao atalho de teclado do Windows-L:</span><span class="sxs-lookup"><span data-stu-id="12491-190">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="12491-191">Toque e segure ou clique com o botão direito do mouse na área de trabalho, selecione **novo**  >  **atalho**  >  **navegar**na  >  **área de trabalho**  >  **OK**  >  **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="12491-191">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="12491-192">Forneça um nome para o atalho, como **bloquear meu PC**e, em seguida, selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="12491-192">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="12491-193">Clique com o botão direito do mouse ou toque e mantenha pressionado o atalho recém-criado na área de trabalho e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="12491-193">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="12491-194">Na guia **atalho** , insira o seguinte no campo de **destino** : **Rundll32.exe User32.dll, LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="12491-194">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="12491-195">Selecione o botão **Alterar ícone** e navegue até **C:\Windows\System32\imageres.dll** e selecione um ícone para usar.</span><span class="sxs-lookup"><span data-stu-id="12491-195">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="12491-196">Veja o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="12491-196">See the following example:</span></span>

    ![Escolher um ícone](images/lock.png)
    
1.  <span data-ttu-id="12491-198">Selecione **OK** para salvar o atalho.</span><span class="sxs-lookup"><span data-stu-id="12491-198">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="12491-199">Clique com o botão direito do mouse ou toque e segure o atalho e selecione **fixar na barra de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="12491-199">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="12491-200">Depois de fixar o atalho de bloqueio à barra de tarefas, você pode excluí-lo da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="12491-200">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="12491-201">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="12491-201">Applications</span></span>

### <span data-ttu-id="12491-202">Atualizar aplicativos instalados</span><span class="sxs-lookup"><span data-stu-id="12491-202">Update installed apps</span></span>

<span data-ttu-id="12491-203">Para atualizar todos os aplicativos da loja instalados:</span><span class="sxs-lookup"><span data-stu-id="12491-203">To update all installed Store apps:</span></span>

1. <span data-ttu-id="12491-204">Abra o aplicativo da Microsoft Store e selecione **Ver mais** reticências no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="12491-204">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="12491-205">Selecione **Downloads e atualizações**.</span><span class="sxs-lookup"><span data-stu-id="12491-205">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="12491-206">Selecione **Obter atualizações**.</span><span class="sxs-lookup"><span data-stu-id="12491-206">Select **Get updates**.</span></span>

### <span data-ttu-id="12491-207">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="12491-207">Microsoft Whiteboard</span></span>

<span data-ttu-id="12491-208">Para instalar o Microsoft whiteboard:</span><span class="sxs-lookup"><span data-stu-id="12491-208">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="12491-209">Selecione o ícone do **espaço de trabalho do Windows Ink** no canto inferior direito da barra de tarefas e baixe o **whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="12491-209">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Espaço de trabalho à tinta](images/ink.png) 

<span data-ttu-id="12491-211">Você também pode instalar o whiteboard na Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="12491-211">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="12491-212">Abra o aplicativo da Microsoft Store e pesquise por **whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="12491-212">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="12491-213">Escolha **não graças** para entrar e usar entre dispositivos.</span><span class="sxs-lookup"><span data-stu-id="12491-213">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="12491-214">Fixar quadro de comunicações na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-214">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="12491-215">Aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="12491-215">Surface app</span></span>

1. <span data-ttu-id="12491-216">Na Microsoft Store, procure por **Surface**.</span><span class="sxs-lookup"><span data-stu-id="12491-216">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="12491-217">Defina o filtro **disponível em** **todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="12491-217">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="12491-218">Instale o aplicativo **Surface** .</span><span class="sxs-lookup"><span data-stu-id="12491-218">Install the **Surface** app.</span></span> <span data-ttu-id="12491-219">Este deve ser o primeiro aplicativo listado.</span><span class="sxs-lookup"><span data-stu-id="12491-219">This should be the first app listed.</span></span> <span data-ttu-id="12491-220">Talvez seja necessário associar o MSA à loja para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="12491-220">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="12491-221">Fixar o aplicativo **Surface** à barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-221">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="12491-222">Captura e Esboço</span><span class="sxs-lookup"><span data-stu-id="12491-222">Snip & Sketch</span></span>

1. <span data-ttu-id="12491-223">Abra o aplicativo **corte & esboço** e fixe-o na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-223">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="12491-224">Selecione as reticências no canto superior direito e selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="12491-224">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="12491-225">Em **configurações**, ative **a cópia automática para a área de transferência**, **salve recortes**e **várias janelas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="12491-225">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="12491-226">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="12491-226">Microsoft Office</span></span>

1. <span data-ttu-id="12491-227">Abra o [portal do Office](https://portal.office.com/account#installs) e instale os aplicativos desejados.</span><span class="sxs-lookup"><span data-stu-id="12491-227">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="12491-228">Fixar aplicativos do Office desejados na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-228">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="12491-229">Se o Outlook estiver instalado, certifique-se de definir o OST do Outlook para salvar somente as últimas duas últimas semanas do cache.</span><span class="sxs-lookup"><span data-stu-id="12491-229">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="12491-230">Isso reduzirá consideravelmente o uso do disco e o tempo de configuração.</span><span class="sxs-lookup"><span data-stu-id="12491-230">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="12491-231">Selecione **File**  >  **configurações de conta** de arquivo e selecione sua conta.</span><span class="sxs-lookup"><span data-stu-id="12491-231">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="12491-232">Selecione **alterar** e defina o controle deslizante para **usar o modo cache do Exchange** como 14 dias.</span><span class="sxs-lookup"><span data-stu-id="12491-232">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="12491-233">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12491-233">Microsoft Teams</span></span>

1. <span data-ttu-id="12491-234">Baixe e instale [o Microsoft Teams](https://teams.microsoft.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="12491-234">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="12491-235">Definir configurações para iniciar o aplicativo automaticamente (opcional).</span><span class="sxs-lookup"><span data-stu-id="12491-235">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="12491-236">Fixar equipes na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-236">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="12491-237">Considere reduzir as notificações do Microsoft Teams no dispositivo para evitar distrações (opcional).</span><span class="sxs-lookup"><span data-stu-id="12491-237">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![Notificações do teams](images/teams.png)

### <span data-ttu-id="12491-239">Conectar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="12491-239">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12491-240">No Windows 10, versão 2004 e posterior, a projeção conectar aplicativo para conexão sem fio que usa Miracast não é instalada por padrão, mas está disponível como um recurso opcional.</span><span class="sxs-lookup"><span data-stu-id="12491-240">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="12491-241">Para instalar o aplicativo, selecione **configurações**  >  **aplicativos aplicativos**  >  **opcionais**  >  **adicione um recurso** e instale o aplicativo de **exibição sem fio** .</span><span class="sxs-lookup"><span data-stu-id="12491-241">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="12491-242">Procure **conexão**.</span><span class="sxs-lookup"><span data-stu-id="12491-242">Search for **Connect**.</span></span>
2. <span data-ttu-id="12491-243">Abra o aplicativo e feche-o (o**Project para este computador** pode não funcionar, a menos que o aplicativo tenha sido executado pelo menos uma vez).</span><span class="sxs-lookup"><span data-stu-id="12491-243">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="12491-244">Toque e segure ou clique com o botão direito do mouse para fixar à barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-244">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="12491-245">Pesquisar **configurações de projeção**.</span><span class="sxs-lookup"><span data-stu-id="12491-245">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="12491-246">Em **alguns dispositivos Windows e Android podem projetar neste computador quando você disser que está ok**, escolha **disponível em qualquer lugar** se o dispositivo não estiver em uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="12491-246">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="12491-247">Caso contrário, você pode escolher **disponível em todos os lugares em redes seguras**.</span><span class="sxs-lookup"><span data-stu-id="12491-247">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="12491-248">Em **pedir projeto para este PC**, escolha **primeira vez apenas**.</span><span class="sxs-lookup"><span data-stu-id="12491-248">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="12491-249">Em **exigir PIN para emparelhamento**, escolha **nunca**.</span><span class="sxs-lookup"><span data-stu-id="12491-249">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="12491-250">Configuração recomendada quando não estiver na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="12491-250">Recommended configuration when not on the corporate network:</span></span>

  ![Configurações em casa](images/project1.png)

<span data-ttu-id="12491-252">Configuração recomendada na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="12491-252">Recommended configuration on the corporate network:</span></span>

  ![Configurações no trabalho](images/project2.png)

### <span data-ttu-id="12491-254">Seu Telefone</span><span class="sxs-lookup"><span data-stu-id="12491-254">Your Phone</span></span>

<span data-ttu-id="12491-255">O aplicativo de **telefone** é instalado por padrão no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="12491-255">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="12491-256">Se não estiver presente, você também poderá instalá-lo na Windows Store.</span><span class="sxs-lookup"><span data-stu-id="12491-256">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="12491-257">Para obter informações sobre como configurar o aplicativo, consulte [como configurar seu telefone no Windows 10 e sincronizar dados entre seu PC e telefone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="12491-257">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="12491-258">Veja também [como corrigir problemas comuns com o aplicativo de telefone no Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="12491-258">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="12491-259">Zonas super sofisticadas</span><span class="sxs-lookup"><span data-stu-id="12491-259">Super Fancy Zones</span></span>

<span data-ttu-id="12491-260">As **zonas Supersofisticadas** ajudam os usuários a organizar o Windows para maximizar o estado real da tela.</span><span class="sxs-lookup"><span data-stu-id="12491-260">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="12491-261">Agora ele está incluído em [PowerToys](https://github.com/microsoft/PowerToys/releases) no github.</span><span class="sxs-lookup"><span data-stu-id="12491-261">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="12491-262">Navegador do Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="12491-262">Edge Chromium browser</span></span>

<span data-ttu-id="12491-263">Baixe e instale o novo [navegador Chromium do Edge](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span><span class="sxs-lookup"><span data-stu-id="12491-263">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="12491-264">Configurações adicionais</span><span class="sxs-lookup"><span data-stu-id="12491-264">Additional settings</span></span>

### <span data-ttu-id="12491-265">Cauda da caneta selecione para iniciar o quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="12491-265">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="12491-266">Procure **caneta** e selecione **caneta & configurações de tinta do Windows**.</span><span class="sxs-lookup"><span data-stu-id="12491-266">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="12491-267">Próximo à parte inferior da página, em **atalhos de caneta** , defina **selecionar uma vez** para o **Microsoft whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="12491-267">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="12491-268">Gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="12491-268">Power management</span></span>

<span data-ttu-id="12491-269">Há várias configurações de energia disponíveis para obter a melhor experiência com o Windows 10 pro ou Enterprise no Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="12491-269">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="12491-270">Isso inclui tempos limite de tela e do PC e como eles interagem com a detecção de presença humana (Doppler) interna, a proteção de tela e a proteção por senha e, em seguida, se for apropriado como passar configurações de energia de política de grupo para usuários de laptop/desktop.</span><span class="sxs-lookup"><span data-stu-id="12491-270">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="12491-271">O Windows 10 pro ou Enterprise no Surface Hub 2 mantém a tela de entrar no estado de suspensão por ações de toque, mouse e teclado, além da detecção de ocupação humana interna (Doppler).</span><span class="sxs-lookup"><span data-stu-id="12491-271">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="12491-272">A detecção de ocupação humana é habilitada por padrão, mas, se desejado, pode ser desabilitada na UEFI alternando a opção de dispositivo na ferramenta configurador UEFI do Surface como parte da migração inicial ou criando e aplicando um pacote de configuração UEFI mais recente.</span><span class="sxs-lookup"><span data-stu-id="12491-272">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="12491-273">Gerenciamento de energia: configurações de tela e suspensão do computador</span><span class="sxs-lookup"><span data-stu-id="12491-273">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="12491-274">Selecione **Iniciar**  >  **configurações**  >  **sistema**  >  **alimentação & suspender**.</span><span class="sxs-lookup"><span data-stu-id="12491-274">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="12491-275">Defina o controle deslizante do modo de energia para **obter o melhor desempenho**.</span><span class="sxs-lookup"><span data-stu-id="12491-275">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="12491-276">Configure os valores de tela e de repouso para sua preferência enquanto também faz a Doppler de detecção de presença do que ativa o dispositivo quando o movimento é detectado.</span><span class="sxs-lookup"><span data-stu-id="12491-276">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="12491-277">Portanto, como prática recomendada, é recomendável definir a tela para desligar **após 2 horas** e o computador para **desligar após 4 horas.**</span><span class="sxs-lookup"><span data-stu-id="12491-277">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="12491-278">Gerenciamento de energia: proteção de tela</span><span class="sxs-lookup"><span data-stu-id="12491-278">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="12491-279">Pesquisar a **tela de bloqueio** e abrir **as configurações da tela de bloqueio**.</span><span class="sxs-lookup"><span data-stu-id="12491-279">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="12491-280">Defina **as configurações de tempo limite de tela** e **as configurações de proteção de tela** para sua preferência.</span><span class="sxs-lookup"><span data-stu-id="12491-280">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="12491-281">Sensor de armazenamento</span><span class="sxs-lookup"><span data-stu-id="12491-281">Storage Sense</span></span>

<span data-ttu-id="12491-282">O Surface Hub 2 tem uma SSD de 128 GB para armazenamento local, portanto, é necessário considerar o uso das medidas de salvamento de armazenamento durante o uso normal.</span><span class="sxs-lookup"><span data-stu-id="12491-282">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="12491-283">Para configurar o sensor de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="12491-283">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="12491-284">Procure **configurações de armazenamento**, que se encontra em **configurações do sistema**.</span><span class="sxs-lookup"><span data-stu-id="12491-284">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="12491-285">Em **configurações**, selecione **ativar o sensor de armazenamento** para abrir a página Configurações de **armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="12491-285">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="12491-286">Mude o sensor de armazenamento para **ligado**.</span><span class="sxs-lookup"><span data-stu-id="12491-286">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="12491-287">Selecione **Configurar o sensor de armazenamento ou executá-lo agora** e defina as configurações para manter os arquivos online o máximo possível (devido a espaço limitado na unidade).</span><span class="sxs-lookup"><span data-stu-id="12491-287">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="12491-288">Configurações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="12491-288">Recommended settings:</span></span>
- <span data-ttu-id="12491-289">Executar detecção de armazenamento = todos os dias.</span><span class="sxs-lookup"><span data-stu-id="12491-289">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="12491-290">Exclua os arquivos temporários que os meus aplicativos não estão usando = a cada 14 dias (pelo menos).</span><span class="sxs-lookup"><span data-stu-id="12491-290">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="12491-291">Exclua os arquivos na pasta Meus downloads se eles estiverem lá por mais de = 30 dias.</span><span class="sxs-lookup"><span data-stu-id="12491-291">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="12491-292">OneDrive: o conteúdo ficará online apenas se não for aberto por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="12491-292">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="12491-293">Modo tablet</span><span class="sxs-lookup"><span data-stu-id="12491-293">Tablet mode</span></span>

<span data-ttu-id="12491-294">Ative o modo tablet, se quiser, para atender às necessidades de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="12491-294">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="12491-295">Gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="12491-295">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="12491-296">Antes de executar o procedimento a seguir, verifique com seu departamento de ti para aprovação para excluir um dispositivo Surface Hub 2S da política global de gerenciamento de energia.</span><span class="sxs-lookup"><span data-stu-id="12491-296">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="12491-297">Algumas configurações de gerenciamento de energia podem desabilitar a função de detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="12491-297">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="12491-298">Procure pela **central de software** e abra-a.</span><span class="sxs-lookup"><span data-stu-id="12491-298">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="12491-299">Selecione **Opções** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="12491-299">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="12491-300">Expanda a seção **Gerenciamento de energia** e selecione **não aplicar configurações de energia do meu departamento de ti para este computador**.</span><span class="sxs-lookup"><span data-stu-id="12491-300">Expand the **Power management** section and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Configurações de software](images/soft-cntr.png)

### <span data-ttu-id="12491-302">Configurações de som</span><span class="sxs-lookup"><span data-stu-id="12491-302">Sound settings</span></span>

1. <span data-ttu-id="12491-303">Procure **configurações de sons** e abra esta página.</span><span class="sxs-lookup"><span data-stu-id="12491-303">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="12491-304">Selecione o **painel de controle de som** à direita e selecione a guia **sons** .</span><span class="sxs-lookup"><span data-stu-id="12491-304">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="12491-305">Em **eventos do programa** , defina **conexão do dispositivo** e **dispositivo desconectar** para **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="12491-305">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="12491-306">Notificações de silêncio</span><span class="sxs-lookup"><span data-stu-id="12491-306">Silence notifications</span></span>

1. <span data-ttu-id="12491-307">Pesquise o **Assistente de foco** e abra esta página.</span><span class="sxs-lookup"><span data-stu-id="12491-307">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="12491-308">Selecione **apenas alarmes**.</span><span class="sxs-lookup"><span data-stu-id="12491-308">Select **Alarms Only**.</span></span> <span data-ttu-id="12491-309">Isso evitará submenus de notificação constante.</span><span class="sxs-lookup"><span data-stu-id="12491-309">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="12491-310">Limpeza de Disco</span><span class="sxs-lookup"><span data-stu-id="12491-310">Disk Cleanup</span></span>

1. <span data-ttu-id="12491-311">Procure por **limpeza de disco** e abra este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="12491-311">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="12491-312">Em **arquivos a serem excluídos**, selecione os arquivos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="12491-312">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="12491-313">Além disso, selecione **limpar arquivos do sistema**.</span><span class="sxs-lookup"><span data-stu-id="12491-313">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="12491-314">Concluir e verificar</span><span class="sxs-lookup"><span data-stu-id="12491-314">Complete and verify</span></span>

1. <span data-ttu-id="12491-315">Procure e instale todas as atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="12491-315">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="12491-316">Atualizar política de grupo</span><span class="sxs-lookup"><span data-stu-id="12491-316">Update Group Policy</span></span>
    1. <span data-ttu-id="12491-317">Em um prompt de comando elevado, digite **gpupdate/force/boot/Wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="12491-317">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="12491-318">Reinicialize o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12491-318">Reboot the device.</span></span>
4. <span data-ttu-id="12491-319">Verifique os aplicativos da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="12491-319">Verify taskbar apps.</span></span>
    - <span data-ttu-id="12491-320">Conectar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="12491-320">Connect App</span></span>
    - <span data-ttu-id="12491-321">Ícone de cadeado</span><span class="sxs-lookup"><span data-stu-id="12491-321">Lock Icon</span></span>
    - <span data-ttu-id="12491-322">Captura e Esboço</span><span class="sxs-lookup"><span data-stu-id="12491-322">Snip & Sketch</span></span>
    - <span data-ttu-id="12491-323">Equipes (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="12491-323">Teams (if applicable)</span></span>
    - <span data-ttu-id="12491-324">Aplicativos do Office (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="12491-324">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="12491-325">Aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="12491-325">Surface App</span></span>
    - <span data-ttu-id="12491-326">Quadro de Comunicações</span><span class="sxs-lookup"><span data-stu-id="12491-326">Whiteboard</span></span>
5. <span data-ttu-id="12491-327">Verificar a detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="12491-327">Verify presence detection.</span></span>
    - <span data-ttu-id="12491-328">A detecção de presença será um ícone verde na bandeja do sistema</span><span class="sxs-lookup"><span data-stu-id="12491-328">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="12491-329">Verifique se a projeção neste computador está habilitada com o aplicativo conectar (o aplicativo não precisa estar em execução antes de conectar).</span><span class="sxs-lookup"><span data-stu-id="12491-329">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="12491-330">Verifique as configurações de energia e suspensão.</span><span class="sxs-lookup"><span data-stu-id="12491-330">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="12491-331">Proteção de tela: 15 minutos, definir como (nenhum), polígonos ou ficar em branco; a caixa de seleção para exigir a senha está marcada</span><span class="sxs-lookup"><span data-stu-id="12491-331">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="12491-332">Tela: **desative após 2 horas.**</span><span class="sxs-lookup"><span data-stu-id="12491-332">Screen: **Turn off after 2 hours.**</span></span>
    - <span data-ttu-id="12491-333">PC:  **desative após 4 horas.**</span><span class="sxs-lookup"><span data-stu-id="12491-333">PC:  **Turn off after 4 hours.**</span></span>
8. <span data-ttu-id="12491-334">Verifique se o Windows Hello está funcionando.</span><span class="sxs-lookup"><span data-stu-id="12491-334">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="12491-335">Verifique se a sincronização suas configurações está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="12491-335">Verify sync your settings is disabled.</span></span>
10. <span data-ttu-id="12491-336">Verifique os aplicativos de inicialização.</span><span class="sxs-lookup"><span data-stu-id="12491-336">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="12491-337">Após a instalação e a configuração do Windows 10, o Surface Hub 2S pode ser gerenciado assim como qualquer outro dispositivo com o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="12491-337">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="12491-338">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="12491-338">Related topics</span></span>

[<span data-ttu-id="12491-339">Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="12491-339">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
