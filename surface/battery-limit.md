---
title: Configuração do Limite de Bateria (Surface)
description: O Limite da Bateria é uma configuração UEFI que altera a forma como a bateria do dispositivo Surface é carregada e pode prolongar sua longevidade.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 9cf623a9a4b9d1a8d292cfa0cff25d2e57318db7
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338324"
---
# <a name="battery-limit-setting"></a>Configuração de limite da bateria

A opção Limite de Bateria é uma configuração UEFI que altera a forma como a bateria do dispositivo Surface é carregada e pode prolongar sua longevidade. Essa configuração é recomendada nos casos em que o dispositivo está conectado continuamente à energia, por exemplo, quando os dispositivos são integrados às soluções de quiosque.  

## <a name="how-battery-limit-works"></a>Como funciona o Limite de Bateria

A configuração do dispositivo em Limite de Bateria altera o protocolo para carregar a bateria do dispositivo. Quando o Limite da Bateria estiver habilitado, a carga da bateria será limitada a 50% de sua capacidade máxima. O nível de carga relatado Windows refletirá esse limite. Portanto, ele mostrará que a bateria é carregada até 50% e não será carregada além desse limite. Se você habilitar o Limite de Bateria enquanto o dispositivo estiver acima de 50% de carga, o ícone Bateria mostrará que o dispositivo está conectado, mas descarregando até que o dispositivo atinja 50% de sua capacidade máxima de carga.  

## <a name="supported-devices"></a>Dispositivos com suporte

A configuração UEFI de Limite de Bateria é criada em dispositivos Surface por padrão, incluindo: 

- Surface Pro 7 e posteriores
- Surface Laptop 3 e posteriores
- Surface Book 3
- Surface Laptop Studio
- Surface Laptop Go
- Surface Studio 2
- Surface Laptop ES

 Dispositivos anteriores exigem uma atualização de [firmware uefi do Surface](manage-surface-driver-and-firmware-updates.md), disponível por meio do Windows Update ou por meio dos pacotes de driver e firmware MSI no [site de Suporte do Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface). Verifique [Habilitar "Limite de Bateria" para dispositivos Surface que precisam ser conectados por longos períodos](https://support.microsoft.com/help/4464941) de tempo para a versão UEFI do Surface específica necessária para cada dispositivo com suporte.

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-4-and-later"></a>Habilitando o limite de bateria no Surface UEFI (Surface Pro 4 e posterior)

A configuração limite da bateria UEFI do Surface pode ser configurada inicializando-se no Surface UEFI (**Power + Vol Up** ao ligar o dispositivo). Escolha **configuração de inicialização** e, em **Opções** Avançadas, alterne **Habilitar Modo de Limite de Bateria** para **Ativado**.  

![Opções avançadas de Limite de Bateria.](images/enable-bl.png)

## <a name="enabling-battery-limit-on-surface-go-all-generations"></a>Habilitando o limite de bateria no Surface Go (todas as gerações)

A configuração limite da bateria surface pode ser configurada inicializando-se no Surface UEFI (**Power + Vol Up** ao ligar o dispositivo). Escolha **configuração de** inicialização e, em Modo **Quiosque**, mova o controle deslizante para a direita para definir o Limite da Bateria como **Habilitado**.  

![Limite de bateria do modo quiosque no Surface Go.](images/go-batterylimit.png)

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-3"></a>Habilitando o limite de bateria no Surface UEFI (Surface Pro 3)

A configuração limite da bateria UEFI do Surface pode ser configurada inicializando-se no Surface UEFI (**Power + Vol Up** ao ligar o dispositivo). Escolha **Modo quiosque**, selecione **Limite de** Bateria e, em seguida, escolha **Habilitado**.

![Captura de tela de opções avançadas.](images/enable-bl-sp3.png)

![Opções avançadas.](images/enable-bl-sp3-2.png)

## <a name="enabling-battery-limit-using-surface-enterprise-management-mode-semm-or-surface-pro-3-firmware-powershell-scripts"></a>Habilitando o limite de bateria usando o Surface Enterprise Modo de Gerenciamento (SEMM) ou Surface Pro scripts do PowerShell de firmware 3

O limite de bateria UEFI do Surface também está disponível para configuração por meio dos seguintes métodos:

- Surface Pro 4 e posterior
  - [Configurador UEFI do Microsoft Surface](surface-enterprise-management-mode.md)  
    - Scripts do Surface UEFI Manager powershell (SEMM_Powershell.zip) nos [downloads do Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)

### <a name="using-microsoft-surface-uefi-configurator"></a>Usando o Configurador UEFI do Microsoft Surface

Para configurar o modo Limite de Bateria, defina a configuração Substituições de **Quiosque** **na** página Configuração avançada Configurações no SEMM (Surface Pro 4 e posterior).

![Captura de tela de configurações avançadas.](images/semm-bl.png)

### <a name="using-surface-uefi-manager-powershell-scripts"></a>Usando scripts do PowerShell do Surface UEFI Manager

O recurso de limite de bateria é controlado por meio da seguinte configuração:  

`407 = Battery Profile`

**Descrição**: Esquema de gerenciamento ativo para padrão de uso de bateria

**Padrão**:  `0`

De definir isso para `1` habilitar o Limite de Bateria.
