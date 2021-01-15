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
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270616"
---
# <span data-ttu-id="09560-103">Proteção DMA em dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="09560-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="09560-104">A proteção de Acesso Direto à Memória (DMA) foi projetada para reduzir possíveis vulnerabilidades de segurança associadas ao uso de SSDs removíveis ou dispositivos de armazenamento externo.</span><span class="sxs-lookup"><span data-stu-id="09560-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="09560-105">Dispositivos Surface mais novos vêm com a Proteção DMA habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="09560-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="09560-106">Isso inclui o Surface Pro 7+.</span><span class="sxs-lookup"><span data-stu-id="09560-106">These include Surface Pro 7+.</span></span> <span data-ttu-id="09560-107">Surface Pro 7, Surface Laptop 3 e Surface Pro X.  Para verificar a presença do recurso de proteção DMA em seu dispositivo, abra Informações do Sistema **(** Iniciarmsinfo32.exe), conforme mostrado na  >  \*\* \*\*figura abaixo.</span><span class="sxs-lookup"><span data-stu-id="09560-107">Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![Informações do sistema mostrando a Proteção de DMA habilitada](images/systeminfodma.png)

<span data-ttu-id="09560-109">Se um SSD removível do Surface for adulterado, o dispositivo desligará a energia.</span><span class="sxs-lookup"><span data-stu-id="09560-109">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="09560-110">A reinicialização resultante faz com que a UEFI limpe a memória, apagando quaisquer dados residuais.</span><span class="sxs-lookup"><span data-stu-id="09560-110">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
