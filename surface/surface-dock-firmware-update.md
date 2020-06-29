---
title: Atualização do firmware do Dock Surface da Microsoft-informações técnicas para administradores de ti
description: Este artigo explica como usar a atualização do firmware do ensurface Dock da Microsoft para atualizar o firmware do Dock Surface. Quando instalado em seu dispositivo Surface, ele atualizará qualquer encaixe de superfície anexado ao seu dispositivo Surface.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: aab4c67a6a262b11cd5982ebe145afbddfeaa1c9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830260"
---
# <span data-ttu-id="3e8d8-104">Atualização do firmware do Dock Surface da Microsoft: informações técnicas para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="3e8d8-104">Microsoft Surface Dock Firmware Update: Technical information for IT administrators</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e8d8-105">Este artigo contém instruções técnicas para administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="3e8d8-106">Se você for um usuário doméstico, consulte [como atualizar o firmware do Dock Surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   no site de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="3e8d8-107">As instruções no site de suporte são as mesmas etapas gerais de instalação, mas este artigo tem informações adicionais para monitorar, verificar e implantar a atualização em vários dispositivos em uma rede.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="3e8d8-108">Este artigo explica como usar a atualização do firmware do ensurface Dock da Microsoft para atualizar o firmware do Dock Surface.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-108">This article explains how to use Microsoft Surface Dock Firmware Update to update Surface Dock firmware.</span></span> <span data-ttu-id="3e8d8-109">Quando instalado em seu dispositivo Surface, ele atualizará qualquer encaixe de superfície anexado ao seu dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-109">When installed on your Surface device, it will update any Surface Dock attached to your Surface device.</span></span> 

<span data-ttu-id="3e8d8-110">Esta ferramenta substitui a ferramenta anterior do atualizador do Microsoft Surface Dock, anteriormente disponível para download como parte das ferramentas de superfície para isso.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-110">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="3e8d8-111">A ferramenta anterior foi nomeada Surface_Dock_Updater_vx.xx.xxx.x.msi (em que x indica o número da versão) e não está mais disponível para download e não deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-111">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="3e8d8-112">Instalar a atualização do firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="3e8d8-112">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="3e8d8-113">Esta seção descreve como instalar manualmente a atualização de firmware.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-113">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="3e8d8-114">A Microsoft lança periodicamente novas versões da atualização do firmware do Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-114">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="3e8d8-115">O arquivo MSI não está autoatualizável.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-115">The MSI file is not self-updating.</span></span> <span data-ttu-id="3e8d8-116">Se você implantou o MSI em dispositivos de superfície e uma nova versão do firmware estiver liberada, será necessário implantar a nova versão.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-116">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="3e8d8-117">Baixe e instale a [atualização do firmware do Microsoft Surface Dock](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="3e8d8-117">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="3e8d8-118">A atualização requer um dispositivo de superfície executando o Windows 10, versão 1803 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-118">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="3e8d8-119">Instalar o arquivo MSI pode solicitar que você reinicie a superfície.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-119">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="3e8d8-120">No entanto, não é necessário reiniciar para executar a atualização.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-120">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="3e8d8-121">Desconecte o dispositivo Surface do Dock Dock (usando o adaptador de energia), aguarde cerca de 5 segundos e, em seguida, reconecte-se.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-121">Disconnect your Surface device from the Surface Dock (using the power adapter), wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="3e8d8-122">A atualização do firmware do Surface Dock atualizará o encaixe em modo silencioso em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-122">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="3e8d8-123">O processo pode levar alguns minutos para ser concluído e continuará mesmo que seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-123">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="3e8d8-124">Monitorar a atualização do firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="3e8d8-124">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="3e8d8-125">Esta seção é opcional e fornece uma visão geral de como monitorar a instalação da atualização de firmware.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-125">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="3e8d8-126">Para monitorar a atualização:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-126">To monitor the update:</span></span>

1. <span data-ttu-id="3e8d8-127">Abra o Visualizador de eventos, navegue até **logs do Windows > aplicativo**e, em **ações** no painel à direita, clique em **Filtrar log atual**, digite **SurfaceDockFwUpdate** ao lado de **origens do evento**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-127">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="3e8d8-128">Digite o seguinte comando em um prompt de comando elevado:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-128">Type the following command at an elevated command prompt:</span></span>

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="3e8d8-129">Instale a atualização conforme descrito na [próxima seção](#install-the-surface-dock-firmware-update) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-129">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>
4. <span data-ttu-id="3e8d8-130">O evento 2007 com o seguinte texto indica uma atualização bem-sucedida: **atualização do firmware concluída. hr = 0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-130">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 
    - <span data-ttu-id="3e8d8-131">Se a atualização não for bem-sucedida, a ID do evento 2007 será exibida como um evento de **erro** em vez de **informações**.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-131">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="3e8d8-132">Além disso, a versão relatada no registro do Windows não será atual.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-132">Additionally, the version reported in the Windows Registry will not be current.</span></span>
5. <span data-ttu-id="3e8d8-133">Quando a atualização estiver completa, os valores DWORD atualizados serão exibidos no registro do Windows, correspondente à versão atual da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-133">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="3e8d8-134">Consulte a seção de [referência de versões](#versions-reference) neste artigo para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-134">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="3e8d8-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-135">For example:</span></span>
    - <span data-ttu-id="3e8d8-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="3e8d8-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="3e8d8-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="3e8d8-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="3e8d8-138">Se você vir "a descrição para a identificação do evento xxxx do SurfaceDockFwUpdate de origem não pode ser encontrado" no texto do evento, isso é esperado e pode ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-138">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="3e8d8-139">Além disso, Confira as seções a seguir neste artigo:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-139">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="3e8d8-140">Como verificar a conclusão da atualização do firmware</span><span class="sxs-lookup"><span data-stu-id="3e8d8-140">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="3e8d8-141">Log de eventos</span><span class="sxs-lookup"><span data-stu-id="3e8d8-141">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="3e8d8-142">Dicas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3e8d8-142">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="3e8d8-143">Referência de versões</span><span class="sxs-lookup"><span data-stu-id="3e8d8-143">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="3e8d8-144">Implantação de rede</span><span class="sxs-lookup"><span data-stu-id="3e8d8-144">Network deployment</span></span>

<span data-ttu-id="3e8d8-145">Você pode usar os comandos do Windows Installer (Msiexec.exe) para implantar a atualização do firmware do Surface Dock em vários dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-145">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="3e8d8-146">Ao usar o Gerenciador de configuração do Microsoft Endpoint ou outra ferramenta de implantação, insira a seguinte sintaxe para garantir que a instalação seja silenciosa:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-146">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="3e8d8-147">Msiexec.exe/i \<path to msi file\> /quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="3e8d8-147">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

  <span data-ttu-id="3e8d8-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-148">For example:</span></span>
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > <span data-ttu-id="3e8d8-149">Um arquivo de log não é criado por padrão.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-149">A log file is not created by default.</span></span> <span data-ttu-id="3e8d8-150">Para criar um arquivo de log, você precisará acrescentar "/l*v [caminho]". Por exemplo: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI. log "</span><span class="sxs-lookup"><span data-stu-id="3e8d8-150">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

  <span data-ttu-id="3e8d8-151">Para obter mais informações, consulte a documentação de [Opções de linha de comando](https://docs.microsoft.com/windows/win32/msi/command-line-options) .</span><span class="sxs-lookup"><span data-stu-id="3e8d8-151">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e8d8-152">Se você quiser manter o encaixe de superfície atualizado usando qualquer outro método, consulte [atualizar seu Dock Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-152">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="3e8d8-153">Implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="3e8d8-153">Intune deployment</span></span>

<span data-ttu-id="3e8d8-154">Você pode usar o Intune para distribuir a atualização do firmware do Surface Dock para seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-154">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="3e8d8-155">Primeiro, você precisará converter o arquivo MSI no formato. intunewin, conforme descrito na documentação a seguir: [Intune standalone-gerenciamento de aplicativos Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="3e8d8-155">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="3e8d8-156">Use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-156">Use the following command:</span></span>
  - **<span data-ttu-id="3e8d8-157">msiexec/i \<path to msi file\> /Quiet/q</span><span class="sxs-lookup"><span data-stu-id="3e8d8-157">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="3e8d8-158">Como verificar a conclusão da atualização do firmware</span><span class="sxs-lookup"><span data-stu-id="3e8d8-158">How to verify completion of the firmware update</span></span>

<span data-ttu-id="3e8d8-159">O firmware do Dock Surface consiste em dois componentes:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-159">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="3e8d8-160">**Component10:** Firmware da micro controller Unit (MCU)</span><span class="sxs-lookup"><span data-stu-id="3e8d8-160">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="3e8d8-161">**Component20:** Firmware de porta de vídeo (DP).</span><span class="sxs-lookup"><span data-stu-id="3e8d8-161">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="3e8d8-162">A conclusão bem-sucedida da atualização do firmware do Surface Dock resulta em novos valores de chave do registro para estes componentes de firmware.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-162">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="3e8d8-163">Para verificar as atualizações:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-163">To verify updates:</span></span>**

1. <span data-ttu-id="3e8d8-164">Abra o regedit e navegue até o seguinte caminho de registro:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-164">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="3e8d8-165">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="3e8d8-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="3e8d8-166">Procure as chaves do registro: **Component10CurrentFwVersion e Component20CurrentFwVersion**, que se referem ao firmware que está atualmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-166">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Processo de instalação da atualização do firmware do Surface Dock](images/regeditDock.png)

3. <span data-ttu-id="3e8d8-168">Verifique se os novos valores da chave do registro correspondem aos valores de chave do registro atualizados listados na referência versões no final deste documento.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-168">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="3e8d8-169">Se os valores corresponderem, o firmware foi atualizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-169">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="3e8d8-170">Se não for possível verificar, revise as dicas de solução de problemas e log de eventos na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-170">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="3e8d8-171">Log de eventos</span><span class="sxs-lookup"><span data-stu-id="3e8d8-171">Event logging</span></span>

**<span data-ttu-id="3e8d8-172">Tabela 1.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-172">Table 1.</span></span> <span data-ttu-id="3e8d8-173">Arquivos de log para atualização do firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="3e8d8-173">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="3e8d8-174">Log</span><span class="sxs-lookup"><span data-stu-id="3e8d8-174">Log</span></span>                              | <span data-ttu-id="3e8d8-175">Localização</span><span class="sxs-lookup"><span data-stu-id="3e8d8-175">Location</span></span>                               | <span data-ttu-id="3e8d8-176">Observações</span><span class="sxs-lookup"><span data-stu-id="3e8d8-176">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="3e8d8-177">Log de atualização do firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="3e8d8-177">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="3e8d8-178">O caminho deve ser especificado (veja a observação)</span><span class="sxs-lookup"><span data-stu-id="3e8d8-178">Path needs to be specified (see note)</span></span> | <span data-ttu-id="3e8d8-179">Versões anteriores dessa ferramenta escreveram eventos para aplicativos e serviços que o Logs\Microsoft Surface Dock para o Updater.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-179">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="3e8d8-180">Log de instalação do dispositivo do Windows</span><span class="sxs-lookup"><span data-stu-id="3e8d8-180">Windows Device Install log</span></span>       | <span data-ttu-id="3e8d8-181">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="3e8d8-181">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="3e8d8-182">Para obter mais informações sobre como usar o log de instalação do dispositivo, consulte documentação de [log setupapi](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) .</span><span class="sxs-lookup"><span data-stu-id="3e8d8-182">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="3e8d8-183">Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-183">Table 2.</span></span> <span data-ttu-id="3e8d8-184">IDs de log de eventos para atualização do firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="3e8d8-184">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="3e8d8-185">Os eventos são registrados no log de eventos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-185">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="3e8d8-186">Observação: as versões anteriores dessa ferramenta escreveram eventos para aplicativos e serviços que o Logs\Microsoft Surface Dock redater.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-186">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="3e8d8-187">Event ID</span><span class="sxs-lookup"><span data-stu-id="3e8d8-187">Event ID</span></span> | <span data-ttu-id="3e8d8-188">Event type</span><span class="sxs-lookup"><span data-stu-id="3e8d8-188">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="3e8d8-189">2001</span><span class="sxs-lookup"><span data-stu-id="3e8d8-189">2001</span></span>     | <span data-ttu-id="3e8d8-190">A atualização de firmware Dock foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-190">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="3e8d8-191">2002</span><span class="sxs-lookup"><span data-stu-id="3e8d8-191">2002</span></span>     | <span data-ttu-id="3e8d8-192">Encaixar atualização de firmware ignorada porque o encaixe é conhecido como atualizado.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-192">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="3e8d8-193">2003</span><span class="sxs-lookup"><span data-stu-id="3e8d8-193">2003</span></span>     | <span data-ttu-id="3e8d8-194">Falha na atualização do firmware Dock para obter a versão do firmware.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-194">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="3e8d8-195">2004</span><span class="sxs-lookup"><span data-stu-id="3e8d8-195">2004</span></span>     | <span data-ttu-id="3e8d8-196">Consultando a versão do firmware.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-196">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="3e8d8-197">2005</span><span class="sxs-lookup"><span data-stu-id="3e8d8-197">2005</span></span>     | <span data-ttu-id="3e8d8-198">Falha no firmware Dock ao iniciar a atualização.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-198">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="3e8d8-199">2006</span><span class="sxs-lookup"><span data-stu-id="3e8d8-199">2006</span></span>     | <span data-ttu-id="3e8d8-200">Falha ao enviar pares de oferta/carga.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-200">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="3e8d8-201">2007</span><span class="sxs-lookup"><span data-stu-id="3e8d8-201">2007</span></span>     | <span data-ttu-id="3e8d8-202">Atualização do firmware concluída.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-202">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="3e8d8-203">2008</span><span class="sxs-lookup"><span data-stu-id="3e8d8-203">2008</span></span>     | <span data-ttu-id="3e8d8-204">Comece a encaixar telemetria.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-204">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="3e8d8-205">2011</span><span class="sxs-lookup"><span data-stu-id="3e8d8-205">2011</span></span>     | <span data-ttu-id="3e8d8-206">Encaixar telemetria encaixada.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-206">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="3e8d8-207">Dicas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3e8d8-207">Troubleshooting tips</span></span>

- <span data-ttu-id="3e8d8-208">Desconecte completamente a alimentação do Surface Dock da alimentação CA para redefinir o Dock Surface.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-208">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="3e8d8-209">Desconecte todos os periféricos, exceto para o encaixe de superfície.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-209">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="3e8d8-210">Desinstale qualquer atualização de firmware do Dock Surface atual e instale a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-210">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="3e8d8-211">Verifique se o cais Surface está desconectado e, em seguida, deixe tempo suficiente para que a atualização seja concluída conforme monitorado via LED na porta Ethernet do Dock.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-211">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="3e8d8-212">Aguarde até que o LED pare de piscar antes de desconectar o encaixe de superfície da energia.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-212">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="3e8d8-213">Conecte o encaixe de superfície a um dispositivo diferente para ver se ele pode atualizar o Dock.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-213">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="3e8d8-214">Referência de versões</span><span class="sxs-lookup"><span data-stu-id="3e8d8-214">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="3e8d8-215">O arquivo de instalação é lançado com o seguinte formato de nomenclatura: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) e é instalado por padrão para C:\Program Files\SurfaceUpdate.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-215">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="3e8d8-216">Versão 1.42.139</span><span class="sxs-lookup"><span data-stu-id="3e8d8-216">Version 1.42.139</span></span> 
*<span data-ttu-id="3e8d8-217">Data do lançamento: setembro de 18 2019</span><span class="sxs-lookup"><span data-stu-id="3e8d8-217">Release Date: September 18 2019</span></span>*

<span data-ttu-id="3e8d8-218">Esta versão, contida em Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, atualiza o firmware em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-218">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 
**<span data-ttu-id="3e8d8-219">Valores atualizados da chave do registro:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-219">Updated registry key values:</span></span>**<br>

- <span data-ttu-id="3e8d8-220">Component10CurrentFwVersion atualizado para **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-220">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="3e8d8-221">Component20CurrentFwVersion atualizado para **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-221">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="3e8d8-222">Ele adiciona suporte para Surface Pro 7 e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-222">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="3e8d8-223">Versões herdadas</span><span class="sxs-lookup"><span data-stu-id="3e8d8-223">Legacy versions</span></span>

### <span data-ttu-id="3e8d8-224">Versão 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-224">Version 2.23.139.0</span></span>
*<span data-ttu-id="3e8d8-225">Data do lançamento: 10 de outubro de 2018</span><span class="sxs-lookup"><span data-stu-id="3e8d8-225">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="3e8d8-226">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-226">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="3e8d8-227">Adicionar suporte para Surface pro 6</span><span class="sxs-lookup"><span data-stu-id="3e8d8-227">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="3e8d8-228">Adicionar suporte para o laptop 2 Surface</span><span class="sxs-lookup"><span data-stu-id="3e8d8-228">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="3e8d8-229">Versão 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-229">Version 2.22.139.0</span></span>
*<span data-ttu-id="3e8d8-230">Data do lançamento: 26 de julho de 2018</span><span class="sxs-lookup"><span data-stu-id="3e8d8-230">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="3e8d8-231">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-231">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="3e8d8-232">Aumentar a confiabilidade da atualização</span><span class="sxs-lookup"><span data-stu-id="3e8d8-232">Increase update reliability</span></span>
- <span data-ttu-id="3e8d8-233">Adicionar suporte para a superfície go</span><span class="sxs-lookup"><span data-stu-id="3e8d8-233">Add support for Surface Go</span></span>

### <span data-ttu-id="3e8d8-234">Versão2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-234">Version 2.12.136.0</span></span>
*<span data-ttu-id="3e8d8-235">Data do lançamento: 29 de janeiro de 2018</span><span class="sxs-lookup"><span data-stu-id="3e8d8-235">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="3e8d8-236">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-236">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="3e8d8-237">Atualização do firmware do chipset principal do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="3e8d8-237">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="3e8d8-238">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="3e8d8-238">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="3e8d8-239">Estabilidade aprimorada para vídeos externos quando usados com o Surface Book ou o Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="3e8d8-239">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="3e8d8-240">Além disso, a instalação desta versão do Surface Dock Updater em dispositivos Surface Book inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-240">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="3e8d8-241">Atualização do firmware da Base do Surface Book</span><span class="sxs-lookup"><span data-stu-id="3e8d8-241">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="3e8d8-242">Adição de suporte para atualizações do firmware do Surface Dock com melhorias direcionadas a dispositivos Surface Book</span><span class="sxs-lookup"><span data-stu-id="3e8d8-242">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="3e8d8-243">Versão2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-243">Version 2.9.136.0</span></span>
*<span data-ttu-id="3e8d8-244">Data do lançamento: 3 de novembro de 2017</span><span class="sxs-lookup"><span data-stu-id="3e8d8-244">Release date: November 3, 2017</span></span>*

<span data-ttu-id="3e8d8-245">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-245">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3e8d8-246">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="3e8d8-246">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="3e8d8-247">Resolve um problema de áudio sobre adaptadores de porta de exibição passiva</span><span class="sxs-lookup"><span data-stu-id="3e8d8-247">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="3e8d8-248">Versão2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-248">Version 2.1.15.0</span></span>
*<span data-ttu-id="3e8d8-249">Data do lançamento: 19 de junho de 2017</span><span class="sxs-lookup"><span data-stu-id="3e8d8-249">Release date: June 19, 2017</span></span>*

<span data-ttu-id="3e8d8-250">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-250">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3e8d8-251">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="3e8d8-251">Surface Laptop</span></span>
* <span data-ttu-id="3e8d8-252">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="3e8d8-252">Surface Pro</span></span>

### <span data-ttu-id="3e8d8-253">Versão2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-253">Version 2.1.6.0</span></span>
*<span data-ttu-id="3e8d8-254">Data do lançamento: 7 de abril de 2017</span><span class="sxs-lookup"><span data-stu-id="3e8d8-254">Release date: April 7, 2017</span></span>*

<span data-ttu-id="3e8d8-255">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-255">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3e8d8-256">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="3e8d8-256">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="3e8d8-257">Requer o Windows 10</span><span class="sxs-lookup"><span data-stu-id="3e8d8-257">Requires Windows 10</span></span>

### <span data-ttu-id="3e8d8-258">Versão2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-258">Version 2.0.22.0</span></span>
*<span data-ttu-id="3e8d8-259">Data do lançamento: 21 de outubro de 2016</span><span class="sxs-lookup"><span data-stu-id="3e8d8-259">Release date: October 21, 2016</span></span>*

<span data-ttu-id="3e8d8-260">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-260">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3e8d8-261">Atualização do firmware do Surface Dock USB</span><span class="sxs-lookup"><span data-stu-id="3e8d8-261">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="3e8d8-262">Maior confiabilidade de portas Ethernet, áudio e USB</span><span class="sxs-lookup"><span data-stu-id="3e8d8-262">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="3e8d8-263">Versão1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="3e8d8-263">Version 1.0.8.0</span></span>
*<span data-ttu-id="3e8d8-264">Data do lançamento: 26 de abril de 2016</span><span class="sxs-lookup"><span data-stu-id="3e8d8-264">Release date: April 26, 2016</span></span>*

<span data-ttu-id="3e8d8-265">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e8d8-265">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3e8d8-266">Atualização do firmware do chipset principal do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="3e8d8-266">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="3e8d8-267">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="3e8d8-267">Update for Surface Dock DisplayPort firmware</span></span>

