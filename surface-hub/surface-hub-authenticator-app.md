---
title: Fazer logon no Surface Hub com o Microsoft Authenticator
description: Use o Microsoft Authenticator em seu dispositivo móvel para fazer logon no Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830416"
---
# Faça logon no Surface Hub com Microsoft Authenticator

Pessoas em sua organização podem fazer logon em um Surface Hub sem uma senha usando o aplicativo Microsoft Authenticator, disponível em Android e iOS.

## Pré-requisitos de organização

Para permitir que as pessoas em sua organização efetuem login no Surface Hub com seus telefones e outros dispositivos em vez de uma senha, você precisará garantir que sua organização atende a esses pré-requisitos: 

- Sua organização deve ser uma organização híbrida ou somente na nuvem, respaldada pelo Active Directory do Azure (Azure AD). Para saber mais, consulte [O que é o Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis).

- Certifique-se de que você tem, pelo menos, uma assinatura do Office 365 E3. 

- [Configurar autenticação multi-fator](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings). Certifique-se de **Notificação pelo aplicativo móvel** está selecionado. 

    ![opções de autenticação multi-fator](images/mfa-options.png)

- Habilite a hospedagem de conteúdo nos serviços do Azure AD, como o Office, o SharePoint, etc. 

- O Surface Hub deve estar executando o Windows 10, versão 1703 ou posterior.

- O Surface Hub é configurado com uma conta local ou domínio.

No momento, você não pode usar o Microsoft Authenticator para iniciar sessão em Surface Hubs que ingressaram no Azure AD.

## Pré-requisitos individuais

- Um telefone Android com versão 6.0 ou posterior, ou um iPhone ou iPad com versão iOS9 ou posterior 

- A versão mais recente do aplicativo Microsoft Authenticator da loja apropriado da loja de aplicativos

    >[!NOTE]
    >No iOS, a versão do aplicativo deve ser 5.4.0 ou superior.
    >
    >O aplicativo Microsoft Authenticator em telefones que executam um sistema operacional Windows não pode ser usado para fazer logon no Surface Hub.

- Senha ou tela de bloqueio em seu dispositivo está habilitada

- Um endereço de email SMTP padrão (exemplo: joe@contoso.com). Não padrão ou endereços de email SMTP banidos (exemplo: firstname.lastname@contoso.com) atualmente não funcionam.

## Como usar o aplicativo Microsoft Authenticator

>[!NOTE]
>Se o Portal de empresas estiver instalado em seu dispositivo Android, desinstale-a antes de configurar o Microsoft Authenticator. Depois de configurar o aplicativo, você pode reinstalar o Portal de empresas.
>
>Se você já tiver configurado o Microsoft Authenticator no seu telefone e registrado o dispositivo, vá para instruções de entrada.

1. Adicione sua conta corporativa ou escolar ao Microsoft Authenticator para a autenticação multi-fator. Você precisará de um código QR fornecido pelo seu departamento de TI. Para obter ajuda, consulte [Introdução ao aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).
2. Vá para **Configurações** e registre seu dispositivo.
3. Retorne à página das contas e escolha **Habilitar entrada por telefone** no menu suspenso de conta.

## Como fazer logon no Surface Hub durante uma reunião

1. Depois que você configurou uma reunião, vá para o Surface Hub e selecione **Entrar para ver as reuniões e arquivos**.

    >[!NOTE]
    >Se você não tiver certeza de como agendar uma reunião em um Surface Hub, veja [Agendar uma reunião no Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).

    ![captura de tela da opção de entrada no Surface Hub](images/sign-in.png)

2. Você verá uma lista das pessoas convidadas para a reunião. Selecione por conta própria (ou a pessoa que quer fazer logon – certifique-se de que essa pessoa passou pelas etapas para configurar seu dispositivo antes da reunião) e, em seguida, selecione **Continuar**.

    ![captura de tela da lista de participantes em uma reunião](images/attendees.png)

    Você verá um código no Surface Hub.

    ![captura de tela do código para aprovar login](images/approve-signin.png)

3. Para aprovar a entrada, abra o aplicativo autenticador, insira o código de quatro dígitos que é exibido no Surface Hub e selecione **Aprovar**. Em seguida, você deverá inserir o PIN ou usar sua impressão digital para concluir o login. 

    ![captura de tela da tela Aprovar entrada no Microsoft Authenticator](images/approve-signin2.png)

Agora você pode acessar todos os arquivos por meio do aplicativo OneDrive.