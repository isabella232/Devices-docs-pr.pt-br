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
# <span data-ttu-id="c6a97-103">Proteção DMA em dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="c6a97-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="c6a97-104">A proteção de acesso direto à memória (DMA) foi projetada para atenuar possíveis vulnerabilidades de segurança associadas ao uso de dispositivos de armazenamento externo ou SSDs removíveis.</span><span class="sxs-lookup"><span data-stu-id="c6a97-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="c6a97-105">Os dispositivos de superfície mais recentes vêm com a proteção DMA habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c6a97-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="c6a97-106">Eles incluem Surface Pro 7, Surface laptop 3 e Surface Pro X.  Para verificar a presença do recurso de proteção de DMA em seu dispositivo, abra as informações do sistema (**Iniciar**  >  **msinfo32.exe**), conforme mostrado na figura abaixo.</span><span class="sxs-lookup"><span data-stu-id="c6a97-106">These include Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![Informações do sistema mostrando a proteção DMA habilitada](images/systeminfodma.png)

<span data-ttu-id="c6a97-108">Se um SSD removível de superfície for adulterado, o dispositivo será shutoff energia.</span><span class="sxs-lookup"><span data-stu-id="c6a97-108">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="c6a97-109">A reinicialização resultante faz com que a UEFI Limpe a memória para apagar dados residuais.</span><span class="sxs-lookup"><span data-stu-id="c6a97-109">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
