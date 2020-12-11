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
# Autenticação moderna no Surface Hub

O suporte para autenticação moderna de contas baseadas em nuvem é totalmente integrado à [atualização do Windows 10 Team 2020](surface-hub-2020-update.md). Depois de instalar a atualização do 2020, você pode migrar da autenticação básica herdada e usar as melhorias de segurança mais recentes do Microsoft Azure e do Exchange Online. Com a atualização 2020, o Surface Hub dá suporte a protocolos do Exchange Web Services (EWS) e à autenticação baseada em ADAL (Active Directory Authentication Library), permitindo que o Exchange Online seja sincronizado com a sincronização da conta do dispositivo.

Para novas contas baseadas em nuvem, o Surface Hub usa automaticamente a autenticação moderna para se conectar ao Exchange Online sem exigir configuração adicional além de simplesmente criar contas de dispositivo usando o formato [alias@contoso.com](mailto:alias@contoso.com). Não use o formato herdado – Contoso\alias, que não tem suporte para autenticação moderna. Para obter mais informações, consulte [criar conta de dispositivo do Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> O Surface Hub não dá suporte à autenticação moderna para contas locais. As contas devem ser criadas na nuvem.

