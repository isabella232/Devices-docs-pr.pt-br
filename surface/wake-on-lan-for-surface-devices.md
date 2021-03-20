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
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442149"
---
# <a name="wake-on-lan-for-surface-devices"></a>Wake On LAN para dispositivos Surface

Os dispositivos Surface que usam um adaptador Surface Ethernet para se conectar a uma rede com fio podem tirar proveito do Wake On LAN (WOL) de Espera Conectada. Com o WOL, você pode acordar remotamente dispositivos e executar tarefas de gerenciamento automaticamente usando soluções de gerenciamento, como o Microsoft Endpoint Manager/Microsoft Intune.

## <a name="wol-supported-devices"></a>Dispositivos compatíveis com o WOL

- Adaptador Surface Ethernet
- Surface USB-C para Ethernet e Adaptador USB
- Surface Dock 2
- Surface Pro 6 e posterior
- Surface Book (todas as gerações)
- Surface Laptop (todas as gerações)
- Surface Go (todas as gerações)
- Surface Studio 2 (consulte Apêndice)


## <a name="using-surface-wol"></a>Usando o Surface WOL

Os administradores de IT podem disparar dispositivos usando um wake on LAN request (pacote mágico) que contém o endereço MAC do computador de destino. Para enviar um pacote mágico e acordar um dispositivo usando o WOL, você deve saber o endereço MAC do dispositivo de destino e o adaptador Ethernet. Como o pacote mágico não usa o protocolo de rede IP, não é possível usar o endereço IP ou o nome DNS do dispositivo.

Muitas soluções de gerenciamento, como o Microsoft Endpoint Configuration Manager e aplicativos da Microsoft Store de terceiros oferecem suporte integrado para o WOL. Observe que os dispositivos precisam estar no modo De espera conectado (Sleep) e conectados à energia ac. Para saber mais sobre como acordar dispositivos com o Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).


## <a name="to-check-wol-is-enabled-on-your-device"></a>Para verificar se a WOL está habilitada em seu dispositivo

1. Em seu dispositivo conectado Ethernet, selecione seu adaptador de rede e selecione **Propriedades**.

   > [!div class="mx-imgBorder"]
   > ![Adaptador Surface Ethernet](images/surface-ethernet.png)

2. Selecione **Configurar**  >  **Avançado**.
3. Role até **Pacote Moderno de Espera WoL Mágico** e certifique-se de que **Habilitado** está selecionado.

     ![Verificar se a WOL está habilitada no dispositivo](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a>Apêndice: Surface Studio 2

Para habilitar o WOL no Surface Studio 2, use o procedimento a seguir.

1. Crie as seguintes chaves do Registro:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Execute o seguinte comando

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a>Saiba mais

- [Microsoft Surface USB-C para Ethernet e Adaptador USB](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [Adaptador Ethernet Surface USB 3.0 Gigabit](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
