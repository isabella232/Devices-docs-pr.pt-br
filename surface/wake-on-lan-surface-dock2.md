---
title: WOL com Surface Dock 2
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
ms.date: 11/30/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 8f09941b555ba1b0870bd1e27fa1b85d0d72a19c
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448434"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>WOL com Surface Dock 2

Para manter os dispositivos totalmente atualizados, os administradores de TI precisam ser capazes de gerenciar dispositivos quando não estão em uso, normalmente durante janelas de manutenção noturna. O Surface Dock 2 oferece o melhor suporte para Wake on LAN (WOL), permitindo que os administradores acordem remotamente os dispositivos Surface e executem tarefas de gerenciamento automaticamente com Microsoft Endpoint Manager ou outras soluções de terceiros.

## <a name="requirements"></a>Requisitos

Os dispositivos devem ter uma conexão com fio com o Surface Dock 2 e permanecer conectados ao AC Power.

> [!div class="mx-imgBorder"]
> ![Surface Dock 2.](images/surface-dock2-angled.png)

> [!NOTE]
> Acordar dispositivos conectados ao Surface Dock 2 não requer o uso do Surface Enterprise Management Mode (SEMM) ou a habilitação de qualquer configuração de política UEFI.
 
## <a name="supported-surface-devices"></a>Dispositivos Surface com suporte

- Surface Laptop 4 (processadores Intel)
- Surface Laptop 4 (processadores AMD)
- Surface Laptop 3 (processadores Intel)
- Surface Pro 8
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go (todas as gerações)
- Surface Laptop Go
- Surface Book 3
- Surface Laptop Studio

O Surface Dock 2 oferece suporte a WOL para dispositivos nos seguintes estados de energia:

- Modo de espera conectado
- Hibernação (estado de energia S4)
- Desligamento (estado de energia "soft off" S5)

Para saber mais sobre estados de energia, consulte [System Power States](/windows/win32/power/system-power-states).

## <a name="how-it-works"></a>Como funciona

Quando não estiver em uso, os dispositivos Surface entram em um estado ocioso e com baixa potência conhecido como Espera Moderna ou Espera Conectada. Ou os dispositivos podem estar em estado de energia de hibernação (S4) ou desligamento (S5) com base nas configurações de energia configuradas no dispositivo. Os administradores de IT podem disparar remotamente dispositivos usando uma solicitação de alerta (pacote mágico) que contém o endereço MAC (Controle de Acesso de Mídia) do dispositivo Surface de destino. Muitas soluções de gerenciamento, como Microsoft Endpoint Configuration Manager e aplicativos de terceiros Microsoft Store oferecem suporte integrado para o WOL.

Para habilitar o WOL em dispositivos sem o Surface Dock 2, consulte:

- [Acordar na LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

## <a name="learn-more"></a>Saiba mais

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [WOL para dispositivos Surface](wake-on-lan-for-surface-devices.md)
- [Estados de energia do sistema](/windows/win32/power/system-power-states)

