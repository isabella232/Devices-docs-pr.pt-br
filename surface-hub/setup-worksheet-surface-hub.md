---
title: Planilha de instalação (Surface Hub)
description: Quando você terminar a pré-instalação e estiver pronto para iniciar a instalação pela primeira vez do Microsoft Surface Hub, verifique se tem todas as informações listadas nesta seção.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: Planilha de instalação, pré-instalação, instalação pela primeira vez
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831046"
---
# Planilha de instalação (Surface Hub)


Quando você terminar a pré-instalação e estiver pronto para iniciar a instalação pela primeira vez do Microsoft Surface Hub, verifique se tem todas as informações listadas nesta seção.

Você deve preencher uma lista para cada Surface Hub que precisa configurar, embora algumas informações possa ser usadas em todos os Surface Hubs, como as informações de proxy ou as credenciais de domínio. Algumas dessas informações talvez não sejam necessárias, dependendo de como você decidiu configurar seu dispositivo, ou dependendo de como o ambiente é configurado para a infraestrutura da organização.

<table>
<tr>
<th>Propriedade</th>
<th>Para que isso é usado</th>
<th>Exemplo</th>
<th>Valor real</th>
</tr>
<tr>
<td>
<p>Informações de proxy</p>
</td>
<td>
<p>Se sua rede usa um proxy de rede e/ou acesso à Internet, você deve fornecer um script ou informações de servidor/porta.</p>
</td>
<td>
<p>Script de proxy: <code>http://contoso/proxy.pa</code> </br>
- OU - </br>
Informações de servidor e porta: 10.10.10.100, porta 80
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Credenciais de rede sem fio (nome de usuário e senha)</p>
</td>
<td>
<p>Se você decidir conectar o dispositivo ao Wi-Fi, e sua rede sem fio exigir credenciais de usuário.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>UPN da conta de dispositivo ou domínio/nome de usuário e senha da conta de dispositivo</p>
</td>
<td>
<p>Isso é o Nome Principal de Usuário (UPN) ou o domínio/nome de usuário e a senha da conta de dispositivo. E-mail, calendário e Skype for Business dependem de uma conta de dispositivo compatível.</p>
</td>
<td>
<p> UPN: ConfRoom15@contoso.com, #Passw0rd1 </br>
- OU - <br> 
Domínio e nome de usuário: CONTOSO\ConfRoom15, #Passw0rd1</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Microsoft Exchange Server da conta de dispositivo</p>
</td>
<td>
<p>É o servidor do Exchange da conta de dispositivo.
Email, calendário e Skype for Business dependem de uma conta de dispositivo compatível.
Para que email e calendário funcionem, a conta de dispositivo deve ter um servidor do Exchange válido. O dispositivo tentará encontrar isso automaticamente.</p>
</td>
<td>
<p>outlook.office365.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Endereço Session Initiation Protocol (SIP) da conta de dispositivo</p>
</td>
<td>
<p>É o endereço SIP do Skype for Business da conta de dispositivo.
Email, calendário e Skype for Business dependem de uma conta de dispositivo compatível.
Para que o Skype for Business funcione, a conta de dispositivo deve ter um endereço SIP válido. O dispositivo tentará encontrar isso automaticamente.</p>
</td>
<td>
<p>sip: ConfRoom15@contoso.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Nome amigável</p>
</td>
<td>
<p>O nome amigável do dispositivo é o nome de transmissão que pessoas vão ver quando tentarem se conectar sem fio ao Surface Hub. Esse nome será exibido com destaque na tela do Surface Hub.
Sugerimos que o nome amigável que você escolher seja reconhecível e exclusivo para que as pessoas possam distinguir um Surface Hub de outro ao tentar se conectar.</p>
</td>
<td>
<p>Sala de conferência 15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Nome do dispositivo</p>
</td>
<td>
<p>O nome do dispositivo é o nome que será usado para o ingresso em domínio e é a identidade que aparecerá no seu provedor de MDM se o dispositivo estiver registrado em MDM.
O nome do dispositivo que você escolher não deve ser o mesmo nome de nenhum outro dispositivo no domínio do Active Directory do usuário (se optar por ingressar o dispositivo no domínio). O dispositivo não poderá ingressar no domínio se seu nome não for exclusivo.
</p>
</td>
<td>
<p>confroom15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SE VOCÊ ESTIVER INGRESSANDO NO AZURE AD</b></p>
</td>
</tr>
<tr>
<td>
<p>Credenciais de usuário de locatário do Azure AD (nome de usuário e senha)</p>
</td>
<td>
<p>Se decidir que as pessoas em sua organização do Azure Active Directory (Azure AD) se tornam administradores no dispositivo, você precisará ingressar no Azure AD.
Para ingressar no Azure AD, você precisará de credenciais de usuário válidas.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SE VOCÊ ESTIVER INGRESSANDO EM UM DOMÍNIO</b></p>
</td>
</tr>
<tr>
<td>
<p>Domínio no qual ingressar</p>
</td>
<td>
<p>Este é o domínio em que você precisará ingressar para que um grupo de segurança de sua escolha possa ser administrador do dispositivo.
Talvez seja necessário o nome de domínio totalmente qualificado (FQDN).</p>
</td>
<td>
<p>contoso (nome abreviado) OU contoso.corp.com (FQDN)</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Credenciais da conta de domínio (nome de usuário e senha)</p>
</td>
<td>
<p>Não é possível ingressar em um domínio, a menos que você forneça credenciais de conta suficientes para ingressar no domínio. Assim que você fornecer um domínio no qual ingressar e credenciais para ingressar no domínio, um grupo de segurança de sua escolha poderá alterar as configurações no dispositivo.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Alias de grupo de segurança de administração</p>
</td>
<td>
<p>Isso é um grupo de segurança em seu Active Directory (AD); todos os membros deste grupo de segurança podem alterar as configurações no dispositivo.</p>
</td>
<td>
<p>SurfaceHubAdmins</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SE VOCÊ ESTIVER USANDO UM ADMINISTRADOR LOCAL</b></p>
</td>
</tr>
<tr>
<td>
<p>Credenciais da conta de administrador local (nome de usuário e senha)</p>
</td>
<td>
<p>Se você decidir não ingressar em um domínio do AD ou Azure AD, poderá criar uma conta de administrador local no dispositivo.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SE VOCÊ PRECISAR INSTALAR CERTIFICADOS OU APLICATIVOS</b></p>
</td>
</tr>
<tr>
<td>
<p>Unidade USB</p>
</td>
<td>
<p>Se você souber antes da primeira execução que deseja instalar certificados ou aplicativos universais, siga as etapas em <a href="provisioning-packages-for-certificates-surface-hub.md">Criar pacotes de provisionamento</a>. Os pacotes de provisionamento serão criados em uma unidade USB.</p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





