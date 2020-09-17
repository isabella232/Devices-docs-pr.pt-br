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
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016552"
---
# Microsoft Surface Deployment Accelerator

O Microsoft Surface Deployment Accelerator (SDA) automatiza a criação e a configuração de uma experiência de implantação recomendada pela Microsoft usando as ferramentas de implantação gratuitas da Microsoft.

Reprojetado em abril de 2020 para simplificar e automatizar a implantação de imagens de superfície em um ambiente corporativo, a ferramenta SDA permite que você crie uma imagem do Windows "de fábrica" que você pode personalizar para seus requisitos organizacionais.

A ferramenta de fonte aberta SDA orientada por script aproveita o kit de avaliação e implantação do Windows (ADK) para Windows 10, facilitando a criação de imagens do Windows (WIM) em ambientes de teste ou produção. Se o ADK mais recente ainda não estiver instalado, ele será baixado e instalado ao executar a ferramenta SDA.

A imagem resultante corresponde à configuração de imagens de recuperação bare-metal (BMR), sem nenhum aplicativo pré-instalado, como o Microsoft Office ou o aplicativo da superfície da UWP.

## Requisitos

1. Uma unidade USB Thumb com pelo menos 16 GB de tamanho. A unidade USB será formatada.
2. Um arquivo. ISO com o Windows 10 pro ou o Windows 10 Enterprise. A ferramenta de criação de mídia pode ser usada para baixar o Windows 10 e criar um arquivo. ISO. Para obter mais informações, consulte [baixar o Windows 10](https://www.microsoft.com/software-download/windows10).
3. Um dispositivo com o Windows 10, versão 2004 ou posterior, com acesso à Internet.

Consulte a seção [pré-requisitos](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) do documento README para obter uma lista detalhada dos requisitos.

## Como executar o SDA

**Para executar o SDA:**

1. Acesse [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) no github. 
2. Examine a documentação do [Leiame](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .
3. Na página [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) , clique no botão **código** e, em seguida, selecione **baixar CEP** para salvar os arquivos localmente em seu computador.
4. Clique com o botão direito do mouse no arquivo. zip e, em seguida, clique em **Propriedades**.
5. Na guia **geral** , marque a caixa de seleção **desbloquear** e clique em **OK**.
6. Extraia o arquivo. zip para um local em seu disco rígido (por exemplo: C:\SDA).
7. Abra um prompt do Windows PowerShell elevado e defina ExecutionPolicy para a sessão atual como Irrestrito.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. Execute o script SDA especificando os parâmetros para o seu ambiente. O script pode ser usado para criar imagens para instalar o Windows 10 em uma variedade de dispositivos Surface. Para obter uma lista completa dos dispositivos compatíveis, consulte a [Descrição do parâmetro Device](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) no artigo SDA README. 

    Por exemplo, o comando a seguir criará uma unidade USB inicializável que pode ser usada para [instalar o Windows 10 no Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    Exemplo de saída de script abaixo.

   ![Ferramenta de aceleração de implantação de superfície em execução](images/sda1.png)

    O script exigirá cerca de 45 minutos para ser executado, mas pode demorar mais, dependendo da CPU e dos recursos de disco disponíveis. 

    Depois de criar uma imagem do Windows, o script solicitará que você insira e confirme a letra da unidade USB. A unidade USB será formatada, configurada como inicializável, e os arquivos copiados para habilitar a instalação da imagem personalizada do Windows 10 para dispositivos Surface.

9. Insira a unidade USB no dispositivo em que você deseja instalar o Windows 10 e reiniciar para começar a instalar o Windows 10. A inicialização USB deve estar habilitada no BIOS, o que pode exigir que você Desabilite temporariamente a inicialização segura.

> [!IMPORTANT]
> A inicialização a partir da unidade USB iniciará imediatamente a instalação do Windows 10. Verifique se o seu dispositivo está pronto antes de inserir o USB e reiniciar. 

## Links relacionados

 - [Ferramenta de implantação de imagem de fonte aberta liberada no GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [Baixar e instalar o Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
