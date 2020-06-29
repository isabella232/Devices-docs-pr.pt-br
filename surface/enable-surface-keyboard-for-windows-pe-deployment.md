---
title: Como habilitar o teclado do laptop Surface durante a implantação do MDT
description: Ao usar o MDT para implantar o Windows 10 em laptops Surface, você precisa importar drivers de teclado para usar no ambiente Windows PE.
keywords: superfície do Windows 10, automatizar, personalizar, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830281"
---
# <span data-ttu-id="c14da-104">Como habilitar o teclado do laptop Surface durante a implantação do MDT</span><span class="sxs-lookup"><span data-stu-id="c14da-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="c14da-105">Este artigo aborda uma abordagem de implantação que usa o Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="c14da-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="c14da-106">Você também pode aplicar essas informações a outras metodologias de implantação.</span><span class="sxs-lookup"><span data-stu-id="c14da-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="c14da-107">Na maioria dos tipos de dispositivos Surface, o teclado deve funcionar durante a instalação do Lite Touch (LTI).</span><span class="sxs-lookup"><span data-stu-id="c14da-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="c14da-108">No entanto, o Surface laptop requer alguns drivers adicionais para ativar o teclado.</span><span class="sxs-lookup"><span data-stu-id="c14da-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="c14da-109">Para laptop Surface (1ª gen) e dispositivos Surface laptop 2, você deve preparar a estrutura de pastas e os perfis de seleção que permitem especificar os drivers de teclado para uso durante a fase de Windows PE (ambiente de pré-instalação do Windows) do LTI.</span><span class="sxs-lookup"><span data-stu-id="c14da-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="c14da-110">Para obter mais informações sobre essa estrutura de pastas, consulte [implantar uma imagem do Windows 10 usando o MDT: etapa 5: preparar o repositório de drivers](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="c14da-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="c14da-111">No momento, não há suporte para adicionar drivers de teclado 2 de Surface laptop 2 e Surface laptop 3 na mesma instância de inicialização do Windows PE devido a um conflito de driver; em vez disso, use instâncias separadas.</span><span class="sxs-lookup"><span data-stu-id="c14da-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c14da-112">Se você estiver implantando uma imagem do Windows 10 em um laptop Surface com o Windows 10 no modo S pré-instalado, consulte KB [4032347, problemas ao implantar o Windows em dispositivos Surface com o Windows 10 pré-instalado no modo S](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="c14da-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="c14da-113">Para adicionar os drivers do teclado ao perfil de seleção, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c14da-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="c14da-114">Baixe o arquivo MSI do laptop de superfície mais recente nos locais apropriados:</span><span class="sxs-lookup"><span data-stu-id="c14da-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="c14da-115">Firmware e drivers de laptop Surface (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="c14da-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="c14da-116">Firmware e drivers do Surface laptop 2</span><span class="sxs-lookup"><span data-stu-id="c14da-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="c14da-117">Laptop Surface 3 com drivers e firmware do processador Intel</span><span class="sxs-lookup"><span data-stu-id="c14da-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="c14da-118">Extraia o conteúdo do arquivo MSI do laptop Surface para uma pasta que você pode localizar facilmente (por exemplo, c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="c14da-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="c14da-119">Para extrair o conteúdo, abra uma janela de prompt de comando elevado e execute o comando do seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="c14da-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="c14da-120">Abra o Workbench de implantação e expanda o nó **compartilhamentos de implantação** e o compartilhamento de implantação e navegue até a pasta **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="c14da-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Imagem que mostra o local da pasta WindowsPEX64 no Workbench de implantação](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="c14da-122">Clique com o botão direito do mouse na pasta **WindowsPEX64** e selecione **importar drivers**.</span><span class="sxs-lookup"><span data-stu-id="c14da-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="c14da-123">Siga as instruções no assistente de importação de driver para importar as pastas do driver para a pasta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="c14da-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="c14da-124">Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.</span><span class="sxs-lookup"><span data-stu-id="c14da-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="c14da-125">A estrutura do diretório começará com o SurfacePlatformInstaller (arquivos MSI mais antigos) ou com o SurfaceUpdate (arquivos MSI mais recentes), dependendo de quando o MSI foi lançado.</span><span class="sxs-lookup"><span data-stu-id="c14da-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="c14da-126">Para dar suporte ao laptop Surface (1ª gen), importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="c14da-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="c14da-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="c14da-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="c14da-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="c14da-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c14da-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="c14da-131">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="c14da-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="c14da-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="c14da-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="c14da-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="c14da-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c14da-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="c14da-136">Para dar suporte a Surface laptop 2, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="c14da-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="c14da-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="c14da-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="c14da-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="c14da-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="c14da-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="c14da-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="c14da-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="c14da-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="c14da-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="c14da-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c14da-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="c14da-144">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="c14da-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="c14da-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="c14da-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c14da-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="c14da-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c14da-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="c14da-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c14da-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="c14da-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c14da-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="c14da-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c14da-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="c14da-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c14da-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="c14da-152">Para dar suporte ao laptop 4 do Surface com processador Intel, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="c14da-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="c14da-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="c14da-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c14da-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="c14da-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c14da-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="c14da-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c14da-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="c14da-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c14da-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="c14da-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c14da-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="c14da-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="c14da-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="c14da-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c14da-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="c14da-161">A importação das seguintes pastas habilitará a funcionalidade completa do teclado, do trackpad e do toque no PE para laptops Surface 3.</span><span class="sxs-lookup"><span data-stu-id="c14da-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="c14da-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="c14da-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c14da-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="c14da-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c14da-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="c14da-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c14da-165">IclSerialIOUART</span></span>
- <span data-ttu-id="c14da-166">itouch</span><span class="sxs-lookup"><span data-stu-id="c14da-166">itouch</span></span>
- <span data-ttu-id="c14da-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="c14da-167">IclChipset</span></span>
- <span data-ttu-id="c14da-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="c14da-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="c14da-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="c14da-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="c14da-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="c14da-170">ManagementEngine</span></span>
- <span data-ttu-id="c14da-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="c14da-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="c14da-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="c14da-172">SurfaceBattery</span></span>
- <span data-ttu-id="c14da-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="c14da-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="c14da-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c14da-174">SurfaceHidMini</span></span>
- <span data-ttu-id="c14da-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="c14da-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="c14da-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="c14da-176">SurfaceIntegration</span></span>
- <span data-ttu-id="c14da-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c14da-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="c14da-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="c14da-178">SurfaceService</span></span>
- <span data-ttu-id="c14da-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="c14da-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="c14da-180">Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.</span><span class="sxs-lookup"><span data-stu-id="c14da-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="c14da-181">A estrutura do diretório começará com o SurfacePlatformInstaller (arquivos MSI mais antigos) ou com o SurfaceUpdate (arquivos MSI mais recentes), dependendo de quando o MSI foi lançado.</span><span class="sxs-lookup"><span data-stu-id="c14da-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="c14da-182">Para dar suporte ao laptop Surface (1ª gen), importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="c14da-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="c14da-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="c14da-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="c14da-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="c14da-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c14da-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="c14da-187">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="c14da-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="c14da-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="c14da-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="c14da-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="c14da-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c14da-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="c14da-192">Para dar suporte a Surface laptop 2, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="c14da-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="c14da-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="c14da-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="c14da-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c14da-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="c14da-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="c14da-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="c14da-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="c14da-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="c14da-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="c14da-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="c14da-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c14da-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="c14da-200">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="c14da-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="c14da-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="c14da-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c14da-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="c14da-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c14da-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="c14da-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c14da-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="c14da-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c14da-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="c14da-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c14da-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="c14da-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c14da-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="c14da-208">Para dar suporte ao laptop 4 do Surface com processador Intel, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="c14da-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="c14da-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c14da-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="c14da-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c14da-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="c14da-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c14da-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="c14da-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c14da-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="c14da-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c14da-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="c14da-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c14da-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="c14da-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="c14da-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="c14da-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c14da-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="c14da-217">Para o laptop de Surface 3 com processador Intel, o modelo é o laptop Surface 3.</span><span class="sxs-lookup"><span data-stu-id="c14da-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="c14da-218">Os drivers de laptop da superfície restante estão localizados na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="c14da-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="c14da-219">Verifique se a pasta WindowsPEX64 agora contém os drivers importados.</span><span class="sxs-lookup"><span data-stu-id="c14da-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="c14da-220">A pasta deve ser semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="c14da-220">The folder should resemble the following:</span></span>  

   ![Imagem que mostra os drivers recém importados na pasta WindowsPEX64 do Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="c14da-222">Configurar um perfil de seleção que usa a pasta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="c14da-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="c14da-223">O perfil de seleção deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="c14da-223">The selection profile should resemble the following:</span></span>  

   ![Imagem que mostra a pasta WindowsPEX64 selecionada como parte de um perfil de seleção](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="c14da-225">Configure as propriedades do Windows PE do compartilhamento de implantação do MDT para usar o novo perfil de seleção, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c14da-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="c14da-226">Para a **plataforma**, selecione **x64**.</span><span class="sxs-lookup"><span data-stu-id="c14da-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="c14da-227">Para o **perfil de seleção**, selecione o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="c14da-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="c14da-228">Selecione **incluir todos os drivers do perfil de seleção**.</span><span class="sxs-lookup"><span data-stu-id="c14da-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Imagem que mostra as propriedades do Windows PE do compartilhamento de implantação do MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="c14da-230">Verifique se você configurou os drivers de laptop da superfície restante usando um perfil de seleção ou uma variável **DriverGroup001** .</span><span class="sxs-lookup"><span data-stu-id="c14da-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="c14da-231">Para laptop Surface (1ª gen), o modelo é o **laptop Surface**.</span><span class="sxs-lookup"><span data-stu-id="c14da-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="c14da-232">Os drivers de laptop da superfície restante devem residir na pasta de \MDT de implantação do Share\Out-of-Box Drivers\Windows10\X64\Surface laptop, conforme mostrado na figura que segue esta lista.</span><span class="sxs-lookup"><span data-stu-id="c14da-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="c14da-233">Para o Surface laptop 2, o modelo é o **laptop Surface 2**.</span><span class="sxs-lookup"><span data-stu-id="c14da-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="c14da-234">Os drivers de laptop da superfície restante devem residir na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 2.</span><span class="sxs-lookup"><span data-stu-id="c14da-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="c14da-235">Para o laptop de Surface 3 com processador Intel, o modelo é o laptop Surface 3.</span><span class="sxs-lookup"><span data-stu-id="c14da-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="c14da-236">Os drivers de laptop da superfície restante estão localizados na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="c14da-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Imagem que mostra os drivers de laptop de superfície normal (1ª gen) na pasta de laptop Surface do Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="c14da-238">Depois de configurar o compartilhamento de implantação do MDT para usar o novo perfil de seleção e as configurações relacionadas, continue o processo de implantação conforme descrito em [implantar uma imagem do Windows 10 usando o MDT: etapa 6: criar a sequência de tarefas de implantação](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span><span class="sxs-lookup"><span data-stu-id="c14da-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
