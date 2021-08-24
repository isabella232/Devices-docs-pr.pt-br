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
ms.openlocfilehash: 48f89e8929bdb9d075bea988558fea234da5bbd2
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911416"
---
# <a name="microsoft-surface-deployment-accelerator"></a>Microsoft Surface Deployment Accelerator

O Microsoft Surface Deployment Accelerator (SDA) automatiza a criação e a configuração de uma experiência de implantação recomendada pela Microsoft usando ferramentas de implantação gratuitas da Microsoft.

Redesenhada em abril de 2020 para simplificar e automatizar a implantação de imagens do Surface em um ambiente corporativo, a ferramenta SDA permite que você crie uma imagem "de fábrica" Windows que você pode personalizar para seus requisitos organizacionais.

A ferramenta SDA orientada por script e de código aberto utiliza o ADK (Kit de Avaliação e Implantação) do Windows para Windows 10, facilitando a criação de imagens wi-Windows (WIM) em ambientes de teste ou produção. Se o ADK mais recente ainda não estiver instalado, ele será baixado e instalado ao executar a ferramenta SDA.

A imagem resultante corresponde de perto à configuração de imagens de Recuperação de Bare Metal (BMR), sem qualquer aplicativo pré-instalado, como o Microsoft Office ou o aplicativo UWP do Surface.

## <a name="requirements"></a>Requisitos

1. Uma unidade de pen drive de pelo menos 16 GB de tamanho. A unidade USB será formatada.
2. Um arquivo .iso com Windows 10 Pro ou Windows 10 Enterprise. A ferramenta de criação de mídia pode ser usada para baixar Windows 10 e criar um arquivo .iso. Para obter mais informações, [consulte Download Windows 10](https://www.microsoft.com/software-download/windows10).
3. Um dispositivo executando Windows 10, versão 2004 ou posterior com acesso à Internet.

Consulte a [seção Pré-requisitos](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) do documento README para ver uma lista detalhada de requisitos.

## <a name="how-to-run-the-sda"></a>Como executar o SDA

**Para executar o SDA:**

1. Vá para [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) no GitHub. 
2. Revise a [documentação README.](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md)
3. Na página [SurfaceDeploymentAccelerator,](https://github.com/microsoft/SurfaceDeploymentAccelerator) **** clique no botão Código e selecione **Baixar ZIP** para salvar os arquivos localmente em seu computador.
4. Clique com o botão direito do mouse no arquivo .zip e clique em **Propriedades**.
5. Na guia **Geral,** selecione a caixa de **seleção Desbloquear** e clique em **OK**.
6. Extraia o .zip para um local no disco rígido (ex: C:\SDA).
7. Abra um prompt Windows PowerShell e de definir ExecutionPolicy para a sessão atual como Irrestrita.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. Execute o script SDA especificando parâmetros para seu ambiente. O script pode ser usado para criar imagens para instalar Windows 10 em uma variedade de dispositivos Surface. Para uma lista completa de dispositivos com suporte, consulte a descrição do parâmetro [Device](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) no artigo README do SDA. 

    Por exemplo, o comando a seguir criará uma unidade USB inicializável que pode ser usada para instalar o Windows 10 [no Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    A saída de script de exemplo está abaixo.

   ![Executando a ferramenta Acelerador de Implantação do Surface.](images/sda1.png)

    O script exigirá cerca de 45 minutos para ser executado, mas pode demorar mais, dependendo dos recursos de CPU e disco disponíveis. 

    Depois de criar uma Windows, o script solicitará que você insira e confirme a letra de unidade da unidade USB. Em seguida, a unidade USB será formatada, configurada como inicializável e os arquivos copiados para habilitar a instalação da imagem Windows 10 personalizada para dispositivos Surface.

9. Insira a unidade USB no dispositivo onde você deseja instalar Windows 10 e reiniciar para começar a instalar Windows 10. A inicialização USB deve estar habilitada no BIOS, o que pode exigir que você desabilite temporariamente a Inicialização Segura.

> [!IMPORTANT]
> A inicialização da unidade USB começará imediatamente a instalar Windows 10. Verifique se o dispositivo está pronto antes de inserir a USB e reiniciar. 

## <a name="related-links"></a>Links relacionados

 - [Ferramenta de implantação de imagem de código aberto lançada no GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [Baixar e instalar o Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
