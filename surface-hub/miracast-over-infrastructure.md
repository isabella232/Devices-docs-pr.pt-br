---
title: Miracast em rede sem fio existente ou LAN
description: Windows 10 permite que você envie um fluxo de Miracast por uma rede local.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/24/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d63b3de0f76cb70fe86fff246d82cbe166278461
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831171"
---
# Miracast em infra-estrutura

No Windows 10, versão 1703, a Microsoft estendeu a capacidade de enviar um fluxo de Miracast por uma rede local, e não por um link direto sem fio. Essa funcionalidade é baseada no [Miracast via protocolo de estabelecimento de Conexão de infraestrutura (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx).

O Miracast sobre infraestrutura oferece vários benefícios:

- O Windows automaticamente detecta quando o envio do fluxo de vídeo sobre esse caminho é aplicável.
- O Windows escolherá esta rota somente se a conexão for via Ethernet ou por uma rede Wi-Fi protegida.
- Os usuários não precisam mudar como eles se conectam a um receptor Miracast. Eles usam a mesma experiência do usuário para conexões de Miracast padrão.
- Nenhuma mudança no hardware do computador ou drivers atuais sem fio é necessária.
- Ele funciona bem com o hardware mais antigo sem fio que não é otimizado para Miracast por Wi-Fi Direct.
- Ele utiliza uma conexão existente que reduz o tempo para se conectar e fornece um fluxo bastante estável.


## Como funciona

Os usuários tentam se conectar a um receptor Miracast por meio de seu adaptador Wi-Fi como antes. Quando a lista dos receptores Miracast é preenchida, o Windows 10 identificará se o receptor é capaz de dar suporte a uma conexão ao longo da infraestrutura. Quando o usuário seleciona um receptor Miracast, o Windows 10 tenta resolver o nome do host do dispositivo por meio do padrão DNS, bem como por meio de multicast DNS (mDNS). Se o nome não puder ser resolvido por meio de qualquer método DNS, o Windows 10 se voltará para estabelecer a sessão de Miracast usando a conexão direta de Wi-Fi padrão.

> [!NOTE]
> Para obter mais informações sobre a sequência de negociação de conexão, consulte [Miracast over protocolo de estabelecimento de conexão de infraestrutura (MS-mouse)](https://msdn.microsoft.com/library/mt796768.aspx)




## Habilitando Miracast sobre infraestrutura 

Se você tiver um Surface Hub ou outro dispositivo Windows 10 que foi atualizado para o Windows 10, versão 1703, então você tem automaticamente esse novo recurso. Para tirar proveito dele em seu ambiente, você precisa garantir que o seguinte é verdadeiro dentro de sua implantação:

- O Surface Hub ou o dispositivo (computador ou Windows phone) precisa estar executando o Windows 10, versão 1703.
- Abra a porta TCP: **7250**.
- Um Surface Hub ou computador com o Windows pode atuar como um Miracast sobre o *receptor* de infraestrutura. Um computador Windows ou telefone pode agir como um Miracast sobre a *fonte* da infraestrutura.
    - Como um receptor Miracast, o Surface Hub ou o dispositivo deve estar conectado à sua rede corporativa por meio de Ethernet ou uma conexão Wi-Fi segura (por exemplo, usando WPA2-PSK ou segurança WPA2-Enterprise). Se o Hub de superfície ou dispositivo estiver conectado a uma conexão Wi-Fi aberta, o Miracast na infraestrutura será desabilitado.
    - Como uma fonte de Miracast, o computador com Windows ou o telefone deve estar conectado à mesma rede empresarial por meio de Ethernet ou uma conexão Wi-Fi segura.
- O nome do host DNS (nome do dispositivo) do Surface Hub ou dispositivo precisa ser resolvível por meio de seus servidores DNS. Você pode conseguir isso permitindo que o Surface Hub registre automaticamente por meio do DNS dinâmico, ou criando manualmente um registro A ou AAAA para o nome do host do Surface Hub. 
- Os computadores com Windows 10 devem estar conectados à mesma rede empresarial por meio de Ethernet ou uma conexão Wi-Fi segura. 
-   Em computadores com Windows 10, o recurso **projetar para este PC** deve estar habilitado nas configurações do sistema, e o dispositivo deve ter uma interface Wi-Fi habilitada para responder às solicitações de descoberta que ocorrem apenas pelo adaptador Wi-Fi.


É importante observar que Miracast sobre infraestrutura não é um substituto para Miracast padrão. Em vez disso, a funcionalidade é um complemento e oferece uma vantagem para os usuários que fazem parte da rede corporativa. Os usuários que são convidados para um local específico e não têm acesso à rede corporativa continuar a se conectar usando o método de conexão Wi-Fi Direct.

A configuração **InBoxApps/WirelessProjection/PinRequired** no [Provedor de serviço de configuração (CSP) do SurfaceHub](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) não é necessária para o Miracast sobre infraestrutura. Isso ocorre porque Miracast sobre infraestrutura funciona apenas quando ambos os dispositivos estão conectados à mesma rede empresarial. Isso remove a restrição de segurança que estava anteriormente ausente do Miracast. Recomendamos que você continue usando esta configuração (se tiver usado anteriormente) porque o Miracast voltará ao Miracast normal se a conexão de infraestrutura não funcionar. 

## Perguntas frequentes
**Por que eu ainda preciso de Wi-Fi para usar o Miracast na infraestrutura?**<br>
As solicitações de descoberta para identificar receptores Miracast podem ocorrer apenas por meio do adaptador Wi-Fi. Após a identificação dos destinatários, o Windows 10 pode tentar a conexão com a rede.
