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
ms.openlocfilehash: 1674b7abd74a666e2ab1040f66d9ea548ab3c201
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385159"
---
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="05dcf-104">Autenticação moderna no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="05dcf-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="05dcf-105">A Atualização do Windows 10 Team 2020 adiciona suporte para autenticação moderna da conta de dispositivo Hub em alguns cenários.</span><span class="sxs-lookup"><span data-stu-id="05dcf-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="05dcf-106">Depois de instalar a atualização 2020, você poderá migrar da autenticação básica herdada para fazer uso das melhorias de segurança mais recentes se a conta do dispositivo for autenticada por meio do Azure Active Directory e a caixa de correio da conta estiver hospedada no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05dcf-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="05dcf-107">Com a Atualização 2020, o Surface Hub dá suporte a protocolos do Exchange Web Services (EWS) e autenticação baseada na Biblioteca de Autenticação do Active Directory (ADAL) ao sincronizar a conta de dispositivo com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05dcf-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="05dcf-108">Para novas contas baseadas em nuvem, o Surface Hub usa automaticamente a Autenticação Moderna para se conectar ao Exchange Online sem exigir configurações adicionais além de simplesmente criar contas de dispositivo usando o formato [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="05dcf-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="05dcf-109">Não use o formato herdado – Contoso\alias, que não é suportado para autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="05dcf-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="05dcf-110">Para obter mais informações, consulte [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="05dcf-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="05dcf-111">O Surface Hub não dá suporte à autenticação moderna para contas locais.</span><span class="sxs-lookup"><span data-stu-id="05dcf-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="05dcf-112">As contas devem ser criadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="05dcf-112">The accounts must be created in the cloud.</span></span>

