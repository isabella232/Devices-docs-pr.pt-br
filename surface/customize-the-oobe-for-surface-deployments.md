---
title: Personalizar a configuração inicial pelo usuário para implantações do Surface
description: Este artigo o orientará durante o processo de personalizar a configuração inicial pelo usuário do Surface para usuários finais em sua organização.
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: implantar, personalizar, automatizar, rede, Caneta, emparelhar, inicialização
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 97cc262d803875a76427d04c8f9b70547152f895
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830519"
---
# Personalizar a configuração inicial pelo usuário para implantações do Surface

Este artigo descreve a personalização da experiência inicial pelo usuário da superfície para os usuários finais de sua organização.

Em uma implantação do Windows, é prática comum personalizar a experiência do usuário para a primeira inicialização dos computadores implantados — a configuração inicial pelo usuário, ou tela de apresentação.

>[!NOTE]
>A configuração inicial pelo usuário muitas vezes também é usada para descrever a fase ou o passo de configuração da instalação do Windows durante o qual a experiência do usuário é exibida. Para obter mais informações sobre a fase da configuração inicial pelo usuário da instalação, confira [Como os passos de configuração funcionam](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx).

Em alguns cenários, convém fornecer automação completa para garantir que, no fim de uma implantação, os computadores estejam prontos para uso sem interação do usuário. Em outros cenários, convém deixar elementos-chave da experiência para que os usuários executem ações necessárias ou selecionem dentre opções importantes. Para administradores que implantam em dispositivos Surface, cada um desses cenários apresenta um desafio exclusivo a ser superado.

> [!NOTE]
> Este artigo não se aplica ao Surface Pro X. Para obter mais informações, consulte [implantação, gerenciamento e manutenção do Surface Pro X](surface-pro-arm-app-management.md)

Este artigo fornece um resumo dos cenários em que uma implantação pode exigir etapas adicionais. Ele também fornece as informações necessárias para garantir que a experiência desejada seja atingida em qualquer dispositivo Surface recém-implantado. Este artigo se destina a administradores que estão familiarizados com o processo de implantação e com conceitos como arquivos de resposta e [imagens de referência](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).

>[!NOTE]
>Embora a fase OOBE da instalação ainda seja executada durante uma implantação com uma solução de implantação automatizada, como o kit de ferramentas de implantação da [Microsoft (MDT)](https://go.microsoft.com/fwlink/p/?LinkId=618117) ou implantação do sistema operacional Microsoft Endpoint Configuration Manager (OSD), ela é automatizada pelas configurações fornecidas no assistente de implantação e na sequência de tarefas. Para saber mais, confira:<br/>
>- [Implantar o Windows 10 com o Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)
>- [Implantar o Windows 10 com o System Center 2012 R2 Configuration Manager](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-system-center-2012-r2-configuration-manager)

 

##  <a name="scenario-1:-wireless-networking-in-oobe-with-mdt-2013"></a>Cenário 1: rede sem fio na configuração inicial pelo usuário com MDT 2013


Quando um adaptador de rede sem fio está presente na tela de apresentação, a página **Ingressar em uma rede sem fio** é exibida, solicitando que um usuário se conecte a uma rede sem fio. Essa página não é ocultada automaticamente pelas tecnologias de implantação, incluindo o MDT 2013. Portanto, ela será exibida mesmo quando uma implantação estiver configurada para automação completa.

Para garantir que uma implantação automatizada não seja interrompida por essa página, a página deve ser ocultada definindo-se uma configuração adicional no arquivo de resposta, **HideWirelessSetupInOOBE**. Você pode encontrar informações adicionais sobre a configuração **HideWirelessSetupInOOBE** na [Referência de instalação autônoma do Windows](https://technet.microsoft.com/library/ff716213.aspx).

##  <a name="scenario-2:-surface-pen-pairing-in-oobe"></a>Cenário 2: emparelhamento da Caneta Surface na tela de apresentação


Quando você retira da embalagem um Surface Pro 3, um Surface Pro 4, um Surface Book ou um Surface Studio e o inicia, a tela de apresentação da imagem de fábrica inclui um prompt que o solicita a emparelhar com o dispositivo a Caneta Surface incluída. Esse prompt é fornecido apenas pela imagem de fábrica que acompanha o dispositivo e não é incluído em outras imagens usadas para implantação, como a mídia de instalação do Windows Enterprise baixada do Centro de Serviços de Licenciamento por Volume. Como o emparelhamento da Caneta Surface Bluetooth fora dessa experiência requer que você entre no Painel de Controle ou nas Configurações do computador e emparelhe manualmente um dispositivo Bluetooth, convém deixar que os usuários ou um técnico usem esse prompt para executar a operação de emparelhamento.

Para fornecer a experiência de emparelhamento da Caneta Surface de fábrica na configuração inicial pelo usuário, primeiro você deve copiar quatro arquivos da imagem do Surface de fábrica para a imagem de referência. Você pode copiar esses arquivos para o ambiente de referência antes de capturar a imagem de referência ou pode adicioná-los mais tarde usando o DISM (Gerenciamento e Manutenção de Imagens de Implantação) para montar a imagem. Os quatro arquivos necessários são:

-   %windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png

>[!NOTE]
>Você deve copiar os arquivos de uma imagem de fábrica para o mesmo modelo do dispositivo Surface no qual pretende implantar. Por exemplo, você deve usar os arquivos de um Surface Pro 7 para implantar na Surface Pro 7 e os arquivos do catálogo de superfície 2 para implantar o catálogo de superfície 2, mas não deve usar os arquivos de um Surface Pro 7 para implantar o Surface Book ou o Surface pro 6.

 

O processo passo a passo para adicionar esses arquivos necessários a uma imagem é descrito em [Dicas de implantação da Caneta Surface Pro 3 e do OneNote](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/). Essa postagem de blog também inclui dicas para garantir que as atualizações necessárias para a Experiência de Anotações Rápidas da Caneta Surface sejam instaladas, o que permite aos usuários enviar anotações ao OneNote com um único clique.

 

 





