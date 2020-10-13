---
title: Implantar o Windows 10 em dispositivos de superfície com o kit de ferramentas de implantação da Microsoft (Surface)
description: Percorra o processo recomendado de como implantar o Windows 10 em seus dispositivos de superfície com o kit de ferramentas de implantação da Microsoft.
keywords: superfície do Windows 10, automatizar, personalizar, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 10/12/2020
ms.openlocfilehash: 858b6726f1127e3c439864f8946274ed0ea1edd3
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114559"
---
# <span data-ttu-id="7e2c5-104">Implantar o Windows 10 em dispositivos de superfície com o kit de ferramentas de implantação da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e2c5-104">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>

**<span data-ttu-id="7e2c5-105">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="7e2c5-105">Applies to</span></span>**

- <span data-ttu-id="7e2c5-106">Surface Studio e posterior</span><span class="sxs-lookup"><span data-stu-id="7e2c5-106">Surface Studio and later</span></span>
- <span data-ttu-id="7e2c5-107">Surface Pro 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="7e2c5-107">Surface Pro 4 and later</span></span>
- <span data-ttu-id="7e2c5-108">Catálogo de superfície e mais tarde</span><span class="sxs-lookup"><span data-stu-id="7e2c5-108">Surface Book and later</span></span>
- <span data-ttu-id="7e2c5-109">Surface laptop e posterior</span><span class="sxs-lookup"><span data-stu-id="7e2c5-109">Surface Laptop and later</span></span>
- <span data-ttu-id="7e2c5-110">Usar o laptop Surface</span><span class="sxs-lookup"><span data-stu-id="7e2c5-110">Surface Laptop Go</span></span>
- <span data-ttu-id="7e2c5-111">Surface Go</span><span class="sxs-lookup"><span data-stu-id="7e2c5-111">Surface Go</span></span>
- <span data-ttu-id="7e2c5-112">Surface 3</span><span class="sxs-lookup"><span data-stu-id="7e2c5-112">Surface 3</span></span>
- <span data-ttu-id="7e2c5-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7e2c5-113">Windows 10</span></span>

> [!NOTE]
> <span data-ttu-id="7e2c5-114">O MDT não é compatível com o Surface Pro X. Para obter mais informações, consulte [implantação, gerenciamento e manutenção do Surface Pro X](surface-pro-arm-app-management.md).</span><span class="sxs-lookup"><span data-stu-id="7e2c5-114">MDT is not supported on Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

<span data-ttu-id="7e2c5-115">Para obter as informações mais recentes sobre como usar o MDT, consulte [implantar uma imagem do Windows 10 usando o MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span><span class="sxs-lookup"><span data-stu-id="7e2c5-115">For the latest information about using MDT, refer to [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span></span>

