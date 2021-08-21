---
title: Configurar rede e Qualidade de Serviço para Microsoft Teams Sala no Surface Hub
description: Este artigo explica os requisitos e recomendações para rede e Qualidade do Serviço para otimizar Salas do Microsoft Teams no Surface Hub.
keywords: Salas do Teams, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d06a69d89d94839c3a9616a29ff1be12badec76e
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2021
ms.locfileid: "11909951"
---
# <a name="configure-networking-and-quality-of-service-for-microsoft-teams-rooms-on-surface-hub"></a>Configurar rede e Qualidade de Serviço para Salas do Microsoft Teams no Surface Hub

Este artigo explica como preparar seu ambiente para otimizar o Salas do Microsoft Teams em Surface Hub.

## <a name="create-and-test-a-device-account"></a>Criar e testar uma conta de dispositivo

Uma conta de dispositivo é uma conta que o cliente Salas do Microsoft Teams usa para acessar recursos de Exchange, como calendário, e para habilitar Skype for Business. [Consulte Criar e testar uma conta de dispositivo](create-and-test-a-device-account-surface-hub.md)

## <a name="check-network-availability"></a>Verificar a disponibilidade da rede

> [!TIP]
> É recomendável usar as práticas de configuração de rede listadas [Microsoft 365 de conectividade de rede](https://aka.ms/pnc)

Salas do Teams no Surface Hub deve ter acesso a uma rede que atenda a esses requisitos:

- Acesso à sua instância do Active Directory ou Azure Active Directory (Azure AD)
- Acesso a um servidor que pode fornecer um endereço IP usando DHCP. Salas do Microsoft Teams no Surface Hub não pode ser configurado com um endereço IP estático.
- Acesso às portas HTTP 80 e 443.
- Portas TCP e UDP configuradas conforme descrito em Requisitos de porta e protocolo para [urls](/microsoft-365/enterprise/urls-and-ip-address-ranges) Microsoft 365 e Office 365 e intervalos de endereços IP para Microsoft Teams.

> [!IMPORTANT]
> Salas do Microsoft Teams não dá suporte à autenticação de proxy, pois pode interferir nas operações regulares de Teams. Verifique se Surface Hub dispositivos ou Microsoft 365 de serviço foram isentos da autenticação de proxy antes de entrar em produção com Salas do Teams no Surface Hub.

## <a name="implement-quality-of-service-qos-on-surface-hub"></a>Implementar qoS (qualidade de serviço) em Surface Hub

A QoS (Qualidade do Serviço) é uma combinação de tecnologias de rede que permite aos administradores otimizar a experiência de comunicações de áudio/vídeo e compartilhamento de aplicativos em tempo real.
A configuração de QoS para Microsoft Teams no Surface Hub pode ser feita usando seu provedor de gerenciamento de dispositivo móvel [(MDM)](manage-settings-with-mdm-for-surface-hub.md) ou por meio de um [pacote de provisionamento](provisioning-packages-for-surface-hub.md).

Para configurar o QoS para Surface Hub usando Microsoft Intune:

1. No Intune, [crie uma política personalizada.](/intune/custom-settings-configure)

2. Em **Custom OMA-URI Configurações**, selecione **Adicionar**. Para cada configuração que você adicionar, você inserirá um nome, descrição (opcional), tipo de dados, OMA-URI e valor.

3. Para garantir a qualidade ideal de vídeo e áudio no Surface Hub, adicione as seguintes configurações de QoS ao dispositivo.

    | Nome                  | Descrição           | OMA-URI                                                                        | Tipo    | Valor       |
    | --------------------- | --------------------- | ------------------------------------------------------------------------------ | ------- | ----------- |
    | **Portas de áudio**       | Intervalo de porta de áudio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortMatchCondition      | String  | 50000-50019 |
    | **DSCP de Áudio**        | Marcação de portas de áudio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction                    | Inteiro | 46          |
    | **Porta de vídeo**        | Intervalo de porta de vídeo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortMatchCondition      | String  | 50020-50039 |
    | **DSCP de vídeo**        | Marcação de portas de vídeo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction                    | Inteiro | 34          |
    | **Porta de Compartilhamento**      | Intervalo de Porta de Compartilhamento    | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/SourcePortMatchCondition    | String  | 50040-50059 |
    | **Compartilhamento de DSCP**      | Marcação de portas de compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction                  | Inteiro | 18          |

4. Quando a política tiver sido criada, implante-a Surface Hub.

## <a name="learn-more"></a>Saiba mais

- [Implementar qoS (qualidade de serviço) no Microsoft Teams](/microsoftteams/qos-in-teams)
