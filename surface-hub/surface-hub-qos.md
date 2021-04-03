---
title: Implementar a Qualidade do Serviço no Surface Hub
ms.reviewer: ''
manager: laurawi
description: Saiba como configurar a QoS no Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470479"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a><span data-ttu-id="7ea68-103">Implementar qoS (qualidade de serviço) no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="7ea68-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="7ea68-104">A QoS (Qualidade do Serviço) é uma combinação de tecnologias de rede que permite aos administradores otimizar a experiência de comunicações de áudio/vídeo e compartilhamento de aplicativos em tempo real.</span><span class="sxs-lookup"><span data-stu-id="7ea68-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="7ea68-105">A [configuração de QoS para Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) no Surface Hub pode ser feita usando seu provedor de gerenciamento de dispositivo móvel [(MDM)](manage-settings-with-mdm-for-surface-hub.md) ou por meio de um [pacote de provisionamento](provisioning-packages-for-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="7ea68-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="7ea68-106">Este procedimento explica como configurar o QoS para o Surface Hub usando o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="7ea68-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="7ea68-107">No Intune, [crie uma política personalizada.](https://docs.microsoft.com/intune/custom-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="7ea68-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da caixa de diálogo de criação de política personalizada no Intune](images/qos-create.png)

2. <span data-ttu-id="7ea68-109">Em **Configurações personalizadas do OMA-URI,** selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7ea68-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="7ea68-110">Para cada configuração que você adicionar, você inserirá um nome, descrição (opcional), tipo de dados, OMA-URI e valor.</span><span class="sxs-lookup"><span data-stu-id="7ea68-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Captura de tela de uma caixa de diálogo de configuração OMA-URI em branco](images/qos-setting.png)

3. <span data-ttu-id="7ea68-112">Adicione as seguintes configurações personalizadas do OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="7ea68-112">Add the following custom OMA-URI settings:</span></span><br/><br/>

    <span data-ttu-id="7ea68-113">Nome</span><span class="sxs-lookup"><span data-stu-id="7ea68-113">Name</span></span> | <span data-ttu-id="7ea68-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="7ea68-114">Data type</span></span> | <span data-ttu-id="7ea68-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="7ea68-115">OMA-URI</span></span><br><span data-ttu-id="7ea68-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="7ea68-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="7ea68-117">Valor</span><span class="sxs-lookup"><span data-stu-id="7ea68-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="7ea68-118">Porta de origem de áudio</span><span class="sxs-lookup"><span data-stu-id="7ea68-118">Audio Source Port</span></span> | <span data-ttu-id="7ea68-119">String</span><span class="sxs-lookup"><span data-stu-id="7ea68-119">String</span></span> |  <span data-ttu-id="7ea68-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="7ea68-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="7ea68-121">Obter os valores do administrador do Skype</span><span class="sxs-lookup"><span data-stu-id="7ea68-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="7ea68-122">DSCP de Áudio</span><span class="sxs-lookup"><span data-stu-id="7ea68-122">Audio DSCP</span></span> | <span data-ttu-id="7ea68-123">Inteiro</span><span class="sxs-lookup"><span data-stu-id="7ea68-123">Integer</span></span> |  <span data-ttu-id="7ea68-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="7ea68-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="7ea68-125">46</span><span class="sxs-lookup"><span data-stu-id="7ea68-125">46</span></span>
    <span data-ttu-id="7ea68-126">Porta de Origem do Vídeo</span><span class="sxs-lookup"><span data-stu-id="7ea68-126">Video Source Port</span></span> | <span data-ttu-id="7ea68-127">String</span><span class="sxs-lookup"><span data-stu-id="7ea68-127">String</span></span> |  <span data-ttu-id="7ea68-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="7ea68-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="7ea68-129">Obter os valores do administrador do Skype</span><span class="sxs-lookup"><span data-stu-id="7ea68-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="7ea68-130">DSCP de vídeo</span><span class="sxs-lookup"><span data-stu-id="7ea68-130">Video DSCP</span></span> | <span data-ttu-id="7ea68-131">Inteiro</span><span class="sxs-lookup"><span data-stu-id="7ea68-131">Integer</span></span> |  <span data-ttu-id="7ea68-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="7ea68-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="7ea68-133">34</span><span class="sxs-lookup"><span data-stu-id="7ea68-133">34</span></span>
    <span data-ttu-id="7ea68-134">Nome do processo de áudio</span><span class="sxs-lookup"><span data-stu-id="7ea68-134">Audio Process Name</span></span> | <span data-ttu-id="7ea68-135">String</span><span class="sxs-lookup"><span data-stu-id="7ea68-135">String</span></span> |  <span data-ttu-id="7ea68-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="7ea68-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="7ea68-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="7ea68-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="7ea68-138">Nome do processo de vídeo</span><span class="sxs-lookup"><span data-stu-id="7ea68-138">Video Process Name</span></span> | <span data-ttu-id="7ea68-139">String</span><span class="sxs-lookup"><span data-stu-id="7ea68-139">String</span></span> |  <span data-ttu-id="7ea68-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="7ea68-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="7ea68-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="7ea68-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="7ea68-142">Cada **caminho OMA-URI** começa com `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="7ea68-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="7ea68-143">O caminho completo para a configuração da porta de origem de áudio, por exemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="7ea68-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>

4. <span data-ttu-id="7ea68-144">Quando a política for criada, implante-a no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7ea68-144">When the policy has been created, deploy it to Surface Hub.</span></span>


>[!WARNING]
><span data-ttu-id="7ea68-145">Atualmente, você não pode configurar a **configuração IPProtocolMatchCondition** no [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span><span class="sxs-lookup"><span data-stu-id="7ea68-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="7ea68-146">Se essa configuração estiver configurada, a política não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="7ea68-146">If this setting is configured, the policy will fail to apply.</span></span>
 
