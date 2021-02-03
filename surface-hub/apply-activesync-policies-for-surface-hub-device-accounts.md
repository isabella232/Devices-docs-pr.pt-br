---
title: Aplicando políticas do ActiveSync a contas de dispositivo (Surface Hub)
description: A conta de dispositivo do Microsoft Surface Hub usa o ActiveSync para sincronizar e-mail e calendário. Isso permite que as pessoas participem e iniciem reuniões agendadas do Surface Hub e enviem por e-mail quadros de comunicações feitos durante a reunião.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, políticas do ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: b5f828ee6757c150b1287e8210c81592e970b74a
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11311957"
---
# <span data-ttu-id="1e5f9-105">Aplicando políticas do ActiveSync a contas de dispositivo (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="1e5f9-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="1e5f9-106">A conta de dispositivo do Microsoft Surface Hub usa o ActiveSync para sincronizar e-mail e calendário.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-106">The Microsoft Surface Hub's device account uses ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="1e5f9-107">Isso permite que as pessoas participem e iniciem reuniões agendadas do Surface Hub e enviem por e-mail quadros de comunicações feitos durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="1e5f9-108">Para que esses recursos funcionem, as políticas do ActiveSync para sua organização devem ser configuradas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1e5f9-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="1e5f9-109">Não pode haver políticas globais que bloqueiem a sincronização de caixa de correio do recurso que está sendo usado pela conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="1e5f9-110">Se houver essa política de bloqueio, você precisará adicionar o Surface Hub como um dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="1e5f9-111">Você deve definir uma política de caixa de correio de dispositivo móvel onde a configuração **PasswordEnabled** seja definida como False.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="1e5f9-112">Outras configurações de política de caixa de correio de dispositivo móvel não são compatíveis com o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <span data-ttu-id="1e5f9-113">Permitindo o DeviceID</span><span class="sxs-lookup"><span data-stu-id="1e5f9-113">Allowing the DeviceID</span></span>

<span data-ttu-id="1e5f9-114">Sua organização pode ter uma política global que impede a sincronização de contas de dispositivo provisionadas em Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="1e5f9-115">Para configurar essa propriedade, consulte [Permitindo IDs de dispositivo para o ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span><span class="sxs-lookup"><span data-stu-id="1e5f9-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <span data-ttu-id="1e5f9-116">Configuração PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="1e5f9-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="1e5f9-117">A conta de dispositivo deve ter uma política do ActiveSync onde o atributo **PasswordEnabled** seja definido como False ou 0.</span><span class="sxs-lookup"><span data-stu-id="1e5f9-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="1e5f9-118">Para configurar essa propriedade, consulte [Criando uma política do Microsoft Exchange ActiveSync compatível com o Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="1e5f9-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





