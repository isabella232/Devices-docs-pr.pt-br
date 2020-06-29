---
title: Usar o nome de domínio totalmente qualificado com o Surface Hub
description: Solucione problemas comuns, incluindo problemas de instalação e erros do Exchange ActiveSync.
keywords:
- Solucionar problemas comuns
- problemas de instalação
- Erros do Exchange ActiveSync
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830315"
---
# Configurar o nome de domínio para o Skype for Business

Existem alguns cenários em que você precisa especificar o nome de domínio do seu Skype for Business Server:
- **Vários sufixos DNS** – quando a infraestrutura do Skype for Business tem namespaces separados de tal forma que um ou mais servidores tenham um sufixo DNS que não corresponda ao sufixo do SIP (endereço de entrada) do Skype for Business.  
- **Os sufixos do Skype for Business e do Exchange são diferentes** – quando o sufixo do endereço de entrada para o Skype for Business difere do sufixo do endereço do Exchange usado para a conta do dispositivo.
- **Trabalhando com certificados** – grandes organizações com servidores do Skype for Business local geralmente usam certificados com sua própria CA (autoridade de certificação raiz). É comum que o domínio da CA seja diferente do domínio do Skype for Business Server, que faz com que o certificado não seja confiável e que haja falha na entrada.  O Skype precisa saber o nome de domínio do certificado para configurar uma relação de confiança. As empresas geralmente usam a Política de Grupo para enviar isso à área de trabalho do Skype, mas não há suporte para a Política de grupo no Surface Hub.

**Para configurar o nome de domínio do Skype for Business Server**</br>
1. No Surface Hub, abra **Configurações**.
2. Clique em **Surface Hub**e, em seguida, clique em **Chamadas e áudio**. 
3. Em **Configuração do Skype for Business**, clique em **Configurar nome de domínio**. 
4. Digite o nome de domínio do Skype for Business Server e clique em **Ok**. 
   > [!TIP]
   > Você pode digitar vários nomes de domínio, separados por vírgulas. <br> Por exemplo: lync.com, outlook.com, lync.glbdns.microsoft.com

    ![Adicionar FQDN para configurações do Skype for Business](images/system-settings-add-fqdn.png)
