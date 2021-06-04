---
title: Habilitar PEAP, EAP-FAST e Cisco LEAP em dispositivos Surface (Surface)
description: Saiba como habilitar o suporte para protocolos PEAP, EAP-FAST ou Cisco LEAP no dispositivo Surface.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: rede, sem fio, dispositivo, implantação, autenticação, protocolo
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830595"
---
# Habilitar PEAP, EAP-FAST e Cisco LEAP em dispositivos Surface


Saiba como habilitar o suporte para protocolos PEAP, EAP-FAST ou Cisco LEAP no dispositivo Surface.

Se usa PEAP, EAP-FAST ou Cisco LEAP em sua rede corporativa, você provavelmente já sabe que esses três protocolos de autenticação sem fio não têm suporte incluído nos dispositivos Surface. Alguns usuários podem descobrir isso ao tentarem se conectar à rede sem fio; outros podem descobri-lo quando não conseguem acessar recursos dentro da rede, como compartilhamentos de arquivos e sites internos. Para obter mais informações, confira [Protocolo de Autenticação Extensível](https://technet.microsoft.com/network/bb643147).

Você pode adicionar suporte para cada protocolo executando um pequeno pacote MSI por meio de um pen drive ou um compartilhamento de arquivos. Para as organizações que desejam habilitar o suporte a EAP em seus dispositivos Surface, o formato do pacote MSI oferece suporte à implantação com muitas ferramentas de gerenciamento e implantação, como o Microsoft Deployment Toolkit (MDT) e o Microsoft Endpoint Configuration Manager.

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a>Baixar arquivos de instalação para PEAP, EAP-FAST ou Cisco LEAP


Você pode baixar os arquivos de instalação MSI para PEAP, EAP-FAST ou Cisco LEAP em um único arquivo zip do Centro de Download da Microsoft. Para baixar este arquivo, acesse a página [Ferramentas do Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) no Centro de Download da Microsoft, clique em **Baixar** e selecione o arquivo **Cisco EAP-Supplicant Installer.zip**.

##  <a name="deploy-peap,-eap-fast,-or-cisco-leap-with-mdt"></a>Implantar PEAP, EAP-FAST ou Cisco LEAP com o MDT


Se você já está executando uma implantação do Windows em dispositivos Surface em sua organização, é rápido e fácil adicionar os arquivos de instalação de cada protocolo a seu compartilhamento de implantação e configurar a instalação automática durante a implantação. Você pode até mesmo configurar uma sequência de tarefas que atualiza dispositivos Surface implantados anteriormente para dar suporte a esses protocolos usando o mesmo processo.

Para habilitar o suporte a PEAP, EAP-FAST ou Cisco LEAP em dispositivos Surface recém-implantados, siga estas etapas:

1.  Baixe e extraia os arquivos de instalação de cada protocolo para pastas separadas em um local de fácil acesso.

2.  Abra o MDT Deployment Workbench e expanda seu compartilhamento de implantação para a pasta **Aplicativos**.

3.  Selecione **Novo Aplicativo** no painel **Ação**.

4.  Escolha **Aplicativo com arquivos de origem** para copiar os arquivos MSI para o Compartilhamento de Implantação.

5.  Selecione a pasta que você criou na etapa 1 para o protocolo desejado.

6.  Nomeie a pasta no compartilhamento de implantação em que os arquivos de instalação serão armazenados.

7.  Especifique a linha de comando para implantar o aplicativo:

    -   Para PEAP, use **EAP-PEAP.msi /qn /norestart**.

    -   Para LEAP, use **EAP-LEAP.msi /qn /norestart**.

    -   Para EAP-FAST, use **EAP-FAST.msi /qn /norestart**.

8.  Use as opções padrão para concluir o Assistente para Criar Novo Aplicativo.

9.  Repita as etapas 3 a 8 para cada protocolo desejado.

Depois que você executar essas etapas para importar os três pacotes MSI como aplicativos no MDT, eles estarão disponíveis para seleção na página Aplicativos do Assistente de Implantação do Windows. Embora, em alguns cenários de implantação simples, isso possa ser suficiente para que os técnicos selecionem cada pacote no momento da implantação, não é recomendado. Essa prática introduz a possibilidade de que um técnico possa tentar aplicar esses pacotes a computadores que não dispositivos Surface ou que um dispositivo Surface possa ser implantado sem suporte a EAP devido a erros humanos.

Para ocultar esses aplicativos na página Instalar Aplicativos, marque a caixa de seleção **Ocultar este aplicativo no Assistente de Implantação** nas propriedades de cada aplicativo. Depois que os aplicativos estiverem ocultos, não serão exibidos como aplicativos opcionais durante a implantação. Para implantá-los em sua sequência de tarefas de implantação do Surface, eles devem ser definidos explicitamente para a instalação por meio de uma etapa separada na sequência de tarefas.

Para especificar o(s) protocolo(s) explicitamente, siga estas etapas:

1.  Abra as propriedades de sua sequência de tarefa de implantação do Surface no MDT Deployment Workbench.

2.  Na guia **Sequência de Tarefas**, selecione a etapa **Instalar Aplicativos** em **Restauração de Estado**. Ela geralmente é encontrada entre as etapas pré-aplicativo e pós-aplicativo do Windows Update.

3.  Use o botão **Adicionar** para criar uma nova etapa **Instalar Aplicativo** da categoria **Geral**.

4.  Selecione **Instalar um único aplicativo** na etapa da guia **Propriedades**.

5.  Selecione o protocolo EAP desejado na lista.

6.  Repita as etapas 2 a 5 para cada protocolo desejado.

##  <a name="deploy-peap,-eap-fast,-or-cisco-leap-with-configuration-manager"></a>Implantar PEAP, EAP-FAST ou Cisco LEAP com o Gerenciador de Configurações


Para organizações que gerenciam dispositivos Surface com o Gerenciador de Configurações, é ainda mais fácil implantar o suporte a PEAP, EAP-FAST ou Cisco LEAP em dispositivos Surface. Basta importar cada arquivo MSI como um aplicativo da Biblioteca doe Software e configurar uma implantação para sua coleção de dispositivos Surface.

Para obter mais informações sobre como implantar aplicativos com o Gerenciador de Configurações, confira [Como criar aplicativos no Gerenciador de Configurações](https://technet.microsoft.com/library/gg682159.aspx) e [Como implantar aplicativos no Gerenciador de Configurações](https://technet.microsoft.com/library/gg682082.aspx).

 

 





