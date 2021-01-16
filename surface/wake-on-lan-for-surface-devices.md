---
title: Wake On LAN para dispositivos Surface (Surface)
description: Veja como você pode usar o Wake On LAN para acioná-los remotamente para realizar tarefas de gerenciamento ou manutenção ou para habilitar soluções de gerenciamento automaticamente, mesmo que os dispositivos sejam desligados.
keywords: atualizar, implantar, driver, ltd, wake-on-lan
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
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271118"
---
# <span data-ttu-id="d29d0-104">Wake On LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="d29d0-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="d29d0-105">Dispositivos Surface que executem o Windows 10, versão 1607 (também conhecido como Atualização de Aniversário do Windows 10) ou posterior e usam um adaptador Ethernet do Surface para se conectar a uma rede com fio, são capazes de Wake On LAN (ETHERNET) do Modo de Espera Conectado.</span><span class="sxs-lookup"><span data-stu-id="d29d0-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="d29d0-106">Com o DRAG, você pode ativar remotamente os dispositivos para executar tarefas de gerenciamento ou manutenção ou habilitar soluções de gerenciamento (como o Microsoft Endpoint Configuration Manager) automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d29d0-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="d29d0-107">Por exemplo, você pode implantar aplicativos em dispositivos Surface à esquerda encaixados com um Surface Dock ou Uma Base de Encaixe do Surface Pro 3 usando o Microsoft Endpoint Configuration Manager durante uma janela no meio da noite, quando o escritório estiver vazio.</span><span class="sxs-lookup"><span data-stu-id="d29d0-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="d29d0-108">Os dispositivos Surface devem estar conectados à alimentação AC e em modo de espera conectado ( sleep) para dar suporte a BLUETOOTH.</span><span class="sxs-lookup"><span data-stu-id="d29d0-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="d29d0-109">NÃO é possível com dispositivos que estão em hibernação ou desligados.</span><span class="sxs-lookup"><span data-stu-id="d29d0-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="d29d0-110">Dispositivos com suporte</span><span class="sxs-lookup"><span data-stu-id="d29d0-110">Supported devices</span></span>

<span data-ttu-id="d29d0-111">Os seguintes dispositivos são compatíveis com o BLUETOOTH:</span><span class="sxs-lookup"><span data-stu-id="d29d0-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="d29d0-112">Adaptador Ethernet Surface</span><span class="sxs-lookup"><span data-stu-id="d29d0-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="d29d0-113">Surface USB-C para Ethernet e adaptador USB</span><span class="sxs-lookup"><span data-stu-id="d29d0-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="d29d0-114">Encaixe do Surface</span><span class="sxs-lookup"><span data-stu-id="d29d0-114">Surface Dock</span></span>
* <span data-ttu-id="d29d0-115">Base de Encaixe do Surface para Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d29d0-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="d29d0-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="d29d0-116">Surface 3</span></span>
* <span data-ttu-id="d29d0-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d29d0-117">Surface Pro 3</span></span>
* <span data-ttu-id="d29d0-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="d29d0-118">Surface Pro 4</span></span>
* <span data-ttu-id="d29d0-119">Surface Pro (5ª geração)</span><span class="sxs-lookup"><span data-stu-id="d29d0-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="d29d0-120">Surface Pro (5ª geração) com LTE Avançado</span><span class="sxs-lookup"><span data-stu-id="d29d0-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="d29d0-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="d29d0-121">Surface Book</span></span>
* <span data-ttu-id="d29d0-122">Surface Laptop (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="d29d0-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="d29d0-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="d29d0-123">Surface Pro 6</span></span>
* <span data-ttu-id="d29d0-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="d29d0-124">Surface Book 2</span></span>
* <span data-ttu-id="d29d0-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="d29d0-125">Surface Laptop 2</span></span>
* <span data-ttu-id="d29d0-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="d29d0-126">Surface Go</span></span>
* <span data-ttu-id="d29d0-127">Surface Go com LTE Avançado</span><span class="sxs-lookup"><span data-stu-id="d29d0-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="d29d0-128">Surface Studio 2 (consulte as instruções do Surface Studio 2 abaixo)</span><span class="sxs-lookup"><span data-stu-id="d29d0-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="d29d0-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="d29d0-129">Surface Pro 7</span></span>
* <span data-ttu-id="d29d0-130">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="d29d0-130">Surface Laptop 3</span></span>
* <span data-ttu-id="d29d0-131">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="d29d0-131">Surface Laptop Go</span></span>
* <span data-ttu-id="d29d0-132">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="d29d0-132">Surface Pro 7+</span></span>

## <span data-ttu-id="d29d0-133">Driver DELM</span><span class="sxs-lookup"><span data-stu-id="d29d0-133">WOL driver</span></span>

<span data-ttu-id="d29d0-134">Para habilitar o suporte a ETHERNET em dispositivos Surface, é necessário um driver específico para o adaptador Ethernet do Surface.</span><span class="sxs-lookup"><span data-stu-id="d29d0-134">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="d29d0-135">Esse driver não está incluído no pacote de firmware e driver padrão para dispositivos Surface – você deve baixá-lo e instalá-lo separadamente.</span><span class="sxs-lookup"><span data-stu-id="d29d0-135">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="d29d0-136">Você pode baixar o driver SURFACE SURFACE (SurfaceWOL.msi) na página Ferramentas do [Surface para](https://www.microsoft.com/download/details.aspx?id=46703) TI no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d29d0-136">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="d29d0-137">Você pode executar esse arquivo do Microsoft Windows Installer (.msi) em um dispositivo Surface para instalar o driver SURFACE USB ou distribuí-lo para dispositivos Surface com uma solução de implantação de aplicativo, como o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d29d0-137">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d29d0-138">Para incluir o driver DO SURFACE SURFACE DURANTE A implantação, você pode instalar o arquivo .msi como um aplicativo durante o processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="d29d0-138">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="d29d0-139">Você também pode extrair os arquivos de driver DO SURFACE LTD para incluí-los no processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="d29d0-139">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="d29d0-140">Por exemplo, você pode incluí-los no compartilhamento de implantação do Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="d29d0-140">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="d29d0-141">Você pode ler mais sobre a implantação do Surface com o MDT em Implantar o Windows 10 em dispositivos [Surface com o Microsoft Deployment Toolkit.](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)</span><span class="sxs-lookup"><span data-stu-id="d29d0-141">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="d29d0-142">Durante a instalação do SurfaceWOL.msi, a chave do Registro a seguir é definida como um valor 1, o que permite a identificação fácil de sistemas em que o driver DOLS foi instalado.</span><span class="sxs-lookup"><span data-stu-id="d29d0-142">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="d29d0-143">Se você optar por extrair e instalar esses drivers separadamente durante a implantação, essa chave do Registro não será configurada e deverá ser configurada manualmente ou com um script.</span><span class="sxs-lookup"><span data-stu-id="d29d0-143">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="d29d0-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="d29d0-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="d29d0-145">Para extrair o conteúdo do SurfaceWOL.msi, use a opção de instalação administrativa MSIExec (**/a**), conforme mostrado no exemplo a seguir, para extrair o conteúdo para a pasta C:\IBM\:</span><span class="sxs-lookup"><span data-stu-id="d29d0-145">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="d29d0-146">Instruções do Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="d29d0-146">Surface Studio 2 instructions</span></span>

<span data-ttu-id="d29d0-147">Para habilitar o RECURSO NO Surface Studio 2, você deve usar o procedimento a seguir</span><span class="sxs-lookup"><span data-stu-id="d29d0-147">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="d29d0-148">Crie as seguintes chaves do Registro:</span><span class="sxs-lookup"><span data-stu-id="d29d0-148">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="d29d0-149">Execute o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="d29d0-149">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="d29d0-150">Usando o Surface SURFACE SURFACE</span><span class="sxs-lookup"><span data-stu-id="d29d0-150">Using Surface WOL</span></span>

<span data-ttu-id="d29d0-151">O driver SURFACEFORM está em conformidade com o padrão PORTAL, por meio do qual o dispositivo é comunicado por uma comunicação de rede especial conhecida como um pacote mágico.</span><span class="sxs-lookup"><span data-stu-id="d29d0-151">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="d29d0-152">O pacote clássico consiste em 6 bytes de 255 (ou FF em hexadecimal) seguidos por 16 repetições do endereço MAC do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="d29d0-152">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="d29d0-153">Você pode ler mais sobre o pacote clássico e o padrão DELM na [Wikipédia.](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)</span><span class="sxs-lookup"><span data-stu-id="d29d0-153">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="d29d0-154">Para enviar um pacote clássico e apertá-lo usando o ETHERNET, você deve saber o endereço MAC do dispositivo de destino e do adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d29d0-154">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="d29d0-155">Como o pacote sujo não usa o protocolo de rede IP, não é possível usar o endereço IP ou o nome DNS do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d29d0-155">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="d29d0-156">Muitas soluções de gerenciamento, como o Configuration Manager, fornecem suporte integrado para o TAMBÉM.</span><span class="sxs-lookup"><span data-stu-id="d29d0-156">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="d29d0-157">Há também muitas soluções, incluindo aplicativos da Microsoft Store, módulos do PowerShell, aplicativos de terceiros e soluções de gerenciamento de terceiros que permitem que você envie um pacote mágico para apertá-lo.</span><span class="sxs-lookup"><span data-stu-id="d29d0-157">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="d29d0-158">Por exemplo, você pode usar o [módulo Wake On LAN PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) do TechNet Script Center.</span><span class="sxs-lookup"><span data-stu-id="d29d0-158">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="d29d0-159">Depois que um dispositivo tiver sido reatado com um pacote mágico, o dispositivo retornará ao sleep se um aplicativo não estiver ativamente impedindo o sleep no sistema ou se a chave do Registro AllowSystemRequiredPowerRequests não estiver configurada como 1, o que permite que os aplicativos impeçam o sleep.</span><span class="sxs-lookup"><span data-stu-id="d29d0-159">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="d29d0-160">Consulte a [seção do driver DELLs](#wol-driver) deste artigo para obter mais informações sobre essa chave do Registro.</span><span class="sxs-lookup"><span data-stu-id="d29d0-160">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
