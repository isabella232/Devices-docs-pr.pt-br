---
title: Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho
description: Como usar o SDT para ajudar os usuários em sua organização a executar a ferramenta para identificar e diagnosticar problemas com o dispositivo Surface e enviar solicitações de suporte diretamente da ferramenta.
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
ms.date: 7/31/2020
ms.openlocfilehash: 8b113d16f2053fe0904518b2643f1bafeaebdf64
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145936"
---
# <span data-ttu-id="cf86f-103">Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="cf86f-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="cf86f-104">Este tópico explica como usar o SDT (Kit de ferramentas de diagnóstico de superfície) para ajudar os usuários em sua organização a executarem a ferramenta para identificar e diagnosticar problemas com o dispositivo de superfície e enviar solicitações de suporte diretamente da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="cf86f-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with their Surface device as well as submit Support requests directly from the tool.</span></span> 

<span data-ttu-id="cf86f-105">A execução bem-sucedida do SDT pode determinar rapidamente se um problema relatado é causado por um erro de hardware ou usuário com falha.</span><span class="sxs-lookup"><span data-stu-id="cf86f-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="cf86f-106">Para obter uma lista de dispositivos de superfície com suporte no SDT, consulte [implantar o kit de ferramentas de diagnóstico de superfície para empresas](surface-diagnostic-toolkit-business.md).</span><span class="sxs-lookup"><span data-stu-id="cf86f-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="cf86f-107">Direcione o usuário para instalar [o pacote SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)) de um ponto de distribuição de software ou compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="cf86f-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)) from a software distribution point or network share.</span></span> <span data-ttu-id="cf86f-108">Depois de instalado, você está pronto para orientar o usuário em uma série de testes.</span><span class="sxs-lookup"><span data-stu-id="cf86f-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="cf86f-109">Comece na Home Page, que permite que os usuários insiram uma descrição do problema e clique em **continuar**, conforme mostrado na Figura 1.</span><span class="sxs-lookup"><span data-stu-id="cf86f-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="cf86f-110">Inicie o SDT no modo de área de trabalho ](images/sdt-desk-1.png)
 *Figura 1. SDT no modo de área de trabalho*</span><span class="sxs-lookup"><span data-stu-id="cf86f-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="cf86f-111">Quando o SDT indicar que o dispositivo tem as atualizações mais recentes, clique em **continuar** para avançar para o catálogo de testes disponíveis, conforme mostrado na Figura 2.</span><span class="sxs-lookup"><span data-stu-id="cf86f-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="cf86f-112">Selecione entre as opções do SDT ](images/sdt1.png)
 *Figura 2. Selecionar a partir de opções do SDT*</span><span class="sxs-lookup"><span data-stu-id="cf86f-112">Select from SDT options](images/sdt1.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="cf86f-113">Você pode optar por executar todos os testes de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="cf86f-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="cf86f-114">Ou, se você já suspeitar de um problema específico, como uma exibição defeituosa ou um problema de fonte de alimentação, clique em **selecionar** para escolher um dos testes disponíveis e clique em **executar selecionado**, conforme mostrado na Figura 3.</span><span class="sxs-lookup"><span data-stu-id="cf86f-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="cf86f-115">Consulte a tabela a seguir para obter detalhes de cada teste.</span><span class="sxs-lookup"><span data-stu-id="cf86f-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="cf86f-116">Selecione testes de hardware ](images/sdt2.png)
 *Figura 3. Selecionar testes de hardware*</span><span class="sxs-lookup"><span data-stu-id="cf86f-116">Select hardware tests](images/sdt2.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="cf86f-117">Teste de hardware</span><span class="sxs-lookup"><span data-stu-id="cf86f-117">Hardware test</span></span> | <span data-ttu-id="cf86f-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="cf86f-118">Description</span></span>
    --- | ---
    <span data-ttu-id="cf86f-119">Fonte de alimentação e bateria</span><span class="sxs-lookup"><span data-stu-id="cf86f-119">Power Supply and Battery</span></span> |  <span data-ttu-id="cf86f-120">Verifica se a fonte de alimentação está funcionando adequadamente</span><span class="sxs-lookup"><span data-stu-id="cf86f-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="cf86f-121">Vídeo e áudio</span><span class="sxs-lookup"><span data-stu-id="cf86f-121">Display and Sound</span></span>   | <span data-ttu-id="cf86f-122">Verifica o brilho, pixels bloqueados ou inativos, alto-falante e o microfone funciona</span><span class="sxs-lookup"><span data-stu-id="cf86f-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="cf86f-123">Portas e acessórios</span><span class="sxs-lookup"><span data-stu-id="cf86f-123">Ports and Accessories</span></span>   | <span data-ttu-id="cf86f-124">Verifica os acessórios, anexação de tela e funcionamento USB</span><span class="sxs-lookup"><span data-stu-id="cf86f-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="cf86f-125">Connectivity</span><span class="sxs-lookup"><span data-stu-id="cf86f-125">Connectivity</span></span> |  <span data-ttu-id="cf86f-126">Verifica a conectividade Bluetooth, sem fio e LTE</span><span class="sxs-lookup"><span data-stu-id="cf86f-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="cf86f-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="cf86f-127">Security</span></span>    | <span data-ttu-id="cf86f-128">Verifica problemas relacionados à segurança</span><span class="sxs-lookup"><span data-stu-id="cf86f-128">Checks security related issues</span></span>
    <span data-ttu-id="cf86f-129">Touch</span><span class="sxs-lookup"><span data-stu-id="cf86f-129">Touch</span></span>   | <span data-ttu-id="cf86f-130">Verifica problemas relacionados ao toque</span><span class="sxs-lookup"><span data-stu-id="cf86f-130">Checks touch related issues</span></span>
    <span data-ttu-id="cf86f-131">Teclado e toque</span><span class="sxs-lookup"><span data-stu-id="cf86f-131">Keyboard and touch</span></span> |    <span data-ttu-id="cf86f-132">Verifica a conexão do teclado integrada e digite a capa</span><span class="sxs-lookup"><span data-stu-id="cf86f-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="cf86f-133">Sensores</span><span class="sxs-lookup"><span data-stu-id="cf86f-133">Sensors</span></span> | <span data-ttu-id="cf86f-134">Verifica o funcionamento de sensores diferentes no dispositivo</span><span class="sxs-lookup"><span data-stu-id="cf86f-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="cf86f-135">Hardware</span><span class="sxs-lookup"><span data-stu-id="cf86f-135">Hardware</span></span> |  <span data-ttu-id="cf86f-136">Verifica problemas com diferentes componentes de hardware, como placa gráfica e câmera</span><span class="sxs-lookup"><span data-stu-id="cf86f-136">Checks issues with different hardware components such as graphics card and camera</span></span>

5. <span data-ttu-id="cf86f-137">Quando todos os testes terminarem, a ferramenta solicitará que você confirme se o problema foi corrigido.</span><span class="sxs-lookup"><span data-stu-id="cf86f-137">When all tests have finished, the tool asks you to confirm if your issue is fixed.</span></span> 

 ![<span data-ttu-id="cf86f-138">Seu problema foi resolvido? ](images/sdt3.png)
 *Figura 3a. o seu problema foi resolvido?*</span><span class="sxs-lookup"><span data-stu-id="cf86f-138">Has your problem been resolved?](images/sdt3.png)
*Figure 3a. Has your problem been resolved?*</span></span>

6. <span data-ttu-id="cf86f-139">Se o problema não for resolvido ou você não souber, poderá enviar um tíquete de suporte selecionando **entre em contato conosco** para **obter ajuda agora.**</span><span class="sxs-lookup"><span data-stu-id="cf86f-139">If the issue isn't resolved or you don't know, you can submit a Support ticket by selecting **Contact us** to **Get help now.**</span></span>
 
 ![<span data-ttu-id="cf86f-140">Envie um tíquete de suporte para o ](images/sdt4.png)
 *número 3B. enviar um tíquete de suporte*</span><span class="sxs-lookup"><span data-stu-id="cf86f-140">Submit a Support ticket](images/sdt4.png)
*Figure 3b. Submit a Support ticket*</span></span>

<span id="multiple" />

## <span data-ttu-id="cf86f-141">Executando vários testes de hardware para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="cf86f-141">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="cf86f-142">O SDT foi projetado como uma ferramenta interativa que executa uma série de testes.</span><span class="sxs-lookup"><span data-stu-id="cf86f-142">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="cf86f-143">Para cada teste, o SDT fornece instruções Resumindo a natureza do teste e o que os usuários devem esperar ou procurar para que o teste seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="cf86f-143">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="cf86f-144">Por exemplo, para diagnosticar se o brilho da exibição estiver funcionando corretamente, o SDT começará em zero e aumentará o brilho para 100%, solicitando que os usuários confirmem: respondendo **Sim** ou **não** --se o brilho está funcionando conforme o esperado, conforme mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="cf86f-144">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="cf86f-145">Para cada teste, se a funcionalidade não funcionar como esperado e o usuário clicar em **não**, o SDT gerará um relatório das possíveis causas e maneiras de solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="cf86f-145">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="cf86f-146">Executando o diagnóstico de hardware ](images/sdt-desk-4.png)
 *Figura 4. Executando o diagnóstico de hardware*</span><span class="sxs-lookup"><span data-stu-id="cf86f-146">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="cf86f-147">Se o brilho se ajusta com êxito de 0-100% conforme o esperado, direcione o usuário para clicar em **Sim** e, em seguida, clique em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="cf86f-147">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="cf86f-148">Se o brilho não for ajustado de 0-100% conforme o esperado, instrua o usuário a clicar em **não** e, em seguida, clicar em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="cf86f-148">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="cf86f-149">Orientar os usuários nos testes remanescentes, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="cf86f-149">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="cf86f-150">Quando concluído, o SDT fornece automaticamente um resumo de alto nível do relatório, incluindo as possíveis causas de problemas de hardware, além de orientação para resolução.</span><span class="sxs-lookup"><span data-stu-id="cf86f-150">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="cf86f-151">Reparar aplicativos</span><span class="sxs-lookup"><span data-stu-id="cf86f-151">Repairing applications</span></span>

<span data-ttu-id="cf86f-152">O SDT permite que você diagnostique e repare aplicativos que possam estar causando problemas, como mostrado na Figura 5.</span><span class="sxs-lookup"><span data-stu-id="cf86f-152">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="cf86f-153">Executando reparos ](images/sdt-desk-5.png)
 *Figura 5. Executando reparos*</span><span class="sxs-lookup"><span data-stu-id="cf86f-153">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="cf86f-154">Gerando logs para analisar problemas</span><span class="sxs-lookup"><span data-stu-id="cf86f-154">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="cf86f-155">O SDT fornece amplo suporte de diagnóstico habilitado para logs entre aplicativos, Drivers, hardware e problemas do sistema operacional, como mostrado na Figura 6.</span><span class="sxs-lookup"><span data-stu-id="cf86f-155">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="cf86f-156">Gerando logs ](images/sdt-desk-6.png)
 *Figura 6. Gerando logs*</span><span class="sxs-lookup"><span data-stu-id="cf86f-156">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="cf86f-157">Gerando relatórios detalhados comparando o dispositivo versus configuração ideal</span><span class="sxs-lookup"><span data-stu-id="cf86f-157">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="cf86f-158">Com base nos logs, o SDT gera um relatório para problemas baseados em software e firmware que você pode salvar em um local preferencial.</span><span class="sxs-lookup"><span data-stu-id="cf86f-158">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="cf86f-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cf86f-159">Related topics</span></span>

- [<span data-ttu-id="cf86f-160">Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos</span><span class="sxs-lookup"><span data-stu-id="cf86f-160">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

