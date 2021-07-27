---
title: Novidades na atualização do Windows 10 Team 2020
description: Confira as novidades na atualização mais recente do sistema operacional Surface Hub, Windows 10 Team 2020 Update.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 753f0b64eb05e6d18d0ec2e32af8e0566a8c50b5
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676635"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Novidades na atualização do Windows 10 Team 2020

Windows 10 Team atualização 2020 traz melhorias importantes para a implantação e a capacidade de gerenciamento de dispositivos, juntamente com os recursos Windows 10 mais recentes.

##  <a name="deployment-and-manageability"></a>Implantação e capacidade de gerenciamento

- **Autenticação moderna para contas de dispositivos de nuvem.** O Surface Hub oferece suporte Exchange web services (EWS) e autenticação baseada na Biblioteca de Autenticação do Active Directory (ADAL) para se conectar ao Exchange, permitindo que os clientes preteram o uso da autenticação básica. Para saber mais, confira [Autenticação moderna no Surface Hub](surface-hub-modern-auth.md).
- Mais de 20 configurações de política de gerenciamento de dispositivo **móvel (MDM) novas e atualizadas.**  Essas configurações de política dão aos administradores de TI um controle aprimorado sobre várias configurações de dispositivo, incluindo: atualizações de aplicativos do Microsoft Store, configurações de projeção sem fio, como Miracast sobre infraestrutura, configurações de rede, como Qualidade de Serviço e autenticação com fio 802,1x e novas configurações relacionadas à privacidade/RGPD. Os novos provedores de serviços de configuração (CSPs) incluem: 

  - [CSP Accounts](/windows/client-management/mdm/accounts-csp) 
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp) 
  - [CSP RemoteWipe](/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp) 

Para saber mais, confira: 
- [CSPs com suporte em Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Gerenciar o Surface Hub com um provedor MDM](manage-settings-with-mdm-for-surface-hub.md)


##  <a name="azure-active-directory-joined-devices"></a>Azure Active Directory Dispositivos ingressados

- **SSO (SSO) para dispositivos ingressados no Azure AD.** Quando os usuários Microsoft 365 suas credenciais para "Minhas reuniões e arquivos", suas credenciais de usuário fluem perfeitamente de aplicativo para aplicativo, incluindo Microsoft 365 experiências no navegador.
- **Acesso condicional (CA) para dispositivos ingressados no Azure AD.** Os administradores de IT podem controlar o acesso do usuário aos recursos organizacionais dos Surface Hubs ingressados no Azure AD atribuindo políticas de dispositivo de acordo com seus requisitos corporativos de segurança e conformidade.
- **Suporte para administradores não globais para dispositivos ingressados no Azure AD.** Os clientes podem escolher um conjunto mais granular de administradores em sua hierarquia de administradores para gerenciar Surface Hub. Para saber mais, consulte [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="browser-and-pen"></a>Navegador e caneta

- **Suporte para o novo Microsoft Edge**. Microsoft Edge foi reconstruído para obter o melhor desempenho de compatibilidade, segurança e privacidade. Para saber mais, consulte [Install and configure the new Microsoft Edge on Surface Hub](surface-hub-install-chromium-edge.md).
- **Dual-pen inking no Surface Hub 2S**.   Os usuários podem fazer whiteboard e colaborar lado a lado no Surface Hub 2S usando duas Surface Hub 2 Canetas. As atualizações de firmware necessárias para habilitar o uso de dupla caneta serão lançadas com uma atualização subsequente.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams instalado por padrão**.        Microsoft Teams é incluído como o aplicativo padrão reuniões, chamada e colaboração em novos dispositivos Surface Hub que podem ser alterados ou configurados por meio do MDM ou diretamente no Surface Hub usando o aplicativo Configurações. Para saber mais, consulte [Deploy Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Suporte para a junção de proximidade com Microsoft Teams**.  A União de Proximidade permite que os usuários Microsoft Teams chamadas agendadas em um Surface Hub usando seu laptop/telefone ou transibilem perfeitamente uma reunião em andamento para um Surface Hub. Windows 10 Team atualização 2020 adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar a Junção de Proximidade. Para saber mais, confira: 

  - [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Gerenciar as configurações do Microsoft Teams no Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Suporte para reuniões coordenadas com Microsoft Teams**. Em salas de reunião que apresentam um Surface Hub e um dispositivo de sala Microsoft Teams, ou espaços com dois dispositivos Surface Hub, as Reuniões Coordenadas permitem que os usuários aproveitem facilmente os dois dispositivos durante uma Microsoft Teams reunião. Com um único toque, os usuários podem ingressar em uma reunião de um dispositivo e maximizar a propriedade da tela mostrando feeds de vídeo em um dispositivo e um quadro de trabalho digital ou conteúdo no outro. Windows 10 Team atualização 2020 adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar Reuniões Coordenadas, e o recurso será lançado posteriormente como uma atualização Microsoft Teams por meio do Microsoft Store. Para saber mais, confira [Configurar Reuniões Coordenadas com Salas do Microsoft Teams e Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

## <a name="security"></a>Security

- Entrar sem senha usando chaves de segurança **FIDO2**     Usando chaves de segurança FIDO2, os clientes podem entrar rapidamente e facilmente Surface Hub sem precisar digitar nomes de usuário e senhas. Combinado com o SSO (Single Sign-On), esse recurso fornece autenticação rápida e perfeita para arquivos, aplicativos e sites durante uma reunião. Para saber mais, consulte [Configure passwordless sign-in on Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Melhorias na login sem senha usando Microsoft Authenticator**.  Para organizações que usam o Azure AD, os usuários podem usar o aplicativo Microsoft Authenticator para entrar sem precisar digitar nomes de usuário e senhas. Além disso, os usuários podem entrar usando seus aliases de email preferenciais no Azure AD, além do nome principal do usuário (UPN). Para saber mais, confira [Entrar Surface Hub com Microsoft Authenticator](surface-hub-authenticator-app.md).


## <a name="learn-more"></a>Saiba mais

- [Atualização para a versão de lançamento do Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Instale a Atualização do Windows 10 Team 2020](surface-hub-2020-update.md)  
 
