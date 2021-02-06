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
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4db5066c62f4e0e324a5cc3ddad027e00a2e18c9
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314404"
---
# <span data-ttu-id="28dab-105">Aplicando políticas do ActiveSync a contas de dispositivo (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="28dab-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="28dab-106">A conta do dispositivo em todas as versões do Microsoft Surface Hub usa o ActiveSync para sincronizar email e calendário.</span><span class="sxs-lookup"><span data-stu-id="28dab-106">The device account in all versions of Microsoft Surface Hub uses ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="28dab-107">Isso permite que as pessoas participem e iniciem reuniões agendadas do Surface Hub e enviem por e-mail quadros de comunicações feitos durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="28dab-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="28dab-108">Para que esses recursos funcionem, as políticas do ActiveSync para sua organização devem ser configuradas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="28dab-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="28dab-109">Não pode haver políticas globais que bloqueiem a sincronização de caixa de correio do recurso que está sendo usado pela conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="28dab-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="28dab-110">Se houver essa política de bloqueio, você precisará adicionar o Surface Hub como um dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="28dab-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="28dab-111">Você deve definir uma política de caixa de correio de dispositivo móvel onde a configuração **PasswordEnabled** seja definida como False.</span><span class="sxs-lookup"><span data-stu-id="28dab-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="28dab-112">Outras configurações de política de caixa de correio de dispositivo móvel não são compatíveis com o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="28dab-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <span data-ttu-id="28dab-113">Permitindo o DeviceID</span><span class="sxs-lookup"><span data-stu-id="28dab-113">Allowing the DeviceID</span></span>

<span data-ttu-id="28dab-114">Sua organização pode ter uma política global que impede a sincronização de contas de dispositivo provisionadas em Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="28dab-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="28dab-115">Para configurar essa propriedade, consulte [Permitindo IDs de dispositivo para o ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span><span class="sxs-lookup"><span data-stu-id="28dab-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <span data-ttu-id="28dab-116">Configuração PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="28dab-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="28dab-117">A conta de dispositivo deve ter uma política do ActiveSync onde o atributo **PasswordEnabled** seja definido como False ou 0.</span><span class="sxs-lookup"><span data-stu-id="28dab-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="28dab-118">Para configurar essa propriedade, consulte [Criando uma política do Microsoft Exchange ActiveSync compatível com o Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="28dab-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





