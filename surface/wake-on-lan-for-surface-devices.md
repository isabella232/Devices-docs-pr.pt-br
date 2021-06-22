---
title: Wake On LAN para dispositivos Surface
description: Veja como você pode usar Wake On LAN para acordar remotamente dispositivos para executar tarefas de gerenciamento automaticamente.
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613791"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="e63ee-104">Wake On LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="e63ee-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="e63ee-105">Para manter os dispositivos totalmente atualizados, os administradores de TI precisam ser capazes de gerenciar dispositivos quando não estão em uso, normalmente durante janelas de manutenção noturna.</span><span class="sxs-lookup"><span data-stu-id="e63ee-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="e63ee-106">O Wake on LAN (WOL) permite que os administradores acordem remotamente os dispositivos e executem tarefas de gerenciamento automaticamente com Microsoft Endpoint Manager ou soluções de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e63ee-106">Wake on LAN (WOL) enables admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or third-party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="e63ee-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e63ee-107">Requirements</span></span>

<span data-ttu-id="e63ee-108">Os dispositivos devem estar conectados à energia ac e ter uma conexão com fio com um dos seguintes adaptadores Ethernet compatíveis:</span><span class="sxs-lookup"><span data-stu-id="e63ee-108">Devices must be connected to AC power and have a wired connection with one of the following compatible Ethernet adapters:</span></span>

- <span data-ttu-id="e63ee-109">Adaptador Ethernet Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="e63ee-109">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>
- <span data-ttu-id="e63ee-110">Adaptador Surface Ethernet</span><span class="sxs-lookup"><span data-stu-id="e63ee-110">Surface Ethernet Adapter</span></span>
- <span data-ttu-id="e63ee-111">Surface USB-C para Ethernet e Adaptador USB</span><span class="sxs-lookup"><span data-stu-id="e63ee-111">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="e63ee-112">Microsoft USB-C Travel Adapter Hub</span><span class="sxs-lookup"><span data-stu-id="e63ee-112">Microsoft USB-C Travel Adapter Hub</span></span>
- <span data-ttu-id="e63ee-113">Encaixe do Surface</span><span class="sxs-lookup"><span data-stu-id="e63ee-113">Surface Dock</span></span>
- <span data-ttu-id="e63ee-114">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="e63ee-114">Surface Dock 2</span></span>

> [!NOTE]
> <span data-ttu-id="e63ee-115">O Surface Dock 2 oferece o melhor suporte para Wake on LAN sem a necessidade de qualquer configuração de TI adicional.</span><span class="sxs-lookup"><span data-stu-id="e63ee-115">Surface Dock 2 provides the best support for Wake on LAN without the need for any additional IT configuration.</span></span> <span data-ttu-id="e63ee-116">Para saber mais, confira [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)</span><span class="sxs-lookup"><span data-stu-id="e63ee-116">To learn more, see [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="e63ee-117">Como funciona</span><span class="sxs-lookup"><span data-stu-id="e63ee-117">How it works</span></span>

<span data-ttu-id="e63ee-118">Quando não estiver em uso, os dispositivos Surface entram em um estado ocioso e com baixa potência conhecido como Espera Moderna ou Espera Conectada.</span><span class="sxs-lookup"><span data-stu-id="e63ee-118">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="e63ee-119">Os administradores de IT podem disparar remotamente dispositivos usando uma solicitação de alerta (pacote mágico) que contém o endereço MAC (Controle de Acesso de Mídia) do dispositivo Surface de destino.</span><span class="sxs-lookup"><span data-stu-id="e63ee-119">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="e63ee-120">Muitas soluções de gerenciamento, como Microsoft Endpoint Configuration Manager e aplicativos de terceiros Microsoft Store oferecem suporte integrado para o WOL.</span><span class="sxs-lookup"><span data-stu-id="e63ee-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="e63ee-121">Para saber mais sobre como acordar dispositivos com o Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span><span class="sxs-lookup"><span data-stu-id="e63ee-121">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>

<span data-ttu-id="e63ee-122">O suporte para Wake on LAN varia dependendo do estado de sono: Espera conectada ou hibernação (estado de energia S4).</span><span class="sxs-lookup"><span data-stu-id="e63ee-122">Support for Wake on LAN varies depending on sleep state:  Connected Standby or Hibernation (S4 power state).</span></span>

## <a name="connected-standby"></a><span data-ttu-id="e63ee-123">Espera conectada</span><span class="sxs-lookup"><span data-stu-id="e63ee-123">Connected Standby</span></span>

<span data-ttu-id="e63ee-124">Por padrão, Windows 10 suporta Wake on LAN para dispositivos Surface em Espera Conectada.</span><span class="sxs-lookup"><span data-stu-id="e63ee-124">By default, Windows 10 supports Wake on LAN for Surface devices in Connected Standby.</span></span>

### <a name="supported-surface-devices---connected-standby"></a><span data-ttu-id="e63ee-125">Dispositivos Surface com suporte - Espera Conectada</span><span class="sxs-lookup"><span data-stu-id="e63ee-125">Supported Surface devices - Connected Standby</span></span>

- <span data-ttu-id="e63ee-126">Surface Laptop 4 (somente processadores Intel)</span><span class="sxs-lookup"><span data-stu-id="e63ee-126">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="e63ee-127">Surface Laptop 3 (somente processadores Intel)</span><span class="sxs-lookup"><span data-stu-id="e63ee-127">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="e63ee-128">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="e63ee-128">Surface Pro 7+</span></span>
- <span data-ttu-id="e63ee-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="e63ee-129">Surface Pro 7</span></span>
- <span data-ttu-id="e63ee-130">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="e63ee-130">Surface Pro X</span></span>
- <span data-ttu-id="e63ee-131">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="e63ee-131">Surface Go 2</span></span>
- <span data-ttu-id="e63ee-132">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="e63ee-132">Surface Laptop Go</span></span>
- <span data-ttu-id="e63ee-133">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="e63ee-133">Surface Book 3</span></span>

## <a name="hibernation"></a><span data-ttu-id="e63ee-134">Hibernação</span><span class="sxs-lookup"><span data-stu-id="e63ee-134">Hibernation</span></span>

<span data-ttu-id="e63ee-135">Para acordar os dispositivos fora da Hibernação, é necessário habiler uma configuração de política UEFI por meio do [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (não necessário para dispositivos conectados ao Surface Dock 2).</span><span class="sxs-lookup"><span data-stu-id="e63ee-135">To wake devices out of Hibernation requires enabling a UEFI policy setting via [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (not required for devices connected to Surface Dock 2).</span></span>

### <a name="supported-surface-devices---hibernation"></a><span data-ttu-id="e63ee-136">Dispositivos Surface com suporte - Hibernação</span><span class="sxs-lookup"><span data-stu-id="e63ee-136">Supported Surface devices - Hibernation</span></span>

- <span data-ttu-id="e63ee-137">Surface Laptop 4 (somente processadores Intel)</span><span class="sxs-lookup"><span data-stu-id="e63ee-137">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="e63ee-138">Surface Laptop 3 (somente processadores Intel)</span><span class="sxs-lookup"><span data-stu-id="e63ee-138">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="e63ee-139">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="e63ee-139">Surface Pro 7+</span></span>
- <span data-ttu-id="e63ee-140">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="e63ee-140">Surface Pro 7</span></span>
- <span data-ttu-id="e63ee-141">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="e63ee-141">Surface Laptop Go</span></span>
- <span data-ttu-id="e63ee-142">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="e63ee-142">Surface Book 3</span></span>

### <a name="to-enable-wake-on-lan-uefi-setting"></a><span data-ttu-id="e63ee-143">Para habilitar a configuração Wake on LAN UEFI</span><span class="sxs-lookup"><span data-stu-id="e63ee-143">To enable Wake on LAN UEFI setting</span></span>

<span data-ttu-id="e63ee-144">Para habilitar a configuração Wake on LAN UEFI, você precisa registrar dispositivos de destino no SEMM, criar um pacote de configuração e aplicar o pacote aos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e63ee-144">To enable the Wake on LAN UEFI setting you need to enroll target devices into SEMM, create a configuration package, and apply the package to the devices.</span></span> <span data-ttu-id="e63ee-145">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="e63ee-145">For more information, refer to:</span></span>

- [<span data-ttu-id="e63ee-146">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="e63ee-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="e63ee-147">Registrar e configurar dispositivos Surface com o SEMM</span><span class="sxs-lookup"><span data-stu-id="e63ee-147">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)

1. <span data-ttu-id="e63ee-148">Baixe e instale [**o Configurador UEFI do Surface.**](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="e63ee-148">Download and install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
2. <span data-ttu-id="e63ee-149">Selecione **Iniciar**  >  **Pacote de**  >  **Configuração Criar**  > **+ Proteção de Certificado.**</span><span class="sxs-lookup"><span data-stu-id="e63ee-149">Select **Start** > **Configuration Package** > **Create** >**+ Certificate Protection**.</span></span>
3. <span data-ttu-id="e63ee-150">Vá para **Configurações avançadas** e **alternar Wake on LAN** para **On**.</span><span class="sxs-lookup"><span data-stu-id="e63ee-150">Go to **Advanced settings** and switch **Wake on LAN** to **On**.</span></span>
4. <span data-ttu-id="e63ee-151">Aplique o pacote a dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="e63ee-151">Apply the package to target devices.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Habilitar a configuração da política Wake on LAN UEFI](images/wol-uefi.png)

## <a name="learn-more"></a><span data-ttu-id="e63ee-153">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="e63ee-153">Learn more</span></span>

- [<span data-ttu-id="e63ee-154">Acordar na LAN para o Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="e63ee-154">Wake on LAN for Surface Dock 2</span></span>](wake-on-lan-surface-dock2.md)
- [<span data-ttu-id="e63ee-155">Microsoft Surface USB-C para Ethernet e Adaptador USB</span><span class="sxs-lookup"><span data-stu-id="e63ee-155">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [<span data-ttu-id="e63ee-156">Adaptador Ethernet Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="e63ee-156">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
