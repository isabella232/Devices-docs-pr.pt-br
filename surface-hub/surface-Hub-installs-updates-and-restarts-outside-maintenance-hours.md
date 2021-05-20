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
ms.openlocfilehash: 7df7857258c1baeedf4ff239eda17c66c93a531c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577021"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a><span data-ttu-id="faa32-104">O Surface Hub pode instalar atualizações e reiniciar fora do horário de manutenção</span><span class="sxs-lookup"><span data-stu-id="faa32-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="faa32-105">Em circunstâncias específicas, Surface Hub instala atualizações durante o horário comercial, em vez de durante a janela de manutenção regular.</span><span class="sxs-lookup"><span data-stu-id="faa32-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="faa32-106">Em seguida, o dispositivo é reiniciado, se necessário.</span><span class="sxs-lookup"><span data-stu-id="faa32-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="faa32-107">Não é possível usar o dispositivo até que o processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="faa32-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="faa32-108">Esse não é o comportamento esperado para a falta de uma janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="faa32-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="faa32-109">Ela só ocorrerá se o dispositivo estiver desa datado por muito tempo.</span><span class="sxs-lookup"><span data-stu-id="faa32-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <a name="cause"></a><span data-ttu-id="faa32-110">Causa</span><span class="sxs-lookup"><span data-stu-id="faa32-110">Cause</span></span>

<span data-ttu-id="faa32-111">Para garantir que o Surface Hub permaneça disponível para uso durante o horário comercial, o Hub é configurado para executar funções administrativas durante uma janela de manutenção definida no Configurações (consulte "Referências", abaixo).</span><span class="sxs-lookup"><span data-stu-id="faa32-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="faa32-112">Durante esse período de manutenção, o Hub instala automaticamente todas as atualizações disponíveis por meio do Windows Update ou Windows Update for Business (WUfB).</span><span class="sxs-lookup"><span data-stu-id="faa32-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Update for Business (WUfB).</span></span> <span data-ttu-id="faa32-113">Depois que as atualizações são concluídas, o Hub pode ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="faa32-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="faa32-114">As atualizações só poderão ser instaladas durante a janela de manutenção se o Surface Hub estiver ligado, mas não estiver em uso ou reservado.</span><span class="sxs-lookup"><span data-stu-id="faa32-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="faa32-115">Por exemplo, se o Surface Hub estiver agendado para uma reunião que dura 24 horas, todas as atualizações agendadas para serem instaladas serão adiadas até que o Hub seja disponibilizado durante a próxima janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="faa32-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="faa32-116">Se o Hub continuar ocupado e perder várias janelas de manutenção, o Hub começará a instalar e baixar atualizações.</span><span class="sxs-lookup"><span data-stu-id="faa32-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="faa32-117">Isso pode ocorrer durante ou fora da janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="faa32-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="faa32-118">Depois que o download e a instalação tiver começado, o dispositivo poderá ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="faa32-118">Once the download and installation has begun, the device may restart.</span></span>

## <a name="to-avoid-this-issue"></a><span data-ttu-id="faa32-119">Para evitar esse problema</span><span class="sxs-lookup"><span data-stu-id="faa32-119">To avoid this issue</span></span>

<span data-ttu-id="faa32-120">É importante que você reserve o tempo de manutenção para Surface Hub executar funções administrativas.</span><span class="sxs-lookup"><span data-stu-id="faa32-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="faa32-121">A reserva do Surface Hub intervalos de 24 horas ou o uso do dispositivo durante a janela de manutenção atrasa a instalação de atualizações.</span><span class="sxs-lookup"><span data-stu-id="faa32-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="faa32-122">Recomendamos que você não use ou reserve o Hub durante o período de manutenção agendado.</span><span class="sxs-lookup"><span data-stu-id="faa32-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="faa32-123">Uma janela de duas horas deve ser reservada para atualização.</span><span class="sxs-lookup"><span data-stu-id="faa32-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="faa32-124">Uma opção que você pode usar para controlar a disponibilidade de atualizações é Windows Update for Business.</span><span class="sxs-lookup"><span data-stu-id="faa32-124">One option that you can use to control the availability of updates is Windows Update for Business.</span></span>

## <a name="learn-more"></a><span data-ttu-id="faa32-125">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="faa32-125">Learn more</span></span>
 
- [<span data-ttu-id="faa32-126">Atualizar o Surface Hub</span><span class="sxs-lookup"><span data-stu-id="faa32-126">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 
- [<span data-ttu-id="faa32-127">Janela de manutenção</span><span class="sxs-lookup"><span data-stu-id="faa32-127">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 
