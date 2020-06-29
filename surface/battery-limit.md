---
title: Configuração de limite de bateria (Surface)
description: O limite da bateria é uma configuração de UEFI que muda a forma como a bateria do dispositivo de superfície é cobrada e pode prolongar sua longevidade.
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
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830599"
---
# <span data-ttu-id="a1d8c-103">Configuração de limite da bateria</span><span class="sxs-lookup"><span data-stu-id="a1d8c-103">Battery Limit setting</span></span>

<span data-ttu-id="a1d8c-104">A opção de limite de bateria é uma configuração de UEFI que altera a carga da bateria do dispositivo Surface e pode prolongar sua longevidade.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="a1d8c-105">Essa configuração é recomendada em casos em que o dispositivo está conectado continuamente à energia, por exemplo, quando dispositivos são integrados em soluções de quiosque.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="a1d8c-106">Como o limite de bateria funciona</span><span class="sxs-lookup"><span data-stu-id="a1d8c-106">How Battery Limit works</span></span>

<span data-ttu-id="a1d8c-107">Configurar o dispositivo com o limite de bateria altera o protocolo para carregar a bateria do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="a1d8c-108">Quando o limite da bateria estiver habilitado, a carga da bateria estará limitada a 50% de sua capacidade máxima.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="a1d8c-109">O nível de encargo informado no Windows refletirá esse limite.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="a1d8c-110">Portanto, ele mostrará que a bateria será cobrada até 50% e não será cobrada além desse limite.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="a1d8c-111">Se você habilitar o limite de bateria enquanto o dispositivo estiver acima de 50% do encargo, o ícone de bateria mostrará que o dispositivo está conectado, mas que será descarregado até que o dispositivo atinja 50% da sua capacidade máxima de cobrança.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="a1d8c-112">Dispositivos com suporte</span><span class="sxs-lookup"><span data-stu-id="a1d8c-112">Supported devices</span></span>
<span data-ttu-id="a1d8c-113">A configuração UEFI de limite de bateria está incorporada aos dispositivos de superfície mais recentes, incluindo Surface Pro 7 e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7 and Surface Laptop 3.</span></span> <span data-ttu-id="a1d8c-114">Dispositivos anteriores exigem uma [atualização de firmware da superfície de superfície](manage-surface-driver-and-firmware-updates.md), disponível por meio do Windows Update ou por meio do driver msi e pacotes de firmware no [site de suporte do Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span><span class="sxs-lookup"><span data-stu-id="a1d8c-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="a1d8c-115">Verifique [habilitar "limite de bateria" para dispositivos Surface que precisam ser conectados por períodos prolongados](https://support.microsoft.com/help/4464941) para a versão UEFI de superfície específica necessária para cada dispositivo compatível.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="a1d8c-116">Habilitando o limite da bateria no Surface UEFI (Surface Pro 4 e posterior)</span><span class="sxs-lookup"><span data-stu-id="a1d8c-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="a1d8c-117">A configuração de limite de bateria UEFI de Surface pode ser configurada na inicialização do Surface UEFI (**Power + Vol up** ao ligar o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="a1d8c-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="a1d8c-118">Escolha **configuração de inicialização**e, em **Opções avançadas**, ative o **modo de limite de bateria** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Captura de tela de opções avançadas](images/enable-bl.png) 

## <span data-ttu-id="a1d8c-120">Habilitando o limite de bateria no Surface Go e na superfície 2</span><span class="sxs-lookup"><span data-stu-id="a1d8c-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="a1d8c-121">A configuração de limite de bateria do Surface pode ser configurada na inicialização do Surface UEFI (**Power + Vol up** ao ligar o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="a1d8c-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="a1d8c-122">Escolha **configuração de inicialização**e, em **modo de quiosque**, mova o controle deslizante para a direita para definir o limite de bateria como **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Captura de tela do modo de quiosque de bateria no Surface go](images/go-batterylimit.png) 

## <span data-ttu-id="a1d8c-124">Habilitando o limite da bateria no Surface UEFI (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="a1d8c-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="a1d8c-125">A configuração de limite de bateria UEFI de Surface pode ser configurada na inicialização do Surface UEFI (**Power + Vol up** ao ligar o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="a1d8c-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="a1d8c-126">Escolha **modo de quiosque**, selecione **limite de bateria**e escolha **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Captura de tela de opções avançadas](images/enable-bl-sp3.png) 

![Captura de tela de opções avançadas](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="a1d8c-129">Habilitando o limite de bateria usando o modo de gerenciamento do Surface Enterprise (SEMM) ou scripts do PowerShell do Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="a1d8c-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="a1d8c-130">O limite de bateria UEFI da superfície também está disponível para configuração por meio dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="a1d8c-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="a1d8c-131">Surface Pro 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="a1d8c-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="a1d8c-132">Configurador UEFI da Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="a1d8c-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="a1d8c-133">Scripts do PowerShell do Surface Manager do Surface Manager (SEMM_Powershell.zip) nas [ferramentas de superfície para downloads de ti](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="a1d8c-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="a1d8c-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="a1d8c-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="a1d8c-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="a1d8c-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="a1d8c-136">Usando o Microsoft Surface UEFI Configuration</span><span class="sxs-lookup"><span data-stu-id="a1d8c-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="a1d8c-137">Para configurar o modo de limite de bateria, defina a configuração de o **quiosque substituis** na página configuração **avançada de configurações** no Semm (Surface Pro 4 e posterior).</span><span class="sxs-lookup"><span data-stu-id="a1d8c-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Captura de tela de configurações avançadas](images/semm-bl.png)

### <span data-ttu-id="a1d8c-139">Usar scripts do PowerShell Surface Manager do Gerenciador</span><span class="sxs-lookup"><span data-stu-id="a1d8c-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="a1d8c-140">O recurso de limite de bateria é controlado por meio da seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="a1d8c-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="a1d8c-141">**Descrição**: esquema de gerenciamento ativo para o padrão de uso da bateria</span><span class="sxs-lookup"><span data-stu-id="a1d8c-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="a1d8c-142">**Padrão**:</span><span class="sxs-lookup"><span data-stu-id="a1d8c-142">**Default**:</span></span>  `0` 

<span data-ttu-id="a1d8c-143">Defina como `1` para habilitar o limite de bateria.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="a1d8c-144">Usando as ferramentas de firmware do Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="a1d8c-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="a1d8c-145">O recurso de limite de bateria é controlado por meio da seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="a1d8c-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="a1d8c-146">**Nome**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="a1d8c-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="a1d8c-147">**Descrição**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="a1d8c-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="a1d8c-148">**Valor atual**:</span><span class="sxs-lookup"><span data-stu-id="a1d8c-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="a1d8c-149">**Valor padrão**:</span><span class="sxs-lookup"><span data-stu-id="a1d8c-149">**Default Value**:</span></span> `0`

<span data-ttu-id="a1d8c-150">**Valor proposto**:</span><span class="sxs-lookup"><span data-stu-id="a1d8c-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="a1d8c-151">Defina como `1` para habilitar o limite de bateria.</span><span class="sxs-lookup"><span data-stu-id="a1d8c-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="a1d8c-152">Para definir essa configuração, você deve usar [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="a1d8c-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

