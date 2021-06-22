---
title: Acordar na LAN com o Surface Dock 2
description: O Surface Dock 2 oferece o melhor suporte para Wake on LAN (WOL), permitindo que os administradores acordem remotamente os dispositivos e executem tarefas de gerenciamento automaticamente.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 6/03/2021
ms.openlocfilehash: 74b36b60cb58ecb9042b73b8cdba7271d0af8c80
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614030"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>Acordar na LAN com o Surface Dock 2

Para manter os dispositivos totalmente atualizados, os administradores de TI precisam ser capazes de gerenciar dispositivos quando não estão em uso, normalmente durante janelas de manutenção noturna. O Surface Dock 2 oferece o melhor suporte para Wake on LAN (WOL), permitindo que os administradores acordem remotamente os dispositivos e executem automaticamente tarefas de gerenciamento com Microsoft Endpoint Manager ou outras soluções de terceiros.

## <a name="requirements"></a>Requisitos

Os dispositivos devem ter uma conexão com fio com o Surface Dock 2 e permanecer conectados ao AC Power.

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a>Dispositivos Surface com suporte

- Surface Laptop 4 (processadores Intel)
- Surface Laptop 4 (processadores AMD)
- Surface Laptop 3 (processadores Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop Go
- Surface Book 3

O Surface Dock 2 oferece suporte a WOL para dispositivos nos seguintes estados de energia:

- Modo de espera conectado
- Hibernação (estado de energia S4)
- Hibernação (estado de energia "soft off" S5)

Para saber mais sobre estados de energia, consulte [System Power States](/windows/win32/power/system-power-states).

## <a name="how-it-works"></a>Como funciona

Quando não estiver em uso, os dispositivos Surface entram em um estado ocioso e com baixa potência conhecido como Espera Moderna ou Espera Conectada. Os administradores de IT podem disparar remotamente dispositivos usando uma solicitação de alerta (pacote mágico) que contém o endereço MAC (Controle de Acesso de Mídia) do dispositivo Surface de destino. Muitas soluções de gerenciamento, como Microsoft Endpoint Configuration Manager e aplicativos de terceiros Microsoft Store oferecem suporte integrado para o WOL.

Para habilitar o WOL em dispositivos sem o Surface Dock 2, consulte [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).

## <a name="learn-more"></a>Saiba mais

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [Wake On LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)
- [Estados de energia do sistema](/windows/win32/power/system-power-states)
- [Configurar Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
