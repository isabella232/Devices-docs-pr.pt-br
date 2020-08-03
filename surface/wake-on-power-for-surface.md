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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902989"
---
# <span data-ttu-id="f6d21-104">Wake on Power para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="f6d21-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="f6d21-105">Os dispositivos de superfície podem ser desligados enquanto estiverem longe da mesa ou definidas para o modo de hibernação para economizar bateria.</span><span class="sxs-lookup"><span data-stu-id="f6d21-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="f6d21-106">Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos de superfície compatíveis sejam iniciados automaticamente quando reconectados à alimentação.</span><span class="sxs-lookup"><span data-stu-id="f6d21-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="f6d21-107">Configurar o Wake on Power requer o uso do modo de gerenciamento do Surface Enterprise (SEMM) por meio do Configurador UEFI ou do Gerenciador UEFI.</span><span class="sxs-lookup"><span data-stu-id="f6d21-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="f6d21-108">O Wake on Power é um recurso disponível nos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f6d21-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="f6d21-109">Catálogo de superfície 3</span><span class="sxs-lookup"><span data-stu-id="f6d21-109">Surface Book 3</span></span>
- <span data-ttu-id="f6d21-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="f6d21-110">Surface Pro 7</span></span>
- <span data-ttu-id="f6d21-111">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="f6d21-111">Surface Laptop 3</span></span>
- <span data-ttu-id="f6d21-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="f6d21-112">Surface Pro X</span></span> 

## <span data-ttu-id="f6d21-113">Visão geral e pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f6d21-113">Overview and prerequisites</span></span>

<span data-ttu-id="f6d21-114">Você pode usar o configurador UEFI de Surface para definir configurações individuais de UEFI salvas em um pacote do Windows Installer. msi para distribuição para dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="f6d21-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="f6d21-115">Este artigo pressupõe que você esteja familiarizado com o uso do SEMM.</span><span class="sxs-lookup"><span data-stu-id="f6d21-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="f6d21-116">Para obter mais informações, consulte documentação [do modo de gerenciamento do Surface Enterprise (Semm)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="f6d21-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="f6d21-117">Para habilitar o Wake on Power</span><span class="sxs-lookup"><span data-stu-id="f6d21-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="f6d21-118">Baixe a versão mais recente do [configurador UEFI de Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="f6d21-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="f6d21-119">Conecte-se ao seu dispositivo Surface como administrador, abra o **configurador UEFI do Surface**, selecione **dispositivos de superfície**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
3.  <span data-ttu-id="f6d21-121">Selecione **Iniciar** e, em **pacote de configuração** , selecione **criar**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione criar pacote de configuração.":::
4.  <span data-ttu-id="f6d21-123">Selecione **proteção de certificado** e adicione seu arquivo. pfx de certificado.</span><span class="sxs-lookup"><span data-stu-id="f6d21-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="f6d21-124">Depois de inserir a senha, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="f6d21-125">Adicione **proteção por senha**, conforme apropriado, e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="f6d21-126">Na página **escolha qual tipo de superfície você deseja direcionar** , selecione os dispositivos de destino conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="f6d21-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="f6d21-127">Por exemplo, **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="f6d21-128">Na página **recursos avançados** , selecione **Ativar no Power** e definido como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="f6d21-129">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione Ativar na energia e definido como ativado."::: 
7.  <span data-ttu-id="f6d21-131">Na página **êxito** , selecione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f6d21-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="f6d21-132">Se esta for a primeira vez que você fornece configurações ao seu dispositivo, você será solicitado a fornecer os dois últimos caracteres da impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="f6d21-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="f6d21-133">Salve o pacote. msi.</span><span class="sxs-lookup"><span data-stu-id="f6d21-133">Save the .msi package.</span></span> 

## <span data-ttu-id="f6d21-134">Aplicar o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="f6d21-134">Apply the MSI package</span></span> 

<span data-ttu-id="f6d21-135">Você pode aplicar o pacote MSI a dispositivos em sua rede usando ferramentas de distribuição de software como o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6d21-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="f6d21-136">Este procedimento inclui etapas para instalar o pacote em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="f6d21-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="f6d21-137">Abra um prompt de comando elevado e insira o caminho completo do arquivo. msi para executar o pacote. msi.</span><span class="sxs-lookup"><span data-stu-id="f6d21-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="f6d21-138">Na caixa de diálogo de **aviso** , selecione **OK** ou desabilitar o BitLocker conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="f6d21-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione OK ou desabilitar o BitLocker conforme apropriado.":::
3.  <span data-ttu-id="f6d21-140">Na página de boas-vindas, selecione **Avançar** para executar o pacote e aplicar a configuração UEFI recém configurada.</span><span class="sxs-lookup"><span data-stu-id="f6d21-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Uma página de boas-vindas, selecione avançar.":::
4.  <span data-ttu-id="f6d21-142">Reinicie o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f6d21-142">Restart your device.</span></span> 

<span data-ttu-id="f6d21-143">O Wake on Power está configurado agora.</span><span class="sxs-lookup"><span data-stu-id="f6d21-143">Wake on Power is now configured.</span></span> <span data-ttu-id="f6d21-144">Para testar a configuração, desligue o dispositivo, desconecte o cabo de alimentação e reconecte a energia.</span><span class="sxs-lookup"><span data-stu-id="f6d21-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="f6d21-145">O dispositivo será iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f6d21-145">The device will start automatically.</span></span> 

## <span data-ttu-id="f6d21-146">Mais informações</span><span class="sxs-lookup"><span data-stu-id="f6d21-146">More information</span></span>

<span data-ttu-id="f6d21-147">Para obter mais informações, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="f6d21-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="f6d21-148">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="f6d21-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="f6d21-149">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="f6d21-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="f6d21-150">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="f6d21-150">Still need help?</span></span> <span data-ttu-id="f6d21-151">Vá para [comunidade da Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f6d21-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>