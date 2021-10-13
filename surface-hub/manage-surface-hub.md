---
title: Gerenciar o Microsoft Surface Hub
description: Como gerenciar o Surface Hub após a conclusão do programa de primeira execução.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gerenciar o Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/17/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7fa715c679803da460cc1d57bd6e84fa33d30413
ms.sourcegitcommit: d9c413f1c50908a81e5489aca2c6023eab573148
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2021
ms.locfileid: "12093038"
---
# <a name="manage-microsoft-surface-hub"></a>Gerenciar o Microsoft Surface Hub

Após a configuração inicial do Microsoft Surface Hub, as configurações e as configurações do dispositivo podem ser modificadas ou alteradas de algumas maneiras:

- **Gerenciamento local** – Cada Surface Hub pode ser configurado localmente usando-se o aplicativo **Configurações** no dispositivo. Para evitar que usuários não autorizados alterem configurações, o aplicativo Configurações requer credenciais de administrador para abrir o aplicativo. Para obter mais informações, consulte [Gerenciamento local para configurações do Surface Hub](local-management-surface-hub-settings.md).
- **Gerenciamento** remoto - Surface Hub permitir que os administradores de TI gerenciem configurações e políticas usando um provedor de gerenciamento de dispositivo móvel (MDM), como Microsoft Intune, Microsoft Endpoint Configuration Manager e outros provedores de terceiros. Além disso, os administradores podem monitorar Surface Hubs usando o Azure Monitor.  Para obter mais informações, consulte [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md), and [Monitor Surface Hubs with Azure Monitor to track their health](/azure/azure-monitor/insights/surface-hubs). 

> [!NOTE]
> Esses métodos de gerenciamento não são mutuamente exclusivos. Os dispositivos podem ser gerenciados local e remotamente se você preferir. No entanto, as políticas e configurações do MDM substituirão as alterações locais quando o Surface Hub sincronizar com o servidor de gerenciamento. 

## <a name="in-this-section"></a>Nesta seção

Saiba mais sobre como gerenciar e atualizar o Surface Hub.

| Tópico | Descrição |
| ----- | ----------- |
| [Gerenciamento remoto do Surface Hub](remote-surface-hub-management.md) |Tópicos relacionados ao gerenciamento remoto do Surface Hub. Inclua instalar aplicativos, gerenciar configurações com o MDM e monitorar com o Operations Management Suite. |
| [Gerenciar configurações do Surface Hub](manage-surface-hub-settings.md) |Tópicos relacionados ao gerenciamento das configurações do Surface Hub: acessibilidade, conta de dispositivo, redefinição de dispositivo, nome de domínio totalmente qualificado, configurações do Windows Update e rede sem fio |
| [Instalar aplicativos no Surface Hub](install-apps-on-surface-hub.md) | Os administradores podem instalar aplicativos da Microsoft Store ou da Microsoft Store para Empresas.|
[Configurar o menu Iniciar do Surface Hub](surface-hub-start-menu.md) | Use o MDM para personalizar o menu Iniciar para o Surface Hub.
| [Configurar e usar o Microsoft Whiteboard](whiteboard-collaboration.md)  | Atualização mais recente do Microsoft Whiteboard inclui a capacidade para dois Surface Hubs colaborarem em tempo real na mesma placa.   |
| [Encerrar uma reunião com Encerrar sessão](finishing-your-surface-hub-meeting.md) | No final de uma reunião, os usuários podem tocar em **Encerrar sessão** para apagar dados confidenciais e preparar o dispositivo para a próxima reunião.|
| [Faça logon no Surface Hub com Microsoft Authenticator](surface-hub-authenticator-app.md) | Você pode fazer logon em um Surface Hub sem uma senha usando o aplicativo Microsoft Authenticator, disponível em Android e iOS.   |
| [Salvar a chave do BitLocker](save-bitlocker-key-surface-hub.md) | Todo Surface Hub é configurado automaticamente com o software de criptografia de unidade de disco BitLocker. A Microsoft recomenda veementemente que você faça o backup das chaves de recuperação do BitLocker.|
| [Conectar outros dispositivos e exibir seu conteúdo com o Surface Hub](connect-and-display-with-surface-hub.md) | Você pode conectar outro dispositivo ao Surface Hub para exibir seu conteúdo.|
| [Miracast em rede sem fio existente ou LAN](miracast-over-infrastructure.md) | Você pode usar Miracast em sua rede sem fio ou LAN para se conectar ao Surface Hub. |
 [Habilitar autenticação com fio 802.1x](enable-8021x-wired-authentication.md) | As políticas do MDM de Autenticação com Fio 802.1x têm sido habilitadas em dispositivos Surface Hub. 
| [Uso de um sistema de controle de sala](use-room-control-system-with-surface-hub.md) | Sistemas de controle de sala podem ser usados com o Microsoft Surface Hub.|
[Uso da Ferramenta de Recuperação do Surface Hub](surface-hub-recovery-tool.md) | Use a Surface Hub Ferramenta de Recuperação para reimimá-lo Surface Hub SSD.
[Substituição da SSD do Surface Hub](surface-hub-ssd-replacement.md) | Saiba como remover e substituir a unidade de estado sólido em sua Surface Hub.

## <a name="related-topics"></a>Tópicos relacionados

- [Exibir o modo de apresentação Power BI no Surface Hub e no Windows 10](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)
