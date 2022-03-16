---
title: Notas do desenvolvedor do Surface Slim Pen 2 háptico
description: Esta página fornece notas de implementação para desenvolvedores de aplicativos que querem estender Windows 11 recursos de tinta do Surface Slim Pen 2 para Empresas.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/07/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
appliesto:
- Windows 11
ms.openlocfilehash: 881ac52cb7a27b82fa9b7e6b5afd86040581ea86
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448534"
---
# <a name="surface-slim-pen-2-haptics-dev-notes"></a>Notas do desenvolvedor do Surface Slim Pen 2 háptico

Esta página fornece notas de implementação para desenvolvedores de aplicativos que querem estender Windows 11 recursos de tinta do [Surface Slim Pen 2 para Empresas](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?). Os recursos de haptics personalizáveis incluem o seguinte:

- **Comentários de escrita à** tinta que simulam a sensação de canetas, lápis e outras ferramentas de escrita ou desenho.
- **Feedback de** interação que responde diretamente a ações do usuário, como passar o mouse sobre um botão, clicar em um botão ou concluir uma tarefa com a caneta.

Se você estiver personalização de um aplicativo para o Surface Slim Pen 2, consulte as diretrizes de Windows Ink descritas em Interações de caneta e comentários [hápticos](/windows/apps/design/input/pen-haptics) e consulte as anotações abaixo.

## <a name="implementation-notes"></a>Notas de implementação

A Caneta Fina do Surface 2 está em conformidade com as diretrizes Windows 11 Ink com as seguintes exceções:

- **Forma de onda de interação.** Conforme documentado na seção [Enviar](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback) e interromper comentários de interação", o envio de uma forma de onda de interação quando uma forma de onda inking está sendo tocada interromperá temporariamente a forma de onda de inking. No entanto, com a implementação atual da Caneta Fina 2, a forma de onda de tinta pode não ser retomada quando a forma de onda de interação for interrompida. Portanto, se ainda for necessário, a forma de onda de inking precisa ser rehabilitada após os comentários de interação. Não é necessário aguardar a conclusão dos comentários de interação.
- **Recursos sem suporte.** Conforme documentado na seção Personalizações de comentários hápticos", os seguintes recursos opcionais não são [suportados](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations) no Surface Slim Pen 2: Contagem de Reprodução e Intervalo de Pausa de Repetição. Embora esses usos apareçam no descritor, eles não têm suporte no momento. Portanto, as seguintes funções retornam um valor incorreto: IsPlayCountSupported, IsPlayDurationSupported, IsReplayPauseIntervalSupported.

## <a name="learn-more"></a>Saiba mais

- [Interações de caneta e Windows Ink em Windows aplicativos](/windows/apps/design/input/pen-and-stylus-interactions)
- [Surface Slim Pen 2 for Business](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)
- [Recursos e compatibilidade da caneta Surface](https://support.microsoft.com/surface/identify-your-surface-pen-and-features-c82a0208-2e35-b347-dae0-d7f4922edc77)

