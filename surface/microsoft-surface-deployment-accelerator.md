---
title: Microsoft Surface Deployment Accelerator (Surface)
description: O Microsoft Surface Deployment Accelerator fornece um mecanismo de implantação simples e rápido para que as organizações refaçam imagens de dispositivos Surface.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: implantar, instalar, ferramenta
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 0e136bd0a69db7a4c4e5cea7d2c065727dcc8fcc
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016430"
---
# <span data-ttu-id="0be93-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="0be93-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="0be93-105">O Microsoft Surface Deployment Accelerator (SDA) automatiza a criação e a configuração de uma experiência de implantação recomendada pela Microsoft usando as ferramentas de implantação gratuitas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0be93-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="0be93-106">Reprojetado em abril de 2020 para simplificar e automatizar a implantação de imagens de superfície em um ambiente corporativo, a ferramenta SDA permite que você crie uma imagem do Windows "de fábrica" que você pode personalizar para seus requisitos organizacionais.</span><span class="sxs-lookup"><span data-stu-id="0be93-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="0be93-107">A ferramenta de fonte aberta SDA orientada por script aproveita o kit de avaliação e implantação do Windows (ADK) para Windows 10, facilitando a criação de imagens do Windows (WIM) em ambientes de teste ou produção.</span><span class="sxs-lookup"><span data-stu-id="0be93-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="0be93-108">Se o ADK mais recente ainda não estiver instalado, ele será baixado e instalado ao executar a ferramenta SDA.</span><span class="sxs-lookup"><span data-stu-id="0be93-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="0be93-109">A imagem resultante corresponde à configuração de imagens de recuperação bare-metal (BMR), sem nenhum aplicativo pré-instalado, como o Microsoft Office ou o aplicativo da superfície da UWP.</span><span class="sxs-lookup"><span data-stu-id="0be93-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="0be93-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0be93-110">Requirements</span></span>

1. <span data-ttu-id="0be93-111">Uma unidade USB Thumb com pelo menos 16 GB de tamanho.</span><span class="sxs-lookup"><span data-stu-id="0be93-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="0be93-112">A unidade USB será formatada.</span><span class="sxs-lookup"><span data-stu-id="0be93-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="0be93-113">Um arquivo. ISO com o Windows 10 pro ou o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0be93-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="0be93-114">A ferramenta de criação de mídia pode ser usada para baixar o Windows 10 e criar um arquivo. ISO.</span><span class="sxs-lookup"><span data-stu-id="0be93-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="0be93-115">Para obter mais informações, consulte [baixar o Windows 10](https://www.microsoft.com/software-download/windows10).</span><span class="sxs-lookup"><span data-stu-id="0be93-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>

## <span data-ttu-id="0be93-116">Como executar o SDA</span><span class="sxs-lookup"><span data-stu-id="0be93-116">How to run SDA</span></span>

**<span data-ttu-id="0be93-117">Para executar o SDA:</span><span class="sxs-lookup"><span data-stu-id="0be93-117">To run SDA:</span></span>**

1. <span data-ttu-id="0be93-118">Acesse [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) no github.</span><span class="sxs-lookup"><span data-stu-id="0be93-118">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="0be93-119">Examine a documentação do [Leiame](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .</span><span class="sxs-lookup"><span data-stu-id="0be93-119">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="0be93-120">Na página [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) , clique no botão **código** e, em seguida, selecione **baixar CEP** para salvar os arquivos localmente em seu computador.</span><span class="sxs-lookup"><span data-stu-id="0be93-120">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="0be93-121">Clique com o botão direito do mouse no arquivo. zip e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0be93-121">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="0be93-122">Na guia **geral** , marque a caixa de seleção **desbloquear** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0be93-122">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="0be93-123">Extraia o arquivo. zip para um local em seu disco rígido (por exemplo: C:\SDA).</span><span class="sxs-lookup"><span data-stu-id="0be93-123">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="0be93-124">Abra um prompt do Windows PowerShell elevado e defina ExecutionPolicy para a sessão atual como Irrestrito.</span><span class="sxs-lookup"><span data-stu-id="0be93-124">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="0be93-125">Execute o script SDA especificando os parâmetros para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0be93-125">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="0be93-126">Por exemplo, o comando a seguir criará uma unidade USB inicializável que pode ser usada para instalar o Windows 10 em um Surface Hub 2:</span><span class="sxs-lookup"><span data-stu-id="0be93-126">For example, the following command will create a bootable USB drive that can be used to install Windows 10 on a Surface Hub 2:</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```

   ![Ferramenta de aceleração de implantação de superfície em execução](images/sda1.png)

    <span data-ttu-id="0be93-128">O script exigirá cerca de 45 minutos para ser executado, mas pode demorar mais, dependendo da CPU e dos recursos de disco disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0be93-128">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="0be93-129">Depois de criar uma imagem do Windows, o script solicitará que você confirme a letra da unidade USB.</span><span class="sxs-lookup"><span data-stu-id="0be93-129">After creating a Windows image, the script will ask you to confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="0be93-130">A unidade USB será formatada, configurada como inicializável, e os arquivos copiados para habilitar a instalação da imagem personalizada do Windows 10 para dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="0be93-130">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="0be93-131">Insira a unidade USB no dispositivo em que você deseja instalar o Windows 10 e reiniciar para começar a instalar o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0be93-131">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="0be93-132">A inicialização USB deve estar habilitada no BIOS, o que pode exigir que você Desabilite temporariamente a inicialização segura.</span><span class="sxs-lookup"><span data-stu-id="0be93-132">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0be93-133">A inicialização a partir da unidade USB iniciará imediatamente a instalação do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0be93-133">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="0be93-134">Verifique se o seu dispositivo está pronto antes de inserir o USB e reiniciar.</span><span class="sxs-lookup"><span data-stu-id="0be93-134">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="0be93-135">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="0be93-135">Related links</span></span>

 - [<span data-ttu-id="0be93-136">Ferramenta de implantação de imagem de fonte aberta liberada no GitHub</span><span class="sxs-lookup"><span data-stu-id="0be93-136">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="0be93-137">Baixar e instalar o Windows ADK</span><span class="sxs-lookup"><span data-stu-id="0be93-137">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
