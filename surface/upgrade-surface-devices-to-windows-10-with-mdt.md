---
title: Fazer upgrade de dispositivos do Surface para o Windows 10 usando o Microsoft Deployment Toolkit (Surface)
description: Saiba como executar uma implantação de upgrade do Windows 10 em seus dispositivos Surface.
keywords: surface para windows 10, upgrade, personalizar, mdt
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
ms.date: 04/24/2020
ms.openlocfilehash: e1a1d34c4d32c5e6f95c985e335e405c0d9e59e4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830486"
---
# <span data-ttu-id="31959-104">Fazer upgrade dispositivos Surface para o Windows 10 com o Microsoft Deployment Toolkit</span><span class="sxs-lookup"><span data-stu-id="31959-104">Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit</span></span>

#### <span data-ttu-id="31959-105">Aplica-se ao</span><span class="sxs-lookup"><span data-stu-id="31959-105">Applies to</span></span>
- <span data-ttu-id="31959-106">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="31959-106">Surface Pro 6</span></span>
- <span data-ttu-id="31959-107">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="31959-107">Surface Laptop 2</span></span>
- <span data-ttu-id="31959-108">Surface Go</span><span class="sxs-lookup"><span data-stu-id="31959-108">Surface Go</span></span>
- <span data-ttu-id="31959-109">Surface Go com LTE</span><span class="sxs-lookup"><span data-stu-id="31959-109">Surface Go with LTE</span></span>
- <span data-ttu-id="31959-110">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="31959-110">Surface Book 2</span></span>
- <span data-ttu-id="31959-111">Surface Pro com LTE Avançado (Model 1807)</span><span class="sxs-lookup"><span data-stu-id="31959-111">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="31959-112">Surface Pro (Model 1796)</span><span class="sxs-lookup"><span data-stu-id="31959-112">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="31959-113">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="31959-113">Surface Laptop</span></span>
- <span data-ttu-id="31959-114">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="31959-114">Surface Studio</span></span>
- <span data-ttu-id="31959-115">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="31959-115">Surface Studio 2</span></span>
- <span data-ttu-id="31959-116">Surface Book</span><span class="sxs-lookup"><span data-stu-id="31959-116">Surface Book</span></span>
- <span data-ttu-id="31959-117">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="31959-117">Surface Pro 4</span></span>
- <span data-ttu-id="31959-118">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="31959-118">Surface 3 LTE</span></span>
- <span data-ttu-id="31959-119">Surface 3</span><span class="sxs-lookup"><span data-stu-id="31959-119">Surface 3</span></span>
- <span data-ttu-id="31959-120">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="31959-120">Surface Pro 3</span></span>
- <span data-ttu-id="31959-121">Surface Pro 2</span><span class="sxs-lookup"><span data-stu-id="31959-121">Surface Pro 2</span></span>
- <span data-ttu-id="31959-122">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="31959-122">Surface Pro</span></span>
- <span data-ttu-id="31959-123">Windows 10</span><span class="sxs-lookup"><span data-stu-id="31959-123">Windows 10</span></span>

<span data-ttu-id="31959-124">Além do método de implantação tradicional de dispositivos para refazer imagens, os administradores que desejam fazer upgrade de dispositivos Surface que estejam executando o Windows 8.1 ou o Windows 10 têm a opção de implantação de upgrades.</span><span class="sxs-lookup"><span data-stu-id="31959-124">In addition to the traditional deployment method of reimaging devices, administrators who want to upgrade Surface devices that are running Windows 8.1 or Windows 10 have the option of deploying upgrades.</span></span> <span data-ttu-id="31959-125">Ao executar uma implantação de upgrade, o Windows 10 pode ser aplicado a dispositivos sem remover usuários, aplicativos ou configuração.</span><span class="sxs-lookup"><span data-stu-id="31959-125">By performing an upgrade deployment, Windows 10 can be applied to devices without removing users, apps, or configuration.</span></span> <span data-ttu-id="31959-126">Os usuários dos dispositivos implantados podem simplesmente continuar usando os dispositivos com os mesmos aplicativos e configurações que eles usaram antes do upgrade.</span><span class="sxs-lookup"><span data-stu-id="31959-126">The users of the deployed devices can simply continue using the devices with the same apps and settings that they used prior to the upgrade.</span></span> 

<span data-ttu-id="31959-127">Para obter as informações mais recentes sobre como atualizar dispositivos Surface usando o MDT, confira [Executar uma atualização in-loco para o Windows 10 com o MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="31959-127">For the latest information about upgrading surface devices using MDT, refer to [Perform an in-place upgrade to Windows 10 with MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

