---
title: Atualize o firmware da caneta no Surface Hub 2S
description: Esta página descreve como atualizar o firmware para a caneta Surface Hub 2.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830448"
---
# Atualize o firmware da caneta no Surface Hub 2S

Você pode atualizar o firmware na caneta Surface Hub 2 do Windows Update para empresas ou baixando a atualização de firmware para um computador separado. O firmware atualizado está disponível no Windows Update a partir de 26 de fevereiro de 2020. 

## Atualizar o firmware da caneta usando o Windows Update para empresas

Esta seção descreve como atualizar o firmware da caneta por meio dos ciclos de manutenção automatizados do Windows Update, configurados por padrão para ocorrer à noite às 3h. Você precisará planejar dois ciclos de manutenção para concluir antes de aplicar a atualização à caneta Surface Hub 2. Como alternativa, como qualquer outra atualização, você pode usar o Windows Server Update Services (WSUS) para aplicar o firmware da caneta. Para obter mais informações, consulte [gerenciando atualizações do Windows em Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Verifique se a caneta Surface Hub 2 está emparelhada com o Surface Hub 2S: Pressione e mantenha pressionado o botão **superior** até que a luz do LED do indicador branco comece a piscar. <br>
![Caneta Surface Hub 2](images/sh2-pen-1.png) <br>
2. Em Surface Hub, faça logon como administrador, abra **configurações**e, em seguida, procure novos dispositivos Bluetooth.
3. Selecione a caneta para completar o processo de emparelhamento.
4. Pressione o botão **superior** na caneta para aplicar a atualização. Pode levar até duas horas para concluir.

## Atualize o firmware da caneta baixando para um computador separado

Você pode atualizar o firmware na caneta Surface Hub 2 a partir de um computador separado executando o Windows 10. Esse método também permite que você verifique se o firmware da caneta foi atualizado com êxito para a versão mais recente.

1. Emparelhar a caneta Surface Hub 2 ao seu PC compatível com Bluetooth: Pressione e mantenha pressionado o botão **superior** até que a luz do LED do indicador branco comece a piscar. <br>
![Caneta Surface Hub 2](images/sh2-pen-1.png) <br>
2. No computador, verifique se há novos dispositivos Bluetooth.
3. Selecione a caneta para completar o processo de emparelhamento.
4. Desconecte todas as outras canetas do Surface Hub 2s antes de iniciar uma nova atualização.
3. Baixe a [ferramenta de atualização do firmware do Surface Hub 2](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) em seu computador.
4. Executar **PenCfu.exe.** O progresso da instalação é exibido na ferramenta. Pode levar alguns minutos para concluir a atualização. 


## Verificar a versão do firmware da caneta Surface Hub 2

1. Execute **get_version.bat** e pressione o botão **superior** na caneta.
2. A ferramenta irá relatar a versão do firmware da caneta. Exemplo:
    - O firmware antigo é 468.2727.368
    - O novo firmware é 468.2863.369

## Opções de linha de comando

Você pode executar a ferramenta de atualização do firmware da Surface Hub 2 (PenCfu.exe) a partir da linha de comando.

1. Emparelhe a caneta em seu computador e clique no botão **superior** na caneta.
2. Clique duas vezes **PenCfu.exe** para iniciar a atualização do firmware. Observe que o arquivo de configuração e os arquivos de imagem do firmware devem ser armazenados na mesma pasta da ferramenta.
3. Para opções adicionais, execute **PenCfu.exe-h** para exibir os parâmetros disponíveis, conforme listados na tabela a seguir.  
    - Exemplo: PenCfu.exe-h
4. Digite **Ctrl + C** para desligar a ferramenta com segurança.

 

| **Comando**    | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h ajuda        | Ajuda e saída da interface de linha de comando da ferramenta de vídeo.                                                                                                                                                                                                                                                                                                                                             |
| -v versão     | Exibir versão da ferramenta e sair.                                                                                                                                                                                                                                                                                                                                                                 |
| -l log-filtrar  | Definir um nível de filtro para o arquivo de log. As mensagens de log têm 4 níveis possíveis: DEBUG (menor), INFO, WARNING e ERROR (maior). Configurar um nível de filtro de log filtra mensagens de log para apenas mensagens com o mesmo nível ou superior. Por exemplo, se o nível do filtro estiver definido como aviso, apenas mensagens de aviso e de erro serão registradas. Por padrão, essa opção é definida como desativado, o que desabilita o registro em log. |
| -g get-version | Se especificado, a ferramenta somente Obtém a versão FW da caneta conectada que corresponde ao arquivo de configuração armazenado na mesma pasta da ferramenta.                                                                                                                                                                                                                                    