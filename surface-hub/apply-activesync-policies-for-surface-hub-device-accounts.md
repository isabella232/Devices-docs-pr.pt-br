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
ms.openlocfilehash: fa393eca697897ee620732b543ebb6889aa035d1
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472570"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a>Aplicando políticas do ActiveSync a contas de dispositivo (Surface Hub)

Os Surface Hubs no Windows 10 Team 1703 e versões anteriores usaram o ActiveSync para sincronizar emails & calendário.

Os Surface Hub requisitos para políticas activeSync em sua organização são os seguintes:

-   Não pode haver nenhuma política global que bloqueie a sincronização da caixa de correio de recurso que está sendo usada pela conta de dispositivo Surface Hub do servidor. Se houver essa política de bloqueio, você precisará adicionar o Surface Hub como um dispositivo permitido.
-   Você deve definir uma política de caixa de correio de dispositivo móvel onde a configuração **PasswordEnabled** seja definida como False. Outras configurações de política de caixa de correio de dispositivo móvel não são compatíveis com o Surface Hub.

## <a name="allowing-the-deviceid"></a>Permitindo o DeviceID

Sua organização pode ter uma política global que impede a sincronização de contas de dispositivo provisionadas em Surface Hubs. Para configurar essa propriedade, consulte [Permitindo IDs de dispositivo para o ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## <a name="setting-passwordenabled"></a>Configuração PasswordEnabled

A conta de dispositivo deve ter uma política do ActiveSync onde o atributo **PasswordEnabled** seja definido como False ou 0. Para configurar essa propriedade, consulte [Criando uma política do Microsoft Exchange ActiveSync compatível com o Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





