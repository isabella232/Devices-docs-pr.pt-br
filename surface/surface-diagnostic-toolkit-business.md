---
title: Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas
description: Este tópico explica como usar o Surface Diagnostic Toolkit for Business.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271575"
---
# <span data-ttu-id="5aa64-103">Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas</span><span class="sxs-lookup"><span data-stu-id="5aa64-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="5aa64-104">O Microsoft Surface Diagnostic Toolkit for Business (SDT) permite que os administradores de IT investiguem, solucionem rapidamente problemas de hardware, software e firmware com dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="5aa64-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="5aa64-105">Você pode executar vários testes de diagnóstico e reparos de software, além de obter informações e diretrizes de saúde do dispositivo para resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="5aa64-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="5aa64-106">Especificamente, o SDT para Empresas permite que você:</span><span class="sxs-lookup"><span data-stu-id="5aa64-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="5aa64-107">Personalize o pacote.</span><span class="sxs-lookup"><span data-stu-id="5aa64-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="5aa64-108">Execute o aplicativo usando comandos.</span><span class="sxs-lookup"><span data-stu-id="5aa64-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="5aa64-109">Execute vários testes de hardware para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="5aa64-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="5aa64-110">Gere logs para analisar problemas.</span><span class="sxs-lookup"><span data-stu-id="5aa64-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="5aa64-111">Obtenha um relatório detalhado comparando o dispositivo com a configuração ideal.</span><span class="sxs-lookup"><span data-stu-id="5aa64-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <a name="primary-scenarios-and-download-resources"></a><span data-ttu-id="5aa64-112">Cenários principais e recursos de download</span><span class="sxs-lookup"><span data-stu-id="5aa64-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="5aa64-113">Para executar o SDT para Empresas, baixe os componentes listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5aa64-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="5aa64-114">Modo</span><span class="sxs-lookup"><span data-stu-id="5aa64-114">Mode</span></span> |  <span data-ttu-id="5aa64-115">Cenários principais</span><span class="sxs-lookup"><span data-stu-id="5aa64-115">Primary scenarios</span></span> | <span data-ttu-id="5aa64-116">Baixar</span><span class="sxs-lookup"><span data-stu-id="5aa64-116">Download</span></span> | <span data-ttu-id="5aa64-117">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="5aa64-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="5aa64-118">Modo desktop</span><span class="sxs-lookup"><span data-stu-id="5aa64-118">Desktop mode</span></span> |  <span data-ttu-id="5aa64-119">Ajude os usuários a executar o SDT em seus dispositivos Surface para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="5aa64-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="5aa64-120">Crie um pacote personalizado para implantar em um ou mais dispositivos Surface, permitindo que os usuários selecionem logs específicos para coletar e analisar.</span><span class="sxs-lookup"><span data-stu-id="5aa64-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="5aa64-121">Pacote MSI distribuível do SDT:</span><span class="sxs-lookup"><span data-stu-id="5aa64-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="5aa64-122">Instalador do Microsoft Surface Diagnostic Toolkit for Business</span><span class="sxs-lookup"><span data-stu-id="5aa64-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="5aa64-123">Ferramentas Surface para TI</span><span class="sxs-lookup"><span data-stu-id="5aa64-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="5aa64-124">Usar o Surface Diagnostic Toolkit no modo desktop</span><span class="sxs-lookup"><span data-stu-id="5aa64-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="5aa64-125">Linha de comando</span><span class="sxs-lookup"><span data-stu-id="5aa64-125">Command line</span></span> |  <span data-ttu-id="5aa64-126">Solucionar problemas diretamente de dispositivos Surface remotamente sem a interação do usuário, usando ferramentas padrão, como o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="5aa64-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="5aa64-127">Ele inclui os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="5aa64-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="5aa64-128">coleta todos os arquivos de log</span><span class="sxs-lookup"><span data-stu-id="5aa64-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="5aa64-129">executa diagnósticos de saúde usando o Analisador de Práticas Práticas Melhores.</span><span class="sxs-lookup"><span data-stu-id="5aa64-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="5aa64-130">verifica se há atualizações de firmware ou driver ausentes no Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5aa64-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="5aa64-131">verifica as informações de garantia.</span><span class="sxs-lookup"><span data-stu-id="5aa64-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="5aa64-132">Aplicativo de console SDT:</span><span class="sxs-lookup"><span data-stu-id="5aa64-132">SDT console app:</span></span><br><span data-ttu-id="5aa64-133">Console do Aplicativo de Diagnóstico do Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="5aa64-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="5aa64-134">Ferramentas Surface para TI</span><span class="sxs-lookup"><span data-stu-id="5aa64-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="5aa64-135">Executar o Surface Diagnostic Toolkit usando comandos</span><span class="sxs-lookup"><span data-stu-id="5aa64-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <a name="supported-devices-"></a><span data-ttu-id="5aa64-136">Dispositivos com suporte</span><span class="sxs-lookup"><span data-stu-id="5aa64-136">Supported devices</span></span> 

<span data-ttu-id="5aa64-137">O SDT para Empresas tem suporte no Surface 3 e em dispositivos posteriores, incluindo:</span><span class="sxs-lookup"><span data-stu-id="5aa64-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="5aa64-138">Surface Book – todas as gerações</span><span class="sxs-lookup"><span data-stu-id="5aa64-138">Surface Book - all generations</span></span>
- <span data-ttu-id="5aa64-139">Surface Go – todas as gerações</span><span class="sxs-lookup"><span data-stu-id="5aa64-139">Surface Go - all generations</span></span>
- <span data-ttu-id="5aa64-140">Surface Laptop – todas as gerações</span><span class="sxs-lookup"><span data-stu-id="5aa64-140">Surface Laptop - all generations</span></span>
- <span data-ttu-id="5aa64-141">Surface Pro 3 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa64-141">Surface Pro 3 and later</span></span>
- <span data-ttu-id="5aa64-142">Surface Pro X - todas as gerações</span><span class="sxs-lookup"><span data-stu-id="5aa64-142">Surface Pro X - all generations</span></span>
- <span data-ttu-id="5aa64-143">Surface Studio – todas as gerações</span><span class="sxs-lookup"><span data-stu-id="5aa64-143">Surface Studio - all generations</span></span>
- <span data-ttu-id="5aa64-144">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="5aa64-144">Surface 3 LTE</span></span>
- <span data-ttu-id="5aa64-145">Surface 3</span><span class="sxs-lookup"><span data-stu-id="5aa64-145">Surface 3</span></span>


## <a name="installing-surface-diagnostic-toolkit-for-business"></a><span data-ttu-id="5aa64-146">Instalando o Surface Diagnostic Toolkit for Business</span><span class="sxs-lookup"><span data-stu-id="5aa64-146">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="5aa64-147">Para criar um pacote SDT que você pode distribuir aos usuários em sua organização:</span><span class="sxs-lookup"><span data-stu-id="5aa64-147">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="5aa64-148">Entre no dispositivo Surface usando a conta de Administrador.</span><span class="sxs-lookup"><span data-stu-id="5aa64-148">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="5aa64-149">Baixe o pacote do Windows Installer (.msi) do SDT na página de download do [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) e copie-o para um local preferencial no dispositivo Surface, como a área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5aa64-149">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="5aa64-150">O assistente de instalação do SDT é exibido, conforme mostrado na figura 1.</span><span class="sxs-lookup"><span data-stu-id="5aa64-150">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="5aa64-151">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5aa64-151">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="5aa64-152">Se o assistente de configuração não aparecer, verifique se você está entrando na conta de Administrador no computador.</span><span class="sxs-lookup"><span data-stu-id="5aa64-152">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![bem-vindo ao assistente de configuração do Surface Diagnostic Toolkit](images/sdt-1.png)

    *<span data-ttu-id="5aa64-154">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="5aa64-154">Figure 1.</span></span> <span data-ttu-id="5aa64-155">Assistente de configuração do Surface Diagnostic Toolkit</span><span class="sxs-lookup"><span data-stu-id="5aa64-155">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="5aa64-156">Quando o assistente de instalação do SDT for exibido, clique em **Próximo**, aceite o EULA (Contrato de Licença de Usuário Final)</span><span class="sxs-lookup"><span data-stu-id="5aa64-156">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="5aa64-157">Na tela Opções de Instalação, altere o local de instalação padrão, se desejado.</span><span class="sxs-lookup"><span data-stu-id="5aa64-157">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="5aa64-158">Em Tipo de Instalação, selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="5aa64-158">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="5aa64-159">A opção padrão permite que os usuários executem a ferramenta de diagnóstico diretamente no dispositivo Surface, desde que eles sejam conectados ao dispositivo usando uma conta de Administrador.</span><span class="sxs-lookup"><span data-stu-id="5aa64-159">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Opções de instalação: Avançado](images/sdt-install.png)

7. <span data-ttu-id="5aa64-161">Clique **em Próximo** e, em seguida, clique em **Instalar.**</span><span class="sxs-lookup"><span data-stu-id="5aa64-161">Click **Next** and then click **Install**.</span></span> 

## <a name="installing-using-the-command-line"></a><span data-ttu-id="5aa64-162">Instalando usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="5aa64-162">Installing using the command line</span></span>
<span data-ttu-id="5aa64-163">Se desejado, você pode instalar o SDT em um prompt de comando e definir um sinalizador personalizado para instalar a ferramenta no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="5aa64-163">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="5aa64-164">O SDT contém os seguintes sinalizadores de opção de instalação:</span><span class="sxs-lookup"><span data-stu-id="5aa64-164">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="5aa64-165">envia dados de telemetria para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5aa64-165">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="5aa64-166">O sinalizador aceita `0` para desabilitado `1` ou habilitado.</span><span class="sxs-lookup"><span data-stu-id="5aa64-166">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="5aa64-167">O valor padrão é `1` enviar telemetria.</span><span class="sxs-lookup"><span data-stu-id="5aa64-167">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="5aa64-168">configura a ferramenta a ser instalada no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="5aa64-168">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="5aa64-169">O sinalizador aceita para o `0` modo cliente ou para o modo administrador de `1` IT.</span><span class="sxs-lookup"><span data-stu-id="5aa64-169">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="5aa64-170">O valor padrão é `0`.</span><span class="sxs-lookup"><span data-stu-id="5aa64-170">The default value is `0`.</span></span>

### <a name="to-install-sdt-from-the-command-line"></a><span data-ttu-id="5aa64-171">Para instalar o SDT a partir da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="5aa64-171">To install SDT from the command line:</span></span>

1. <span data-ttu-id="5aa64-172">Abra um prompt de comando e insira:</span><span class="sxs-lookup"><span data-stu-id="5aa64-172">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="5aa64-173">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="5aa64-173">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <a name="locating-sdt-on-your-surface-device"></a><span data-ttu-id="5aa64-174">Localizar o SDT em seu dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="5aa64-174">Locating SDT on your Surface device</span></span>

<span data-ttu-id="5aa64-175">O SDT e o console do aplicativo SDT estão instalados em `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="5aa64-175">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="5aa64-176">Além do arquivo .exe, o SDT instala um arquivo JSON e um arquivo admin.dll (modules\admin.dll), conforme mostrado na figura 2.</span><span class="sxs-lookup"><span data-stu-id="5aa64-176">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![lista de arquivos instalados do SDT no Explorador de Arquivos](images/sdt-2.png)

*<span data-ttu-id="5aa64-178">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="5aa64-178">Figure 2.</span></span> <span data-ttu-id="5aa64-179">Arquivos instalados pelo SDT</span><span class="sxs-lookup"><span data-stu-id="5aa64-179">Files installed by SDT</span></span>*

## <a name="preparing-the-sdt-package-for-distribution"></a><span data-ttu-id="5aa64-180">Preparando o pacote SDT para distribuição</span><span class="sxs-lookup"><span data-stu-id="5aa64-180">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="5aa64-181">Criar um pacote personalizado permite direcionar a ferramenta a problemas conhecidos específicos.</span><span class="sxs-lookup"><span data-stu-id="5aa64-181">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="5aa64-182">Clique **em Iniciar > Executar,** insira o **Surface** e clique em Surface **Diagnostic Toolkit for Business.**</span><span class="sxs-lookup"><span data-stu-id="5aa64-182">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="5aa64-183">Quando a ferramenta for aberta, **clique em Criar Pacote Personalizado,** conforme mostrado na figura 3.</span><span class="sxs-lookup"><span data-stu-id="5aa64-183">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Criar uma opção de pacote personalizado](images/sdt-3.png)

    *<span data-ttu-id="5aa64-185">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="5aa64-185">Figure 3.</span></span> <span data-ttu-id="5aa64-186">Criar um pacote personalizado</span><span class="sxs-lookup"><span data-stu-id="5aa64-186">Create custom package</span></span>*

### <a name="language-and-telemetry-settings"></a><span data-ttu-id="5aa64-187">Configurações de idioma e telemetria</span><span class="sxs-lookup"><span data-stu-id="5aa64-187">Language and telemetry settings</span></span>

  <span data-ttu-id="5aa64-188">Ao criar um pacote, você pode selecionar configurações de idioma ou optar por não enviar informações de telemetria para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5aa64-188">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="5aa64-189">Por padrão, o SDT envia telemetria para a Microsoft que é usada para melhorar o aplicativo de acordo com a Política [de Privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement)</span><span class="sxs-lookup"><span data-stu-id="5aa64-189">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="5aa64-190">Se você quiser recusar, des marque a caixa de seleção ao criar um pacote personalizado, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="5aa64-190">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="5aa64-191">Ou des clear the **Send telemetry to Microsoft** check box on the Install **Options** page during SDT Setup.</span><span class="sxs-lookup"><span data-stu-id="5aa64-191">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="5aa64-192">Essa configuração não afeta a telemetria mínima armazenada automaticamente nos servidores da Microsoft durante a execução de testes e reparos que exigem uma conexão com a Internet, como o Windows Update e o reparo de software, ou o fornecimento de comentários usando os botões Feliz ou Rosto Feliz na barra de ferramentas do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5aa64-192">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Selecionar configurações de idioma e telemetria](images/sdt-4.png)

*<span data-ttu-id="5aa64-194">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="5aa64-194">Figure 4.</span></span> <span data-ttu-id="5aa64-195">Selecionar configurações de idioma e telemetria</span><span class="sxs-lookup"><span data-stu-id="5aa64-195">Select language and telemetry settings</span></span>*


### <a name="windows-update-page"></a><span data-ttu-id="5aa64-196">Página do Windows Update</span><span class="sxs-lookup"><span data-stu-id="5aa64-196">Windows Update page</span></span>

<span data-ttu-id="5aa64-197">Selecione a opção apropriada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5aa64-197">Select the option appropriate for your organization.</span></span> <span data-ttu-id="5aa64-198">A maioria das organizações com vários usuários normalmente selecionará receber atualizações por meio do Windows Server Update Services (WSUS), conforme mostrado na figura 5.</span><span class="sxs-lookup"><span data-stu-id="5aa64-198">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="5aa64-199">Se estiver usando pacotes locais do Windows Update ou WSUS, insira o caminho conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="5aa64-199">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Selecionar a opção Windows Update](images/sdt-5.png)

*<span data-ttu-id="5aa64-201">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="5aa64-201">Figure 5.</span></span> <span data-ttu-id="5aa64-202">Opção Windows Update</span><span class="sxs-lookup"><span data-stu-id="5aa64-202">Windows Update option</span></span>*

### <a name="software-repair-page"></a><span data-ttu-id="5aa64-203">Página de reparo de software</span><span class="sxs-lookup"><span data-stu-id="5aa64-203">Software repair page</span></span>

<span data-ttu-id="5aa64-204">Isso permite que você selecione ou remova a opção de executar atualizações de reparo de software.</span><span class="sxs-lookup"><span data-stu-id="5aa64-204">This allows you to select or remove the option to run software repair updates.</span></span> 

![Selecionar a opção de reparo de software](images/sdt-6.png)

*<span data-ttu-id="5aa64-206">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="5aa64-206">Figure 6.</span></span> <span data-ttu-id="5aa64-207">Opção de reparo de software</span><span class="sxs-lookup"><span data-stu-id="5aa64-207">Software repair option</span></span>*

### <a name="collecting-logs-and-saving-package-page"></a><span data-ttu-id="5aa64-208">Coletando logs e salvando a página do pacote</span><span class="sxs-lookup"><span data-stu-id="5aa64-208">Collecting logs and saving package page</span></span>

<span data-ttu-id="5aa64-209">Você pode optar por executar uma ampla variedade de logs entre aplicativos, drivers, hardware e o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="5aa64-209">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="5aa64-210">Clique na área apropriada e selecione no menu de logs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5aa64-210">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="5aa64-211">Em seguida, você pode salvar o pacote em um ponto de distribuição de software ou um local equivalente que os usuários possam acessar.</span><span class="sxs-lookup"><span data-stu-id="5aa64-211">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Selecionar opções de log](images/sdt-7.png)

*<span data-ttu-id="5aa64-213">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="5aa64-213">Figure 7.</span></span> <span data-ttu-id="5aa64-214">Opção de log e salvar pacote</span><span class="sxs-lookup"><span data-stu-id="5aa64-214">Log option and save package</span></span>*

## <a name="next-steps"></a><span data-ttu-id="5aa64-215">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5aa64-215">Next steps</span></span>

- [<span data-ttu-id="5aa64-216">Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="5aa64-216">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="5aa64-217">Usar o Surface Diagnostic Toolkit for Business usando comandos</span><span class="sxs-lookup"><span data-stu-id="5aa64-217">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <a name="changes-and-updates"></a><span data-ttu-id="5aa64-218">Alterações e atualizações</span><span class="sxs-lookup"><span data-stu-id="5aa64-218">Changes and updates</span></span>

### <a name="version-2.131.139.0"></a><span data-ttu-id="5aa64-219">Versão 2.131.139.0</span><span class="sxs-lookup"><span data-stu-id="5aa64-219">Version 2.131.139.0</span></span>

<span data-ttu-id="5aa64-220">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-220">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="5aa64-221">Suporte para Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="5aa64-221">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="5aa64-222">Experiência de suporte perfeita no Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="5aa64-222">Seamless support experience on Surface Pro X</span></span>
- <span data-ttu-id="5aa64-223">Melhorias de segurança</span><span class="sxs-lookup"><span data-stu-id="5aa64-223">Security improvements</span></span>
- <span data-ttu-id="5aa64-224">Melhorias na experiência do usuário inclusiva</span><span class="sxs-lookup"><span data-stu-id="5aa64-224">Inclusive user experience improvements</span></span>

### <a name="version-2.124.139.0"></a><span data-ttu-id="5aa64-225">Versão 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="5aa64-225">Version 2.124.139.0</span></span>

<span data-ttu-id="5aa64-226">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-226">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="5aa64-227">Suporte integrado contínuo</span><span class="sxs-lookup"><span data-stu-id="5aa64-227">Seamless integrated support</span></span>
- <span data-ttu-id="5aa64-228">Salvar todos os resultados do teste</span><span class="sxs-lookup"><span data-stu-id="5aa64-228">Save all test results</span></span>
- <span data-ttu-id="5aa64-229">Verificar se a imagem é personalizada criada</span><span class="sxs-lookup"><span data-stu-id="5aa64-229">Check if the image is custom created</span></span>
- <span data-ttu-id="5aa64-230">Incluir avisos do gerenciador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5aa64-230">Include warnings from device manager</span></span>
- <span data-ttu-id="5aa64-231">Versão do firmware do Dock</span><span class="sxs-lookup"><span data-stu-id="5aa64-231">Dock firmware version</span></span>
- <span data-ttu-id="5aa64-232">Sinalizar unidades como possíveis falhas no teste de armazenamento</span><span class="sxs-lookup"><span data-stu-id="5aa64-232">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="5aa64-233">Remover link do armazenamento</span><span class="sxs-lookup"><span data-stu-id="5aa64-233">Remove store link</span></span> 

### <a name="version-2.121.139"></a><span data-ttu-id="5aa64-234">Versão 2.121.139</span><span class="sxs-lookup"><span data-stu-id="5aa64-234">Version 2.121.139</span></span>
*<span data-ttu-id="5aa64-235">Data do lançamento: 31 de julho de 2020</span><span class="sxs-lookup"><span data-stu-id="5aa64-235">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="5aa64-236">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-236">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="5aa64-237">Experiência de suporte contínuo</span><span class="sxs-lookup"><span data-stu-id="5aa64-237">Seamless support experience</span></span>
- <span data-ttu-id="5aa64-238">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="5aa64-238">Bug fixes</span></span>

### <a name="version-2.94.139.0"></a><span data-ttu-id="5aa64-239">Versão 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="5aa64-239">Version 2.94.139.0</span></span>
*<span data-ttu-id="5aa64-240">Data do lançamento: 11 de maio de 2020</span><span class="sxs-lookup"><span data-stu-id="5aa64-240">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="5aa64-241">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="5aa64-242">Capacidade de ignorar o Windows Update para executar a verificação de hardware.</span><span class="sxs-lookup"><span data-stu-id="5aa64-242">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="5aa64-243">Capacidade de receber notificações sobre a atualização de versão mais recente</span><span class="sxs-lookup"><span data-stu-id="5aa64-243">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="5aa64-244">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="5aa64-244">Surface Go 2</span></span>
- <span data-ttu-id="5aa64-245">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="5aa64-245">Surface Book 3</span></span>
- <span data-ttu-id="5aa64-246">Mostrar indicador de progresso</span><span class="sxs-lookup"><span data-stu-id="5aa64-246">Show progress indicator</span></span>


### <a name="version-2.43.139.0"></a><span data-ttu-id="5aa64-247">Versão 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="5aa64-247">Version 2.43.139.0</span></span>
*<span data-ttu-id="5aa64-248">Data do lançamento: 21 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="5aa64-248">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="5aa64-249">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-249">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="5aa64-250">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="5aa64-250">Surface Pro 7</span></span>
- <span data-ttu-id="5aa64-251">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="5aa64-251">Surface Laptop 3</span></span>

### <a name="version-2.42.139.0"></a><span data-ttu-id="5aa64-252">Versão 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="5aa64-252">Version 2.42.139.0</span></span>
*<span data-ttu-id="5aa64-253">Data do lançamento: 24 de setembro de 2019</span><span class="sxs-lookup"><span data-stu-id="5aa64-253">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="5aa64-254">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-254">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="5aa64-255">Capacidade de baixar relatórios de hardware.</span><span class="sxs-lookup"><span data-stu-id="5aa64-255">Ability to download hardware reports.</span></span>
- <span data-ttu-id="5aa64-256">Capacidade de entrar em contato com o Suporte da Microsoft diretamente da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="5aa64-256">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <a name="version-2.41.139.0"></a><span data-ttu-id="5aa64-257">Versão 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="5aa64-257">Version 2.41.139.0</span></span>
*<span data-ttu-id="5aa64-258">Data do lançamento: 24 de junho de 2019</span><span class="sxs-lookup"><span data-stu-id="5aa64-258">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="5aa64-259">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-259">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="5aa64-260">Informações de versão do driver incluídas em logs e relatórios.</span><span class="sxs-lookup"><span data-stu-id="5aa64-260">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="5aa64-261">Capacidade de fornecer comentários sobre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5aa64-261">Ability to provide feedback about the app.</span></span><br>


### <a name="version-2.36.139.0"></a><span data-ttu-id="5aa64-262">Versão 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="5aa64-262">Version 2.36.139.0</span></span>
*<span data-ttu-id="5aa64-263">Data do lançamento: 26 de abril de 2019</span><span class="sxs-lookup"><span data-stu-id="5aa64-263">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="5aa64-264">Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aa64-264">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="5aa64-265">Opção de instalação avançada para desbloquear recursos de administrador por meio da interface do usuário do instalador, sem a necessidade de configuração de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="5aa64-265">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="5aa64-266">Melhorias de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="5aa64-266">Accessibility improvements.</span></span>
- <span data-ttu-id="5aa64-267">Configurações de controle de brilho da superfície incluídas nos logs.</span><span class="sxs-lookup"><span data-stu-id="5aa64-267">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="5aa64-268">Link de suporte de compatibilidade do monitor externo no gerador de relatório.</span><span class="sxs-lookup"><span data-stu-id="5aa64-268">External monitor compatibility support link in report generator.</span></span>
