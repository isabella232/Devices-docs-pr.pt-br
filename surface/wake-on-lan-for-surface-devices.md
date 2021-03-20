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
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442149"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="d90c9-104">Wake On LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="d90c9-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="d90c9-105">Os dispositivos Surface que usam um adaptador Surface Ethernet para se conectar a uma rede com fio podem tirar proveito do Wake On LAN (WOL) de Espera Conectada.</span><span class="sxs-lookup"><span data-stu-id="d90c9-105">Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="d90c9-106">Com o WOL, você pode acordar remotamente dispositivos e executar tarefas de gerenciamento automaticamente usando soluções de gerenciamento, como o Microsoft Endpoint Manager/Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d90c9-106">With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.</span></span>

## <a name="wol-supported-devices"></a><span data-ttu-id="d90c9-107">Dispositivos compatíveis com o WOL</span><span class="sxs-lookup"><span data-stu-id="d90c9-107">WOL-supported devices</span></span>

- <span data-ttu-id="d90c9-108">Adaptador Surface Ethernet</span><span class="sxs-lookup"><span data-stu-id="d90c9-108">Surface Ethernet adapter</span></span>
- <span data-ttu-id="d90c9-109">Surface USB-C para Ethernet e Adaptador USB</span><span class="sxs-lookup"><span data-stu-id="d90c9-109">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="d90c9-110">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="d90c9-110">Surface Dock 2</span></span>
- <span data-ttu-id="d90c9-111">Surface Pro 6 e posterior</span><span class="sxs-lookup"><span data-stu-id="d90c9-111">Surface Pro 6 and later</span></span>
- <span data-ttu-id="d90c9-112">Surface Book (todas as gerações)</span><span class="sxs-lookup"><span data-stu-id="d90c9-112">Surface Book (all generations)</span></span>
- <span data-ttu-id="d90c9-113">Surface Laptop (todas as gerações)</span><span class="sxs-lookup"><span data-stu-id="d90c9-113">Surface Laptop (all generations)</span></span>
- <span data-ttu-id="d90c9-114">Surface Go (todas as gerações)</span><span class="sxs-lookup"><span data-stu-id="d90c9-114">Surface Go (all generations)</span></span>
- <span data-ttu-id="d90c9-115">Surface Studio 2 (consulte Apêndice)</span><span class="sxs-lookup"><span data-stu-id="d90c9-115">Surface Studio 2 (see Appendix)</span></span>


## <a name="using-surface-wol"></a><span data-ttu-id="d90c9-116">Usando o Surface WOL</span><span class="sxs-lookup"><span data-stu-id="d90c9-116">Using Surface WOL</span></span>

<span data-ttu-id="d90c9-117">Os administradores de IT podem disparar dispositivos usando um wake on LAN request (pacote mágico) que contém o endereço MAC do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="d90c9-117">IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address.</span></span> <span data-ttu-id="d90c9-118">Para enviar um pacote mágico e acordar um dispositivo usando o WOL, você deve saber o endereço MAC do dispositivo de destino e o adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d90c9-118">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="d90c9-119">Como o pacote mágico não usa o protocolo de rede IP, não é possível usar o endereço IP ou o nome DNS do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d90c9-119">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="d90c9-120">Muitas soluções de gerenciamento, como o Microsoft Endpoint Configuration Manager e aplicativos da Microsoft Store de terceiros oferecem suporte integrado para o WOL.</span><span class="sxs-lookup"><span data-stu-id="d90c9-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="d90c9-121">Observe que os dispositivos precisam estar no modo De espera conectado (Sleep) e conectados à energia ac.</span><span class="sxs-lookup"><span data-stu-id="d90c9-121">Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power.</span></span> <span data-ttu-id="d90c9-122">Para saber mais sobre como acordar dispositivos com o Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span><span class="sxs-lookup"><span data-stu-id="d90c9-122">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>


## <a name="to-check-wol-is-enabled-on-your-device"></a><span data-ttu-id="d90c9-123">Para verificar se a WOL está habilitada em seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="d90c9-123">To check WOL is enabled on your device</span></span>

1. <span data-ttu-id="d90c9-124">Em seu dispositivo conectado Ethernet, selecione seu adaptador de rede e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d90c9-124">On your Ethernet connected device, select your network adapter, and then select **Properties**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Adaptador Surface Ethernet](images/surface-ethernet.png)

2. <span data-ttu-id="d90c9-126">Selecione **Configurar**  >  **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="d90c9-126">Select **Configure** > **Advanced**.</span></span>
3. <span data-ttu-id="d90c9-127">Role até **Pacote Moderno de Espera WoL Mágico** e certifique-se de que **Habilitado** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="d90c9-127">Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.</span></span>

     ![Verificar se a WOL está habilitada no dispositivo](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a><span data-ttu-id="d90c9-129">Apêndice: Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="d90c9-129">Appendix: Surface Studio 2</span></span>

<span data-ttu-id="d90c9-130">Para habilitar o WOL no Surface Studio 2, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="d90c9-130">To enable WOL on Surface Studio 2, use the following procedure.</span></span>

1. <span data-ttu-id="d90c9-131">Crie as seguintes chaves do Registro:</span><span class="sxs-lookup"><span data-stu-id="d90c9-131">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="d90c9-132">Execute o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="d90c9-132">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a><span data-ttu-id="d90c9-133">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="d90c9-133">Learn more</span></span>

- [<span data-ttu-id="d90c9-134">Microsoft Surface USB-C para Ethernet e Adaptador USB</span><span class="sxs-lookup"><span data-stu-id="d90c9-134">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [<span data-ttu-id="d90c9-135">Adaptador Ethernet Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="d90c9-135">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
