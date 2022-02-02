---
title: Controle de brilho do Surface
description: Este tópico descreve como você pode usar o aplicativo Surface Brightness Control para gerenciar o brilho de exibição em cenários de ponto de venda e quiosque.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 660a96a8825002c6d52d067dac77894bb0c0b7a9
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337824"
---
# <a name="surface-brightness-control"></a>Controle de brilho do Surface

Ao implantar dispositivos Surface no ponto de venda ou em outros cenários de quiosque "always-on", você pode otimizar o gerenciamento de energia usando o aplicativo Surface Brightness Control. O Controle de Brilho de Superfície foi projetado para ajudar a reduzir a carga térmica e reduzir a emissão geral de carbono para dispositivos Surface implantados. A ferramenta apaga automaticamente a tela quando não está em uso e inclui as seguintes opções de configuração:

- Período de inatividade antes de escurecer a exibição.
- Nível de brilho quando esmaecida.
- Nível máximo de brilho quando em uso.

Baixe o Controle de Brilho de Superfície do [Surface Tools para IT](https://www.microsoft.com/download/details.aspx?id=46703). Selecione o arquivo **Surface_Brightness_Control_v1.16.137.0.msi** na lista disponível.

## <a name="supported-devices"></a>Dispositivos com suporte

- Surface Pro 3 e posterior
- Surface Pro X (todas as gerações)
- Surface 3
- Surface Book (todas as gerações)
- Surface Laptop Studio
- Surface Studio (todas as gerações)
- Surface Laptop (todas as gerações)
- Surface Laptop Go
- Surface Go (todas as gerações)


## <a name="run-surface-brightness-control"></a>Executar o Controle de Brilho de Superfície

- Instale **Surface_Brightness_Control_v1.16.137.0.msi** no dispositivo de destino e o Controle de Brilho de Superfície começará a funcionar imediatamente.

## <a name="configure-surface-brightness-control"></a>Configurar o Controle de Brilho de Superfície

Você pode ajustar os valores padrão por meio do Windows Registro. Para obter mais informações sobre como usar o Windows Registro, consulte a [documentação do Registro](/windows/desktop/sysinfo/registry).

1. Execute **o regedit** de um prompt de comando para abrir o editor Windows Registro.
2. Navegue até Computador\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control.
3. Ajuste os valores principais do Registro, conforme descrito na tabela a seguir.

> [!TIP]
> Se você estiver executando uma versão mais antiga do controle Surface Brightness, navegue até: Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\SurfaceBrightnessControl\

| Configuração do Registro | Dados| Descrição  
|-----------|------------|---------------
| BrightnessControlEnabled  |  Padrão: 01  <br> Opção: 01,00 <br> Tipo: REG_BINARY |  Essa configuração permite ativar ou desativar o Controle de Brilho de Superfície. Para desabilitar o Controle de Brilho de Superfície, de definir o valor como 00. Se você não definir essa configuração, o Surface Brightness Control será a opção. |
| BrightnessControlOnPowerEnabled| Padrão: 01 <br> Opções: 01,00 <br> Tipo: REG_BINARY | Essa configuração permite desativar o Controle de Brilho de Superfície quando o dispositivo está diretamente conectado à energia. Para desabilitar o Surface Brightness Control quando a energia estiver conectada, de definir o valor como 00. Se você não definir essa configuração, o Surface Brightness Control será a opção. |
| DimmedBrightness   | Padrão: 20  <br>Opção: Intervalo de 0 a 100% do brilho da tela <br> Tipo de dados: inteiro positivo <br> Tipo: REG_DWORD | Essa configuração permite gerenciar o intervalo de brilho durante períodos de inatividade. Se você não configurar essa configuração, o nível de brilho baixará para 20% do brilho total após 30 segundos de inatividade. |
FullBrightness   | Padrão: 100  <br>Opção: Intervalo de 0 a 100% do brilho da tela <br> Tipo de dados: inteiro positivo <br> Tipo: REG_DWORD  | Essa configuração permite gerenciar o intervalo máximo de brilho para o dispositivo. Se você não configurar essa configuração, o intervalo máximo de brilho será 100%.|  
| InactivityTimeout| Padrão: 30 segundos <br>Opção: Qualquer valor numérico  <br>Tipo de dados: Integer  <br> Tipo: REG_DWORD | Essa configuração permite gerenciar o período de inatividade antes de escurecer o dispositivo. Se você não configurar essa configuração, o tempo de inatividade será de 30 segundos.|
| TelemetryEnabled | Padrão: 01 <br>Opção: 01,00 <br> Tipo: REG_BINARY  | Essa configuração permite gerenciar o compartilhamento de informações de uso do aplicativo para melhorar o software e proporcionar uma melhor experiência do usuário. Para desabilitar a telemetria, de definir o valor como 00. Se você não definir essa configuração, as informações de telemetria são compartilhadas com a Microsoft de acordo com a [Declaração de Privacidade da Microsoft](https://privacy.microsoft.com/privacystatement). |

## <a name="changes-and-updates"></a>Alterações e atualizações

### <a name="version-116137br"></a>Versão 1.16.137<br>

*Data de lançamento: 22 de outubro de 2019*<br>
Esta versão do Surface Brightness Control adiciona suporte para o seguinte: -Recompilado para x86, adicionando suporte para o Surface Pro 7, Surface Pro X e Surface Laptop 3.

### <a name="version-1122390"></a>Versão 1.12.239.0

*Data de lançamento: 26 de abril de 2019*<br>
Esta versão do Surface Brightness Control adiciona suporte para o seguinte:

- Correções de atraso por toque.

## <a name="related-topics"></a>Tópicos relacionados

- [Configuração de limite de bateria](battery-limit.md)
