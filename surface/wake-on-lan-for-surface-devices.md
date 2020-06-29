---
title: Wake on LAN para dispositivos Surface (Surface)
description: Veja como você pode usar o Wake on LAN para ativar dispositivos remotamente para executar tarefas de gerenciamento ou manutenção ou para habilitar as soluções de gerenciamento automaticamente – mesmo se os dispositivos estiverem desligados.
keywords: atualização, implantação, Driver, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830480"
---
# <span data-ttu-id="43412-104">Wake On LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="43412-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="43412-105">Dispositivos Surface que executam o Windows 10, versão 1607 (também conhecida como atualização de aniversário do Windows 10) ou posterior e usam um adaptador Ethernet Surface para se conectar a uma rede com fio, são capazes de Wake on LAN (WOL) do modo de espera conectado.</span><span class="sxs-lookup"><span data-stu-id="43412-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="43412-106">Com o WOL, você pode ativar dispositivos remotamente para executar tarefas de gerenciamento ou manutenção ou habilitar soluções de gerenciamento (como o Microsoft Endpoint Configuration Manager) automaticamente.</span><span class="sxs-lookup"><span data-stu-id="43412-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="43412-107">Por exemplo, você pode implantar aplicativos em dispositivos de superfície à esquerda encaixados com um Dock Dock ou Surface Pro 3 Docking Station usando o Gerenciador de configuração do Microsoft Endpoint durante uma janela no meio da noite, quando o escritório está vazio.</span><span class="sxs-lookup"><span data-stu-id="43412-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="43412-108">Os dispositivos Surface devem estar conectados à alimentação CA e no modo de espera conectado (Sleep) para dar suporte ao WOL.</span><span class="sxs-lookup"><span data-stu-id="43412-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="43412-109">O WOL não é possível em dispositivos que estejam em hibernação ou desligado.</span><span class="sxs-lookup"><span data-stu-id="43412-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="43412-110">Dispositivos com suporte</span><span class="sxs-lookup"><span data-stu-id="43412-110">Supported devices</span></span>

<span data-ttu-id="43412-111">Os seguintes dispositivos são compatíveis com o WOL:</span><span class="sxs-lookup"><span data-stu-id="43412-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="43412-112">Adaptador Ethernet Surface</span><span class="sxs-lookup"><span data-stu-id="43412-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="43412-113">Surface USB-C para Ethernet e adaptador USB</span><span class="sxs-lookup"><span data-stu-id="43412-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="43412-114">Encaixe do Surface</span><span class="sxs-lookup"><span data-stu-id="43412-114">Surface Dock</span></span>
* <span data-ttu-id="43412-115">Estação de acoplamento Surface para Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="43412-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="43412-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="43412-116">Surface 3</span></span>
* <span data-ttu-id="43412-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="43412-117">Surface Pro 3</span></span>
* <span data-ttu-id="43412-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="43412-118">Surface Pro 4</span></span>
* <span data-ttu-id="43412-119">Surface pro (5ª gen)</span><span class="sxs-lookup"><span data-stu-id="43412-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="43412-120">Surface pro (5ª geração) com LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="43412-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="43412-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="43412-121">Surface Book</span></span>
* <span data-ttu-id="43412-122">Laptop Surface (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="43412-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="43412-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="43412-123">Surface Pro 6</span></span>
* <span data-ttu-id="43412-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="43412-124">Surface Book 2</span></span>
* <span data-ttu-id="43412-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="43412-125">Surface Laptop 2</span></span>
* <span data-ttu-id="43412-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="43412-126">Surface Go</span></span>
* <span data-ttu-id="43412-127">Surface Go com LTE Avançado</span><span class="sxs-lookup"><span data-stu-id="43412-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="43412-128">Surface Studio 2 (veja as instruções do Surface Studio 2 abaixo)</span><span class="sxs-lookup"><span data-stu-id="43412-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="43412-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="43412-129">Surface Pro 7</span></span>
* <span data-ttu-id="43412-130">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="43412-130">Surface Laptop 3</span></span>

## <span data-ttu-id="43412-131">Driver WOL</span><span class="sxs-lookup"><span data-stu-id="43412-131">WOL driver</span></span>

<span data-ttu-id="43412-132">Para habilitar o suporte a WOL em dispositivos Surface, é necessário um driver específico para o adaptador de Ethernet Surface.</span><span class="sxs-lookup"><span data-stu-id="43412-132">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="43412-133">Este driver não está incluído no driver padrão e no pacote de firmware para dispositivos Surface – você deve baixá-lo e instalá-lo separadamente.</span><span class="sxs-lookup"><span data-stu-id="43412-133">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="43412-134">Você pode baixar o driver WOL de Surface (SurfaceWOL.msi) na página [Surface Tools para it](https://www.microsoft.com/download/details.aspx?id=46703) no centro de download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43412-134">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="43412-135">Você pode executar este arquivo do Microsoft Windows Installer (. msi) em um dispositivo Surface para instalar o driver WOL de Surface, ou pode distribuí-lo a dispositivos Surface com uma solução de implantação de aplicativo, como o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="43412-135">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="43412-136">Para incluir o driver WOL de Surface durante a implantação, você pode instalar o arquivo. msi como um aplicativo durante o processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="43412-136">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="43412-137">Você também pode extrair os arquivos de driver WOL da superfície para incluí-los no processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="43412-137">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="43412-138">Por exemplo, você pode incluí-los em seu compartilhamento de implantação do Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="43412-138">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="43412-139">Você pode ler mais sobre a implantação de superfície com [o MDT em implantar o Windows 10 em dispositivos de superfície com o kit de ferramentas de implantação da Microsoft](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span><span class="sxs-lookup"><span data-stu-id="43412-139">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="43412-140">Durante a instalação do SurfaceWOL.msi, a chave do registro a seguir é definida como um valor 1, que permite a fácil identificação de sistemas em que o driver WOL foi instalado.</span><span class="sxs-lookup"><span data-stu-id="43412-140">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="43412-141">Se você optou por extrair e instalar esses drivers separadamente durante a implantação, essa chave do registro não será configurada e deve ser configurada manualmente ou com um script.</span><span class="sxs-lookup"><span data-stu-id="43412-141">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="43412-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="43412-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="43412-143">Para extrair o conteúdo de SurfaceWOL.msi, use a opção de instalação administrativa do MSIExec (**/a**), conforme mostrado no exemplo a seguir, para extrair o conteúdo para a pasta C:\WOL\:</span><span class="sxs-lookup"><span data-stu-id="43412-143">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="43412-144">Instruções do Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="43412-144">Surface Studio 2 instructions</span></span>

<span data-ttu-id="43412-145">Para habilitar o WOL no Surface Studio 2, você deve usar o procedimento a seguir</span><span class="sxs-lookup"><span data-stu-id="43412-145">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="43412-146">Crie as seguintes chaves do registro:</span><span class="sxs-lookup"><span data-stu-id="43412-146">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="43412-147">Execute o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="43412-147">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="43412-148">Usando o WOL da superfície</span><span class="sxs-lookup"><span data-stu-id="43412-148">Using Surface WOL</span></span>

<span data-ttu-id="43412-149">O driver WOL de Surface está em conformidade com o padrão WOL, no qual o dispositivo é wokendo por uma comunicação de rede especial conhecida como pacote mágico.</span><span class="sxs-lookup"><span data-stu-id="43412-149">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="43412-150">O pacote mágico consiste em 6 bytes de 255 (ou FF em hexadecimal) seguido por 16 repetições do endereço MAC do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="43412-150">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="43412-151">Você pode ler mais sobre o pacote mágico e o padrão WOL na [Wikipédia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span><span class="sxs-lookup"><span data-stu-id="43412-151">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="43412-152">Para enviar um pacote mágico e ativar um dispositivo usando o WOL, você precisa saber o endereço MAC do dispositivo de destino e do adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="43412-152">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="43412-153">Como o pacote mágico não usa o protocolo de rede IP, não é possível usar o endereço IP ou o nome DNS do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43412-153">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="43412-154">Muitas soluções de gerenciamento, como o Configuration Manager, fornecem suporte interno para WOL.</span><span class="sxs-lookup"><span data-stu-id="43412-154">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="43412-155">Também há muitas soluções, incluindo aplicativos da Microsoft Store, módulos do PowerShell, aplicativos de terceiros e soluções de gerenciamento de terceiros que permitem que você envie um pacote mágico para ativar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43412-155">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="43412-156">Por exemplo, você pode usar o [módulo do PowerShell Wake on LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) a partir do TechNet Script Center.</span><span class="sxs-lookup"><span data-stu-id="43412-156">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="43412-157">Depois que um dispositivo foi wokendo com um pacote mágico, o dispositivo retornará ao estado de suspensão se um aplicativo não estiver bloqueando ativamente a suspensão no sistema ou se a chave do registro AllowSystemRequiredPowerRequests não estiver configurada como 1, o que permite que os aplicativos impeçam a suspensão.</span><span class="sxs-lookup"><span data-stu-id="43412-157">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="43412-158">Consulte a seção [Driver WOL](#wol-driver) deste artigo para obter mais informações sobre essa chave do registro.</span><span class="sxs-lookup"><span data-stu-id="43412-158">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
