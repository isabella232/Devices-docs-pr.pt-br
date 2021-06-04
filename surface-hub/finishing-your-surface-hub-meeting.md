---
title: Encerrar sessão - encerramento de uma reunião do Surface Hub
description: Para encerrar uma reunião do Surface Hub, toque em Encerrar sessão. O Surface Hub limpa o estado do aplicativo, o estado do sistema operacional e a interface do usuário para que o Surface Hub fique pronto para a próxima reunião.
keywords: Terminei, encerrar reunião do Surface Hub, concluir reunião do Surface Hub, limpar reunião do Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830661"
---
# Encerrar uma reunião do Surface Hub com Encerrar sessão
O Surface Hub é um dispositivo de colaboração projetado para ser usado em espaços de reunião por grupos de pessoas diferentes. No final de uma reunião, os usuários podem tocar em **Encerrar sessão** para apagar dados confidenciais e preparar o dispositivo para a próxima reunião. O Surface Hub limpará ou redefinirá os seguintes estados:
- Aplicativos
- Sistema operacional
- Interface do usuário

Este tópico explica o que **Encerrar sessão** redefine para cada um destes estados.

##  <a name="applications"></a>Aplicativos
Quando você inicia aplicativos no Surface Hub, eles são armazenados na memória, e os dados são armazenados no nível do aplicativo. Os dados ficam disponíveis para todos os usuários durante aquela sessão (ou reunião) até que a data seja removida ou substituída. Quando **Encerrar sessão** é selecionado, o estado do aplicativo do Surface Hub é limpo pelo fechamento de aplicativos, exclusão do histórico do navegador, redefinição de aplicativos e remoção de registros do Skype.

###  <a name="close-applications"></a>Fechar aplicativos
O Surface Hub fecha todas as janelas visíveis, incluindo aplicativos Win32 e Plataforma Universal do Windows (UWP). O estágio de fechamento de aplicativos usa o modo de exibição multitarefa para consultar as janelas visíveis. Janelas do Win32 que não fecharem dentro de um determinado período serão fechadas usando o **TerminateProcess**. 
   
###  <a name="delete-browser-history"></a>Apagar histórico do navegador
O Surface Hub usa o recurso Excluir histórico do navegador (DBH) na Borda para limpar o histórico da Borda e dados em cache. Isso se assemelha a como um usuário pode limpar o histórico do navegador manualmente, mas **Encerrar sessão** também limpa os estados do aplicativo, e os dados são removidos antes do início da próxima sessão ou reunião. 
 
###  <a name="reset-applications"></a>Redefinir aplicativos
**Encerrar sessão** redefine o estado de cada aplicativo que é instalado no Surface Hub. A redefinição de um aplicativo limpa todas as tarefas em segundo plano, dados de aplicativos, notificações e caixas de diálogo de consentimento do usuário. Os aplicativos voltam ao estado da primeira execução para as próximas pessoas que usarem o Surface Hub.  
 
###  <a name="remove-skype-logs"></a>Remover registros do Skype
O Skype não armazena informações de identificação pessoal no Surface Hub. As informações são armazenadas no serviço Skype para atender às orientações existentes do Skype for Business. As informações de registro do Skype locais são os únicos dados removidos quando **Encerrar sessão** é selecionado. Isso inclui os registros da plataforma de clientes de comunicações unificada (UCCP) e de mídia.   

##  <a name="operating-system"></a>Sistema operacional
O sistema operacional hospeda uma variedade de informações sobre o estado das sessões que precisa ser limpo após cada reunião no Surface Hub. 

###  <a name="file-system"></a>Sistema de arquivos
Os participantes da reunião têm acesso a um conjunto limitado de diretórios no Surface Hub. Quando **Encerrar sessão** é selecionado, o Surface Hub limpa estes diretórios:<br>
- Música
- Vídeos
- Documentos
- Imagens
- Downloads

O Surface Hub também limpa esses diretórios, já que muitos aplicativos costumam escrever para eles:
- Área de trabalho
- Favoritos
- Recentes
- Documentos Públicos
- Músicas Públicas
- Vídeos Públicos
- Downloads Públicos

###  <a name="credentials"></a>Credenciais
As credenciais de usuário que são armazenadas em **TokenBroker**, **PasswordVault** ou **Gerenciador de Credenciais** são apagadas quando você toca em **Encerrar sessão**.

##  <a name="user-interface"></a>Interface do usuário
Os ajustes da interface do usuário (IU) voltam aos valores padrão quando **Encerrar sessão** é selecionado. 

###  <a name="ui-items"></a>Itens de interface do usuário
- Redefinir Ações rápidas para o estado padrão
- Limpar Notificações do sistema
- Redefinir níveis de volume
- Redefinir a largura da barra lateral
- Redefinir o layout do modo tablet
- Como fazer o usuário sair de reuniões e de arquivos do Office 365

###  <a name="accessibility"></a>Acessibilidade
Aplicativos e recursos de acessibilidade retornam aos ajustes padrão quando **Encerrar sessão** é selecionado.
- Teclas de filtragem
- Alto contraste
- Teclas de aderência
- Teclas de alternância
- Teclas do mouse
- Lupa
- Narrador

###  <a name="clipboard"></a>Área de Transferência
A área de transferência é limpa para remover dados que foram copiados para a área de transferência durante a sessão. 

##  <a name="faq"></a>Perguntas frequentes
**O que acontece se eu esquecer de tocar em Encerrar sessão no final de uma reunião e outra pessoa usar o Surface Hub depois?**<br>
O Surface Hub apaga o conteúdo da reunião somente quando os usuários tocam em **Encerrar sessão**. Se você sair da reunião sem tocar em **Encerrar sessão**, o dispositivo retornará à tela de boas-vindas após algum tempo. Na tela de boas-vindas, os usuários terão a opção de continuar a sessão anterior ou iniciar uma nova. Você também pode desabilitar a capacidade de retomar uma sessão se **Encerrar sessão** não for pressionado.

**Os documentos podem ser recuperados?**<br> A remoção de arquivos do disco rígido com a seleção do **Encerrar sessão** é exatamente igual a qualquer outra exclusão de arquivos da unidade de disco rígido. Softwares de terceiros talvez possam recuperar dados da unidade de disco rígido, mas a recuperação de arquivos não é um recurso com suporte no Surface Hub. Para evitar a perda de dados, salve sempre os dados necessários antes de sair de uma reunião.

**As ações de limpeza da opção Encerrar sessão estão em conformidade com o padrão de limpeza e remoção do Departamento de Defesa dos EUA: DoD 5220.22-M?**<br>
Não. Atualmente, as ações de limpeza de **Encerrar sessão** não são compatíveis com esse padrão.  
  
