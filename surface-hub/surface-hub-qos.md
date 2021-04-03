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
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>Implementar qoS (qualidade de serviço) no Surface Hub

A QoS (Qualidade do Serviço) é uma combinação de tecnologias de rede que permite aos administradores otimizar a experiência de comunicações de áudio/vídeo e compartilhamento de aplicativos em tempo real.
 
A [configuração de QoS para Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) no Surface Hub pode ser feita usando seu provedor de gerenciamento de dispositivo móvel [(MDM)](manage-settings-with-mdm-for-surface-hub.md) ou por meio de um [pacote de provisionamento](provisioning-packages-for-surface-hub.md). 
 
 
Este procedimento explica como configurar o QoS para o Surface Hub usando o Microsoft Intune. 

1. No Intune, [crie uma política personalizada.](https://docs.microsoft.com/intune/custom-settings-configure)

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da caixa de diálogo de criação de política personalizada no Intune](images/qos-create.png)

2. Em **Configurações personalizadas do OMA-URI,** selecione **Adicionar**. Para cada configuração que você adicionar, você inserirá um nome, descrição (opcional), tipo de dados, OMA-URI e valor.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela de uma caixa de diálogo de configuração OMA-URI em branco](images/qos-setting.png)

3. Adicione as seguintes configurações personalizadas do OMA-URI:<br/><br/>

    Nome | Tipo de dados | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Valor
    --- | --- | --- | ---
    Porta de origem de áudio | String |  /HubAudio/SourcePortMatchCondition  |   Obter os valores do administrador do Skype
    DSCP de Áudio | Inteiro |  /HubAudio/DSCPAction  |   46
    Porta de Origem do Vídeo | String |  /HubVideo/SourcePortMatchCondition   |  Obter os valores do administrador do Skype
    DSCP de vídeo | Inteiro |  /HubVideo/DSCPAction   |   34
    Nome do processo de áudio | String |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Nome do processo de vídeo | String |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Cada **caminho OMA-URI** começa com `./Device/Vendor/MSFT/NetworkQoSPolicy` . O caminho completo para a configuração da porta de origem de áudio, por exemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .

4. Quando a política for criada, implante-a no Surface Hub.


>[!WARNING]
>Atualmente, você não pode configurar a **configuração IPProtocolMatchCondition** no [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Se essa configuração estiver configurada, a política não será aplicada.
 
