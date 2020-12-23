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
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247303"
---
# <span data-ttu-id="d102e-104">Como habilitar o teclado do laptop Surface durante a implantação do MDT</span><span class="sxs-lookup"><span data-stu-id="d102e-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="d102e-105">Este artigo aborda uma abordagem de implantação que usa o Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="d102e-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="d102e-106">Você também pode aplicar essas informações a outras metodologias de implantação.</span><span class="sxs-lookup"><span data-stu-id="d102e-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="d102e-107">Na maioria dos tipos de dispositivos Surface, o teclado deve funcionar durante a instalação do Lite Touch (LTI).</span><span class="sxs-lookup"><span data-stu-id="d102e-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="d102e-108">No entanto, o Surface laptop requer alguns drivers adicionais para ativar o teclado.</span><span class="sxs-lookup"><span data-stu-id="d102e-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="d102e-109">Para laptop Surface (1ª gen) e dispositivos Surface laptop 2, você deve preparar a estrutura de pastas e os perfis de seleção que permitem especificar os drivers de teclado para uso durante a fase de Windows PE (ambiente de pré-instalação do Windows) do LTI.</span><span class="sxs-lookup"><span data-stu-id="d102e-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="d102e-110">Para obter mais informações sobre essa estrutura de pastas, consulte [implantar uma imagem do Windows 10 usando o MDT: etapa 5: preparar o repositório de drivers](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="d102e-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d102e-111">Se você estiver implantando uma imagem do Windows 10 em um laptop Surface com o Windows 10 no modo S pré-instalado, consulte KB [4032347, problemas ao implantar o Windows em dispositivos Surface com o Windows 10 pré-instalado no modo S](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="d102e-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="d102e-112">Para adicionar os drivers do teclado ao perfil de seleção, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d102e-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="d102e-113">Baixe o arquivo MSI do laptop de superfície mais recente nos locais apropriados:</span><span class="sxs-lookup"><span data-stu-id="d102e-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="d102e-114">Firmware e drivers de laptop Surface (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="d102e-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="d102e-115">Firmware e drivers do Surface laptop 2</span><span class="sxs-lookup"><span data-stu-id="d102e-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="d102e-116">Laptop Surface 3 com drivers e firmware do processador Intel</span><span class="sxs-lookup"><span data-stu-id="d102e-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="d102e-117">Extraia o conteúdo do arquivo MSI do laptop Surface para uma pasta que você pode localizar facilmente (por exemplo, c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="d102e-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="d102e-118">Para extrair o conteúdo, abra uma janela de prompt de comando elevado e execute o comando do seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="d102e-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="d102e-119">Abra o Workbench de implantação e expanda o nó **compartilhamentos de implantação** e o compartilhamento de implantação e navegue até a pasta **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="d102e-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Imagem que mostra o local da pasta WindowsPEX64 no Workbench de implantação](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="d102e-121">Clique com o botão direito do mouse na pasta **WindowsPEX64** e selecione **importar drivers**.</span><span class="sxs-lookup"><span data-stu-id="d102e-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="d102e-122">Siga as instruções no assistente de importação de driver para importar as pastas do driver para a pasta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="d102e-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="d102e-123">Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.</span><span class="sxs-lookup"><span data-stu-id="d102e-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="d102e-124">A estrutura do diretório começará com o SurfacePlatformInstaller (arquivos MSI mais antigos) ou com o SurfaceUpdate (arquivos MSI mais recentes), dependendo de quando o MSI foi lançado.</span><span class="sxs-lookup"><span data-stu-id="d102e-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="d102e-125">Para dar suporte ao laptop Surface (1ª gen), importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="d102e-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="d102e-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="d102e-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="d102e-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="d102e-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d102e-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="d102e-130">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="d102e-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="d102e-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="d102e-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="d102e-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="d102e-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d102e-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="d102e-135">Para dar suporte a Surface laptop 2, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="d102e-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="d102e-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="d102e-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="d102e-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="d102e-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="d102e-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="d102e-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="d102e-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="d102e-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="d102e-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="d102e-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d102e-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="d102e-143">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="d102e-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="d102e-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="d102e-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d102e-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="d102e-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d102e-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="d102e-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d102e-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="d102e-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d102e-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="d102e-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d102e-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="d102e-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d102e-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="d102e-151">Para dar suporte ao laptop 4 do Surface com processador Intel, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="d102e-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="d102e-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="d102e-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d102e-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="d102e-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d102e-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="d102e-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d102e-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="d102e-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d102e-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="d102e-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d102e-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="d102e-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="d102e-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="d102e-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d102e-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="d102e-160">A importação das seguintes pastas habilitará a funcionalidade completa do teclado, do trackpad e do toque no PE para laptops Surface 3.</span><span class="sxs-lookup"><span data-stu-id="d102e-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="d102e-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="d102e-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d102e-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="d102e-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d102e-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="d102e-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d102e-164">IclSerialIOUART</span></span>
- <span data-ttu-id="d102e-165">itouch</span><span class="sxs-lookup"><span data-stu-id="d102e-165">itouch</span></span>
- <span data-ttu-id="d102e-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="d102e-166">IclChipset</span></span>
- <span data-ttu-id="d102e-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="d102e-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="d102e-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="d102e-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="d102e-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="d102e-169">ManagementEngine</span></span>
- <span data-ttu-id="d102e-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="d102e-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="d102e-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="d102e-171">SurfaceBattery</span></span>
- <span data-ttu-id="d102e-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="d102e-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="d102e-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d102e-173">SurfaceHidMini</span></span>
- <span data-ttu-id="d102e-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="d102e-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="d102e-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="d102e-175">SurfaceIntegration</span></span>
- <span data-ttu-id="d102e-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d102e-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="d102e-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="d102e-177">SurfaceService</span></span>
- <span data-ttu-id="d102e-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="d102e-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="d102e-179">Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.</span><span class="sxs-lookup"><span data-stu-id="d102e-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="d102e-180">A estrutura do diretório começará com o SurfacePlatformInstaller (arquivos MSI mais antigos) ou com o SurfaceUpdate (arquivos MSI mais recentes), dependendo de quando o MSI foi lançado.</span><span class="sxs-lookup"><span data-stu-id="d102e-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="d102e-181">Para dar suporte ao laptop Surface (1ª gen), importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="d102e-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="d102e-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="d102e-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="d102e-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="d102e-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d102e-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="d102e-186">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="d102e-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="d102e-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="d102e-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="d102e-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="d102e-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d102e-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="d102e-191">Para dar suporte a Surface laptop 2, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="d102e-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="d102e-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="d102e-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="d102e-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d102e-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="d102e-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="d102e-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="d102e-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="d102e-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="d102e-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="d102e-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="d102e-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d102e-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="d102e-199">Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="d102e-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="d102e-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="d102e-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d102e-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="d102e-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d102e-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="d102e-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d102e-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="d102e-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d102e-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="d102e-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d102e-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="d102e-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d102e-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="d102e-207">Para dar suporte ao laptop 4 do Surface com processador Intel, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="d102e-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="d102e-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d102e-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="d102e-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d102e-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="d102e-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d102e-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="d102e-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d102e-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="d102e-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d102e-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="d102e-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d102e-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="d102e-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="d102e-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="d102e-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d102e-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="d102e-216">Para o laptop de Surface 3 com processador Intel, o modelo é o laptop Surface 3.</span><span class="sxs-lookup"><span data-stu-id="d102e-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="d102e-217">Os drivers de laptop da superfície restante estão localizados na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="d102e-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="d102e-218">Verifique se a pasta WindowsPEX64 agora contém os drivers importados.</span><span class="sxs-lookup"><span data-stu-id="d102e-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="d102e-219">A pasta deve ser semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="d102e-219">The folder should resemble the following:</span></span>  

   ![Imagem que mostra os drivers recém importados na pasta WindowsPEX64 do Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="d102e-221">Configurar um perfil de seleção que usa a pasta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="d102e-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="d102e-222">O perfil de seleção deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="d102e-222">The selection profile should resemble the following:</span></span>  

   ![Imagem que mostra a pasta WindowsPEX64 selecionada como parte de um perfil de seleção](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="d102e-224">Configure as propriedades do Windows PE do compartilhamento de implantação do MDT para usar o novo perfil de seleção, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d102e-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="d102e-225">Para a **plataforma**, selecione **x64**.</span><span class="sxs-lookup"><span data-stu-id="d102e-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="d102e-226">Para o **perfil de seleção**, selecione o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="d102e-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="d102e-227">Selecione **incluir todos os drivers do perfil de seleção**.</span><span class="sxs-lookup"><span data-stu-id="d102e-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Imagem que mostra as propriedades do Windows PE do compartilhamento de implantação do MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="d102e-229">Verifique se você configurou os drivers de laptop da superfície restante usando um perfil de seleção ou uma variável **DriverGroup001** .</span><span class="sxs-lookup"><span data-stu-id="d102e-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="d102e-230">Para laptop Surface (1ª gen), o modelo é o **laptop Surface**.</span><span class="sxs-lookup"><span data-stu-id="d102e-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="d102e-231">Os drivers de laptop da superfície restante devem residir na pasta de \MDT de implantação do Share\Out-of-Box Drivers\Windows10\X64\Surface laptop, conforme mostrado na figura que segue esta lista.</span><span class="sxs-lookup"><span data-stu-id="d102e-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="d102e-232">Para o Surface laptop 2, o modelo é o **laptop Surface 2**.</span><span class="sxs-lookup"><span data-stu-id="d102e-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="d102e-233">Os drivers de laptop da superfície restante devem residir na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 2.</span><span class="sxs-lookup"><span data-stu-id="d102e-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="d102e-234">Para o laptop de Surface 3 com processador Intel, o modelo é o laptop Surface 3.</span><span class="sxs-lookup"><span data-stu-id="d102e-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="d102e-235">Os drivers de laptop da superfície restante estão localizados na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="d102e-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Imagem que mostra os drivers de laptop de superfície normal (1ª gen) na pasta de laptop Surface do Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="d102e-237">Depois de configurar o compartilhamento de implantação do MDT para usar o novo perfil de seleção e as configurações relacionadas, continue o processo de implantação conforme descrito em [implantar uma imagem do Windows 10 usando o MDT: etapa 6: criar a sequência de tarefas de implantação](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span><span class="sxs-lookup"><span data-stu-id="d102e-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
