---
title: Implementar a Qualidade do Serviço no Surface Hub
ms.reviewer: ''
manager: laurawi
description: Saiba como configurar o QoS no Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830400"
---
# <span data-ttu-id="3ca17-103">Implementar a QoS (qualidade de serviço) no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="3ca17-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="3ca17-104">A QoS (qualidade de serviço) é uma combinação de tecnologias de rede que permite que os administradores otimizem a experiência de comunicação de áudio/vídeo e compartilhamento de aplicativos em tempo real.</span><span class="sxs-lookup"><span data-stu-id="3ca17-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="3ca17-105">A configuração [de QoS para o Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) no Surface Hub pode ser feita usando o [provedor de gerenciamento de dispositivo móvel (MDM)](manage-settings-with-mdm-for-surface-hub.md) ou um pacote de [provisionamento](provisioning-packages-for-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="3ca17-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="3ca17-106">Este procedimento explica como configurar o QoS para Surface Hub usando o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3ca17-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="3ca17-107">No Intune, [crie uma política personalizada](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="3ca17-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Captura de tela da caixa de diálogo criação de política personalizada no Intune](images/qos-create.png)

2. <span data-ttu-id="3ca17-109">Em **configurações OMA-URI personalizadas**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3ca17-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="3ca17-110">Para cada configuração que você adicionar, insira um nome, descrição (opcional), tipo de dados, OMA-URI e valor.</span><span class="sxs-lookup"><span data-stu-id="3ca17-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![Captura de tela de uma caixa de diálogo de configuração OMA-URI em branco](images/qos-setting.png)

3. <span data-ttu-id="3ca17-112">Adicione as seguintes configurações de OMA-URI personalizadas:</span><span class="sxs-lookup"><span data-stu-id="3ca17-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="3ca17-113">Nome</span><span class="sxs-lookup"><span data-stu-id="3ca17-113">Name</span></span> | <span data-ttu-id="3ca17-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3ca17-114">Data type</span></span> | <span data-ttu-id="3ca17-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="3ca17-115">OMA-URI</span></span><br><span data-ttu-id="3ca17-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca17-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="3ca17-117">Valor</span><span class="sxs-lookup"><span data-stu-id="3ca17-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="3ca17-118">Porta de origem de áudio</span><span class="sxs-lookup"><span data-stu-id="3ca17-118">Audio Source Port</span></span> | <span data-ttu-id="3ca17-119">String</span><span class="sxs-lookup"><span data-stu-id="3ca17-119">String</span></span> |  <span data-ttu-id="3ca17-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="3ca17-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="3ca17-121">Obter os valores do seu administrador do Skype</span><span class="sxs-lookup"><span data-stu-id="3ca17-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="3ca17-122">DSCP de Áudio</span><span class="sxs-lookup"><span data-stu-id="3ca17-122">Audio DSCP</span></span> | <span data-ttu-id="3ca17-123">Inteiro</span><span class="sxs-lookup"><span data-stu-id="3ca17-123">Integer</span></span> |  <span data-ttu-id="3ca17-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="3ca17-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="3ca17-125">46</span><span class="sxs-lookup"><span data-stu-id="3ca17-125">46</span></span>
    <span data-ttu-id="3ca17-126">Porta de origem de vídeo</span><span class="sxs-lookup"><span data-stu-id="3ca17-126">Video Source Port</span></span> | <span data-ttu-id="3ca17-127">String</span><span class="sxs-lookup"><span data-stu-id="3ca17-127">String</span></span> |  <span data-ttu-id="3ca17-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="3ca17-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="3ca17-129">Obter os valores do seu administrador do Skype</span><span class="sxs-lookup"><span data-stu-id="3ca17-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="3ca17-130">DSCP de vídeo</span><span class="sxs-lookup"><span data-stu-id="3ca17-130">Video DSCP</span></span> | <span data-ttu-id="3ca17-131">Inteiro</span><span class="sxs-lookup"><span data-stu-id="3ca17-131">Integer</span></span> |  <span data-ttu-id="3ca17-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="3ca17-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="3ca17-133">34</span><span class="sxs-lookup"><span data-stu-id="3ca17-133">34</span></span>
    <span data-ttu-id="3ca17-134">Nome do processo de áudio</span><span class="sxs-lookup"><span data-stu-id="3ca17-134">Audio Process Name</span></span> | <span data-ttu-id="3ca17-135">String</span><span class="sxs-lookup"><span data-stu-id="3ca17-135">String</span></span> |  <span data-ttu-id="3ca17-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="3ca17-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="3ca17-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="3ca17-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="3ca17-138">Nome do processo de vídeo</span><span class="sxs-lookup"><span data-stu-id="3ca17-138">Video Process Name</span></span> | <span data-ttu-id="3ca17-139">String</span><span class="sxs-lookup"><span data-stu-id="3ca17-139">String</span></span> |  <span data-ttu-id="3ca17-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="3ca17-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="3ca17-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="3ca17-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="3ca17-142">Cada caminho **OMA-URI** começa com `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="3ca17-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="3ca17-143">O caminho completo da configuração da porta de origem de áudio, por exemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="3ca17-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="3ca17-144">Quando a política tiver sido criada, [implante-a no Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="3ca17-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="3ca17-145">Atualmente, você não pode definir a configuração **IPProtocolMatchCondition** no [provedor de NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span><span class="sxs-lookup"><span data-stu-id="3ca17-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="3ca17-146">Se essa configuração estiver configurada, a política não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="3ca17-146">If this setting is configured, the policy will fail to apply.</span></span>
 
