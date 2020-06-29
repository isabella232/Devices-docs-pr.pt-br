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
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830200"
---
# <span data-ttu-id="38434-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="38434-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="38434-105">O Microsoft Surface Deployment Accelerator (SDA) automatiza a criação e a configuração de uma experiência de implantação recomendada pela Microsoft usando as ferramentas de implantação gratuitas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38434-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="38434-106">Reprojetado em abril de 2020 para simplificar e automatizar a implantação de imagens de superfície em um ambiente corporativo, a ferramenta SDA permite que você crie uma imagem do Windows "de fábrica" que você pode personalizar para seus requisitos organizacionais.</span><span class="sxs-lookup"><span data-stu-id="38434-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="38434-107">A ferramenta de fonte aberta SDA orientada por script aproveita o kit de avaliação e implantação do Windows (ADK) para Windows 10, facilitando a criação de imagens do Windows (WIM) em ambientes de teste ou produção.</span><span class="sxs-lookup"><span data-stu-id="38434-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="38434-108">Se o ADK mais recente ainda não estiver instalado, ele será baixado e instalado ao executar a ferramenta SDA.</span><span class="sxs-lookup"><span data-stu-id="38434-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="38434-109">A imagem resultante corresponde à configuração de imagens de recuperação bare-metal (BMR), sem nenhum aplicativo pré-instalado, como o Microsoft Office ou o aplicativo da superfície da UWP.</span><span class="sxs-lookup"><span data-stu-id="38434-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="38434-110">Para executar o SDA:</span><span class="sxs-lookup"><span data-stu-id="38434-110">To run SDA:</span></span>**

1. <span data-ttu-id="38434-111">Acesse [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) no github.</span><span class="sxs-lookup"><span data-stu-id="38434-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="38434-112">Selecione **clonar ou baixar** e revisar o arquivo readme.</span><span class="sxs-lookup"><span data-stu-id="38434-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="38434-113">Edite o script com as variáveis adequadas para o seu ambiente, conforme documentado no README, e examine antes de executá-lo em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="38434-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![Ferramenta de aceleração de implantação de superfície em execução](images/surface-deployment-accelerator.png)

## <span data-ttu-id="38434-115">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="38434-115">Related links</span></span>

 - [<span data-ttu-id="38434-116">Ferramenta de implantação de imagem de fonte aberta liberada no GitHub</span><span class="sxs-lookup"><span data-stu-id="38434-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="38434-117">Baixar e instalar o Windows ADK</span><span class="sxs-lookup"><span data-stu-id="38434-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
