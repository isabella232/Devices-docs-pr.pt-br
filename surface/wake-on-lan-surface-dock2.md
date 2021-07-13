---
title: WOL com Surface Dock 2
description: O Surface Dock 2 oferece o melhor suporte para Wake on LAN (WOL), permitindo que os administradores acordem remotamente os dispositivos e executem tarefas de gerenciamento automaticamente.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643847"
---
# <a name="wake-on-lan-with-surface-dock-2"></a><span data-ttu-id="f4f78-104">WOL com Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="f4f78-104">Wake On LAN with Surface Dock 2</span></span>

<span data-ttu-id="f4f78-105">Para manter os dispositivos totalmente atualizados, os administradores de TI precisam ser capazes de gerenciar dispositivos quando não estão em uso, normalmente durante janelas de manutenção noturna.</span><span class="sxs-lookup"><span data-stu-id="f4f78-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="f4f78-106">O Surface Dock 2 oferece o melhor suporte para Wake on LAN (WOL), permitindo que os administradores acordem remotamente os dispositivos e executem automaticamente tarefas de gerenciamento com Microsoft Endpoint Manager ou outras soluções de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4f78-106">Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or other third party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4f78-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4f78-107">Requirements</span></span>

<span data-ttu-id="f4f78-108">Os dispositivos devem ter uma conexão com fio com o Surface Dock 2 e permanecer conectados ao AC Power.</span><span class="sxs-lookup"><span data-stu-id="f4f78-108">Devices must have a wired connection with Surface Dock 2 and stay connected to AC Power.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a><span data-ttu-id="f4f78-110">Dispositivos Surface com suporte</span><span class="sxs-lookup"><span data-stu-id="f4f78-110">Supported Surface devices</span></span>

- <span data-ttu-id="f4f78-111">Surface Laptop 4 (processadores Intel)</span><span class="sxs-lookup"><span data-stu-id="f4f78-111">Surface Laptop 4 (Intel processors)</span></span>
- <span data-ttu-id="f4f78-112">Surface Laptop 4 (processadores AMD)</span><span class="sxs-lookup"><span data-stu-id="f4f78-112">Surface Laptop 4 (AMD processors)</span></span>
- <span data-ttu-id="f4f78-113">Surface Laptop 3 (processadores Intel)</span><span class="sxs-lookup"><span data-stu-id="f4f78-113">Surface Laptop 3 (Intel processors)</span></span>
- <span data-ttu-id="f4f78-114">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="f4f78-114">Surface Pro 7+</span></span>
- <span data-ttu-id="f4f78-115">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="f4f78-115">Surface Pro 7</span></span>
- <span data-ttu-id="f4f78-116">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="f4f78-116">Surface Pro X</span></span>
- <span data-ttu-id="f4f78-117">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="f4f78-117">Surface Go 2</span></span>
- <span data-ttu-id="f4f78-118">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="f4f78-118">Surface Laptop Go</span></span>
- <span data-ttu-id="f4f78-119">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="f4f78-119">Surface Book 3</span></span>

<span data-ttu-id="f4f78-120">O Surface Dock 2 oferece suporte a WOL para dispositivos nos seguintes estados de energia:</span><span class="sxs-lookup"><span data-stu-id="f4f78-120">Surface Dock 2 provides WOL support for devices in the following power states:</span></span>

- <span data-ttu-id="f4f78-121">Modo de espera conectado</span><span class="sxs-lookup"><span data-stu-id="f4f78-121">Connected standby</span></span>
- <span data-ttu-id="f4f78-122">Hibernação (estado de energia S4)</span><span class="sxs-lookup"><span data-stu-id="f4f78-122">Hibernation (S4 power state)</span></span>
- <span data-ttu-id="f4f78-123">Desligamento (estado de energia "soft off" S5)</span><span class="sxs-lookup"><span data-stu-id="f4f78-123">Shutdown (S5 “soft off” power state)</span></span>

<span data-ttu-id="f4f78-124">Para saber mais sobre estados de energia, consulte [System Power States](/windows/win32/power/system-power-states).</span><span class="sxs-lookup"><span data-stu-id="f4f78-124">To learn more about power states, see [System Power States](/windows/win32/power/system-power-states).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="f4f78-125">Como funciona</span><span class="sxs-lookup"><span data-stu-id="f4f78-125">How it works</span></span>

<span data-ttu-id="f4f78-126">Quando não estiver em uso, os dispositivos Surface entram em um estado ocioso e com baixa potência conhecido como Espera Moderna ou Espera Conectada.</span><span class="sxs-lookup"><span data-stu-id="f4f78-126">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="f4f78-127">Os administradores de IT podem disparar remotamente dispositivos usando uma solicitação de alerta (pacote mágico) que contém o endereço MAC (Controle de Acesso de Mídia) do dispositivo Surface de destino.</span><span class="sxs-lookup"><span data-stu-id="f4f78-127">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="f4f78-128">Muitas soluções de gerenciamento, como Microsoft Endpoint Configuration Manager e aplicativos de terceiros Microsoft Store oferecem suporte integrado para o WOL.</span><span class="sxs-lookup"><span data-stu-id="f4f78-128">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span>

<span data-ttu-id="f4f78-129">Para habilitar o WOL em dispositivos sem o Surface Dock 2, consulte [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).</span><span class="sxs-lookup"><span data-stu-id="f4f78-129">To enable WOL on devices without Surface Dock 2, see [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="f4f78-130">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="f4f78-130">Learn more</span></span>

- [<span data-ttu-id="f4f78-131">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="f4f78-131">Surface Dock 2</span></span>](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [<span data-ttu-id="f4f78-132">WOL para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="f4f78-132">Wake On LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)
- [<span data-ttu-id="f4f78-133">Estados de energia do sistema</span><span class="sxs-lookup"><span data-stu-id="f4f78-133">System Power States</span></span>](/windows/win32/power/system-power-states)
- [<span data-ttu-id="f4f78-134">Configurar Wake on LAN - Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f4f78-134">Configure Wake on LAN - Configuration Manager</span></span>](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
