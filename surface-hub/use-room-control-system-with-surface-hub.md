---
title: Usando um sistema de controle de sala (Surface Hub)
description: Sistemas de controle de sala podem ser usados com o Microsoft Surface Hub.
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: sistema de controle de sala, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830314"
---
# Usando um sistema de controle de sala (Surface Hub)


Sistemas de controle de sala podem ser usados com o Microsoft Surface Hub.

Usar um sistema de controle de sala com o Surface Hub envolve conectar o hardware de controle de sala ao Surface Hub, geralmente por meio da porta serial RJ11 na parte inferior do Surface Hub.

## Configurações de terminal

Para se conectar a um painel de controle de sistema de controle de sala, não é necessário definir nenhuma configuração de terminal do Surface Hub. Se deseja conectar um computador ou laptop ao Surface Hub e enviar comandos seriais a partir do Surface Hub, você pode usar um programa emulador de terminal como Tera Term ou PuTTY. 

| Configuração | Valor |
| --- | --- |
| Taxa de transmissão | 115200 |
| Bits de dados | 08 | 
| Bits de parada | um |
| Paridade | nenhuma |
| Controle de fluxo | nenhuma |
| Alimentação de linha | retorno de cada carro |
 

## Diagrama de conexão

Você pode usar um conector RJ-11 (6P6C) padrão para conectar a porta serial do Surface Hub a um sistema de controle de sala. Este é o método recomendado. Você também pode usar um cabo de 4 condutores RJ-11, mas não recomendamos esse método.

Este diagrama mostra a saída de pinos correta usada para um cabo RJ-11 (6P6C) para DB9.

![Imagem mostrando o diagrama de conexão.](images/room-control-wiring-diagram.png)

## Conjuntos de comando

Os sistemas de controle de sala usam cenários comuns de sala de reuniões para comandos. Os comandos são originados do sistema de controle de sala e transmitidos por uma conexão serial para um Surface Hub. Os comandos são baseados em ASCII e o Surface Hub confirmará quando ocorrem alterações de estado.

Os seguintes modificadores de comando estão disponíveis. Os comandos terminam com um caractere de nova linha (\n). As respostas podem vir a qualquer momento em resposta a alterações de estado não disparadas diretamente por um comando de porta de gerenciamento.

| Modificador | Resultado |
| --- | --- |
| + | Incrementar um valor |
| - | Diminuir um valor |
| = | Definir um valor distinto |
| ? | Consultas para um valor atual |
 

## Ligar/Desligar

O Surface Hub pode estar em um destes estados de energia.

| Estado | Estado Energy Star| Descrição |
| --- | --- | --- |
| 0 | S5 | Desativado |
| um | - | Ligado (indeterminado) |
| 2 | S3 | Suspensão |
| 5 | S0 | Pronto |


No modo de substituição de computador, os estados de energia serão somente Pronto e Desativado e somente alteram a tela. A porta de gerenciamento não pode ser usada para ligar o computador de substituição. 

| Estado | Estado Energy Star| Descrição |
| --- | --- | --- |
| 0 | S5 | Desativado |
| 5 | S0 | Pronto |

Para um dispositivo de controle, algo diferente de 5/Pronto deve ser considerado Desativado. Cada comando Powerize resulta em duas alterações de estado e respostas. 

| Comando | Mudança de estado| Resposta |
| --- | --- | --- |
| PowerOn | Dispositivo é ativado (tela + computador).</br></br>O serviço de computador notifica o SMC que o computador está pronto. |  Power=0</br></br>Power=5 |
| PowerOff | O dispositivo faz a transição para o estado de ambiente (computador ativado, tela esmaecida). |  Power=0 |
| Power? |  O SMC relata o último estado de energia. |  Power=<#> |



## Brilho

O nível de brilho atual tem um intervalo de 0 a 100.

Alterações em níveis de brilho podem ser enviadas por um sistema de controle de sala ou outro sistema.

| Comando | Mudança de estado |Resposta |
| --- | --- | --- |
| Brightness+ | O controlador de gerenciamento do sistema (SMC) envia o comando de aumento de brilho.</br></br>O serviço de computador no sistema de controle de sala notifica o SMC sobre o novo nível de brilho. |  Brightness = 51 |
| Brightness- |  O SMC envia o comando de diminuição de brilho.</br></br>O serviço de computador notifica o SMC sobre o novo nível de brilho. | Brightness = 50 |

## Volume

O nível de volume atual é um intervalo de 0 a 100.

Alterações em níveis de volume podem ser enviadas por um sistema de controle de sala ou outro sistema.

>[!NOTE]
>O comando de Volume controla somente o volume no modo incorporado ou computador substituto, não de [Fontes convidadas](connect-and-display-with-surface-hub.md).

| Comando | Mudança de estado | Resposta</br>(No [modo Computador substituto](connect-and-display-with-surface-hub.md#replacement-pc-mode)) |
| --- | --- | --- |
| Volume+ |  O SMC envia o comando de aumentar volume.</br></br>O serviço de computador notifica o SMC sobre o novo nível de volume. |  Volume = 51 |
| Volume- |  O SMC envia o comando de diminuir volume.</br></br>O serviço de computador notifica o SMC sobre o novo nível de volume. |  Volume = 50 |


 

## Silenciar para áudio

O áudio pode ser desativado.

| Comando | Mudança de estado | Resposta |
| --- | --- | --- |
| AudioMute+ |  O SMC envia o comando de silenciar áudio.</br></br>O serviço de computador notifica o SMC que o áudio está desativado. |  nenhuma |


 

## Fonte de vídeo

Várias fontes de exibição podem ser usadas.

| Estado | Descrição | 
| --- | --- |
| 0 |  Computador integrado |
| um |  DisplayPort |
| 2 |  HDMI |
| 3D |  VGA |


 

Alterações na fonte de exibição podem ser enviadas por um sistema de controle de sala ou outro sistema.

| Comando | Mudança de estado | Resposta |
| --- | --- | --- |
| Source=# |  O SMC muda para a fonte desejada.</br></br>O serviço de computador notifica o SMC que a fonte de exibição mudou. |  Source=&lt;#&gt; |
| Source+ |  O SMC alterna para a próxima fonte de entrada ativa.</br></br>O serviço de computador notifica o SMC sobre a fonte de entrada atual. |  Source=&lt;#&gt; |
| Source- | O SMC alterna para a fonte de entrada ativa anterior.</br></br>O serviço de computador notifica o SMC sobre a fonte de entrada atual. |  Source=&lt;#&gt; |
| Source? |  O SMC consulta o serviço do computador quanto à fonte de entrada ativa.</br></br>O serviço de computador notifica o SMC sobre a fonte de entrada atual. | Source=&lt;#&gt; |

## Erros

Os erros são retornados seguindo o formato nesta tabela.

| Erro | Observações |
| --- | --- |
| Erro: comando desconhecido '&lt;input&gt;'. |  A instrução contém um comando inicial desconhecido. Por exemplo, &quot;VOL+&quot; seria inválido e retornaria &quot; Erro: comando desconhecido 'VOL'&quot;. |
| Erro: operador desconhecido '&lt;input&gt;'. |  A instrução contém um operador desconhecido. Por exemplo, &quot;Volume!&quot; seria inválido e retornaria &quot; Erro: Operador desconhecido '!'&quot;. |
| Erro: parâmetro desconhecido '&lt;input&gt;'. |  A instrução contém um parâmetro desconhecido. Por exemplo, &quot;Volume=abc&quot; seria inválido e retornaria &quot; Erro: parâmetro desconhecido 'abc'&quot;. |
| Erro: comando não disponível quando '&lt;input&gt;' está desativado. |  Quando o Surface Hub está desativado, comandos diferentes de Liga/Desliga retornam esse erro. Por exemplo, &quot;Volume+&quot; seria inválido e retornaria &quot; Erro: comando não disponível quando 'Volume' está desativado&quot;. |


 

## Tópicos relacionados


[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





