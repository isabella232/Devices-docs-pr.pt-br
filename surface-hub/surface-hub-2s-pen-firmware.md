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
ms.openlocfilehash: 6f1ca4f05653ec798ed1b47d2e42e974e7f7414d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576951"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>Atualizar o firmware da caneta no Surface Hub 2S

Você pode atualizar o firmware Surface Hub caneta 2 do Windows Update for Business ou baixando a atualização de firmware para um computador separado. O firmware atualizado está disponível no Windows Update a partir de 26 de fevereiro de 2020. 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>Atualizar o firmware da caneta usando Windows Atualização para Empresas

Esta seção descreve como atualizar o firmware de caneta por meio dos ciclos de manutenção automatizados do Windows Update, configurados por padrão para ocorrerem à noite às 3 da manhã. Você precisará planejar dois ciclos de manutenção para ser concluído antes de aplicar a atualização à Surface Hub 2. Como qualquer outra atualização, você pode usar o Windows Update for Business (WUfB) para aplicar o firmware de caneta. Para obter mais informações, consulte [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Verifique se Surface Hub caneta 2 está emparelhada Surface Hub 2S: pressione **** e segure o botão superior até que a luz LED do indicador branco comece a piscar. <br>
![Surface Hub caneta 2](images/sh2-pen-1.png) <br>
2. No Surface Hub, faça logon como administrador, **abra**Configurações e, em seguida, procure novos Bluetooth dispositivos.
3. Selecione a caneta para concluir o processo de emparelhamento.
4. Pressione o **botão** superior na caneta para aplicar a atualização. Pode levar até duas horas para ser concluído.

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>Atualizar o firmware da caneta baixando para o computador separado

Você pode atualizar o firmware na Surface Hub 2 de um computador separado que executa Windows 10. Esse método também permite verificar se o firmware da caneta foi atualizado com êxito para a versão mais recente.

1. Emparelhe Surface Hub caneta 2 ao computador com capacidade Bluetooth: pressione **** e segure o botão superior até que a luz LED do indicador branco comece a piscar. <br>
![Surface Hub caneta 2](images/sh2-pen-1.png) <br>
2. No computador, procure novos dispositivos Bluetooth.
3. Selecione a caneta para concluir o processo de emparelhamento.
4. Desconecte todas as Surface Hub 2s antes de iniciar uma nova atualização.
3. Baixe a [Surface Hub de Atualização de Firmware de 2 Canetas](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) no computador.
4. Execute **PenCfu.exe.** O progresso da instalação é exibido na ferramenta. Pode levar vários minutos para concluir a atualização. 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>Verificar a versão de firmware Surface Hub caneta 2

1. Execute **get_version.bat** e pressione o **botão superior** da caneta.
2. A ferramenta relatará a versão de firmware da caneta. Exemplo:
    - O firmware antigo é 468.2727.368
    - O novo firmware é 468.3347.368

## <a name="command-line-options"></a>Opções de linha de comando

Você pode executar Surface Hub Ferramenta de Atualização de Firmware de 2 Canetas (PenCfu.exe) na linha de comando.

1. Emparelhe a caneta no computador e clique no **botão superior** da caneta.
2. Clique duas **PenCfu.exe** para iniciar a atualização de firmware. Observe que o arquivo de configuração e os arquivos de imagem do firmware devem ser armazenados na mesma pasta que a ferramenta.
3. Para opções adicionais, execute **PenCfu.exe -h** para exibir os parâmetros disponíveis, conforme listado na tabela a seguir.  
    - Exemplo: PenCfu.exe -h
4. Insira **Ctrl+C** para desligar com segurança a ferramenta.

 

| **Comando**    | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h ajuda        | Ajuda e saída da interface de linha de comando da ferramenta de exibição.                                                                                                                                                                                                                                                                                                                                             |
| Versão -v     | Exibir versão e sair da ferramenta.                                                                                                                                                                                                                                                                                                                                                                 |
| -l log-filter  | Definir um nível de filtro para o arquivo de log. As mensagens de log têm 4 níveis possíveis: DEPURAÇÃO (mais baixa), INFO, AVISO e ERRO (mais alto). A configuração de um nível de filtro de log filtra as mensagens de log apenas com o mesmo nível ou superior. Por exemplo, se o nível de filtro estiver definido como AVISO, somente as mensagens WARNING e ERROR serão registradas. Por padrão, essa opção é definida como OFF, que desabilita o registro em log. |
| -g get-version | Se especificado, a ferramenta receberá apenas a versão FW da caneta conectada que corresponde ao arquivo de configuração armazenado na mesma pasta que a ferramenta.                                                                                                                                                                                                                                    
