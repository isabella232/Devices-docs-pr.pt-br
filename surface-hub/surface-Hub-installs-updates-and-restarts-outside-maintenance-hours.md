---
title: O Surface Hub pode instalar atualizações e reiniciar fora do horário de manutenção
description: informações de solução de problemas para Surface Hub em relação a atualizações automáticas
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: Hub Surface, janela de manutenção, atualização
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831035"
---
# O Surface Hub pode instalar atualizações e reiniciar fora do horário de manutenção

Em circunstâncias específicas, o Surface Hub instala atualizações durante o horário comercial, em vez de durante a janela de manutenção regular. Em seguida, o dispositivo reinicia se for necessário. Não é possível usar o dispositivo até que o processo seja concluído.

> [!NOTE]  
> Esse não é um comportamento esperado para faltar uma janela de manutenção. Isso ocorre apenas se o dispositivo estiver desatualizado por muito tempo.

## Causa
Para garantir que o Surface Hub permaneça disponível para uso durante o horário comercial, o Hub está configurado para executar funções administrativas durante uma janela de manutenção definida em configurações (consulte "referências" abaixo). Durante esse período de manutenção, o Hub instala automaticamente todas as atualizações disponíveis por meio do Windows Update ou do WSUS (Windows Server Update Service). Depois que as atualizações forem concluídas, o Hub poderá ser reiniciado.

As atualizações podem ser instaladas durante a janela de manutenção apenas se o Surface Hub estiver ativado, mas não estiver em uso ou reservado. Por exemplo, se o Surface Hub estiver agendado para uma reunião que dura 24 horas, todas as atualizações agendadas para serem instaladas serão adiadas até que o Hub esteja disponível durante a próxima janela de manutenção. Se o Hub continuar ocupado e perder várias janelas de manutenção, o Hub começará a instalar e baixar as atualizações. Isso pode ocorrer durante ou fora da janela de manutenção. Depois que o download e a instalação começarem, o dispositivo poderá ser reiniciado.

## Para evitar esse problema

É importante definir o tempo de manutenção do Surface Hub para executar funções administrativas. Reservar o Surface Hub para intervalos de 24 horas ou usar o dispositivo durante a janela de manutenção atrasa a instalação das atualizações. Recomendamos que você não use ou reserve o Hub durante o período de manutenção programada. Uma janela de duas horas deve ser reservada para atualização.

Uma opção que você pode usar para controlar a disponibilidade de atualizações é o WSUS (Windows Server Update Service). O WSUS oferece controle sobre quais atualizações estão instaladas e quando.

## Referências 
 
[Atualizar o Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 

[Janela de manutenção](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[Implantar atualizações do Windows 10 usando o Windows Server Update Services (WSUS)](/windows/deployment/update/waas-manage-updates-wsus) 


