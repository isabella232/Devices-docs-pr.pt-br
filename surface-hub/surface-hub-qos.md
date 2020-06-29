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
# Implementar a QoS (qualidade de serviço) no Surface Hub

A QoS (qualidade de serviço) é uma combinação de tecnologias de rede que permite que os administradores otimizem a experiência de comunicação de áudio/vídeo e compartilhamento de aplicativos em tempo real.
 
A configuração [de QoS para o Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) no Surface Hub pode ser feita usando o [provedor de gerenciamento de dispositivo móvel (MDM)](manage-settings-with-mdm-for-surface-hub.md) ou um pacote de [provisionamento](provisioning-packages-for-surface-hub.md). 
 
 
Este procedimento explica como configurar o QoS para Surface Hub usando o Microsoft Intune. 

1. No Intune, [crie uma política personalizada](https://docs.microsoft.com/intune/custom-settings-configure).

    ![Captura de tela da caixa de diálogo criação de política personalizada no Intune](images/qos-create.png)

2. Em **configurações OMA-URI personalizadas**, selecione **Adicionar**. Para cada configuração que você adicionar, insira um nome, descrição (opcional), tipo de dados, OMA-URI e valor.

    ![Captura de tela de uma caixa de diálogo de configuração OMA-URI em branco](images/qos-setting.png)

3. Adicione as seguintes configurações de OMA-URI personalizadas:

    Nome | Tipo de dados | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Valor
    --- | --- | --- | ---
    Porta de origem de áudio | String |  /HubAudio/SourcePortMatchCondition  |   Obter os valores do seu administrador do Skype
    DSCP de Áudio | Inteiro |  /HubAudio/DSCPAction  |   46
    Porta de origem de vídeo | String |  /HubVideo/SourcePortMatchCondition   |  Obter os valores do seu administrador do Skype
    DSCP de vídeo | Inteiro |  /HubVideo/DSCPAction   |   34
    Nome do processo de áudio | String |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Nome do processo de vídeo | String |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Cada caminho **OMA-URI** começa com `./Device/Vendor/MSFT/NetworkQoSPolicy` . O caminho completo da configuração da porta de origem de áudio, por exemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .




4. Quando a política tiver sido criada, [implante-a no Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>Atualmente, você não pode definir a configuração **IPProtocolMatchCondition** no [provedor de NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Se essa configuração estiver configurada, a política não será aplicada.
 
