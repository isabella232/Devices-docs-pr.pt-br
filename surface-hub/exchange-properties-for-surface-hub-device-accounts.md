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
# <span data-ttu-id="1f846-104">Propriedades do Microsoft Exchange (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="1f846-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="1f846-105">Algumas propriedades do Microsoft Exchange da conta de dispositivo devem ser definidas como valores específicos para ter a melhor experiência de reunião no Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1f846-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="1f846-106">A tabela a seguir lista várias propriedades do Exchange com base em parâmetros cmdlet do PowerShell, suas finalidades e valores com os quais devem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="1f846-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1f846-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="1f846-107">Property</span></span></th>
<th align="left"><span data-ttu-id="1f846-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f846-108">Description</span></span></th>
<th align="left"><span data-ttu-id="1f846-109">Valor</span><span class="sxs-lookup"><span data-stu-id="1f846-109">Value</span></span></th>
<th align="left"><span data-ttu-id="1f846-110">Impacto</span><span class="sxs-lookup"><span data-stu-id="1f846-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f846-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="1f846-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-112">O parâmetro AutomateProcessing habilita ou desabilita o processamento de calendário na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="1f846-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="1f846-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-114">O Surface Hub será capaz de aceitar ou recusar solicitações de reunião automaticamente com base em sua disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="1f846-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1f846-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="1f846-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-116">O parâmetro AddOrganizerToSubject especifica se o nome do organizador da reunião é usado como assunto da solicitação de reunião.</span><span class="sxs-lookup"><span data-stu-id="1f846-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-117">$False</span><span class="sxs-lookup"><span data-stu-id="1f846-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-118">A tela de boas-vindas não mostrará o organizador da reunião duas vezes (em vez de mostrá-lo como o organizador e no assunto da reunião).</span><span class="sxs-lookup"><span data-stu-id="1f846-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f846-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="1f846-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-120">O parâmetro AllowConflicts especifica se é possível permitir solicitações de reunião conflitantes.</span><span class="sxs-lookup"><span data-stu-id="1f846-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-121">$False</span><span class="sxs-lookup"><span data-stu-id="1f846-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-122">O Surface Hub recusará solicitações de reunião que entrem em conflito com o horário de outra reunião.</span><span class="sxs-lookup"><span data-stu-id="1f846-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1f846-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="1f846-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-124">O parâmetro DeleteComments especifica se é preciso remover ou manter qualquer texto no corpo da mensagem de solicitações de reunião recebidas.</span><span class="sxs-lookup"><span data-stu-id="1f846-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-125">$False</span><span class="sxs-lookup"><span data-stu-id="1f846-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-126">O corpo da mensagem de reuniões pode ser mantido e recuperado de um Surface Hub se você precisar dele durante uma reunião.</span><span class="sxs-lookup"><span data-stu-id="1f846-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f846-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="1f846-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-128">O parâmetro DeleteSubject especifica se é preciso remover ou manter o assunto de solicitações de reunião recebidas.</span><span class="sxs-lookup"><span data-stu-id="1f846-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-129">$False</span><span class="sxs-lookup"><span data-stu-id="1f846-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-130">Os assuntos de solicitação de reunião podem ser mostrados no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1f846-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1f846-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="1f846-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-132">O parâmetro RemovePrivateProperty especifica se é preciso apagar o sinalizador privado para solicitações de reunião recebidas.</span><span class="sxs-lookup"><span data-stu-id="1f846-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-133">$False</span><span class="sxs-lookup"><span data-stu-id="1f846-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-134">Assuntos de reunião particular serão mostrados como Particular na tela de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="1f846-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f846-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="1f846-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-136">O parâmetro AddAdditionalResponse especifica se informações adicionais serão enviadas da caixa de correio de recurso ao responder às solicitações de reunião.</span><span class="sxs-lookup"><span data-stu-id="1f846-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-137">$True</span><span class="sxs-lookup"><span data-stu-id="1f846-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-138">Quando uma resposta é enviada para uma solicitação de reunião, um texto personalizado é fornecido na resposta.</span><span class="sxs-lookup"><span data-stu-id="1f846-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1f846-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="1f846-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-140">O parâmetro AdditionalResponse especifica as informações adicionais a serem incluídas nas respostas às solicitações de reunião.</span><span class="sxs-lookup"><span data-stu-id="1f846-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1f846-141">Observação </strong> esse texto não será enviado, a menos que AddAdditionalResponse esteja definido como $true.</span><span class="sxs-lookup"><span data-stu-id="1f846-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="1f846-142">Você decide: a resposta adicional pode ser usada para informar às pessoas como usar um Surface Hub ou direcioná-las para recursos.</span><span class="sxs-lookup"><span data-stu-id="1f846-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f846-143">Adicionar uma mensagem de resposta adicional pode fornecer às pessoas uma introdução de como elas podem usar um Surface Hub na reunião.</span><span class="sxs-lookup"><span data-stu-id="1f846-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





