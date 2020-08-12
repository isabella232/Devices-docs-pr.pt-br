---
title: Novidades no Windows 10, versão 1703 para o Surface Hub
description: Windows 10, versão 1703 (Atualização para criadores) traz novos recursos ao Microsoft Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924937"
---
# <span data-ttu-id="c975b-103">O que há de novo no Windows 10, versão 1703 para o Microsoft Surface Hub?</span><span class="sxs-lookup"><span data-stu-id="c975b-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="c975b-104">Assista ao engenheiro de Surface Hub, Jordan Marchese, apresentar atualizações do Microsoft Surface Hub com Windows 10, versão 1703 (criadores de atualização).</span><span class="sxs-lookup"><span data-stu-id="c975b-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="c975b-105">O Windows 10, versão 1703 (também chamado da Atualização para Criadores), apresenta as seguintes alterações para o Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c975b-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="c975b-106">Novas configurações</span><span class="sxs-lookup"><span data-stu-id="c975b-106">New settings</span></span>

<span data-ttu-id="c975b-107">As configurações foram adicionadas ao gerenciamento de dispositivo móvel (MDM) e aos provedores de serviço de configuração (CSPs) para expandir os recursos de gerenciamento do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c975b-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="c975b-108">[As novas configurações incluem](manage-settings-with-mdm-for-surface-hub.md):</span><span class="sxs-lookup"><span data-stu-id="c975b-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="c975b-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="c975b-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="c975b-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="c975b-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="c975b-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="c975b-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="c975b-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="c975b-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="c975b-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="c975b-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="c975b-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="c975b-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="c975b-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="c975b-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="c975b-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="c975b-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="c975b-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="c975b-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="c975b-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="c975b-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="c975b-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="c975b-119">System/AllowStorageCard</span></span>

<span data-ttu-id="c975b-120">Além das configurações baseadas no novo [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) e [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span><span class="sxs-lookup"><span data-stu-id="c975b-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="c975b-121">Assistente de provisionamento</span><span class="sxs-lookup"><span data-stu-id="c975b-121">Provisioning wizard</span></span>

<span data-ttu-id="c975b-122">Um assistente fácil de usar ajuda você a criar rapidamente os pacotes de provisionamento que podem ser aplicados a vários dispositivos Surface Hub e inclui o ingresso em massa no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c975b-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="c975b-123">Saiba como criar um pacote de provisionamento para o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c975b-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![Etapas no assistente de dispositivos de provisionamento do Surface Hub](images/wcd-wizard.png)
    
## <span data-ttu-id="c975b-125">Miracast em sua rede sem fio existente ou LAN</span><span class="sxs-lookup"><span data-stu-id="c975b-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="c975b-126">A Microsoft estendeu a capacidade de [enviar um fluxo de Miracast por uma rede local](miracast-over-infrastructure.md), e não por um link direto sem fio.</span><span class="sxs-lookup"><span data-stu-id="c975b-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="c975b-127">Recuperação na nuvem</span><span class="sxs-lookup"><span data-stu-id="c975b-127">Cloud recovery</span></span>

<span data-ttu-id="c975b-128">Ao restaurar um dispositivo Surface Hub, agora você pode baixar e instalar uma versão de fábrica do sistema operacional da nuvem.</span><span class="sxs-lookup"><span data-stu-id="c975b-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="c975b-129">Saiba mais sobre a recuperação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="c975b-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="c975b-130">A recuperação na nuvem não funciona com servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="c975b-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![Reinstalar](images/reinstall.png)
    
## <span data-ttu-id="c975b-132">Encerrar sessão</span><span class="sxs-lookup"><span data-stu-id="c975b-132">End session</span></span>

<span data-ttu-id="c975b-133">**Terminei** agora é **Encerrar a sessão**.</span><span class="sxs-lookup"><span data-stu-id="c975b-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="c975b-134">Saiba como usar a opção de Encerrar a sessão.</span><span class="sxs-lookup"><span data-stu-id="c975b-134">Learn how to use End session.</span></span>](finishing-your-surface-hub-meeting.md) 

![encerrar a sessão](images/end-session.png)



 

 
