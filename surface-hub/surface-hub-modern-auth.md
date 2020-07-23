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
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893123"
---
# <span data-ttu-id="67773-104">Autenticação moderna no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="67773-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="67773-105">O suporte para autenticação moderna de contas baseadas na nuvem é totalmente integrado à atualização do Windows 10 Team 2020, permitindo que você migre da autenticação básica herdada e use as melhorias de segurança mais recentes do Microsoft Azure e do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="67773-105">Support for modern authentication of cloud-based accounts is fully integrated in Windows 10 Team 2020 Update, allowing you to migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="67773-106">Com a atualização 2020, o Surface Hub dá suporte a protocolos do Exchange Web Services (EWS) e à autenticação baseada em ADAL (Active Directory Authentication Library), permitindo que o Exchange Online seja sincronizado com a sincronização da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67773-106">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="67773-107">Para novas contas baseadas em nuvem, o Surface Hub usa automaticamente a autenticação moderna para se conectar ao Exchange Online sem exigir configuração adicional além de simplesmente criar contas de dispositivo usando o formato [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="67773-107">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="67773-108">Não use o formato herdado – Contoso\alias, que não tem suporte para autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="67773-108">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="67773-109">Para obter mais informações, consulte [criar conta de dispositivo do Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="67773-109">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="67773-110">O Surface Hub não dá suporte à autenticação moderna para contas locais.</span><span class="sxs-lookup"><span data-stu-id="67773-110">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="67773-111">As contas devem ser criadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="67773-111">The accounts must be created in the cloud.</span></span>

