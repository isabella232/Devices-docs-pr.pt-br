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
ms.openlocfilehash: f87b8f084b8731bfb329b6c52403d565bca03e3e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312047"
---
# Novidades na atualização do Windows 10 Team 2020

A Atualização do Windows 10 Team 2020 traz melhorias importantes para a implantação e a capacidade de gerenciamento de dispositivos, juntamente com os recursos mais recentes do Windows 10.

##  Implantação e capacidade de gerenciamento

- **Autenticação moderna para contas de dispositivo de nuvem.** O Surface Hub dá suporte aos Serviços Web do Exchange (EWS) e à autenticação baseada na Biblioteca de Autenticação do Active Directory (ADAL) para se conectar ao Exchange, permitindo que os clientes preteram o uso da autenticação Básica. Para saber mais, confira [Autenticação moderna no Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)
- **Mais de 20 políticas de gerenciamento de dispositivo móvel (MDM)** novas e atualizadas.      Essas políticas dão aos administradores de TI maior controle sobre várias configurações de dispositivo, incluindo: atualizações de aplicativos da Microsoft Store, configurações de projeção sem fio, como Miracast sobre infraestrutura, configurações de rede como Qualidade de Serviço e autenticação com fio 802.1x e novas configurações relacionadas à privacidade/RGPD. Para saber mais, confira: 
- [Gerencie o Surface Hub 2S com o Microsoft Intune.](surface-hub-2s-manage-intune.md)
- [CSPs de políticas suportados pelo Microsoft Surface Hub](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  Dispositivos ingressados no Azure Active Directory

- **SSO (SSO) para dispositivos ingressados no Azure AD.** Quando os usuários se conectem com suas credenciais do Microsoft 365 para "Minhas reuniões e arquivos", suas credenciais de usuário fluem perfeitamente de aplicativo para aplicativo, incluindo experiências do Microsoft 365 no navegador.
- **Acesso condicional (CA) para dispositivos ingressados no Azure AD.**       Os administradores de IT podem implantar políticas de segurança no nível do dispositivo no Surface Hub ingressado no Azure AD para controlar o acesso aos recursos organizacionais de acordo com os requisitos de conformidade e segurança corporativa.
- **Suporte para administradores não globais para dispositivos ingressados no Azure AD.** Os clientes podem escolher um conjunto mais granular de administradores em sua hierarquia de administração para gerenciar o Surface Hub. Para saber mais, consulte [Configurar contas de administrador não globais no Surface Hub 2S.](surface-hub-2s-nonglobal-admin.md)


## Navegador e caneta

- **Suporte para o novo Microsoft Edge.** O Microsoft Edge foi reconstruído para obter o melhor desempenho, segurança e privacidade de compatibilidade. Para saber mais, consulte [Instalar e configurar o novo Microsoft Edge no Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- - **Tinta com caneta dupla no Surface Hub 2S.**   Os usuários podem fazer whiteboard e colaborar lado a lado no Surface Hub 2S usando duas Canetas do Surface Hub 2. As atualizações de firmware necessárias para habilitar a tinta com caneta dupla serão lançadas com uma atualização subsequente.

## Microsoft Teams  

- **O Microsoft Teams instalado por padrão.**        O Microsoft Teams está incluído como o aplicativo padrão de reuniões, chamada e colaboração em novos dispositivos Surface Hub que podem ser alterados ou configurados via MDM ou diretamente no Surface Hub usando o aplicativo Configurações. Para saber mais, confira [Implantar o Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **Suporte para o união de proximidade com o Microsoft Teams.**  O Recurso de Proximidade permite aos usuários fazer chamadas agendadas do Microsoft Teams em um Surface Hub próximo usando seu laptop/telefone ou fazer a transição perfeita de uma reunião em andamento para um Surface Hub próximo. A Atualização do Windows 10 Team 2020 adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar o Proximity Join. Para saber mais, confira: 

  - [Blog do Microsoft Teams.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833) 
  - [Gerenciar as configurações do Microsoft Teams no Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Suporte para reuniões coordenadas com o Microsoft Teams.** Em salas de reunião que apresentam um Surface Hub e um dispositivo de Sala do Microsoft Teams ou espaços com dois dispositivos Surface Hub, as Reuniões Coordenadas permitem que os usuários aproveitem facilmente os dois dispositivos durante uma reunião do Microsoft Teams. Com um único toque, os usuários podem ingressar em uma reunião em qualquer dispositivo e maximizar o estado real da tela mostrando feeds de vídeo em um dispositivo e um quadro de branco digital ou conteúdo no outro. A Atualização do Windows 10 Team 2020 adiciona suporte ao Gerenciamento de Dispositivo Móvel (MDM) para configurar Reuniões Coordenadas, e o recurso será lançado posteriormente como uma atualização do Microsoft Teams por meio do Microsoft Store.To saiba mais, confira Configurar reuniões coordenadas com salas do Microsoft Teams e [Surface Hub.](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)

## Segurança

- Entrar sem senha usando chaves de **segurança FIDO2**     Usando chaves de segurança FIDO2, os clientes podem entrar com rapidez e facilidade no Surface Hub sem precisar digitar nomes de usuário e senhas. Combinado com o SSO (single Sign-On), esse recurso fornece autenticação rápida e perfeita para arquivos, aplicativos e sites durante uma reunião. Para saber mais, confira Configurar a login sem [senha no Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)
- **Melhorias na login sem senha usando o Microsoft Authenticator.**  Para organizações que usam o Azure AD, os usuários podem usar o aplicativo Microsoft Authenticator para entrar sem precisar digitar nomes de usuário e senhas. Além disso, os usuários podem entrar usando seus aliases de email preferenciais no Azure AD, além do NOME UPN. Para saber mais, confira [Entrar no Surface Hub com o Microsoft Authenticator.](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## Saiba mais

- [Atualização para a versão de lançamento do Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Instale a Atualização do Windows 10 Team 2020](surface-hub-2020-update.md)  
 