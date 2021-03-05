---
title: Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2
description: Este artigo inclui recomendações para garantir a melhor experiência ao usar um computador de tela grande e caneta personalizado.
keywords: Surface Hub, Windows 10, área de trabalho, instalação, configuração
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
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393589"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="fb7f5-104">Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fb7f5-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="fb7f5-105">Depois de concluir o processo de instalação de migração para o Windows 10 Pro ou Enterprise, você pode executar as etapas a seguir para configurar aplicativos e configurações em seu Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="fb7f5-106">Estas etapas são recomendadas para garantir a melhor experiência ao usar esse computador de toque de tela grande e caneta personalizado.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="fb7f5-107">Ao executar essas etapas, você pode achar útil usar um teclado e mouse com fio ou sem fio.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <a name="configure-system-settings"></a><span data-ttu-id="fb7f5-108">Configurar configurações do sistema</span><span class="sxs-lookup"><span data-stu-id="fb7f5-108">Configure system settings</span></span>

1. <span data-ttu-id="fb7f5-109">Entre com uma conta que tenha privilégios de administrador local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="fb7f5-110">Em dispositivos ingressados no Azure AD, o usuário que executa a junção do Azure AD é adicionado automaticamente ao grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="fb7f5-111">Os administradores globais do Azure AD e os administradores de dispositivos do Azure AD <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> também são administradores </a> locais.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="fb7f5-112">Você pode digitar **administradores de grupo local líquido em** um prompt de comando para listar as contas que têm direitos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="fb7f5-113">Renomeie o dispositivo usando um nome amigável, por exemplo: **username-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="fb7f5-114">Selecione **Iniciar**  >  **Configurações Contas**  >  \*\*\*\*  >  **Sincronizar suas configurações** e desativar **configurações de** sincronização.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="fb7f5-115">As configurações usadas aqui se destinam a habilitar a melhor experiência de toque de tela grande e, portanto, talvez você não queira sincronizar outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="fb7f5-116">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-116">Restart the device.</span></span>

## <a name="enable-the-touch-keyboard-and-touchpad"></a><span data-ttu-id="fb7f5-117">Habilitar o teclado touch e o touchpad</span><span class="sxs-lookup"><span data-stu-id="fb7f5-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="fb7f5-118">Selecione **Iniciar**  >  **Configurações**  >  **Dispositivos**  >  **Digitando** \*\*\*\* e ativar Mostrar o teclado touch quando não estiver no modo tablet e não houver teclado conectado.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-118">Select **Start** > **Settings** > **Devices** > **Typing** and turn **Show the touch keyboard when not in tablet mode and there's no keyboard attached** on.</span></span>

2. <span data-ttu-id="fb7f5-119">Toque e segure ou clique com o botão direito do mouse na barra de tarefas e selecione Mostrar botão de **teclado** por toque e **Mostrar botão touchpad**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="fb7f5-120">O teclado touch é útil para entrada direta do usuário, e o touchpad virtual ajuda com seleções precisas, dicas de tela de foco ou como uma alternativa para tocar e segurar para clicar com o botão direito do mouse.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="fb7f5-121">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-121">See the following example.</span></span>

      ![Configurações de toque](images/touch.png)

3. <span data-ttu-id="fb7f5-123">Configure o teclado touch como QWERTY e flutuante.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-123">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="fb7f5-124">Selecione o **ícone Teclado** na barra de tarefas para mostrar o teclado por toque.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-124">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    1. <span data-ttu-id="fb7f5-125">No teclado touch, selecione o ícone de teclado no canto superior esquerdo para abrir as configurações do teclado.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    1. <span data-ttu-id="fb7f5-126">Selecione o próximo ou último tipo de teclado na linha superior para habilitar o QWERTY e a última opção na segunda linha para habilitar o flutuante, o que é muito útil nessa tela grande.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="fb7f5-127">Consulte os exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-127">See the following examples.</span></span>

       ![Configurações de teclado](images/kbd.png)
 
4. <span data-ttu-id="fb7f5-129">Configure as configurações do teclado suave.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-129">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="fb7f5-130">Selecione o **ícone Configurações** no teclado de toque ou procure e abra **Configurações de Digitação**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-130">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![configurações de teclado suave](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="fb7f5-132">Habilita todas as opções em Teclado ortográfico, de digitação e de toque.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-132">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="fb7f5-133">O exemplo a seguir mostra o trackpad, que é útil para navegar e selecionar opções.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-133">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="fb7f5-134">O teclado na tela está sendo usado para pesquisar na Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-134">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Usando o trackpad](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a><span data-ttu-id="fb7f5-136">Configurar Bluetooth teclado e mouse (opcional)</span><span class="sxs-lookup"><span data-stu-id="fb7f5-136">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="fb7f5-137">Conecte um teclado e um mouse se você estiver usando o dispositivo como seu dispositivo Windows principal ou use-o com frequência para digitar ou trabalhar com precisão.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-137">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="fb7f5-138">Se o dispositivo Surface Hub estiver próximo de um computador, você poderá usar Mouse sem Bordas para se mover perfeitamente entre o <a href="https://aka.ms/mm" target="_blank"> Surface Hub e o </a> computador.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-138">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="fb7f5-139">Para obter mais informações, consulte <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Download da Microsoft em O Garage: Mouse sem Bordas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-139">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <a name="example-of-taskbar-layout"></a><span data-ttu-id="fb7f5-140">Exemplo de layout da barra de tarefas</span><span class="sxs-lookup"><span data-stu-id="fb7f5-140">Example of Taskbar layout</span></span>

<span data-ttu-id="fb7f5-141">Depois de concluir as etapas a seguir para configurar/configurar o Surface Hub 2 para Windows 10 Professional ou Enterprise, recomendamos que você utilize fixar seus aplicativos mais usados na Barra de Tarefas para um início rápido de um toque de cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-141">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="fb7f5-142">Veja a seguir um exemplo de como sua barra de tarefas poderia ser:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-142">Below is an example of what your taskbar could look like:</span></span>

 ![Layout da barra de tarefas](images/taskblyt.png)
### <a name="update-installed-apps"></a><span data-ttu-id="fb7f5-144">Atualizar aplicativos instalados</span><span class="sxs-lookup"><span data-stu-id="fb7f5-144">Update installed apps</span></span>

<span data-ttu-id="fb7f5-145">Para atualizar todos os aplicativos da Loja instalados:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-145">To update all installed Store apps:</span></span>

1. <span data-ttu-id="fb7f5-146">Abra o aplicativo da Microsoft Store e selecione **See more** ellipsis in the top-right corner.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-146">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="fb7f5-147">Selecione **Downloads e atualizações.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-147">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="fb7f5-148">Selecionar **Obter atualizações**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-148">Select **Get updates**</span></span>

### <a name="scan-for-and-install-all-windows-updates"></a><span data-ttu-id="fb7f5-149">Examinar e instalar todas as Atualizações do Windows</span><span class="sxs-lookup"><span data-stu-id="fb7f5-149">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="fb7f5-150">Depois de migrar para o Windows 10 Professional ou o Windows 10 Enterprise, pode haver atualizações de recursos e manutenção disponíveis para você instalar.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-150">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="fb7f5-151">Vá para **Configurações**  >  **Atualizar & Segurança** > e selecione Verificar se há **atualizações**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-151">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="fb7f5-152">Se houver atualizações, instale-as, reinicie e repita o processo até que você veja a seguinte notificação:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-152">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Notificação do Windows Update "Você está atualizado"](images/wustatus.png)


## <a name="onedrive-for-business"></a><span data-ttu-id="fb7f5-154">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="fb7f5-154">OneDrive for Business</span></span>

<span data-ttu-id="fb7f5-155">Use o OneDrive for Business para compartilhar facilmente ferramentas, logs e <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> outros arquivos entre todos os </a> dispositivos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="fb7f5-156">O OneDrive permite que você compartilhe seus arquivos de trabalho entre seus laptops, Surface Hub Desktop e seus dispositivos móveis gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-156">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="fb7f5-157">Os arquivos podem ser editados em qualquer dispositivo e todos os dispositivos conectados à rede serão atualizados com as alterações.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-157">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="fb7f5-158">Considerando o tamanho do SSD do Surface Hub (128 GB), se você configurar o OneDrive em seu dispositivo Surface Hub Desktop, certifique-se de que a configuração padrão é manter os arquivos online e baixar arquivos conforme você os usa.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-158">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="fb7f5-159">Para configurar o OneDrive para baixar arquivos somente quando necessário, de definir a configuração **Arquivos Sob** Demanda como Salvar espaço e baixar arquivos conforme você **os usa**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-159">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="fb7f5-160">Para obter mais informações, <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> consulte Query and set Files On-Demand states in Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-160">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![Configurações do OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="fb7f5-162">Você também pode repetir essas etapas para configurar um OneDrive pessoal, mas não deixe de economizar espaço na unidade e apenas baixar arquivos conforme precisar deles.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-162">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <a name="sharepoint-and-teams"></a><span data-ttu-id="fb7f5-163">SharePoint e Teams</span><span class="sxs-lookup"><span data-stu-id="fb7f5-163">SharePoint and Teams</span></span>

<span data-ttu-id="fb7f5-164">Os arquivos do SharePoint e do Teams Channel também podem sincronizar localmente com seus dispositivos de área de trabalho, como laptops e Surface Hubs, usando o mecanismo de sincronização do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-164">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="fb7f5-165">Para sincronizar arquivos corporativos internos com sua unidade local com o aplicativo de sincronização do OneDrive:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-165">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="fb7f5-166">Vá para um site do SharePoint e navegue até o diretório de documentos de nível superior para os arquivos que você está interessado em exibir ou editar do dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-166">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="fb7f5-167">Selecione no botão **Sincronizar** na parte superior da faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-167">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="fb7f5-168">Selecione em **Abrir** no pop-up **Este site está tentando abrir o Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-168">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="fb7f5-169">Verifique se os arquivos do SharePoint estão sincronizando com sua unidade local selecionando no ícone do OneDrive na parte inferior direita da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-169">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="fb7f5-170">Verifique se a configuração está definida para manter os arquivos online e baixar os arquivos somente conforme você os usa:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-170">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="fb7f5-171">Abra o explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-171">Open file explorer.</span></span>
    
    2. <span data-ttu-id="fb7f5-172">Navegue até e clique com o botão direito do mouse no nome do SharePoint; por exemplo, \*\*Contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-172">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="fb7f5-173">Selecione **Liberar espaço**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-173">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="fb7f5-174">A coluna Status exibirá o status de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-174">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="fb7f5-175">Para obter mais informações, consulte <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sincronizar arquivos do SharePoint com o cliente de sincronização do OneDrive. </a></span><span class="sxs-lookup"><span data-stu-id="fb7f5-175">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="fb7f5-176">Os arquivos do Teams Channel são armazenados em sites do SharePoint, com todas as mesmas funcionalidades de documento do SharePoint, incluindo histórico de versão e sincronização com seus dispositivos de área de trabalho locais.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-176">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="fb7f5-177">Para sincronizar arquivos do Teams Channel:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-177">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="fb7f5-178">Navegue até o Canal do Teams de interesse e selecione a guia **Arquivos** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-178">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="fb7f5-179">Em seguida, **selecione Sincronizar**. Os arquivos iniciarão a sincronização e estarão visíveis no Explorador de Arquivos na \*\*Área de Trabalho \ Contoso \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-179">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="fb7f5-180">Use o mesmo procedimento que você usou para sincronizar sites do SharePoint para manter os arquivos na nuvem e apenas baixá-los quando você usá-los, tocar e segurar ou clicar com o botão direito do mouse no Explorador de Arquivos no nome do Canal do Teams e, em seguida, **selecionando Liberar**espaço .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-180">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <a name="surface-hub-pen-settings"></a><span data-ttu-id="fb7f5-181">Configurações de caneta do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fb7f5-181">Surface Hub pen settings</span></span>

**<span data-ttu-id="fb7f5-182">Emparelhar a caneta Bluetooth Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fb7f5-182">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="fb7f5-183">Emparelhar a caneta para manter o firmware de caneta atualizado, definir os atalhos de caneta e obter informações sobre a carga da bateria na página de configurações do dispositivo Bluetooth ou no aplicativo Surface:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-183">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="fb7f5-184">Selecione **Iniciar**  >  **Dispositivos de**  >  **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-184">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="fb7f5-185">Selecione **Adicionar Bluetooth ou outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-185">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="fb7f5-186">Escolha **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-186">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="fb7f5-187">Remova o botão de cauda de caneta e balance para desconectar a conexão da bateria.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-187">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="fb7f5-188">Coloque a tampa novamente e pressione e segure a tampa até o LED de emparelhamento piscar.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-188">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="fb7f5-189">Nas configurações do Surface Hub Bluetooth, escolha **Surface Hub 2 Pen**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-189">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="fb7f5-190">Conclua a operação de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-190">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="fb7f5-191">Se o emparelhamento não for bem-sucedido, você poderá tentar emparelhar a caneta novamente.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-191">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="fb7f5-192">Se isso não funcionar, você poderá testar para ver se a bateria é carregada verificando se a caneta funciona no aplicativo de Quadro de Branco.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-192">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="fb7f5-193">Caso não seja, substitua a bateria e tente emparelhar a caneta novamente.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-193">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="fb7f5-194">Se necessário, reinicie o dispositivo e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-194">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="fb7f5-195">**Definir atalhos de caneta** A caneta Surface Hub tem um botão de atalho às vezes chamado de "clique na cauda".</span><span class="sxs-lookup"><span data-stu-id="fb7f5-195">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="fb7f5-196">A configuração de atalhos exige que você primeiro emparelhe a caneta, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-196">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="fb7f5-197">Pesquise Caneta e **selecione Caneta & configurações do Windows Ink.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-197">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="fb7f5-198">Na parte inferior da página, selecione Atalhos de caneta que abre a caixa de diálogo, mostrada aqui:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-198">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Atalhos de caneta](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a><span data-ttu-id="fb7f5-200">Configuração da câmera</span><span class="sxs-lookup"><span data-stu-id="fb7f5-200">Camera configuration</span></span>

<span data-ttu-id="fb7f5-201">Você pode montar a câmera na parte superior ou em ambos os lados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-201">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="fb7f5-202">Monte a câmera em uma posição para otimizar o ângulo da câmera se você estiver usando o Hub com um suporte de área de trabalho em vez de um carrinho ou estiver próximo do Hub.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-202">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="fb7f5-203">A câmera não gira automaticamente, portanto, você precisa ter uma chave hexaxa de 2 mm para girar manualmente a câmera.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-203">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="fb7f5-204">Para obter mais informações sobre como montar lateralmente a câmera e girar a câmera manualmente, consulte Orientação da lente da câmera <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> do Surface Hub 2S </a> .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-204">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <a name="windows-hello-configuration"></a><span data-ttu-id="fb7f5-205">Configuração do Windows Hello</span><span class="sxs-lookup"><span data-stu-id="fb7f5-205">Windows Hello configuration</span></span>

<span data-ttu-id="fb7f5-206">O Surface Hub 2S que executa o Windows 10 Enterprise permite o pacote completo de aplicativos de área de trabalho Win32, bem como opções biométricas do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-206">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="fb7f5-207">O acessório Leitor de Impressão Digital do Surface Hub 2 pode ser conectado a qualquer porta USB-C no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-207">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="fb7f5-208">Para solicitar um Leitor de Impressão Digital do Surface Hub 2 ou exibir especificações técnicas, consulte (surface-hub-2-essential-add-ons.md" target="_blank">Complementos essenciais para Windows 10 Pro e Enterprise no Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-208">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="fb7f5-209">Depois de inserir o leitor de impressão digital, selecione **Iniciar**  >  **Configurações**Opções de  >  \*\*\*\*  >  **logon**do  >  **Windows Hello Fingerprint** para registrar sua impressão digital.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-209">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="fb7f5-210">Use um dispositivo certificado do Windows Hello para reconhecimento de rosto.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-210">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="fb7f5-211">A câmera do Surface Hub 2S não dá suporte ao reconhecimento facial do Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-211">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a><span data-ttu-id="fb7f5-212">Habilitar um ícone de atalho de Tela de Bloqueio na barra de tarefas</span><span class="sxs-lookup"><span data-stu-id="fb7f5-212">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="fb7f5-213">Para adicionar um ícone à barra de tarefas que habilita um bloqueio de tela de toque semelhante ao atalho do teclado windows-L:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-213">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="fb7f5-214">Toque e segure ou clique com o botão direito do mouse na área de trabalho, selecione **Novo**  >  **Atalho**  >  **Procurar**  >  **Área de Trabalho**OK  >  \*\*\*\*  >  **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-214">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="fb7f5-215">Forneça um nome para o atalho, como **Bloquear meu computador**e selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-215">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="fb7f5-216">Clique com o botão direito do mouse ou toque e segure o atalho recém-criado na área de trabalho e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-216">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="fb7f5-217">Na guia **Atalho,** insira o seguinte no campo **Destino:** **Rundll32.exe User32.dll,LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-217">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="fb7f5-218">Selecione o **botão Alterar Ícone** e navegue \*\* até \*\*C:\Windows\System32\imageres.dlle selecione um ícone a ser usado.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-218">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="fb7f5-219">Veja o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-219">See the following example:</span></span>

    ![Escolher um ícone](images/lock.png)
    
1.  <span data-ttu-id="fb7f5-221">Selecione **OK** para salvar o atalho.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-221">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="fb7f5-222">Clique com o botão direito do mouse ou toque e segure o atalho e selecione **Fixar na barra de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-222">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="fb7f5-223">Depois de ter fixado o atalho de bloqueio na barra de tarefas, você pode excluí-lo da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-223">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <a name="applications"></a><span data-ttu-id="fb7f5-224">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="fb7f5-224">Applications</span></span>


### <a name="microsoft-whiteboard"></a><span data-ttu-id="fb7f5-225">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="fb7f5-225">Microsoft Whiteboard</span></span>

<span data-ttu-id="fb7f5-226">Para instalar o Quadro de Whiteboard da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-226">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="fb7f5-227">Selecione o **ícone do Espaço de Trabalho do Windows Ink** no canto inferior direito da barra de tarefas e baixe o Quadro de **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-227">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Espaço de trabalho de tinta](images/ink.png) 

<span data-ttu-id="fb7f5-229">Como alternativa, você pode instalar o Quadro de Trabalho na Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-229">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="fb7f5-230">Abra o aplicativo da Microsoft Store e pesquise **whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-230">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="fb7f5-231">Escolha **Não graças** a entrar e usar em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-231">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="fb7f5-232">Fixar quadro de trabalho na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-232">Pin Whiteboard to the taskbar.</span></span>

### <a name="surface-app"></a><span data-ttu-id="fb7f5-233">Aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="fb7f5-233">Surface app</span></span>

1. <span data-ttu-id="fb7f5-234">Na Microsoft Store, pesquise o **Surface**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-234">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="fb7f5-235">De definir **o filtro Disponível em** todos os **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-235">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="fb7f5-236">Instale o **aplicativo Surface.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-236">Install the **Surface** app.</span></span> <span data-ttu-id="fb7f5-237">Este deve ser o primeiro aplicativo listado.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-237">This should be the first app listed.</span></span> <span data-ttu-id="fb7f5-238">Talvez seja necessário associar seu MSA à Loja para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-238">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="fb7f5-239">Fixar o **aplicativo Surface** na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-239">Pin the **Surface** app to taskbar.</span></span>

### <a name="snip--sketch"></a><span data-ttu-id="fb7f5-240">Captura e Esboço</span><span class="sxs-lookup"><span data-stu-id="fb7f5-240">Snip & Sketch</span></span>

1. <span data-ttu-id="fb7f5-241">Abra o **aplicativo Snip & Sketch** e fixe-o na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-241">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="fb7f5-242">Selecione a reellipse no canto superior direito e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-242">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="fb7f5-243">Em **Configurações,** a opção **Copiar automaticamente**para área de transferência, **Salvar trechos**e Várias **janelas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-243">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <a name="microsoft-office"></a><span data-ttu-id="fb7f5-244">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="fb7f5-244">Microsoft Office</span></span>

1. <span data-ttu-id="fb7f5-245">Abra o <a href="https://portal.office.com/account#installs" target="_blank"> Portal do Office e instale seus </a> aplicativos desejados.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-245">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="fb7f5-246">Fixar aplicativos do Office desejados na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-246">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="fb7f5-247">Se o Outlook estiver instalado, certifique-se de definir o Outlook OST para salvar apenas o cache das últimas duas semanas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-247">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="fb7f5-248">Isso reduzirá consideravelmente o uso do disco e o tempo de instalação.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-248">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="fb7f5-249">Selecione **Configurações**  >  **da Conta de Arquivo** e selecione sua conta.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-249">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="fb7f5-250">Selecione **Alterar** e de definir o controle deslizante para **Usar o Modo cache do Exchange** como 14 dias.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-250">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="fb7f5-251">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb7f5-251">Microsoft Teams</span></span>

1. <span data-ttu-id="fb7f5-252">Baixar e instalar <a href="https://teams.microsoft.com/downloads" target="_blank"> o Microsoft </a> Teams.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-252">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="fb7f5-253">Configure as configurações para o aplicativo de início automático (opcional).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-253">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="fb7f5-254">Fixar o Teams na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-254">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="fb7f5-255">Considere reduzir as notificações do Teams no dispositivo para evitar distrações (opcionais).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-255">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Notificações do Teams](images/teams.png)

### <a name="connect-app"></a><span data-ttu-id="fb7f5-257">Conectar aplicativo</span><span class="sxs-lookup"><span data-stu-id="fb7f5-257">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb7f5-258">No Windows 10, versão 2004 e posterior, o aplicativo Connect para projeção sem fio usando Miracast não é instalado por padrão, mas está disponível como um recurso opcional.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-258">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="fb7f5-259">Se você tiver instalado (ou atualizado para) o Windows versão 2004 ou posterior, poderá ver o seguinte na tela Projetando para este computador nas configurações:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-259">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Project para este computador](images/sh2-project.png) 


1. <span data-ttu-id="fb7f5-261">Para instalar o aplicativo na página de configurações "Projetando para este computador", selecione Recursos opcionais \*\*\*\* Adicionar um recurso e, em seguida, instalar o aplicativo De  >  \*\*\*\* **exibição sem** fio.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-261">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="fb7f5-262">Em **Alguns dispositivos Windows e Android podem projetar**para este computador quando você diz que está OK , escolha:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-262">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="fb7f5-263">**Disponível em todos os** lugares se o dispositivo não estiver em uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-263">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="fb7f5-264">Caso contrário, escolha **Disponível em qualquer lugar em redes seguras.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-264">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="fb7f5-265">Em **Pedir para projetar para este computador,** escolha Somente primeira **vez**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-265">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="fb7f5-266">Em **Exigir PIN para emparelhamento,** escolha **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-266">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="fb7f5-267">Para então iniciar o aplicativo e fixá-lo na barra de tarefas, pesquise **por Connect**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-267">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="fb7f5-268">Abra o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-268">Open the app.</span></span> <span data-ttu-id="fb7f5-269">Enquanto o aplicativo estiver aberto, clique com o botão direito do mouse no ícone do aplicativo Conectar na barra de tarefas e selecione **o pino na**barra de tarefas .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-269">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="fb7f5-270">Em seguida, feche o aplicativo Connect.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-270">Then close the Connect app.</span></span> <span data-ttu-id="fb7f5-271">**O project para esse computador pode** não funcionar, a menos que o aplicativo tenha sido executado pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-271">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="fb7f5-272">Configuração recomendada quando não estiver na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-272">Recommended configuration when not on the corporate network:</span></span>

![Configurações em casa](images/project1.png)

<span data-ttu-id="fb7f5-274">Configuração recomendada na rede corporativa:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-274">Recommended configuration on the corporate network:</span></span>

![Configurações no trabalho](images/project2.png)

### <a name="your-phone"></a><span data-ttu-id="fb7f5-276">Seu Telefone</span><span class="sxs-lookup"><span data-stu-id="fb7f5-276">Your Phone</span></span>

<span data-ttu-id="fb7f5-277">O **aplicativo Seu Telefone** é instalado por padrão no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-277">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="fb7f5-278">Se ele não estiver presente, você também poderá instalá-lo na Windows Store.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-278">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="fb7f5-279">Para obter informações sobre como configurar o aplicativo, consulte Como configurar Seu Telefone no Windows 10 e sincronizar dados entre seu <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> computador e </a> telefone.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-279">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="fb7f5-280">Consulte Também <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Como corrigir problemas comuns com o aplicativo Seu Telefone no Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-280">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <a name="fancy-zones"></a><span data-ttu-id="fb7f5-281">Zonas sofisticadas</span><span class="sxs-lookup"><span data-stu-id="fb7f5-281">Fancy Zones</span></span>


<span data-ttu-id="fb7f5-282">**Zonas Sofisticadas** faz parte de uma coleção de ferramentas chamadas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> no GitHub..</span><span class="sxs-lookup"><span data-stu-id="fb7f5-282">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="fb7f5-283">É uma ótima maneira de utilizar a propriedade de tela em um Surface Hub 2, dando a você a capacidade de definir layouts fixos em sua exibição ("zonas") e, em seguida, selecione qual aplicativo será executado em cada zona.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-283">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="fb7f5-284">O [wiki do PowerToys tem](https://github.com/microsoft/PowerToys/wiki) instruções sobre como usar e personalizar cada ferramenta, incluindo [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-284">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="fb7f5-285">Em alto nível – depois de instalar o PowerToys, você pode selecionar ou criar um layout personalizado e, em seguida, segurar a tecla de turno para baixo e arrastar ou usar teclas de teclado para mover um aplicativo em execução para zonas específicas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-285">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="fb7f5-286">Usar um Bluetooth ou o teclado USB e o mouse ajudarão com isso, ou você pode usar o teclado touch na tela e o touchpad.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-286">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="fb7f5-287">Dicas de power toys</span><span class="sxs-lookup"><span data-stu-id="fb7f5-287">Power toys tips</span></span>**
- <span data-ttu-id="fb7f5-288">Para receber notificações por email das atualizações de versão do PowerToys no GitHub, clique no botão "inscrever-se" na parte superior da [página](https://github.com/microsoft/PowerToys/releases).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-288">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="fb7f5-289">Depois que o PowerToys for instalado, você poderá receber notificações do Windows e/ou baixar e instalar as atualizações mais recentes configurando as configurações do PowerToys **Baixar** atualizações automaticamente para.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-289">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="fb7f5-290">Para acessar as configurações do PowerToys, \*\*\*\* selecione o quilate para cima Executando aplicativos na barra de tarefas e clique com o botão direito do mouse ou pressione e segure o ícone PowerToys até que o menu apareça.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-290">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="fb7f5-291">Selecione "Configurações".</span><span class="sxs-lookup"><span data-stu-id="fb7f5-291">Select “Settings”.</span></span>
- <span data-ttu-id="fb7f5-292">Na parte inferior da página de configurações do PowerToys, a opção **Baixar atualizações automaticamente** para.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-292">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="fb7f5-293">Quando uma atualização for lançada, uma notificação do Windows aparecerá, dando a você a opção de quando instalar a atualização.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-293">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <a name="edge-chromium-browser"></a><span data-ttu-id="fb7f5-294">Navegador edge Chromium</span><span class="sxs-lookup"><span data-stu-id="fb7f5-294">Edge Chromium browser</span></span>

<span data-ttu-id="fb7f5-295">Baixe e instale o novo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> navegador edge Chromium </a> .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-295">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <a name="surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="fb7f5-296">Ferramenta de Diagnóstico de Hardware do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fb7f5-296">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="fb7f5-297">A <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> ferramenta diagnóstico de hardware do Surface Hub disponível </a> gratuitamente na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-297">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="fb7f5-298">A ferramenta foi projetada para ajudá-lo a garantir que o Surface Hub está em melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-298">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="fb7f5-299">Ele contém testes para determinar se o firmware está atualizado e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-299">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="fb7f5-300">Testes interativos permitem confirmar que a funcionalidade essencial está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-300">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="fb7f5-301">Se forem encontrados problemas, os resultados poderão ser salvos e compartilhados com a equipe de suporte do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-301">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="fb7f5-302">Clique no link para instalá-lo na Microsoft Store e fixe o aplicativo na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-302">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <a name="additional-settings"></a><span data-ttu-id="fb7f5-303">Configurações adicionais</span><span class="sxs-lookup"><span data-stu-id="fb7f5-303">Additional settings</span></span>

### <a name="pen-tail-select-to-launch-whiteboard"></a><span data-ttu-id="fb7f5-304">Caneta tail select to launch Whiteboard</span><span class="sxs-lookup"><span data-stu-id="fb7f5-304">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="fb7f5-305">Pesquise **Caneta** e selecione **Caneta & configurações do Windows Ink.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-305">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="fb7f5-306">Na parte inferior da página, em **Atalhos de caneta,** desempenha **Selecionar uma vez** para o Quadro de Branco da **Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-306">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <a name="power-management"></a><span data-ttu-id="fb7f5-307">Gerenciamento de energia</span><span class="sxs-lookup"><span data-stu-id="fb7f5-307">Power management</span></span>

<span data-ttu-id="fb7f5-308">Há várias configurações de energia disponíveis para obter a melhor experiência usando o Windows 10 Pro ou Enterprise no Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-308">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="fb7f5-309">Isso inclui tempos-extra de tela e computador e como eles interagem com a detecção de presença humana interna (Doppler), a proteção de senha e economia de tela e, se apropriado, como passar as configurações de energia da política de grupo destinadas a usuários de laptop/área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-309">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="fb7f5-310">O Windows 10 Pro ou Enterprise no Surface Hub 2 impede que a tela adore por ações de toque, mouse e teclado, bem como a detecção de ocupação humana (Doppler) integrada.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-310">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="fb7f5-311">A detecção de ocência humana é habilitada por padrão, mas, se desejado, ela pode ser desabilitada na UEFI por meio da agregação da opção de dispositivo na ferramenta Configurador uefi do Surface como parte da migração inicial ou pela criação e aplicação de um pacote de configuração UEFI posterior.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-311">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="fb7f5-312">Gerenciamento de Energia: Configurações de sleep de tela e computador</span><span class="sxs-lookup"><span data-stu-id="fb7f5-312">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="fb7f5-313">Selecione **Iniciar**  >  **Configurações do**  >  **Sistema**Energia & de  >  **1.000.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-313">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="fb7f5-314">De definir o controle deslizante do modo de alimentação **como Melhor desempenho.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-314">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="fb7f5-315">Configure os valores de tela e de encefação para sua preferência enquanto também contabilização da detecção de presença do Doppler que acorda o dispositivo quando o movimento é detectado.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-315">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="fb7f5-316">Assim, como prática recomendada, é recomendável definir Tela como Desativar após **2** horas e o computador para **Desativar após 4 horas.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-316">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="fb7f5-317">Gerenciamento de Energia: Economia de tela</span><span class="sxs-lookup"><span data-stu-id="fb7f5-317">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="fb7f5-318">**Pesquise as** configurações de tela de bloqueio e abra a **tela de bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-318">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="fb7f5-319">Configure **configurações de tempo de tempo de tela** e **configurações de economia de tela** para sua preferência.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-319">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="fb7f5-320">Os valores padrão recomendados são:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-320">Recommended default values are:</span></span>

   - <span data-ttu-id="fb7f5-321">Economia de tela como (Nenhum) ou um protetor de tela de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-321">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="fb7f5-322">Tempo de espera para 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-322">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="fb7f5-323">Ao retomar, exibe a tela de logon.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-323">On resume, display logon screen.</span></span>


**<span data-ttu-id="fb7f5-324">Gerenciamento de Energia: Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="fb7f5-324">Power Management: Group Policy</span></span>**

<span data-ttu-id="fb7f5-325">Antes de executar o procedimento a seguir, verifique com seu departamento de IT a aprovação para excluir um dispositivo Surface Hub 2S da política de gerenciamento de energia global.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-325">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="fb7f5-326">Algumas configurações de gerenciamento de energia podem desabilitar a função de detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-326">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="fb7f5-327">Pesquise **o Centro de Software** e abra-o.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-327">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="fb7f5-328">Selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-328">Select **Options**.</span></span>

3. <span data-ttu-id="fb7f5-329">Expanda **o gerenciamento de energia**  e selecione Não aplicar configurações de energia do meu departamento de IT a este **computador**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-329">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Configurações de software](images/soft-cntr.png)

### <a name="storage-sense"></a><span data-ttu-id="fb7f5-331">Sensor de armazenamento</span><span class="sxs-lookup"><span data-stu-id="fb7f5-331">Storage Sense</span></span>

<span data-ttu-id="fb7f5-332">O Surface Hub 2 tem um SSD de 128 GB para armazenamento local, portanto, é necessário considerar o uso de medidas de economia de armazenamento durante o uso normal.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-332">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="fb7f5-333">Para configurar o Sentido de Armazenamento:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-333">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="fb7f5-334">**Pesquise as configurações de armazenamento**, que é encontrada em **Configurações do sistema**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-334">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="fb7f5-335">Em **Configurações,** selecione **Ativar o sentido de armazenamento** para abrir a página **Configurações** de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-335">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="fb7f5-336">Ativar o Sentido de **Armazenamento**para .</span><span class="sxs-lookup"><span data-stu-id="fb7f5-336">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="fb7f5-337">Selecione **Configurar o Sentido de Armazenamento ou execute-o** agora e configure as configurações para manter os arquivos online o máximo possível (devido ao espaço limitado da unidade).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-337">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="fb7f5-338">Configurações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="fb7f5-338">Recommended settings:</span></span>

- <span data-ttu-id="fb7f5-339">Executar o Sentido de Armazenamento = Todos os Dias.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-339">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="fb7f5-340">Exclua arquivos temporários que meus aplicativos não estão usando = a cada 14 dias (pelo menos).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-340">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="fb7f5-341">Exclua arquivos na minha pasta Downloads se eles estão lá há mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-341">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="fb7f5-342">OneDrive: o conteúdo se tornará somente online se não for aberto por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-342">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <a name="tablet-mode"></a><span data-ttu-id="fb7f5-343">Modo tablet</span><span class="sxs-lookup"><span data-stu-id="fb7f5-343">Tablet mode</span></span>

<span data-ttu-id="fb7f5-344">Ativar o modo Tablet, se desejado para necessidades de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-344">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <a name="sound-settings"></a><span data-ttu-id="fb7f5-345">Configurações de som</span><span class="sxs-lookup"><span data-stu-id="fb7f5-345">Sound settings</span></span>

1. <span data-ttu-id="fb7f5-346">Pesquise **as configurações de Sons** e abra esta página.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-346">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="fb7f5-347">Selecione **Painel de Controle de Som** à direita e selecione a guia **Sons.**</span><span class="sxs-lookup"><span data-stu-id="fb7f5-347">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="fb7f5-348">Em **Eventos de Programa,** **desconectar** dispositivo e conexão **de dispositivo** como **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-348">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <a name="silence-notifications"></a><span data-ttu-id="fb7f5-349">Notificações de silêncio</span><span class="sxs-lookup"><span data-stu-id="fb7f5-349">Silence notifications</span></span>

1. <span data-ttu-id="fb7f5-350">Procure ajuda **de Foco e** abra esta página.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-350">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="fb7f5-351">Selecione **Somente Alarmes**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-351">Select **Alarms Only**.</span></span> <span data-ttu-id="fb7f5-352">Isso evitará os sobrevoos de notificação constante.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-352">This will avoid constant notification flyouts.</span></span>

### <a name="disk-cleanup"></a><span data-ttu-id="fb7f5-353">Limpeza de Disco</span><span class="sxs-lookup"><span data-stu-id="fb7f5-353">Disk Cleanup</span></span>

1. <span data-ttu-id="fb7f5-354">**Pesquise a Limpeza de Disco** e abra este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-354">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="fb7f5-355">Em **Arquivos a ser excluído,** selecione os arquivos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-355">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="fb7f5-356">Selecione Também **Limpar arquivos do sistema**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-356">Also select **Clean up system files**.</span></span>

## <a name="complete-and-verify"></a><span data-ttu-id="fb7f5-357">Concluir e verificar</span><span class="sxs-lookup"><span data-stu-id="fb7f5-357">Complete and verify</span></span>

1. <span data-ttu-id="fb7f5-358">Examinar e instalar todas as Atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-358">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="fb7f5-359">Atualizar Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-359">Update Group Policy.</span></span>

   1. <span data-ttu-id="fb7f5-360">Em um prompt de comando elevado, insira **gpupdate /force /boot /wait:0**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-360">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="fb7f5-361">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-361">Restart the device.</span></span>

4. <span data-ttu-id="fb7f5-362">Verifique os aplicativos da barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-362">Verify taskbar apps.</span></span>

   - <span data-ttu-id="fb7f5-363">Conectar Aplicativo</span><span class="sxs-lookup"><span data-stu-id="fb7f5-363">Connect App</span></span>
   - <span data-ttu-id="fb7f5-364">Ícone de bloqueio</span><span class="sxs-lookup"><span data-stu-id="fb7f5-364">Lock Icon</span></span>
   - <span data-ttu-id="fb7f5-365">Captura e Esboço</span><span class="sxs-lookup"><span data-stu-id="fb7f5-365">Snip & Sketch</span></span>
   - <span data-ttu-id="fb7f5-366">Teams (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="fb7f5-366">Teams (if applicable)</span></span>
   - <span data-ttu-id="fb7f5-367">Office Apps (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="fb7f5-367">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="fb7f5-368">Surface App</span><span class="sxs-lookup"><span data-stu-id="fb7f5-368">Surface App</span></span>
   - <span data-ttu-id="fb7f5-369">Quadro de Comunicações</span><span class="sxs-lookup"><span data-stu-id="fb7f5-369">Whiteboard</span></span>
    
5. <span data-ttu-id="fb7f5-370">Verifique a detecção de presença.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-370">Verify presence detection.</span></span>

   - <span data-ttu-id="fb7f5-371">A detecção de presença será um ícone verde na bandeja do sistema.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-371">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="fb7f5-372">Verifique se a projeção para esse computador está habilitada com o Aplicativo Connect.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-372">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="fb7f5-373">Depois de configurar  **o Project para essas configurações** de computador, execute o Aplicativo conectar pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-373">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="fb7f5-374">(Subsequentemente, o Aplicativo Connect não precisa ser executado para projetar para o Surface Hub.)</span><span class="sxs-lookup"><span data-stu-id="fb7f5-374">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="fb7f5-375">Verifique as configurações de energia e de sono.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-375">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="fb7f5-376">Screen Saver: 15 minutos, definido como (nenhum), Mystify ou Blank; verifique se a caixa de seleção para exigir senha está selecionada.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-376">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="fb7f5-377">Tela: **Desativar após 2 horas**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-377">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="fb7f5-378">PC:  **Desativar após 4 horas**.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-378">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="fb7f5-379">Verifique se o Windows Hello está funcionando.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-379">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="fb7f5-380">Verifique se a sincronização das configurações está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-380">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="fb7f5-381">Verifique os aplicativos de inicialização.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-381">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="fb7f5-382">Depois de instalar e configurar o Windows 10, o Surface Hub 2S pode ser gerenciado da mesma forma que qualquer outro dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-382">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fb7f5-383">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fb7f5-383">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="fb7f5-384">Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fb7f5-384">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
