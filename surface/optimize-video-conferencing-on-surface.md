---
title: Otimize a videoconferência em dispositivos Surface
description: Esta página fornece práticas recomendadas para o uso de Microsoft Teams e outras soluções de videoconferência em dispositivos Surface
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/10/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 28ad64b41dedb7d66092cf98388920a732fee737
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449674"
---
# <a name="optimize-video-conferencing-on-surface-devices"></a>Otimize a videoconferência em dispositivos Surface

Os dispositivos Surface aproveitam os avanços mais recentes no consumo de energia de dispositivo móvel para oferecer uma experiência simplificada otimizada em cargas de trabalho. Para a maioria das cargas de trabalho, isso oferece uma ótima experiência. Para algumas cargas de trabalho usando Microsoft Teams ou outros aplicativos de videoconferência, siga estas recomendações para garantir a melhor experiência.

## <a name="surface-drivers-and-firmware"></a>Drivers e firmware do Surface

A Microsoft lança regularmente atualizações para dispositivos Surface e lançou várias atualizações do Surface que visam cargas de trabalho de videoconferência, incluindo:

- Melhorias de desempenho do sistema
- Melhorias de consumo de energia em drivers de câmera
- Atualizações de driver de elementos gráficos
- Otimizações de configurações de energia

### <a name="get-updates-to-all-devices"></a>Obter atualizações para todos os dispositivos

Verifique se sua organização tem um processo para que seus dispositivos recebam essas atualizações. Se você estiver usando o Windows Update ou [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb), você já está recebendo as atualizações mais recentes do Surface quando elas são lançadas. Verifique se há atualizações usando o Windows Update e verifique se as atualizações mais novas do Surface foram instaladas. Para saber mais, confira:

- [Histórico de atualizações do Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)
- [Instalar atualizações Windows Surface](https://www.microsoft.com/surface/support/performance-and-maintenance/install-software-updates-for-surface?)

Se você estiver usando outras opções para instalar drivers do Surface e atualizações de firmware, precisará instalar as atualizações mais recentes do Surface manualmente usando os arquivos MSI publicados ou instalar as atualizações usando o Configuration Manager. Para saber mais, confira:

- [Baixar drivers e firmware para Surface](https://support.microsoft.com/help/4023482)
- [Gerenciar e implantar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md)
- [Como gerenciar atualizações de driver do Surface no Configuration Manager](https://support.microsoft.com/help/4098906)

### <a name="graphics-driver-updates-for-microsoft-teams"></a>Atualizações de driver de elementos gráficos para Microsoft Teams

Modelos de dispositivo Surface mais recentes com processadores Intel de 10ª e 11ª geração receberam atualizações de driver de elementos gráficos que ajudam com cargas de trabalho de videoconferência. Para habilitar essas melhorias, instale o seguinte:

- Microsoft Teams versão **1.4.00.22472** ou posterior.
- Driver gráfico Intel **27.20.100.9621** ou posterior.

### <a name="power-settings-optimizations"></a>Otimizações de configurações de energia

Os dispositivos Surface podem ajustar as configurações de energia relacionadas ao desempenho alterando Windows posição do controle deslizante de energia de desempenho no Windows 10, também conhecido como modo de energia no Windows 11.

Alguns dispositivos Surface receberam atualizações que incluem otimizações de configuração de energia para cargas de trabalho de conferência de vídeo com base na posição do controle deslizante de energia ou no modo de alimentação. No entanto, como Windows 10 e Windows 11 usam a posição recomendada do controle deslizante **** de energia e a posição do modo de energia para cargas de trabalho de videoconferência, você precisará ajustar o controle deslizante de energia para habilitar essas otimizações:

1. Conexão a energia ac (as otimizações não são executados ao usar a energia da bateria).  
2. Ajuste o controle deslizante de energia ou a posição do modo de alimentação para usar **Melhor Desempenho** ou **Melhor Desempenho.**

## <a name="learn-more"></a>Saiba mais

- [Práticas recomendadas de configurações de energia para dispositivos Surface](maintain-optimal-power-settings-on-surface-devices.md)
- [Maximizar a duração da bateria do Surface](https://support.microsoft.com/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)
