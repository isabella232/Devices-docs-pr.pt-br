---
title: Implantar o aplicativo Surface com a Microsoft Store para Empresas ou a Microsoft Store para Educação (Surface)
description: Saiba como adicionar e baixar o aplicativo Surface com a Microsoft Store para Empresas ou a Microsoft Store para Educação, bem como instalar o aplicativo Surface com o PowerShell e o MDT.
keywords: surface app, app, implantação, personalizar
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271068"
---
# <span data-ttu-id="ebe8d-104">Implantar o aplicativo Surface com a Microsoft Store para Empresas e Educação</span><span class="sxs-lookup"><span data-stu-id="ebe8d-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="ebe8d-105">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="ebe8d-105">Applies to</span></span>**

- <span data-ttu-id="ebe8d-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="ebe8d-106">Surface Pro 7+</span></span>
- <span data-ttu-id="ebe8d-107">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="ebe8d-107">Surface Laptop Go</span></span>
- <span data-ttu-id="ebe8d-108">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ebe8d-108">Surface Pro 7</span></span>
- <span data-ttu-id="ebe8d-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="ebe8d-109">Surface Laptop 3</span></span>
- <span data-ttu-id="ebe8d-110">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="ebe8d-110">Surface Pro 6</span></span>
- <span data-ttu-id="ebe8d-111">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="ebe8d-111">Surface Laptop 2</span></span>
- <span data-ttu-id="ebe8d-112">Surface Go</span><span class="sxs-lookup"><span data-stu-id="ebe8d-112">Surface Go</span></span>
- <span data-ttu-id="ebe8d-113">Surface Go com LTE</span><span class="sxs-lookup"><span data-stu-id="ebe8d-113">Surface Go with LTE</span></span>
- <span data-ttu-id="ebe8d-114">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="ebe8d-114">Surface Book 2</span></span>
- <span data-ttu-id="ebe8d-115">Surface Pro com LTE Avançado (Model 1807)</span><span class="sxs-lookup"><span data-stu-id="ebe8d-115">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="ebe8d-116">Surface Pro (Model 1796)</span><span class="sxs-lookup"><span data-stu-id="ebe8d-116">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="ebe8d-117">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="ebe8d-117">Surface Laptop</span></span>
- <span data-ttu-id="ebe8d-118">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="ebe8d-118">Surface Studio</span></span>
- <span data-ttu-id="ebe8d-119">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="ebe8d-119">Surface Studio 2</span></span>
- <span data-ttu-id="ebe8d-120">Surface Book</span><span class="sxs-lookup"><span data-stu-id="ebe8d-120">Surface Book</span></span>
- <span data-ttu-id="ebe8d-121">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="ebe8d-121">Surface Pro 4</span></span>
- <span data-ttu-id="ebe8d-122">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="ebe8d-122">Surface 3 LTE</span></span>
- <span data-ttu-id="ebe8d-123">Surface 3</span><span class="sxs-lookup"><span data-stu-id="ebe8d-123">Surface 3</span></span>
- <span data-ttu-id="ebe8d-124">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="ebe8d-124">Surface Pro 3</span></span>


<span data-ttu-id="ebe8d-125">O aplicativo do Surface é um aplicativo leve da Microsoft Store que fornece controle de muitas configurações e opções específicas do Surface, incluindo:</span><span class="sxs-lookup"><span data-stu-id="ebe8d-125">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="ebe8d-126">Habilitar ou desabilitar o botão Windows no dispositivo Surface 
</span><span class="sxs-lookup"><span data-stu-id="ebe8d-126">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="ebe8d-127">Ajustar a sensibilidade de uma Caneta Surface 
</span><span class="sxs-lookup"><span data-stu-id="ebe8d-127">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="ebe8d-128">Personalizar ações de botão da Caneta Surface 
</span><span class="sxs-lookup"><span data-stu-id="ebe8d-128">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="ebe8d-129">Habilitar ou desabilitar os aperfeiçoamentos de áudio do Surface 
</span><span class="sxs-lookup"><span data-stu-id="ebe8d-129">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="ebe8d-130">Acesso rápido à documentação de suporte e informações do seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="ebe8d-130">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="ebe8d-131">Os clientes que usam o Windows Update normalmente receberão o aplicativo Surface como parte das atualizações automáticas.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-131">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="ebe8d-132">Mas se sua organização estiver preparando imagens para implantação em seus dispositivos Surface, talvez você queira incluir o aplicativo do Surface (anteriormente chamado de Surface Hub) em seu processo de implantação e imagens em vez de exigir que os usuários de cada dispositivo individual baixem e instalem o aplicativo da Microsoft Store ou da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-132">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="ebe8d-133">Este artigo não se aplica ao Surface Pro X. Para obter mais informações, consulte [Implantação, gerenciamento](surface-pro-arm-app-management.md) e manutenção do Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ebe8d-133">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="ebe8d-134">Visão geral do aplicativo do Surface</span><span class="sxs-lookup"><span data-stu-id="ebe8d-134">Surface app overview</span></span>

<span data-ttu-id="ebe8d-135">O aplicativo do Surface está disponível como um download gratuito da [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="ebe8d-135">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="ebe8d-136">Os usuários podem baixá-lo e instalá-lo da Microsoft Store, mas se sua organização usa a Microsoft Store para Empresas, você precisará adicioná-lo ao inventário da loja e possivelmente incluir o aplicativo como parte do processo de implantação do Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-136">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="ebe8d-137">Esses processos são discutidos ao longo deste artigo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-137">These processes are discussed throughout this article.</span></span> <span data-ttu-id="ebe8d-138">Para obter mais informações sobre a Microsoft Store para Empresas, [consulte a Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/) no Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-138">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="ebe8d-139">Adicionar o aplicativo Surface a uma conta da Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="ebe8d-139">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="ebe8d-140">Antes que os usuários possam instalar ou implantar um aplicativo da conta da Microsoft Store para Empresas de uma empresa, os aplicativos desejados devem primeiro ser disponibilizados e licenciados para os usuários de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-140">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="ebe8d-141">Se você ainda não tiver feito isso, crie uma [conta da Microsoft Store para Empresas.](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="ebe8d-141">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="ebe8d-142">Faça logoff no portal.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-142">Log on to the portal.</span></span> 

3. <span data-ttu-id="ebe8d-143">Habilita o licenciamento offline: clique em Gerenciar >configurações da Loja e selecione Mostrar **aplicativos licenciados** **offline** para pessoas que estão comprando na loja, conforme mostrado na Figura 1.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-143">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="ebe8d-144">Para obter mais informações sobre modelos de licenciamento de aplicativos da Microsoft Store para Empresas, consulte Aplicativos na [Microsoft Store para Empresas e Educação.](https://docs.microsoft.com/microsoft-store/)</span><span class="sxs-lookup"><span data-stu-id="ebe8d-144">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Mostrar a caixa de seleção de aplicativos de licenças offline](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="ebe8d-146">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-146">Figure 1.</span></span> <span data-ttu-id="ebe8d-147">Habilitar aplicativos para uso offline</span><span class="sxs-lookup"><span data-stu-id="ebe8d-147">Enable apps for offline use</span></span>*

4. <span data-ttu-id="ebe8d-148">Adicione o aplicativo Surface à sua conta da Microsoft Store para Empresas seguindo este procedimento:</span><span class="sxs-lookup"><span data-stu-id="ebe8d-148">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="ebe8d-149">Clique no menu **Comprar.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-149">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="ebe8d-150">Na caixa de pesquisa, digite **o aplicativo Surface**e clique no ícone de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-150">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="ebe8d-151">Depois que o aplicativo Surface for apresentado nos resultados da pesquisa, clique no ícone do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-151">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="ebe8d-152">Você pode escolher (selecionar **Online** ou **Offline),** conforme mostrado na Figura 2.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-152">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="ebe8d-154">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-154">Figure 2.</span></span> <span data-ttu-id="ebe8d-155">Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário</span><span class="sxs-lookup"><span data-stu-id="ebe8d-155">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="ebe8d-156">Clique **em Offline** para selecionar o modo de licenciamento offline.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-156">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="ebe8d-157">Clique **em Obter o aplicativo** para adicionar o aplicativo ao inventário da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-157">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="ebe8d-158">Conforme mostrado na Figura 3, você verá uma caixa de diálogo solicitando que você confirme que os aplicativos offline podem ser implantados usando uma ferramenta de gerenciamento ou baixados da página de inventário da empresa em seu armazenamento particular.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-158">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="ebe8d-159">Janela de confirmação de aplicativo licenciado offline ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figura 3. Confirmação de aplicativo licenciado offline*</span><span class="sxs-lookup"><span data-stu-id="ebe8d-159">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="ebe8d-160">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-160">Click **OK**.</span></span>

## <span data-ttu-id="ebe8d-161">Baixar o aplicativo Surface de uma conta da Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="ebe8d-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="ebe8d-162">Depois de adicionar um aplicativo à conta da Microsoft Store para Empresas no modo Offline, você pode baixar e adicionar o aplicativo como um AppxBundle a um compartilhamento de implantação.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="ebe8d-163">Faça logoff na conta da Microsoft Store para Empresas em https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="ebe8d-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="ebe8d-164">Clique **em Gerenciar >aplicativos & software.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="ebe8d-165">Uma lista de todos os aplicativos da empresa é exibida, incluindo o aplicativo do Surface que você adicionou no aplicativo Adicionar Surface a uma seção de conta da [Microsoft Store](#add-surface-app-to-a-microsoft-store-for-business-account) para Empresas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="ebe8d-166">Em **Ações,** clique nas reellipses (**...**) e clique em **Baixar para uso offline** para o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="ebe8d-167">Selecione as opções \*\*\*\* de **Plataforma** e Arquitetura desejadas nas seleções disponíveis para o aplicativo selecionado, conforme mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exemplo do pacote AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="ebe8d-169">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-169">Figure 4.</span></span> <span data-ttu-id="ebe8d-170">Baixar o pacote AppxBundle para um aplicativo</span><span class="sxs-lookup"><span data-stu-id="ebe8d-170">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="ebe8d-171">Clique **em Baixar.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-171">Click **Download**.</span></span> <span data-ttu-id="ebe8d-172">O pacote AppxBundle será baixado.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="ebe8d-173">Certifique-se de anotar o caminho do arquivo baixado, pois você precisará disso posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="ebe8d-174">Clique na opção **licença codificada** ou **não codificada.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="ebe8d-175">Use a opção de licença codificada com ferramentas de gerenciamento como o Microsoft Endpoint Configuration Manager ou quando você usa o Designer de Configuração do Windows para criar um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="ebe8d-176">Selecione a opção de licença não codificada ao usar o Gerenciamento e Manutenção de Imagens de Implantação (DISM) ou soluções de implantação baseadas em imagens, incluindo o Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="ebe8d-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="ebe8d-177">Clique **em Gerar** para gerar e baixar a licença do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="ebe8d-178">Certifique-se de anotar o caminho do arquivo de licença, pois você precisará disso mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="ebe8d-179">Ao baixar um aplicativo para uso offline, como o aplicativo Surface, você pode notar uma seção na parte inferior da página rotulada como **estruturas necessárias.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="ebe8d-180">Os computadores de destino devem ter as estruturas instaladas para que o aplicativo seja executado, portanto, talvez seja necessário repetir o processo de download para cada uma das estruturas necessárias para sua arquitetura (x86 ou x64) e também incluí-las como parte da implantação do Windows discutida mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="ebe8d-181">A Figura 5 mostra as estruturas necessárias para o aplicativo do Surface.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Estruturas necessárias para o aplicativo do Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="ebe8d-183">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-183">Figure 5.</span></span> <span data-ttu-id="ebe8d-184">Estruturas necessárias para o aplicativo do Surface</span><span class="sxs-lookup"><span data-stu-id="ebe8d-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="ebe8d-185">Os números de versão do aplicativo Surface e as estruturas necessárias mudarão à medida que os aplicativos são atualizados.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="ebe8d-186">Verifique a versão mais recente do aplicativo Surface e cada estrutura na Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="ebe8d-187">Sempre use o aplicativo do Surface e as versões de estrutura recomendadas, conforme fornecido pela Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="ebe8d-188">O uso de estruturas desatualizadas ou versões incorretas pode resultar em erros ou falhas no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="ebe8d-189">Para baixar as estruturas necessárias para o aplicativo Surface, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ebe8d-189">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="ebe8d-190">Clique no **botão Baixar** em **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="ebe8d-191">Isso baixa o Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Arquivo Appx para a pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="ebe8d-192">Clique no **botão Baixar** em **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="ebe8d-193">Isso baixa o arquivo Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx para a pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="ebe8d-194">Somente a versão de 64 bits (x64) de cada estrutura é necessária para dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="ebe8d-195">Dispositivos Surface são dispositivos UEFI nativos de 64 bits e não são compatíveis com versões de 32 bits (x86) do Windows que exigiriam estruturas de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="ebe8d-196">Instalar o aplicativo Surface em seu computador com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebe8d-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="ebe8d-197">O procedimento a seguir provisiona o aplicativo Surface em seu computador e o disponibiliza para qualquer conta de usuário criada posteriormente no computador.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="ebe8d-198">Usando o procedimento descrito na seção Como baixar o aplicativo Surface de uma seção de conta da [Microsoft Store para](#download-surface-app-from-a-microsoft-store-for-business-account) Empresas deste artigo, baixe o app Surface AppxBundle e o arquivo de licença.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="ebe8d-199">Inicie uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ebe8d-200">Se você não executar o PowerShell como Administrador, a sessão não terá as permissões necessárias para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="ebe8d-201">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="ebe8d-201">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="ebe8d-202">Onde `<DownloadPath>` está a pasta onde você baixou o AppxBundle e o arquivo de licença da conta da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="ebe8d-203">Por exemplo, se você baixou os arquivos para c:\Temp, o comando executado será:</span><span class="sxs-lookup"><span data-stu-id="ebe8d-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="ebe8d-204">Agora o aplicativo do Surface estará disponível no computador atual com o Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-204">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="ebe8d-205">Antes que o aplicativo do Surface seja funcional no computador em que ele foi provisionado, você também deve provisioná-lo conforme descrito anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-205">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="ebe8d-206">Para provisionar essas estruturas, use o procedimento a seguir na sessão elevada do PowerShell que você usou para provisionar o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-206">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="ebe8d-207">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="ebe8d-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="ebe8d-208">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="ebe8d-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="ebe8d-209">Instalar o aplicativo Surface com o MDT</span><span class="sxs-lookup"><span data-stu-id="ebe8d-209">Install Surface app with MDT</span></span>
<span data-ttu-id="ebe8d-210">O procedimento a seguir usa o MDT para automatizar a instalação do aplicativo Surface no momento da implantação.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-210">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="ebe8d-211">O aplicativo é provisionado automaticamente pelo MDT durante a implantação e, assim, você pode usar esse processo com imagens existentes.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-211">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="ebe8d-212">Esse é o processo recomendado para implantar o aplicativo surface como parte de uma implantação do Windows em dispositivos Surface porque ele não reduz a compatibilidade entre plataformas da imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-212">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="ebe8d-213">Usando o procedimento descrito [anteriormente neste artigo,](#download-surface-app-from-a-microsoft-store-for-business-account)baixe o app AppxBundle do Surface e o arquivo de licença.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-213">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="ebe8d-214">Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-214">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="ebe8d-215">Na página **Detalhes do** Comando do Assistente \*\*\*\* para Novo Aplicativo, especifique o Diretório de Trabalho padrão e, para o comando, especifique o nome de arquivo do AppxBundle, da seguinte forma: \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ebe8d-215">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="ebe8d-216">Comando:</span><span class="sxs-lookup"><span data-stu-id="ebe8d-216">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="ebe8d-217">Diretório de Trabalho: %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="ebe8d-217">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="ebe8d-218">Para que o aplicativo do Surface funcione no computador de destino, ele também exigirá as estruturas descritas anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-218">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="ebe8d-219">Use o procedimento a seguir para importar as estruturas necessárias para o aplicativo Surface para o MDT e configurá-las como dependências.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-219">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="ebe8d-220">Usando o procedimento descrito anteriormente neste artigo, baixe os arquivos de estrutura.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-220">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="ebe8d-221">Armazene cada estrutura em uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-221">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="ebe8d-222">Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-222">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="ebe8d-223">Na página **Detalhes do** Comando, digite o nome de arquivo de cada aplicativo que você baixou no campo **Comando** e no Diretório de Trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-223">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="ebe8d-224">Para configurar as estruturas como dependências do aplicativo Surface, use este processo:</span><span class="sxs-lookup"><span data-stu-id="ebe8d-224">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="ebe8d-225">Abra as propriedades do aplicativo Surface no MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-225">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="ebe8d-226">Clique na **guia Dependências** e em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-226">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="ebe8d-227">Marque a caixa de seleção de cada estrutura usando o nome fornecido no Assistente para Novo Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-227">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="ebe8d-228">Após a importação, o aplicativo Do Surface estará disponível para seleção na etapa **Aplicativos** do Assistente de Implantação do Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-228">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="ebe8d-229">Você também pode instalar o aplicativo automaticamente, especificando-o na sequência de tarefas de implantação com este processo:</span><span class="sxs-lookup"><span data-stu-id="ebe8d-229">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="ebe8d-230">Abra a sequência de tarefas de implantação no MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-230">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="ebe8d-231">Adicione uma nova tarefa **instalar Aplicativo** na seção **Restaurar Estado** da implantação.</span><span class="sxs-lookup"><span data-stu-id="ebe8d-231">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="ebe8d-232">Selecione **Instalar um único aplicativo** e especifique o Aplicativo do **Surface** como o Aplicativo a **ser instalado.**</span><span class="sxs-lookup"><span data-stu-id="ebe8d-232">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="ebe8d-233">Para obter mais informações sobre como incluir aplicativos em suas implantações do Windows, consulte [Implantar o Windows 10 com o Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="ebe8d-233">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
