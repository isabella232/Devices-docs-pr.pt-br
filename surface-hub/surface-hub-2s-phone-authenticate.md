---
title: Configurar a entrada com menos senha no Surface Hub
description: Saiba como simplificar a conexão com o Surface Hub.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893043"
---
# Configurar entrada sem senha no Surface Hub

 
O logon sem senha simplifica o acesso a seus aplicativos, reuniões e arquivos. O Surface Hub permite entrar usando o aplicativo Microsoft Authenticator e as chaves de segurança FIDO2 fornecidas pela sua organização.

**Importante:** Este conteúdo destina-se a usuários. Para usar o recurso de entrada sem senha, seu administrador de ti deve habilitar a autenticação sem senha para a sua organização. Para obter mais informações, consulte:

- [Habilitar entrada de telefone sem senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Habilitar entrada de chave de segurança sem senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## Configurar a entrada usando o aplicativo Microsoft Authenticator

**Observação:** A partir da atualização do Windows 10 Team 2020, os usuários podem usar seus aliases de email preferenciais no Azure AD, bem como seu nome de usuário principal (UPN), para entrar usando o autenticador da Microsoft. Por exemplo, um usuário pode usar o alias preferencial (John.Doe@contoso.com) ou o UPN (jdoe@contoso.com) para entrar.
 
O aplicativo Microsoft Authenticator ajuda você a entrar no Surface Hub usando seu dispositivo móvel. Para configurar a entrada usando o autenticador da Microsoft:


1. Em seu dispositivo móvel, baixe o aplicativo Microsoft Authenticator.
    - Google Android: em seu dispositivo Android, vá para Google Play para [baixar e instalar o aplicativo Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).
    - Apple iOS: em seu dispositivo Apple iOS, vá para a App Store para [baixar e instalar o aplicativo Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).
2. Em seu computador, [Configure o aplicativo Microsoft Authenticator da página de informações de segurança](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) para sua conta corporativa ou de estudante.
3. No aplicativo Microsoft Authenticator em seu dispositivo móvel, [ative e use a entrada de telefone](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) para sua conta corporativa ou de estudante.

 
## Configurar a entrada usando chaves de segurança FIDO2

> [!NOTE]
>  A entrada sem senha no Surface Hub usando chaves de segurança FIDO2 requer a atualização do Windows 10 Team 2020.

> [!IMPORTANT]
> O Surface hub só é compatível com as chaves de segurança USB.
 
Você também pode entrar no Surface Hub usando uma chave de segurança FIDO2 fornecida pela sua organização. 

### Para configurar a entrada usando uma chave de segurança:


1. Em seu computador, acesse a [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) página e entre em sua conta corporativa ou de estudante.
2. Selecione **informações de segurança** no painel de navegação à esquerda ou no link no **bloco informações de segurança** e selecione **Adicionar método** na página informações de **segurança** .
3. Na página **Adicionar um método** , selecione **chave de segurança** na lista suspensa e, em seguida, selecione **Adicionar**.
4. Na página **chave de segurança** , escolha **dispositivo USB**.
5. Prepare a chave de segurança e selecione **Avançar**.
6. Na caixa de diálogo que é exibida, siga as instruções para inserir a chave de segurança, crie ou insira um PIN e execute o gesto obrigatório (biométrica ou touch).
7. Na página **chave de segurança** , forneça um nome para a chave de segurança e selecione **Avançar**.
8. Selecione **concluído** para concluir o processo.

## Entrada no Surface Hub

Depois de configurar a entrada sem senha, você pode usá-la para facilitar o acesso a seus aplicativos, reuniões e arquivos no Surface Hub:

- Ingresse rapidamente em suas reuniões e abra arquivos recentes do Microsoft 365. Para obter mais informações, consulte [**entrar para ver suas reuniões e arquivos**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).
- Conecte-se rapidamente a aplicativos da Microsoft, como o whiteboard, o PowerPoint, o Word, o Excel, o OneDrive e o Power BI.
- Acesse rapidamente o novo Microsoft Edge para acessar seus favoritos e preferências de navegação. Para obter mais informações, consulte [instalar e configurar o novo Microsoft Edge](surface-hub-install-chromium-edge.md).
- Depois de conectar-se ao Surface Hub, você pode usar outros aplicativos sem precisar entrar novamente até selecionar **encerrar sessão**. Selecionar **encerrar sessão** exclui suas credenciais, arquivos e dados pessoais do dispositivo. Para obter mais informações, consulte [encerrar sessão](finishing-your-surface-hub-meeting.md).


## Saiba mais

- [Opções de autenticação com senha para o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [Entrada sem senha com o aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Entrada sem senha usando as chaves de segurança FIDO2](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

