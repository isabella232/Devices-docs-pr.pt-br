---
title: Proteção DMA de superfície
description: Este artigo descreve a proteção DMA em dispositivos de superfície compatíveis
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830379"
---
# Proteção DMA em dispositivos Surface

A proteção de acesso direto à memória (DMA) foi projetada para atenuar possíveis vulnerabilidades de segurança associadas ao uso de dispositivos de armazenamento externo ou SSDs removíveis. Os dispositivos de superfície mais recentes vêm com a proteção DMA habilitada por padrão. Eles incluem Surface Pro 7, Surface laptop 3 e Surface Pro X.  Para verificar a presença do recurso de proteção de DMA em seu dispositivo, abra as informações do sistema (**Iniciar**  >  **msinfo32.exe**), conforme mostrado na figura abaixo.

![Informações do sistema mostrando a proteção DMA habilitada](images/systeminfodma.png)

Se um SSD removível de superfície for adulterado, o dispositivo será shutoff energia. A reinicialização resultante faz com que a UEFI Limpe a memória para apagar dados residuais.
