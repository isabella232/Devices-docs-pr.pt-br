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
# Microsoft Surface Deployment Accelerator

O Microsoft Surface Deployment Accelerator (SDA) automatiza a criação e a configuração de uma experiência de implantação recomendada pela Microsoft usando as ferramentas de implantação gratuitas da Microsoft.

Reprojetado em abril de 2020 para simplificar e automatizar a implantação de imagens de superfície em um ambiente corporativo, a ferramenta SDA permite que você crie uma imagem do Windows "de fábrica" que você pode personalizar para seus requisitos organizacionais.

A ferramenta de fonte aberta SDA orientada por script aproveita o kit de avaliação e implantação do Windows (ADK) para Windows 10, facilitando a criação de imagens do Windows (WIM) em ambientes de teste ou produção. Se o ADK mais recente ainda não estiver instalado, ele será baixado e instalado ao executar a ferramenta SDA.

A imagem resultante corresponde à configuração de imagens de recuperação bare-metal (BMR), sem nenhum aplicativo pré-instalado, como o Microsoft Office ou o aplicativo da superfície da UWP.

**Para executar o SDA:**

1. Acesse [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) no github. 
2. Selecione **clonar ou baixar** e revisar o arquivo readme.
3. Edite o script com as variáveis adequadas para o seu ambiente, conforme documentado no README, e examine antes de executá-lo em seu ambiente de teste. 

   ![Ferramenta de aceleração de implantação de superfície em execução](images/surface-deployment-accelerator.png)

## Links relacionados

 - [Ferramenta de implantação de imagem de fonte aberta liberada no GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Baixar e instalar o Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
