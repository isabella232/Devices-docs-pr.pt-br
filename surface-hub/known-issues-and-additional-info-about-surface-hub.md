---
title: Problemas conhecidos e informações adicionais sobre o Microsoft Surface Hub
description: Descreve problemas conhecidos com o Microsoft Surface Hub.
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: superfície, Hub, problemas
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830460"
---
# Problemas conhecidos e informações adicionais sobre o Microsoft Surface Hub

Estamos ouvindo. A qualidade é uma prioridade superior, e queremos mantê-lo informado sobre problemas que afetam os clientes. Veja a seguir alguns problemas conhecidos do Microsoft Surface Hub:

- **O Skype for Business não está usando proxy para tráfego de mídia com o RS2**
<br/>Para alguns usuários do Surface Hub que estiverem atrás de um proxy, o Skype for Business não usará o servidor proxy para mídia. No entanto, o Surface Hub poderá entrar na conta. Recebemos seus comentários e estamos cientes do problema de tráfego de mídia quando você estiver usando o proxy. Estamos investigando ativamente esse problema e lançaremos correções assim que uma solução for identificada e testada. 

- **Para dispositivos ingressados no AAD, quando um usuário tenta entrar em "minhas reuniões & arquivos", o Surface Hub relata que não há conexão à Internet**
<br/>Estamos cientes de um conjunto de problemas que afetam a entrada e o acesso a documentos no Surface Hub. Estamos investigando ativamente esses problemas. Como solução alternativa até que uma resolução seja liberada, os clientes podem redefinir seus dispositivos e configurar o Hub para usar uma conta de administrador local. Após a reconfiguração para usar a conta de administrador local, "minhas reuniões e arquivos" funcionará conforme o esperado.
- **Logon único quando o Azure AD ingressou**
<br/>O Surface Hub foi projetado para espaços públicos, que afeta a maneira como as credenciais do usuário são armazenadas. Por isso, há limitações no momento em como o logon único funciona quando os dispositivos são associados ao Azure AD. A Microsoft está ciente da limitação e está investigando ativamente as opções de resolução.
- **O Miracast sobre a projeção de infraestrutura para Surface Hub falha se o Surface Hub tiver um caractere de ponto (.) no nome amigável**
<br/>Os usuários do Surface Hub podem enfrentar problemas para projetar seus dispositivos se o nome amigável incluir um ponto ou ponto no nome (.)--por exemplo, "conf. Room42". Para contornar o problema, altere o nome amigável do Hub em **configurações**  >  **Hub Surface Hub**  >  **About**e reinicie o dispositivo. A Microsoft está trabalhando em uma solução para esse problema.