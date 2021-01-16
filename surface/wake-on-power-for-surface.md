---
title: Como habilitar o Wake on Power para Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Descreve como habilitar e desabilitar o Wake on Power para dispositivos Surface.
keywords: atualizar, implantar, driver, ltd, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271555"
---
# <span data-ttu-id="9eaa6-104">Wake on Power para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="9eaa6-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="9eaa6-105">Os dispositivos Surface podem ser desligados enquanto você estiver longe da sua mesa ou definir o modo de hibernação para economizar a duração da bateria.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="9eaa6-106">Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos Surface compatíveis iniciem automaticamente quando eles se reconectam à energia.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="9eaa6-107">Para configurar o Wake on Power, você pode usar o Surface Enterprise Management Mode (SEMM) por meio do Configurador UEFI do Surface ou do Gerenciador UEFI.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="9eaa6-108">O recurso Wake on Power está disponível nos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="9eaa6-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="9eaa6-109">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="9eaa6-109">Surface Pro 7+</span></span>
- <span data-ttu-id="9eaa6-110">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="9eaa6-110">Surface Book 3</span></span>
- <span data-ttu-id="9eaa6-111">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="9eaa6-111">Surface Pro 7</span></span>
- <span data-ttu-id="9eaa6-112">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="9eaa6-112">Surface Laptop 3</span></span>
- <span data-ttu-id="9eaa6-113">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="9eaa6-113">Surface Laptop Go</span></span>
- <span data-ttu-id="9eaa6-114">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="9eaa6-114">Surface Pro X</span></span> 


## <span data-ttu-id="9eaa6-115">Visão geral e pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9eaa6-115">Overview and prerequisites</span></span>

<span data-ttu-id="9eaa6-116">O Configurador UEFI do Surface permite salvar configurações UEFI individuais em um pacote .msi do Windows Installer para distribuição a dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-116">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="9eaa6-117">Este artigo presume que você saiba como usar o SEMM.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-117">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="9eaa6-118">Para obter mais informações, consulte [a documentação do Surface Enterprise Management Mode (SEMM).](surface-enterprise-management-mode.md)</span><span class="sxs-lookup"><span data-stu-id="9eaa6-118">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="9eaa6-119">Para habilitar o Wake on Power</span><span class="sxs-lookup"><span data-stu-id="9eaa6-119">To enable Wake on Power</span></span>

1.  <span data-ttu-id="9eaa6-120">Baixe a versão mais recente do [Configurador UEFI do Surface.](https://www.microsoft.com/download/confirmation.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="9eaa6-120">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="9eaa6-121">Entre no dispositivo Surface como administrador, abra o **Configurador UEFI**do Surface, selecione **Dispositivos Surface**e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9eaa6-121">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione Dispositivos Surface e Clique em Próximo.":::
3.  <span data-ttu-id="9eaa6-123">Selecione **Iniciar**e Criar em **Pacote** **de Configuração.**</span><span class="sxs-lookup"><span data-stu-id="9eaa6-123">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione Criar Pacote de Configuração.":::
4.  <span data-ttu-id="9eaa6-125">Selecione **Proteção de Certificado**e adicione seu arquivo .pfx de certificado.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-125">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="9eaa6-126">Insira sua senha, selecione **Próximo**, adicionar Proteção **por Senha,** conforme apropriado e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-126">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="9eaa6-127">Na página **Escolha qual tipo de Surface você deseja direcionar,** selecione seus dispositivos de destino conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-127">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="9eaa6-128">Por exemplo, selecione **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-128">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="9eaa6-129">Na página **Recursos Avançados,** selecione a opção \*\*\*\* **Acioná-lo,** definir o recurso como On e, em seguida, selecione **Avançar.**</span><span class="sxs-lookup"><span data-stu-id="9eaa6-129">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione a opção Acioná-la e de definida como 1."::: 
8.  <span data-ttu-id="9eaa6-131">Na página **Bem-sucedida,** selecione **End**.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-131">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eaa6-132">Se esta for a primeira vez que você estiver fornecendo configurações para seu dispositivo, também será solicitado a fornecer os dois últimos caracteres da impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-132">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="9eaa6-133">Salve o pacote .msi.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-133">Save the .msi package.</span></span> 

## <span data-ttu-id="9eaa6-134">Aplicar o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="9eaa6-134">Apply the MSI package</span></span> 

<span data-ttu-id="9eaa6-135">Você pode aplicar o pacote MSI a dispositivos em sua rede usando ferramentas de distribuição de software, como o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-135">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="9eaa6-136">Esse procedimento inclui etapas para instalar o pacote no computador local.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-136">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="9eaa6-137">Em um prompt de comando com elevação, insira o caminho completo do arquivo .msi para executar o pacote .msi.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-137">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="9eaa6-138">Na caixa **de** diálogo Aviso, selecione **OK ou** desabilite o BitLocker, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-138">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione OK ou desabilite o BitLocker conforme apropriado.":::
3.  <span data-ttu-id="9eaa6-140">Na página de boas-vindas, selecione **Próximo** para executar o pacote e aplicar a configuração UEFI recém-configurada.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Uma página de boas-vindas, selecione Próxima.":::
4.  <span data-ttu-id="9eaa6-142">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-142">Restart your device.</span></span> 

<span data-ttu-id="9eaa6-143">O Wake on Power agora está configurado.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-143">Wake on Power is now configured.</span></span> <span data-ttu-id="9eaa6-144">Para testar as configurações, desligue o dispositivo, desconecte a energia e reconecte a energia.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-144">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="9eaa6-145">O dispositivo deve iniciar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-145">The device should start automatically.</span></span> 

## <span data-ttu-id="9eaa6-146">Referências</span><span class="sxs-lookup"><span data-stu-id="9eaa6-146">References</span></span>

<span data-ttu-id="9eaa6-147">Para obter mais informações, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="9eaa6-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="9eaa6-148">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="9eaa6-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="9eaa6-149">Adoção na LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="9eaa6-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="9eaa6-150">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="9eaa6-150">Still need help?</span></span> <span data-ttu-id="9eaa6-151">Vá para [a Comunidade da Microsoft.](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="9eaa6-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>