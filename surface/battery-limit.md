---
title: Configuração de limite de bateria (Surface)
description: O limite da bateria é uma configuração de UEFI que muda a forma como a bateria do dispositivo de superfície é cobrada e pode prolongar sua longevidade.
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
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830599"
---
# Configuração de limite da bateria

A opção de limite de bateria é uma configuração de UEFI que altera a carga da bateria do dispositivo Surface e pode prolongar sua longevidade. Essa configuração é recomendada em casos em que o dispositivo está conectado continuamente à energia, por exemplo, quando dispositivos são integrados em soluções de quiosque.  

## Como o limite de bateria funciona

Configurar o dispositivo com o limite de bateria altera o protocolo para carregar a bateria do dispositivo. Quando o limite da bateria estiver habilitado, a carga da bateria estará limitada a 50% de sua capacidade máxima. O nível de encargo informado no Windows refletirá esse limite. Portanto, ele mostrará que a bateria será cobrada até 50% e não será cobrada além desse limite. Se você habilitar o limite de bateria enquanto o dispositivo estiver acima de 50% do encargo, o ícone de bateria mostrará que o dispositivo está conectado, mas que será descarregado até que o dispositivo atinja 50% da sua capacidade máxima de cobrança.  

## Dispositivos com suporte
A configuração UEFI de limite de bateria está incorporada aos dispositivos de superfície mais recentes, incluindo Surface Pro 7 e Surface laptop 3. Dispositivos anteriores exigem uma [atualização de firmware da superfície de superfície](manage-surface-driver-and-firmware-updates.md), disponível por meio do Windows Update ou por meio do driver msi e pacotes de firmware no [site de suporte do Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface). Verifique [habilitar "limite de bateria" para dispositivos Surface que precisam ser conectados por períodos prolongados](https://support.microsoft.com/help/4464941) para a versão UEFI de superfície específica necessária para cada dispositivo compatível. 

## Habilitando o limite da bateria no Surface UEFI (Surface Pro 4 e posterior)

A configuração de limite de bateria UEFI de Surface pode ser configurada na inicialização do Surface UEFI (**Power + Vol up** ao ligar o dispositivo). Escolha **configuração de inicialização**e, em **Opções avançadas**, ative o **modo de limite de bateria** para **ativado**.  

![Captura de tela de opções avançadas](images/enable-bl.png) 

## Habilitando o limite de bateria no Surface Go e na superfície 2
A configuração de limite de bateria do Surface pode ser configurada na inicialização do Surface UEFI (**Power + Vol up** ao ligar o dispositivo). Escolha **configuração de inicialização**e, em **modo de quiosque**, mova o controle deslizante para a direita para definir o limite de bateria como **habilitado**.  

![Captura de tela do modo de quiosque de bateria no Surface go](images/go-batterylimit.png) 

## Habilitando o limite da bateria no Surface UEFI (Surface Pro 3)

A configuração de limite de bateria UEFI de Surface pode ser configurada na inicialização do Surface UEFI (**Power + Vol up** ao ligar o dispositivo). Escolha **modo de quiosque**, selecione **limite de bateria**e escolha **habilitado**.

![Captura de tela de opções avançadas](images/enable-bl-sp3.png) 

![Captura de tela de opções avançadas](images/enable-bl-sp3-2.png) 

## Habilitando o limite de bateria usando o modo de gerenciamento do Surface Enterprise (SEMM) ou scripts do PowerShell do Surface Pro 3

O limite de bateria UEFI da superfície também está disponível para configuração por meio dos seguintes métodos:

- Surface Pro 4 e posterior 
    - [Configurador UEFI da Microsoft Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Scripts do PowerShell do Surface Manager do Surface Manager (SEMM_Powershell.zip) nas [ferramentas de superfície para downloads de ti](https://www.microsoft.com/download/details.aspx?id=46703)
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### Usando o Microsoft Surface UEFI Configuration

Para configurar o modo de limite de bateria, defina a configuração de o **quiosque substituis** na página configuração **avançada de configurações** no Semm (Surface Pro 4 e posterior).

![Captura de tela de configurações avançadas](images/semm-bl.png)

### Usar scripts do PowerShell Surface Manager do Gerenciador

O recurso de limite de bateria é controlado por meio da seguinte configuração:  

`407 = Battery Profile`

**Descrição**: esquema de gerenciamento ativo para o padrão de uso da bateria

**Padrão**:  `0` 

Defina como `1` para habilitar o limite de bateria.

### Usando as ferramentas de firmware do Surface Pro 3

O recurso de limite de bateria é controlado por meio da seguinte configuração:  

**Nome**: BatteryLimitEnable

**Descrição**: BatteryLimit

**Valor atual**:  `0` 

**Valor padrão**: `0`

**Valor proposto**: `0` 

Defina como `1` para habilitar o limite de bateria.

>[!NOTE]
>Para definir essa configuração, você deve usar [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703). 

