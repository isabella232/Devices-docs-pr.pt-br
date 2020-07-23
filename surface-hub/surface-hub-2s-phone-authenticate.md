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
# <span data-ttu-id="919b4-104">Configurar entrada sem senha no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="919b4-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="919b4-105">O logon sem senha simplifica o acesso a seus aplicativos, reuniões e arquivos.</span><span class="sxs-lookup"><span data-stu-id="919b4-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="919b4-106">O Surface Hub permite entrar usando o aplicativo Microsoft Authenticator e as chaves de segurança FIDO2 fornecidas pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="919b4-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="919b4-107">**Importante:** Este conteúdo destina-se a usuários.</span><span class="sxs-lookup"><span data-stu-id="919b4-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="919b4-108">Para usar o recurso de entrada sem senha, seu administrador de ti deve habilitar a autenticação sem senha para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="919b4-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="919b4-109">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="919b4-109">For more information, see:</span></span>

- [<span data-ttu-id="919b4-110">Habilitar entrada de telefone sem senha</span><span class="sxs-lookup"><span data-stu-id="919b4-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="919b4-111">Habilitar entrada de chave de segurança sem senha</span><span class="sxs-lookup"><span data-stu-id="919b4-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="919b4-112">Configurar a entrada usando o aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="919b4-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="919b4-113">**Observação:** A partir da atualização do Windows 10 Team 2020, os usuários podem usar seus aliases de email preferenciais no Azure AD, bem como seu nome de usuário principal (UPN), para entrar usando o autenticador da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="919b4-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="919b4-114">Por exemplo, um usuário pode usar o alias preferencial (John.Doe@contoso.com) ou o UPN (jdoe@contoso.com) para entrar.</span><span class="sxs-lookup"><span data-stu-id="919b4-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="919b4-115">O aplicativo Microsoft Authenticator ajuda você a entrar no Surface Hub usando seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="919b4-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="919b4-116">Para configurar a entrada usando o autenticador da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="919b4-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="919b4-117">Em seu dispositivo móvel, baixe o aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="919b4-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="919b4-118">Google Android: em seu dispositivo Android, vá para Google Play para [baixar e instalar o aplicativo Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span><span class="sxs-lookup"><span data-stu-id="919b4-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="919b4-119">Apple iOS: em seu dispositivo Apple iOS, vá para a App Store para [baixar e instalar o aplicativo Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span><span class="sxs-lookup"><span data-stu-id="919b4-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="919b4-120">Em seu computador, [Configure o aplicativo Microsoft Authenticator da página de informações de segurança](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) para sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="919b4-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="919b4-121">No aplicativo Microsoft Authenticator em seu dispositivo móvel, [ative e use a entrada de telefone](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) para sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="919b4-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="919b4-122">Configurar a entrada usando chaves de segurança FIDO2</span><span class="sxs-lookup"><span data-stu-id="919b4-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="919b4-123">A entrada sem senha no Surface Hub usando chaves de segurança FIDO2 requer a atualização do Windows 10 Team 2020.</span><span class="sxs-lookup"><span data-stu-id="919b4-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="919b4-124">O Surface hub só é compatível com as chaves de segurança USB.</span><span class="sxs-lookup"><span data-stu-id="919b4-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="919b4-125">Você também pode entrar no Surface Hub usando uma chave de segurança FIDO2 fornecida pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="919b4-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="919b4-126">Para configurar a entrada usando uma chave de segurança:</span><span class="sxs-lookup"><span data-stu-id="919b4-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="919b4-127">Em seu computador, acesse a [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) página e entre em sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="919b4-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="919b4-128">Selecione **informações de segurança** no painel de navegação à esquerda ou no link no **bloco informações de segurança** e selecione **Adicionar método** na página informações de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="919b4-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="919b4-129">Na página **Adicionar um método** , selecione **chave de segurança** na lista suspensa e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="919b4-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="919b4-130">Na página **chave de segurança** , escolha **dispositivo USB**.</span><span class="sxs-lookup"><span data-stu-id="919b4-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="919b4-131">Prepare a chave de segurança e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="919b4-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="919b4-132">Na caixa de diálogo que é exibida, siga as instruções para inserir a chave de segurança, crie ou insira um PIN e execute o gesto obrigatório (biométrica ou touch).</span><span class="sxs-lookup"><span data-stu-id="919b4-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="919b4-133">Na página **chave de segurança** , forneça um nome para a chave de segurança e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="919b4-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="919b4-134">Selecione **concluído** para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="919b4-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="919b4-135">Entrada no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="919b4-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="919b4-136">Depois de configurar a entrada sem senha, você pode usá-la para facilitar o acesso a seus aplicativos, reuniões e arquivos no Surface Hub:</span><span class="sxs-lookup"><span data-stu-id="919b4-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="919b4-137">Ingresse rapidamente em suas reuniões e abra arquivos recentes do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="919b4-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="919b4-138">Para obter mais informações, consulte [**entrar para ver suas reuniões e arquivos**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span><span class="sxs-lookup"><span data-stu-id="919b4-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="919b4-139">Conecte-se rapidamente a aplicativos da Microsoft, como o whiteboard, o PowerPoint, o Word, o Excel, o OneDrive e o Power BI.</span><span class="sxs-lookup"><span data-stu-id="919b4-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="919b4-140">Acesse rapidamente o novo Microsoft Edge para acessar seus favoritos e preferências de navegação.</span><span class="sxs-lookup"><span data-stu-id="919b4-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="919b4-141">Para obter mais informações, consulte [instalar e configurar o novo Microsoft Edge](surface-hub-install-chromium-edge.md).</span><span class="sxs-lookup"><span data-stu-id="919b4-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="919b4-142">Depois de conectar-se ao Surface Hub, você pode usar outros aplicativos sem precisar entrar novamente até selecionar **encerrar sessão**.</span><span class="sxs-lookup"><span data-stu-id="919b4-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="919b4-143">Selecionar **encerrar sessão** exclui suas credenciais, arquivos e dados pessoais do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="919b4-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="919b4-144">Para obter mais informações, consulte [encerrar sessão](finishing-your-surface-hub-meeting.md).</span><span class="sxs-lookup"><span data-stu-id="919b4-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="919b4-145">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="919b4-145">Learn more</span></span>

- [<span data-ttu-id="919b4-146">Opções de autenticação com senha para o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="919b4-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="919b4-147">Entrada sem senha com o aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="919b4-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="919b4-148">Entrada sem senha usando as chaves de segurança FIDO2</span><span class="sxs-lookup"><span data-stu-id="919b4-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

