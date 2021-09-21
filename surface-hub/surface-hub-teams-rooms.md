---
title: Salas do Microsoft Teams no Surface Hub
description: Este artigo fornece uma visão geral do Salas do Microsoft Teams no Surface Hub.
keywords: Salas do Teams, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 05160bc2c1b77843b8ad832452501d7b065a8bc6
ms.sourcegitcommit: 38bde856b6091097d25745f6d080edebf72e3e17
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2021
ms.locfileid: "12030816"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Salas do Microsoft Teams no Surface Hub

Salas do Teams for Surface Hub substituirá automaticamente o aplicativo Surface Hub Teams [atual](hub-teams-app.md) como parte de uma versão global de 4 semanas a partir de 30 de setembro. Para uma demonstração da nova experiência Teams, atualmente disponível como uma visualização por meio do programa Windows Insider, consulte Apresentando Salas do Teams [no](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373)Surface Hub .

## <a name="whats-new"></a>Quais são as novidades?

- As reuniões ingressam Surface Hub tela de boas-vindas ou nova página agenda estão ingressando em "Borda para Borda" para colocar as pessoas em primeiro plano.
- Recursos de reunião familiares, incluindo bolhas de chat, reações, compartilhamento de área de trabalho e aplicativo, controle e controle e áudio, suporte completo PowerPoint ao vivo, modo conjunto e galeria grande.
- Salas do Teams no Surface Hub pode ser executado lado a lado com outros aplicativos ou ser executado minimizado.
- Os administradores podem configurar recursos como Reunião Coordenada e Participação de Proximidade para Surface Hub. [Os arquivos XML](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) são suportados e serão migrados para o novo modelo de configurações.
- Novas opções de QoS e requisitos de rede. Para saber mais, consulte [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).
- Alterações no Teams, substituindo Skype for Business como o aplicativo de colaboração e reunião padrão. Para saber mais, consulte [Deploy Microsoft Teams for Surface Hub](/MicrosoftTeams/teams-surface-hub).

## <a name="in-meeting-experience"></a>Na experiência de reunião

Salas do Teams no Surface Hub reuniões está alinhada à experiência familiar que os usuários conhecem de seus dispositivos pessoais com ajustes feitos para otimizar para um dispositivo de tela grande. Abrir Teams no Surface Hub permite que os usuários acessem os principais recursos, incluindo a junção de reunião do One-touch, Meet Now e Dial Pad para PSTN ou chamadas ponto a ponto.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Salas do Teams no Surface Hub Agenda.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Salas do Teams em Surface Hub Reunião.":::

## <a name="manage-teams-rooms-on-surface-hub"></a>Gerenciar Salas do Teams no Surface Hub

 Você pode personalizar a experiência Teams diretamente do menu Configurações depois de inserir credenciais administrativas, incluindo:

- Configurar [Reuniões Coordenadas e](/microsoftteams/rooms/coordinated-meetings) Participar de Proximidade.
- Ajuste as configurações para microfones, câmeras e alto-falantes padrão.
- Verifique a versão do cliente e procure as atualizações mais recentes.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Salas do Teams Configurações.":::

O novo Salas do Teams para Surface Hub cliente, aplicará automaticamente as configurações existentes configuradas por meio de arquivos XML, pacotes de provisionamento ou um provedor MDM. Esses métodos, explicados em [Manage Microsoft Teams configuration on Surface Hub](/microsoftteams/rooms/surface-hub-manage-config), serão substituídos por novas soluções baseadas em nuvem, conforme descrito abaixo em Gerenciamento simplificado de Teams chegando a [Surface Hub](#simplified-management-of-teams-coming-to-surface-hub).

### <a name="prepare-networking-for-teams-rooms"></a>Preparar rede para Salas do Teams

Para otimizar Salas do Teams consulte os requisitos e recomendações descritos em [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>Gerenciamento simplificado de Teams chegando ao Surface Hub

Quando Salas do Teams for Surface Hub lançado publicamente no final deste ano, os administradores poderão aproveitar as seguintes soluções:

- **Teams Centro de administração.** Teams O Centro de Administração fornece uma plataforma abrangente de auto-gerenciamento para monitorar e gerenciar a experiência Salas do Teams em Teams dispositivos. Teams O Centro de Administração estará disponível para Salas do Microsoft Teams usuários sem custo adicional.
- **Salas do Microsoft Teams serviço gerenciado.** O [Salas do Microsoft Teams](/microsoftteams/rooms/microsoft-teams-rooms-premium) gerenciado é um serviço de gerenciamento e monitoramento de IT baseado em nuvem que mantém os dispositivos Salas do Microsoft Teams e seus periféricos atualizados e monitorados proativamente, suportando um ambiente otimizado para uma ótima experiência do usuário.
