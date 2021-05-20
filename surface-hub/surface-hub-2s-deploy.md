---
title: Criar pacotes de provisionamento para o Surface Hub 2S
description: Esta página descreve como implantar o Surface Hub 2S usando pacotes de provisionamento e outras ferramentas.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576861"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a>Criar pacotes de provisionamento para o Surface Hub 2S

Você pode usar Windows Configuration Designer (WCD) para criar pacotes de provisionamento para automatizar a implantação do Surface Hub 2S. Use pacotes de provisionamento para adicionar certificados, configurar proxies, configurar administradores de dispositivos e contas de dispositivo. Você também pode usar pacotes de provisionamento juntamente com um arquivo de configuração para implantar vários Surface Hubs com uma única unidade de pen drive USB.

### <a name="install-windows-configuration-designer"></a>Instalar o Designer de Configuração do Windows

Instale Windows Designer de Configuração Windows ADK (Kit de Avaliação e Implantação) Windows 10. Baixe e instale o [ADK para Windows 10, versão 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542). Para mais informações, consulte [Baixe e instale o Kit de Avaliação e Implantação do Windows](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### <a name="add-certificates"></a>Adicionar certificados

Você pode importar certificados de Autoridade de Certificação para Surface Hub 2S.
Para adicionar certificados ao Surface Hub 2S, você precisa de uma cópia de cada certificado como X.509 no formato .cer. Não é possível importar .crt, .pfx ou outros formatos de contêiner. Os certificados devem ser importados para Windows Designer de Configuração e organizados pela hierarquia:

> [!div class="mx-imgBorder"]
> ![Adicionar certificados](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a>Configurar proxy durante o OOBE

Em Windows Designer de Configuração, vá para a guia Configurar configurações de proxy e insira as configurações apropriadas, conforme mostrado abaixo.

> [!div class="mx-imgBorder"]
> ![Configurar as definições do proxy](images/sh2-proxy.png) 

> [!NOTE]
> Ao configurar configurações de **** proxy, desligue Automaticamente as configurações de detecção se você pretende usar um script de instalação ou um servidor proxy. Você pode usar um script de instalação *ou um* servidor proxy, não ambos.

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a>Afiliada Surface Hub 2S com Azure Active Directory

Você pode associar o Surface Hub 2S ao Azure Active Directory usando um pacote de provisionamento: como administrador global do Azure Active Directory, você pode associar um grande número de novos dispositivos Windows ao Azure Active Directory e ao Intune usando um token em massa.

Para criar um token em massa, dê um nome amigável, configure a data de expiração (máximo de 30 dias) e use suas credenciais de Administrador para adquirir o token, conforme mostrado abaixo:

> [!div class="mx-imgBorder"]
> ![Configurar administradores de dispositivos exemplo 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Configurar administradores de dispositivos exemplo 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Configurar administradores de dispositivos exemplo 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a>Provisionamento de vários dispositivos (.csv arquivo)

Além do pacote de provisionamento, você pode usar um arquivo de configuração Surface Hub para facilitar ainda mais a configuração de seus dispositivos. Um Surface Hub de configuração contém uma lista de contas de dispositivo e nomes amigáveis para projeção sem fio. Durante a primeira execução, você tem a opção de escolher uma conta de dispositivo e um nome amigável de um arquivo de configuração.

### <a name="to-create-a-surface-hub-configuration-file"></a>Para criar um arquivo Surface Hub configuração

1. Usando Microsoft Excel ou outro editor CSV, crie um arquivo CSV chamado: **SurfaceHubConfiguration.csv**

2. Insira uma lista de contas de dispositivo e nomes amigáveis neste formato:

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. Salve o arquivo na raiz da unidade de polegar USB onde você copiou o arquivo PPKG.

    > [!div class="mx-imgBorder"]
    > ![Exemplo de arquivo de configuração](images/sh2-config-file.png)
