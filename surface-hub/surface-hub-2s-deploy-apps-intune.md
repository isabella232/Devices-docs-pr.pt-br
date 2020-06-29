---
title: Implantar aplicativos no Surface Hub 2S usando o Intune
description: Saiba como você pode implantar aplicativos em Surface Hub 2S usando o Intune.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830524"
---
# <span data-ttu-id="cfb92-104">Implantar aplicativos no Surface Hub 2S usando o Intune</span><span class="sxs-lookup"><span data-stu-id="cfb92-104">Deploy apps to Surface Hub 2S using Intune</span></span>

<span data-ttu-id="cfb92-105">Você pode instalar aplicativos adicionais para atender às necessidades da sua equipe ou da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cfb92-105">You can install additional apps to fit your team or organization's needs.</span></span>

## <span data-ttu-id="cfb92-106">Diretrizes de desenvolvedor</span><span class="sxs-lookup"><span data-stu-id="cfb92-106">Developer guidelines</span></span>

- <span data-ttu-id="cfb92-107">O Surface Hub executa apenas [aplicativos da Plataforma Universal do Windows (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span><span class="sxs-lookup"><span data-stu-id="cfb92-107">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="cfb92-108">Os aplicativos criados usando o [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) não serão executados no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cfb92-108">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="cfb92-109">Os aplicativos devem ser voltados para a [família de dispositivos universais](https://msdn.microsoft.com/library/windows/apps/dn894631) ou família de dispositivos da Equipe do Windows.</span><span class="sxs-lookup"><span data-stu-id="cfb92-109">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="cfb92-110">O Surface hub só dá suporte [a aplicativos licenciados offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) da [Microsoft Store para empresas](https://businessstore.microsoft.com/store).</span><span class="sxs-lookup"><span data-stu-id="cfb92-110">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="cfb92-111">Por padrão, os aplicativos devem ser assinados pela Microsoft Store para serem instalados.</span><span class="sxs-lookup"><span data-stu-id="cfb92-111">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="cfb92-112">Durante o processo de teste e desenvolvimento, você também pode optar por executar os aplicativos UWP assinados pelo desenvolvedor colocando o dispositivo no modo de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="cfb92-112">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="cfb92-113">Ao desenvolver e enviar aplicativos para a Microsoft Store, defina a disponibilidade da família de dispositivos e as opções de licenciamento organizacional para garantir que os aplicativos estejam disponíveis para serem executados no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cfb92-113">When developing and submitting apps to the Microsoft Store, set Device family availability and Organizational licensing options to ensure that apps are available to run on Surface Hub.</span></span>
- <span data-ttu-id="cfb92-114">Você precisa de credenciais de administrador para instalar aplicativos no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="cfb92-114">You need admin credentials to install apps on Surface Hub.</span></span> <span data-ttu-id="cfb92-115">Projetado para uso em salas de reunião e outros espaços compartilhados, o Surface Hub impede que usuários regulares acessem a Microsoft Store para baixar e instalar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cfb92-115">Designed for use in meeting rooms and other shared spaces, Surface Hub prevents regular users from accessing the Microsoft Store to download and install apps.</span></span>

## <span data-ttu-id="cfb92-116">Diretrizes de implantação</span><span class="sxs-lookup"><span data-stu-id="cfb92-116">Deployment guidelines</span></span>

<span data-ttu-id="cfb92-117">Você pode implantar aplicativos da plataforma universal do Windows (UWP) em Surface Hub 2S usando o Intune, facilitando a implantação do aplicativo em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cfb92-117">You can deploy Universal Windows Platform (UWP) apps to Surface Hub 2S using Intune, easing app deployment to devices.</span></span>

1. <span data-ttu-id="cfb92-118">Para implantar aplicativos, habilite o MDM para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="cfb92-118">To deploy apps, enable MDM for your organization.</span></span> <span data-ttu-id="cfb92-119">No portal do Intune, selecione o **Intune** como sua autoridade de MDM (recomendado).</span><span class="sxs-lookup"><span data-stu-id="cfb92-119">In the Intune portal, select **Intune** as your MDM Authority (recommended).</span></span> <br>

    ![Escolher autoridade do MDM](images/sh2-set-intune5.png)

2. <span data-ttu-id="cfb92-121">Habilite a Microsoft Store para empresas no Intune.</span><span class="sxs-lookup"><span data-stu-id="cfb92-121">Enable the Microsoft Store for Business in Intune.</span></span> <span data-ttu-id="cfb92-122">Abra o Intune, selecione **aplicativos cliente**  >  **Microsoft Store para empresas.**</span><span class="sxs-lookup"><span data-stu-id="cfb92-122">Open Intune, select **Client apps** > **Microsoft Store for Business.**</span></span> <br>

    ![Habilitar a loja para empresas](images/sh2-deploy-apps-sync.png)

3. <span data-ttu-id="cfb92-124">No Intune, abra **a Microsoft Store para empresas** e selecione **configurações**  >  **distribuir**  >  **ferramentas de gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="cfb92-124">In Intune open **Microsoft Store for Business** and select **Settings** > **Distribute** > **Management tools**.</span></span> <span data-ttu-id="cfb92-125">Escolha o **Microsoft Intune** como sua ferramenta de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="cfb92-125">Choose **Microsoft Intune** as your management tool.</span></span> <br>

    ![Adicionar o Intune como sua ferramenta de gerenciamento](images/sh2-set-intune8.png)

4. <span data-ttu-id="cfb92-127">Na Microsoft Store para empresas, selecione **configurações**de compra de compras  >  **Shop**  >  **Shopping Experience**e, em seguida, selecione **Mostrar aplicativos offline**.</span><span class="sxs-lookup"><span data-stu-id="cfb92-127">In Microsoft Store for Business, select **Settings** > **Shop** > **Shopping Experience**, and then select **Show offline apps**.</span></span> <span data-ttu-id="cfb92-128">Os aplicativos offline fazem referência a aplicativos que podem ser sincronizados com o Intune e implantados de forma centralizada em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfb92-128">Offline apps refer to apps that can be synced to Intune and centrally deployed to a device.</span></span>
5. <span data-ttu-id="cfb92-129">Depois de habilitar compras offline, você pode adquirir licenças offline para aplicativos que você pode sincronizar com o Intune e implantar como licenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfb92-129">After enabling Offline shopping, you can acquire offline licenses for apps that you can sync to Intune and deploy as Device licensing.</span></span>
6. <span data-ttu-id="cfb92-130">Em **Intune**  >  **aplicativos cliente**do Intune  >  ,**Microsoft Store para empresas**, selecione **sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="cfb92-130">In **Intune** > **Client apps** > **Microsoft Store for Business**, select **Sync**.</span></span>
7. <span data-ttu-id="cfb92-131">Na página aplicativos cliente, procure o aplicativo na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cfb92-131">In the Client apps page, search for the app in the apps list.</span></span> <span data-ttu-id="cfb92-132">Atribua os aplicativos ao grupo de dispositivos ou grupos desejado.</span><span class="sxs-lookup"><span data-stu-id="cfb92-132">Assign the apps to the desired device group or groups.</span></span> <span data-ttu-id="cfb92-133">Selecione **tarefas**  >  **Adicionar grupo**.</span><span class="sxs-lookup"><span data-stu-id="cfb92-133">Select **Assignments** > **Add group**.</span></span> <br>

![\* Atribuição de aplicativos a grupos \*](images/sh2-assign-group.png) <br>

8. <span data-ttu-id="cfb92-135">Em tipo de atribuição, escolha **obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="cfb92-135">Under assignment type, choose **Required**.</span></span> <br>

![\* Atribuição de aplicativos a grupos \*](images/sh2-add-group.png) <br>

9. <span data-ttu-id="cfb92-137">Para os grupos selecionados, escolha **Licenciamento de dispositivo** e, em seguida, selecione **OK** e salve a tarefa.</span><span class="sxs-lookup"><span data-stu-id="cfb92-137">For the selected groups, choose **Device licensing** and then select **OK** and save the assignment.</span></span> <br>
 
![\* Atribuição de aplicativos a grupos \*](images/sh2-apps-assign.png)
