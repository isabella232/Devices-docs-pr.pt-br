---
title: Encerrar sessão - encerramento de uma reunião do Surface Hub
description: Para encerrar uma reunião do Surface Hub, toque em Encerrar sessão. O Surface Hub limpa o estado do aplicativo, o estado do sistema operacional e a interface do usuário para que o Surface Hub fique pronto para a próxima reunião.
keywords: Terminei, encerrar reunião do Surface Hub, concluir reunião do Surface Hub, limpar reunião do Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830661"
---
# <span data-ttu-id="9787d-105">Encerrar uma reunião do Surface Hub com Encerrar sessão</span><span class="sxs-lookup"><span data-stu-id="9787d-105">End a Surface Hub meeting with End session</span></span>
<span data-ttu-id="9787d-106">O Surface Hub é um dispositivo de colaboração projetado para ser usado em espaços de reunião por grupos de pessoas diferentes.</span><span class="sxs-lookup"><span data-stu-id="9787d-106">Surface Hub is a collaboration device designed to be used in meeting spaces by different groups of people.</span></span> <span data-ttu-id="9787d-107">No final de uma reunião, os usuários podem tocar em **Encerrar sessão** para apagar dados confidenciais e preparar o dispositivo para a próxima reunião.</span><span class="sxs-lookup"><span data-stu-id="9787d-107">At the end of a meeting, users can tap **End session** to clean up any sensitive data and prepare the device for the next meeting.</span></span> <span data-ttu-id="9787d-108">O Surface Hub limpará ou redefinirá os seguintes estados:</span><span class="sxs-lookup"><span data-stu-id="9787d-108">Surface Hub will clean up, or reset, the following states:</span></span>
- <span data-ttu-id="9787d-109">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="9787d-109">Applications</span></span>
- <span data-ttu-id="9787d-110">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9787d-110">Operating system</span></span>
- <span data-ttu-id="9787d-111">Interface do usuário</span><span class="sxs-lookup"><span data-stu-id="9787d-111">User interface</span></span>

<span data-ttu-id="9787d-112">Este tópico explica o que **Encerrar sessão** redefine para cada um destes estados.</span><span class="sxs-lookup"><span data-stu-id="9787d-112">This topic explains what **End session** resets for each of these states.</span></span>

## <span data-ttu-id="9787d-113">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="9787d-113">Applications</span></span>
<span data-ttu-id="9787d-114">Quando você inicia aplicativos no Surface Hub, eles são armazenados na memória, e os dados são armazenados no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9787d-114">When you start apps on Surface Hub, they are stored in memory and data is stored at the application level.</span></span> <span data-ttu-id="9787d-115">Os dados ficam disponíveis para todos os usuários durante aquela sessão (ou reunião) até que a data seja removida ou substituída.</span><span class="sxs-lookup"><span data-stu-id="9787d-115">Data is available to all users during that session (or meeting) until date is removed or overwritten.</span></span> <span data-ttu-id="9787d-116">Quando **Encerrar sessão** é selecionado, o estado do aplicativo do Surface Hub é limpo pelo fechamento de aplicativos, exclusão do histórico do navegador, redefinição de aplicativos e remoção de registros do Skype.</span><span class="sxs-lookup"><span data-stu-id="9787d-116">When **End session** is selected, Surface Hub application state is cleared out by closing applications, deleting browser history, resetting applications, and removing Skype logs.</span></span>

### <span data-ttu-id="9787d-117">Fechar aplicativos</span><span class="sxs-lookup"><span data-stu-id="9787d-117">Close applications</span></span>
<span data-ttu-id="9787d-118">O Surface Hub fecha todas as janelas visíveis, incluindo aplicativos Win32 e Plataforma Universal do Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="9787d-118">Surface Hub closes all visible windows, including Win32 and Universal Windows Platform (UWP) applications.</span></span> <span data-ttu-id="9787d-119">O estágio de fechamento de aplicativos usa o modo de exibição multitarefa para consultar as janelas visíveis.</span><span class="sxs-lookup"><span data-stu-id="9787d-119">The application close stage uses the multitasking view to query the visible windows.</span></span> <span data-ttu-id="9787d-120">Janelas do Win32 que não fecharem dentro de um determinado período serão fechadas usando o **TerminateProcess**.</span><span class="sxs-lookup"><span data-stu-id="9787d-120">Win32 windows that do not close within a certain timeframe are closed using **TerminateProcess**.</span></span> 
   
### <span data-ttu-id="9787d-121">Apagar histórico do navegador</span><span class="sxs-lookup"><span data-stu-id="9787d-121">Delete browser history</span></span>
<span data-ttu-id="9787d-122">O Surface Hub usa o recurso Excluir histórico do navegador (DBH) na Borda para limpar o histórico da Borda e dados em cache.</span><span class="sxs-lookup"><span data-stu-id="9787d-122">Surface Hub uses Delete Browser History (DBH) in Edge to clear Edge history and cached data.</span></span> <span data-ttu-id="9787d-123">Isso se assemelha a como um usuário pode limpar o histórico do navegador manualmente, mas **Encerrar sessão** também limpa os estados do aplicativo, e os dados são removidos antes do início da próxima sessão ou reunião.</span><span class="sxs-lookup"><span data-stu-id="9787d-123">This is similar to how a user can clear out their browser history manually, but **End session** also ensures that application states are cleared and data is removed before the next session, or meeting, starts.</span></span> 
 
### <span data-ttu-id="9787d-124">Redefinir aplicativos</span><span class="sxs-lookup"><span data-stu-id="9787d-124">Reset applications</span></span>
<span data-ttu-id="9787d-125">**Encerrar sessão** redefine o estado de cada aplicativo que é instalado no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9787d-125">**End session** resets the state of each application that is installed on the Surface Hub.</span></span> <span data-ttu-id="9787d-126">A redefinição de um aplicativo limpa todas as tarefas em segundo plano, dados de aplicativos, notificações e caixas de diálogo de consentimento do usuário.</span><span class="sxs-lookup"><span data-stu-id="9787d-126">Resetting an application clears all background tasks, application data, notifications, and user consent dialogs.</span></span> <span data-ttu-id="9787d-127">Os aplicativos voltam ao estado da primeira execução para as próximas pessoas que usarem o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9787d-127">Applications are returned to their first-run state for the next people that use Surface Hub.</span></span>  
 
### <span data-ttu-id="9787d-128">Remover registros do Skype</span><span class="sxs-lookup"><span data-stu-id="9787d-128">Remove Skype logs</span></span>
<span data-ttu-id="9787d-129">O Skype não armazena informações de identificação pessoal no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9787d-129">Skype does not store personally-identifiable information on Surface Hub.</span></span> <span data-ttu-id="9787d-130">As informações são armazenadas no serviço Skype para atender às orientações existentes do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9787d-130">Information is stored in the Skype service to meet existing Skype for Business guidance.</span></span> <span data-ttu-id="9787d-131">As informações de registro do Skype locais são os únicos dados removidos quando **Encerrar sessão** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="9787d-131">Local Skype logging information is the only data removed when **End session** is selected.</span></span> <span data-ttu-id="9787d-132">Isso inclui os registros da plataforma de clientes de comunicações unificada (UCCP) e de mídia.</span><span class="sxs-lookup"><span data-stu-id="9787d-132">This includes Unified Communications Client Platform (UCCP) logs and media logs.</span></span>   

## <span data-ttu-id="9787d-133">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9787d-133">Operating System</span></span>
<span data-ttu-id="9787d-134">O sistema operacional hospeda uma variedade de informações sobre o estado das sessões que precisa ser limpo após cada reunião no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9787d-134">The operating system hosts a variety of information about the state of the sessions that needs to be cleared after each Surface Hub meeting.</span></span> 

### <span data-ttu-id="9787d-135">Sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="9787d-135">File System</span></span>
<span data-ttu-id="9787d-136">Os participantes da reunião têm acesso a um conjunto limitado de diretórios no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9787d-136">Meeting attendees have access to a limited set of directories on the Surface Hub.</span></span> <span data-ttu-id="9787d-137">Quando **Encerrar sessão** é selecionado, o Surface Hub limpa estes diretórios:</span><span class="sxs-lookup"><span data-stu-id="9787d-137">When **End session** is selected, Surface Hub clears these directories:</span></span><br>
- <span data-ttu-id="9787d-138">Música</span><span class="sxs-lookup"><span data-stu-id="9787d-138">Music</span></span>
- <span data-ttu-id="9787d-139">Vídeos</span><span class="sxs-lookup"><span data-stu-id="9787d-139">Videos</span></span>
- <span data-ttu-id="9787d-140">Documentos</span><span class="sxs-lookup"><span data-stu-id="9787d-140">Documents</span></span>
- <span data-ttu-id="9787d-141">Imagens</span><span class="sxs-lookup"><span data-stu-id="9787d-141">Pictures</span></span>
- <span data-ttu-id="9787d-142">Downloads</span><span class="sxs-lookup"><span data-stu-id="9787d-142">Downloads</span></span>

<span data-ttu-id="9787d-143">O Surface Hub também limpa esses diretórios, já que muitos aplicativos costumam escrever para eles:</span><span class="sxs-lookup"><span data-stu-id="9787d-143">Surface Hub also clears these directories, since many applications often write to them:</span></span>
- <span data-ttu-id="9787d-144">Área de trabalho</span><span class="sxs-lookup"><span data-stu-id="9787d-144">Desktop</span></span>
- <span data-ttu-id="9787d-145">Favoritos</span><span class="sxs-lookup"><span data-stu-id="9787d-145">Favorites</span></span>
- <span data-ttu-id="9787d-146">Recentes</span><span class="sxs-lookup"><span data-stu-id="9787d-146">Recent</span></span>
- <span data-ttu-id="9787d-147">Documentos Públicos</span><span class="sxs-lookup"><span data-stu-id="9787d-147">Public Documents</span></span>
- <span data-ttu-id="9787d-148">Músicas Públicas</span><span class="sxs-lookup"><span data-stu-id="9787d-148">Public Music</span></span>
- <span data-ttu-id="9787d-149">Vídeos Públicos</span><span class="sxs-lookup"><span data-stu-id="9787d-149">Public Videos</span></span>
- <span data-ttu-id="9787d-150">Downloads Públicos</span><span class="sxs-lookup"><span data-stu-id="9787d-150">Public Downloads</span></span>

### <span data-ttu-id="9787d-151">Credenciais</span><span class="sxs-lookup"><span data-stu-id="9787d-151">Credentials</span></span>
<span data-ttu-id="9787d-152">As credenciais de usuário que são armazenadas em **TokenBroker**, **PasswordVault** ou **Gerenciador de Credenciais** são apagadas quando você toca em **Encerrar sessão**.</span><span class="sxs-lookup"><span data-stu-id="9787d-152">User credentials that are stored in **TokenBroker**, **PasswordVault**, or **Credential Manager** are cleared when you tap **End session**.</span></span>

## <span data-ttu-id="9787d-153">Interface do usuário</span><span class="sxs-lookup"><span data-stu-id="9787d-153">User interface</span></span>
<span data-ttu-id="9787d-154">Os ajustes da interface do usuário (IU) voltam aos valores padrão quando **Encerrar sessão** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="9787d-154">User interface (UI) settings are returned to their default values when **End session** is selected.</span></span> 

### <span data-ttu-id="9787d-155">Itens de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="9787d-155">UI items</span></span>
- <span data-ttu-id="9787d-156">Redefinir Ações rápidas para o estado padrão</span><span class="sxs-lookup"><span data-stu-id="9787d-156">Reset Quick Actions to default state</span></span>
- <span data-ttu-id="9787d-157">Limpar Notificações do sistema</span><span class="sxs-lookup"><span data-stu-id="9787d-157">Clear Toast notifications</span></span>
- <span data-ttu-id="9787d-158">Redefinir níveis de volume</span><span class="sxs-lookup"><span data-stu-id="9787d-158">Reset volume levels</span></span>
- <span data-ttu-id="9787d-159">Redefinir a largura da barra lateral</span><span class="sxs-lookup"><span data-stu-id="9787d-159">Reset sidebar width</span></span>
- <span data-ttu-id="9787d-160">Redefinir o layout do modo tablet</span><span class="sxs-lookup"><span data-stu-id="9787d-160">Reset tablet mode layout</span></span>
- <span data-ttu-id="9787d-161">Como fazer o usuário sair de reuniões e de arquivos do Office 365</span><span class="sxs-lookup"><span data-stu-id="9787d-161">Sign user out of Office 365 meetings and files</span></span>

### <span data-ttu-id="9787d-162">Acessibilidade</span><span class="sxs-lookup"><span data-stu-id="9787d-162">Accessibility</span></span>
<span data-ttu-id="9787d-163">Aplicativos e recursos de acessibilidade retornam aos ajustes padrão quando **Encerrar sessão** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="9787d-163">Accessibility features and apps are returned to default settings when **End session** is selected.</span></span>
- <span data-ttu-id="9787d-164">Teclas de filtragem</span><span class="sxs-lookup"><span data-stu-id="9787d-164">Filter keys</span></span>
- <span data-ttu-id="9787d-165">Alto contraste</span><span class="sxs-lookup"><span data-stu-id="9787d-165">High contrast</span></span>
- <span data-ttu-id="9787d-166">Teclas de aderência</span><span class="sxs-lookup"><span data-stu-id="9787d-166">Sticky keys</span></span>
- <span data-ttu-id="9787d-167">Teclas de alternância</span><span class="sxs-lookup"><span data-stu-id="9787d-167">Toggle keys</span></span>
- <span data-ttu-id="9787d-168">Teclas do mouse</span><span class="sxs-lookup"><span data-stu-id="9787d-168">Mouse keys</span></span>
- <span data-ttu-id="9787d-169">Lupa</span><span class="sxs-lookup"><span data-stu-id="9787d-169">Magnifier</span></span>
- <span data-ttu-id="9787d-170">Narrador</span><span class="sxs-lookup"><span data-stu-id="9787d-170">Narrator</span></span>

### <span data-ttu-id="9787d-171">Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="9787d-171">Clipboard</span></span>
<span data-ttu-id="9787d-172">A área de transferência é limpa para remover dados que foram copiados para a área de transferência durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="9787d-172">The clipboard is cleared to remove data that was copied to the clipboard during the session.</span></span> 

## <span data-ttu-id="9787d-173">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="9787d-173">Frequently asked questions</span></span>
**<span data-ttu-id="9787d-174">O que acontece se eu esquecer de tocar em Encerrar sessão no final de uma reunião e outra pessoa usar o Surface Hub depois?</span><span class="sxs-lookup"><span data-stu-id="9787d-174">What happens if I forget to tap End session at the end of a meeting, and someone else uses the Surface Hub later?</span></span>**<br>
<span data-ttu-id="9787d-175">O Surface Hub apaga o conteúdo da reunião somente quando os usuários tocam em **Encerrar sessão**.</span><span class="sxs-lookup"><span data-stu-id="9787d-175">Surface Hub only cleans up meeting content when users tap **End session**.</span></span> <span data-ttu-id="9787d-176">Se você sair da reunião sem tocar em **Encerrar sessão**, o dispositivo retornará à tela de boas-vindas após algum tempo.</span><span class="sxs-lookup"><span data-stu-id="9787d-176">If you leave the meeting without tapping **End session**, the device will return to the welcome screen after some time.</span></span> <span data-ttu-id="9787d-177">Na tela de boas-vindas, os usuários terão a opção de continuar a sessão anterior ou iniciar uma nova.</span><span class="sxs-lookup"><span data-stu-id="9787d-177">From the welcome screen, users have the option to resume the previous session or start a new one.</span></span> <span data-ttu-id="9787d-178">Você também pode desabilitar a capacidade de retomar uma sessão se **Encerrar sessão** não for pressionado.</span><span class="sxs-lookup"><span data-stu-id="9787d-178">You can also disable the ability to resume a session if **End session** is not pressed.</span></span>

**<span data-ttu-id="9787d-179">Os documentos podem ser recuperados?</span><span class="sxs-lookup"><span data-stu-id="9787d-179">Are documents recoverable?</span></span>**<br> <span data-ttu-id="9787d-180">A remoção de arquivos do disco rígido com a seleção do **Encerrar sessão** é exatamente igual a qualquer outra exclusão de arquivos da unidade de disco rígido.</span><span class="sxs-lookup"><span data-stu-id="9787d-180">Removing files from the hard drive when **End session** is selected is just like any other file deletion from a hard disk drive.</span></span> <span data-ttu-id="9787d-181">Softwares de terceiros talvez possam recuperar dados da unidade de disco rígido, mas a recuperação de arquivos não é um recurso com suporte no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9787d-181">Third-party software might be able to recover data from the hard disk drive, but file recovery is not a supported feature on Surface Hub.</span></span> <span data-ttu-id="9787d-182">Para evitar a perda de dados, salve sempre os dados necessários antes de sair de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="9787d-182">To prevent data loss, always save the data you need before leaving a meeting.</span></span>

**<span data-ttu-id="9787d-183">As ações de limpeza da opção Encerrar sessão estão em conformidade com o padrão de limpeza e remoção do Departamento de Defesa dos EUA: DoD 5220.22-M?</span><span class="sxs-lookup"><span data-stu-id="9787d-183">Do the clean-up actions from End session comply with the US Department of Defense clearing and sanitizing standard: DoD 5220.22-M?</span></span>**<br>
<span data-ttu-id="9787d-184">Não.</span><span class="sxs-lookup"><span data-stu-id="9787d-184">No.</span></span> <span data-ttu-id="9787d-185">Atualmente, as ações de limpeza de **Encerrar sessão** não são compatíveis com esse padrão.</span><span class="sxs-lookup"><span data-stu-id="9787d-185">Currently, the clean-up actions from **End session** do not comply with this standard.</span></span>  
  
