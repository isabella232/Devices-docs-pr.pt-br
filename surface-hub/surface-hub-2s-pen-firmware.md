---
title: Atualizar o firmware da caneta no Surface Hub 2S
description: Esta página descreve como atualizar o firmware para a Surface Hub 2.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: c94cb701fb1b7fcdc0168a795f57a4e497317902
ms.sourcegitcommit: 77b2c51f8467ac3ac37399551b0cc20d9ce57d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "11585962"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a><span data-ttu-id="4fdde-104">Atualizar o firmware da caneta no Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="4fdde-104">Update pen firmware on Surface Hub 2S</span></span>

<span data-ttu-id="4fdde-105">Você pode atualizar o firmware Surface Hub caneta 2 do Windows Update for Business ou baixando a atualização de firmware para um computador separado.</span><span class="sxs-lookup"><span data-stu-id="4fdde-105">You can update firmware on Surface Hub 2 pen from Windows Update for Business or by downloading the firmware update to a separate PC.</span></span> <span data-ttu-id="4fdde-106">O firmware atualizado está disponível no Windows Update a partir de 26 de fevereiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="4fdde-106">Updated firmware is available from Windows Update beginning February 26, 2020.</span></span> 

## <a name="update-pen-firmware-using-windows-update-for-business"></a><span data-ttu-id="4fdde-107">Atualizar o firmware da caneta usando Windows Atualização para Empresas</span><span class="sxs-lookup"><span data-stu-id="4fdde-107">Update pen firmware using Windows Update for Business</span></span>

<span data-ttu-id="4fdde-108">Esta seção descreve como atualizar o firmware de caneta por meio dos ciclos de manutenção automatizados do Windows Update, configurados por padrão para ocorrerem à noite às 3 da manhã.</span><span class="sxs-lookup"><span data-stu-id="4fdde-108">This section describes how to update pen firmware via the automated maintenance cycles for Windows Update, configured by default to occur nightly at 3 a.m.</span></span> <span data-ttu-id="4fdde-109">Você precisará planejar dois ciclos de manutenção para ser concluído antes de aplicar a atualização à Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="4fdde-109">You will need to plan for two maintenance cycles to complete before applying the update to the Surface Hub 2 pen.</span></span> <span data-ttu-id="4fdde-110">Como qualquer outra atualização, você pode usar o Windows Update for Business (WUfB) para aplicar o firmware de caneta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-110">Alternately, like any other update, you can use Windows Update for Business (WUfB) to apply the pen firmware.</span></span> <span data-ttu-id="4fdde-111">Para obter mais informações, consulte [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="4fdde-111">For more information, see [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span></span>

1. <span data-ttu-id="4fdde-112">Verifique se Surface Hub caneta 2 está emparelhada Surface Hub 2S: pressione \*\*\*\* e segure o botão superior até que a luz LED do indicador branco comece a piscar.</span><span class="sxs-lookup"><span data-stu-id="4fdde-112">Ensure the Surface Hub 2 pen is paired to Surface Hub 2S: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Surface Hub caneta 2](images/sh2-pen-1.png)

2. <span data-ttu-id="4fdde-114">No Surface Hub, faça logon como administrador, **abra**Configurações e, em seguida, procure novos Bluetooth dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4fdde-114">On Surface Hub, login as an Admin, open **Settings**, and then scan for new Bluetooth devices.</span></span>

3. <span data-ttu-id="4fdde-115">Selecione a caneta para concluir o processo de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="4fdde-115">Select the pen to complete the pairing process.</span></span>

4. <span data-ttu-id="4fdde-116">Pressione o **botão** superior na caneta para aplicar a atualização.</span><span class="sxs-lookup"><span data-stu-id="4fdde-116">Press the **top** button on the pen to apply the update.</span></span> <span data-ttu-id="4fdde-117">Pode levar até duas horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4fdde-117">It may take up to two hours to complete.</span></span>

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a><span data-ttu-id="4fdde-118">Atualizar o firmware da caneta baixando para o computador separado</span><span class="sxs-lookup"><span data-stu-id="4fdde-118">Update pen firmware by downloading to separate PC</span></span>

<span data-ttu-id="4fdde-119">Você pode atualizar o firmware na Surface Hub 2 de um computador separado que executa Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4fdde-119">You can update the firmware on Surface Hub 2 pen from a separate PC running Windows 10.</span></span> <span data-ttu-id="4fdde-120">Esse método também permite verificar se o firmware da caneta foi atualizado com êxito para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="4fdde-120">This method also enables you to verify that the pen firmware has successfully updated to the latest version.</span></span>

1. <span data-ttu-id="4fdde-121">Emparelhe Surface Hub caneta 2 ao computador com capacidade Bluetooth: pressione \*\*\*\* e segure o botão superior até que a luz LED do indicador branco comece a piscar.</span><span class="sxs-lookup"><span data-stu-id="4fdde-121">Pair the Surface Hub 2 pen to your Bluetooth-capable PC: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Surface Hub caneta 2](images/sh2-pen-1.png)

2. <span data-ttu-id="4fdde-123">No computador, procure novos dispositivos Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="4fdde-123">On the PC, scan for new Bluetooth devices.</span></span>

3. <span data-ttu-id="4fdde-124">Selecione a caneta para concluir o processo de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="4fdde-124">Select the pen to complete the pairing process.</span></span>

4. <span data-ttu-id="4fdde-125">Desconecte todas as Surface Hub 2s antes de iniciar uma nova atualização.</span><span class="sxs-lookup"><span data-stu-id="4fdde-125">Disconnect all other Surface Hub 2s pens before starting a new update.</span></span>

5. <span data-ttu-id="4fdde-126">Baixe a [Surface Hub de Atualização de Firmware de 2 Canetas](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) no computador.</span><span class="sxs-lookup"><span data-stu-id="4fdde-126">Download the [Surface Hub 2 Pen Firmware Update Tool](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) to your PC.</span></span>

6. <span data-ttu-id="4fdde-127">Execute **PenCfu.exe.**</span><span class="sxs-lookup"><span data-stu-id="4fdde-127">Run **PenCfu.exe.**</span></span> <span data-ttu-id="4fdde-128">O progresso da instalação é exibido na ferramenta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-128">The install progress is displayed in the tool.</span></span> <span data-ttu-id="4fdde-129">Pode levar vários minutos para concluir a atualização.</span><span class="sxs-lookup"><span data-stu-id="4fdde-129">It may take several minutes to finish updating.</span></span> 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a><span data-ttu-id="4fdde-130">Verificar a versão de firmware Surface Hub caneta 2</span><span class="sxs-lookup"><span data-stu-id="4fdde-130">Check firmware version of Surface Hub 2 pen</span></span>

1. <span data-ttu-id="4fdde-131">Execute **get_version.bat** e pressione o **botão superior** da caneta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-131">Run **get_version.bat** and press the **top** button on the pen.</span></span>

2. <span data-ttu-id="4fdde-132">A ferramenta relatará a versão de firmware da caneta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-132">The tool will report the firmware version of the pen.</span></span> 

   <span data-ttu-id="4fdde-133">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="4fdde-133">Example:</span></span>
    - <span data-ttu-id="4fdde-134">O firmware antigo é 468.2727.368</span><span class="sxs-lookup"><span data-stu-id="4fdde-134">Old firmware is 468.2727.368</span></span>
    - <span data-ttu-id="4fdde-135">O novo firmware é 468.3347.368</span><span class="sxs-lookup"><span data-stu-id="4fdde-135">New firmware is 468.3347.368</span></span>

## <a name="command-line-options"></a><span data-ttu-id="4fdde-136">Opções de linha de comando</span><span class="sxs-lookup"><span data-stu-id="4fdde-136">Command line options</span></span>

<span data-ttu-id="4fdde-137">Você pode executar Surface Hub Ferramenta de Atualização de Firmware de 2 Canetas (PenCfu.exe) na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="4fdde-137">You can run Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) from the command line.</span></span>

1. <span data-ttu-id="4fdde-138">Emparelhe a caneta no computador e clique no **botão superior** da caneta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-138">Pair the pen to your PC and click the **top** button on the pen.</span></span>

2. <span data-ttu-id="4fdde-139">Clique duas **PenCfu.exe** para iniciar a atualização de firmware.</span><span class="sxs-lookup"><span data-stu-id="4fdde-139">Double click **PenCfu.exe** to initiate the firmware update.</span></span> <span data-ttu-id="4fdde-140">Observe que o arquivo de configuração e os arquivos de imagem do firmware devem ser armazenados na mesma pasta que a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-140">Note that the configuration file and the firmware image files must be stored in the same folder as the tool.</span></span>

3. <span data-ttu-id="4fdde-141">Para opções adicionais, execute **PenCfu.exe -h** para exibir os parâmetros disponíveis, conforme listado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="4fdde-141">For additional options, run **PenCfu.exe -h** to display the available parameters, as listed in the following table.</span></span>  

   <span data-ttu-id="4fdde-142">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="4fdde-142">Example:</span></span> `PenCfu.exe -h`

4. <span data-ttu-id="4fdde-143">Insira **Ctrl+C** para desligar com segurança a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-143">Enter **Ctrl+C** to safely shut down the tool.</span></span>


| <span data-ttu-id="4fdde-144">Comando</span><span class="sxs-lookup"><span data-stu-id="4fdde-144">Command</span></span> | <span data-ttu-id="4fdde-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="4fdde-145">Description</span></span> |
| -------------- |---------------------------- |
| <span data-ttu-id="4fdde-146">-h ajuda</span><span class="sxs-lookup"><span data-stu-id="4fdde-146">-h help</span></span>        | <span data-ttu-id="4fdde-147">Ajuda e saída da interface de linha de comando da ferramenta de exibição.</span><span class="sxs-lookup"><span data-stu-id="4fdde-147">Display tool command line interface help and exit.</span></span> |
| <span data-ttu-id="4fdde-148">Versão -v</span><span class="sxs-lookup"><span data-stu-id="4fdde-148">-v version</span></span>     | <span data-ttu-id="4fdde-149">Exibir versão e sair da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-149">Display tool version and exit.</span></span> |
| <span data-ttu-id="4fdde-150">-l log-filter</span><span class="sxs-lookup"><span data-stu-id="4fdde-150">-l log-filter</span></span>  | <span data-ttu-id="4fdde-151">Definir um nível de filtro para o arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="4fdde-151">Set a filter level for the log file.</span></span> <span data-ttu-id="4fdde-152">As mensagens de log têm 4 níveis possíveis: DEPURAÇÃO (mais baixa), INFO, AVISO e ERRO (mais alto).</span><span class="sxs-lookup"><span data-stu-id="4fdde-152">Log messages have 4 possible levels: DEBUG (lowest), INFO, WARNING and ERROR (highest).</span></span> <span data-ttu-id="4fdde-153">A configuração de um nível de filtro de log filtra as mensagens de log apenas com o mesmo nível ou superior.</span><span class="sxs-lookup"><span data-stu-id="4fdde-153">Setting a log filter level filters log messages to only message with the same level or higher.</span></span> <span data-ttu-id="4fdde-154">Por exemplo, se o nível de filtro estiver definido como AVISO, somente as mensagens WARNING e ERROR serão registradas.</span><span class="sxs-lookup"><span data-stu-id="4fdde-154">For example, if the filter level is set to WARNING, only WARNING and ERROR messages will be logged.</span></span> <span data-ttu-id="4fdde-155">Por padrão, essa opção é definida como OFF, que desabilita o registro em log.</span><span class="sxs-lookup"><span data-stu-id="4fdde-155">By default, this option is set to OFF, which disables logging.</span></span> |
| <span data-ttu-id="4fdde-156">-g get-version</span><span class="sxs-lookup"><span data-stu-id="4fdde-156">-g get-version</span></span> | <span data-ttu-id="4fdde-157">Se especificado, a ferramenta receberá apenas a versão FW da caneta conectada que corresponde ao arquivo de configuração armazenado na mesma pasta que a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="4fdde-157">If specified, the tool will only get the FW version of the connected pen that matches the configuration file that is stored in the same folder as the tool.</span></span>  |

