---
title: Aplicando políticas do ActiveSync a contas de dispositivo (Surface Hub)
description: A conta de dispositivo do Microsoft Surface Hub usa o ActiveSync para sincronizar e-mail e calendário. Isso permite que as pessoas participem e iniciem reuniões agendadas do Surface Hub e enviem por e-mail quadros de comunicações feitos durante a reunião.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, políticas do ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 7ead08e49d3eee2d616ac9fcf06b85dd82e136dc
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474728"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a>Aplicando políticas do ActiveSync a contas de dispositivo (Surface Hub)


Os Surface Hubs que usam contas de dispositivo do Active Directory (provisionados no Hub no formato **domínio\nome** de usuário) e serviços locais do Exchange usam o ActiveSync para sincronizar email e calendário. Isso permite que as pessoas participem e iniciem reuniões agendadas do Surface Hub e enviem por e-mail quadros de comunicações feitos durante a reunião.

Para que esses recursos funcionem, as políticas do ActiveSync para sua organização devem ser configuradas da seguinte maneira:

-   Não pode haver políticas globais que bloqueiem a sincronização de caixa de correio do recurso que está sendo usado pela conta de dispositivo do Surface Hub. Se houver essa política de bloqueio, você precisará adicionar o Surface Hub como um dispositivo permitido.
-   Você deve definir uma política de caixa de correio de dispositivo móvel onde a configuração **PasswordEnabled** seja definida como False. Outras configurações de política de caixa de correio de dispositivo móvel não são compatíveis com o Surface Hub.

## <a name="allowing-the-deviceid"></a>Permitindo o DeviceID

Sua organização pode ter uma política global que impede a sincronização de contas de dispositivo provisionadas em Surface Hubs. Para configurar essa propriedade, consulte [Permitindo IDs de dispositivo para o ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## <a name="setting-passwordenabled"></a>Configuração PasswordEnabled

A conta de dispositivo deve ter uma política do ActiveSync onde o atributo **PasswordEnabled** seja definido como False ou 0. Para configurar essa propriedade, consulte [Criando uma política do Microsoft Exchange ActiveSync compatível com o Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





