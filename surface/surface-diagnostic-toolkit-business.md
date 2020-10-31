---
title: Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas
description: Este tópico explica como usar o kit de ferramentas de diagnóstico de superfície para empresas.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 97d0a3d76cf9286ca946e08be9f605084084b2ba
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145956"
---
# <span data-ttu-id="3d971-103">Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas</span><span class="sxs-lookup"><span data-stu-id="3d971-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="3d971-104">O Microsoft Surface Diagnostic Toolkit for Business (SDT) permite que os administradores de ti investiguem rapidamente, solucionem problemas e resolvam problemas de hardware, software e firmware com dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="3d971-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="3d971-105">Você pode executar diversos testes de diagnóstico e recorreções de software, além de obter orientação sobre a integridade do dispositivo e orientação para a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="3d971-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="3d971-106">Especificamente, o SDT para empresas permite que você:</span><span class="sxs-lookup"><span data-stu-id="3d971-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="3d971-107">Personalize o pacote.</span><span class="sxs-lookup"><span data-stu-id="3d971-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="3d971-108">Executar o aplicativo usando comandos.</span><span class="sxs-lookup"><span data-stu-id="3d971-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="3d971-109">Execute vários testes de hardware para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="3d971-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="3d971-110">Gere logs para analisar problemas.</span><span class="sxs-lookup"><span data-stu-id="3d971-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="3d971-111">Obter um relatório detalhado para comparar o dispositivo versus a configuração ideal.</span><span class="sxs-lookup"><span data-stu-id="3d971-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="3d971-112">Principais cenários e recursos de download</span><span class="sxs-lookup"><span data-stu-id="3d971-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="3d971-113">Para executar o SDT para empresas, baixe os componentes listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d971-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="3d971-114">Modo</span><span class="sxs-lookup"><span data-stu-id="3d971-114">Mode</span></span> |  <span data-ttu-id="3d971-115">Cenários principais</span><span class="sxs-lookup"><span data-stu-id="3d971-115">Primary scenarios</span></span> | <span data-ttu-id="3d971-116">Baixar</span><span class="sxs-lookup"><span data-stu-id="3d971-116">Download</span></span> | <span data-ttu-id="3d971-117">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="3d971-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="3d971-118">Modo desktop</span><span class="sxs-lookup"><span data-stu-id="3d971-118">Desktop mode</span></span> |  <span data-ttu-id="3d971-119">Ajude os usuários a executar o SDT em seus dispositivos de superfície para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="3d971-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="3d971-120">Crie um pacote personalizado para implantar em um ou mais dispositivos Surface, permitindo que os usuários selecionem logs específicos para coletar e analisar.</span><span class="sxs-lookup"><span data-stu-id="3d971-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="3d971-121">Pacote MSI distribuído do SDT:</span><span class="sxs-lookup"><span data-stu-id="3d971-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="3d971-122">Instalador do kit de ferramentas de diagnóstico de superfície Microsoft para empresas</span><span class="sxs-lookup"><span data-stu-id="3d971-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="3d971-123">Ferramentas Surface para TI</span><span class="sxs-lookup"><span data-stu-id="3d971-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="3d971-124">Usar o kit de ferramentas de diagnóstico Surface no modo de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="3d971-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="3d971-125">Linha de comando</span><span class="sxs-lookup"><span data-stu-id="3d971-125">Command line</span></span> |  <span data-ttu-id="3d971-126">Solucionar problemas diretamente de dispositivos Surface remotamente sem interação do usuário, usando ferramentas padrão, como o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="3d971-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="3d971-127">Ele inclui os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="3d971-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="3d971-128">coleta todos os arquivos de log</span><span class="sxs-lookup"><span data-stu-id="3d971-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="3d971-129">executa o diagnóstico de integridade usando o analisador de práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="3d971-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="3d971-130">verifica se há atualizações de firmware ou drivers ausentes no Windows Update.</span><span class="sxs-lookup"><span data-stu-id="3d971-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="3d971-131">verifica as informações de garantia.</span><span class="sxs-lookup"><span data-stu-id="3d971-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="3d971-132">Aplicativo de console do SDT:</span><span class="sxs-lookup"><span data-stu-id="3d971-132">SDT console app:</span></span><br><span data-ttu-id="3d971-133">Console do aplicativo Microsoft Surface Diagnostics</span><span class="sxs-lookup"><span data-stu-id="3d971-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="3d971-134">Ferramentas Surface para TI</span><span class="sxs-lookup"><span data-stu-id="3d971-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="3d971-135">Executar o kit de ferramentas de diagnóstico de Surface usando comandos</span><span class="sxs-lookup"><span data-stu-id="3d971-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="3d971-136">Dispositivos com suporte</span><span class="sxs-lookup"><span data-stu-id="3d971-136">Supported devices</span></span> 

<span data-ttu-id="3d971-137">O SDT para empresas tem suporte em dispositivos Surface 3 e posteriores, incluindo:</span><span class="sxs-lookup"><span data-stu-id="3d971-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="3d971-138">Usar o laptop Surface</span><span class="sxs-lookup"><span data-stu-id="3d971-138">Surface Laptop Go</span></span>
- <span data-ttu-id="3d971-139">Catálogo de superfície 3</span><span class="sxs-lookup"><span data-stu-id="3d971-139">Surface Book 3</span></span>
- <span data-ttu-id="3d971-140">Ir para a superfície 2</span><span class="sxs-lookup"><span data-stu-id="3d971-140">Surface Go 2</span></span>
- <span data-ttu-id="3d971-141">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="3d971-141">Surface Pro X</span></span>
- <span data-ttu-id="3d971-142">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="3d971-142">Surface Pro 7</span></span>
- <span data-ttu-id="3d971-143">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="3d971-143">Surface Laptop 3</span></span>
- <span data-ttu-id="3d971-144">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="3d971-144">Surface Pro 6</span></span>
- <span data-ttu-id="3d971-145">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="3d971-145">Surface Laptop 2</span></span>
- <span data-ttu-id="3d971-146">Surface Go</span><span class="sxs-lookup"><span data-stu-id="3d971-146">Surface Go</span></span>
- <span data-ttu-id="3d971-147">Surface Go com LTE</span><span class="sxs-lookup"><span data-stu-id="3d971-147">Surface Go with LTE</span></span>
- <span data-ttu-id="3d971-148">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="3d971-148">Surface Book 2</span></span>
- <span data-ttu-id="3d971-149">Surface Pro com LTE Avançado (Model 1807)</span><span class="sxs-lookup"><span data-stu-id="3d971-149">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="3d971-150">Surface Pro (Model 1796)</span><span class="sxs-lookup"><span data-stu-id="3d971-150">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="3d971-151">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="3d971-151">Surface Laptop</span></span>
- <span data-ttu-id="3d971-152">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="3d971-152">Surface Studio</span></span>
- <span data-ttu-id="3d971-153">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="3d971-153">Surface Studio 2</span></span>
- <span data-ttu-id="3d971-154">Surface Book</span><span class="sxs-lookup"><span data-stu-id="3d971-154">Surface Book</span></span>
- <span data-ttu-id="3d971-155">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="3d971-155">Surface Pro 4</span></span>
- <span data-ttu-id="3d971-156">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="3d971-156">Surface 3 LTE</span></span>
- <span data-ttu-id="3d971-157">Surface 3</span><span class="sxs-lookup"><span data-stu-id="3d971-157">Surface 3</span></span>
- <span data-ttu-id="3d971-158">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="3d971-158">Surface Pro 3</span></span>

## <span data-ttu-id="3d971-159">Instalando o kit de ferramentas de diagnóstico de superfície para empresas</span><span class="sxs-lookup"><span data-stu-id="3d971-159">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="3d971-160">Para criar um pacote do SDT que você pode distribuir para os usuários em sua organização:</span><span class="sxs-lookup"><span data-stu-id="3d971-160">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="3d971-161">Conecte-se ao seu dispositivo Surface usando a conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="3d971-161">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="3d971-162">Baixe o pacote do SDT do Windows Installer (. msi) da [página de ferramentas do Surface para download](https://www.microsoft.com/download/details.aspx?id=46703) e copie-o para um local preferido no seu dispositivo Surface, como área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3d971-162">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="3d971-163">O assistente de configuração do SDT é exibido, como mostra a Figura 1.</span><span class="sxs-lookup"><span data-stu-id="3d971-163">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="3d971-164">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3d971-164">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="3d971-165">Se o assistente de configuração não for exibido, verifique se você está conectado à conta de administrador em seu computador.</span><span class="sxs-lookup"><span data-stu-id="3d971-165">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Bem-vindo ao assistente de configuração do kit de ferramentas de diagnóstico de superfície](images/sdt-1.png)

    *<span data-ttu-id="3d971-167">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="3d971-167">Figure 1.</span></span> <span data-ttu-id="3d971-168">Assistente de configuração do kit de ferramentas de diagnóstico de superfície</span><span class="sxs-lookup"><span data-stu-id="3d971-168">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="3d971-169">Quando o assistente de configuração do SDT for exibido, clique em **Avançar**e aceite o contrato de licença de usuário final (EULA)</span><span class="sxs-lookup"><span data-stu-id="3d971-169">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="3d971-170">Na tela opções de instalação, altere o local de instalação padrão, se desejar.</span><span class="sxs-lookup"><span data-stu-id="3d971-170">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="3d971-171">Em tipo de instalação, selecione **avançado**.</span><span class="sxs-lookup"><span data-stu-id="3d971-171">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="3d971-172">A opção padrão permite que os usuários executem a ferramenta de diagnóstico diretamente em seu dispositivo Surface desde que estejam conectadas ao dispositivo usando uma conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="3d971-172">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Opções de instalação: avançado](images/sdt-install.png)

7. <span data-ttu-id="3d971-174">Clique em **Avançar** e, em seguida, clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="3d971-174">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="3d971-175">Instalando usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="3d971-175">Installing using the command line</span></span>
<span data-ttu-id="3d971-176">Se desejar, você pode instalar o SDT em um prompt de comando e definir um sinalizador personalizado para instalar a ferramenta no modo de administração.</span><span class="sxs-lookup"><span data-stu-id="3d971-176">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="3d971-177">O SDT contém os seguintes sinalizadores de opções de instalação:</span><span class="sxs-lookup"><span data-stu-id="3d971-177">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="3d971-178">envia dados de telemetria para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d971-178">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="3d971-179">O sinalizador aceita `0` para Disabled ou `1` for Enabled.</span><span class="sxs-lookup"><span data-stu-id="3d971-179">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="3d971-180">O valor padrão é `1` Enviar telemetria.</span><span class="sxs-lookup"><span data-stu-id="3d971-180">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="3d971-181">configura a ferramenta para ser instalada no modo de administração.</span><span class="sxs-lookup"><span data-stu-id="3d971-181">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="3d971-182">O sinalizador aceita o `0` modo de cliente ou `1` para o modo de administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="3d971-182">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="3d971-183">O valor padrão é `0`.</span><span class="sxs-lookup"><span data-stu-id="3d971-183">The default value is `0`.</span></span>

### <span data-ttu-id="3d971-184">Para instalar o SDT na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="3d971-184">To install SDT from the command line:</span></span>

1. <span data-ttu-id="3d971-185">Abra um prompt de comando e digite:</span><span class="sxs-lookup"><span data-stu-id="3d971-185">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="3d971-186">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="3d971-186">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="3d971-187">Localizando o SDT em seu dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="3d971-187">Locating SDT on your Surface device</span></span>

<span data-ttu-id="3d971-188">O SDT e o console do aplicativo SDT são instalados em `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="3d971-188">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="3d971-189">Além do arquivo. exe, o SDT instala um arquivo JSON e um arquivo admin.dll (modules\admin.dll), como mostrado na Figura 2.</span><span class="sxs-lookup"><span data-stu-id="3d971-189">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![lista de arquivos instalados do SDT no explorador de arquivos](images/sdt-2.png)

*<span data-ttu-id="3d971-191">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="3d971-191">Figure 2.</span></span> <span data-ttu-id="3d971-192">Arquivos instalados pelo SDT</span><span class="sxs-lookup"><span data-stu-id="3d971-192">Files installed by SDT</span></span>*

## <span data-ttu-id="3d971-193">Preparando o pacote SDT para distribuição</span><span class="sxs-lookup"><span data-stu-id="3d971-193">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="3d971-194">A criação de um pacote personalizado permite direcionar a ferramenta para problemas específicos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="3d971-194">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="3d971-195">Clique em **iniciar > executar**, digite **Surface** e clique em **Kit de ferramentas de diagnóstico de Surface for Business**.</span><span class="sxs-lookup"><span data-stu-id="3d971-195">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="3d971-196">Quando a ferramenta abrir, clique em **criar pacote personalizado**, conforme mostrado na Figura 3.</span><span class="sxs-lookup"><span data-stu-id="3d971-196">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Criar opção de pacote personalizado](images/sdt-3.png)

    *<span data-ttu-id="3d971-198">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="3d971-198">Figure 3.</span></span> <span data-ttu-id="3d971-199">Criar pacote personalizado</span><span class="sxs-lookup"><span data-stu-id="3d971-199">Create custom package</span></span>*

### <span data-ttu-id="3d971-200">Configurações de idioma e telemetria</span><span class="sxs-lookup"><span data-stu-id="3d971-200">Language and telemetry settings</span></span>

  <span data-ttu-id="3d971-201">Ao criar um pacote, você pode selecionar as configurações de idioma ou optar por não enviar informações de telemetria à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d971-201">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="3d971-202">Por padrão, o SDT envia telemetria à Microsoft que é usada para melhorar o aplicativo de acordo com a [política de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="3d971-202">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="3d971-203">Se quiser recusar, desmarque a caixa de seleção ao criar um pacote personalizado, como mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="3d971-203">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="3d971-204">Ou desmarque a caixa de seleção **Enviar telemetria para a Microsoft** na página **Opções de instalação** durante a configuração do SDT.</span><span class="sxs-lookup"><span data-stu-id="3d971-204">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="3d971-205">Essa configuração não afeta a telemetria mínima armazenada automaticamente em servidores Microsoft durante a execução de testes e reparos que exigem uma conexão à Internet, como o Windows Update e o reparo de software, ou o fornecimento de comentários usando os botões sorrir ou rosto triste na barra de ferramentas do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d971-205">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Selecionar configurações de idioma e telemetria](images/sdt-4.png)

*<span data-ttu-id="3d971-207">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="3d971-207">Figure 4.</span></span> <span data-ttu-id="3d971-208">Selecionar configurações de idioma e telemetria</span><span class="sxs-lookup"><span data-stu-id="3d971-208">Select language and telemetry settings</span></span>*


### <span data-ttu-id="3d971-209">Página do Windows Update</span><span class="sxs-lookup"><span data-stu-id="3d971-209">Windows Update page</span></span>

<span data-ttu-id="3d971-210">Selecione a opção apropriada para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d971-210">Select the option appropriate for your organization.</span></span> <span data-ttu-id="3d971-211">A maioria das organizações com vários usuários geralmente selecionam receber atualizações por meio do WSUS (Windows Server Update Services), conforme mostrado na Figura 5.</span><span class="sxs-lookup"><span data-stu-id="3d971-211">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="3d971-212">Se estiver usando pacotes locais do Windows Update ou WSUS, digite o caminho conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="3d971-212">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Selecione a opção de atualização do Windows](images/sdt-5.png)

*<span data-ttu-id="3d971-214">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="3d971-214">Figure 5.</span></span> <span data-ttu-id="3d971-215">Opção de atualização do Windows</span><span class="sxs-lookup"><span data-stu-id="3d971-215">Windows Update option</span></span>*

### <span data-ttu-id="3d971-216">Página de reparo de software</span><span class="sxs-lookup"><span data-stu-id="3d971-216">Software repair page</span></span>

<span data-ttu-id="3d971-217">Isso permite que você selecione ou remova a opção para executar atualizações de reparo de software.</span><span class="sxs-lookup"><span data-stu-id="3d971-217">This allows you to select or remove the option to run software repair updates.</span></span> 

![Selecione a opção de reparo de software](images/sdt-6.png)

*<span data-ttu-id="3d971-219">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="3d971-219">Figure 6.</span></span> <span data-ttu-id="3d971-220">Opção de reparo de software</span><span class="sxs-lookup"><span data-stu-id="3d971-220">Software repair option</span></span>*

### <span data-ttu-id="3d971-221">Página coletando logs e salvando pacote</span><span class="sxs-lookup"><span data-stu-id="3d971-221">Collecting logs and saving package page</span></span>

<span data-ttu-id="3d971-222">Você pode optar por executar uma ampla variedade de logs entre aplicativos, Drivers, hardware e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="3d971-222">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="3d971-223">Clique na área apropriada e selecione no menu de logs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3d971-223">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="3d971-224">Em seguida, você pode salvar o pacote em um ponto de distribuição de software ou em um local equivalente que os usuários possam acessar.</span><span class="sxs-lookup"><span data-stu-id="3d971-224">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Selecionar opções de log](images/sdt-7.png)

*<span data-ttu-id="3d971-226">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="3d971-226">Figure 7.</span></span> <span data-ttu-id="3d971-227">Opção de log e salvar pacote</span><span class="sxs-lookup"><span data-stu-id="3d971-227">Log option and save package</span></span>*

## <span data-ttu-id="3d971-228">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3d971-228">Next steps</span></span>

- [<span data-ttu-id="3d971-229">Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="3d971-229">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="3d971-230">Usar o kit de ferramentas de diagnóstico de superfície para empresas usando comandos</span><span class="sxs-lookup"><span data-stu-id="3d971-230">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="3d971-231">Alterações e atualizações</span><span class="sxs-lookup"><span data-stu-id="3d971-231">Changes and updates</span></span>

### <span data-ttu-id="3d971-232">Versão 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="3d971-232">Version 2.124.139.0</span></span>

<span data-ttu-id="3d971-233">Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d971-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="3d971-234">Suporte integrado ininterrupto</span><span class="sxs-lookup"><span data-stu-id="3d971-234">Seamless integrated support</span></span>
- <span data-ttu-id="3d971-235">Salvar todos os resultados do teste</span><span class="sxs-lookup"><span data-stu-id="3d971-235">Save all test results</span></span>
- <span data-ttu-id="3d971-236">Verificar se a imagem é personalizada criada</span><span class="sxs-lookup"><span data-stu-id="3d971-236">Check if the image is custom created</span></span>
- <span data-ttu-id="3d971-237">Incluir avisos do Gerenciador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="3d971-237">Include warnings from device manager</span></span>
- <span data-ttu-id="3d971-238">Encaixar versão do firmware</span><span class="sxs-lookup"><span data-stu-id="3d971-238">Dock firmware version</span></span>
- <span data-ttu-id="3d971-239">Sinalizar unidades como possíveis falhas no teste de armazenamento</span><span class="sxs-lookup"><span data-stu-id="3d971-239">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="3d971-240">Remover link da loja</span><span class="sxs-lookup"><span data-stu-id="3d971-240">Remove store link</span></span> 

### <span data-ttu-id="3d971-241">Versão 2.121.139</span><span class="sxs-lookup"><span data-stu-id="3d971-241">Version 2.121.139</span></span>
*<span data-ttu-id="3d971-242">Data do lançamento: 31 2020 de julho</span><span class="sxs-lookup"><span data-stu-id="3d971-242">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="3d971-243">Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d971-243">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="3d971-244">Experiência de suporte contínua</span><span class="sxs-lookup"><span data-stu-id="3d971-244">Seamless support experience</span></span>
- <span data-ttu-id="3d971-245">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="3d971-245">Bug fixes</span></span>

### <span data-ttu-id="3d971-246">Versão 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="3d971-246">Version 2.94.139.0</span></span>
*<span data-ttu-id="3d971-247">Data do lançamento: 11 de maio de 2020</span><span class="sxs-lookup"><span data-stu-id="3d971-247">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="3d971-248">Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d971-248">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="3d971-249">Capacidade de ignorar o Windows Update para executar a verificação de hardware.</span><span class="sxs-lookup"><span data-stu-id="3d971-249">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="3d971-250">Capacidade de receber notificações sobre a atualização da versão mais recente</span><span class="sxs-lookup"><span data-stu-id="3d971-250">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="3d971-251">Ir para a superfície 2</span><span class="sxs-lookup"><span data-stu-id="3d971-251">Surface Go 2</span></span>
- <span data-ttu-id="3d971-252">Catálogo de superfície 3</span><span class="sxs-lookup"><span data-stu-id="3d971-252">Surface Book 3</span></span>
- <span data-ttu-id="3d971-253">Mostrar indicador de progresso</span><span class="sxs-lookup"><span data-stu-id="3d971-253">Show progress indicator</span></span>


### <span data-ttu-id="3d971-254">Versão 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="3d971-254">Version 2.43.139.0</span></span>
*<span data-ttu-id="3d971-255">Data do lançamento: 21 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="3d971-255">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="3d971-256">Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d971-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="3d971-257">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="3d971-257">Surface Pro 7</span></span>
- <span data-ttu-id="3d971-258">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="3d971-258">Surface Laptop 3</span></span>

### <span data-ttu-id="3d971-259">Versão 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="3d971-259">Version 2.42.139.0</span></span>
*<span data-ttu-id="3d971-260">Data do lançamento: 24 de setembro de 2019</span><span class="sxs-lookup"><span data-stu-id="3d971-260">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="3d971-261">Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d971-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="3d971-262">Capacidade de baixar relatórios de hardware.</span><span class="sxs-lookup"><span data-stu-id="3d971-262">Ability to download hardware reports.</span></span>
- <span data-ttu-id="3d971-263">Capacidade de entrar em contato com o suporte da Microsoft diretamente da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="3d971-263">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="3d971-264">Versão 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="3d971-264">Version 2.41.139.0</span></span>
*<span data-ttu-id="3d971-265">Data do lançamento: 24 de junho de 2019</span><span class="sxs-lookup"><span data-stu-id="3d971-265">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="3d971-266">Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d971-266">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="3d971-267">Informações sobre a versão do driver incluídas em logs e relatórios.</span><span class="sxs-lookup"><span data-stu-id="3d971-267">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="3d971-268">Capacidade de fornecer comentários sobre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d971-268">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="3d971-269">Versão 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="3d971-269">Version 2.36.139.0</span></span>
*<span data-ttu-id="3d971-270">Data do lançamento: 26 de abril de 2019</span><span class="sxs-lookup"><span data-stu-id="3d971-270">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="3d971-271">Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d971-271">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="3d971-272">Opção configuração avançada para desbloquear os recursos de administração por meio da interface do usuário do instalador, sem exigir configuração de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3d971-272">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="3d971-273">Melhorias de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d971-273">Accessibility improvements.</span></span>
- <span data-ttu-id="3d971-274">Configurações de controle de brilho da superfície incluídas nos logs.</span><span class="sxs-lookup"><span data-stu-id="3d971-274">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="3d971-275">Link de suporte de compatibilidade do monitor externo no gerador de relatórios.</span><span class="sxs-lookup"><span data-stu-id="3d971-275">External monitor compatibility support link in report generator.</span></span>
