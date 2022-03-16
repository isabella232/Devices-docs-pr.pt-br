---
title: Novidades nas atualizações Windows 10 Team 2020
description: Confira as novidades na atualização mais recente do sistema operacional Surface Hub, Windows 10 Team 2020 Update.
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
ms.openlocfilehash: c44ec68a39158910c841375aeda0a6d6bf11635f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448264"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Novidades nas atualizações Windows 10 Team 2020

Surface Hub benefícios de atualizações periódicas que oferecem novos recursos e funcionalidades. A Atualização 2020 (20H2) para Windows 10 Team e, posteriormente, a Atualização 1 & Atualização 2, oferecem melhorias significativas na implantação e na capacidade de gerenciamento de dispositivos, juntamente com os recursos Windows 10 mais recentes.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 Team Atualização 2020 

### <a name="gcc-high-support"></a>GCC suporte alto

Após a instalação dessa atualização ([KB5010415](https://support.microsoft.com/help/5010415) ou uma cu Windows posterior), os Surface Hubs são suportados em ambientes GCC High. Neste momento, etapas [adicionais ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) são necessárias para que o cliente Salas do Teams se conecte com êxito GCC alto locatários.

### <a name="ease-of-access-updates"></a>Facilidade de atualizações do Access

Os usuários podem ajustar as configurações de Facilidade de Acesso durante uma sessão de Surface Hub e fechar aplicativos, assim como fazem em outras versões do Windows 10. 

- **Facilidade de Acesso**. Os usuários podem ajustar as seguintes configurações sem entrar: Display, Text cursor, Lupa, Alto contraste, Narrador, Legendas fechadas e Teclado. 
- **Interface do usuário familiar para aplicativos**. Os usuários podem fechar aplicativos no Surface Hub selecionando o botão Fechar no canto superior direito do aplicativo. Isso remove a necessidade de fechar aplicativos arrastando-os para a parte inferior do Surface Hub de exibição. (Observação: essa funcionalidade estará disponível no navegador de Borda como parte da próxima atualização de Borda, agendada para março de 2022.) 

Para saber mais, confira [Ajustar configurações de Facilidade de Acesso Surface Hub](accessibility-surface-hub.md).

### <a name="administrator-updates"></a>Atualizações de administrador

- **Visualizador de Eventos**. Os administradores podem acessar o Windows visualizador de eventos diretamente do Configurações app. 
- **Novas configurações de política de gerenciamento de dispositivo móvel (MDM**). Os novos provedores de serviços de configuração (CSPs) incluem:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

Para saber mais, consulte [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="windows-10-team-2020-update-1"></a>Windows 10 Team Atualização 1 de 2020

### <a name="support-for-new-teams-rooms-application"></a>Suporte para novo Salas do Teams aplicativo

Após a instalação dessa atualização ([KB5005101](https://support.microsoft.com/help/5005101) ou uma cu Windows posterior), os Surface Hubs suportam uma atualização automática para o novo cliente [Salas do Teams](surface-hub-teams-rooms.md) por meio do Windows Update.

### <a name="support-for-new-whiteboard-application"></a>Suporte para novo aplicativo de quadro de trabalho

Após a instalação dessa atualização, os Surface Hubs suportam uma atualização automática (quando disponível) para o novo aplicativo [de quadro](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) de Microsoft Store atualizações.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>Novo Microsoft Edge navegador instalado por padrão

Após a instalação dessa atualização, os Surface Hubs substituirão automaticamente seu navegador Versão Prévia do Microsoft Edge por um novo navegador Chromium de Borda baseado em Chromium.  Para saber mais, consulte [Manage Microsoft Edge on Surface Hub](surface-hub-install-chromium-edge.md). O Edge Legacy não está mais disponível no Windows 10 Team após a instalação dessa atualização ou uma atualização Windows CU subsequente.


## <a name="windows-10-team-2020-update-20h2"></a>Atualização do Windows 10 Team 2020 (20H2)

### <a name="deployment-and-manageability"></a>Implantação e capacidade de gerenciamento

- **Autenticação moderna para contas de dispositivos na nuvem**. Surface Hub dá suporte Exchange Web Services (EWS) e autenticação baseada na Biblioteca de Autenticação do Active Directory (ADAL) para se conectar ao Exchange, permitindo que os clientes preteram o uso da autenticação básica. Para saber mais, confira [Autenticação moderna no Surface Hub](surface-hub-modern-auth.md).
- **Mais de 20 configurações de política MDM novas e atualizadas**.  Essas configurações de política dão aos administradores de TI um controle aprimorado sobre várias configurações de dispositivo, incluindo atualizações de aplicativos do Microsoft Store, configurações de projeção sem fio, como Miracast sobre infraestrutura, configurações de rede, como Qualidade de Serviço e autenticação com fio 802,1x e novas configurações relacionadas à privacidade/RGPD. Os novos CSPs incluem:

  - [CSP Accounts](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [CSP RemoteWipe](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

Para saber mais, confira:

- [CSPs com suporte em Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Gerenciar o Surface Hub com um provedor MDM](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory ingressados

- **SSO (entrada única) para dispositivos ingressados no Azure AD**. Quando os usuários entrarem com suas credenciais Microsoft 365 minhas reuniões e **** arquivos suas credenciais fluem perfeitamente de aplicativo para aplicativo , incluindo Microsoft 365 experiências no navegador.
- **Acesso condicional (CA) para dispositivos ingressados no Azure AD**. Os administradores de IT podem controlar o acesso do usuário aos recursos organizacionais dos Surface Hubs ingressados no Azure AD atribuindo políticas de dispositivo de acordo com seus requisitos corporativos de segurança e conformidade.
- **Suporte para administradores não globais para dispositivos ingressados no Azure AD**. Os clientes podem escolher um conjunto mais granular de administradores em sua hierarquia de administradores para gerenciar Surface Hub. Para saber mais, consulte [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

### <a name="inking-improvements"></a>Melhorias de inking

- **Suporte para duplo uso de caneta no Surface Hub 2S**.  Use o quadro de trabalho e colabore lado a lado no Surface Hub 2S com duas Surface Hub 2 Canetas. Qualquer atualização de hardware do sistema instalada após a atualização para o Windows 10 Team 2020 adicionará suporte ao firmware para esse cenário.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams instalado por padrão**. Microsoft Teams é incluído como o aplicativo padrão para reuniões, chamadas e colaboração em novos dispositivos Surface Hub, que podem ser alterados ou configurados via MDM ou diretamente no Surface Hub usando o aplicativo Configurações. Para saber mais, consulte [Deploy Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Suporte para a junção de proximidade com Microsoft Teams**.  A União de Proximidade permite que os usuários Microsoft Teams chamadas agendadas em um Surface Hub usando seu laptop ou telefone.  Ele também permite aos usuários fazer a transição de uma reunião em andamento para um local Surface Hub. Windows 10 Team atualização 2020 adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar a Junção de Proximidade. Para saber mais, confira:

  - [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Gerenciar as configurações do Microsoft Teams no Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Suporte para reuniões coordenadas com Microsoft Teams**. Em salas de reunião que apresentam um Surface Hub e um dispositivo de sala Microsoft Teams, ou espaços com dois dispositivos Surface Hub, reuniões coordenadas permitem que os usuários aproveitem rapidamente os dois dispositivos durante uma reunião Microsoft Teams. Os usuários podem participar de uma reunião de um dispositivo com um único toque e maximizar a propriedade da tela mostrando feeds de vídeo em um dispositivo e um quadro de trabalho digital ou conteúdo no outro. Windows 10 Team Atualização 2020 adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar Reuniões Coordenadas, e o recurso será lançado posteriormente como uma atualização Microsoft Teams por meio do Microsoft Store. Para saber mais, confira [Configurar Reuniões Coordenadas com Salas do Microsoft Teams e Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### <a name="security"></a>Segurança

- **Entrar sem senha usando chaves de segurança FIDO2** Com chaves de segurança FIDO2, os usuários podem entrar rapidamente no Surface Hub sem digitar nomes de usuário e senhas. Combinado com o SSO (single Sign-On), esse recurso fornece autenticação rápida e perfeita para arquivos, aplicativos e sites durante uma reunião. Para saber mais, consulte [Configure passwordless sign-in on Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Melhorias na login sem senha usando Microsoft Authenticator**.  Para organizações que usam o Azure AD, os usuários podem entrar com o Microsoft Authenticator app. Além disso, os usuários podem entrar com seus aliases de email preferidos no Azure AD, bem como seu Nome de Entidade de Usuário (UPN). Para saber mais, confira [Entrar Surface Hub com Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>Saiba mais

- [Windows 10 Team Atualização 1 2020 lançada para todos os Surface Hubs](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 Team atualização 2020 disponível em 27 de outubro](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Instale a Atualização do Windows 10 Team 2020](surface-hub-2020-update.md)
