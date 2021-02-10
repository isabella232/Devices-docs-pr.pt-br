---
title: Configurar o Perfil de Trabalho Empresarial do Android para o Surface Duo
description: Este artigo explica como configurar o perfil de trabalho no Surface Duo.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326103"
---
# <span data-ttu-id="101a4-103">Configurar o Perfil de Trabalho Empresarial do Android para o Surface Duo</span><span class="sxs-lookup"><span data-stu-id="101a4-103">Configure Android Enterprise Work Profile for Surface Duo</span></span>

<span data-ttu-id="101a4-104">Direcionados a implantações BYOD, os perfis de trabalho fornecem um espaço separado no Duo para dados e aplicativos de trabalho, dando às organizações controle total de seus dados, aplicativos e políticas de segurança sem impedir que os funcionários usem seus dispositivos para aplicativos e dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="101a4-104">Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.</span></span>

### <span data-ttu-id="101a4-105">Configurar o Perfil de Trabalho empresarial do Android</span><span class="sxs-lookup"><span data-stu-id="101a4-105">Set up Android Enterprise Work Profile</span></span>

<span data-ttu-id="101a4-106">Use perfis de trabalho para gerenciar dados corporativos e aplicativos em dispositivos Android de propriedade do usuário.</span><span class="sxs-lookup"><span data-stu-id="101a4-106">Use work profiles to manage corporate data and apps on user-owned Android devices.</span></span> <span data-ttu-id="101a4-107">Por padrão, o registro de dispositivos de perfil de trabalho de propriedade pessoal está habilitado e não requer mais configuração de administrador.</span><span class="sxs-lookup"><span data-stu-id="101a4-107">By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.</span></span>  

**<span data-ttu-id="101a4-108">Para habilitar o Perfil de Trabalho corporativo:</span><span class="sxs-lookup"><span data-stu-id="101a4-108">To enable Enterprise Work Profile:</span></span>**

- <span data-ttu-id="101a4-109">No Endpoint Manager, selecione **dispositivos**  >  **android**  >  **registro** e, em seguida, selecione **dispositivos pessoais com perfil de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="101a4-109">In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.</span></span>
<br><br>
 ![Habilitar Perfil de Trabalho Corporativo](images/enroll-start.png)

 
**<span data-ttu-id="101a4-111">Entrar no Surface Duo com o Perfil de Trabalho Empresarial do Android</span><span class="sxs-lookup"><span data-stu-id="101a4-111">Sign into Surface Duo with Android Enterprise Work Profile</span></span>**

1. <span data-ttu-id="101a4-112">Instale o aplicativo Portal da Empresa na Google Play Store e entre com sua conta de trabalho ou de estudante da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="101a4-112">Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.</span></span><br><br>
![Entrar no Surface Duo](images/duo-wp-1.png)
 
2. <span data-ttu-id="101a4-114">Na página Configuração do Access, selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="101a4-114">On the Access Setup page, select **Begin**.</span></span><br><br>
![Begin](images/duo-wp-2.png)

3. <span data-ttu-id="101a4-116">Revise as informações na página de privacidade e selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="101a4-116">Review the information on the privacy page and select **Continue**.</span></span><br><br>
 ![Continuar](images/duo-wp-3.png)
<br><br>
 ![Selecionar continuar](images/duo-wp-4.png)
 
4. <span data-ttu-id="101a4-119">Quando a configuração do perfil de trabalho for concluída, selecione **Continuar** para ativar e registrar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="101a4-119">When the work profile setup completes, select **Continue** to activate and register the device.</span></span><br><br>
 ![Selecione continuar a ativar e registrar o dispositivo](images/duo-wp-5.png)

5. <span data-ttu-id="101a4-121">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="101a4-121">Select **Continue**.</span></span><br><br>
 ![Selecionar continuar novamente](images/duo-wp-6.png)

6. <span data-ttu-id="101a4-123">Quando você tiver ativado o perfil de trabalho, selecione **Continuar** para atualizar as configurações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="101a4-123">When you have activated the work profile, select **Continue** to update device settings.</span></span> <span data-ttu-id="101a4-124">Neste exemplo, o perfil de trabalho aplica uma configuração MDM para exigir uma senha alfanumérica de seis dígitos mais forte.</span><span class="sxs-lookup"><span data-stu-id="101a4-124">In this example, the work profile applies an MDM setting to require a stronger 6-digit alphanumeric password.</span></span> <br><br>

     ![Exemplo de senha alfanumérica](images/duo-wp-7.png)<br><br>
7. <span data-ttu-id="101a4-126">Selecione **Resolver** para inserir a autenticação necessária e, em seguida, **selecione Continuar** para concluir a configuração do Perfil de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="101a4-126">Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup.</span></span> <br><br>
     ![Selecione continuar para concluir a instalação](images/duo-wp-8.png)<br><br>
     ![configuração completa](images/duo-wp-9.png)<br><br>

## <span data-ttu-id="101a4-129">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="101a4-129">Learn more</span></span>

- [<span data-ttu-id="101a4-130">Configurar o registro de dispositivos de perfil de trabalho android Enterprise</span><span class="sxs-lookup"><span data-stu-id="101a4-130">Set up enrollment of Android Enterprise work profile devices</span></span>](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

