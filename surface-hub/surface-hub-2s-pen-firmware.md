---
title: Atualizar o firmware da caneta no Surface Hub 2S
description: Esta página descreve como atualizar o firmware para a Surface Hub 2.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: b1955f1806c963ce553d5d2eef99e72e90c5adfe
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497714"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>Atualizar o firmware da caneta no Surface Hub 2S

Você pode atualizar o firmware Surface Hub caneta 2 do Windows Update for Business ou baixando a atualização de firmware para um computador separado. O firmware atualizado está disponível desde Windows Update a partir de 26 de fevereiro de 2020. 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>Atualizar o firmware da caneta usando o Windows Update for Business

Esta seção descreve como atualizar o firmware da caneta por meio dos ciclos de manutenção automatizados para Windows Update, configurados por padrão para ocorrerem à noite às 3h. Você precisará planejar a conclusão de dois ciclos de manutenção antes de aplicar a atualização à Surface Hub 2. Como alternativa, como qualquer outra atualização, você pode usar o Windows Update for Business (WUfB) para aplicar o firmware da caneta. Para obter mais informações, [consulte Gerenciando Windows atualizações no Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Verifique se Surface Hub caneta 2 está emparelhada com Surface Hub 2S: pressione e segure o botão superior até que a luz LED do **** indicador branco comece a piscar.

    > [!div class="mx-imgBorder"]
    > ![Surface Hub caneta 2.](images/sh2-pen-1.png)

2. No Surface Hub, faça logon como administrador **, abra Configurações** e, em seguida, verifique se há novos Bluetooth dispositivos.

3. Selecione a caneta para concluir o processo de emparelhamento.

4. Pressione o **botão** superior na caneta para aplicar a atualização. Pode levar até duas horas para ser concluído.

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>Atualizar o firmware da caneta baixando para um computador separado

Você pode atualizar o firmware na Surface Hub 2 de um computador separado executando Windows 10 ou Windows 11. Esse método também permite que você verifique se o firmware da caneta foi atualizado com êxito para a versão mais recente.

1. Emparelhe Surface Hub caneta 2 ao computador com Bluetooth: pressione e segure o botão superior até que a luz led indicadora **** branca comece a piscar.

    > [!div class="mx-imgBorder"]
    > ![Surface Hub caneta 2.](images/sh2-pen-1.png)

2. No computador, verifique se há novos Bluetooth dispositivos.

3. Selecione a caneta para concluir o processo de emparelhamento.

4. Desconecte todas as outras Surface Hub canetas 2s antes de iniciar uma nova atualização.

5. Baixe a [Surface Hub atualização de firmware de 2](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) canetas no computador.

6. Execute **PenCfu.exe.** O progresso da instalação é exibido na ferramenta. Pode levar vários minutos para concluir a atualização. 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>Verificar a versão do firmware Surface Hub caneta 2

1. Execute **get_version.bat** e pressione o **botão** superior na caneta.

2. A ferramenta relatará a versão do firmware da caneta. 

   Exemplo:
    - O firmware antigo é 468.2727.368
    - O novo firmware é 468.3347.368

## <a name="command-line-options"></a>Opções de linha de comando

Você pode executar Surface Hub 2 Ferramentas de Atualização de Firmware de Caneta (PenCfu.exe) na linha de comando.

1. Emparelhe a caneta no computador e clique **no botão** superior da caneta.

2. Clique duas **PenCfu.exe** para iniciar a atualização de firmware. Observe que o arquivo de configuração e os arquivos de imagem de firmware devem ser armazenados na mesma pasta que a ferramenta.

3. Para obter opções adicionais, **PenCfu.exe -h** para exibir os parâmetros disponíveis, conforme listado na tabela a seguir.  

   Exemplo: `PenCfu.exe -h`

4. Insira **Ctrl+C** para desligar a ferramenta com segurança.


| Comando | Descrição |
| -------------- |---------------------------- |
| -h ajuda        | Exibir ajuda e saída da interface de linha de comando da ferramenta. |
| -v version     | Exibir versão e sair da ferramenta. |
| -l log-filter  | Defina um nível de filtro para o arquivo de log. As mensagens de log têm quatro níveis possíveis: DEBUG (mais baixo), INFO, WARNING e ERROR (mais alto). Definir um nível de filtro de log filtra as mensagens de log apenas com o mesmo nível ou superior. Por exemplo, se o nível de filtro estiver definido como AVISO, somente as mensagens WARNING e ERROR serão registradas. Por padrão, essa opção é definida como OFF, o que desabilita o registro em log. |
| -g get-version | Se especificado, a ferramenta obterá apenas a versão FW da caneta conectada que corresponde ao arquivo de configuração armazenado na mesma pasta que a ferramenta.  |

