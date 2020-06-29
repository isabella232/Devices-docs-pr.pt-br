---
title: Propriedades do Microsoft Exchange (Surface Hub)
description: Algumas propriedades do Microsoft Exchange da conta de dispositivo devem ser definidas como valores específicos para ter a melhor experiência de reunião no Microsoft Surface Hub.
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Propriedades do Microsoft Exchange, conta do dispositivo, Surface Hub, cmdlet do Windows PowerShell
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830662"
---
# Propriedades do Microsoft Exchange (Surface Hub)


Algumas propriedades do Microsoft Exchange da conta de dispositivo devem ser definidas como valores específicos para ter a melhor experiência de reunião no Microsoft Surface Hub. A tabela a seguir lista várias propriedades do Exchange com base em parâmetros cmdlet do PowerShell, suas finalidades e valores com os quais devem ser definidas.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Propriedade</th>
<th align="left">Descrição</th>
<th align="left">Valor</th>
<th align="left">Impacto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>O parâmetro AutomateProcessing habilita ou desabilita o processamento de calendário na caixa de correio.</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>O Surface Hub será capaz de aceitar ou recusar solicitações de reunião automaticamente com base em sua disponibilidade.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>O parâmetro AddOrganizerToSubject especifica se o nome do organizador da reunião é usado como assunto da solicitação de reunião.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>A tela de boas-vindas não mostrará o organizador da reunião duas vezes (em vez de mostrá-lo como o organizador e no assunto da reunião).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>O parâmetro AllowConflicts especifica se é possível permitir solicitações de reunião conflitantes.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>O Surface Hub recusará solicitações de reunião que entrem em conflito com o horário de outra reunião.</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>O parâmetro DeleteComments especifica se é preciso remover ou manter qualquer texto no corpo da mensagem de solicitações de reunião recebidas.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>O corpo da mensagem de reuniões pode ser mantido e recuperado de um Surface Hub se você precisar dele durante uma reunião.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>O parâmetro DeleteSubject especifica se é preciso remover ou manter o assunto de solicitações de reunião recebidas.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Os assuntos de solicitação de reunião podem ser mostrados no Surface Hub.</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>O parâmetro RemovePrivateProperty especifica se é preciso apagar o sinalizador privado para solicitações de reunião recebidas.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Assuntos de reunião particular serão mostrados como Particular na tela de boas-vindas.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>O parâmetro AddAdditionalResponse especifica se informações adicionais serão enviadas da caixa de correio de recurso ao responder às solicitações de reunião.</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>Quando uma resposta é enviada para uma solicitação de reunião, um texto personalizado é fornecido na resposta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>O parâmetro AdditionalResponse especifica as informações adicionais a serem incluídas nas respostas às solicitações de reunião.</p>
<div class="alert">
<strong>Observação </strong> esse texto não será enviado, a menos que AddAdditionalResponse esteja definido como $true.
</div>
<div>
 
</div></td>
<td align="left"><p>Você decide: a resposta adicional pode ser usada para informar às pessoas como usar um Surface Hub ou direcioná-las para recursos.</p></td>
<td align="left"><p>Adicionar uma mensagem de resposta adicional pode fornecer às pessoas uma introdução de como elas podem usar um Surface Hub na reunião.</p></td>
</tr>
</tbody>
</table>

 

 

 





