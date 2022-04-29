---
title: Novidades nas atualizações Windows 10 Team 2020
description: Confira as novidades na atualização mais recente do sistema operacional Surface Hub, Windows 10 Team 2020.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
ms.openlocfilehash: 995766eb216051de270a387c15c96ee42dd008a3
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497954"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Novidades nas atualizações Windows 10 Team 2020

Surface Hub benefícios de atualizações periódicas que fornecem novos recursos e funcionalidades. A Atualização 2020 (20H2) para o Windows 10 Team e, posteriormente, a Atualização 1 do & Atualização 2, oferecem melhorias significativas na implantação e na capacidade de gerenciamento do dispositivo, juntamente com os recursos mais Windows mais recentes.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 Team Atualização 2 de 2020 

### <a name="gcc-high-support"></a>GCC suporte alto

Após a instalação dessa atualização ([KB5010415](https://support.microsoft.com/help/5010415) ou uma CU de Windows subsequente), os Surface Hubs têm suporte em ambientes GCC Alta. Neste momento, etapas [adicionais são ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) necessárias para que o Salas do Teams cliente se conecte com êxito GCC locatários altos.

### <a name="support-for-surface-hub-2-smart-camera"></a>Suporte para Surface Hub 2 Smart Camera

A Câmera Inteligente do Surface Hub 2 da plataforma IA é otimizada para equipes híbridas, permitindo que os participantes remotos vejam as pessoas interagirem com o conteúdo no Surface Hub enquanto também exibem todas as outras pessoas na sala.  Para saber mais, confira [Instalar e gerenciar Surface Hub 2 Smart Camera](surface-hub-2-smart-camera.md). 

### <a name="support-for-progressive-web-apps-pwas"></a>Suporte para PWAs (Aplicativos Web progressivo)

Os administradores podem instalar remotamente PWAs em Surface Hubs usando um MDM (provedor de gerenciamento de dispositivo móvel) aplicando um pacote de provisionamento. Para saber mais, confira [Instalar o Aplicativos Web Progressivo no Surface Hub](install-pwa-surface-hub.md). 

### <a name="ease-of-access-updates"></a>Atualizações de facilidade de acesso

Os usuários podem ajustar as configurações de Facilidade de Acesso durante uma sessão Surface Hub e fechar aplicativos, assim como fazem em outras versões do Windows 10 ou Windows 11. 

- **Facilidade de acesso**. Os usuários podem ajustar as seguintes configurações sem entrar: Exibição, Cursor de texto, Lupa, Alto Contraste, Narrador, Legendas ocultas e Teclado. 
- **Interface do usuário familiar para aplicativos**. Os usuários podem fechar aplicativos no Surface Hub selecionando o botão Fechar no canto superior direito do aplicativo. Isso remove a necessidade de fechar aplicativos arrastando-os para a parte inferior da Surface Hub exibição. (Observação: essa funcionalidade estará disponível no navegador Edge como parte da próxima atualização do Edge, agendada para março de 2022.) 

Para saber mais, confira [Ajustar as configurações de Facilidade de Acesso Surface Hub](accessibility-surface-hub.md).

### <a name="administrator-updates"></a>Atualizações do administrador

- **Visualizador de Eventos.** Os administradores podem acessar o Windows Visualizador de Eventos diretamente do Configurações aplicativo. 
- **Novas configurações de política de MDM (gerenciamento de dispositivo móvel**). Os novos CSPs (provedores de serviços de configuração) incluem:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

Para saber mais, confira [Configurar contas de administrador não globais Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="windows-10-team-2020-update-1"></a>Windows 10 Team Atualização 1 de 2020

### <a name="support-for-new-teams-rooms-application"></a>Suporte para novo Salas do Teams aplicativo

Após a instalação dessa atualização ([KB5005101](https://support.microsoft.com/help/5005101) ou uma cu Windows subsequente), os Surface Hubs dão suporte a uma atualização automática para o novo [cliente Salas do Teams](surface-hub-teams-rooms.md) por meio do Windows Update.

### <a name="support-for-new-whiteboard-application"></a>Suporte para o novo aplicativo Whiteboard

Após a instalação dessa atualização, os Surface Hubs dão suporte a uma atualização automática (quando disponível) para o novo aplicativo [Whiteboard](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) por meio Microsoft Store atualizações.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>Novo Microsoft Edge de dados instalado por padrão

Após a instalação dessa atualização, os Surface Hubs substituirão automaticamente seus navegadores Versão Prévia do Microsoft Edge pelo novo navegador edge Chromium baseado em Chromium.  Para saber mais, confira [Gerenciar Microsoft Edge no Surface Hub](surface-hub-install-chromium-edge.md). O Edge Legacy não está mais disponível no Windows 10 Team após a instalação dessa atualização ou uma atualização Windows CU subsequente.


## <a name="windows-10-team-2020-update-20h2"></a>Atualização do Windows 10 Team 2020 (20H2)

### <a name="deployment-and-manageability"></a>Implantação e capacidade de gerenciamento

- **Autenticação moderna para contas de dispositivo de nuvem**. O Surface Hub dá suporte Exchange autenticação baseada em serviços Web (EWS) e ADAL (Biblioteca de Autenticação do Active Directory) para se conectar ao Exchange, permitindo que os clientes preteram o uso da autenticação básica. Para saber mais, confira [Autenticação moderna Surface Hub](surface-hub-modern-auth.md).
- **Mais de 20 configurações de política de MDM novas e atualizadas**.  Essas configurações de política oferecem aos administradores de TI um controle aprimorado sobre várias configurações de dispositivo, incluindo atualizações de aplicativo do Microsoft Store, configurações de projeção sem fio, como Miracast sobre infraestrutura, configurações de rede, como Qualidade de Serviço e autenticação com fio 802.1x e novas configurações relacionadas à privacidade/RGPD. Os novos CSPs incluem:

  - [CSP Accounts](/windows/client-management/mdm/accounts-csp)
  - [Firewall -CSP](/windows/client-management/mdm/firewall-csp)
  - [CSP RemoteWipe](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

Para saber mais, confira:

- [CSPs com suporte no Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Gerenciar o Surface Hub com um provedor MDM](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory dispositivos ingressados

- **SSO (logon único) para Azure AD ingressados**. Quando os usuários Microsoft 365 suas credenciais para Minhas reuniões e **arquivos, suas** credenciais fluem perfeitamente de aplicativo para aplicativo, incluindo Microsoft 365 experiências no navegador.
- **Ac (acesso condicional) para Azure AD ingressados**. Os administradores de TI podem controlar o acesso do usuário aos recursos organizacionais Azure AD Surface Hubs ingressados atribuindo políticas de dispositivo de acordo com seus requisitos corporativos de segurança e conformidade.
- **Suporte para administradores não globais para Azure AD ingressados**. Os clientes podem escolher um conjunto mais granular de administradores em sua hierarquia de administração para gerenciar Surface Hub. Para saber mais, confira [Configurar contas de administrador não globais Surface Hub](surface-hub-2s-nonglobal-admin.md).

### <a name="inking-improvements"></a>Melhorias de escrita à tinta

- **Suporte para escrita à tinta com caneta dupla Surface Hub 2S**.  Use o quadro de comunicações e colabore lado a lado no Surface Hub 2S com duas Surface Hub 2 Canetas. Qualquer atualização de hardware do sistema instalada após a atualização para o Windows 10 Team 2020 adicionará suporte a firmware para esse cenário.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams instalado por padrão**. Microsoft Teams é o aplicativo padrão para reuniões, chamadas e colaboração em novos dispositivos Surface Hub, que podem ser alterados ou configurados por meio do MDM ou diretamente no Surface Hub usando o aplicativo Configurações. Para saber mais, confira [Implantar Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Suporte para ingresso por proximidade com Microsoft Teams**.  O Ingresso por Proximidade permite que os usuários Microsoft Teams chamadas agendadas em um Surface Hub usando seu laptop ou telefone.  Ele também permite aos usuários fazer a transição de uma reunião em andamento para uma reunião Surface Hub. Windows 10 Team atualização de 2020 adiciona suporte Gerenciamento de Dispositivos (MDM) móvel para configurar o Ingresso por Proximidade. Para saber mais, confira:

  - [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Gerenciar as configurações do Microsoft Teams no Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Suporte para reuniões coordenadas com Microsoft Teams**. Em salas de reunião que apresentam um Surface Hub e um dispositivo de sala Microsoft Teams ou espaços com dois dispositivos Surface Hub, as Reuniões Coordenadas permitem que os usuários aproveitem rapidamente os dois dispositivos durante uma Microsoft Teams reunião. Os usuários podem ingressar em uma reunião de qualquer dispositivo com um único toque e maximizar a propriedade da tela mostrando feeds de vídeo em um dispositivo e um quadro de comunicações digital ou conteúdo no outro. Windows 10 Team Atualização 2020 adiciona suporte ao MDM (Mobile Gerenciamento de Dispositivos) para configurar Reuniões Coordenadas e o recurso será lançado posteriormente como uma atualização Microsoft Teams por meio do Microsoft Store. Para saber mais, confira [Configurar Reuniões Coordenadas com Salas do Microsoft Teams e Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### <a name="security"></a>Segurança

- **Entrada sem senha usando chaves de segurança FIDO2** Com as chaves de segurança FIDO2, os usuários podem entrar rapidamente no Surface Hub sem digitar nomes de usuário e senhas. Combinado com o SSO (single Sign-On), esse recurso fornece autenticação rápida e perfeita para arquivos, aplicativos e sites durante uma reunião. Para saber mais, confira [Configurar a entrada sem senha no Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Melhorias na entrada sem senha usando Microsoft Authenticator**.  Para organizações que usam Azure AD, os usuários podem entrar com o Microsoft Authenticator aplicativo. Além disso, os usuários podem entrar com seus aliases de email preferenciais no Azure AD ou no NOME UPN. Para saber mais, confira [Entrar no Surface Hub com Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>Saiba mais

- [Windows 10 Team Atualização 1 de 2020 lançada para todos os Surface Hubs](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 Team atualização de 2020 disponível em 27 de outubro](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Instale a Atualização do Windows 10 Team 2020](surface-hub-2020-update.md)
