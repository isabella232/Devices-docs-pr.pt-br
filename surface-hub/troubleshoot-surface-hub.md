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
# <span data-ttu-id="29aa6-104">Solução de problemas do Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="29aa6-104">Troubleshoot Microsoft Surface Hub</span></span>


<span data-ttu-id="29aa6-105">Solucione problemas comuns, incluindo problemas de instalação e erros do Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="29aa6-105">Troubleshoot common problems, including setup issues, Exchange ActiveSync errors.</span></span>

<span data-ttu-id="29aa6-106">A [ferramenta Diagnóstico de Hardware do Surface Hub](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contém testes interativos que permitem verificar se a funcionalidade essencial do Hub está operando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-106">The [Surface Hub Hardware Diagnostic tool](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contains interactive tests which allow you to confirm essential functionality of your Hub is working as expected.</span></span> <span data-ttu-id="29aa6-107">Além de testar o hardware, o diagnóstico pode testar a conta do recurso para verificar se ela está configurada corretamente para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-107">In addition to testing hardware, the diagnostic can test the resource account to verify that it is configured properly for your environment.</span></span> <span data-ttu-id="29aa6-108">Se forem encontrados problemas, os resultados poderão ser salvos e compartilhados com a equipe de suporte do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-108">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="29aa6-109">Para obter informações de uso, consulte [Como usar a ferramenta Diagnóstico de Hardware do Surface Hub para testar uma conta de dispositivo](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span><span class="sxs-lookup"><span data-stu-id="29aa6-109">For usage information, see [Using the Surface Hub Hardware Diagnostic Tool to test a device account](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span></span>

<span data-ttu-id="29aa6-110">Problemas comuns são listados na tabela a seguir, juntamente com as causas e correções possíveis.</span><span class="sxs-lookup"><span data-stu-id="29aa6-110">Common issues are listed in the following table, along with causes and possible fixes.</span></span> <span data-ttu-id="29aa6-111">A seção [Solução de problemas de instalação](#setup-troubleshooting) contém uma lista de problemas no dispositivo, juntamente com vários tipos de problemas que podem ser encontrados durante a experiência de primeira execução.</span><span class="sxs-lookup"><span data-stu-id="29aa6-111">The [Setup troubleshooting](#setup-troubleshooting) section contains a listing of on-device problems, along with several types of issues that may be encountered during the first-run experience.</span></span> <span data-ttu-id="29aa6-112">A seção [Erros do Exchange ActiveSync](#exchange-activesync-errors) lista erros comuns que o dispositivo pode encontrar ao tentar sincronizar com um servidor do Microsoft Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="29aa6-112">The [Exchange ActiveSync errors](#exchange-activesync-errors) section lists common errors the device may encounter when trying to synchronize with an Microsoft Exchange ActiveSync server.</span></span>




## <a name="setup-troubleshooting"></a><span data-ttu-id="29aa6-113">Solução de problemas de instalação</span><span class="sxs-lookup"><span data-stu-id="29aa6-113">Setup troubleshooting</span></span>


<span data-ttu-id="29aa6-114">Esta seção lista as causas e possíveis correções para ajudar a solucionar problemas que você pode encontrar ao configurar o Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-114">This section lists causes, and possible fixes to help troubleshoot issues you might find when you set up your Microsoft Surface Hub.</span></span>

### <a name="on-device"></a><span data-ttu-id="29aa6-115">No dispositivo</span><span class="sxs-lookup"><span data-stu-id="29aa6-115">On-device</span></span>

<span data-ttu-id="29aa6-116">Possíveis correções para os problemas no Surface Hub depois de concluir a primeira execução do programa.</span><span class="sxs-lookup"><span data-stu-id="29aa6-116">Possible fixes for issues on the Surface Hub after you've completed the first-run program.</span></span>

<table>
<tr>
<th><span data-ttu-id="29aa6-117">Problema</span><span class="sxs-lookup"><span data-stu-id="29aa6-117">Issue</span></span></th>
<th><span data-ttu-id="29aa6-118">Causas</span><span class="sxs-lookup"><span data-stu-id="29aa6-118">Causes</span></span></th>
<th><span data-ttu-id="29aa6-119">Possíveis correções</span><span class="sxs-lookup"><span data-stu-id="29aa6-119">Possible fixes</span></span></th>
</tr>
<tr>
<td rowspan="2">
<p><span data-ttu-id="29aa6-120">Não receber mensagens de aceitação/recusa automáticas.</span><span class="sxs-lookup"><span data-stu-id="29aa6-120">Not receiving automatic accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-121">A conta do dispositivo não está configurada para aceitar/recusar mensagens automaticamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-121">The device account isn't configured to automatically accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-122">Use o cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code> do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29aa6-122">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-123">A conta do dispositivo não está configurada para processar solicitações de reuniões externas.</span><span class="sxs-lookup"><span data-stu-id="29aa6-123">The device account isn't configured to process external meeting requests.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-124">Use o cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code> do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29aa6-124">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-125">O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (nenhuma conta provisionada)" está sendo exibida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-125">Calendar is not showing on the Welcome screen, or message "Appointments of date (no account provisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-126">Nenhuma conta do dispositivo está configurada neste Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-126">No device account is set up on this Surface Hub.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-127">Provisione uma conta do dispositivo em Configurações.</span><span class="sxs-lookup"><span data-stu-id="29aa6-127">Provision a device account through Settings.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-128">O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (provisionados em excesso)" está sendo exibida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-128">Calendar is not showing on the Welcome screen or message "Appointments of date (overprovisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-129">A conta do dispositivo está provisionada em muitos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29aa6-129">The device account is provisioned on too many devices.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-130">Remova a conta do dispositivo de outros dispositivos os quais estão provisionados.</span><span class="sxs-lookup"><span data-stu-id="29aa6-130">Remove the device account from other devices that it's provisioned to.</span></span> <span data-ttu-id="29aa6-131">Isso pode ser feito por meio do portal de administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="29aa6-131">This can be done using the Exchange admin portal.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-132">O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (credenciais inválidas)" está sendo exibida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-132">Calendar is not showing on the Welcome screen or message "Appointments of date (invalid credentials)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-133">A senha da conta do dispositivo expirou e não é mais válida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-133">The device account's password has expired and is no longer valid.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-134">Atualize a senha da conta em Configurações.</span><span class="sxs-lookup"><span data-stu-id="29aa6-134">Update the account's password in Settings.</span></span> <span data-ttu-id="29aa6-135">Consulte também <a href="password-management-for-surface-hub-device-accounts.md">Gerenciamento de senhas</a>.</span><span class="sxs-lookup"><span data-stu-id="29aa6-135">Also see <a href="password-management-for-surface-hub-device-accounts.md">Password management</a>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-136">O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados (política da conta)" está sendo exibida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-136">Calendar is not showing on the Welcome screen or message "Appointments of date (account policy)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-137">A conta do dispositivo está usando uma política do ActiveSync inválida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-137">The device account is using an invalid ActiveSync policy.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-138">Verifique se a conta do dispositivo tem uma política do ActiveSync em que <code>PasswordEnabled == False</code>.</span><span class="sxs-lookup"><span data-stu-id="29aa6-138">Make sure the device account has an ActiveSync policy where <code>PasswordEnabled == False</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-139">O calendário não está sendo exibido na tela de boas-vindas ou a mensagem "Os compromissos podem estar desatualizados" está sendo exibida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-139">Calendar is not showing on the Welcome screen or message "Appointments may be out of date" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-140">O Exchange não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-140">Exchange is not enabled.</span></span></p>
</td>
<td><span data-ttu-id="29aa6-141">Habilite a conta do dispositivo para os serviços do Exchange em Configurações.</span><span class="sxs-lookup"><span data-stu-id="29aa6-141">Enable the device account for Exchange services through Settings.</span></span> <span data-ttu-id="29aa6-142">Você precisa verificar se você tem o conjunto de políticas do ActiveSync correto e também se tem instalado quaisquer certificados necessários para os serviços do Exchange funcionarem.</span><span class="sxs-lookup"><span data-stu-id="29aa6-142">You need to make sure you have the right set of ActiveSync policies and have also installed any necessary certificates for Exchange services to work.</span></span></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-143">Não é possível fazer logon no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="29aa6-143">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-144">A conta do dispositivo não tem uma propriedade de endereço do Protocolo de Início de Sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="29aa6-144">The device account does not have a Session Initiation Protocol (SIP) address property.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-145">A conta não tem uma propriedade de endereço SIP e seu Nome UPN não coincide com o endereço SIP real.</span><span class="sxs-lookup"><span data-stu-id="29aa6-145">The account does not have a SIP address property and its User Principal Name (UPN) does not match the actual SIP address.</span></span> <span data-ttu-id="29aa6-146">A conta deve ter seu endereço SIP definido ou o endereço SIP deve ser adicionado usando o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="29aa6-146">The account must have its SIP address set, or the SIP address should be added using the Settings app.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-147">Não é possível fazer logon no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="29aa6-147">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-148">A conta do dispositivo requer um certificado para se autenticar no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="29aa6-148">The device account requires a certificate to authenticate into Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-149">Instale o certificado apropriado usando pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-149">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
</table>
 

### <a name="first-run"></a><span data-ttu-id="29aa6-150">Primeira execução</span><span class="sxs-lookup"><span data-stu-id="29aa6-150">First run</span></span>

<span data-ttu-id="29aa6-151">Possíveis correções para os problemas com o programa de primeira execução do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-151">Possible fixes for issues with Surface Hub first-run program.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="29aa6-152">Problema</span><span class="sxs-lookup"><span data-stu-id="29aa6-152">Issue</span></span></th>
<th align="left"><span data-ttu-id="29aa6-153">Causas</span><span class="sxs-lookup"><span data-stu-id="29aa6-153">Causes</span></span></th>
<th align="left"><span data-ttu-id="29aa6-154">Possíveis correções</span><span class="sxs-lookup"><span data-stu-id="29aa6-154">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-155">Não é possível encontrar a conta quando solicitado o nome de usuário e domínio.</span><span class="sxs-lookup"><span data-stu-id="29aa6-155">Cannot find account when asked for domain and user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-156">O domínio precisa ter o nome totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="29aa6-156">Domain needs to be the fully qualified domain name (FQDN).</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-157">O FQDN deve ser fornecido no campo domínio.</span><span class="sxs-lookup"><span data-stu-id="29aa6-157">The FQDN should be provided in the domain field.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a><span data-ttu-id="29aa6-158">A página de conta do dispositivo, problemas de novas configurações de conta</span><span class="sxs-lookup"><span data-stu-id="29aa6-158">Device account page, issues for new account settings</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="29aa6-159">Problema</span><span class="sxs-lookup"><span data-stu-id="29aa6-159">Issue</span></span></th>
<th align="left"><span data-ttu-id="29aa6-160">Causas</span><span class="sxs-lookup"><span data-stu-id="29aa6-160">Causes</span></span></th>
<th align="left"><span data-ttu-id="29aa6-161">Possíveis correções</span><span class="sxs-lookup"><span data-stu-id="29aa6-161">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-162">Não é possível localizar a conta fornecida no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="29aa6-162">Unable to find the provided account in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-163">O Nome UPN da conta fornecido tem um locatário que não pode ser acessado no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="29aa6-163">The provided account's User Principal Name (UPN) has a tenant that can't be reached in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-164">Certifique-se que possui uma conexão com a Internet ativa e que o dispositivo pode acessar os Serviços Online da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="29aa6-164">Make sure that you have a working Internet connection, and that the device can reach Microsoft Online Services.</span></span> <span data-ttu-id="29aa6-165">Verifique se as credenciais da conta estão inseridas corretamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-165">Make sure the account credentials are entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-166">Não é possível acessar o diretório especificado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-166">Unable to reach the specified directory.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-167">O domínio da conta fornecido especifica um domínio que não pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-167">The provided account domain specifies a domain that can't be reached.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-168">Certifique-se que possui uma conexão de rede ativa e que o dispositivo pode acessar o controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="29aa6-168">Make sure that you have a working network connection, and that the device can reach the domain controller.</span></span> <span data-ttu-id="29aa6-169">Verifique se as credenciais da conta estão inseridas corretamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-169">Make sure the account credentials are entered correctly.</span></span> <span data-ttu-id="29aa6-170">Você também pode tentar usar o FQDN em vez disso.</span><span class="sxs-lookup"><span data-stu-id="29aa6-170">You can also try using the FQDN instead.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-171">Não é possível detectar automaticamente o servidor do Exchange.</span><span class="sxs-lookup"><span data-stu-id="29aa6-171">Can't auto-discover Exchange server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-172">O servidor do Exchange não está configurado para detecção automática.</span><span class="sxs-lookup"><span data-stu-id="29aa6-172">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-173">Habilite a detecção automática do servidor do Exchange para a conta do dispositivo, ou insira o endereço do servidor do Exchange da conta manualmente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-173">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-174">Não é possível descobrir o endereço SIP depois de inserir as credenciais da conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-174">Could not discover the SIP address after entering the account credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-175">Não havia nenhuma entrada de endereço SIP no Active Directory ou Azure AD.</span><span class="sxs-lookup"><span data-stu-id="29aa6-175">There was no SIP address entry in Active Directory or Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-176">Verifique se a conta está habilitada com o Skype for Business e que possui um endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="29aa6-176">Make sure the account is enabled with Skype for Business and has a SIP address.</span></span> <span data-ttu-id="29aa6-177">Caso contrário, você pode inserir o endereço SIP manualmente na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="29aa6-177">If not, you can enter the SIP address manually into the text box.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a name="device-account-page,-issues-for-existing-account-settings"></a><span data-ttu-id="29aa6-178">Página da conta do dispositivo, problemas de configurações de conta existente</span><span class="sxs-lookup"><span data-stu-id="29aa6-178">Device account page, issues for existing account settings</span></span>

<table>
<tr>
<th><span data-ttu-id="29aa6-179">Problema</span><span class="sxs-lookup"><span data-stu-id="29aa6-179">Issue</span></span></th>
<th><span data-ttu-id="29aa6-180">Causas</span><span class="sxs-lookup"><span data-stu-id="29aa6-180">Causes</span></span></th>
<th><span data-ttu-id="29aa6-181">Códigos de erro</span><span class="sxs-lookup"><span data-stu-id="29aa6-181">Error codes</span></span></th>
<th><span data-ttu-id="29aa6-182">Possíveis correções</span><span class="sxs-lookup"><span data-stu-id="29aa6-182">Possible fixes</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-183">A conta não pôde autenticar com as credenciais especificadas.</span><span class="sxs-lookup"><span data-stu-id="29aa6-183">Account could not authenticate with the specified credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-184">A conta não está habilitada como um usuário no Active Directory (AD), é preciso de uma senha para autenticar ou a senha está incorreta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-184">The account is not enabled as a user in Active Directory (AD), needs a password to authenticate, or the password is incorrect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-185">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="29aa6-185">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-186">Verifique se as credenciais estão inseridas corretamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-186">Make sure the credentials are entered correctly.</span></span> <span data-ttu-id="29aa6-187">Habilite a conta como um usuário no AD e adicione uma senha ou defina a RoomMailboxPassword</span><span class="sxs-lookup"><span data-stu-id="29aa6-187">Enable the account as a user in AD and add a password, or set the RoomMailboxPassword</span></span></p><span data-ttu-id="29aa6-188">.</span><span class="sxs-lookup"><span data-stu-id="29aa6-188">.</span></span> </td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-189">Erro 0x800C0019 é exibido ao fornecer um Exchange server.</span><span class="sxs-lookup"><span data-stu-id="29aa6-189">Error 0x800C0019 is displayed when providing an Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-190">A conta do dispositivo requer um certificado para autenticar.</span><span class="sxs-lookup"><span data-stu-id="29aa6-190">The device account requires a certificate to authenticate.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-191">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="29aa6-191">0x800C0019</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-192">Instale o certificado apropriado usando pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-192">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-193">As credenciais da conta do dispositivo não são válidas para o servidor do Exchange fornecido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-193">Device account credentials are not valid for the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-194">O servidor do Exchange fornecido não é onde a caixa de correio da conta do dispositivo está hospedada.</span><span class="sxs-lookup"><span data-stu-id="29aa6-194">The provided Exchange server is not where the device account's mailbox is hosted.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-195">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="29aa6-195">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-196">Verifique se você está fornecendo o servidor de email do Exchange correto para a conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29aa6-196">Make sure you are providing the correct Exchange mail server for the device account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-197">Tempo limite HTTP ao tentar acessar o servidor do Exchange.</span><span class="sxs-lookup"><span data-stu-id="29aa6-197">HTTP timeout while trying to reach Exchange server.</span></span></p>
</td>
<td></td>
<td>
<p><span data-ttu-id="29aa6-198">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="29aa6-198">0x80072EE2</span></span></p>
</td>
<td></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-199">Não foi possível localizar o servidor do Exchange fornecido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-199">Couldn't find the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-200">O servidor do Exchange fornecido não pôde ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-200">The Exchange server provided could not be found.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-201">Nenhum</span><span class="sxs-lookup"><span data-stu-id="29aa6-201">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-202">Verifique se você possui uma conexão com a Internet ou rede, e se o servidor do Exchange que você forneceu está correto.</span><span class="sxs-lookup"><span data-stu-id="29aa6-202">Ensure that you have a working network or Internet connection, and that the Exchange server you provided is correct.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-203">HTTP não suportado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-203">http not supported.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-204">Um servidor do Exchange com <i>http://</i>, em vez de <i>https://</i>, foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-204">An Exchange server with <i>http://</i> instead of <i>https://</i> was provided.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-205">Nenhum</span><span class="sxs-lookup"><span data-stu-id="29aa6-205">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-206">Utilize um servidor do Exchange que use https.</span><span class="sxs-lookup"><span data-stu-id="29aa6-206">Use an Exchange server that uses https.</span></span></p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p><span data-ttu-id="29aa6-207">As pessoas entram na página intitulada "Há um problema com esta conta" em relação ao ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="29aa6-207">People land on the page titled "There's a problem with this account" regarding ActiveSync.</span></span></p>
</div>
<div> </div>
</td>
<td>
<p><span data-ttu-id="29aa6-208">A política PasswordEnabled do ActiveSync está definida como True (ou 1).</span><span class="sxs-lookup"><span data-stu-id="29aa6-208">The ActiveSync policy PasswordEnabled is set to True (or 1).</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-209">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="29aa6-209">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-210">Crie uma nova política ActiveSync onde PasswordEnabled é definido como False (ou 0) e depois aplique essa política à conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-210">Create a new ActiveSync policy where PasswordEnabled is set to False (or 0), and then apply that policy to the account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-211">O Surface Hub não tem uma conexão com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="29aa6-211">The Surface Hub doesn't have a connection to Exchange.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-212">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="29aa6-212">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-213">Certifique-se que possui uma conexão com a Internet ou rede ativa.</span><span class="sxs-lookup"><span data-stu-id="29aa6-213">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="29aa6-214">Exchange retorna um código de status indicando um erro.</span><span class="sxs-lookup"><span data-stu-id="29aa6-214">Exchange returns a status code indicating an error.</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-215">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="29aa6-215">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="29aa6-216">Certifique-se que possui uma conexão com a Internet ou rede ativa.</span><span class="sxs-lookup"><span data-stu-id="29aa6-216">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a><span data-ttu-id="29aa6-217">Executado pela primeira vez, o Domínio é associado aos problemas da página</span><span class="sxs-lookup"><span data-stu-id="29aa6-217">First run, Domain join page issues</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="29aa6-218">Problema</span><span class="sxs-lookup"><span data-stu-id="29aa6-218">Issue</span></span></th>
<th align="left"><span data-ttu-id="29aa6-219">Causas</span><span class="sxs-lookup"><span data-stu-id="29aa6-219">Causes</span></span></th>
<th align="left"><span data-ttu-id="29aa6-220">Possíveis correções</span><span class="sxs-lookup"><span data-stu-id="29aa6-220">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-221">Ao tentar ingressar em um domínio, um erro mostra que a conta não pôde autenticar usando as credenciais especificadas.</span><span class="sxs-lookup"><span data-stu-id="29aa6-221">When trying to join a domain, an error shows that the account couldn't authenticate using the specified credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-222">As credenciais fornecidas não são capazes de ingressar no domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-222">The credentials provided are not capable of joining the specified domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-223">Insira credenciais corretas para uma conta que existe no domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-223">Enter correct credentials for an account that exists in the specified domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-224">Ao especificar um grupo de um domínio, um erro mostra que o grupo não pôde ser encontrado no domínio.</span><span class="sxs-lookup"><span data-stu-id="29aa6-224">When specifying a group from a domain, an error shows that the group couldn't be found on the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-225">O grupo pode ter sido removido ou não existe mais.</span><span class="sxs-lookup"><span data-stu-id="29aa6-225">The group may have been removed or no longer exists.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-226">Verifique se o grupo existe dentro do domínio.</span><span class="sxs-lookup"><span data-stu-id="29aa6-226">Verify that the group exists within the domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a name="first-run,-exchange-server-page"></a><span data-ttu-id="29aa6-227">Primeira execução, página do servidor do Exchange</span><span class="sxs-lookup"><span data-stu-id="29aa6-227">First run, Exchange server page</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="29aa6-228">Problema</span><span class="sxs-lookup"><span data-stu-id="29aa6-228">Issue</span></span></th>
<th align="left"><span data-ttu-id="29aa6-229">Causas</span><span class="sxs-lookup"><span data-stu-id="29aa6-229">Causes</span></span></th>
<th align="left"><span data-ttu-id="29aa6-230">Possíveis correções</span><span class="sxs-lookup"><span data-stu-id="29aa6-230">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-231">As pessoas entram nesta página e é solicitado que preencham o endereço do servidor do Exchange.</span><span class="sxs-lookup"><span data-stu-id="29aa6-231">People land on this page and are asked for the Exchange server address.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-232">O servidor do Exchange não está configurado para detecção automática.</span><span class="sxs-lookup"><span data-stu-id="29aa6-232">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-233">Habilite a detecção automática do servidor do Exchange para a conta do dispositivo, ou insira o endereço do servidor do Exchange da conta manualmente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-233">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a><span data-ttu-id="29aa6-234">Primeira execução, problemas no dispositivo</span><span class="sxs-lookup"><span data-stu-id="29aa6-234">First run, On-device issues</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="29aa6-235">Problema</span><span class="sxs-lookup"><span data-stu-id="29aa6-235">Issue</span></span></th>
<th align="left"><span data-ttu-id="29aa6-236">Causas</span><span class="sxs-lookup"><span data-stu-id="29aa6-236">Causes</span></span></th>
<th align="left"><span data-ttu-id="29aa6-237">Códigos de erro</span><span class="sxs-lookup"><span data-stu-id="29aa6-237">Error codes</span></span></th>
<th align="left"><span data-ttu-id="29aa6-238">Possíveis correções</span><span class="sxs-lookup"><span data-stu-id="29aa6-238">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-239">Não é possível sincronizar o calendário/email.</span><span class="sxs-lookup"><span data-stu-id="29aa6-239">Can't sync mail/calendar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-240">A conta não tem permissão do Surface Hub como um dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-240">The account has not allowed the Surface Hub as an allowed device.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-241">0x86000C1C</span><span class="sxs-lookup"><span data-stu-id="29aa6-241">0x86000C1C</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-242">Adicione a ID do dispositivo do Surface Hub à lista de permissões, definindo a <strong> </strong> Propriedade ActiveSyncAllowedDeviceIds para a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="29aa6-242">Add the Surface Hub device ID to the allowed list by setting the <strong>ActiveSyncAllowedDeviceIds</strong> property for the mailbox.</span></span></p></td>
</tr>
</tbody>
</table>

 



 

## <a name="exchange-activesync-errors"></a><span data-ttu-id="29aa6-243">Erros do Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="29aa6-243">Exchange ActiveSync errors</span></span>


<span data-ttu-id="29aa6-244">Esta seção lista códigos de status, mapeamento, mensagens de usuário e ações que um administrador pode executar para resolver erros do Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="29aa6-244">This section lists status codes, mapping, user messages, and actions an admin can take to solve Exchange ActiveSync errors.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="29aa6-245">Código hexadecimal</span><span class="sxs-lookup"><span data-stu-id="29aa6-245">Hex Code</span></span></th>
<th align="left"><span data-ttu-id="29aa6-246">Mapeamento</span><span class="sxs-lookup"><span data-stu-id="29aa6-246">Mapping</span></span></th>
<th align="left"><span data-ttu-id="29aa6-247">Mensagem amigável</span><span class="sxs-lookup"><span data-stu-id="29aa6-247">User-Friendly Message</span></span></th>
<th align="left"><span data-ttu-id="29aa6-248">Ações a serem executadas pelo administrador</span><span class="sxs-lookup"><span data-stu-id="29aa6-248">Action admin should take</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-249">0x85010002</span><span class="sxs-lookup"><span data-stu-id="29aa6-249">0x85010002</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-250">E_HTTP_DENIED</span><span class="sxs-lookup"><span data-stu-id="29aa6-250">E_HTTP_DENIED</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-251">A senha deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="29aa6-251">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-252">Atualize a senha.</span><span class="sxs-lookup"><span data-stu-id="29aa6-252">Update the password.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-253">0x80072EFD</span><span class="sxs-lookup"><span data-stu-id="29aa6-253">0x80072EFD</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-254">WININET_E_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="29aa6-254">WININET_E_CANNOT_CONNECT</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-255">Não é possível se conectar ao servidor no momento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-255">Can't connect to the server right now.</span></span> <span data-ttu-id="29aa6-256">Aguarde um pouco e tente novamente ou verifique as configurações da conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-256">Wait a while and try again, or check the account settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-257">Verifique se o nome do servidor está correto e acessível.</span><span class="sxs-lookup"><span data-stu-id="29aa6-257">Verify that the server name is correct and reachable.</span></span> <span data-ttu-id="29aa6-258">Verifique se o dispositivo está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="29aa6-258">Verify that the device is connected to the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-259">0x86000C29</span><span class="sxs-lookup"><span data-stu-id="29aa6-259">0x86000C29</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (as políticas não correspondem)</span><span class="sxs-lookup"><span data-stu-id="29aa6-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (policies don't match)</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-261">A conta está configurada com políticas não compatíveis com o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-261">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-262">Desabilite a política <strong>PasswordEnabled</strong> para essa conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-262">Disable the <strong>PasswordEnabled</strong> policy for this account.</span></span></p>
<p><span data-ttu-id="29aa6-263">Temos um bug que pode haver erros de política de superfície se a conta não receber notificações de servidor dentro do intervalo de atualização de política.</span><span class="sxs-lookup"><span data-stu-id="29aa6-263">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-264">0x86000C4C</span><span class="sxs-lookup"><span data-stu-id="29aa6-264">0x86000C4C</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span><span class="sxs-lookup"><span data-stu-id="29aa6-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-266">A conta tem muitas parcerias de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29aa6-266">The account has too many device partnerships.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-267">Exclua uma ou mais parcerias no servidor.</span><span class="sxs-lookup"><span data-stu-id="29aa6-267">Delete one or more partnerships on the server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-268">0x86000C0A</span><span class="sxs-lookup"><span data-stu-id="29aa6-268">0x86000C0A</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span><span class="sxs-lookup"><span data-stu-id="29aa6-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-270">Não é possível se conectar ao servidor no momento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-270">Can't connect to the server right now.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-271">Aguarde até que o servidor fique online novamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-271">Wait until the server comes back online.</span></span> <span data-ttu-id="29aa6-272">Se o problema persistir, provisione novamente a conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-272">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-273">0x85050003</span><span class="sxs-lookup"><span data-stu-id="29aa6-273">0x85050003</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-274">E_CREDENTIALS_EXPIRED (As credenciais expiraram e precisam ser atualizadas)</span><span class="sxs-lookup"><span data-stu-id="29aa6-274">E_CREDENTIALS_EXPIRED (Credentials have expired and need to be updated)</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-275">A senha deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="29aa6-275">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-276">Atualize a senha.</span><span class="sxs-lookup"><span data-stu-id="29aa6-276">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-277">0x8505000D</span><span class="sxs-lookup"><span data-stu-id="29aa6-277">0x8505000D</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-278">E_AIRSYNC_RESET_RETRY</span><span class="sxs-lookup"><span data-stu-id="29aa6-278">E_AIRSYNC_RESET_RETRY</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-279">Não é possível se conectar ao servidor no momento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-279">Can't connect to the server right now.</span></span> <span data-ttu-id="29aa6-280">Aguarde um momento ou verifique as configurações da conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-280">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-281">Isso normalmente é um erro temporário, mas, se o problema persistir, verifique a quantidade de dispositivos associados à conta e exclua alguns deles se o número for grande.</span><span class="sxs-lookup"><span data-stu-id="29aa6-281">This is normally a transient error but if the issue persists check the number of devices associated with the account and delete some of them if the number is large.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-282">0x86000C16</span><span class="sxs-lookup"><span data-stu-id="29aa6-282">0x86000C16</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span><span class="sxs-lookup"><span data-stu-id="29aa6-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-284">A caixa de correio foi migrada para um servidor diferente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-284">The mailbox was migrated to a different server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-285">Você nunca deve ver esse erro.</span><span class="sxs-lookup"><span data-stu-id="29aa6-285">You should never see this error.</span></span> <span data-ttu-id="29aa6-286">Se o problema persistir, provisione novamente a conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-286">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-287">0x85010004</span><span class="sxs-lookup"><span data-stu-id="29aa6-287">0x85010004</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-288">E_HTTP_FORBIDDEN</span><span class="sxs-lookup"><span data-stu-id="29aa6-288">E_HTTP_FORBIDDEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-289">Não é possível se conectar ao servidor no momento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-289">Can't connect to the server right now.</span></span> <span data-ttu-id="29aa6-290">Aguarde um momento e tente novamente ou verifique as configurações da conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-290">Wait a while and try again, or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-291">Verifique o nome do servidor para certificar se está correto.</span><span class="sxs-lookup"><span data-stu-id="29aa6-291">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="29aa6-292">Se a conta estiver usando autenticação baseada em certificado, verifique se o certificado ainda é válido e atualize-o se necessário.</span><span class="sxs-lookup"><span data-stu-id="29aa6-292">If the account is using cert based authentication make sure the certificate is still valid and update it if not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-293">0x85030028</span><span class="sxs-lookup"><span data-stu-id="29aa6-293">0x85030028</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span><span class="sxs-lookup"><span data-stu-id="29aa6-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-295">A senha da conta ou o certificado do cliente estão ausentes ou são inválidos.</span><span class="sxs-lookup"><span data-stu-id="29aa6-295">The account's password or client certificate are missing or invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-296">Atualize a senha e/ou implemente o certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-296">Update the password and/or deploy the client certificate.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-297">0x86000C2A</span><span class="sxs-lookup"><span data-stu-id="29aa6-297">0x86000C2A</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span><span class="sxs-lookup"><span data-stu-id="29aa6-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-299">A conta está configurada com políticas não compatíveis com o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-299">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-300">Desabilite a política PasswordEnabled para essa conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-300">Disable the PasswordEnabled policy for this account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-301">0x85050002</span><span class="sxs-lookup"><span data-stu-id="29aa6-301">0x85050002</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-302">E_CREDENTIALS_UNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29aa6-302">E_CREDENTIALS_UNAVAILABLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-303">A senha deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="29aa6-303">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-304">Atualize a senha.</span><span class="sxs-lookup"><span data-stu-id="29aa6-304">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-305">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="29aa6-305">0x80072EE2</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-306">WININET_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="29aa6-306">WININET_E_TIMEOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-307">A rede não é compatível com o tempo limite de ociosidade mínimo necessário para receber a notificação do servidor ou o servidor está offline.</span><span class="sxs-lookup"><span data-stu-id="29aa6-307">The network doesn't support the minimum idle timeout required to receive server notification, or the server is offline.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-308">Verifique se o servidor está em execução.</span><span class="sxs-lookup"><span data-stu-id="29aa6-308">Verify that the server is running.</span></span> <span data-ttu-id="29aa6-309">Verifique as configurações de NAT.</span><span class="sxs-lookup"><span data-stu-id="29aa6-309">Verify the NAT settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-310">0x85002004</span><span class="sxs-lookup"><span data-stu-id="29aa6-310">0x85002004</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-311">E_FAIL_ABORT</span><span class="sxs-lookup"><span data-stu-id="29aa6-311">E_FAIL_ABORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-312">Este erro é usado para interromper a sincronização deslocada e não será exposto aos usuários.</span><span class="sxs-lookup"><span data-stu-id="29aa6-312">This error is used to interrupt the hanging sync, and will not be exposed to users.</span></span> <span data-ttu-id="29aa6-313">Ele será mostrado nos dados de diagnóstico se você forçar uma sincronização interativa, excluir a conta ou atualizar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="29aa6-313">It will be shown in the diagnostic data if you force an interactive sync, delete the account, or update its settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-314">Nada.</span><span class="sxs-lookup"><span data-stu-id="29aa6-314">Nothing.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-315">0x85010017</span><span class="sxs-lookup"><span data-stu-id="29aa6-315">0x85010017</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-316">E_HTTP_SERVICE_UNAVAIL</span><span class="sxs-lookup"><span data-stu-id="29aa6-316">E_HTTP_SERVICE_UNAVAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-317">Não é possível se conectar ao servidor no momento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-317">Can't connect to the server right now.</span></span> <span data-ttu-id="29aa6-318">Aguarde um momento ou verifique as configurações da conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-318">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-319">Verifique o nome do servidor para certificar se está correto.</span><span class="sxs-lookup"><span data-stu-id="29aa6-319">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="29aa6-320">Aguarde até que o servidor fique online novamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-320">Wait until the server comes back online.</span></span> <span data-ttu-id="29aa6-321">Se o problema persistir, provisione novamente a conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-321">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-322">0x86000C0D</span><span class="sxs-lookup"><span data-stu-id="29aa6-322">0x86000C0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span><span class="sxs-lookup"><span data-stu-id="29aa6-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-324">Não é possível se conectar ao servidor no momento.</span><span class="sxs-lookup"><span data-stu-id="29aa6-324">Can't connect to the server right now.</span></span> <span data-ttu-id="29aa6-325">Aguarde um momento ou verifique as configurações da conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-325">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-326">Verifique o nome do servidor para certificar se está correto.</span><span class="sxs-lookup"><span data-stu-id="29aa6-326">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="29aa6-327">Aguarde até que o servidor fique online novamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-327">Wait until the server comes back online.</span></span> <span data-ttu-id="29aa6-328">Se o problema persistir, provisione novamente a conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-328">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-329">0x85030027</span><span class="sxs-lookup"><span data-stu-id="29aa6-329">0x85030027</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-330">E_ACTIVESYNC_GETCERT</span><span class="sxs-lookup"><span data-stu-id="29aa6-330">E_ACTIVESYNC_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-331">O servidor do Exchange requer um certificado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-331">The Exchange server requires a certificate.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-332">Importe o certificado EAS apropriado do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-332">Import the appropriate EAS certificate on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-333">0x86000C2B</span><span class="sxs-lookup"><span data-stu-id="29aa6-333">0x86000C2B</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span><span class="sxs-lookup"><span data-stu-id="29aa6-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-335">A conta está configurada com políticas não compatíveis com o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="29aa6-335">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-336">Desabilite a política PasswordEnabled para essa conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-336">Disable the PasswordEnabled policy for this account.</span></span></p>
<p><span data-ttu-id="29aa6-337">Temos um bug que pode haver erros de política de superfície se a conta não receber notificações de servidor dentro do intervalo de atualização de política.</span><span class="sxs-lookup"><span data-stu-id="29aa6-337">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-338">0x85010005</span><span class="sxs-lookup"><span data-stu-id="29aa6-338">0x85010005</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-339">E_HTTP_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="29aa6-339">E_HTTP_NOT_FOUND</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-340">O nome do servidor é inválido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-340">The server name is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-341">Verifique o nome do servidor para garantir que ele esteja correto.</span><span class="sxs-lookup"><span data-stu-id="29aa6-341">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="29aa6-342">Se o problema persistir, provisione novamente a conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-342">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-343">0x85010014</span><span class="sxs-lookup"><span data-stu-id="29aa6-343">0x85010014</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-344">E_HTTP_SERVER_ERROR</span><span class="sxs-lookup"><span data-stu-id="29aa6-344">E_HTTP_SERVER_ERROR</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-345">Não é possível se conectar ao servidor.</span><span class="sxs-lookup"><span data-stu-id="29aa6-345">Can't connect to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-346">Verifique o nome do servidor para garantir que ele esteja correto.</span><span class="sxs-lookup"><span data-stu-id="29aa6-346">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="29aa6-347">Acione uma sincronização e, se o problema persistir, provisione novamente a conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-347">Trigger a sync and, if the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-348">0x80072EE7</span><span class="sxs-lookup"><span data-stu-id="29aa6-348">0x80072EE7</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-349">WININET_E_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="29aa6-349">WININET_E_NAME_NOT_RESOLVED</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-350">O nome ou endereço do servidor não pôde ser resolvido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-350">The server name or address could not be resolved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-351">Verifique se o nome do servidor está inserido corretamente.</span><span class="sxs-lookup"><span data-stu-id="29aa6-351">Make sure the server name is entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-352">0x8007052F</span><span class="sxs-lookup"><span data-stu-id="29aa6-352">0x8007052F</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-353">ERROR_ACCOUNT_RESTRICTION</span><span class="sxs-lookup"><span data-stu-id="29aa6-353">ERROR_ACCOUNT_RESTRICTION</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-354">Durante a detecção automática do servidor do Exchange, é aplicada uma política que impede o usuário conectado de fazer logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="29aa6-354">While auto-discovering the Exchange server, a policy is applied that prevents the logged-in user from logging in to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-355">Este é um problema de tempo.</span><span class="sxs-lookup"><span data-stu-id="29aa6-355">This is a timing issue.</span></span> <span data-ttu-id="29aa6-356">Verifique novamente as credenciais da conta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-356">Re-verify the account's credentials.</span></span> <span data-ttu-id="29aa6-357">Tente provisionar novamente quando elas estiverem corretas.</span><span class="sxs-lookup"><span data-stu-id="29aa6-357">Try to re-provision when they're correct.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-358">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="29aa6-358">0x800C0019</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-359">INET_E_INVALID_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="29aa6-359">INET_E_INVALID_CERTIFICATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-360">O certificado de segurança necessário para acessar este recurso é inválido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-360">Security certificate required to access this resource is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-361">Instale o certificado do ActiveSync correto necessário para a conta do dispositivo fornecida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-361">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29aa6-362">0x80072F0D</span><span class="sxs-lookup"><span data-stu-id="29aa6-362">0x80072F0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-363">WININET_E_INVALID_CA</span><span class="sxs-lookup"><span data-stu-id="29aa6-363">WININET_E_INVALID_CA</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-364">A autoridade de certificação é inválida ou está incorreta.</span><span class="sxs-lookup"><span data-stu-id="29aa6-364">The certificate authority is invalid or is incorrect.</span></span> <span data-ttu-id="29aa6-365">Não é possível detectar automaticamente o servidor do Exchange porque um certificado não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="29aa6-365">Could not auto-discover the Exchange server because a certificate is missing.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-366">Instale o certificado do ActiveSync correto necessário para a conta do dispositivo fornecida.</span><span class="sxs-lookup"><span data-stu-id="29aa6-366">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29aa6-367">0x80004005</span><span class="sxs-lookup"><span data-stu-id="29aa6-367">0x80004005</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-368">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29aa6-368">E_FAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-369">Não foi possível localizar o domínio fornecido.</span><span class="sxs-lookup"><span data-stu-id="29aa6-369">The domain provided couldn't be found.</span></span> <span data-ttu-id="29aa6-370">O servidor do Exchange não pôde ser detectado automaticamente e não foi fornecido nas configurações.</span><span class="sxs-lookup"><span data-stu-id="29aa6-370">The Exchange server could not be auto-discovered and was not provided in the settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29aa6-371">Certifique-se de que o domínio digitado é o FQDN e de que há um servidor do Exchange inserido na caixa de texto do servidor do Exchange.</span><span class="sxs-lookup"><span data-stu-id="29aa6-371">Make sure that the domain entered is the FQDN, and that there is an Exchange server entered in the Exchange server text box.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="contact-support"></a><span data-ttu-id="29aa6-372">Contatar o Suporte</span><span class="sxs-lookup"><span data-stu-id="29aa6-372">Contact Support</span></span>

<span data-ttu-id="29aa6-373">Se tiver dúvidas ou precisar de ajuda, você pode [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="29aa6-373">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


 
## <a name="related-content"></a><span data-ttu-id="29aa6-374">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="29aa6-374">Related content</span></span>

- [<span data-ttu-id="29aa6-375">Solução de problemas de conexão do Miracast para o Surface Hub</span><span class="sxs-lookup"><span data-stu-id="29aa6-375">Troubleshooting Miracast connection to the Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 





