---
title: Como habilitar o teclado do Surface Laptop durante a implantação do MDT
description: Ao usar o MDT para implantar o Windows 10 em laptops Surface, você precisa importar drivers de teclado para usar no ambiente do Windows PE.
keywords: windows 10 surface, automatizar, personalizar, mdt
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
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312057"
---
# <span data-ttu-id="791a7-104">Como habilitar o teclado do Surface Laptop durante a implantação do MDT</span><span class="sxs-lookup"><span data-stu-id="791a7-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="791a7-105">Este artigo aborda uma abordagem de implantação que usa o Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="791a7-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="791a7-106">Você também pode aplicar essas informações a outras metodologias de implantação.</span><span class="sxs-lookup"><span data-stu-id="791a7-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="791a7-107">Na maioria dos tipos de dispositivos Surface, o teclado deve funcionar durante a Lite Touch Installation (LTI).</span><span class="sxs-lookup"><span data-stu-id="791a7-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="791a7-108">No entanto, o Surface Laptop requer alguns drivers adicionais para habilitar o teclado.</span><span class="sxs-lookup"><span data-stu-id="791a7-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="791a7-109">Para dispositivos Surface Laptop (1ª geração) e Surface Laptop 2, você deve preparar a estrutura de pastas e os perfis de seleção que permitem especificar drivers de teclado para uso durante a fase do Ambiente de Pré-instalação do Windows (Windows PE) do LTI.</span><span class="sxs-lookup"><span data-stu-id="791a7-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="791a7-110">Para obter mais informações sobre essa estrutura de pastas, consulte Implantar uma imagem do [Windows 10 usando o MDT: Etapa 5: Preparar](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)o repositório de drivers.</span><span class="sxs-lookup"><span data-stu-id="791a7-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="791a7-111">Ao usar drivers de teclado para o Surface Laptop 2 e o Surface Laptop 3 na mesma instância de inicialização do Windows PE, talvez seja necessário redefinir manualmente o firmware se o teclado ou o touchpad não funcionarem no Windows PE:</span><span class="sxs-lookup"><span data-stu-id="791a7-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="791a7-112">Pressione e segure o botão Ligar/Desligar por 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="791a7-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="791a7-113">Se você estiver conectado a uma PSU (unidade de alimentação), pressione e segure o botão Ligar/Desligar até ver a luz no final do cabo PSU desligar brevemente antes de reconectar.</span><span class="sxs-lookup"><span data-stu-id="791a7-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="791a7-114">Se você estiver implantando uma imagem do Windows 10 em um Surface Laptop que tenha o Windows 10 no modo S pré-instalado, consulte KB [4032347,](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Problemas ao implantar o Windows em dispositivos Surface com o Windows 10 pré-instalado no modo S.</span><span class="sxs-lookup"><span data-stu-id="791a7-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="791a7-115">Para adicionar os drivers de teclado ao perfil de seleção, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="791a7-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="791a7-116">Baixe o arquivo MSI mais recente do Surface Laptop dos locais apropriados:</span><span class="sxs-lookup"><span data-stu-id="791a7-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="791a7-117">Firmware e drivers do Surface Laptop (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="791a7-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="791a7-118">Firmware e drivers do Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="791a7-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="791a7-119">Surface Laptop 3 com firmware e drivers de processador Intel</span><span class="sxs-lookup"><span data-stu-id="791a7-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="791a7-120">Extraia o conteúdo do arquivo MSI do Surface Laptop para uma pasta que você pode localizar facilmente (por exemplo, c:\surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="791a7-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="791a7-121">Para extrair o conteúdo, abra uma janela de Prompt de Comando com elevação e execute o comando a partir do exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="791a7-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="791a7-122">Abra o Deployment Workbench e expanda o nó **Deployment Shares** e seu compartilhamento de implantação e navegue até a **pasta WindowsPEX64.**</span><span class="sxs-lookup"><span data-stu-id="791a7-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Imagem que mostra o local da pasta WindowsPEX64 no Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="791a7-124">Clique com o botão direito do mouse **na pasta WindowsPEX64** e selecione **Import Drivers**.</span><span class="sxs-lookup"><span data-stu-id="791a7-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="791a7-125">Siga as instruções do Assistente para Importação de Driver para importar as pastas de driver para a pasta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="791a7-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="791a7-126">Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.</span><span class="sxs-lookup"><span data-stu-id="791a7-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="791a7-127">A estrutura de diretórios começará com SurfacePlatformInstaller (arquivos MSI mais antigos) ou SurfaceUpdate (arquivos MSI mais novos), dependendo de quando o MSI foi lançado.</span><span class="sxs-lookup"><span data-stu-id="791a7-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="791a7-128">Para dar suporte ao Surface Laptop (1ª geração), importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="791a7-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="791a7-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="791a7-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="791a7-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="791a7-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="791a7-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="791a7-133">Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="791a7-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="791a7-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="791a7-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="791a7-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="791a7-137">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="791a7-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="791a7-138">Para dar suporte ao Surface Laptop 2, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="791a7-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="791a7-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="791a7-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="791a7-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="791a7-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="791a7-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="791a7-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="791a7-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="791a7-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="791a7-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="791a7-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="791a7-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="791a7-146">Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="791a7-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="791a7-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="791a7-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="791a7-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="791a7-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="791a7-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="791a7-150">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="791a7-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="791a7-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="791a7-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="791a7-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="791a7-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="791a7-153">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="791a7-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="791a7-154">Para dar suporte ao Surface Laptop 3 com processador Intel, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="791a7-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="791a7-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="791a7-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="791a7-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="791a7-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="791a7-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="791a7-158">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="791a7-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="791a7-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="791a7-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="791a7-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="791a7-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="791a7-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="791a7-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="791a7-162">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="791a7-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="791a7-163">A importação das seguintes pastas habilita a funcionalidade completa de teclado, trackpad e toque no PE para Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="791a7-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="791a7-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="791a7-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="791a7-165">SerialIOI2C</span></span>
    - <span data-ttu-id="791a7-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="791a7-166">SerialIOSPI</span></span>
    - <span data-ttu-id="791a7-167">SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="791a7-167">SerialIOUART</span></span>
    - <span data-ttu-id="791a7-168">itouch</span><span class="sxs-lookup"><span data-stu-id="791a7-168">itouch</span></span>
    - <span data-ttu-id="791a7-169">Chipset</span><span class="sxs-lookup"><span data-stu-id="791a7-169">Chipset</span></span>
    - <span data-ttu-id="791a7-170">ChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="791a7-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="791a7-171">ChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="791a7-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="791a7-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="791a7-172">ManagementEngine</span></span>
    - <span data-ttu-id="791a7-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="791a7-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="791a7-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="791a7-174">SurfaceBattery</span></span>
    - <span data-ttu-id="791a7-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="791a7-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="791a7-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="791a7-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="791a7-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="791a7-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="791a7-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="791a7-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="791a7-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="791a7-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="791a7-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="791a7-180">SurfaceService</span></span>
    - <span data-ttu-id="791a7-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="791a7-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="791a7-182">Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.</span><span class="sxs-lookup"><span data-stu-id="791a7-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="791a7-183">A estrutura de diretórios começará com SurfacePlatformInstaller (arquivos MSI mais antigos) ou SurfaceUpdate (arquivos MSI mais novos), dependendo de quando o MSI foi lançado.</span><span class="sxs-lookup"><span data-stu-id="791a7-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="791a7-184">Para dar suporte ao Surface Laptop (1ª geração), importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="791a7-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="791a7-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="791a7-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="791a7-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="791a7-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="791a7-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="791a7-189">Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="791a7-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="791a7-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="791a7-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="791a7-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="791a7-193">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="791a7-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="791a7-194">Para dar suporte ao Surface Laptop 2, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="791a7-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="791a7-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="791a7-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="791a7-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="791a7-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="791a7-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="791a7-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="791a7-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="791a7-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="791a7-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="791a7-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="791a7-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="791a7-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="791a7-202">Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="791a7-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="791a7-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="791a7-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="791a7-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="791a7-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="791a7-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="791a7-206">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="791a7-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="791a7-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="791a7-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="791a7-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="791a7-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="791a7-209">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="791a7-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="791a7-210">Para dar suporte ao Surface Laptop 3 com processador Intel, importe as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="791a7-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="791a7-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="791a7-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="791a7-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="791a7-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="791a7-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="791a7-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="791a7-214">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="791a7-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="791a7-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="791a7-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="791a7-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="791a7-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="791a7-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="791a7-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="791a7-218">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="791a7-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="791a7-219">Para o Surface Laptop 3 com processador Intel, o modelo é o Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="791a7-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="791a7-220">Os drivers restantes do Surface Laptop estão localizados na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="791a7-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="791a7-221">Verifique se a pasta WindowsPEX64 agora contém os drivers importados.</span><span class="sxs-lookup"><span data-stu-id="791a7-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="791a7-222">A pasta deve se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="791a7-222">The folder should resemble the following:</span></span>  

   ![Imagem que mostra os drivers recém-importados na pasta WindowsPEX64 do Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="791a7-224">Configure um perfil de seleção que use a pasta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="791a7-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="791a7-225">O perfil de seleção deve se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="791a7-225">The selection profile should resemble the following:</span></span>  

   ![Imagem que mostra a pasta WindowsPEX64 selecionada como parte de um perfil de seleção](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="791a7-227">Configure as propriedades do Windows PE do compartilhamento de implantação do MDT para usar o novo perfil de seleção, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="791a7-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="791a7-228">For **Platform**, select **x64**.</span><span class="sxs-lookup"><span data-stu-id="791a7-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="791a7-229">Para **o perfil de seleção,** selecione o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="791a7-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="791a7-230">Selecione **Incluir todos os drivers do perfil de seleção.**</span><span class="sxs-lookup"><span data-stu-id="791a7-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Imagem que mostra as propriedades do Windows PE do compartilhamento de implantação do MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="791a7-232">Verifique se você configurou os drivers restantes do Surface Laptop usando um perfil de seleção ou uma **variável DriverGroup001.**</span><span class="sxs-lookup"><span data-stu-id="791a7-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="791a7-233">Para o Surface Laptop (1ª geração), o modelo é **o Surface Laptop.**</span><span class="sxs-lookup"><span data-stu-id="791a7-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="791a7-234">Os drivers restantes do Surface Laptop devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, conforme mostrado na figura que segue esta lista.</span><span class="sxs-lookup"><span data-stu-id="791a7-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="791a7-235">Para o Surface Laptop 2, o modelo é **o Surface Laptop 2.**</span><span class="sxs-lookup"><span data-stu-id="791a7-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="791a7-236">Os drivers restantes do Surface Laptop devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.</span><span class="sxs-lookup"><span data-stu-id="791a7-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="791a7-237">Para o Surface Laptop 3 com processador Intel, o modelo é o Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="791a7-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="791a7-238">Os drivers restantes do Surface Laptop estão localizados na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="791a7-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Imagem que mostra os drivers regulares do Surface Laptop (1ª geração) na pasta Surface Laptop do Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="791a7-240">Depois de configurar o Compartilhamento de Implantação do MDT para usar o novo perfil de seleção e as configurações relacionadas, continue o processo de implantação conforme descrito em Implantar uma imagem do [Windows 10 usando o MDT: Etapa 6:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)Criar a sequência de tarefas de implantação.</span><span class="sxs-lookup"><span data-stu-id="791a7-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
