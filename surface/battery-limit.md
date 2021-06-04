---
title: Configuração de Limite de Bateria (Surface)
description: O Limite de Bateria é uma configuração UEFI que altera a forma como a bateria do dispositivo Surface é carregada e pode prolongar sua longevidade.
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
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271138"
---
# Configuração de limite da bateria

A opção limite de bateria é uma configuração UEFI que altera como a bateria do dispositivo Surface é carregada e pode prolongar sua longevidade. Essa configuração é recomendada em casos em que o dispositivo está continuamente conectado à energia, por exemplo, quando os dispositivos são integrados a soluções de quiosque.  

##  <a name="how-battery-limit-works"></a>Como funciona o Limite de Bateria

Definir o dispositivo no Limite de Bateria altera o protocolo para carregar a bateria do dispositivo. Quando o Limite da Bateria estiver habilitado, a carga da bateria será limitada a 50% de sua capacidade máxima. O nível de cobrança relatado no Windows refletirá esse limite. Portanto, ele mostrará que a bateria é carregada até 50% e não será carregada além desse limite. Se você habilitar o Limite de Bateria enquanto o dispositivo estiver acima de 50% da carga, o ícone de bateria mostrará que o dispositivo está conectado, mas descarregando até que o dispositivo atinja 50% de sua capacidade máxima de carga.  

##  <a name="supported-devices"></a>Dispositivos com suporte

A configuração UEFI de Limite de Bateria foi criada nos dispositivos Surface mais recentes, incluindo o Surface Pro 7+, o Surface Pro 7 e o Surface Laptop 3. Dispositivos anteriores exigem uma atualização de [firmware UEFI](manage-surface-driver-and-firmware-updates.md)do Surface, disponível por meio do Windows Update ou por meio dos pacotes de driver e firmware MSI no site de suporte [do Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface) Marque [Habilitar "Limite](https://support.microsoft.com/help/4464941) de Bateria" para dispositivos Surface que precisam estar conectados por longos períodos de tempo para a versão UEFI específica do Surface necessária para cada dispositivo compatível. 

##  <a name="enabling-battery-limit-in-surface-uefi-(surface-pro-4-and-later)"></a>Habilitando o limite de bateria no UeFI do Surface (Surface Pro 4 e posterior)

A configuração de Limite de Bateria UEFI do Surface pode ser configurada inicializando-se no UEFI do Surface (**Ligar/Desligar + Vol Up** ao ligar o dispositivo). Escolha **a configuração**de inicialização e, em **Opções Avançadas,** alterne a opção Habilitar Modo de Limite **de Bateria** para **Ativado.**  

![Opções avançadas de limite de bateria](images/enable-bl.png) 

##  <a name="enabling-battery-limit-on-surface-go-and-surface-go-2"></a>Habilitando o limite de bateria no Surface Go e no Surface Go 2
A configuração do Limite de Bateria do Surface pode ser configurada inicializando-se no UEFI do Surface (**Power + Vol Up** ao ligar o dispositivo). Escolha **a configuração**de inicialização e, em **Modo de Quiosque,** mova o controle deslizante para a direita para definir o Limite de Bateria como **Habilitado.**  

![Limite de bateria do modo de quiosque no Surface Go](images/go-batterylimit.png) 

##  <a name="enabling-battery-limit-in-surface-uefi-(surface-pro-3)"></a>Habilitando o limite de bateria no Surface UEFI (Surface Pro 3)

A configuração de Limite de Bateria UEFI do Surface pode ser configurada inicializando-se no UEFI do Surface (**Ligar/Desligar + Vol Up** ao ligar o dispositivo). Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.

![Captura de tela das opções avançadas](images/enable-bl-sp3.png) 

![Opções avançadas](images/enable-bl-sp3-2.png) 

##  <a name="enabling-battery-limit-using-surface-enterprise-management-mode-(semm)-or-surface-pro-3-firmware-powershell-scripts"></a>Habilitando o limite de bateria usando scripts do PowerShell do Surface Enterprise Management Mode (SEMM) ou do firmware do Surface Pro 3

O limite de bateria UEFI do Surface também está disponível para configuração por meio dos seguintes métodos:

- Surface Pro 4 e posterior 
    - [Configurador UEFI do Microsoft Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Scripts do Powershell do Surface UEFI Manager (SEMM_Powershell.zip) nos [downloads](https://www.microsoft.com/download/details.aspx?id=46703) do Surface Tools for IT
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

###  <a name="using-microsoft-surface-uefi-configurator"></a>Usando o configurador UEFI do Microsoft Surface

Para configurar o modo Limite de Bateria, defina a configuração Substituições de **Quiosque** na página configuração Configurações **Avançadas** no SEMM (Surface Pro 4 e posterior).

![Captura de tela das configurações avançadas](images/semm-bl.png)

###  <a name="using-surface-uefi-manager-powershell-scripts"></a>Usando scripts do PowerShell do Surface UEFI Manager

O recurso de limite de bateria é controlado por meio da seguinte configuração:  

`407 = Battery Profile`

**Descrição**: Esquema de gerenciamento ativo para o padrão de uso da bateria

**Padrão:**  `0` 

De configurar isso para `1` habilitar o Limite de Bateria.

###  <a name="using-surface-pro-3-firmware-tools"></a>Usando ferramentas de firmware do Surface Pro 3

O recurso de limite de bateria é controlado por meio da seguinte configuração:  

**Nome**: BatteryLimitEnable

**Descrição**: BatteryLimit

**Valor atual:**  `0` 

**Valor padrão:** `0`

**Valor Proposto:** `0` 

De configurar isso para `1` habilitar o Limite de Bateria.

>[!NOTE]
>Para definir essa configuração, você deve usar [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703). 

