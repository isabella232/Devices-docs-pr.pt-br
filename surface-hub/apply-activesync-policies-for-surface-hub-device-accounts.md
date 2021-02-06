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
ms.openlocfilehash: 4db5066c62f4e0e324a5cc3ddad027e00a2e18c9
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314404"
---
# Aplicando políticas do ActiveSync a contas de dispositivo (Surface Hub)


A conta do dispositivo em todas as versões do Microsoft Surface Hub usa o ActiveSync para sincronizar email e calendário. Isso permite que as pessoas participem e iniciem reuniões agendadas do Surface Hub e enviem por e-mail quadros de comunicações feitos durante a reunião.

Para que esses recursos funcionem, as políticas do ActiveSync para sua organização devem ser configuradas da seguinte maneira:

-   Não pode haver políticas globais que bloqueiem a sincronização de caixa de correio do recurso que está sendo usado pela conta de dispositivo do Surface Hub. Se houver essa política de bloqueio, você precisará adicionar o Surface Hub como um dispositivo permitido.
-   Você deve definir uma política de caixa de correio de dispositivo móvel onde a configuração **PasswordEnabled** seja definida como False. Outras configurações de política de caixa de correio de dispositivo móvel não são compatíveis com o Surface Hub.

## Permitindo o DeviceID

Sua organização pode ter uma política global que impede a sincronização de contas de dispositivo provisionadas em Surface Hubs. Para configurar essa propriedade, consulte [Permitindo IDs de dispositivo para o ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## Configuração PasswordEnabled

A conta de dispositivo deve ter uma política do ActiveSync onde o atributo **PasswordEnabled** seja definido como False ou 0. Para configurar essa propriedade, consulte [Criando uma política do Microsoft Exchange ActiveSync compatível com o Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





