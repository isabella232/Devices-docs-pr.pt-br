---
title: Autenticação moderna no Surface Hub
description: Esta página descreve o uso da autenticação moderna no Surface Hub em contraste com a autenticação básica herdada.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004463"
---
# <span data-ttu-id="43885-104">Autenticação moderna no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="43885-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="43885-105">O suporte para autenticação moderna de contas baseadas em nuvem é totalmente integrado à próxima atualização do 2020 do Windows 10 Team, com compilações de visualização disponíveis no [programa Windows Insider](https://insider.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="43885-105">Support for modern authentication of cloud-based accounts is fully integrated in the upcoming Windows 10 Team 2020 Update, with preview builds available from the [Windows Insider Program](https://insider.windows.com/).</span></span> <span data-ttu-id="43885-106">Depois de [instalar a versão prévia](surface-hub-install-2020preview.md), você pode migrar da autenticação básica herdada e usar os aprimoramentos de segurança mais recentes do Microsoft Azure e do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="43885-106">Once you [install the preview build](surface-hub-install-2020preview.md), you can migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="43885-107">Com a atualização 2020, o Surface Hub dá suporte a protocolos do Exchange Web Services (EWS) e à autenticação baseada em ADAL (Active Directory Authentication Library), permitindo que o Exchange Online seja sincronizado com a sincronização da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43885-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="43885-108">Para novas contas baseadas em nuvem, o Surface Hub usa automaticamente a autenticação moderna para se conectar ao Exchange Online sem exigir configuração adicional além de simplesmente criar contas de dispositivo usando o formato [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="43885-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="43885-109">Não use o formato herdado – Contoso\alias, que não tem suporte para autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="43885-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="43885-110">Para obter mais informações, consulte [criar conta de dispositivo do Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="43885-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="43885-111">O Surface Hub não dá suporte à autenticação moderna para contas locais.</span><span class="sxs-lookup"><span data-stu-id="43885-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="43885-112">As contas devem ser criadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="43885-112">The accounts must be created in the cloud.</span></span>

