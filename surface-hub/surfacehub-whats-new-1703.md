---
title: Novidades no Windows 10, versão 1703 para o Surface Hub
description: Windows 10, versão 1703 (Atualização para criadores) traz novos recursos ao Microsoft Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924937"
---
# O que há de novo no Windows 10, versão 1703 para o Microsoft Surface Hub?

Assista ao engenheiro de Surface Hub, Jordan Marchese, apresentar atualizações do Microsoft Surface Hub com Windows 10, versão 1703 (criadores de atualização). 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

O Windows 10, versão 1703 (também chamado da Atualização para Criadores), apresenta as seguintes alterações para o Microsoft Surface Hub.

##  <a name="new-settings"></a>Novas configurações

As configurações foram adicionadas ao gerenciamento de dispositivo móvel (MDM) e aos provedores de serviço de configuração (CSPs) para expandir os recursos de gerenciamento do Surface Hub. [As novas configurações incluem](manage-settings-with-mdm-for-surface-hub.md):

- InBoxApps/SkypeForBusiness/DomainName
- InBoxApps/Connect/AutoLaunch
- Properties/DefaultVolume
- Properties/ScreenTimeout
- Properties/SessionTimeout
- Properties/SleepTimeout
- Properties/AllowSessionResume
- Properties/AllowAutoProxyAuth
- Properties/DisableSigninSuggestions
- Properties/DoNotShowMyMeetingsAndFiles
- System/AllowStorageCard

Além das configurações baseadas no novo [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) e [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).
</br>

##  <a name="provisioning-wizard"></a>Assistente de provisionamento

Um assistente fácil de usar ajuda você a criar rapidamente os pacotes de provisionamento que podem ser aplicados a vários dispositivos Surface Hub e inclui o ingresso em massa no Azure Active Directory. [Saiba como criar um pacote de provisionamento para o Surface Hub.](provisioning-packages-for-certificates-surface-hub.md)

![Etapas no assistente de dispositivos de provisionamento do Surface Hub](images/wcd-wizard.png)
    
##  <a name="miracast-on-your-existing-wireless-network-or-lan"></a>Miracast em sua rede sem fio existente ou LAN 

A Microsoft estendeu a capacidade de [enviar um fluxo de Miracast por uma rede local](miracast-over-infrastructure.md), e não por um link direto sem fio. 
    
##  <a name="cloud-recovery"></a>Recuperação na nuvem

Ao restaurar um dispositivo Surface Hub, agora você pode baixar e instalar uma versão de fábrica do sistema operacional da nuvem. [Saiba mais sobre a recuperação na nuvem.](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
>A recuperação na nuvem não funciona com servidores proxy.
    
![Reinstalar](images/reinstall.png)
    
##  <a name="end-session"></a>Encerrar sessão

**Terminei** agora é **Encerrar a sessão**. [Saiba como usar a opção de Encerrar a sessão.](finishing-your-surface-hub-meeting.md) 

![encerrar a sessão](images/end-session.png)



 

 
