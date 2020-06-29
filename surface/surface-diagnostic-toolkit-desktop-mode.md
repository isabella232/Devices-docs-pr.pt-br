---
title: Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho
description: Como usar o SDT para ajudar os usuários em sua organização a executar a ferramenta para identificar e diagnosticar problemas com o dispositivo Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830169"
---
# <span data-ttu-id="b2011-103">Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="b2011-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="b2011-104">Este tópico explica como usar o SDT (Kit de ferramentas de diagnóstico de superfície) para ajudar os usuários em sua organização a executar a ferramenta para identificar e diagnosticar problemas com o dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="b2011-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with the Surface device.</span></span> <span data-ttu-id="b2011-105">A execução bem-sucedida do SDT pode determinar rapidamente se um problema relatado é causado por um erro de hardware ou usuário com falha.</span><span class="sxs-lookup"><span data-stu-id="b2011-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="b2011-106">Para obter uma lista de dispositivos de superfície com suporte no SDT, consulte [implantar o kit de ferramentas de diagnóstico de superfície para empresas](surface-diagnostic-toolkit-business.md).</span><span class="sxs-lookup"><span data-stu-id="b2011-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="b2011-107">Instrua o usuário a instalar [o pacote SDT a](surface-diagnostic-toolkit-business.md#create-custom-sdt) partir de um ponto de distribuição de software ou compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="b2011-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#create-custom-sdt) from a software distribution point or network share.</span></span> <span data-ttu-id="b2011-108">Depois de instalado, você está pronto para orientar o usuário em uma série de testes.</span><span class="sxs-lookup"><span data-stu-id="b2011-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="b2011-109">Comece na Home Page, que permite que os usuários insiram uma descrição do problema e clique em **continuar**, conforme mostrado na Figura 1.</span><span class="sxs-lookup"><span data-stu-id="b2011-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="b2011-110">Inicie o SDT no modo de área de trabalho ](images/sdt-desk-1.png)
 *Figura 1. SDT no modo de área de trabalho*</span><span class="sxs-lookup"><span data-stu-id="b2011-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="b2011-111">Quando o SDT indicar que o dispositivo tem as atualizações mais recentes, clique em **continuar** para avançar para o catálogo de testes disponíveis, conforme mostrado na Figura 2.</span><span class="sxs-lookup"><span data-stu-id="b2011-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="b2011-112">Selecione entre as opções do SDT ](images/sdt-desk-2.png)
 *Figura 2. Selecionar a partir de opções do SDT*</span><span class="sxs-lookup"><span data-stu-id="b2011-112">Select from SDT options](images/sdt-desk-2.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="b2011-113">Você pode optar por executar todos os testes de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="b2011-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="b2011-114">Ou, se você já suspeitar de um problema específico, como uma exibição defeituosa ou um problema de fonte de alimentação, clique em **selecionar** para escolher um dos testes disponíveis e clique em **executar selecionado**, conforme mostrado na Figura 3.</span><span class="sxs-lookup"><span data-stu-id="b2011-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="b2011-115">Consulte a tabela a seguir para obter detalhes de cada teste.</span><span class="sxs-lookup"><span data-stu-id="b2011-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="b2011-116">Selecione testes de hardware ](images/sdt-desk-3.png)
 *Figura 3. Selecionar testes de hardware*</span><span class="sxs-lookup"><span data-stu-id="b2011-116">Select hardware tests](images/sdt-desk-3.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="b2011-117">Teste de hardware</span><span class="sxs-lookup"><span data-stu-id="b2011-117">Hardware test</span></span> | <span data-ttu-id="b2011-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="b2011-118">Description</span></span>
    --- | ---
    <span data-ttu-id="b2011-119">Fonte de alimentação e bateria</span><span class="sxs-lookup"><span data-stu-id="b2011-119">Power Supply and Battery</span></span> |  <span data-ttu-id="b2011-120">Verifica se a fonte de alimentação está funcionando adequadamente</span><span class="sxs-lookup"><span data-stu-id="b2011-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="b2011-121">Vídeo e áudio</span><span class="sxs-lookup"><span data-stu-id="b2011-121">Display and Sound</span></span>   | <span data-ttu-id="b2011-122">Verifica o brilho, pixels bloqueados ou inativos, alto-falante e o microfone funciona</span><span class="sxs-lookup"><span data-stu-id="b2011-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="b2011-123">Portas e acessórios</span><span class="sxs-lookup"><span data-stu-id="b2011-123">Ports and Accessories</span></span>   | <span data-ttu-id="b2011-124">Verifica os acessórios, anexação de tela e funcionamento USB</span><span class="sxs-lookup"><span data-stu-id="b2011-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="b2011-125">Connectivity</span><span class="sxs-lookup"><span data-stu-id="b2011-125">Connectivity</span></span> |  <span data-ttu-id="b2011-126">Verifica a conectividade Bluetooth, sem fio e LTE</span><span class="sxs-lookup"><span data-stu-id="b2011-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="b2011-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="b2011-127">Security</span></span>    | <span data-ttu-id="b2011-128">Verifica problemas relacionados à segurança</span><span class="sxs-lookup"><span data-stu-id="b2011-128">Checks security related issues</span></span>
    <span data-ttu-id="b2011-129">Touch</span><span class="sxs-lookup"><span data-stu-id="b2011-129">Touch</span></span>   | <span data-ttu-id="b2011-130">Verifica problemas relacionados ao toque</span><span class="sxs-lookup"><span data-stu-id="b2011-130">Checks touch related issues</span></span>
    <span data-ttu-id="b2011-131">Teclado e toque</span><span class="sxs-lookup"><span data-stu-id="b2011-131">Keyboard and touch</span></span> |    <span data-ttu-id="b2011-132">Verifica a conexão do teclado integrada e digite a capa</span><span class="sxs-lookup"><span data-stu-id="b2011-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="b2011-133">Sensores</span><span class="sxs-lookup"><span data-stu-id="b2011-133">Sensors</span></span> | <span data-ttu-id="b2011-134">Verifica o funcionamento de sensores diferentes no dispositivo</span><span class="sxs-lookup"><span data-stu-id="b2011-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="b2011-135">Hardware</span><span class="sxs-lookup"><span data-stu-id="b2011-135">Hardware</span></span> |  <span data-ttu-id="b2011-136">Verifica problemas com diferentes componentes de hardware, como placa gráfica e câmera</span><span class="sxs-lookup"><span data-stu-id="b2011-136">Checks issues with different hardware components such as graphics card and camera</span></span>





<span id="multiple" />

## <span data-ttu-id="b2011-137">Executando vários testes de hardware para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="b2011-137">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="b2011-138">O SDT foi projetado como uma ferramenta interativa que executa uma série de testes.</span><span class="sxs-lookup"><span data-stu-id="b2011-138">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="b2011-139">Para cada teste, o SDT fornece instruções Resumindo a natureza do teste e o que os usuários devem esperar ou procurar para que o teste seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="b2011-139">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="b2011-140">Por exemplo, para diagnosticar se o brilho da exibição estiver funcionando corretamente, o SDT começará em zero e aumentará o brilho para 100%, solicitando que os usuários confirmem: respondendo **Sim** ou **não** --se o brilho está funcionando conforme o esperado, conforme mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="b2011-140">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="b2011-141">Para cada teste, se a funcionalidade não funcionar como esperado e o usuário clicar em **não**, o SDT gerará um relatório das possíveis causas e maneiras de solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="b2011-141">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="b2011-142">Executando o diagnóstico de hardware ](images/sdt-desk-4.png)
 *Figura 4. Executando o diagnóstico de hardware*</span><span class="sxs-lookup"><span data-stu-id="b2011-142">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="b2011-143">Se o brilho se ajusta com êxito de 0-100% conforme o esperado, direcione o usuário para clicar em **Sim** e, em seguida, clique em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="b2011-143">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="b2011-144">Se o brilho não for ajustado de 0-100% conforme o esperado, instrua o usuário a clicar em **não** e, em seguida, clicar em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="b2011-144">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="b2011-145">Orientar os usuários nos testes remanescentes, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="b2011-145">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="b2011-146">Quando concluído, o SDT fornece automaticamente um resumo de alto nível do relatório, incluindo as possíveis causas de problemas de hardware, além de orientação para resolução.</span><span class="sxs-lookup"><span data-stu-id="b2011-146">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="b2011-147">Reparar aplicativos</span><span class="sxs-lookup"><span data-stu-id="b2011-147">Repairing applications</span></span>

<span data-ttu-id="b2011-148">O SDT permite que você diagnostique e repare aplicativos que possam estar causando problemas, como mostrado na Figura 5.</span><span class="sxs-lookup"><span data-stu-id="b2011-148">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="b2011-149">Executando reparos ](images/sdt-desk-5.png)
 *Figura 5. Executando reparos*</span><span class="sxs-lookup"><span data-stu-id="b2011-149">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="b2011-150">Gerando logs para analisar problemas</span><span class="sxs-lookup"><span data-stu-id="b2011-150">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="b2011-151">O SDT fornece amplo suporte de diagnóstico habilitado para logs entre aplicativos, Drivers, hardware e problemas do sistema operacional, como mostrado na Figura 6.</span><span class="sxs-lookup"><span data-stu-id="b2011-151">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="b2011-152">Gerando logs ](images/sdt-desk-6.png)
 *Figura 6. Gerando logs*</span><span class="sxs-lookup"><span data-stu-id="b2011-152">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="b2011-153">Gerando relatórios detalhados comparando o dispositivo versus configuração ideal</span><span class="sxs-lookup"><span data-stu-id="b2011-153">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="b2011-154">Com base nos logs, o SDT gera um relatório para problemas baseados em software e firmware que você pode salvar em um local preferencial.</span><span class="sxs-lookup"><span data-stu-id="b2011-154">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="b2011-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b2011-155">Related topics</span></span>

- [<span data-ttu-id="b2011-156">Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos</span><span class="sxs-lookup"><span data-stu-id="b2011-156">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

