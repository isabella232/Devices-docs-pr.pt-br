---
title: Wake On LAN para dispositivos Surface
description: Veja como você pode usar Wake On LAN para acordar remotamente dispositivos para executar tarefas de gerenciamento automaticamente.
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613791"
---
# <a name="wake-on-lan-for-surface-devices"></a>Wake On LAN para dispositivos Surface

Para manter os dispositivos totalmente atualizados, os administradores de TI precisam ser capazes de gerenciar dispositivos quando não estão em uso, normalmente durante janelas de manutenção noturna. O Wake on LAN (WOL) permite que os administradores acordem remotamente os dispositivos e executem tarefas de gerenciamento automaticamente com Microsoft Endpoint Manager ou soluções de terceiros.

## <a name="requirements"></a>Requisitos

Os dispositivos devem estar conectados à energia ac e ter uma conexão com fio com um dos seguintes adaptadores Ethernet compatíveis:

- Adaptador Ethernet Surface USB 3.0 Gigabit
- Adaptador Surface Ethernet
- Surface USB-C para Ethernet e Adaptador USB
- Microsoft USB-C Travel Adapter Hub
- Encaixe do Surface
- Surface Dock 2

> [!NOTE]
> O Surface Dock 2 oferece o melhor suporte para Wake on LAN sem a necessidade de qualquer configuração de TI adicional. Para saber mais, confira [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)

## <a name="how-it-works"></a>Como funciona

Quando não estiver em uso, os dispositivos Surface entram em um estado ocioso e com baixa potência conhecido como Espera Moderna ou Espera Conectada. Os administradores de IT podem disparar remotamente dispositivos usando uma solicitação de alerta (pacote mágico) que contém o endereço MAC (Controle de Acesso de Mídia) do dispositivo Surface de destino. Muitas soluções de gerenciamento, como Microsoft Endpoint Configuration Manager e aplicativos de terceiros Microsoft Store oferecem suporte integrado para o WOL. Para saber mais sobre como acordar dispositivos com o Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).

O suporte para Wake on LAN varia dependendo do estado de sono: Espera conectada ou hibernação (estado de energia S4).

## <a name="connected-standby"></a>Espera conectada

Por padrão, Windows 10 suporta Wake on LAN para dispositivos Surface em Espera Conectada.

### <a name="supported-surface-devices---connected-standby"></a>Dispositivos Surface com suporte - Espera Conectada

- Surface Laptop 4 (somente processadores Intel)
- Surface Laptop 3 (somente processadores Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop Go
- Surface Book 3

## <a name="hibernation"></a>Hibernação

Para acordar os dispositivos fora da Hibernação, é necessário habiler uma configuração de política UEFI por meio do [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (não necessário para dispositivos conectados ao Surface Dock 2).

### <a name="supported-surface-devices---hibernation"></a>Dispositivos Surface com suporte - Hibernação

- Surface Laptop 4 (somente processadores Intel)
- Surface Laptop 3 (somente processadores Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop Go
- Surface Book 3

### <a name="to-enable-wake-on-lan-uefi-setting"></a>Para habilitar a configuração Wake on LAN UEFI

Para habilitar a configuração Wake on LAN UEFI, você precisa registrar dispositivos de destino no SEMM, criar um pacote de configuração e aplicar o pacote aos dispositivos. Para obter mais informações, consulte:

- [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
- [Registrar e configurar dispositivos Surface com o SEMM](enroll-and-configure-surface-devices-with-semm.md)

1. Baixe e instale [**o Configurador UEFI do Surface.**](https://www.microsoft.com/download/details.aspx?id=46703)
2. Selecione **Iniciar**  >  **Pacote de**  >  **Configuração Criar**  > **+ Proteção de Certificado.**
3. Vá para **Configurações avançadas** e **alternar Wake on LAN** para **On**.
4. Aplique o pacote a dispositivos de destino.

    > [!div class="mx-imgBorder"]
    > ![Habilitar a configuração da política Wake on LAN UEFI](images/wol-uefi.png)

## <a name="learn-more"></a>Saiba mais

- [Acordar na LAN para o Surface Dock 2](wake-on-lan-surface-dock2.md)
- [Microsoft Surface USB-C para Ethernet e Adaptador USB](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [Adaptador Ethernet Surface USB 3.0 Gigabit](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
