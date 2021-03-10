---
title: Faça logon no Surface Hub com Microsoft Authenticator
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
ms.openlocfilehash: f8a2bf8ddb75ca6dd3ff89e16fe0d37e099be29d
ms.sourcegitcommit: 85f5a2e67b34fe073ec588ed441ebee239ab0ac6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400732"
---
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a><span data-ttu-id="23b22-103">Faça logon no Surface Hub com Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="23b22-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="23b22-104">Pessoas em sua organização podem fazer logon em um Surface Hub sem uma senha usando o aplicativo Microsoft Authenticator, disponível em Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="23b22-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <a name="organization-prerequisites"></a><span data-ttu-id="23b22-105">Pré-requisitos de organização</span><span class="sxs-lookup"><span data-stu-id="23b22-105">Organization prerequisites</span></span>

<span data-ttu-id="23b22-106">Para permitir que as pessoas em sua organização efetuem login no Surface Hub com seus telefones e outros dispositivos em vez de uma senha, você precisará garantir que sua organização atende a esses pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="23b22-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="23b22-107">Sua organização deve ser uma organização híbrida ou somente na nuvem, respaldada pelo Active Directory do Azure (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="23b22-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="23b22-108">Para saber mais, consulte [O que é o Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="23b22-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="23b22-109">Certifique-se de que você tem, pelo menos, uma assinatura do Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="23b22-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="23b22-110">[Configurar autenticação multi-fator](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span><span class="sxs-lookup"><span data-stu-id="23b22-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="23b22-111">Certifique-se de **Notificação pelo aplicativo móvel** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="23b22-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![opções de autenticação multi-fator](images/mfa-options.png)

- <span data-ttu-id="23b22-113">Habilitar a hospedagem de conteúdo em serviços do Azure AD, como Office, SharePoint, etc.</span><span class="sxs-lookup"><span data-stu-id="23b22-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="23b22-114">O Surface Hub deve estar executando o Windows 10, versão 1703 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="23b22-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="23b22-115">O Surface Hub é configurado com uma conta local ou domínio.</span><span class="sxs-lookup"><span data-stu-id="23b22-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

## <a name="individual-prerequisites"></a><span data-ttu-id="23b22-116">Pré-requisitos individuais</span><span class="sxs-lookup"><span data-stu-id="23b22-116">Individual prerequisites</span></span>

- <span data-ttu-id="23b22-117">Um telefone Android com versão 6.0 ou posterior, ou um iPhone ou iPad com versão iOS9 ou posterior</span><span class="sxs-lookup"><span data-stu-id="23b22-117">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="23b22-118">A versão mais recente do aplicativo Microsoft Authenticator da loja apropriado da loja de aplicativos</span><span class="sxs-lookup"><span data-stu-id="23b22-118">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="23b22-119">No iOS, a versão do aplicativo deve ser 5.4.0 ou superior.</span><span class="sxs-lookup"><span data-stu-id="23b22-119">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="23b22-120">O aplicativo Microsoft Authenticator em telefones que executam um sistema operacional Windows não pode ser usado para fazer logon no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="23b22-120">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="23b22-121">Senha ou tela de bloqueio em seu dispositivo está habilitada</span><span class="sxs-lookup"><span data-stu-id="23b22-121">Passcode or screen lock on your device is enabled</span></span>

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a><span data-ttu-id="23b22-122">Como usar o aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="23b22-122">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="23b22-123">Se o Portal de empresas estiver instalado em seu dispositivo Android, desinstale-a antes de configurar o Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="23b22-123">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="23b22-124">Depois de configurar o aplicativo, você pode reinstalar o Portal de empresas.</span><span class="sxs-lookup"><span data-stu-id="23b22-124">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="23b22-125">Se você já tiver configurado o Microsoft Authenticator no seu telefone e registrado o dispositivo, vá para instruções de entrada.</span><span class="sxs-lookup"><span data-stu-id="23b22-125">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="23b22-126">Adicione sua conta corporativa ou escolar ao Microsoft Authenticator para a autenticação multi-fator.</span><span class="sxs-lookup"><span data-stu-id="23b22-126">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="23b22-127">Você precisará de um código QR fornecido pelo seu departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="23b22-127">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="23b22-128">Para obter ajuda, consulte [Introdução ao aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span><span class="sxs-lookup"><span data-stu-id="23b22-128">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="23b22-129">Vá para **Configurações** e registre seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23b22-129">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="23b22-130">Retorne à página das contas e escolha **Habilitar entrada por telefone** no menu suspenso de conta.</span><span class="sxs-lookup"><span data-stu-id="23b22-130">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a><span data-ttu-id="23b22-131">Como fazer logon no Surface Hub durante uma reunião</span><span class="sxs-lookup"><span data-stu-id="23b22-131">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="23b22-132">Depois que você configurou uma reunião, vá para o Surface Hub e selecione **Entrar para ver as reuniões e arquivos**.</span><span class="sxs-lookup"><span data-stu-id="23b22-132">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="23b22-133">Se você não tiver certeza de como agendar uma reunião em um Surface Hub, veja [Agendar uma reunião no Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span><span class="sxs-lookup"><span data-stu-id="23b22-133">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![captura de tela da opção de entrada no Surface Hub](images/sign-in.png)

2. <span data-ttu-id="23b22-135">Você verá uma lista das pessoas convidadas para a reunião.</span><span class="sxs-lookup"><span data-stu-id="23b22-135">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="23b22-136">Selecione por conta própria (ou a pessoa que quer fazer logon – certifique-se de que essa pessoa passou pelas etapas para configurar seu dispositivo antes da reunião) e, em seguida, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="23b22-136">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![captura de tela da lista de participantes em uma reunião](images/attendees.png)

    <span data-ttu-id="23b22-138">Você verá um código no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="23b22-138">You'll see a code on the Surface Hub.</span></span>

    ![captura de tela do código para aprovar login](images/approve-signin.png)

3. <span data-ttu-id="23b22-140">Para aprovar a entrada, abra o aplicativo autenticador, insira o código de quatro dígitos que é exibido no Surface Hub e selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="23b22-140">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="23b22-141">Em seguida, você deverá inserir o PIN ou usar sua impressão digital para concluir o login.</span><span class="sxs-lookup"><span data-stu-id="23b22-141">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![captura de tela da tela Aprovar entrada no Microsoft Authenticator](images/approve-signin2.png)

<span data-ttu-id="23b22-143">Agora você pode acessar todos os arquivos por meio do aplicativo OneDrive.</span><span class="sxs-lookup"><span data-stu-id="23b22-143">You can now access all files through the OneDrive app.</span></span>
