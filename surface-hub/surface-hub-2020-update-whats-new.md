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
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 96452885e19adc9784bb8d14be8ac6f2f86e883d
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442865"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Novidades na atualização do Windows 10 Team 2020

A Atualização do Windows 10 Team 2020 traz melhorias importantes para a implantação e a capacidade de gerenciamento de dispositivos, juntamente com os recursos mais recentes do Windows 10.

##  <a name="deployment-and-manageability"></a>Implantação e capacidade de gerenciamento

- **Autenticação moderna para contas de dispositivos de nuvem.** O Surface Hub dá suporte ao Exchange Web Services (EWS) e à autenticação baseada na Biblioteca de Autenticação do Active Directory (ADAL) para se conectar ao Exchange, permitindo que os clientes preteram o uso da autenticação básica. Para saber mais, confira [Autenticação moderna no Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth).
- Mais de 20 políticas de gerenciamento de dispositivo **móvel (MDM)** novas e atualizadas.      Essas políticas dão aos administradores de TI um controle aprimorado sobre várias configurações de dispositivo, incluindo: atualizações de aplicativos da Microsoft Store, configurações de projeção sem fio, como Miracast sobre infraestrutura, configurações de rede, como Qualidade de Serviço e autenticação com fio 802,1x e novas configurações relacionadas à privacidade/RGPD. Para saber mais, confira: 
- [Gerenciar o Surface Hub com o Microsoft Intune](surface-hub-2s-manage-intune.md).
- [CSPs de políticas suportados pelo Microsoft Surface Hub](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  <a name="azure-active-directory-joined-devices"></a>Dispositivos ingressados no Azure Active Directory

- **SSO (SSO) para dispositivos ingressados no Azure AD.** Quando os usuários entrar com suas credenciais do Microsoft 365 para "Minhas reuniões e arquivos", suas credenciais de usuário fluem perfeitamente de aplicativo para aplicativo , incluindo experiências do Microsoft 365 no navegador.
- **Acesso condicional (CA) para dispositivos ingressados no Azure AD.**       Os administradores de IT podem implantar políticas de segurança no nível de dispositivo no Surface Hub do Azure AD para controlar o acesso aos recursos organizacionais de acordo com os requisitos corporativos de segurança e conformidade.
- **Suporte para administradores não globais para dispositivos ingressados no Azure AD.** Os clientes podem escolher um conjunto mais granular de administradores em sua hierarquia de administradores para gerenciar o Surface Hub. Para saber mais, consulte [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="browser-and-pen"></a>Navegador e caneta

- **Suporte para o novo Microsoft Edge**. O Microsoft Edge foi reconstruído para obter o melhor desempenho de compatibilidade, segurança e privacidade. Para saber mais, confira [Instalar e configurar o novo Microsoft Edge no Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- **Dupla tinta de caneta no Surface Hub 2S**.   Os usuários podem whiteboard e colaborar lado a lado no Surface Hub 2S usando duas Canetas do Surface Hub 2. As atualizações de firmware necessárias para habilitar o uso de dupla caneta serão lançadas com uma atualização subsequente.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **O Microsoft Teams instalado por padrão**.        O Microsoft Teams está incluído como o aplicativo padrão reuniões, chamada e colaboração em novos dispositivos Surface Hub que podem ser alterados ou configurados por meio do MDM ou diretamente no Surface Hub usando o aplicativo Configurações. Para saber mais, confira [Implantar o Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **Suporte para a junção de proximidade com o Microsoft Teams.**  A Junção de Proximidade permite que os usuários adem chamadas agendadas do Microsoft Teams em um Surface Hub próximo usando seu laptop/telefone ou transiem perfeitamente uma reunião em andamento para um Surface Hub próximo. A Atualização do Windows 10 Team 2020 adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar a União de Proximidade. Para saber mais, confira: 

  - [Blog do Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Gerenciar as configurações do Microsoft Teams no Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Suporte para reuniões coordenadas com o Microsoft Teams.** Em salas de reunião que apresentam um Surface Hub e um dispositivo da Sala do Microsoft Teams ou espaços com dois dispositivos Surface Hub, as Reuniões Coordenadas permitem que os usuários aproveitem facilmente os dois dispositivos durante uma reunião do Microsoft Teams. Com um único toque, os usuários podem ingressar em uma reunião de um dispositivo e maximizar a propriedade da tela mostrando feeds de vídeo em um dispositivo e um quadro de trabalho digital ou conteúdo no outro. O Windows 10 Team 2020 Update adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar Reuniões Coordenadas e o recurso será lançado posteriormente como uma atualização do Microsoft Teams por meio do Microsoft Store.To saiba mais em Configurar Reuniões Coordenadas com salas do Microsoft Teams e [Surface Hub.](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)

## <a name="security"></a>Security

- Entrar sem senha usando chaves de segurança **FIDO2**     Usando chaves de segurança FIDO2, os clientes podem entrar rapidamente e facilmente no Surface Hub sem precisar digitar nomes de usuário e senhas. Combinado com o SSO (Single Sign-On), esse recurso fornece autenticação rápida e perfeita para arquivos, aplicativos e sites durante uma reunião. Para saber mais, consulte [Configure passwordless sign-in on Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate).
- **Melhorias na login sem senha usando o Microsoft Authenticator**.  Para organizações que usam o Azure AD, os usuários podem usar o aplicativo Microsoft Authenticator para entrar sem precisar digitar nomes de usuário e senhas. Além disso, os usuários podem entrar usando seus aliases de email preferenciais no Azure AD, além do nome principal do usuário (UPN). Para saber mais, confira [Entrar no Surface Hub com o Microsoft Authenticator](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app).


## <a name="learn-more"></a>Saiba mais

- [Atualização para a versão de lançamento do Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Instale a Atualização do Windows 10 Team 2020](surface-hub-2020-update.md)  
 