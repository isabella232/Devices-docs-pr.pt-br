---
title: Implantar o aplicativo Surface com a Microsoft Store para empresas ou a Microsoft Store para educação (Surface)
description: Saiba como adicionar e baixar o aplicativo Surface na Microsoft Store para empresas ou Microsoft Store para educação, bem como instalar o aplicativo Surface com o PowerShell e o MDT.
keywords: aplicativo Surface, aplicativo, implantação, personalizar
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
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114709"
---
# <span data-ttu-id="b9d91-104">Implantar o aplicativo Surface com a Microsoft Store para empresas e educação</span><span class="sxs-lookup"><span data-stu-id="b9d91-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="b9d91-105">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="b9d91-105">Applies to</span></span>**

- <span data-ttu-id="b9d91-106">Usar o laptop Surface</span><span class="sxs-lookup"><span data-stu-id="b9d91-106">Surface Laptop Go</span></span>
- <span data-ttu-id="b9d91-107">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="b9d91-107">Surface Pro 7</span></span>
- <span data-ttu-id="b9d91-108">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="b9d91-108">Surface Laptop 3</span></span>
- <span data-ttu-id="b9d91-109">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="b9d91-109">Surface Pro 6</span></span>
- <span data-ttu-id="b9d91-110">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="b9d91-110">Surface Laptop 2</span></span>
- <span data-ttu-id="b9d91-111">Surface Go</span><span class="sxs-lookup"><span data-stu-id="b9d91-111">Surface Go</span></span>
- <span data-ttu-id="b9d91-112">Surface Go com LTE</span><span class="sxs-lookup"><span data-stu-id="b9d91-112">Surface Go with LTE</span></span>
- <span data-ttu-id="b9d91-113">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="b9d91-113">Surface Book 2</span></span>
- <span data-ttu-id="b9d91-114">Surface Pro com LTE Avançado (Model 1807)</span><span class="sxs-lookup"><span data-stu-id="b9d91-114">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="b9d91-115">Surface Pro (Model 1796)</span><span class="sxs-lookup"><span data-stu-id="b9d91-115">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="b9d91-116">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="b9d91-116">Surface Laptop</span></span>
- <span data-ttu-id="b9d91-117">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="b9d91-117">Surface Studio</span></span>
- <span data-ttu-id="b9d91-118">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="b9d91-118">Surface Studio 2</span></span>
- <span data-ttu-id="b9d91-119">Surface Book</span><span class="sxs-lookup"><span data-stu-id="b9d91-119">Surface Book</span></span>
- <span data-ttu-id="b9d91-120">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="b9d91-120">Surface Pro 4</span></span>
- <span data-ttu-id="b9d91-121">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="b9d91-121">Surface 3 LTE</span></span>
- <span data-ttu-id="b9d91-122">Surface 3</span><span class="sxs-lookup"><span data-stu-id="b9d91-122">Surface 3</span></span>
- <span data-ttu-id="b9d91-123">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="b9d91-123">Surface Pro 3</span></span>


<span data-ttu-id="b9d91-124">O aplicativo Surface é um aplicativo da Microsoft Store leve que fornece controle de muitas configurações e opções específicas da superfície, incluindo:</span><span class="sxs-lookup"><span data-stu-id="b9d91-124">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="b9d91-125">Habilitar ou desabilitar o botão Windows no dispositivo Surface 
</span><span class="sxs-lookup"><span data-stu-id="b9d91-125">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="b9d91-126">Ajustar a sensibilidade de uma Caneta Surface 
</span><span class="sxs-lookup"><span data-stu-id="b9d91-126">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="b9d91-127">Personalizar ações de botão da Caneta Surface 
</span><span class="sxs-lookup"><span data-stu-id="b9d91-127">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="b9d91-128">Habilitar ou desabilitar os aperfeiçoamentos de áudio do Surface 
</span><span class="sxs-lookup"><span data-stu-id="b9d91-128">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="b9d91-129">Acesso rápido à documentação de suporte e informações para o seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="b9d91-129">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="b9d91-130">Os clientes que usam o Windows Update normalmente recebem o aplicativo Surface como parte das atualizações automáticas.</span><span class="sxs-lookup"><span data-stu-id="b9d91-130">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="b9d91-131">Mas se a sua organização estiver preparando imagens para implantação em seus dispositivos Surface, talvez você queira incluir o aplicativo Surface (antes chamado de Surface Hub) no seu processo de criação de imagens e implantação em vez de exigir que os usuários de cada dispositivo específico baixem e instalem o aplicativo da Microsoft Store ou da Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="b9d91-131">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="b9d91-132">Este artigo não se aplica ao Surface Pro X. Para obter mais informações, consulte [implantação, gerenciamento e manutenção do Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="b9d91-132">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="b9d91-133">Visão geral do aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="b9d91-133">Surface app overview</span></span>

<span data-ttu-id="b9d91-134">O aplicativo Surface está disponível como um download gratuito na [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span><span class="sxs-lookup"><span data-stu-id="b9d91-134">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="b9d91-135">Os usuários podem baixar e instalá-lo na Microsoft Store, mas se a sua organização usa a Microsoft Store para empresas, você precisará adicioná-lo ao estoque da sua loja e, possivelmente, incluir o aplicativo como parte do processo de implantação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b9d91-135">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="b9d91-136">Esses processos são discutidos em todo este artigo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-136">These processes are discussed throughout this article.</span></span> <span data-ttu-id="b9d91-137">Para obter mais informações sobre a Microsoft Store para empresas, consulte [Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/) no TechCenter do Windows.</span><span class="sxs-lookup"><span data-stu-id="b9d91-137">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="b9d91-138">Adicionar aplicativo Surface a uma conta da Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="b9d91-138">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="b9d91-139">Antes que os usuários possam instalar ou implantar um aplicativo da conta da Microsoft Store para empresas de uma empresa, os aplicativos desejados devem primeiro ser disponibilizados e licenciados para os usuários de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="b9d91-139">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="b9d91-140">Se você ainda não tiver feito isso, crie uma [conta da Microsoft Store para empresas](https://www.microsoft.com/business-store).</span><span class="sxs-lookup"><span data-stu-id="b9d91-140">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="b9d91-141">Faça logon no Portal.</span><span class="sxs-lookup"><span data-stu-id="b9d91-141">Log on to the portal.</span></span> 

3. <span data-ttu-id="b9d91-142">Habilitar o licenciamento offline: clique em **configurações da loja de gerenciar->** e marque a caixa de seleção **Mostrar aplicativos licenciados offline para as pessoas comprando na loja** , conforme mostrado na Figura 1.</span><span class="sxs-lookup"><span data-stu-id="b9d91-142">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="b9d91-143">Para obter mais informações sobre os modelos de licenciamento do aplicativo Microsoft Store para empresas, consulte [aplicativos na Microsoft Store para empresas e instituições de ensino](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="b9d91-143">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Caixa de seleção Mostrar aplicativos de licenças offline](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="b9d91-145">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="b9d91-145">Figure 1.</span></span> <span data-ttu-id="b9d91-146">Habilitar aplicativos para uso offline</span><span class="sxs-lookup"><span data-stu-id="b9d91-146">Enable apps for offline use</span></span>*

4. <span data-ttu-id="b9d91-147">Adicione o aplicativo Surface à sua conta da Microsoft Store para empresas seguindo este procedimento:</span><span class="sxs-lookup"><span data-stu-id="b9d91-147">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="b9d91-148">Clique no menu **comprar** .</span><span class="sxs-lookup"><span data-stu-id="b9d91-148">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="b9d91-149">Na caixa de pesquisa, digite **aplicativo Surface**e, em seguida, clique no ícone Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="b9d91-149">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="b9d91-150">Após o aplicativo Surface ser apresentado nos resultados da pesquisa, clique no ícone do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-150">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="b9d91-151">Você verá uma opção (selecione **online** ou **offline**), conforme mostrado na Figura 2.</span><span class="sxs-lookup"><span data-stu-id="b9d91-151">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Selecionar o modo de licenciamento offline e adicionar o aplicativo ao seu inventário](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="b9d91-153">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="b9d91-153">Figure 2.</span></span> <span data-ttu-id="b9d91-154">Selecionar o modo de licenciamento offline e adicionar o aplicativo ao seu inventário</span><span class="sxs-lookup"><span data-stu-id="b9d91-154">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="b9d91-155">Clique em **offline** para selecionar o modo de licenciamento offline.</span><span class="sxs-lookup"><span data-stu-id="b9d91-155">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="b9d91-156">Clique em **obter o aplicativo** para adicionar o aplicativo ao seu inventário da Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="b9d91-156">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="b9d91-157">Conforme mostrado na Figura 3, você verá uma caixa de diálogo que solicita que você confirme que os aplicativos offline podem ser implantados usando uma ferramenta de gerenciamento ou baixados da página de inventário da empresa em seu repositório particular.</span><span class="sxs-lookup"><span data-stu-id="b9d91-157">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="b9d91-158">Janela de confirmação de aplicativo licenciada offline ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figura 3. Confirmação de aplicativo licenciada offline*</span><span class="sxs-lookup"><span data-stu-id="b9d91-158">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="b9d91-159">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-159">Click **OK**.</span></span>

## <span data-ttu-id="b9d91-160">Baixar o aplicativo Surface de uma conta da Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="b9d91-160">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="b9d91-161">Depois de adicionar um aplicativo à conta da Microsoft Store para empresas no modo offline, você pode baixar e adicionar o aplicativo como uma AppxBundle para um compartilhamento de implantação.</span><span class="sxs-lookup"><span data-stu-id="b9d91-161">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="b9d91-162">Faça logon na conta da Microsoft Store para empresas em https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="b9d91-162">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="b9d91-163">Clique em **Manage->Apps & software**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-163">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="b9d91-164">Uma lista de todos os aplicativos da sua empresa é exibida, incluindo o aplicativo Surface que você adicionou na seção [Adicionar aplicativo Surface a uma conta da Microsoft Store para empresas](#add-surface-app-to-a-microsoft-store-for-business-account) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-164">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="b9d91-165">Em **ações**, clique nas reticências (**...**) e, em seguida, clique em **baixar para uso offline** do aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="b9d91-165">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="b9d91-166">Selecione as opções de **plataforma** e **arquitetura** desejadas nas seleções disponíveis para o aplicativo selecionado, como mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="b9d91-166">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exemplo do pacote AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="b9d91-168">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="b9d91-168">Figure 4.</span></span> <span data-ttu-id="b9d91-169">Baixar o pacote AppxBundle para um aplicativo</span><span class="sxs-lookup"><span data-stu-id="b9d91-169">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="b9d91-170">Clique em **baixar**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-170">Click **Download**.</span></span> <span data-ttu-id="b9d91-171">O pacote AppxBundle será baixado.</span><span class="sxs-lookup"><span data-stu-id="b9d91-171">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="b9d91-172">Certifique-se de anotar o caminho do arquivo baixado porque você precisará mais tarde neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-172">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="b9d91-173">Clique na opção **licença codificada** ou **licença não codificada** .</span><span class="sxs-lookup"><span data-stu-id="b9d91-173">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="b9d91-174">Use a opção de licença codificada com ferramentas de gerenciamento como o Microsoft Endpoint Configuration Manager ou use o designer de configuração do Windows para criar um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="b9d91-174">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="b9d91-175">Selecione a opção licença não codificada quando você usar o DISM (gerenciamento e manutenção de imagens de implantação) ou soluções de implantação com base em imagens, incluindo o kit de ferramentas de implantação da Microsoft (MDT).</span><span class="sxs-lookup"><span data-stu-id="b9d91-175">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="b9d91-176">Clique em **gerar** para gerar e baixar a licença do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-176">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="b9d91-177">Certifique-se de anotar o caminho do arquivo de licença porque você precisará mais tarde neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-177">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="b9d91-178">Ao baixar um aplicativo para uso offline, como o aplicativo Surface, você pode observar uma seção na parte inferior da página rotulada **estruturas obrigatórias**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-178">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="b9d91-179">Seus computadores de destino devem ter estruturas instaladas para que o aplicativo seja executado, portanto, talvez seja necessário repetir o processo de download para cada um dos frameworks obrigatórios para a sua arquitetura (x86 ou x64) e também incluí-los como parte da sua implantação do Windows abordada posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-179">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="b9d91-180">A Figura 5 mostra as estruturas necessárias para o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="b9d91-180">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Estruturas obrigatórias para o aplicativo Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="b9d91-182">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="b9d91-182">Figure 5.</span></span> <span data-ttu-id="b9d91-183">Estruturas obrigatórias para o aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="b9d91-183">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="b9d91-184">Os números de versão do aplicativo Surface e das estruturas obrigatórias serão alterados à medida que os aplicativos forem atualizados.</span><span class="sxs-lookup"><span data-stu-id="b9d91-184">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="b9d91-185">Verifique a última versão do aplicativo Surface e cada estrutura na Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="b9d91-185">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="b9d91-186">Sempre use o aplicativo Surface e versões de estrutura recomendadas conforme fornecido pela Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="b9d91-186">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="b9d91-187">Usar estruturas desatualizadas ou as versões incorretas pode resultar em erros ou falhas do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-187">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="b9d91-188">Para baixar as estruturas necessárias para o aplicativo Surface, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b9d91-188">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="b9d91-189">Clique no botão **baixar** em **Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-189">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="b9d91-190">Isso faz o download do _14. VCLibs. 140.00.0.23816. _x64__8wekyb3d8bbwe. Arquivo Appx para a pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="b9d91-190">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="b9d91-191">Clique no botão **baixar** em **Microsoft. net. Native. Runtime. 1.1 _1.1.23406.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-191">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="b9d91-192">Isso faz o download do arquivo Microsoft. NET. Native. Runtime. 1.1 _1.23406.0 _x64__8wekyb3d8bbwe. Appx para a pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="b9d91-192">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="b9d91-193">Somente a versão de 64 bits (x64) de cada estrutura é necessária para os dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="b9d91-193">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="b9d91-194">Os dispositivos de superfície são dispositivos UEFI nativos de 64 bits e não são compatíveis com versões de 32 bits (x86) do Windows que exigem estruturas de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="b9d91-194">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="b9d91-195">Instalar o aplicativo Surface em seu computador com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9d91-195">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="b9d91-196">O procedimento a seguir provisiona o aplicativo Surface para o seu computador e o disponibiliza para qualquer conta de usuário criada no computador posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b9d91-196">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="b9d91-197">Usando o procedimento descrito na seção [como baixar o aplicativo Surface a partir de uma conta da Microsoft Store para empresas](#download-surface-app-from-a-microsoft-store-for-business-account) deste artigo, baixe o aplicativo Surface AppxBundle e o arquivo de licença.</span><span class="sxs-lookup"><span data-stu-id="b9d91-197">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="b9d91-198">Inicie uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="b9d91-198">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="b9d91-199">Se você não executar o PowerShell como administrador, a sessão não terá as permissões necessárias para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-199">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="b9d91-200">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="b9d91-200">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="b9d91-201">Onde `<DownloadPath>` é a pasta onde você baixou o AppxBundle e o arquivo de licença da conta da Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="b9d91-201">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="b9d91-202">Por exemplo, se você tiver baixado os arquivos para c:\Temp, o comando que executar será:</span><span class="sxs-lookup"><span data-stu-id="b9d91-202">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="b9d91-203">Agora o aplicativo do Surface estará disponível no computador atual com o Windows.</span><span class="sxs-lookup"><span data-stu-id="b9d91-203">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="b9d91-204">Antes de o aplicativo Surface ser funcional no computador em que foi provisionado, você também deve provisionar as estruturas descritas anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-204">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="b9d91-205">Para provisionar essas estruturas, use o procedimento a seguir na sessão elevado do PowerShell que você usou para provisionar o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="b9d91-205">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="b9d91-206">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="b9d91-206">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="b9d91-207">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="b9d91-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="b9d91-208">Instalar o aplicativo Surface com o MDT</span><span class="sxs-lookup"><span data-stu-id="b9d91-208">Install Surface app with MDT</span></span>
<span data-ttu-id="b9d91-209">O procedimento a seguir usa o MDT para automatizar a instalação do aplicativo Surface no momento da implantação.</span><span class="sxs-lookup"><span data-stu-id="b9d91-209">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="b9d91-210">O aplicativo é provisionado automaticamente pelo MDT durante a implantação e, assim, você pode usar esse processo com imagens existentes.</span><span class="sxs-lookup"><span data-stu-id="b9d91-210">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="b9d91-211">Este é o processo recomendado para implantar o aplicativo Surface como parte de uma implantação do Windows para dispositivos Surface porque ele não reduz a compatibilidade entre plataformas da imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="b9d91-211">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="b9d91-212">Usando o procedimento descrito [anteriormente neste artigo](#download-surface-app-from-a-microsoft-store-for-business-account), baixe o arquivo de licença/AppxBundle do aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="b9d91-212">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="b9d91-213">Usando o assistente para novo aplicativo no ambiente de implantação do MDT, importe os arquivos baixados como um novo **aplicativo com arquivos de origem**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-213">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="b9d91-214">Na página **detalhes do comando** do assistente para novo aplicativo, especifique o **diretório de trabalho** padrão e para o **comando** especifique o nome de arquivo do AppxBundle, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b9d91-214">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="b9d91-215">CommandLine</span><span class="sxs-lookup"><span data-stu-id="b9d91-215">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="b9d91-216">Diretório de trabalho:%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="b9d91-216">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="b9d91-217">Para que o aplicativo Surface funcione no computador de destino, ele também precisará das estruturas descritas anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-217">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="b9d91-218">Use o procedimento a seguir para importar os frameworks necessários para o aplicativo Surface para o MDT e configurá-los como dependências.</span><span class="sxs-lookup"><span data-stu-id="b9d91-218">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="b9d91-219">Usando o procedimento descrito anteriormente neste artigo, baixe os arquivos da estrutura.</span><span class="sxs-lookup"><span data-stu-id="b9d91-219">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="b9d91-220">Armazene cada estrutura em uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="b9d91-220">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="b9d91-221">Usando o assistente para novo aplicativo no ambiente de implantação do MDT, importe os arquivos baixados como um novo **aplicativo com arquivos de origem**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-221">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="b9d91-222">Na página **detalhes do comando** , digite o nome do arquivo de cada aplicativo que você baixou no campo de **comando** e o diretório de trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="b9d91-222">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="b9d91-223">Para configurar as estruturas como dependências do aplicativo Surface, use este processo:</span><span class="sxs-lookup"><span data-stu-id="b9d91-223">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="b9d91-224">Abra as propriedades do aplicativo Surface na implantação do MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="b9d91-224">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="b9d91-225">Clique na guia **dependências** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-225">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="b9d91-226">Marque a caixa de seleção de cada estrutura usando o nome fornecido no Assistente para novo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b9d91-226">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="b9d91-227">Após a importação, o aplicativo Surface estará disponível para seleção na etapa **aplicativos** do assistente de implantação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b9d91-227">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="b9d91-228">Você também pode instalar o aplicativo automaticamente, especificando-o na sequência de tarefas de implantação com este processo:</span><span class="sxs-lookup"><span data-stu-id="b9d91-228">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="b9d91-229">Abra a sequência de tarefas de implantação no MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="b9d91-229">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="b9d91-230">Adicione uma nova tarefa **instalar Aplicativo** na seção **Restaurar Estado** da implantação.</span><span class="sxs-lookup"><span data-stu-id="b9d91-230">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="b9d91-231">Selecione **instalar um único aplicativo** e especifique o **aplicativo Surface** como o **aplicativo a ser instalado**.</span><span class="sxs-lookup"><span data-stu-id="b9d91-231">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="b9d91-232">Para obter mais informações sobre como incluir aplicativos em suas implantações do Windows, consulte [implantar o Windows 10 com o kit de ferramentas de implantação da Microsoft](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="b9d91-232">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
