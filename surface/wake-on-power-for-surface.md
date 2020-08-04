---
title: Como habilitar o Wake on Power para Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Descreve como habilitar e desabilitar o Wake on Power para dispositivos Surface.
keywords: atualização, implantação, Driver, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903390"
---
# <span data-ttu-id="3add9-104">Wake on Power para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="3add9-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="3add9-105">Os dispositivos de superfície podem ser desligados enquanto você estiver longe de sua mesa ou configurados para o modo de hibernação para economizar a duração da bateria.</span><span class="sxs-lookup"><span data-stu-id="3add9-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="3add9-106">Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos de superfície compatíveis sejam iniciados automaticamente quando são reconectados à alimentação.</span><span class="sxs-lookup"><span data-stu-id="3add9-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="3add9-107">Para configurar o Wake on Power, você pode usar o modo de gerenciamento do Surface Enterprise (SEMM) por meio do Configurador da Surface ou do Gerenciador UEFI.</span><span class="sxs-lookup"><span data-stu-id="3add9-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="3add9-108">O recurso Wake on Power está disponível nos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="3add9-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="3add9-109">Catálogo de superfície 3</span><span class="sxs-lookup"><span data-stu-id="3add9-109">Surface Book 3</span></span>
- <span data-ttu-id="3add9-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="3add9-110">Surface Pro 7</span></span>
- <span data-ttu-id="3add9-111">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="3add9-111">Surface Laptop 3</span></span>
- <span data-ttu-id="3add9-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="3add9-112">Surface Pro X</span></span> 

## <span data-ttu-id="3add9-113">Visão geral e pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3add9-113">Overview and prerequisites</span></span>

<span data-ttu-id="3add9-114">O configurador UEFI de Surface permite salvar configurações de UEFI individuais em um pacote Windows Installer. msi para distribuição para dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="3add9-114">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="3add9-115">Este artigo pressupõe que você saiba como usar o SEMM.</span><span class="sxs-lookup"><span data-stu-id="3add9-115">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="3add9-116">Para obter mais informações, consulte documentação [do modo de gerenciamento do Surface Enterprise (Semm)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="3add9-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="3add9-117">Para habilitar o Wake on Power</span><span class="sxs-lookup"><span data-stu-id="3add9-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="3add9-118">Baixe a versão mais recente do [configurador UEFI de Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="3add9-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="3add9-119">Entre em seu dispositivo Surface como administrador, abra **Surface configurador UEFI**, selecione **dispositivos de superfície**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3add9-119">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
3.  <span data-ttu-id="3add9-121">Selecione **Iniciar**e, em seguida, selecione **criar** em **pacote de configuração**.</span><span class="sxs-lookup"><span data-stu-id="3add9-121">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione criar pacote de configuração.":::
4.  <span data-ttu-id="3add9-123">Selecione **proteção de certificado**e adicione seu arquivo. pfx de certificado.</span><span class="sxs-lookup"><span data-stu-id="3add9-123">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="3add9-124">Digite sua senha, selecione **Avançar**, adicionar **proteção por senha**, conforme apropriado, e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3add9-124">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="3add9-125">Na página **escolha qual tipo de superfície você deseja direcionar** , selecione os dispositivos de destino conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="3add9-125">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="3add9-126">Por exemplo, selecione **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="3add9-126">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="3add9-127">Na página **recursos avançados** , selecione **Ativar energia**, defina o recurso como **ativado**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3add9-127">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione Ativar na energia e definido como ativado."::: 
8.  <span data-ttu-id="3add9-129">Na página **êxito** , selecione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3add9-129">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3add9-130">Se esta for a primeira vez que você está fornecendo configurações para seu dispositivo, você será solicitado a fornecer também os dois últimos caracteres da impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="3add9-130">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="3add9-131">Salve o pacote. msi.</span><span class="sxs-lookup"><span data-stu-id="3add9-131">Save the .msi package.</span></span> 

## <span data-ttu-id="3add9-132">Aplicar o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="3add9-132">Apply the MSI package</span></span> 

<span data-ttu-id="3add9-133">Você pode aplicar o pacote MSI a dispositivos na rede usando ferramentas de distribuição de software como o Gerenciador de configuração do Microsoft Endpoint.</span><span class="sxs-lookup"><span data-stu-id="3add9-133">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3add9-134">Este procedimento inclui etapas para instalar o pacote em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="3add9-134">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="3add9-135">Em um prompt de comando elevado, insira o caminho completo do arquivo. msi para executar o pacote. msi.</span><span class="sxs-lookup"><span data-stu-id="3add9-135">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="3add9-136">Na caixa de diálogo de **aviso** , selecione **OK** ou desabilitar o BitLocker, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="3add9-136">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione OK ou desabilitar o BitLocker conforme apropriado.":::
3.  <span data-ttu-id="3add9-138">Na página de boas-vindas, selecione **Avançar** para executar o pacote e aplicar a configuração UEFI recém configurada.</span><span class="sxs-lookup"><span data-stu-id="3add9-138">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Uma página de boas-vindas, selecione avançar.":::
4.  <span data-ttu-id="3add9-140">Reinicie o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3add9-140">Restart your device.</span></span> 

<span data-ttu-id="3add9-141">O Wake on Power está configurado agora.</span><span class="sxs-lookup"><span data-stu-id="3add9-141">Wake on Power is now configured.</span></span> <span data-ttu-id="3add9-142">Para testar as configurações, desligue o dispositivo, desconecte o cabo de alimentação e reconecte a energia.</span><span class="sxs-lookup"><span data-stu-id="3add9-142">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="3add9-143">O dispositivo deve ser iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3add9-143">The device should start automatically.</span></span> 

## <span data-ttu-id="3add9-144">Referências</span><span class="sxs-lookup"><span data-stu-id="3add9-144">References</span></span>

<span data-ttu-id="3add9-145">Para obter mais informações, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="3add9-145">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="3add9-146">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="3add9-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="3add9-147">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="3add9-147">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="3add9-148">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="3add9-148">Still need help?</span></span> <span data-ttu-id="3add9-149">Vá para [comunidade da Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3add9-149">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>