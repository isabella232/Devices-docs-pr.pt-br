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
# <span data-ttu-id="9a7ee-104">Usando um sistema de controle de sala (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="9a7ee-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="9a7ee-105">Sistemas de controle de sala podem ser usados com o Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="9a7ee-106">Usar um sistema de controle de sala com o Surface Hub envolve conectar o hardware de controle de sala ao Surface Hub, geralmente por meio da porta serial RJ11 na parte inferior do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <a name="terminal-settings"></a><span data-ttu-id="9a7ee-107">Configurações de terminal</span><span class="sxs-lookup"><span data-stu-id="9a7ee-107">Terminal settings</span></span>

<span data-ttu-id="9a7ee-108">Para se conectar a um painel de controle de sistema de controle de sala, não é necessário definir nenhuma configuração de terminal do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="9a7ee-109">Se deseja conectar um computador ou laptop ao Surface Hub e enviar comandos seriais a partir do Surface Hub, você pode usar um programa emulador de terminal como Tera Term ou PuTTY.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="9a7ee-110">Configuração</span><span class="sxs-lookup"><span data-stu-id="9a7ee-110">Setting</span></span> | <span data-ttu-id="9a7ee-111">Valor</span><span class="sxs-lookup"><span data-stu-id="9a7ee-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="9a7ee-112">Taxa de transmissão</span><span class="sxs-lookup"><span data-stu-id="9a7ee-112">Baud rate</span></span> | <span data-ttu-id="9a7ee-113">115200</span><span class="sxs-lookup"><span data-stu-id="9a7ee-113">115200</span></span> |
| <span data-ttu-id="9a7ee-114">Bits de dados</span><span class="sxs-lookup"><span data-stu-id="9a7ee-114">Data bits</span></span> | <span data-ttu-id="9a7ee-115">08</span><span class="sxs-lookup"><span data-stu-id="9a7ee-115">8</span></span> | 
| <span data-ttu-id="9a7ee-116">Bits de parada</span><span class="sxs-lookup"><span data-stu-id="9a7ee-116">Stop bits</span></span> | <span data-ttu-id="9a7ee-117">um</span><span class="sxs-lookup"><span data-stu-id="9a7ee-117">1</span></span> |
| <span data-ttu-id="9a7ee-118">Paridade</span><span class="sxs-lookup"><span data-stu-id="9a7ee-118">Parity</span></span> | <span data-ttu-id="9a7ee-119">nenhuma</span><span class="sxs-lookup"><span data-stu-id="9a7ee-119">none</span></span> |
| <span data-ttu-id="9a7ee-120">Controle de fluxo</span><span class="sxs-lookup"><span data-stu-id="9a7ee-120">Flow control</span></span> | <span data-ttu-id="9a7ee-121">nenhuma</span><span class="sxs-lookup"><span data-stu-id="9a7ee-121">none</span></span> |
| <span data-ttu-id="9a7ee-122">Alimentação de linha</span><span class="sxs-lookup"><span data-stu-id="9a7ee-122">Line feed</span></span> | <span data-ttu-id="9a7ee-123">retorno de cada carro</span><span class="sxs-lookup"><span data-stu-id="9a7ee-123">every carriage return</span></span> |
 

## <a name="wiring-diagram"></a><span data-ttu-id="9a7ee-124">Diagrama de conexão</span><span class="sxs-lookup"><span data-stu-id="9a7ee-124">Wiring diagram</span></span>

<span data-ttu-id="9a7ee-125">Você pode usar um conector RJ-11 (6P6C) padrão para conectar a porta serial do Surface Hub a um sistema de controle de sala.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="9a7ee-126">Este é o método recomendado.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-126">This is the recommended method.</span></span> <span data-ttu-id="9a7ee-127">Você também pode usar um cabo de 4 condutores RJ-11, mas não recomendamos esse método.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="9a7ee-128">Este diagrama mostra a saída de pinos correta usada para um cabo RJ-11 (6P6C) para DB9.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![Imagem mostrando o diagrama de conexão.](images/room-control-wiring-diagram.png)

## <a name="command-sets"></a><span data-ttu-id="9a7ee-130">Conjuntos de comando</span><span class="sxs-lookup"><span data-stu-id="9a7ee-130">Command sets</span></span>

<span data-ttu-id="9a7ee-131">Os sistemas de controle de sala usam cenários comuns de sala de reuniões para comandos.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="9a7ee-132">Os comandos são originados do sistema de controle de sala e transmitidos por uma conexão serial para um Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="9a7ee-133">Os comandos são baseados em ASCII e o Surface Hub confirmará quando ocorrem alterações de estado.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="9a7ee-134">Os seguintes modificadores de comando estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-134">The following command modifiers are available.</span></span> <span data-ttu-id="9a7ee-135">Os comandos terminam com um caractere de nova linha (\n).</span><span class="sxs-lookup"><span data-stu-id="9a7ee-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="9a7ee-136">As respostas podem vir a qualquer momento em resposta a alterações de estado não disparadas diretamente por um comando de porta de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="9a7ee-137">Modificador</span><span class="sxs-lookup"><span data-stu-id="9a7ee-137">Modifier</span></span> | <span data-ttu-id="9a7ee-138">Resultado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="9a7ee-139">Incrementar um valor</span><span class="sxs-lookup"><span data-stu-id="9a7ee-139">Increment a value</span></span> |
| - | <span data-ttu-id="9a7ee-140">Diminuir um valor</span><span class="sxs-lookup"><span data-stu-id="9a7ee-140">Decrease a value</span></span> |
| = | <span data-ttu-id="9a7ee-141">Definir um valor distinto</span><span class="sxs-lookup"><span data-stu-id="9a7ee-141">Set a discrete value</span></span> |
| <span data-ttu-id="9a7ee-142">?</span><span class="sxs-lookup"><span data-stu-id="9a7ee-142">?</span></span> | <span data-ttu-id="9a7ee-143">Consultas para um valor atual</span><span class="sxs-lookup"><span data-stu-id="9a7ee-143">Queries for a current value</span></span> |
 

## <a name="power"></a><span data-ttu-id="9a7ee-144">Ligar/Desligar</span><span class="sxs-lookup"><span data-stu-id="9a7ee-144">Power</span></span>

<span data-ttu-id="9a7ee-145">O Surface Hub pode estar em um destes estados de energia.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="9a7ee-146">Estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-146">State</span></span> | <span data-ttu-id="9a7ee-147">Estado Energy Star</span><span class="sxs-lookup"><span data-stu-id="9a7ee-147">Energy Star state</span></span>| <span data-ttu-id="9a7ee-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="9a7ee-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9a7ee-149">0</span><span class="sxs-lookup"><span data-stu-id="9a7ee-149">0</span></span> | <span data-ttu-id="9a7ee-150">S5</span><span class="sxs-lookup"><span data-stu-id="9a7ee-150">S5</span></span> | <span data-ttu-id="9a7ee-151">Desativado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-151">Off</span></span> |
| <span data-ttu-id="9a7ee-152">um</span><span class="sxs-lookup"><span data-stu-id="9a7ee-152">1</span></span> | - | <span data-ttu-id="9a7ee-153">Ligado (indeterminado)</span><span class="sxs-lookup"><span data-stu-id="9a7ee-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="9a7ee-154">2</span><span class="sxs-lookup"><span data-stu-id="9a7ee-154">2</span></span> | <span data-ttu-id="9a7ee-155">S3</span><span class="sxs-lookup"><span data-stu-id="9a7ee-155">S3</span></span> | <span data-ttu-id="9a7ee-156">Suspensão</span><span class="sxs-lookup"><span data-stu-id="9a7ee-156">Sleep</span></span> |
| <span data-ttu-id="9a7ee-157">5</span><span class="sxs-lookup"><span data-stu-id="9a7ee-157">5</span></span> | <span data-ttu-id="9a7ee-158">S0</span><span class="sxs-lookup"><span data-stu-id="9a7ee-158">S0</span></span> | <span data-ttu-id="9a7ee-159">Pronto</span><span class="sxs-lookup"><span data-stu-id="9a7ee-159">Ready</span></span> |


<span data-ttu-id="9a7ee-160">No modo de substituição de computador, os estados de energia serão somente Pronto e Desativado e somente alteram a tela.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="9a7ee-161">A porta de gerenciamento não pode ser usada para ligar o computador de substituição.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="9a7ee-162">Estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-162">State</span></span> | <span data-ttu-id="9a7ee-163">Estado Energy Star</span><span class="sxs-lookup"><span data-stu-id="9a7ee-163">Energy Star state</span></span>| <span data-ttu-id="9a7ee-164">Descrição</span><span class="sxs-lookup"><span data-stu-id="9a7ee-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9a7ee-165">0</span><span class="sxs-lookup"><span data-stu-id="9a7ee-165">0</span></span> | <span data-ttu-id="9a7ee-166">S5</span><span class="sxs-lookup"><span data-stu-id="9a7ee-166">S5</span></span> | <span data-ttu-id="9a7ee-167">Desativado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-167">Off</span></span> |
| <span data-ttu-id="9a7ee-168">5</span><span class="sxs-lookup"><span data-stu-id="9a7ee-168">5</span></span> | <span data-ttu-id="9a7ee-169">S0</span><span class="sxs-lookup"><span data-stu-id="9a7ee-169">S0</span></span> | <span data-ttu-id="9a7ee-170">Pronto</span><span class="sxs-lookup"><span data-stu-id="9a7ee-170">Ready</span></span> |

<span data-ttu-id="9a7ee-171">Para um dispositivo de controle, algo diferente de 5/Pronto deve ser considerado Desativado.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="9a7ee-172">Cada comando Powerize resulta em duas alterações de estado e respostas.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="9a7ee-173">Comando</span><span class="sxs-lookup"><span data-stu-id="9a7ee-173">Command</span></span> | <span data-ttu-id="9a7ee-174">Mudança de estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-174">State change</span></span>| <span data-ttu-id="9a7ee-175">Resposta</span><span class="sxs-lookup"><span data-stu-id="9a7ee-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9a7ee-176">PowerOn</span><span class="sxs-lookup"><span data-stu-id="9a7ee-176">PowerOn</span></span> | <span data-ttu-id="9a7ee-177">Dispositivo é ativado (tela + computador).</span><span class="sxs-lookup"><span data-stu-id="9a7ee-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="9a7ee-178">O serviço de computador notifica o SMC que o computador está pronto.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="9a7ee-179">Power=0</span><span class="sxs-lookup"><span data-stu-id="9a7ee-179">Power=0</span></span></br></br><span data-ttu-id="9a7ee-180">Power=5</span><span class="sxs-lookup"><span data-stu-id="9a7ee-180">Power=5</span></span> |
| <span data-ttu-id="9a7ee-181">PowerOff</span><span class="sxs-lookup"><span data-stu-id="9a7ee-181">PowerOff</span></span> | <span data-ttu-id="9a7ee-182">O dispositivo faz a transição para o estado de ambiente (computador ativado, tela esmaecida).</span><span class="sxs-lookup"><span data-stu-id="9a7ee-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="9a7ee-183">Power=0</span><span class="sxs-lookup"><span data-stu-id="9a7ee-183">Power=0</span></span> |
| <span data-ttu-id="9a7ee-184">Power?</span><span class="sxs-lookup"><span data-stu-id="9a7ee-184">Power?</span></span> |  <span data-ttu-id="9a7ee-185">O SMC relata o último estado de energia.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="9a7ee-186">Power=<#></span><span class="sxs-lookup"><span data-stu-id="9a7ee-186">Power=<#></span></span> |



## <a name="brightness"></a><span data-ttu-id="9a7ee-187">Brilho</span><span class="sxs-lookup"><span data-stu-id="9a7ee-187">Brightness</span></span>

<span data-ttu-id="9a7ee-188">O nível de brilho atual tem um intervalo de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="9a7ee-189">Alterações em níveis de brilho podem ser enviadas por um sistema de controle de sala ou outro sistema.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="9a7ee-190">Comando</span><span class="sxs-lookup"><span data-stu-id="9a7ee-190">Command</span></span> | <span data-ttu-id="9a7ee-191">Mudança de estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-191">State change</span></span> |<span data-ttu-id="9a7ee-192">Resposta</span><span class="sxs-lookup"><span data-stu-id="9a7ee-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9a7ee-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="9a7ee-193">Brightness+</span></span> | <span data-ttu-id="9a7ee-194">O controlador de gerenciamento do sistema (SMC) envia o comando de aumento de brilho.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="9a7ee-195">O serviço de computador no sistema de controle de sala notifica o SMC sobre o novo nível de brilho.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="9a7ee-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="9a7ee-196">Brightness = 51</span></span> |
| <span data-ttu-id="9a7ee-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="9a7ee-197">Brightness-</span></span> |  <span data-ttu-id="9a7ee-198">O SMC envia o comando de diminuição de brilho.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="9a7ee-199">O serviço de computador notifica o SMC sobre o novo nível de brilho.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="9a7ee-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="9a7ee-200">Brightness = 50</span></span> |

## <a name="volume"></a><span data-ttu-id="9a7ee-201">Volume</span><span class="sxs-lookup"><span data-stu-id="9a7ee-201">Volume</span></span>

<span data-ttu-id="9a7ee-202">O nível de volume atual é um intervalo de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="9a7ee-203">Alterações em níveis de volume podem ser enviadas por um sistema de controle de sala ou outro sistema.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="9a7ee-204">O comando de Volume controla somente o volume no modo incorporado ou computador substituto, não de [Fontes convidadas](connect-and-display-with-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="9a7ee-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="9a7ee-205">Comando</span><span class="sxs-lookup"><span data-stu-id="9a7ee-205">Command</span></span> | <span data-ttu-id="9a7ee-206">Mudança de estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-206">State change</span></span> | <span data-ttu-id="9a7ee-207">Resposta</span><span class="sxs-lookup"><span data-stu-id="9a7ee-207">Response</span></span></br><span data-ttu-id="9a7ee-208">(No [modo Computador substituto](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span><span class="sxs-lookup"><span data-stu-id="9a7ee-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9a7ee-209">Volume+</span><span class="sxs-lookup"><span data-stu-id="9a7ee-209">Volume+</span></span> |  <span data-ttu-id="9a7ee-210">O SMC envia o comando de aumentar volume.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="9a7ee-211">O serviço de computador notifica o SMC sobre o novo nível de volume.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="9a7ee-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="9a7ee-212">Volume = 51</span></span> |
| <span data-ttu-id="9a7ee-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="9a7ee-213">Volume-</span></span> |  <span data-ttu-id="9a7ee-214">O SMC envia o comando de diminuir volume.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="9a7ee-215">O serviço de computador notifica o SMC sobre o novo nível de volume.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="9a7ee-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="9a7ee-216">Volume = 50</span></span> |


 

## <a name="mute-for-audio"></a><span data-ttu-id="9a7ee-217">Silenciar para áudio</span><span class="sxs-lookup"><span data-stu-id="9a7ee-217">Mute for audio</span></span>

<span data-ttu-id="9a7ee-218">O áudio pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-218">Audio can be muted.</span></span>

| <span data-ttu-id="9a7ee-219">Comando</span><span class="sxs-lookup"><span data-stu-id="9a7ee-219">Command</span></span> | <span data-ttu-id="9a7ee-220">Mudança de estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-220">State change</span></span> | <span data-ttu-id="9a7ee-221">Resposta</span><span class="sxs-lookup"><span data-stu-id="9a7ee-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9a7ee-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="9a7ee-222">AudioMute+</span></span> |  <span data-ttu-id="9a7ee-223">O SMC envia o comando de silenciar áudio.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="9a7ee-224">O serviço de computador notifica o SMC que o áudio está desativado.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="9a7ee-225">nenhuma</span><span class="sxs-lookup"><span data-stu-id="9a7ee-225">none</span></span> |


 

## <a name="video-source"></a><span data-ttu-id="9a7ee-226">Fonte de vídeo</span><span class="sxs-lookup"><span data-stu-id="9a7ee-226">Video source</span></span>

<span data-ttu-id="9a7ee-227">Várias fontes de exibição podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-227">Several display sources can be used.</span></span>

| <span data-ttu-id="9a7ee-228">Estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-228">State</span></span> | <span data-ttu-id="9a7ee-229">Descrição</span><span class="sxs-lookup"><span data-stu-id="9a7ee-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="9a7ee-230">0</span><span class="sxs-lookup"><span data-stu-id="9a7ee-230">0</span></span> |  <span data-ttu-id="9a7ee-231">Computador integrado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-231">Onboard PC</span></span> |
| <span data-ttu-id="9a7ee-232">um</span><span class="sxs-lookup"><span data-stu-id="9a7ee-232">1</span></span> |  <span data-ttu-id="9a7ee-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="9a7ee-233">DisplayPort</span></span> |
| <span data-ttu-id="9a7ee-234">2</span><span class="sxs-lookup"><span data-stu-id="9a7ee-234">2</span></span> |  <span data-ttu-id="9a7ee-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="9a7ee-235">HDMI</span></span> |
| <span data-ttu-id="9a7ee-236">3D</span><span class="sxs-lookup"><span data-stu-id="9a7ee-236">3</span></span> |  <span data-ttu-id="9a7ee-237">VGA</span><span class="sxs-lookup"><span data-stu-id="9a7ee-237">VGA</span></span> |


 

<span data-ttu-id="9a7ee-238">Alterações na fonte de exibição podem ser enviadas por um sistema de controle de sala ou outro sistema.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="9a7ee-239">Comando</span><span class="sxs-lookup"><span data-stu-id="9a7ee-239">Command</span></span> | <span data-ttu-id="9a7ee-240">Mudança de estado</span><span class="sxs-lookup"><span data-stu-id="9a7ee-240">State change</span></span> | <span data-ttu-id="9a7ee-241">Resposta</span><span class="sxs-lookup"><span data-stu-id="9a7ee-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9a7ee-242">Source=#</span><span class="sxs-lookup"><span data-stu-id="9a7ee-242">Source=#</span></span> |  <span data-ttu-id="9a7ee-243">O SMC muda para a fonte desejada.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="9a7ee-244">O serviço de computador notifica o SMC que a fonte de exibição mudou.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="9a7ee-245">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="9a7ee-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="9a7ee-246">Source+</span><span class="sxs-lookup"><span data-stu-id="9a7ee-246">Source+</span></span> |  <span data-ttu-id="9a7ee-247">O SMC alterna para a próxima fonte de entrada ativa.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="9a7ee-248">O serviço de computador notifica o SMC sobre a fonte de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="9a7ee-249">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="9a7ee-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="9a7ee-250">Source-</span><span class="sxs-lookup"><span data-stu-id="9a7ee-250">Source-</span></span> | <span data-ttu-id="9a7ee-251">O SMC alterna para a fonte de entrada ativa anterior.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="9a7ee-252">O serviço de computador notifica o SMC sobre a fonte de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="9a7ee-253">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="9a7ee-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="9a7ee-254">Source?</span><span class="sxs-lookup"><span data-stu-id="9a7ee-254">Source?</span></span> |  <span data-ttu-id="9a7ee-255">O SMC consulta o serviço do computador quanto à fonte de entrada ativa.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="9a7ee-256">O serviço de computador notifica o SMC sobre a fonte de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="9a7ee-257">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="9a7ee-257">Source=&lt;#&gt;</span></span> |

## <a name="errors"></a><span data-ttu-id="9a7ee-258">Erros</span><span class="sxs-lookup"><span data-stu-id="9a7ee-258">Errors</span></span>

<span data-ttu-id="9a7ee-259">Os erros são retornados seguindo o formato nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="9a7ee-260">Erro</span><span class="sxs-lookup"><span data-stu-id="9a7ee-260">Error</span></span> | <span data-ttu-id="9a7ee-261">Observações</span><span class="sxs-lookup"><span data-stu-id="9a7ee-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="9a7ee-262">Erro: comando desconhecido '&lt;input&gt;'.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="9a7ee-263">A instrução contém um comando inicial desconhecido.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="9a7ee-264">Por exemplo, &quot;VOL+&quot; seria inválido e retornaria &quot; Erro: comando desconhecido 'VOL'&quot;.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="9a7ee-265">Erro: operador desconhecido '&lt;input&gt;'.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="9a7ee-266">A instrução contém um operador desconhecido.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="9a7ee-267">Por exemplo, &quot;Volume!&quot; seria inválido e retornaria &quot; Erro: Operador desconhecido '!'&quot;.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="9a7ee-268">Erro: parâmetro desconhecido '&lt;input&gt;'.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="9a7ee-269">A instrução contém um parâmetro desconhecido.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="9a7ee-270">Por exemplo, &quot;Volume=abc&quot; seria inválido e retornaria &quot; Erro: parâmetro desconhecido 'abc'&quot;.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="9a7ee-271">Erro: comando não disponível quando '&lt;input&gt;' está desativado.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="9a7ee-272">Quando o Surface Hub está desativado, comandos diferentes de Liga/Desliga retornam esse erro.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="9a7ee-273">Por exemplo, &quot;Volume+&quot; seria inválido e retornaria &quot; Erro: comando não disponível quando 'Volume' está desativado&quot;.</span><span class="sxs-lookup"><span data-stu-id="9a7ee-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <a name="related-topics"></a><span data-ttu-id="9a7ee-274">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9a7ee-274">Related topics</span></span>


[<span data-ttu-id="9a7ee-275">Gerenciar o Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9a7ee-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="9a7ee-276">Guia do administrador do Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9a7ee-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





