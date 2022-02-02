---
title: Proteção DMA do Surface
description: Este artigo descreve a proteção DMA em dispositivos Surface compatíveis
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/01/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: ae648f54f7abd97a6397dca5aa204205b582e4b0
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338044"
---
# <a name="dma-protection-on-surface-devices"></a>Proteção DMA em dispositivos Surface

A proteção de Acesso direto à Memória (DMA) foi projetada para reduzir possíveis vulnerabilidades de segurança associadas ao uso de SSDs removíveis ou dispositivos de armazenamento externo. Os dispositivos Surface mais novos vêm com a Proteção DMA habilitada por padrão. Eles incluem Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Laptop ES, Surface Pro 7+, Surface Pro 7, Surface Laptop 3 e Surface Pro  X.  Para verificar** a **presença do recurso de proteção DMA em seu dispositivo, abra Informações do Sistema (**Iniciar** > msinfo32.exe), conforme mostrado na figura abaixo.

![Informações do sistema que mostram a Proteção de DMA habilitada.](images/systeminfodma.png)

Se um SSD removível do Surface for adulterado, o dispositivo desligará a energia. A reinicialização resultante faz com que a UEFI limpe a memória, apagando todos os dados residuais.
