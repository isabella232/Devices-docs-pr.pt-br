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
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203544"
---
# <span data-ttu-id="19a0b-104">Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="19a0b-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="19a0b-105">Depois de concluir o processo de instalação da migração para o Windows 10 pro ou Enterprise, você pode executar as seguintes etapas para definir aplicativos e configurações no Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="19a0b-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="19a0b-106">Essas etapas são recomendadas para garantir a melhor experiência ao usar esse computador de tela e o toque de tela grandes personalizados.</span><span class="sxs-lookup"><span data-stu-id="19a0b-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="19a0b-107">Ao executar essas etapas, talvez seja útil usar um mouse e um teclado com fio ou sem fio.</span><span class="sxs-lookup"><span data-stu-id="19a0b-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="19a0b-108">Definir configurações do sistema</span><span class="sxs-lookup"><span data-stu-id="19a0b-108">Configure system settings</span></span>

1. <span data-ttu-id="19a0b-109">Entre com uma conta que tenha privilégios de administrador local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="19a0b-110">Nos dispositivos associados ao Azure AD, o usuário que executa a junção do Azure AD é automaticamente adicionado ao grupo administrador local.</span><span class="sxs-lookup"><span data-stu-id="19a0b-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="19a0b-111">Os administradores globais do Azure AD e os administradores de dispositivos do Azure AD <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> também são administradores locais </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="19a0b-112">Você pode digitar **net localgroup Administrators** em um prompt de comando para listar as contas que têm direitos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="19a0b-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="19a0b-113">Renomeie o dispositivo usando um nome amigável, por exemplo: **nome_do_usuário-SHub-área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="19a0b-114">Selecione **Iniciar**  >  **configurações**  >  **contas**  >  **sincronizar suas configurações** e desativar **as configurações de sincronização** .</span><span class="sxs-lookup"><span data-stu-id="19a0b-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="19a0b-115">As configurações usadas aqui se destinam a habilitar a melhor experiência de toque em tela grande e, portanto, talvez você não queira sincronizar outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="19a0b-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="19a0b-116">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-116">Restart the device.</span></span>

## <span data-ttu-id="19a0b-117">Habilitar o teclado virtual e o touchpad</span><span class="sxs-lookup"><span data-stu-id="19a0b-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="19a0b-118">Toque e segure ou clique com o botão direito do mouse na barra de tarefas e selecione **Mostrar botão do teclado virtual** e **botão Mostrar Touchpad**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="19a0b-119">O teclado virtual é útil para entrada direta do usuário, e o touchpad virtual ajuda com seleções precisas, dicas de tela focalizadas ou como uma alternativa de tocar e segurar para clique com o botão direito do mouse.</span><span class="sxs-lookup"><span data-stu-id="19a0b-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="19a0b-120">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="19a0b-120">See the following example.</span></span>

      ![Configurações de toque](images/touch.png)

2. <span data-ttu-id="19a0b-122">Configurar o teclado de toque para QWERTY e flutuante.</span><span class="sxs-lookup"><span data-stu-id="19a0b-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="19a0b-123">Selecione o ícone de **teclado** na barra de tarefas para mostrar o teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="19a0b-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="19a0b-124">No teclado virtual, selecione o ícone de teclado no canto superior esquerdo para abrir as configurações de teclado.</span><span class="sxs-lookup"><span data-stu-id="19a0b-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="19a0b-125">Selecione o próximo ao último tipo de teclado na linha superior para habilitar a QWERTY e a última opção na segunda linha para habilitar a flutuante, o que é muito útil nesta tela grande.</span><span class="sxs-lookup"><span data-stu-id="19a0b-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="19a0b-126">Consulte os exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="19a0b-126">See the following examples.</span></span>

       ![Configurações do teclado](images/kbd.png)
 
3. <span data-ttu-id="19a0b-128">Defina as configurações do teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="19a0b-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="19a0b-129">Selecione o ícone **configurações** no teclado virtual ou procure e abra configurações de **digitação**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![configurações do teclado virtual](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="19a0b-131">Habilite todas as opções em ortografia, digitação e toque do teclado.</span><span class="sxs-lookup"><span data-stu-id="19a0b-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="19a0b-132">O exemplo a seguir mostra o trackpad, que é útil para navegar e selecionar opções.</span><span class="sxs-lookup"><span data-stu-id="19a0b-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="19a0b-133">O teclado na tela está sendo usado para pesquisar a Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="19a0b-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Usando o trackpad](images/store.png)

## <span data-ttu-id="19a0b-135">Configurar mouse e teclado Bluetooth (opcional)</span><span class="sxs-lookup"><span data-stu-id="19a0b-135">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="19a0b-136">Conecte um teclado e um mouse se estiver usando o dispositivo como seu dispositivo principal do Windows ou use-o com frequência para a digitação ou a precisão do trabalho.</span><span class="sxs-lookup"><span data-stu-id="19a0b-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="19a0b-137">Se o dispositivo do Surface Hub estiver próximo a um computador, você pode usar <a href="https://aka.ms/mm" target="_blank"> o mouse sem bordas </a> para se mover diretamente entre o Surface Hub e o computador.</span><span class="sxs-lookup"><span data-stu-id="19a0b-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="19a0b-138">Para obter mais informações, consulte <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> o download da Microsoft na garagem: mouse sem bordas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="19a0b-139">Exemplo de layout da barra de tarefas</span><span class="sxs-lookup"><span data-stu-id="19a0b-139">Example of Taskbar layout</span></span>

<span data-ttu-id="19a0b-140">Depois de concluir as etapas abaixo para configurar/configurar o Surface Hub 2 para Windows 10 Professional ou Enterprise, recomendamos que você use a fixação dos aplicativos mais usados para a barra de tarefas para uma inicialização rápida com um só toque de cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-140">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="19a0b-141">Veja a seguir um exemplo de como a barra de tarefas poderia se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="19a0b-141">Below is an example of what your taskbar could look like:</span></span>

 ![Layout da barra de tarefas](images/taskblyt.png)
### <span data-ttu-id="19a0b-143">Atualizar aplicativos instalados</span><span class="sxs-lookup"><span data-stu-id="19a0b-143">Update installed apps</span></span>

<span data-ttu-id="19a0b-144">Para atualizar todos os aplicativos da loja instalados:</span><span class="sxs-lookup"><span data-stu-id="19a0b-144">To update all installed Store apps:</span></span>

1. <span data-ttu-id="19a0b-145">Abra o aplicativo da Microsoft Store e selecione **Ver mais** reticências no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="19a0b-145">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="19a0b-146">Selecione **downloads e atualizações.**</span><span class="sxs-lookup"><span data-stu-id="19a0b-146">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="19a0b-147">Selecione **obter atualizações**</span><span class="sxs-lookup"><span data-stu-id="19a0b-147">Select **Get updates**</span></span>

### <span data-ttu-id="19a0b-148">Procurar e instalar todas as atualizações do Windows</span><span class="sxs-lookup"><span data-stu-id="19a0b-148">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="19a0b-149">Após a migração para o Windows 10 Professional ou Windows 10 Enterprise, talvez haja atualizações de serviço e manutenção disponíveis para você instalar.</span><span class="sxs-lookup"><span data-stu-id="19a0b-149">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="19a0b-150">Vá para **configurações**  >  **Atualizar &** > de segurança e, em seguida, selecione **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-150">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="19a0b-151">Se houver alguma atualização, instale-a, reinicialize e repita o processo até que você veja a seguinte notificação:</span><span class="sxs-lookup"><span data-stu-id="19a0b-151">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Notificação do Windows Update ' você está atualizado '](images/wustatus.png)


## <span data-ttu-id="19a0b-153">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="19a0b-153">OneDrive for Business</span></span>

<span data-ttu-id="19a0b-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> o onedrive for Business </a> para compartilhar facilmente ferramentas, logs e outros arquivos entre todos os seus dispositivos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="19a0b-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="19a0b-155">O OneDrive permite que você compartilhe seus arquivos de trabalho entre seus laptops, a área de trabalho do Surface Hub e seus dispositivos móveis gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="19a0b-155">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="19a0b-156">Os arquivos podem ser editados em qualquer dispositivo, e todos os dispositivos conectados à rede serão atualizados com as alterações.</span><span class="sxs-lookup"><span data-stu-id="19a0b-156">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="19a0b-157">Considerando o tamanho da SSD do Surface Hub (128 GB), se você configurar o OneDrive em seu dispositivo de área de trabalho do Surface Hub, verifique se a configuração padrão é manter os arquivos online e baixar os arquivos conforme você os usa.</span><span class="sxs-lookup"><span data-stu-id="19a0b-157">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="19a0b-158">Para configurar o OneDrive para baixar arquivos somente quando necessário, defina a configuração de **arquivos sob demanda** para **economizar espaço e baixar arquivos conforme você os usa**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-158">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="19a0b-159">Para obter mais informações, consulte <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> consultar e definir os Estados de arquivos sob demanda no Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-159">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![Configurações do OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="19a0b-161">Você também pode repetir essas etapas para configurar um OneDrive pessoal, mas lembre-se de conservar o espaço da unidade e apenas baixar arquivos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="19a0b-161">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="19a0b-162">SharePoint e Teams</span><span class="sxs-lookup"><span data-stu-id="19a0b-162">SharePoint and Teams</span></span>

<span data-ttu-id="19a0b-163">Os arquivos de canal do SharePoint e do teams também podem ser sincronizados localmente com seus dispositivos de área de trabalho, como laptops e Surface Hub, usando o mecanismo de sincronização do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="19a0b-163">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="19a0b-164">Para sincronizar arquivos corporativos internos para sua unidade local com o aplicativo de sincronização do OneDrive:</span><span class="sxs-lookup"><span data-stu-id="19a0b-164">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="19a0b-165">Vá para um site do SharePoint e navegue até o diretório de documentos de nível superior dos arquivos nos quais você está interessado em exibir ou editar a partir do seu dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="19a0b-165">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="19a0b-166">Selecione o botão **sincronizar** na parte superior da faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19a0b-166">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="19a0b-167">Selecionar ao **abrir** no pop-up **este site está tentando abrir o Microsoft onedrive**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-167">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="19a0b-168">Verifique se os arquivos do SharePoint estão sincronizando com a unidade local selecionando no ícone do OneDrive na parte inferior direita da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-168">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="19a0b-169">Verifique se a configuração está definida para manter os arquivos online e baixe os arquivos somente quando você os usa:</span><span class="sxs-lookup"><span data-stu-id="19a0b-169">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="19a0b-170">Abra o explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="19a0b-170">Open file explorer.</span></span>
    
    2. <span data-ttu-id="19a0b-171">Acesse e clique com o botão direito do mouse no seu nome do SharePoint; por exemplo, \*\*Contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="19a0b-171">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="19a0b-172">Selecione **liberar espaço**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-172">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="19a0b-173">A coluna status mostrará o status de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-173">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="19a0b-174">Para obter mais informações, consulte <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> sincronizar arquivos do SharePoint com o cliente de sincronização do onedrive </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-174">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="19a0b-175">Os arquivos de canal de equipe são armazenados nos sites do SharePoint, com todas as mesmas funcionalidades de documentos do SharePoint, incluindo histórico de versão e sincronização para seus dispositivos de área de trabalho locais.</span><span class="sxs-lookup"><span data-stu-id="19a0b-175">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="19a0b-176">Para sincronizar arquivos de canais de equipe:</span><span class="sxs-lookup"><span data-stu-id="19a0b-176">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="19a0b-177">Navegue até o canal de interesse do Teams e selecione a guia **arquivos** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="19a0b-177">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="19a0b-178">Em seguida, selecione **sincronizar**. Os arquivos começarão a ser sincronizados e ficarão visíveis no explorador de arquivos \*\*da área \<name of the Teams Channel\> de trabalho \ Contoso \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="19a0b-178">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="19a0b-179">Use o mesmo procedimento usado para sincronizar os sites do SharePoint para manter os arquivos na nuvem e apenas baixá-los quando forem usados, toque e segure ou clique com o botão direito do mouse no explorador de arquivos no nome do canal do Teams e, em seguida, selecione **liberar espaço**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-179">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="19a0b-180">Configurações da caneta do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="19a0b-180">Surface Hub pen settings</span></span>

**<span data-ttu-id="19a0b-181">Emparelhar a caneta do Hub da superfície Bluetooth</span><span class="sxs-lookup"><span data-stu-id="19a0b-181">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="19a0b-182">Emparelhar a caneta para manter o firmware da caneta atualizado, definir os atalhos da caneta e obter informações sobre a carga da bateria na página de configurações do dispositivo Bluetooth ou no aplicativo Surface:</span><span class="sxs-lookup"><span data-stu-id="19a0b-182">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="19a0b-183">Selecione **Iniciar**  >  **configurações**de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-183">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="19a0b-184">Selecione **Adicionar Bluetooth ou outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-184">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="19a0b-185">Escolha **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-185">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="19a0b-186">Remova o botão de cauda da caneta e agite para desconectar a conexão da bateria.</span><span class="sxs-lookup"><span data-stu-id="19a0b-186">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="19a0b-187">Recoloque a tampa e pressione e segure a tampa até que o LED de emparelhamento pisque.</span><span class="sxs-lookup"><span data-stu-id="19a0b-187">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="19a0b-188">Nas configurações de Bluetooth do Surface Hub, escolha **Surface Hub 2 caneta**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-188">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="19a0b-189">Concluir a operação de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="19a0b-189">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="19a0b-190">Se o emparelhamento não for bem-sucedido, você pode tentar emparelhar a caneta novamente.</span><span class="sxs-lookup"><span data-stu-id="19a0b-190">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="19a0b-191">Se isso não funcionar, você pode testar para ver se a bateria está carregada verificando se a caneta funciona no aplicativo do quadro de comunicações.</span><span class="sxs-lookup"><span data-stu-id="19a0b-191">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="19a0b-192">Caso contrário, substitua a bateria e, em seguida, tente emparelhar a caneta novamente.</span><span class="sxs-lookup"><span data-stu-id="19a0b-192">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="19a0b-193">Se necessário, reinicie o dispositivo e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="19a0b-193">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="19a0b-194">**Definir atalhos de caneta** A caneta do Surface Hub tem um botão de atalho, às vezes chamado de "fim do clique".</span><span class="sxs-lookup"><span data-stu-id="19a0b-194">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="19a0b-195">A configuração de atalhos requer que você primeiro Emparelhe a caneta, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="19a0b-195">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="19a0b-196">Procure caneta e selecione **caneta & configurações de tinta do Windows**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-196">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="19a0b-197">Próximo à parte inferior da página, selecione atalhos de caneta que abrem a caixa de diálogo, mostrada aqui:</span><span class="sxs-lookup"><span data-stu-id="19a0b-197">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Atalhos de caneta](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="19a0b-199">Configuração da câmera</span><span class="sxs-lookup"><span data-stu-id="19a0b-199">Camera configuration</span></span>

<span data-ttu-id="19a0b-200">Você pode montar a câmera na parte superior ou em qualquer um dos lados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-200">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="19a0b-201">Monte a câmera em uma posição para otimizar o ângulo da câmera se você estiver usando o Hub com um suporte de área de trabalho em vez de um carrinho ou se estiver próximo ao Hub.</span><span class="sxs-lookup"><span data-stu-id="19a0b-201">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="19a0b-202">A câmera não gira automaticamente, portanto você precisa ter uma chave hex 2mm para girar manualmente a câmera.</span><span class="sxs-lookup"><span data-stu-id="19a0b-202">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="19a0b-203">Para saber mais sobre como montar a câmera lado a lado e girar a câmera manualmente, consulte <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> orientação do Surface Hub 2s orientação da lente da câmera </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-203">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="19a0b-204">Configuração do Windows Hello</span><span class="sxs-lookup"><span data-stu-id="19a0b-204">Windows Hello configuration</span></span>

<span data-ttu-id="19a0b-205">O Surface Hub 2S executando o Windows 10 Enterprise permite o pacote completo de aplicativos da área de trabalho Win32, bem como as opções biométricas do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="19a0b-205">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="19a0b-206">O acessório de leitor de impressão digital Surface Hub 2 pode ser conectado a qualquer porta USB-C do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-206">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="19a0b-207">Para solicitar um leitor de Surface Hub 2 ou exibir especificações técnicas, consulte (surface-hub-2-essential-add-ons.md "target =" _blank ">Complementos essenciais para o Windows 10 pro e Enterprise no Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-207">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="19a0b-208">Depois de inserir o leitor de impressão digital, selecione **Iniciar**  >  **configurações**  >  **conta**  >  **Opções de entrada**e  >  **impressão digital do Windows Hello** para registrar sua impressão digital.</span><span class="sxs-lookup"><span data-stu-id="19a0b-208">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="19a0b-209">Use um dispositivo certificado com Windows Hello para o reconhecimento de rosto.</span><span class="sxs-lookup"><span data-stu-id="19a0b-209">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="19a0b-210">A câmera Surface Hub 2S não dá suporte ao reconhecimento facial do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="19a0b-210">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="19a0b-211">Habilitar um ícone de atalho da tela de bloqueio na barra de tarefas</span><span class="sxs-lookup"><span data-stu-id="19a0b-211">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="19a0b-212">Para adicionar um ícone à barra de tarefas que permite o bloqueio de tela com um toque semelhante ao atalho de teclado do Windows-L:</span><span class="sxs-lookup"><span data-stu-id="19a0b-212">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="19a0b-213">Toque e segure ou clique com o botão direito do mouse na área de trabalho, selecione **novo**  >  **atalho**  >  **navegar**na  >  **área de trabalho**  >  **OK**  >  **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-213">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="19a0b-214">Forneça um nome para o atalho, como **bloquear meu PC**e, em seguida, selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-214">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="19a0b-215">Clique com o botão direito do mouse ou toque e mantenha pressionado o atalho recém-criado na área de trabalho e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-215">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="19a0b-216">Na guia **atalho** , insira o seguinte no campo de **destino** : **Rundll32.exe User32.dll, LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="19a0b-216">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="19a0b-217">Selecione o botão **Alterar ícone** e navegue até **C:\Windows\System32\imageres.dll** e selecione um ícone para usar.</span><span class="sxs-lookup"><span data-stu-id="19a0b-217">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="19a0b-218">Veja o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="19a0b-218">See the following example:</span></span>

    ![Escolher um ícone](images/lock.png)
    
1.  <span data-ttu-id="19a0b-220">Selecione **OK** para salvar o atalho.</span><span class="sxs-lookup"><span data-stu-id="19a0b-220">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="19a0b-221">Clique com o botão direito do mouse ou toque e segure o atalho e selecione **fixar na barra de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-221">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="19a0b-222">Depois de fixar o atalho de bloqueio à barra de tarefas, você pode excluí-lo da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="19a0b-222">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="19a0b-223">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="19a0b-223">Applications</span></span>


### <span data-ttu-id="19a0b-224">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="19a0b-224">Microsoft Whiteboard</span></span>

<span data-ttu-id="19a0b-225">Para instalar o Microsoft whiteboard:</span><span class="sxs-lookup"><span data-stu-id="19a0b-225">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="19a0b-226">Selecione o ícone do **espaço de trabalho do Windows Ink** no canto inferior direito da barra de tarefas e baixe o **whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-226">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Espaço de trabalho à tinta](images/ink.png) 

<span data-ttu-id="19a0b-228">Você também pode instalar o whiteboard na Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="19a0b-228">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="19a0b-229">Abra o aplicativo da Microsoft Store e pesquise por **whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-229">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="19a0b-230">Escolha **não graças** para entrar e usar entre dispositivos.</span><span class="sxs-lookup"><span data-stu-id="19a0b-230">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="19a0b-231">Fixar quadro de comunicações na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-231">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="19a0b-232">Aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="19a0b-232">Surface app</span></span>

1. <span data-ttu-id="19a0b-233">Na Microsoft Store, procure por **Surface**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-233">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="19a0b-234">Defina o filtro **disponível em** **todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-234">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="19a0b-235">Instale o aplicativo **Surface** .</span><span class="sxs-lookup"><span data-stu-id="19a0b-235">Install the **Surface** app.</span></span> <span data-ttu-id="19a0b-236">Este deve ser o primeiro aplicativo listado.</span><span class="sxs-lookup"><span data-stu-id="19a0b-236">This should be the first app listed.</span></span> <span data-ttu-id="19a0b-237">Talvez seja necessário associar o MSA à loja para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-237">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="19a0b-238">Fixar o aplicativo **Surface** à barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-238">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="19a0b-239">Captura e Esboço</span><span class="sxs-lookup"><span data-stu-id="19a0b-239">Snip & Sketch</span></span>

1. <span data-ttu-id="19a0b-240">Abra o aplicativo **corte & esboço** e fixe-o na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-240">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="19a0b-241">Selecione as reticências no canto superior direito e selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-241">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="19a0b-242">Em **configurações**, ative **a cópia automática para a área de transferência**, **salve recortes**e **várias janelas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="19a0b-242">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="19a0b-243">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="19a0b-243">Microsoft Office</span></span>

1. <span data-ttu-id="19a0b-244">Abra o <a href="https://portal.office.com/account#installs" target="_blank"> portal do Office </a> e instale os aplicativos desejados.</span><span class="sxs-lookup"><span data-stu-id="19a0b-244">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="19a0b-245">Fixar aplicativos do Office desejados na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-245">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="19a0b-246">Se o Outlook estiver instalado, certifique-se de definir o OST do Outlook para salvar somente as últimas duas últimas semanas do cache.</span><span class="sxs-lookup"><span data-stu-id="19a0b-246">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="19a0b-247">Isso reduzirá consideravelmente o uso do disco e o tempo de configuração.</span><span class="sxs-lookup"><span data-stu-id="19a0b-247">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="19a0b-248">Selecione **File**  >  **configurações de conta** de arquivo e selecione sua conta.</span><span class="sxs-lookup"><span data-stu-id="19a0b-248">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="19a0b-249">Selecione **alterar** e defina o controle deslizante para **usar o modo cache do Exchange** como 14 dias.</span><span class="sxs-lookup"><span data-stu-id="19a0b-249">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="19a0b-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19a0b-250">Microsoft Teams</span></span>

1. <span data-ttu-id="19a0b-251">Baixe e instale <a href="https://teams.microsoft.com/downloads" target="_blank"> o Microsoft Teams </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-251">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="19a0b-252">Definir configurações para iniciar o aplicativo automaticamente (opcional).</span><span class="sxs-lookup"><span data-stu-id="19a0b-252">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="19a0b-253">Fixar equipes na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-253">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="19a0b-254">Considere reduzir as notificações do Microsoft Teams no dispositivo para evitar distrações (opcional).</span><span class="sxs-lookup"><span data-stu-id="19a0b-254">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Notificações do teams](images/teams.png)

### <span data-ttu-id="19a0b-256">Conectar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="19a0b-256">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19a0b-257">No Windows 10, versão 2004 e posterior, a projeção conectar aplicativo para conexão sem fio que usa Miracast não é instalada por padrão, mas está disponível como um recurso opcional.</span><span class="sxs-lookup"><span data-stu-id="19a0b-257">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="19a0b-258">Se você instalou (ou atualizou para) a versão 2004 ou posterior do Windows, poderá ver o seguinte na tela projetando a this PC em configurações:</span><span class="sxs-lookup"><span data-stu-id="19a0b-258">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Projeto para este PC](images/sh2-project.png) 


1. <span data-ttu-id="19a0b-260">Para instalar o aplicativo na página de configurações "Projetando para este PC", selecione **recursos opcionais**  >  **Adicionar um recurso** e instalar o aplicativo de **exibição sem fio** .</span><span class="sxs-lookup"><span data-stu-id="19a0b-260">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="19a0b-261">Em **alguns dispositivos Windows e Android podem projetar neste computador quando você disser que está ok**, escolha:</span><span class="sxs-lookup"><span data-stu-id="19a0b-261">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="19a0b-262">**Disponível em qualquer lugar** se o dispositivo não estiver em uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="19a0b-262">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="19a0b-263">Caso contrário, escolha **disponível em todos os lugares em redes seguras**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-263">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="19a0b-264">Em **pedir projeto para este PC**, escolha **primeira vez apenas**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-264">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="19a0b-265">Em **exigir PIN para emparelhamento**, escolha **nunca**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-265">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="19a0b-266">Para iniciar o aplicativo e fixá-lo na barra de tarefas, procure **Connect**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-266">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="19a0b-267">Abra o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-267">Open the app.</span></span> <span data-ttu-id="19a0b-268">Enquanto o aplicativo estiver aberto, clique com o botão direito do mouse no ícone conectar aplicativo na barra de tarefas e selecione **fixar na barra de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-268">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="19a0b-269">Em seguida, feche o aplicativo conectar.</span><span class="sxs-lookup"><span data-stu-id="19a0b-269">Then close the Connect app.</span></span> <span data-ttu-id="19a0b-270">O **Project para este computador** pode não funcionar a menos que o aplicativo tenha sido executado pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="19a0b-270">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="19a0b-271">Configuração recomendada quando não estiver na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="19a0b-271">Recommended configuration when not on the corporate network:</span></span>

![Configurações em casa](images/project1.png)

<span data-ttu-id="19a0b-273">Configuração recomendada na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="19a0b-273">Recommended configuration on the corporate network:</span></span>

![Configurações no trabalho](images/project2.png)

### <span data-ttu-id="19a0b-275">Seu Telefone</span><span class="sxs-lookup"><span data-stu-id="19a0b-275">Your Phone</span></span>

<span data-ttu-id="19a0b-276">O aplicativo de **telefone** é instalado por padrão no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="19a0b-276">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="19a0b-277">Se não estiver presente, você também poderá instalá-lo na Windows Store.</span><span class="sxs-lookup"><span data-stu-id="19a0b-277">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="19a0b-278">Para obter informações sobre como configurar o aplicativo, consulte <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> como configurar seu telefone no Windows 10 e sincronizar dados entre seu PC e telefone </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-278">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="19a0b-279">Veja também <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> como corrigir problemas comuns com o aplicativo de telefone no Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-279">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <span data-ttu-id="19a0b-280">Zonas decorativas</span><span class="sxs-lookup"><span data-stu-id="19a0b-280">Fancy Zones</span></span>


<span data-ttu-id="19a0b-281">As **zonas decorativas** fazem parte de uma coleção de ferramentas chamadas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> no github.</span><span class="sxs-lookup"><span data-stu-id="19a0b-281">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="19a0b-282">É uma ótima maneira de usar o estado real da tela em um Surface Hub 2 oferecendo a você a capacidade de definir layouts fixos em seu vídeo ("zonas") e, em seguida, selecionar qual aplicativo será executado em cada zona.</span><span class="sxs-lookup"><span data-stu-id="19a0b-282">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="19a0b-283">O [wiki do PowerToy](https://github.com/microsoft/PowerToys/wiki) tem instruções sobre como usar e personalizar cada ferramenta, incluindo o [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span><span class="sxs-lookup"><span data-stu-id="19a0b-283">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="19a0b-284">Em um nível alto – após a instalação do PowerToys, você pode selecionar ou criar um layout personalizado e, em seguida, manter a tecla Shift pressionada e arrastar ou usar as teclas do teclado para mover um aplicativo em execução para zonas específicas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-284">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="19a0b-285">Usar um teclado Bluetooth ou USB e um mouse ajudará com isso, ou você pode usar o teclado virtual e o touchpad.</span><span class="sxs-lookup"><span data-stu-id="19a0b-285">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="19a0b-286">Dicas do Power Toys</span><span class="sxs-lookup"><span data-stu-id="19a0b-286">Power toys tips</span></span>**
- <span data-ttu-id="19a0b-287">Para receber notificações por email de atualizações de versão do PowerToy no GitHub, clique no botão "inscrição" na parte superior da [página](https://github.com/microsoft/PowerToys/releases).</span><span class="sxs-lookup"><span data-stu-id="19a0b-287">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="19a0b-288">Após a instalação do PowerToys, você pode receber notificações do Windows e/ou baixar e instalar as atualizações mais recentes configurando as configurações do PowerToys **baixar atualizações automaticamente** para ativado.</span><span class="sxs-lookup"><span data-stu-id="19a0b-288">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="19a0b-289">Para acessar as configurações do PowerToys, selecione a guia up Carat **executando aplicativos** na barra de tarefas e clique com o botão direito do mouse ou pressione e mantenha pressionado o ícone do PowerToys até que o menu seja exibido.</span><span class="sxs-lookup"><span data-stu-id="19a0b-289">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="19a0b-290">Selecione "configurações".</span><span class="sxs-lookup"><span data-stu-id="19a0b-290">Select “Settings”.</span></span>
- <span data-ttu-id="19a0b-291">Na parte inferior da página de configurações do PowerToy, ative o **download de atualizações automaticamente** para ativado.</span><span class="sxs-lookup"><span data-stu-id="19a0b-291">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="19a0b-292">Quando uma atualização for liberada, uma notificação do Windows será exibida oferecendo a opção de quando instalar a atualização.</span><span class="sxs-lookup"><span data-stu-id="19a0b-292">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <span data-ttu-id="19a0b-293">Navegador do Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="19a0b-293">Edge Chromium browser</span></span>

<span data-ttu-id="19a0b-294">Baixe e instale o novo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> navegador Chromium do Edge </a> .</span><span class="sxs-lookup"><span data-stu-id="19a0b-294">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="19a0b-295">Ferramenta de diagnóstico de hardware do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="19a0b-295">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="19a0b-296">A <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> ferramenta de diagnóstico de hardware do Surface Hub </a> disponível gratuitamente na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="19a0b-296">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="19a0b-297">A ferramenta foi projetada para ajudar você a garantir que seu Surface Hub esteja se apresentando o melhor.</span><span class="sxs-lookup"><span data-stu-id="19a0b-297">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="19a0b-298">Ele contém testes para determinar se o seu firmware está atualizado e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="19a0b-298">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="19a0b-299">Testes interativos permitem que você confirme que a funcionalidade essencial está funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="19a0b-299">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="19a0b-300">Se forem encontrados problemas, os resultados poderão ser salvos e compartilhados com a equipe de suporte do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="19a0b-300">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="19a0b-301">Clique no link para instalá-lo na Microsoft Store e, em seguida, fixe o aplicativo na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-301">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="19a0b-302">Configurações adicionais</span><span class="sxs-lookup"><span data-stu-id="19a0b-302">Additional settings</span></span>

### <span data-ttu-id="19a0b-303">Cauda da caneta selecione para iniciar o quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="19a0b-303">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="19a0b-304">Procure **caneta** e selecione **caneta & configurações de tinta do Windows**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-304">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="19a0b-305">Próximo à parte inferior da página, em **atalhos de caneta** , defina **selecionar uma vez** para o **Microsoft whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-305">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="19a0b-306">Gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="19a0b-306">Power management</span></span>

<span data-ttu-id="19a0b-307">Há várias configurações de energia disponíveis para obter a melhor experiência com o Windows 10 pro ou Enterprise no Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="19a0b-307">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="19a0b-308">Isso inclui tempos limite de tela e do PC e como eles interagem com a detecção de presença humana (Doppler) interna, a proteção de tela e a proteção por senha e, em seguida, se for apropriado como passar configurações de energia de política de grupo para usuários de laptop/desktop.</span><span class="sxs-lookup"><span data-stu-id="19a0b-308">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="19a0b-309">O Windows 10 pro ou Enterprise no Surface Hub 2 mantém a tela de entrar no estado de suspensão por ações de toque, mouse e teclado, além da detecção de ocupação humana interna (Doppler).</span><span class="sxs-lookup"><span data-stu-id="19a0b-309">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="19a0b-310">A detecção de ocupação humana é habilitada por padrão, mas, se desejado, pode ser desabilitada na UEFI alternando a opção de dispositivo na ferramenta configurador UEFI do Surface como parte da migração inicial ou criando e aplicando um pacote de configuração UEFI mais recente.</span><span class="sxs-lookup"><span data-stu-id="19a0b-310">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="19a0b-311">Gerenciamento de energia: configurações de tela e suspensão do computador</span><span class="sxs-lookup"><span data-stu-id="19a0b-311">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="19a0b-312">Selecione **Iniciar**  >  **configurações**  >  **sistema**  >  **alimentação & suspender**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-312">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="19a0b-313">Defina o controle deslizante do modo de energia para **obter o melhor desempenho**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-313">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="19a0b-314">Configure os valores de tela e de repouso para sua preferência enquanto também faz a Doppler de detecção de presença do que ativa o dispositivo quando o movimento é detectado.</span><span class="sxs-lookup"><span data-stu-id="19a0b-314">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="19a0b-315">Portanto, como prática recomendada, é recomendável definir a tela para desligar **após 2 horas** e o computador para **desligar após 4 horas.**</span><span class="sxs-lookup"><span data-stu-id="19a0b-315">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="19a0b-316">Gerenciamento de energia: proteção de tela</span><span class="sxs-lookup"><span data-stu-id="19a0b-316">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="19a0b-317">Pesquisar a **tela de bloqueio** e abrir **as configurações da tela de bloqueio**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-317">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="19a0b-318">Defina **as configurações de tempo limite de tela** e **as configurações de proteção de tela** para sua preferência.</span><span class="sxs-lookup"><span data-stu-id="19a0b-318">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="19a0b-319">Os valores padrão recomendados são:</span><span class="sxs-lookup"><span data-stu-id="19a0b-319">Recommended default values are:</span></span>

   - <span data-ttu-id="19a0b-320">Proteção de tela para (nenhum) ou uma proteção de tela de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="19a0b-320">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="19a0b-321">Tempo de espera para 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="19a0b-321">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="19a0b-322">Ao continuar, exiba a tela de logon.</span><span class="sxs-lookup"><span data-stu-id="19a0b-322">On resume, display logon screen.</span></span>


**<span data-ttu-id="19a0b-323">Gerenciamento de energia: política de grupo</span><span class="sxs-lookup"><span data-stu-id="19a0b-323">Power Management: Group Policy</span></span>**

<span data-ttu-id="19a0b-324">Antes de executar o procedimento a seguir, verifique com seu departamento de ti para aprovação para excluir um dispositivo Surface Hub 2S da política global de gerenciamento de energia.</span><span class="sxs-lookup"><span data-stu-id="19a0b-324">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="19a0b-325">Algumas configurações de gerenciamento de energia podem desabilitar a função de detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="19a0b-325">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="19a0b-326">Procure pela **central de software** e abra-a.</span><span class="sxs-lookup"><span data-stu-id="19a0b-326">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="19a0b-327">Selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-327">Select **Options**.</span></span>

3. <span data-ttu-id="19a0b-328">Expanda o **Gerenciamento de energia**  e selecione **não aplicar configurações de energia do meu departamento de ti para este computador**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-328">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Configurações de software](images/soft-cntr.png)

### <span data-ttu-id="19a0b-330">Sensor de armazenamento</span><span class="sxs-lookup"><span data-stu-id="19a0b-330">Storage Sense</span></span>

<span data-ttu-id="19a0b-331">O Surface Hub 2 tem uma SSD de 128 GB para armazenamento local, portanto, é necessário considerar o uso das medidas de salvamento de armazenamento durante o uso normal.</span><span class="sxs-lookup"><span data-stu-id="19a0b-331">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="19a0b-332">Para configurar o sensor de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="19a0b-332">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="19a0b-333">Procure **configurações de armazenamento**, que se encontra em **configurações do sistema**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-333">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="19a0b-334">Em **configurações**, selecione **ativar o sensor de armazenamento** para abrir a página Configurações de **armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="19a0b-334">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="19a0b-335">Mude o sensor de armazenamento para **ligado**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-335">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="19a0b-336">Selecione **Configurar o sensor de armazenamento ou executá-lo agora** e defina as configurações para manter os arquivos online o máximo possível (devido a espaço limitado na unidade).</span><span class="sxs-lookup"><span data-stu-id="19a0b-336">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="19a0b-337">Configurações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="19a0b-337">Recommended settings:</span></span>

- <span data-ttu-id="19a0b-338">Executar detecção de armazenamento = todos os dias.</span><span class="sxs-lookup"><span data-stu-id="19a0b-338">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="19a0b-339">Exclua os arquivos temporários que os meus aplicativos não estão usando = a cada 14 dias (pelo menos).</span><span class="sxs-lookup"><span data-stu-id="19a0b-339">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="19a0b-340">Exclua os arquivos na pasta Meus downloads se eles estiverem lá por mais de = 30 dias.</span><span class="sxs-lookup"><span data-stu-id="19a0b-340">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="19a0b-341">OneDrive: o conteúdo ficará online apenas se não for aberto por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="19a0b-341">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="19a0b-342">Modo tablet</span><span class="sxs-lookup"><span data-stu-id="19a0b-342">Tablet mode</span></span>

<span data-ttu-id="19a0b-343">Ative o modo tablet, se quiser, para atender às necessidades de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="19a0b-343">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="19a0b-344">Configurações de som</span><span class="sxs-lookup"><span data-stu-id="19a0b-344">Sound settings</span></span>

1. <span data-ttu-id="19a0b-345">Procure **configurações de sons** e abra esta página.</span><span class="sxs-lookup"><span data-stu-id="19a0b-345">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="19a0b-346">Selecione o **painel de controle de som** à direita e selecione a guia **sons** .</span><span class="sxs-lookup"><span data-stu-id="19a0b-346">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="19a0b-347">Em **eventos do programa** , defina **conexão do dispositivo** e **dispositivo desconectar** para **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-347">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="19a0b-348">Notificações de silêncio</span><span class="sxs-lookup"><span data-stu-id="19a0b-348">Silence notifications</span></span>

1. <span data-ttu-id="19a0b-349">Pesquise o **Assistente de foco** e abra esta página.</span><span class="sxs-lookup"><span data-stu-id="19a0b-349">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="19a0b-350">Selecione **apenas alarmes**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-350">Select **Alarms Only**.</span></span> <span data-ttu-id="19a0b-351">Isso evitará submenus de notificação constante.</span><span class="sxs-lookup"><span data-stu-id="19a0b-351">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="19a0b-352">Limpeza de Disco</span><span class="sxs-lookup"><span data-stu-id="19a0b-352">Disk Cleanup</span></span>

1. <span data-ttu-id="19a0b-353">Procure por **limpeza de disco** e abra este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-353">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="19a0b-354">Em **arquivos a serem excluídos**, selecione os arquivos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="19a0b-354">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="19a0b-355">Além disso, selecione **limpar arquivos do sistema**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-355">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="19a0b-356">Concluir e verificar</span><span class="sxs-lookup"><span data-stu-id="19a0b-356">Complete and verify</span></span>

1. <span data-ttu-id="19a0b-357">Procure e instale todas as atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="19a0b-357">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="19a0b-358">Atualize a política de grupo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-358">Update Group Policy.</span></span>

   1. <span data-ttu-id="19a0b-359">Em um prompt de comando elevado, digite **gpupdate/force/boot/Wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-359">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="19a0b-360">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19a0b-360">Restart the device.</span></span>

4. <span data-ttu-id="19a0b-361">Verifique os aplicativos da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="19a0b-361">Verify taskbar apps.</span></span>

   - <span data-ttu-id="19a0b-362">Conectar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="19a0b-362">Connect App</span></span>
   - <span data-ttu-id="19a0b-363">Ícone de cadeado</span><span class="sxs-lookup"><span data-stu-id="19a0b-363">Lock Icon</span></span>
   - <span data-ttu-id="19a0b-364">Captura e Esboço</span><span class="sxs-lookup"><span data-stu-id="19a0b-364">Snip & Sketch</span></span>
   - <span data-ttu-id="19a0b-365">Equipes (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="19a0b-365">Teams (if applicable)</span></span>
   - <span data-ttu-id="19a0b-366">Aplicativos do Office (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="19a0b-366">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="19a0b-367">Aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="19a0b-367">Surface App</span></span>
   - <span data-ttu-id="19a0b-368">Quadro de Comunicações</span><span class="sxs-lookup"><span data-stu-id="19a0b-368">Whiteboard</span></span>
    
5. <span data-ttu-id="19a0b-369">Verificar a detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="19a0b-369">Verify presence detection.</span></span>

   - <span data-ttu-id="19a0b-370">A detecção de presença será um ícone verde na bandeja do sistema.</span><span class="sxs-lookup"><span data-stu-id="19a0b-370">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="19a0b-371">Verifique se a projeção neste computador está habilitada com o aplicativo conectar.</span><span class="sxs-lookup"><span data-stu-id="19a0b-371">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="19a0b-372">Depois de configurar o  **Project para estas** configurações do computador, execute o aplicativo conectar pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="19a0b-372">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="19a0b-373">(Subsequentemente, o aplicativo de conexão não precisa estar em execução para projetar para o Surface Hub.)</span><span class="sxs-lookup"><span data-stu-id="19a0b-373">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="19a0b-374">Verifique as configurações de energia e suspensão.</span><span class="sxs-lookup"><span data-stu-id="19a0b-374">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="19a0b-375">Proteção de tela: 15 minutos, definir como (nenhum), polígonos ou ficar em branco; Verifique se a caixa de seleção Requer senha está selecionada.</span><span class="sxs-lookup"><span data-stu-id="19a0b-375">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="19a0b-376">Tela: **desative após 2 horas**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-376">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="19a0b-377">PC:  **desative após 4 horas**.</span><span class="sxs-lookup"><span data-stu-id="19a0b-377">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="19a0b-378">Verifique se o Windows Hello está funcionando.</span><span class="sxs-lookup"><span data-stu-id="19a0b-378">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="19a0b-379">Verifique se a sincronização suas configurações está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="19a0b-379">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="19a0b-380">Verifique os aplicativos de inicialização.</span><span class="sxs-lookup"><span data-stu-id="19a0b-380">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="19a0b-381">Após a instalação e a configuração do Windows 10, o Surface Hub 2S pode ser gerenciado assim como qualquer outro dispositivo com o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="19a0b-381">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="19a0b-382">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="19a0b-382">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="19a0b-383">Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="19a0b-383">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
