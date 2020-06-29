---
title: Habilitar PEAP, EAP-FAST e Cisco LEAP em dispositivos Surface (Surface)
description: Saiba como habilitar o suporte para protocolos PEAP, EAP-FAST ou Cisco LEAP no dispositivo Surface.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: rede, sem fio, dispositivo, implantação, autenticação, protocolo
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830595"
---
# <span data-ttu-id="cbd0c-104">Habilitar PEAP, EAP-FAST e Cisco LEAP em dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="cbd0c-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="cbd0c-105">Saiba como habilitar o suporte para protocolos PEAP, EAP-FAST ou Cisco LEAP no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="cbd0c-106">Se usa PEAP, EAP-FAST ou Cisco LEAP em sua rede corporativa, você provavelmente já sabe que esses três protocolos de autenticação sem fio não têm suporte incluído nos dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="cbd0c-107">Alguns usuários podem descobrir isso ao tentarem se conectar à rede sem fio; outros podem descobri-lo quando não conseguem acessar recursos dentro da rede, como compartilhamentos de arquivos e sites internos.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="cbd0c-108">Para obter mais informações, confira [Protocolo de Autenticação Extensível](https://technet.microsoft.com/network/bb643147).</span><span class="sxs-lookup"><span data-stu-id="cbd0c-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="cbd0c-109">Você pode adicionar suporte para cada protocolo executando um pequeno pacote MSI por meio de um pen drive ou um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="cbd0c-110">Para as organizações que desejam habilitar o suporte a EAP em seus dispositivos Surface, o formato do pacote MSI oferece suporte à implantação com muitas ferramentas de gerenciamento e implantação, como o Microsoft Deployment Toolkit (MDT) e o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="cbd0c-111">Baixar arquivos de instalação para PEAP, EAP-FAST ou Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="cbd0c-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="cbd0c-112">Você pode baixar os arquivos de instalação MSI para PEAP, EAP-FAST ou Cisco LEAP em um único arquivo zip do Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="cbd0c-113">Para baixar este arquivo, acesse a página [Ferramentas do Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) no Centro de Download da Microsoft, clique em **Baixar** e selecione o arquivo **Cisco EAP-Supplicant Installer.zip**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="cbd0c-114">Implantar PEAP, EAP-FAST ou Cisco LEAP com o MDT</span><span class="sxs-lookup"><span data-stu-id="cbd0c-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="cbd0c-115">Se você já está executando uma implantação do Windows em dispositivos Surface em sua organização, é rápido e fácil adicionar os arquivos de instalação de cada protocolo a seu compartilhamento de implantação e configurar a instalação automática durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="cbd0c-116">Você pode até mesmo configurar uma sequência de tarefas que atualiza dispositivos Surface implantados anteriormente para dar suporte a esses protocolos usando o mesmo processo.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="cbd0c-117">Para habilitar o suporte a PEAP, EAP-FAST ou Cisco LEAP em dispositivos Surface recém-implantados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="cbd0c-118">Baixe e extraia os arquivos de instalação de cada protocolo para pastas separadas em um local de fácil acesso.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="cbd0c-119">Abra o MDT Deployment Workbench e expanda seu compartilhamento de implantação para a pasta **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="cbd0c-120">Selecione **Novo Aplicativo** no painel **Ação**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="cbd0c-121">Escolha **Aplicativo com arquivos de origem** para copiar os arquivos MSI para o Compartilhamento de Implantação.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="cbd0c-122">Selecione a pasta que você criou na etapa 1 para o protocolo desejado.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="cbd0c-123">Nomeie a pasta no compartilhamento de implantação em que os arquivos de instalação serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="cbd0c-124">Especifique a linha de comando para implantar o aplicativo:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="cbd0c-125">Para PEAP, use **EAP-PEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="cbd0c-126">Para LEAP, use **EAP-LEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="cbd0c-127">Para EAP-FAST, use **EAP-FAST.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="cbd0c-128">Use as opções padrão para concluir o Assistente para Criar Novo Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="cbd0c-129">Repita as etapas 3 a 8 para cada protocolo desejado.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="cbd0c-130">Depois que você executar essas etapas para importar os três pacotes MSI como aplicativos no MDT, eles estarão disponíveis para seleção na página Aplicativos do Assistente de Implantação do Windows.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="cbd0c-131">Embora, em alguns cenários de implantação simples, isso possa ser suficiente para que os técnicos selecionem cada pacote no momento da implantação, não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="cbd0c-132">Essa prática introduz a possibilidade de que um técnico possa tentar aplicar esses pacotes a computadores que não dispositivos Surface ou que um dispositivo Surface possa ser implantado sem suporte a EAP devido a erros humanos.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="cbd0c-133">Para ocultar esses aplicativos na página Instalar Aplicativos, marque a caixa de seleção **Ocultar este aplicativo no Assistente de Implantação** nas propriedades de cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="cbd0c-134">Depois que os aplicativos estiverem ocultos, não serão exibidos como aplicativos opcionais durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="cbd0c-135">Para implantá-los em sua sequência de tarefas de implantação do Surface, eles devem ser definidos explicitamente para a instalação por meio de uma etapa separada na sequência de tarefas.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="cbd0c-136">Para especificar o(s) protocolo(s) explicitamente, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="cbd0c-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="cbd0c-137">Abra as propriedades de sua sequência de tarefa de implantação do Surface no MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="cbd0c-138">Na guia **Sequência de Tarefas**, selecione a etapa **Instalar Aplicativos** em **Restauração de Estado**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="cbd0c-139">Ela geralmente é encontrada entre as etapas pré-aplicativo e pós-aplicativo do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="cbd0c-140">Use o botão **Adicionar** para criar uma nova etapa **Instalar Aplicativo** da categoria **Geral**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="cbd0c-141">Selecione **Instalar um único aplicativo** na etapa da guia **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="cbd0c-142">Selecione o protocolo EAP desejado na lista.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="cbd0c-143">Repita as etapas 2 a 5 para cada protocolo desejado.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="cbd0c-144">Implantar PEAP, EAP-FAST ou Cisco LEAP com o Gerenciador de Configurações</span><span class="sxs-lookup"><span data-stu-id="cbd0c-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="cbd0c-145">Para organizações que gerenciam dispositivos Surface com o Gerenciador de Configurações, é ainda mais fácil implantar o suporte a PEAP, EAP-FAST ou Cisco LEAP em dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="cbd0c-146">Basta importar cada arquivo MSI como um aplicativo da Biblioteca doe Software e configurar uma implantação para sua coleção de dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="cbd0c-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="cbd0c-147">Para obter mais informações sobre como implantar aplicativos com o Gerenciador de Configurações, confira [Como criar aplicativos no Gerenciador de Configurações](https://technet.microsoft.com/library/gg682159.aspx) e [Como implantar aplicativos no Gerenciador de Configurações](https://technet.microsoft.com/library/gg682082.aspx).</span><span class="sxs-lookup"><span data-stu-id="cbd0c-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 





