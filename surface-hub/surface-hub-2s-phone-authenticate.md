---
title: Configurar a entrada sem senha no Surface Hub
description: Saiba como simplificar a sessão Surface Hub.
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
ms.openlocfilehash: 5449a3a168821c61b7c8969bfe445db91f357a2b
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101168"
---
# <a name="configure-passwordless-sign-in-on-surface-hub"></a>Configurar a entrada sem senha no Surface Hub

 
A entrada sem senha simplifica o acesso aos seus aplicativos, reuniões e arquivos. Surface Hub dá suporte a entrar usando o aplicativo Microsoft Authenticator e as chaves de segurança FIDO2 fornecidas pela sua organização.

**Importante:** Esse conteúdo destina-se aos usuários. Para usar a entrada sem senha, o administrador de IT deve habilitar a autenticação sem senha para sua organização. Para obter mais informações, consulte:

- [Habilitar a login de telefone sem senha](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Habilitar a login da chave de segurança sem senha](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <a name="configure-sign-in-using-microsoft-authenticator-app"></a>Configurar a login usando o Microsoft Authenticator app

**Observação:** A partir do Windows 10 Team Atualização 2020, os usuários podem usar seus aliases de email preferidos no Azure AD, bem como seu Nome de Entidade de Usuário (UPN), para entrar usando o Microsoft Authenticator. Por exemplo, um usuário pode usar seu alias preferencial (John.Doe@contoso.com) ou seu UPN (jdoe@contoso.com) para entrar.
 
O Microsoft Authenticator app ajuda você a entrar Surface Hub usando seu dispositivo móvel. Para configurar a login usando Microsoft Authenticator:


1. Em seu dispositivo móvel, baixe o Microsoft Authenticator app.
    - Google Android: em seu dispositivo Android, vá para o Google Play [para baixar e instalar o Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).
    - Apple iOS: Em seu dispositivo Apple iOS, vá para a App Store para [baixar e instalar o Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).
2. Em seu computador, [configure o aplicativo Microsoft Authenticator na página Informações de](/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) segurança para sua conta de trabalho ou de estudante.
3. No aplicativo Microsoft Authenticator em seu dispositivo móvel, a ligue e [use](/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) a entrada de telefone para sua conta comercial ou de estudante.

 
## <a name="configure-sign-in-using-fido2-security-keys"></a>Configurar a login usando chaves de segurança FIDO2

> [!NOTE]
>  O login sem senha no Surface Hub usando chaves de segurança FIDO2 requer a atualização Windows 10 Team 2020.

> [!IMPORTANT]
> Surface Hub dá suporte apenas a chaves de segurança USB.
 
Você também pode entrar no Surface Hub usando uma chave de segurança FIDO2 fornecida pela sua organização. 

### <a name="to-configure-sign-in-using-a-security-key"></a>Para configurar a login usando uma chave de segurança:


1. Em seu computador, vá para sua [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) página e entre na sua conta de trabalho ou de estudante.
2. Selecione **Informações de** segurança no painel de navegação **** esquerdo ou no link no bloco Informações de segurança e selecione **Adicionar** método na página **Informações de** segurança.
3. Na página **Adicionar um método,** selecione **Chave de segurança** na listada e selecione **Adicionar**.
4. Na página **Chave de** segurança, escolha **dispositivo USB**.
5. Tenha sua chave de segurança pronta e selecione **Próximo**.
6. Na caixa de diálogo exibida, siga as instruções para inserir a chave de segurança, criar ou inserir um PIN e executar o gesto necessário (biometria ou toque).
7. Na página **Chave de** segurança, dê um nome à sua chave de segurança e selecione **Next**.
8. Selecione **Concluído** para concluir o processo.

## <a name="sign-in-to-surface-hub"></a>Entre no Surface Hub

Depois de configurar a entrada sem senha, você pode usá-la para facilitar o acesso a seus aplicativos, reuniões e arquivos no Surface Hub:

- Participe rapidamente de suas reuniões e abra arquivos Microsoft 365 arquivos recentes. Para obter mais informações, [**consulte Entrar para ver suas reuniões e arquivos**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).
- Entre rapidamente em aplicativos da Microsoft como Quadro de PowerPoint, Word, Excel, OneDrive e Power BI.
- Entre rapidamente na nova Microsoft Edge para acessar seus favoritos e preferências de navegação. Para obter mais informações, [consulte Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).
- Depois de entrar no Surface Hub, você pode usar outros aplicativos sem precisar entrar novamente até selecionar **Encerrar sessão**. Selecionar **Sessão final** exclui suas credenciais, arquivos e dados pessoais do dispositivo. Para obter mais informações, consulte [Sessão de término](finishing-your-surface-hub-meeting.md).


## <a name="learn-more"></a>Saiba mais

- [Opções de autenticação sem senha para Azure Active Directory](/azure/active-directory/authentication/concept-authentication-passwordless)
- [Entrar sem senha com o Microsoft Authenticator app](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Entrar sem senha usando chaves de segurança FIDO2](/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

