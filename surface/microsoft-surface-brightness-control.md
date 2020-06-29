---
title: Controle de brilho do Surface
description: Este tópico descreve como você pode usar o aplicativo controle de brilho de superfície para gerenciar o brilho de exibição em cenários de ponto de venda e quiosque.
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
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830554"
---
# Controle de brilho do Surface

Ao implantar dispositivos Surface no ponto de venda ou em cenários de quiosque "sempre ativas", você pode otimizar o gerenciamento de energia usando o novo aplicativo controle de brilho de superfície.

Disponível para download com [ferramentas Surface para ele](https://www.microsoft.com/download/details.aspx?id=46703).
O controle de brilho Surface foi projetado para ajudar a reduzir a carga térmica e reduzir a superfície de carbono geral para dispositivos de superfície implantados.
Se você planeja obter apenas essa ferramenta a partir da página de download, selecione o arquivo **Surface_Brightness_Control_v1.16.137.0.msi** na lista disponível.
A ferramenta escurece a tela automaticamente quando não está em uso e inclui as seguintes opções de configuração:

- Período de inatividade antes de desactivar a tela.

- Nível de brilho quando esmaecido.

- Nível de brilho máximo quando em uso.

**Para executar o controle do Surface Bright:**

- Instale surfacebrightnesscontrol.msi no dispositivo de destino e o controle de brilho da superfície começará a funcionar imediatamente.

## Configurando o controle do Surface Bright

Você pode ajustar os valores padrão por meio do registro do Windows. Para obter mais informações sobre como usar o registro do Windows, consulte a [documentação do registro](https://docs.microsoft.com/windows/desktop/sysinfo/registry).

1.  Execute o regedit a partir de um prompt de comando para abrir o editor do registro do Windows.
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface o controle de brilho \ 
    
    Se você estiver executando uma versão mais antiga do controle de brilho do Surface, execute o seguinte comando em vez disso:
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface o controle de brilho \


| Configuração do registro | Dados| Descrição  
|-----------|------------|---------------
| Controle de brilho habilitado  |  Padrão: 01  <br> Opção: 01, 00 <br> Tipo: REG_BINARY |  Essa configuração permite ativar ou desativar o controle de brilho de superfície. Para desabilitar o controle de brilho da superfície, defina o valor como 00. Se você não definir essa configuração, o controle de brilho da superfície estará ativado. |
| Controle de brilho ativado para energia| Padrão: 01 <br> Opções: 01, 00 <br> Tipo: REG_BINARY | Essa configuração permite que você desative o controle de brilho da superfície quando o dispositivo estiver diretamente conectado à alimentação. Para desabilitar o controle de brilho da superfície quando a energia estiver conectada, defina o valor como 00. Se você não definir essa configuração, o controle de brilho da superfície estará ativado. |
| Brilho esmaecido   | Padrão: 20  <br>Opção: intervalo de 0-100% do brilho da tela <br> Tipo de dados: inteiro positivo <br> Tipo: REG_DWORD | Essa configuração permite gerenciar o intervalo de brilho durante os períodos de inatividade. Se você não definir essa configuração, o nível de brilho será solto em 20% do brilho completo após 30 segundos de inatividade. |
Brilho completo   | Padrão: 100  <br>Opção: intervalo de 0-100% do brilho da tela <br> Tipo de dados: inteiro positivo <br> Tipo: REG_DWORD  | Essa configuração permite que você gerencie o intervalo máximo de brilho do dispositivo. Se você não definir essa configuração, o intervalo de brilho máximo será de 100%.|  
| Tempo limite de inatividade| Padrão: 30 segundos <br>Opção: qualquer valor numérico  <br>Tipo de dados: inteiro  <br> Tipo: REG_DWORD | Essa configuração permite que você gerencie o período de inatividade antes de desactivar o dispositivo. Se você não definir essa configuração, o tempo limite de inatividade será de 30 segundos.|
| Telemetria habilitada | Padrão: 01 <br>Opção: 01, 00 <br> Tipo: REG_BINARY  | Essa configuração permite que você gerencie o compartilhamento de informações de uso do aplicativo para melhorar o software e oferecer uma melhor experiência do usuário. Para desabilitar a telemetria, defina o valor como 00. Se você não definir essa configuração, as informações de telemetria serão compartilhadas com a Microsoft de acordo com a [política de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement). |

## Alterações e atualizações

### Versão 1.16.137<br>
*Data do lançamento: 22 de outubro de 2019*<br>
Esta versão do controle de brilho de superfície adiciona suporte para o seguinte:-recompilado para x86, adicionando suporte para Surface Pro 7, Surface Pro X e Surface laptop 3. 

### Versão 1.12.239.0
*Data do lançamento: 26 de abril de 2019*<br>
Esta versão do controle de brilho de superfície adiciona suporte para o seguinte:
- Correções de atraso de toque.


## Tópicos relacionados

- [Configuração de limite de bateria](battery-limit.md)
