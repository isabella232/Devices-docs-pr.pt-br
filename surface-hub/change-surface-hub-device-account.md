---
title: Alterar a conta de dispositivo do Microsoft Surface Hub
description: Você pode alterar a conta do dispositivo em Configurações para adicionar uma conta, caso nenhuma tenha sido provisionada ainda, ou para alterar as propriedades de uma conta que já foi provisionada.
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
ms.reviewer: ''
manager: laurawi
keywords: alterar conta de dispositivo, alterar propriedades, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: b90ef3e208f1e76e4b02fb9f49e3e24030947bc7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831122"
---
# Alterar a conta do dispositivo Microsoft Surface Hub


Você pode alterar a conta do dispositivo em Configurações para adicionar uma conta, caso nenhuma tenha sido provisionada ainda, ou para alterar as propriedades de uma conta que já foi provisionada.

##  <a name="details"></a>Detalhes


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Valor</th>
<th align="left">Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>UPN</p></td>
<td align="left"><p>O nome principal do usuário (UPN) da conta de dispositivo.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Senha</p></td>
<td align="left"><p>A senha correspondente da conta de dispositivo.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Domínio</p></td>
<td align="left"><p>O domínio ao qual a conta de dispositivo pertence. Esse campo não precisa ser fornecido para contas do Office 365.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Nome do usuário</p></td>
<td align="left"><p>O nome do usuário da conta de dispositivo. Esse campo não precisa ser fornecido para contas do Office 365.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Endereço Session Initiation Protocol (SIP)</p></td>
<td align="left"><p>O endereço SIP da conta de dispositivo.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Servidor do Microsoft Exchange</p></td>
<td align="left"><p>É o servidor do Exchange da conta de dispositivo. O nome de usuário e senha da conta de dispositivo devem ser autenticados no servidor do Exchange especificado.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Habilitar serviços do Exchange</p></td>
<td align="left"><p>Quando marcada, todos os serviços do Exchange serão habilitados (por exemplo, calendário na tela de boas-vindas, enviar quadros de comunicações por email). Quando desmarcada, todos os serviços do Exchange serão desabilitados e o servidor do Exchange não precisa ser fornecido.</p></td>
</tr>
</tbody>
</table>

 

##  <a name="what-happened"></a>O que ocorre?


O UPN e a senha são usados para validar a conta no AD ou Azure AD. Se a validação falhar, você talvez precise fornecer o nome de usuário e domínio.

Usando as credenciais fornecidas, tentaremos descobrir o endereço SIP. Se um endereço SIP não for encontrado, o Skype for Business usará o UPN como o endereço SIP. Se este não for o endereço SIP da conta, você precisará fornecer o endereço SIP.

O endereço do servidor do Exchange precisará ser fornecido se o dispositivo não conseguir encontrar um servidor associado às credenciais de logon. O Microsoft Surface Hub usará o servidor do Exchange para se comunicar com o ActiveSync, que ativa vários recursos importantes no dispositivo.

##  <a name="related-topics"></a>Tópicos relacionados


[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





