---
title: Configuração de Limite de Bateria (Surface)
description: O Limite de Bateria é uma configuração UEFI que altera a forma como a bateria do dispositivo Surface é carregada e pode prolongar sua longevidade.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271138"
---
# <span data-ttu-id="5704d-103">Configuração de limite da bateria</span><span class="sxs-lookup"><span data-stu-id="5704d-103">Battery Limit setting</span></span>

<span data-ttu-id="5704d-104">A opção limite de bateria é uma configuração UEFI que altera como a bateria do dispositivo Surface é carregada e pode prolongar sua longevidade.</span><span class="sxs-lookup"><span data-stu-id="5704d-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="5704d-105">Essa configuração é recomendada em casos em que o dispositivo está continuamente conectado à energia, por exemplo, quando os dispositivos são integrados a soluções de quiosque.</span><span class="sxs-lookup"><span data-stu-id="5704d-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="5704d-106">Como funciona o Limite de Bateria</span><span class="sxs-lookup"><span data-stu-id="5704d-106">How Battery Limit works</span></span>

<span data-ttu-id="5704d-107">Definir o dispositivo no Limite de Bateria altera o protocolo para carregar a bateria do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5704d-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="5704d-108">Quando o Limite da Bateria estiver habilitado, a carga da bateria será limitada a 50% de sua capacidade máxima.</span><span class="sxs-lookup"><span data-stu-id="5704d-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="5704d-109">O nível de cobrança relatado no Windows refletirá esse limite.</span><span class="sxs-lookup"><span data-stu-id="5704d-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="5704d-110">Portanto, ele mostrará que a bateria é carregada até 50% e não será carregada além desse limite.</span><span class="sxs-lookup"><span data-stu-id="5704d-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="5704d-111">Se você habilitar o Limite de Bateria enquanto o dispositivo estiver acima de 50% da carga, o ícone de bateria mostrará que o dispositivo está conectado, mas descarregando até que o dispositivo atinja 50% de sua capacidade máxima de carga.</span><span class="sxs-lookup"><span data-stu-id="5704d-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="5704d-112">Dispositivos com suporte</span><span class="sxs-lookup"><span data-stu-id="5704d-112">Supported devices</span></span>

<span data-ttu-id="5704d-113">A configuração UEFI de Limite de Bateria foi criada nos dispositivos Surface mais recentes, incluindo o Surface Pro 7+, o Surface Pro 7 e o Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5704d-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="5704d-114">Dispositivos anteriores exigem uma atualização de [firmware UEFI](manage-surface-driver-and-firmware-updates.md)do Surface, disponível por meio do Windows Update ou por meio dos pacotes de driver e firmware MSI no site de suporte [do Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)</span><span class="sxs-lookup"><span data-stu-id="5704d-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="5704d-115">Marque [Habilitar "Limite](https://support.microsoft.com/help/4464941) de Bateria" para dispositivos Surface que precisam estar conectados por longos períodos de tempo para a versão UEFI específica do Surface necessária para cada dispositivo compatível.</span><span class="sxs-lookup"><span data-stu-id="5704d-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="5704d-116">Habilitando o limite de bateria no UeFI do Surface (Surface Pro 4 e posterior)</span><span class="sxs-lookup"><span data-stu-id="5704d-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="5704d-117">A configuração de Limite de Bateria UEFI do Surface pode ser configurada inicializando-se no UEFI do Surface (**Ligar/Desligar + Vol Up** ao ligar o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="5704d-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="5704d-118">Escolha **a configuração**de inicialização e, em **Opções Avançadas,** alterne a opção Habilitar Modo de Limite **de Bateria** para **Ativado.**</span><span class="sxs-lookup"><span data-stu-id="5704d-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Opções avançadas de limite de bateria](images/enable-bl.png) 

## <span data-ttu-id="5704d-120">Habilitando o limite de bateria no Surface Go e no Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="5704d-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="5704d-121">A configuração do Limite de Bateria do Surface pode ser configurada inicializando-se no UEFI do Surface (**Power + Vol Up** ao ligar o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="5704d-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="5704d-122">Escolha **a configuração**de inicialização e, em **Modo de Quiosque,** mova o controle deslizante para a direita para definir o Limite de Bateria como **Habilitado.**</span><span class="sxs-lookup"><span data-stu-id="5704d-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Limite de bateria do modo de quiosque no Surface Go](images/go-batterylimit.png) 

## <span data-ttu-id="5704d-124">Habilitando o limite de bateria no Surface UEFI (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="5704d-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="5704d-125">A configuração de Limite de Bateria UEFI do Surface pode ser configurada inicializando-se no UEFI do Surface (**Ligar/Desligar + Vol Up** ao ligar o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="5704d-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="5704d-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="5704d-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Captura de tela das opções avançadas](images/enable-bl-sp3.png) 

![Opções avançadas](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="5704d-129">Habilitando o limite de bateria usando scripts do PowerShell do Surface Enterprise Management Mode (SEMM) ou do firmware do Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="5704d-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="5704d-130">O limite de bateria UEFI do Surface também está disponível para configuração por meio dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="5704d-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="5704d-131">Surface Pro 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="5704d-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="5704d-132">Configurador UEFI do Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="5704d-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="5704d-133">Scripts do Powershell do Surface UEFI Manager (SEMM_Powershell.zip) nos [downloads](https://www.microsoft.com/download/details.aspx?id=46703) do Surface Tools for IT</span><span class="sxs-lookup"><span data-stu-id="5704d-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="5704d-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="5704d-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="5704d-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="5704d-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="5704d-136">Usando o configurador UEFI do Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="5704d-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="5704d-137">Para configurar o modo Limite de Bateria, defina a configuração Substituições de **Quiosque** na página configuração Configurações **Avançadas** no SEMM (Surface Pro 4 e posterior).</span><span class="sxs-lookup"><span data-stu-id="5704d-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Captura de tela das configurações avançadas](images/semm-bl.png)

### <span data-ttu-id="5704d-139">Usando scripts do PowerShell do Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="5704d-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="5704d-140">O recurso de limite de bateria é controlado por meio da seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="5704d-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="5704d-141">**Descrição**: Esquema de gerenciamento ativo para o padrão de uso da bateria</span><span class="sxs-lookup"><span data-stu-id="5704d-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="5704d-142">**Padrão:**</span><span class="sxs-lookup"><span data-stu-id="5704d-142">**Default**:</span></span>  `0` 

<span data-ttu-id="5704d-143">De configurar isso para `1` habilitar o Limite de Bateria.</span><span class="sxs-lookup"><span data-stu-id="5704d-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="5704d-144">Usando ferramentas de firmware do Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="5704d-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="5704d-145">O recurso de limite de bateria é controlado por meio da seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="5704d-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="5704d-146">**Nome**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="5704d-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="5704d-147">**Descrição**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="5704d-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="5704d-148">**Valor atual:**</span><span class="sxs-lookup"><span data-stu-id="5704d-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="5704d-149">**Valor padrão:**</span><span class="sxs-lookup"><span data-stu-id="5704d-149">**Default Value**:</span></span> `0`

<span data-ttu-id="5704d-150">**Valor Proposto:**</span><span class="sxs-lookup"><span data-stu-id="5704d-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="5704d-151">De configurar isso para `1` habilitar o Limite de Bateria.</span><span class="sxs-lookup"><span data-stu-id="5704d-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="5704d-152">Para definir essa configuração, você deve usar [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="5704d-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

