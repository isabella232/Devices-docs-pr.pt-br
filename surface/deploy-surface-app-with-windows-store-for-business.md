---
title: Implantar o aplicativo Surface com Microsoft Store para Empresas ou Microsoft Store para Educação (Surface)
description: Saiba como adicionar e baixar o aplicativo Surface com Microsoft Store para Empresas ou Microsoft Store para Educação, bem como instalar o aplicativo Surface com o PowerShell e o MDT.
keywords: surface app, app, deployment, customize
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
ms.date: 4/16/2021
ms.openlocfilehash: c7a882859339ff3d7feeb685c62672bc57c301ec
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576521"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a><span data-ttu-id="5d13e-104">Implantar aplicativo surface com Microsoft Store para Empresas e Education</span><span class="sxs-lookup"><span data-stu-id="5d13e-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="5d13e-105">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="5d13e-105">Applies to</span></span>**

- <span data-ttu-id="5d13e-106">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="5d13e-106">Surface Laptop 4</span></span>
- <span data-ttu-id="5d13e-107">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="5d13e-107">Surface Pro 7+</span></span>
- <span data-ttu-id="5d13e-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="5d13e-108">Surface Laptop Go</span></span>
- <span data-ttu-id="5d13e-109">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="5d13e-109">Surface Pro 7</span></span>
- <span data-ttu-id="5d13e-110">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="5d13e-110">Surface Laptop 3</span></span>
- <span data-ttu-id="5d13e-111">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="5d13e-111">Surface Pro 6</span></span>
- <span data-ttu-id="5d13e-112">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="5d13e-112">Surface Laptop 2</span></span>
- <span data-ttu-id="5d13e-113">Surface Go</span><span class="sxs-lookup"><span data-stu-id="5d13e-113">Surface Go</span></span>
- <span data-ttu-id="5d13e-114">Surface Go com LTE</span><span class="sxs-lookup"><span data-stu-id="5d13e-114">Surface Go with LTE</span></span>
- <span data-ttu-id="5d13e-115">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="5d13e-115">Surface Book 2</span></span>
- <span data-ttu-id="5d13e-116">Surface Pro com LTE Avançado (Model 1807)</span><span class="sxs-lookup"><span data-stu-id="5d13e-116">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="5d13e-117">Surface Pro (Model 1796)</span><span class="sxs-lookup"><span data-stu-id="5d13e-117">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="5d13e-118">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="5d13e-118">Surface Laptop</span></span>
- <span data-ttu-id="5d13e-119">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="5d13e-119">Surface Studio</span></span>
- <span data-ttu-id="5d13e-120">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="5d13e-120">Surface Studio 2</span></span>
- <span data-ttu-id="5d13e-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="5d13e-121">Surface Book</span></span>
- <span data-ttu-id="5d13e-122">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="5d13e-122">Surface Pro 4</span></span>
- <span data-ttu-id="5d13e-123">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="5d13e-123">Surface 3 LTE</span></span>
- <span data-ttu-id="5d13e-124">Surface 3</span><span class="sxs-lookup"><span data-stu-id="5d13e-124">Surface 3</span></span>
- <span data-ttu-id="5d13e-125">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="5d13e-125">Surface Pro 3</span></span>


<span data-ttu-id="5d13e-126">O aplicativo Surface é um aplicativo Microsoft Store leve que fornece controle de muitas configurações e opções específicas do Surface, incluindo:</span><span class="sxs-lookup"><span data-stu-id="5d13e-126">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="5d13e-127">Habilitar ou desabilitar o botão Windows no dispositivo Surface 
</span><span class="sxs-lookup"><span data-stu-id="5d13e-127">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="5d13e-128">Ajustar a sensibilidade de uma Caneta Surface 
</span><span class="sxs-lookup"><span data-stu-id="5d13e-128">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="5d13e-129">Personalizar ações de botão da Caneta Surface 
</span><span class="sxs-lookup"><span data-stu-id="5d13e-129">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="5d13e-130">Habilitar ou desabilitar os aperfeiçoamentos de áudio do Surface 
</span><span class="sxs-lookup"><span data-stu-id="5d13e-130">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="5d13e-131">Acesso rápido para dar suporte a documentação e informações para seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d13e-131">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="5d13e-132">Os clientes que Windows Update normalmente receberão o aplicativo Surface como parte das atualizações automáticas.</span><span class="sxs-lookup"><span data-stu-id="5d13e-132">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="5d13e-133">No entanto, se sua organização estiver preparando imagens para implantação em seus dispositivos Surface, talvez você queira incluir o aplicativo Surface (anteriormente chamado de Surface Hub) em seu processo de imagens e implantação, em vez de exigir que os usuários de cada dispositivo individual baixem e instalem o aplicativo no Microsoft Store ou no Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="5d13e-133">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="5d13e-134">Este artigo não se aplica ao Surface Pro X. Para obter mais informações, consulte [Deploying, managing, and sering Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="5d13e-134">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <a name="surface-app-overview"></a><span data-ttu-id="5d13e-135">Visão geral do aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="5d13e-135">Surface app overview</span></span>

<span data-ttu-id="5d13e-136">O aplicativo Surface está disponível como download gratuito do [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span><span class="sxs-lookup"><span data-stu-id="5d13e-136">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="5d13e-137">Os usuários podem baixá-lo e instalá-lo do Microsoft Store, mas se sua organização usar o Microsoft Store para Empresas, você precisará adicioná-lo ao inventário da sua loja e possivelmente incluir o aplicativo como parte do seu processo de implantação Windows.</span><span class="sxs-lookup"><span data-stu-id="5d13e-137">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="5d13e-138">Esses processos são discutidos ao longo deste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-138">These processes are discussed throughout this article.</span></span> <span data-ttu-id="5d13e-139">Para obter mais informações Microsoft Store para Empresas, [consulte Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/) no Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="5d13e-139">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a><span data-ttu-id="5d13e-140">Adicionar aplicativo Surface a uma Microsoft Store para Empresas de usuário</span><span class="sxs-lookup"><span data-stu-id="5d13e-140">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="5d13e-141">Antes que os usuários possam instalar ou implantar um aplicativo a partir da conta de Microsoft Store para Empresas de uma empresa, os aplicativos desejados primeiro devem ser disponibilizados e licenciados para os usuários de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="5d13e-141">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="5d13e-142">Se você ainda não tiver feito isso, crie uma conta [Microsoft Store para Empresas .](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="5d13e-142">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="5d13e-143">Faça logoff no portal.</span><span class="sxs-lookup"><span data-stu-id="5d13e-143">Log on to the portal.</span></span> 

3. <span data-ttu-id="5d13e-144">Habilitar o licenciamento offline: clique em Gerenciar >configurações da Loja e selecione a caixa de seleção Mostrar **aplicativos licenciados** **offline** para pessoas que estão comprando na loja, conforme mostrado na Figura 1.</span><span class="sxs-lookup"><span data-stu-id="5d13e-144">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="5d13e-145">Para obter mais informações sobre Microsoft Store para Empresas de licenciamento de aplicativos, consulte [Apps in Microsoft Store para Empresas and Education](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="5d13e-145">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Mostrar caixa de seleção de aplicativos de licenças offline](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="5d13e-147">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="5d13e-147">Figure 1.</span></span> <span data-ttu-id="5d13e-148">Habilitar aplicativos para uso offline</span><span class="sxs-lookup"><span data-stu-id="5d13e-148">Enable apps for offline use</span></span>*

4. <span data-ttu-id="5d13e-149">Adicione o aplicativo Surface à sua conta Microsoft Store para Empresas seguindo este procedimento:</span><span class="sxs-lookup"><span data-stu-id="5d13e-149">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="5d13e-150">Clique no menu **Loja.**</span><span class="sxs-lookup"><span data-stu-id="5d13e-150">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="5d13e-151">Na caixa de pesquisa, digite **Aplicativo Surface**e clique no ícone de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5d13e-151">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="5d13e-152">Depois que o aplicativo Surface for apresentado nos resultados da pesquisa, clique no ícone do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-152">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="5d13e-153">Você é apresentado com uma opção (selecione **Online** ou **Offline**), conforme mostrado na Figura 2.</span><span class="sxs-lookup"><span data-stu-id="5d13e-153">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="5d13e-155">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="5d13e-155">Figure 2.</span></span> <span data-ttu-id="5d13e-156">Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário</span><span class="sxs-lookup"><span data-stu-id="5d13e-156">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="5d13e-157">Clique **em Offline** para selecionar o modo de licenciamento offline.</span><span class="sxs-lookup"><span data-stu-id="5d13e-157">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="5d13e-158">Clique **em Obter o aplicativo** para adicionar o aplicativo ao inventário Microsoft Store para Empresas usuário.</span><span class="sxs-lookup"><span data-stu-id="5d13e-158">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="5d13e-159">Conforme mostrado na Figura 3, você verá uma caixa de diálogo que solicita que você reconheça que os aplicativos offline podem ser implantados usando uma ferramenta de gerenciamento ou baixados da página de inventário da empresa em seu armazenamento particular.</span><span class="sxs-lookup"><span data-stu-id="5d13e-159">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="5d13e-160">Janela de confirmação de aplicativo licenciado offline ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figura 3. Reconhecimento de aplicativo licenciado offline*</span><span class="sxs-lookup"><span data-stu-id="5d13e-160">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="5d13e-161">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d13e-161">Click **OK**.</span></span>

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a><span data-ttu-id="5d13e-162">Baixar o aplicativo Surface de uma Microsoft Store para Empresas de usuário</span><span class="sxs-lookup"><span data-stu-id="5d13e-162">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="5d13e-163">Depois de adicionar um aplicativo à conta Microsoft Store para Empresas no modo Offline, você pode baixar e adicionar o aplicativo como um AppxBundle a um compartilhamento de implantação.</span><span class="sxs-lookup"><span data-stu-id="5d13e-163">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="5d13e-164">Faça logoff na conta Microsoft Store para Empresas em https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="5d13e-164">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="5d13e-165">Clique **em Gerenciar aplicativos >aplicativos & software**.</span><span class="sxs-lookup"><span data-stu-id="5d13e-165">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="5d13e-166">Uma lista de todos os aplicativos da sua empresa é exibida, incluindo o aplicativo Surface que você adicionou no aplicativo [Adicionar Surface a](#add-surface-app-to-a-microsoft-store-for-business-account) uma Microsoft Store para Empresas de conta deste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-166">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="5d13e-167">Em **Ações,** clique na reellipse (**...**) e clique em Baixar para uso **offline** para o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="5d13e-167">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="5d13e-168">Selecione as opções \*\*\*\* **de Plataforma** e Arquitetura desejadas nas seleções disponíveis para o aplicativo selecionado, conforme mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="5d13e-168">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exemplo do pacote AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="5d13e-170">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="5d13e-170">Figure 4.</span></span> <span data-ttu-id="5d13e-171">Baixar o pacote AppxBundle para um aplicativo</span><span class="sxs-lookup"><span data-stu-id="5d13e-171">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="5d13e-172">Clique **em Baixar**.</span><span class="sxs-lookup"><span data-stu-id="5d13e-172">Click **Download**.</span></span> <span data-ttu-id="5d13e-173">O pacote AppxBundle será baixado.</span><span class="sxs-lookup"><span data-stu-id="5d13e-173">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="5d13e-174">Observe o caminho do arquivo baixado, pois você precisará disso mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-174">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="5d13e-175">Clique na opção **Licença codificada** ou **Licença não codificada.**</span><span class="sxs-lookup"><span data-stu-id="5d13e-175">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="5d13e-176">Use a opção de licença codificada com ferramentas de gerenciamento como Microsoft Endpoint Configuration Manager ou quando você usa Windows Designer de Configuração para criar um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="5d13e-176">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="5d13e-177">Selecione a opção de licença não codificada ao usar o DISM (Deployment Image Servicing and Management) ou soluções de implantação com base em imagens, incluindo o Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="5d13e-177">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="5d13e-178">Clique **em Gerar** para gerar e baixar a licença do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-178">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="5d13e-179">Certifique-se de observar o caminho do arquivo de licença, pois você precisará disso mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-179">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="5d13e-180">Quando você baixa um aplicativo para uso offline, como o aplicativo Surface, pode notar uma seção na parte inferior da página rotulada **estruturas necessárias.**</span><span class="sxs-lookup"><span data-stu-id="5d13e-180">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="5d13e-181">Os computadores de destino devem ter as estruturas instaladas para que o aplicativo seja executado, portanto, talvez seja necessário repetir o processo de download para cada uma das estruturas necessárias para sua arquitetura (x86 ou x64) e também incluí-las como parte da implantação do Windows discutida posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-181">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="5d13e-182">A Figura 5 mostra as estruturas necessárias para o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="5d13e-182">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Estruturas necessárias para o aplicativo Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="5d13e-184">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="5d13e-184">Figure 5.</span></span> <span data-ttu-id="5d13e-185">Estruturas necessárias para o aplicativo Surface</span><span class="sxs-lookup"><span data-stu-id="5d13e-185">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="5d13e-186">Os números de versão do aplicativo Surface e as estruturas necessárias mudarão à medida que os aplicativos são atualizados.</span><span class="sxs-lookup"><span data-stu-id="5d13e-186">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="5d13e-187">Verifique a versão mais recente do aplicativo Surface e cada estrutura no Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="5d13e-187">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="5d13e-188">Sempre use o aplicativo Surface e as versões recomendadas da estrutura, conforme fornecido pelo Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="5d13e-188">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="5d13e-189">Usar estruturas desatualizadas ou versões incorretas pode resultar em erros ou falhas de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-189">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="5d13e-190">Para baixar as estruturas necessárias para o aplicativo Surface, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="5d13e-190">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="5d13e-191">Clique no **botão Baixar** **em Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="5d13e-191">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="5d13e-192">Isso baixa o Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Arquivo Appx para a pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="5d13e-192">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="5d13e-193">Clique no **botão Baixar** **em Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="5d13e-193">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="5d13e-194">Isso baixa o arquivo Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx para a pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="5d13e-194">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="5d13e-195">Somente a versão de 64 bits (x64) de cada estrutura é necessária para dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="5d13e-195">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="5d13e-196">Os dispositivos Surface são dispositivos UEFI nativos de 64 bits e não são compatíveis com versões de 32 bits (x86) de Windows que exigiriam estruturas de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="5d13e-196">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <a name="install-surface-app-on-your-computer-with-powershell"></a><span data-ttu-id="5d13e-197">Instalar o aplicativo Surface no computador com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d13e-197">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="5d13e-198">O procedimento a seguir provisiona o aplicativo Surface para seu computador e o disponibiliza para quaisquer contas de usuário criadas no computador posteriormente.</span><span class="sxs-lookup"><span data-stu-id="5d13e-198">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="5d13e-199">Usando o procedimento descrito na seção Como baixar o [aplicativo Surface](#download-surface-app-from-a-microsoft-store-for-business-account) Microsoft Store para Empresas conta deste artigo, baixe o aplicativo Surface AppxBundle e o arquivo de licença.</span><span class="sxs-lookup"><span data-stu-id="5d13e-199">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="5d13e-200">Inicie uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="5d13e-200">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="5d13e-201">Se você não executar o PowerShell como administrador, a sessão não terá as permissões necessárias para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-201">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="5d13e-202">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="5d13e-202">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="5d13e-203">Onde `<DownloadPath>` está a pasta onde você baixou o appxBundle e o arquivo de licença Microsoft Store para Empresas conta.</span><span class="sxs-lookup"><span data-stu-id="5d13e-203">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="5d13e-204">Por exemplo, se você baixou os arquivos para c:\Temp, o comando executado será:</span><span class="sxs-lookup"><span data-stu-id="5d13e-204">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="5d13e-205">Agora o aplicativo do Surface estará disponível no computador atual com o Windows.</span><span class="sxs-lookup"><span data-stu-id="5d13e-205">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="5d13e-206">Antes que o aplicativo Surface seja funcional no computador em que ele foi provisionado, você também deve provisioná-los descritos anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-206">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="5d13e-207">Para provisionar essas estruturas, use o procedimento a seguir na sessão elevada do PowerShell que você usou para provisionar o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="5d13e-207">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="5d13e-208">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="5d13e-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="5d13e-209">Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="5d13e-209">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a><span data-ttu-id="5d13e-210">Instalar o aplicativo Surface com o MDT</span><span class="sxs-lookup"><span data-stu-id="5d13e-210">Install Surface app with MDT</span></span>
<span data-ttu-id="5d13e-211">O procedimento a seguir usa o MDT para automatizar a instalação do aplicativo Surface no momento da implantação.</span><span class="sxs-lookup"><span data-stu-id="5d13e-211">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="5d13e-212">O aplicativo é provisionado automaticamente pelo MDT durante a implantação e, assim, você pode usar esse processo com imagens existentes.</span><span class="sxs-lookup"><span data-stu-id="5d13e-212">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="5d13e-213">Este é o processo recomendado para implantar o aplicativo Surface como parte de uma implantação Windows para dispositivos Surface porque ele não reduz a compatibilidade entre plataformas da imagem Windows.</span><span class="sxs-lookup"><span data-stu-id="5d13e-213">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="5d13e-214">Usando o procedimento descrito [anteriormente neste artigo](#download-surface-app-from-a-microsoft-store-for-business-account), baixe o aplicativo Surface AppxBundle e o arquivo de licença.</span><span class="sxs-lookup"><span data-stu-id="5d13e-214">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="5d13e-215">Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem.**</span><span class="sxs-lookup"><span data-stu-id="5d13e-215">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="5d13e-216">Na página **Detalhes do** Comando do Assistente \*\*\*\* para Novo Aplicativo, especifique o Diretório de Trabalho padrão e para o Comando especifique o nome de arquivo do AppxBundle, da seguinte forma: \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5d13e-216">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="5d13e-217">Comando:</span><span class="sxs-lookup"><span data-stu-id="5d13e-217">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="5d13e-218">Diretório de Trabalho: %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="5d13e-218">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="5d13e-219">Para que o aplicativo Surface funcione no computador de destino, ele também exigirá as estruturas descritas anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-219">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="5d13e-220">Use o procedimento a seguir para importar as estruturas necessárias para o aplicativo Surface para o MDT e configurá-las como dependências.</span><span class="sxs-lookup"><span data-stu-id="5d13e-220">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="5d13e-221">Usando o procedimento descrito anteriormente neste artigo, baixe os arquivos de estrutura.</span><span class="sxs-lookup"><span data-stu-id="5d13e-221">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="5d13e-222">Armazene cada estrutura em uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="5d13e-222">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="5d13e-223">Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem.**</span><span class="sxs-lookup"><span data-stu-id="5d13e-223">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="5d13e-224">Na página **Detalhes do Comando,** digite o nome de arquivo de cada aplicativo que você baixou no campo **Comando** e no Diretório de Trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="5d13e-224">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="5d13e-225">Para configurar as estruturas como dependências do aplicativo Surface, use este processo:</span><span class="sxs-lookup"><span data-stu-id="5d13e-225">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="5d13e-226">Abra as propriedades do aplicativo Surface no MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="5d13e-226">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="5d13e-227">Clique na **guia Dependências** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5d13e-227">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="5d13e-228">Marque a caixa de seleção de cada estrutura usando o nome fornecido no Assistente para Novo Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5d13e-228">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="5d13e-229">Após a importação, o aplicativo Surface estará disponível para seleção na etapa **Aplicativos** do Assistente Windows Implantação.</span><span class="sxs-lookup"><span data-stu-id="5d13e-229">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="5d13e-230">Você também pode instalar o aplicativo automaticamente, especificando-o na sequência de tarefas de implantação com este processo:</span><span class="sxs-lookup"><span data-stu-id="5d13e-230">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="5d13e-231">Abra a sequência de tarefas de implantação no MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="5d13e-231">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="5d13e-232">Adicione uma nova tarefa **instalar Aplicativo** na seção **Restaurar Estado** da implantação.</span><span class="sxs-lookup"><span data-stu-id="5d13e-232">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="5d13e-233">Selecione **Instalar um único aplicativo e** especifique o Surface **App** como o aplicativo a **ser instalado.**</span><span class="sxs-lookup"><span data-stu-id="5d13e-233">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="5d13e-234">Para obter mais informações sobre como incluir aplicativos em suas implantações Windows, consulte [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="5d13e-234">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
