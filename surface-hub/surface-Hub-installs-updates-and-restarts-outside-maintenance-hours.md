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
# <span data-ttu-id="40051-104">O Surface Hub pode instalar atualizações e reiniciar fora do horário de manutenção</span><span class="sxs-lookup"><span data-stu-id="40051-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="40051-105">Em circunstâncias específicas, o Surface Hub instala atualizações durante o horário comercial, em vez de durante a janela de manutenção regular.</span><span class="sxs-lookup"><span data-stu-id="40051-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="40051-106">Em seguida, o dispositivo reinicia se for necessário.</span><span class="sxs-lookup"><span data-stu-id="40051-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="40051-107">Não é possível usar o dispositivo até que o processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="40051-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="40051-108">Esse não é um comportamento esperado para faltar uma janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="40051-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="40051-109">Isso ocorre apenas se o dispositivo estiver desatualizado por muito tempo.</span><span class="sxs-lookup"><span data-stu-id="40051-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="40051-110">Causa</span><span class="sxs-lookup"><span data-stu-id="40051-110">Cause</span></span>
<span data-ttu-id="40051-111">Para garantir que o Surface Hub permaneça disponível para uso durante o horário comercial, o Hub está configurado para executar funções administrativas durante uma janela de manutenção definida em configurações (consulte "referências" abaixo).</span><span class="sxs-lookup"><span data-stu-id="40051-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="40051-112">Durante esse período de manutenção, o Hub instala automaticamente todas as atualizações disponíveis por meio do Windows Update ou do WSUS (Windows Server Update Service).</span><span class="sxs-lookup"><span data-stu-id="40051-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="40051-113">Depois que as atualizações forem concluídas, o Hub poderá ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="40051-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="40051-114">As atualizações podem ser instaladas durante a janela de manutenção apenas se o Surface Hub estiver ativado, mas não estiver em uso ou reservado.</span><span class="sxs-lookup"><span data-stu-id="40051-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="40051-115">Por exemplo, se o Surface Hub estiver agendado para uma reunião que dura 24 horas, todas as atualizações agendadas para serem instaladas serão adiadas até que o Hub esteja disponível durante a próxima janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="40051-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="40051-116">Se o Hub continuar ocupado e perder várias janelas de manutenção, o Hub começará a instalar e baixar as atualizações.</span><span class="sxs-lookup"><span data-stu-id="40051-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="40051-117">Isso pode ocorrer durante ou fora da janela de manutenção.</span><span class="sxs-lookup"><span data-stu-id="40051-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="40051-118">Depois que o download e a instalação começarem, o dispositivo poderá ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="40051-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="40051-119">Para evitar esse problema</span><span class="sxs-lookup"><span data-stu-id="40051-119">To avoid this issue</span></span>

<span data-ttu-id="40051-120">É importante definir o tempo de manutenção do Surface Hub para executar funções administrativas.</span><span class="sxs-lookup"><span data-stu-id="40051-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="40051-121">Reservar o Surface Hub para intervalos de 24 horas ou usar o dispositivo durante a janela de manutenção atrasa a instalação das atualizações.</span><span class="sxs-lookup"><span data-stu-id="40051-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="40051-122">Recomendamos que você não use ou reserve o Hub durante o período de manutenção programada.</span><span class="sxs-lookup"><span data-stu-id="40051-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="40051-123">Uma janela de duas horas deve ser reservada para atualização.</span><span class="sxs-lookup"><span data-stu-id="40051-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="40051-124">Uma opção que você pode usar para controlar a disponibilidade de atualizações é o WSUS (Windows Server Update Service).</span><span class="sxs-lookup"><span data-stu-id="40051-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="40051-125">O WSUS oferece controle sobre quais atualizações estão instaladas e quando.</span><span class="sxs-lookup"><span data-stu-id="40051-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="40051-126">Referências</span><span class="sxs-lookup"><span data-stu-id="40051-126">References</span></span> 
 
[<span data-ttu-id="40051-127">Atualizar o Surface Hub</span><span class="sxs-lookup"><span data-stu-id="40051-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="40051-128">Janela de manutenção</span><span class="sxs-lookup"><span data-stu-id="40051-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="40051-129">Implantar atualizações do Windows 10 usando o Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="40051-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 


