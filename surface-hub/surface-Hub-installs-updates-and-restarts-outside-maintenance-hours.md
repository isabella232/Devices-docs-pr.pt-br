---
title: O Surface Hub pode instalar atualizações e reiniciar fora do horário de manutenção
description: informações de solução de problemas para Surface Hub sobre atualizações automáticas
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub, janela de manutenção, atualização
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7c023256750ee997ce50d0adcd392207f47a298f
ms.sourcegitcommit: 3810c4310e9f5b5b9ad7b4584eaede2789ccd946
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902880"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a>O Surface Hub pode instalar atualizações e reiniciar fora do horário de manutenção

Em circunstâncias específicas, Surface Hub instala atualizações durante o horário comercial, em vez de durante a janela de manutenção regular. Em seguida, o dispositivo é reiniciado, se necessário. Não é possível usar o dispositivo até que o processo seja concluído.

> [!NOTE]  
> Esse não é o comportamento esperado para a falta de uma janela de manutenção. Ela só ocorrerá se o dispositivo estiver desa datado por muito tempo.

## <a name="cause"></a>Causa

Para garantir que o Surface Hub permaneça disponível para uso durante o horário comercial, o Hub é configurado para executar funções administrativas durante uma janela de manutenção definida no Configurações (consulte "Referências", abaixo). Durante esse período de manutenção, o Hub instala automaticamente todas as atualizações disponíveis por meio do Windows Update ou Windows Update for Business (WUfB). Depois que as atualizações são concluídas, o Hub pode ser reiniciado.

As atualizações só poderão ser instaladas durante a janela de manutenção se o Surface Hub estiver ligado, mas não estiver em uso ou reservado. Por exemplo, se o Surface Hub estiver agendado para uma reunião que dura 24 horas, todas as atualizações agendadas para serem instaladas serão adiadas até que o Hub seja disponibilizado durante a próxima janela de manutenção. Se o Hub continuar ocupado e perder várias janelas de manutenção, o Hub começará a instalar e baixar atualizações. Isso pode ocorrer durante ou fora da janela de manutenção. Depois que o download e a instalação tiver começado, o dispositivo poderá ser reiniciado.

## <a name="to-avoid-this-issue"></a>Para evitar esse problema

É importante que você reserve o tempo de manutenção para Surface Hub executar funções administrativas. A reserva do Surface Hub intervalos de 24 horas ou o uso do dispositivo durante a janela de manutenção atrasa a instalação de atualizações. Recomendamos que você não use ou reserve o Hub durante o período de manutenção agendado. Uma janela de duas horas deve ser reservada para atualização.

Uma opção que você pode usar para controlar a disponibilidade de atualizações é Windows Update for Business.

## <a name="learn-more"></a>Saiba mais
  
- [Janela de manutenção](manage-windows-updates-for-surface-hub.md#maintenance-window) 
