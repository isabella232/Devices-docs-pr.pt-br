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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831164"
---
# Criar pacotes de provisionamento para o Surface Hub 2S

Você pode usar o Windows Configuration designer (WCD) para criar pacotes de provisionamento para automatizar o processo de implantação do Surface Hub 2S. Use pacotes de provisionamento para adicionar certificados, configurar proxies, configurar administradores de dispositivos e contas de dispositivos. Você também pode usar pacotes de provisionamento juntamente com um arquivo de configuração para implantar vários hubs de superfície com um único pen drive USB.

### Instalar o Designer de Configuração do Windows

Instale o designer de configuração do Windows a partir do kit de avaliação e implantação do Windows (ADK) para Windows 10. Baixe e instale o [ADK para Windows 10, versão 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542). Para obter mais informações, consulte [baixar e instalar o Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### Adicionar certificados

Você pode importar certificados de autoridade de certificação para o Surface Hub 2S.
Para adicionar certificados ao Surface Hub 2S, você precisa de uma cópia de cada certificado como X. 509 no formato. cer. Você não pode importar. CRT,. pfx, ou outros formatos de contêiner. Os certificados devem ser importados para o designer de configuração do Windows e organizados por hierarquia:

 ![Adicionar certificados](images/sh2-wcd.png)

### Configurar proxy durante OOBE

No designer de configuração do Windows, vá para a guia Configurar configurações de proxy e insira as configurações apropriadas, conforme mostrado a seguir.

 ![Configurar as definições do proxy](images/sh2-proxy.png) 

> [!NOTE]
> Ao definir as configurações de proxy, desative **as configurações de detecção automática** se você pretende usar um script de instalação ou um servidor proxy. Você pode usar um script de configuração *ou* um servidor proxy, não ambos.

### Hub de superfície do associado 2S com o Azure Active Directory

Você pode afiliar o Surface Hub 2S ao Azure Active Directory usando um pacote de provisionamento: como um administrador global do Azure Active Directory, você pode ingressar em grandes números de dispositivos novos do Windows para o Azure Active Directory e o Intune usando um token em massa.

Para criar um token em massa, dê a ele um nome amigável, configure a data de expiração (máximo de 30 dias) e use as credenciais de administrador para adquirir o token conforme mostrado abaixo:

 ![Configurar administradores de dispositivo](images/sh2-token.png) <br><br>
 ![Configurar administradores de dispositivo](images/sh2-token2.png) <br><br>
 ![Configurar administradores de dispositivo](images/sh2-token3.png) <br><br>

### Provisionando vários dispositivos (arquivo. csv)

Além do pacote de provisionamento, você pode usar um arquivo de configuração do Surface Hub para facilitar ainda mais a configuração de seus dispositivos. Um arquivo de configuração do Surface Hub contém uma lista de contas de dispositivo e nomes amigáveis para a projeção sem fio. Durante a primeira execução, você tem a opção de escolher uma conta de dispositivo e um nome amigável a partir de um arquivo de configuração.

### Para criar um arquivo de configuração do Surface Hub

1. Usando o Microsoft Excel ou outro editor de CSV, crie um arquivo CSV chamado: **SurfaceHubConfiguration.csv**
2. Insira uma lista de contas de dispositivo e nomes amigáveis neste formato:

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. Salve o arquivo na raiz da unidade do Thumb USB em que você copiou o arquivo PPKG.

    ![Exemplo de arquivo de configuração](images/sh2-config-file.png)
