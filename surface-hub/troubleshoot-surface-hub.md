---
title: Solução de problemas do Microsoft Surface Hub
description: Solucione problemas comuns, incluindo problemas de instalação e erros do Exchange ActiveSync.
ms.assetid: CF58F74D-8077-48C3-981E-FCFDCA34B34A
ms.reviewer: ''
manager: laurawi
keywords: Solucione problemas comuns, problemas de instalação, erros do Exchange ActiveSync.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2018
ms.localizationpriority: medium
ms.openlocfilehash: fe87c56474a05152f991a5b63f6abf0cf05e8b03
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830325"
---
# Solução de problemas do Microsoft Surface Hub


Solucione problemas comuns, incluindo problemas de instalação e erros do Exchange ActiveSync.

A [ferramenta Diagnóstico de Hardware do Surface Hub](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contém testes interativos que permitem verificar se a funcionalidade essencial do Hub está operando conforme o esperado. Além de testar o hardware, o diagnóstico pode testar a conta do recurso para verificar se ela está configurada corretamente para seu ambiente. Se forem encontrados problemas, os resultados poderão ser salvos e compartilhados com a equipe de suporte do Surface Hub. Para obter informações de uso, consulte [Como usar a ferramenta Diagnóstico de Hardware do Surface Hub para testar uma conta de dispositivo](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).

Problemas comuns são listados na tabela a seguir, juntamente com as causas e correções possíveis. A seção [Solução de problemas de instalação](#setup-troubleshooting) contém uma lista de problemas no dispositivo, juntamente com vários tipos de problemas que podem ser encontrados durante a experiência de primeira execução. A seção [Erros do Exchange ActiveSync](#exchange-activesync-errors) lista erros comuns que o dispositivo pode encontrar ao tentar sincronizar com um servidor do Microsoft Exchange ActiveSync.




## Solução de problemas de instalação


Esta seção lista as causas e possíveis correções para ajudar a solucionar problemas que você pode encontrar ao configurar o Microsoft Surface Hub.

### No dispositivo

Possíveis correções para os problemas no Surface Hub depois de concluir a primeira execução do programa.

<table>
<tr>
<th>Problema</th>
<th>Causas</th>
<th>Possíveis correções</th>
</tr>
<tr>
<td rowspan="2">
<p>Não receber mensagens de aceitação/recusa automáticas.</p>
</td>
<td>
<p>A conta do dispositivo não está configurada para aceitar/recusar mensagens automaticamente.</p>
</td>
<td>
<p>Use o cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code> do PowerShell.</p>
</td>
</tr>
<tr>
<td>
<p>A conta do dispositivo não está configurada para processar solicitações de reuniões externas.</p>
</td>
<td>
<p>Use o cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code> do PowerShell.</p>
</td>
</tr>
<tr>
<td>
<p>O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (nenhuma conta provisionada)" está sendo exibida.</p>
</td>
<td>
<p>Nenhuma conta do dispositivo está configurada neste Surface Hub.</p>
</td>
<td>
<p>Provisione uma conta do dispositivo em Configurações.</p>
</td>
</tr>
<tr>
<td>
<p>O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (provisionados em excesso)" está sendo exibida.</p>
</td>
<td>
<p>A conta do dispositivo está provisionada em muitos dispositivos.</p>
</td>
<td>
<p>Remova a conta do dispositivo de outros dispositivos os quais estão provisionados. Isso pode ser feito por meio do portal de administrador do Exchange.</p>
</td>
</tr>
<tr>
<td>
<p>O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (credenciais inválidas)" está sendo exibida.</p>
</td>
<td>
<p>A senha da conta do dispositivo expirou e não é mais válida.</p>
</td>
<td>
<p>Atualize a senha da conta em Configurações. Consulte também <a href="password-management-for-surface-hub-device-accounts.md">Gerenciamento de senhas</a>.</p>
</td>
</tr>
<tr>
<td>
<p>O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (política da conta)" está sendo exibida.</p>
</td>
<td>
<p>A conta do dispositivo está usando uma política do ActiveSync inválida.</p>
</td>
<td>
<p>Verifique se a conta do dispositivo tem uma política do ActiveSync em que <code>PasswordEnabled == False</code>.</p>
</td>
</tr>
<tr>
<td>
<p>O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados" está sendo exibida.</p>
</td>
<td>
<p>O Exchange não está habilitado.</p>
</td>
<td>Habilite a conta do dispositivo para os serviços do Exchange em Configurações. Você precisa verificar se você tem o conjunto de políticas do ActiveSync correto e também se tem instalado quaisquer certificados necessários para os serviços do Exchange funcionarem.</td>
</tr>
<tr>
<td>
<p>Não é possível fazer logon no Skype for Business.</p>
</td>
<td>
<p>A conta do dispositivo não tem uma propriedade de endereço do Protocolo de Início de Sessão (SIP).</p>
</td>
<td>
<p>A conta não tem uma propriedade de endereço SIP e seu Nome UPN não coincide com o endereço SIP real. A conta deve ter seu endereço SIP definido ou o endereço SIP deve ser adicionado usando o aplicativo Configurações.</p>
</td>
</tr>
<tr>
<td>
<p>Não é possível fazer logon no Skype for Business.</p>
</td>
<td>
<p>A conta do dispositivo requer um certificado para se autenticar no Skype for Business.</p>
</td>
<td>
<p>Instale o certificado apropriado usando pacotes de provisionamento.</p>
</td>
</tr>
</table>
 

### Primeira execução

Possíveis correções para os problemas com o programa de primeira execução do Surface Hub.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Possíveis correções</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Não é possível encontrar a conta quando solicitado o nome de usuário e domínio.</p></td>
<td align="left"><p>O domínio precisa ter o nome totalmente qualificado (FQDN).</p></td>
<td align="left"><p>O FQDN deve ser fornecido no campo domínio.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a>A página de conta do dispositivo, problemas de novas configurações de conta

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Possíveis correções</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Não é possível localizar a conta fornecida no Azure AD.</p></td>
<td align="left"><p>O Nome UPN da conta fornecido tem um locatário que não pode ser acessado no Azure AD.</p></td>
<td align="left"><p>Certifique-se que possui uma conexão com a Internet ativa e que o dispositivo pode acessar os Serviços Online da Microsoft. Verifique se as credenciais da conta estão inseridas corretamente.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Não é possível acessar o diretório especificado.</p></td>
<td align="left"><p>O domínio da conta fornecido especifica um domínio que não pode ser acessado.</p></td>
<td align="left"><p>Certifique-se que possui uma conexão de rede ativa e que o dispositivo pode acessar o controlador de domínio. Verifique se as credenciais da conta estão inseridas corretamente. Você também pode tentar usar o FQDN em vez disso.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Não é possível detectar automaticamente o servidor do Exchange.</p></td>
<td align="left"><p>O servidor do Exchange não está configurado para detecção automática.</p></td>
<td align="left"><p>Habilite a detecção automática do servidor do Exchange para a conta do dispositivo, ou insira o endereço do servidor do Exchange da conta manualmente.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Não é possível descobrir o endereço SIP depois de inserir as credenciais da conta.</p></td>
<td align="left"><p>Não havia nenhuma entrada de endereço SIP no Active Directory ou Azure AD.</p></td>
<td align="left"><p>Verifique se a conta está habilitada com o Skype for Business e que possui um endereço SIP. Caso contrário, você pode inserir o endereço SIP manualmente na caixa de texto.</p></td>
</tr>
</tbody>
</table>

 

### Página da conta do dispositivo, problemas de configurações de conta existente

<table>
<tr>
<th>Problema</th>
<th>Causas</th>
<th>Códigos de erro</th>
<th>Possíveis correções</th>
</tr>
<tr>
<td>
<p>A conta não pôde autenticar com as credenciais especificadas.</p>
</td>
<td>
<p>A conta não está habilitada como um usuário no Active Directory (AD), é preciso de uma senha para autenticar ou a senha está incorreta.</p>
</td>
<td>
<p>Nenhum(a)</p>
</td>
<td>
<p>Verifique se as credenciais estão inseridas corretamente. Habilite a conta como um usuário no AD e adicione uma senha ou defina a RoomMailboxPassword</p>. </td>
</tr>
<tr>
<td>
<p>Erro 0x800C0019 é exibido ao fornecer um Exchange server.</p>
</td>
<td>
<p>A conta do dispositivo requer um certificado para autenticar.</p>
</td>
<td>
<p>0x800C0019</p>
</td>
<td>
<p>Instale o certificado apropriado usando pacotes de provisionamento.</p>
</td>
</tr>
<tr>
<td>
<p>As credenciais da conta do dispositivo não são válidas para o servidor do Exchange fornecido.</p>
</td>
<td>
<p>O servidor do Exchange fornecido não é onde a caixa de correio da conta do dispositivo está hospedada.</p>
</td>
<td>
<p>Nenhum(a)</p>
</td>
<td>
<p>Verifique se você está fornecendo o servidor de email do Exchange correto para a conta do dispositivo.</p>
</td>
</tr>
<tr>
<td>
<p>Tempo limite HTTP ao tentar acessar o servidor do Exchange.</p>
</td>
<td></td>
<td>
<p>0x80072EE2</p>
</td>
<td></td>
</tr>
<tr>
<td>
<p>Não foi possível localizar o servidor do Exchange fornecido.</p>
</td>
<td>
<p>O servidor do Exchange fornecido não pôde ser encontrado.</p>
</td>
<td>
<p>Nenhum</p>
</td>
<td>
<p>Verifique se você possui uma conexão com a Internet ou rede, e se o servidor do Exchange que você forneceu está correto.</p>
</td>
</tr>
<tr>
<td>
<p>HTTP não suportado.</p>
</td>
<td>
<p>Um servidor do Exchange com <i>http://</i>, em vez de <i>https://</i>, foi fornecido.</p>
</td>
<td>
<p>Nenhum</p>
</td>
<td>
<p>Utilize um servidor do Exchange que use https.</p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p>As pessoas entram na página intitulada "Há um problema com esta conta" em relação ao ActiveSync.</p>
</div>
<div> </div>
</td>
<td>
<p>A política PasswordEnabled do ActiveSync está definida como True (ou 1).</p>
</td>
<td>
<p>Nenhum(a)</p>
</td>
<td>
<p>Crie uma nova política ActiveSync onde PasswordEnabled é definido como False (ou 0) e depois aplique essa política à conta.</p>
</td>
</tr>
<tr>
<td>
<p>O Surface Hub não tem uma conexão com o Exchange.</p>
</td>
<td>
<p>Nenhuma</p>
</td>
<td>
<p>Certifique-se que possui uma conexão com a Internet ou rede ativa.</p>
</td>
</tr>
<tr>
<td>
<p>Exchange retorna um código de status indicando um erro.</p>
</td>
<td>
<p>Nenhuma</p>
</td>
<td>
<p>Certifique-se que possui uma conexão com a Internet ou rede ativa.</p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a>Executado pela primeira vez, o Domínio é associado aos problemas da página

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Possíveis correções</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Ao tentar ingressar em um domínio, um erro mostra que a conta não pôde autenticar usando as credenciais especificadas.</p></td>
<td align="left"><p>As credenciais fornecidas não são capazes de ingressar no domínio especificado.</p></td>
<td align="left"><p>Insira credenciais corretas para uma conta que existe no domínio especificado.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Ao especificar um grupo de um domínio, um erro mostra que o grupo não pôde ser encontrado no domínio.</p></td>
<td align="left"><p>O grupo pode ter sido removido ou não existe mais.</p></td>
<td align="left"><p>Verifique se o grupo existe dentro do domínio.</p></td>
</tr>
</tbody>
</table>

 

### Primeira execução, página do servidor do Exchange

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Possíveis correções</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>As pessoas entram nesta página e é solicitado que preencham o endereço do servidor do Exchange.</p></td>
<td align="left"><p>O servidor do Exchange não está configurado para detecção automática.</p></td>
<td align="left"><p>Habilite a detecção automática do servidor do Exchange para a conta do dispositivo, ou insira o endereço do servidor do Exchange da conta manualmente.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a>Primeira execução, problemas no dispositivo

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Códigos de erro</th>
<th align="left">Possíveis correções</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Não é possível sincronizar o calendário/email.</p></td>
<td align="left"><p>A conta não tem permissão do Surface Hub como um dispositivo permitido.</p></td>
<td align="left"><p>0x86000C1C</p></td>
<td align="left"><p>Adicione a ID do dispositivo do Surface Hub à lista de permissões, definindo a <strong> </strong> Propriedade ActiveSyncAllowedDeviceIds para a caixa de correio.</p></td>
</tr>
</tbody>
</table>

 



 

## Erros do Exchange ActiveSync


Esta seção lista códigos de status, mapeamento, mensagens de usuário e ações que um administrador pode executar para resolver erros do Exchange ActiveSync.

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Código hexadecimal</th>
<th align="left">Mapeamento</th>
<th align="left">Mensagem amigável</th>
<th align="left">Ações a serem executadas pelo administrador</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0x85010002</p></td>
<td align="left"><p>E_HTTP_DENIED</p></td>
<td align="left"><p>A senha deve ser atualizada.</p></td>
<td align="left"><p>Atualize a senha.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072EFD</p></td>
<td align="left"><p>WININET_E_CANNOT_CONNECT</p></td>
<td align="left"><p>Não é possível se conectar ao servidor no momento. Aguarde um pouco e tente novamente ou verifique as configurações da conta.</p></td>
<td align="left"><p>Verifique se o nome do servidor está correto e acessível. Verifique se o dispositivo está conectado à rede.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C29</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (as políticas não correspondem)</p></td>
<td align="left"><p>A conta está configurada com políticas não compatíveis com o Surface Hub.</p></td>
<td align="left"><p>Desabilite a política <strong>PasswordEnabled</strong> para essa conta.</p>
<p>Temos um bug que pode haver erros de política de superfície se a conta não receber notificações de servidor dentro do intervalo de atualização de política.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C4C</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</p></td>
<td align="left"><p>A conta tem muitas parcerias de dispositivos.</p></td>
<td align="left"><p>Exclua uma ou mais parcerias no servidor.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C0A</p></td>
<td align="left"><p>E_NEXUS_STATUS_SERVERERROR_RETRYLATER</p></td>
<td align="left"><p>Não é possível se conectar ao servidor no momento.</p></td>
<td align="left"><p>Aguarde até que o servidor fique online novamente. Se o problema persistir, provisione novamente a conta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050003</p></td>
<td align="left"><p>E_CREDENTIALS_EXPIRED (As credenciais expiraram e precisam ser atualizadas)</p></td>
<td align="left"><p>A senha deve ser atualizada.</p></td>
<td align="left"><p>Atualize a senha.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x8505000D</p></td>
<td align="left"><p>E_AIRSYNC_RESET_RETRY</p></td>
<td align="left"><p>Não é possível se conectar ao servidor no momento. Aguarde um momento ou verifique as configurações da conta.</p></td>
<td align="left"><p>Isso normalmente é um erro temporário, mas, se o problema persistir, verifique a quantidade de dispositivos associados à conta e exclua alguns deles se o número for grande.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C16</p></td>
<td align="left"><p>E_NEXUS_STATUS_USER_HASNOMAILBOX</p></td>
<td align="left"><p>A caixa de correio foi migrada para um servidor diferente.</p></td>
<td align="left"><p>Você nunca deve ver esse erro. Se o problema persistir, provisione novamente a conta.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010004</p></td>
<td align="left"><p>E_HTTP_FORBIDDEN</p></td>
<td align="left"><p>Não é possível se conectar ao servidor no momento. Aguarde um momento e tente novamente ou verifique as configurações da conta.</p></td>
<td align="left"><p>Verifique o nome do servidor para certificar se está correto. Se a conta estiver usando autenticação baseada em certificado, verifique se o certificado ainda é válido e atualize-o se necessário.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85030028</p></td>
<td align="left"><p>E_ACTIVESYNC_PASSWORD_OR_GETCERT</p></td>
<td align="left"><p>A senha da conta ou o certificado do cliente estão ausentes ou são inválidos.</p></td>
<td align="left"><p>Atualize a senha e/ou implemente o certificado do cliente.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C2A</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_POLICYREFRESH</p></td>
<td align="left"><p>A conta está configurada com políticas não compatíveis com o Surface Hub.</p></td>
<td align="left"><p>Desabilite a política PasswordEnabled para essa conta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050002</p></td>
<td align="left"><p>E_CREDENTIALS_UNAVAILABLE</p></td>
<td align="left"><p>A senha deve ser atualizada.</p></td>
<td align="left"><p>Atualize a senha.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE2</p></td>
<td align="left"><p>WININET_E_TIMEOUT</p></td>
<td align="left"><p>A rede não é compatível com o tempo limite de ociosidade mínimo necessário para receber a notificação do servidor ou o servidor está offline.</p></td>
<td align="left"><p>Verifique se o servidor está em execução. Verifique as configurações de NAT.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85002004</p></td>
<td align="left"><p>E_FAIL_ABORT</p></td>
<td align="left"><p>Este erro é usado para interromper a sincronização deslocada e não será exposto aos usuários. Ele será mostrado nos dados de diagnóstico se você forçar uma sincronização interativa, excluir a conta ou atualizar suas configurações.</p></td>
<td align="left"><p>Nada.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010017</p></td>
<td align="left"><p>E_HTTP_SERVICE_UNAVAIL</p></td>
<td align="left"><p>Não é possível se conectar ao servidor no momento. Aguarde um momento ou verifique as configurações da conta.</p></td>
<td align="left"><p>Verifique o nome do servidor para certificar se está correto. Aguarde até que o servidor fique online novamente. Se o problema persistir, provisione novamente a conta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C0D</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</p></td>
<td align="left"><p>Não é possível se conectar ao servidor no momento. Aguarde um momento ou verifique as configurações da conta.</p></td>
<td align="left"><p>Verifique o nome do servidor para certificar se está correto. Aguarde até que o servidor fique online novamente. Se o problema persistir, provisione novamente a conta.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85030027</p></td>
<td align="left"><p>E_ACTIVESYNC_GETCERT</p></td>
<td align="left"><p>O servidor do Exchange requer um certificado.</p></td>
<td align="left"><p>Importe o certificado EAS apropriado do Surface Hub.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C2B</p></td>
<td align="left"><p>E_NEXUS_STATUS_INVALID_POLICYKEY</p></td>
<td align="left"><p>A conta está configurada com políticas não compatíveis com o Surface Hub.</p></td>
<td align="left"><p>Desabilite a política PasswordEnabled para essa conta.</p>
<p>Temos um bug que pode haver erros de política de superfície se a conta não receber notificações de servidor dentro do intervalo de atualização de política.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010005</p></td>
<td align="left"><p>E_HTTP_NOT_FOUND</p></td>
<td align="left"><p>O nome do servidor é inválido.</p></td>
<td align="left"><p>Verifique o nome do servidor para garantir que ele esteja correto. Se o problema persistir, provisione novamente a conta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85010014</p></td>
<td align="left"><p>E_HTTP_SERVER_ERROR</p></td>
<td align="left"><p>Não é possível se conectar ao servidor.</p></td>
<td align="left"><p>Verifique o nome do servidor para garantir que ele esteja correto. Acione uma sincronização e, se o problema persistir, provisione novamente a conta.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE7</p></td>
<td align="left"><p>WININET_E_NAME_NOT_RESOLVED</p></td>
<td align="left"><p>O nome ou endereço do servidor não pôde ser resolvido.</p></td>
<td align="left"><p>Verifique se o nome do servidor está inserido corretamente.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x8007052F</p></td>
<td align="left"><p>ERROR_ACCOUNT_RESTRICTION</p></td>
<td align="left"><p>Durante a detecção automática do servidor do Exchange, é aplicada uma política que impede o usuário conectado de fazer logon no servidor.</p></td>
<td align="left"><p>Este é um problema de tempo. Verifique novamente as credenciais da conta. Tente provisionar novamente quando elas estiverem corretas.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x800C0019</p></td>
<td align="left"><p>INET_E_INVALID_CERTIFICATE</p></td>
<td align="left"><p>O certificado de segurança necessário para acessar este recurso é inválido.</p></td>
<td align="left"><p>Instale o certificado do ActiveSync correto necessário para a conta do dispositivo fornecida.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072F0D</p></td>
<td align="left"><p>WININET_E_INVALID_CA</p></td>
<td align="left"><p>A autoridade de certificação é inválida ou está incorreta. Não é possível detectar automaticamente o servidor do Exchange porque um certificado não foi encontrado.</p></td>
<td align="left"><p>Instale o certificado do ActiveSync correto necessário para a conta do dispositivo fornecida.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80004005</p></td>
<td align="left"><p>E_FAIL</p></td>
<td align="left"><p>Não foi possível localizar o domínio fornecido. O servidor do Exchange não pôde ser detectado automaticamente e não foi fornecido nas configurações.</p></td>
<td align="left"><p>Certifique-se de que o domínio digitado é o FQDN e de que há um servidor do Exchange inserido na caixa de texto do servidor do Exchange.</p></td>
</tr>
</tbody>
</table>

## Contatar o Suporte

Se tiver dúvidas ou precisar de ajuda, você pode [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).


 
## Conteúdo relacionado

- [Solução de problemas de conexão do Miracast para o Surface Hub](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 





