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
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
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
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114569"
---
# <span data-ttu-id="b3a33-104">Wake on Power para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="b3a33-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="b3a33-105">Os dispositivos de superfície podem ser desligados enquanto você estiver longe de sua mesa ou configurados para o modo de hibernação para economizar a duração da bateria.</span><span class="sxs-lookup"><span data-stu-id="b3a33-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="b3a33-106">Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos de superfície compatíveis sejam iniciados automaticamente quando são reconectados à alimentação.</span><span class="sxs-lookup"><span data-stu-id="b3a33-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="b3a33-107">Para configurar o Wake on Power, você pode usar o modo de gerenciamento do Surface Enterprise (SEMM) por meio do Configurador da Surface ou do Gerenciador UEFI.</span><span class="sxs-lookup"><span data-stu-id="b3a33-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="b3a33-108">O recurso Wake on Power está disponível nos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="b3a33-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="b3a33-109">Catálogo de superfície 3</span><span class="sxs-lookup"><span data-stu-id="b3a33-109">Surface Book 3</span></span>
- <span data-ttu-id="b3a33-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="b3a33-110">Surface Pro 7</span></span>
- <span data-ttu-id="b3a33-111">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="b3a33-111">Surface Laptop 3</span></span>
- <span data-ttu-id="b3a33-112">Usar o laptop Surface</span><span class="sxs-lookup"><span data-stu-id="b3a33-112">Surface Laptop Go</span></span>
- <span data-ttu-id="b3a33-113">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="b3a33-113">Surface Pro X</span></span> 


## <span data-ttu-id="b3a33-114">Visão geral e pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b3a33-114">Overview and prerequisites</span></span>

<span data-ttu-id="b3a33-115">O configurador UEFI de Surface permite salvar configurações de UEFI individuais em um pacote Windows Installer. msi para distribuição para dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="b3a33-115">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="b3a33-116">Este artigo pressupõe que você saiba como usar o SEMM.</span><span class="sxs-lookup"><span data-stu-id="b3a33-116">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="b3a33-117">Para obter mais informações, consulte documentação [do modo de gerenciamento do Surface Enterprise (Semm)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="b3a33-117">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="b3a33-118">Para habilitar o Wake on Power</span><span class="sxs-lookup"><span data-stu-id="b3a33-118">To enable Wake on Power</span></span>

1.  <span data-ttu-id="b3a33-119">Baixe a versão mais recente do [configurador UEFI de Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="b3a33-119">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="b3a33-120">Entre em seu dispositivo Surface como administrador, abra **Surface configurador UEFI**, selecione **dispositivos de superfície**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b3a33-120">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
3.  <span data-ttu-id="b3a33-122">Selecione **Iniciar**e, em seguida, selecione **criar** em **pacote de configuração**.</span><span class="sxs-lookup"><span data-stu-id="b3a33-122">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
4.  <span data-ttu-id="b3a33-124">Selecione **proteção de certificado**e adicione seu arquivo. pfx de certificado.</span><span class="sxs-lookup"><span data-stu-id="b3a33-124">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="b3a33-125">Digite sua senha, selecione **Avançar**, adicionar **proteção por senha**, conforme apropriado, e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b3a33-125">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="b3a33-126">Na página **escolha qual tipo de superfície você deseja direcionar** , selecione os dispositivos de destino conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="b3a33-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="b3a33-127">Por exemplo, selecione **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="b3a33-127">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="b3a33-128">Na página **recursos avançados** , selecione **Ativar energia**, defina o recurso como **ativado**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b3a33-128">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione dispositivos de superfície e selecione avançar."::: 
8.  <span data-ttu-id="b3a33-130">Na página **êxito** , selecione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b3a33-130">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3a33-131">Se esta for a primeira vez que você está fornecendo configurações para seu dispositivo, você será solicitado a fornecer também os dois últimos caracteres da impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="b3a33-131">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="b3a33-132">Salve o pacote. msi.</span><span class="sxs-lookup"><span data-stu-id="b3a33-132">Save the .msi package.</span></span> 

## <span data-ttu-id="b3a33-133">Aplicar o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="b3a33-133">Apply the MSI package</span></span> 

<span data-ttu-id="b3a33-134">Você pode aplicar o pacote MSI a dispositivos na rede usando ferramentas de distribuição de software como o Gerenciador de configuração do Microsoft Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b3a33-134">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="b3a33-135">Este procedimento inclui etapas para instalar o pacote em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="b3a33-135">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="b3a33-136">Em um prompt de comando elevado, insira o caminho completo do arquivo. msi para executar o pacote. msi.</span><span class="sxs-lookup"><span data-stu-id="b3a33-136">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="b3a33-137">Na caixa de diálogo de **aviso** , selecione **OK** ou desabilitar o BitLocker, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="b3a33-137">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
3.  <span data-ttu-id="b3a33-139">Na página de boas-vindas, selecione **Avançar** para executar o pacote e aplicar a configuração UEFI recém configurada.</span><span class="sxs-lookup"><span data-stu-id="b3a33-139">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
4.  <span data-ttu-id="b3a33-141">Reinicie o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3a33-141">Restart your device.</span></span> 

<span data-ttu-id="b3a33-142">O Wake on Power está configurado agora.</span><span class="sxs-lookup"><span data-stu-id="b3a33-142">Wake on Power is now configured.</span></span> <span data-ttu-id="b3a33-143">Para testar as configurações, desligue o dispositivo, desconecte o cabo de alimentação e reconecte a energia.</span><span class="sxs-lookup"><span data-stu-id="b3a33-143">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="b3a33-144">O dispositivo deve ser iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b3a33-144">The device should start automatically.</span></span> 

## <span data-ttu-id="b3a33-145">Referências</span><span class="sxs-lookup"><span data-stu-id="b3a33-145">References</span></span>

<span data-ttu-id="b3a33-146">Para obter mais informações, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b3a33-146">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="b3a33-147">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="b3a33-147">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="b3a33-148">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="b3a33-148">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="b3a33-149">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="b3a33-149">Still need help?</span></span> <span data-ttu-id="b3a33-150">Vá para [comunidade da Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b3a33-150">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>