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
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: dd0b0ad257abbc52c443b075e62db00dcf5713ea
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206275"
---
# <span data-ttu-id="71646-104">Autenticação moderna no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="71646-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="71646-105">O suporte para autenticação moderna de contas baseadas em nuvem é totalmente integrado à [atualização do Windows 10 Team 2020](surface-hub-2020-update.md).</span><span class="sxs-lookup"><span data-stu-id="71646-105">Support for modern authentication of cloud-based accounts is fully integrated in [Windows 10 Team 2020 Update](surface-hub-2020-update.md).</span></span> <span data-ttu-id="71646-106">Depois de instalar a atualização do 2020, você pode migrar da autenticação básica herdada e usar as melhorias de segurança mais recentes do Microsoft Azure e do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="71646-106">Once you install the 2020 update, you can migrate from legacy basic authentication and use the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="71646-107">Com a atualização 2020, o Surface Hub dá suporte a protocolos do Exchange Web Services (EWS) e à autenticação baseada em ADAL (Active Directory Authentication Library), permitindo que o Exchange Online seja sincronizado com a sincronização da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71646-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="71646-108">Para novas contas baseadas em nuvem, o Surface Hub usa automaticamente a autenticação moderna para se conectar ao Exchange Online sem exigir configuração adicional além de simplesmente criar contas de dispositivo usando o formato [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="71646-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="71646-109">Não use o formato herdado – Contoso\alias, que não tem suporte para autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="71646-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="71646-110">Para obter mais informações, consulte [criar conta de dispositivo do Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="71646-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="71646-111">O Surface Hub não dá suporte à autenticação moderna para contas locais.</span><span class="sxs-lookup"><span data-stu-id="71646-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="71646-112">As contas devem ser criadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="71646-112">The accounts must be created in the cloud.</span></span>

