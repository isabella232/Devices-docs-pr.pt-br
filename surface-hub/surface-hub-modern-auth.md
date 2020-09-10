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
# Autenticação moderna no Surface Hub

O suporte para autenticação moderna de contas baseadas em nuvem é totalmente integrado à próxima atualização do 2020 do Windows 10 Team, com compilações de visualização disponíveis no [programa Windows Insider](https://insider.windows.com/). Depois de [instalar a versão prévia](surface-hub-install-2020preview.md), você pode migrar da autenticação básica herdada e usar os aprimoramentos de segurança mais recentes do Microsoft Azure e do Exchange Online. Com a atualização 2020, o Surface Hub dá suporte a protocolos do Exchange Web Services (EWS) e à autenticação baseada em ADAL (Active Directory Authentication Library), permitindo que o Exchange Online seja sincronizado com a sincronização da conta do dispositivo.

Para novas contas baseadas em nuvem, o Surface Hub usa automaticamente a autenticação moderna para se conectar ao Exchange Online sem exigir configuração adicional além de simplesmente criar contas de dispositivo usando o formato [alias@contoso.com](mailto:alias@contoso.com). Não use o formato herdado – Contoso\alias, que não tem suporte para autenticação moderna. Para obter mais informações, consulte [criar conta de dispositivo do Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> O Surface Hub não dá suporte à autenticação moderna para contas locais. As contas devem ser criadas na nuvem.

