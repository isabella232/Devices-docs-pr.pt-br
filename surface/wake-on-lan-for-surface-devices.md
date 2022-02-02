---
title: WOL para dispositivos Surface
description: Os dispositivos Surface que são executados Windows 10, versão 1607 ou posterior e usam um adaptador Surface Ethernet para se conectar a uma rede com fio são capazes de wake on lan (WOL) a partir de Modern Standby.
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
ms.openlocfilehash: eed1cbedea2a39207846301fa6b4f6c2b2f6dd56
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337904"
---
# <a name="wake-on-lan-for-surface-devices"></a>WOL para dispositivos Surface 

Os dispositivos Surface que Windows 10 versão 1607 ou posterior são capazes de Wake On LAN (WOL) de Espera Moderna (também conhecido como Espera Conectada). Com o WOL, os administradores de TI podem acordar remotamente dispositivos e executar tarefas de gerenciamento automaticamente com Microsoft Endpoint Manager ou soluções de terceiros.

>[!NOTE]
>Para dar suporte a WOL, os dispositivos Surface devem estar conectados à energia ac e usar um adaptador Surface Ethernet conectado a uma rede com fio.

## <a name="supported-devices"></a>Dispositivos com suporte

Adaptadores Ethernet com suporte para o WOL:

- Adaptador Ethernet Surface USB 3.0 Gigabit 
- Adaptador Surface Ethernet
- Surface USB-C para Ethernet e Adaptador USB
- Encaixe do Surface
- Surface Dock 2
- Estação de Encaixe do Surface para Surface Pro 3

Dispositivos Surface com suporte para o WOL:

- Surface 3
- Surface Pro 3
- Surface Pro 4
- Surface Pro (5ª Geração)
- Surface Pro (5ª geração) com LTE Avançado
- Surface Book (todas as gerações)
- Surface Laptop (todas as gerações)
- Surface Pro 6
- Surface Book 2
- Surface Go (todas as gerações)
- Surface Studio 2 (consulte Surface Studio 2 instruções abaixo)
- Surface Pro 7
- Surface Pro 7+
- Surface Pro 8
- Surface Laptop Go
- Surface Laptop Studio


## <a name="using-wol"></a>Usando o WOL 

Quando não estiver em uso, os dispositivos Surface entram em um estado ocioso e com baixa potência conhecido como Espera Moderna ou Espera Conectada. Os administradores de IT podem disparar remotamente dispositivos usando uma solicitação de alerta (pacote mágico) que contém o endereço MAC (Controle de Acesso de Mídia) do dispositivo Surface de destino. O NIC (cartão de interface de rede de destino) compara o endereço MAC com o seu próprio antes de acordar o dispositivo. Se o endereço MAC na solicitação de wake do pacote mágico não corresponder ao endereço MAC na NIC de destino, a NIC não acordará o dispositivo. Para saber mais, revise [a documentação De fontes de alerta](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## <a name="modern-standby"></a>Espera moderna

O modo de espera moderno é iniciado quando o usuário faz com que o sistema entre em sleep ou o dispositivo vá para o sono com base nas configurações de Windows de energia definidas pelo usuário. Por exemplo, o usuário pressiona o botão de energia, fecha a tampa ou seleciona Sleep do botão de energia no Windows menu Iniciar. O WOL funciona por padrão para dispositivos Surface no modo de espera moderno Windows 10 versão 1607 ou posterior. Nenhuma configuração de IT adicional é necessária, exceto para Surface Studio 2.

## <a name="surface-studio-2-instructions"></a>Surface Studio 2 instruções

Para habilitar o WOL Surface Studio 2, você deve usar o procedimento a seguir

1. Abra o Editor do Registro (**StartSearch** > **** > **regedit.exe**) e crie as seguintes chaves do Registro:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   ```

2. Execute o seguinte comando

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

> [!NOTE]
> Se você atualizar a versão do Windows 10 em seu Surface Studio 2 (por exemplo, você atualiza do Windows 10 20H2 para 21H1), você precisará seguir essas instruções novamente para habilitar o WOL.


### <a name="to-wake-from-hibernation-s4-or-shutdown-s5"></a>Para acordar da hibernação (S4) ou desligamento (S5) 

- Para dispositivos conectados ao Surface Dock 2, consulte [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)
