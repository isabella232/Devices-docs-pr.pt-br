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
# <a name="modern-authentication-on-surface-hub"></a>Autenticação moderna no Surface Hub

A Atualização do Windows 10 Team 2020 adiciona suporte para autenticação moderna da conta de dispositivo Hub em alguns cenários. Depois de instalar a atualização 2020, você poderá migrar da autenticação básica herdada para fazer uso das melhorias de segurança mais recentes se a conta do dispositivo for autenticada por meio do Azure Active Directory e a caixa de correio da conta estiver hospedada no Exchange Online. Com a Atualização 2020, o Surface Hub dá suporte a protocolos do Exchange Web Services (EWS) e autenticação baseada na Biblioteca de Autenticação do Active Directory (ADAL) ao sincronizar a conta de dispositivo com o Exchange Online.

Para novas contas baseadas em nuvem, o Surface Hub usa automaticamente a Autenticação Moderna para se conectar ao Exchange Online sem exigir configurações adicionais além de simplesmente criar contas de dispositivo usando o formato [alias@contoso.com](mailto:alias@contoso.com). Não use o formato herdado – Contoso\alias, que não é suportado para autenticação moderna. Para obter mais informações, consulte [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> O Surface Hub não dá suporte à autenticação moderna para contas locais. As contas devem ser criadas na nuvem.

