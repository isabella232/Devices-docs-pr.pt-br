---
title: Atualização de firmware do Microsoft Surface Dock 1
description: Este artigo explica como usar a Atualização de Firmware do Microsoft Surface Dock para instalar e gerenciar o firmware no Surface Dock 1 original. Quando instalado no dispositivo Surface, ele atualizará os dispositivos Surface Dock 1 conectados ao dispositivo Surface.
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
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319205"
---
# <span data-ttu-id="6769a-104">Atualização do firmware do Microsoft Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6769a-105">Este artigo contém instruções técnicas para administradores de IT.</span><span class="sxs-lookup"><span data-stu-id="6769a-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="6769a-106">Se você for um usuário local, veja como atualizar [o firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)do Surface Dock no site de suporte da   Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6769a-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="6769a-107">As instruções no site de suporte são as mesmas das etapas gerais de instalação abaixo, mas este artigo tem informações adicionais para monitoramento, verificação e implantação da atualização em vários dispositivos em uma rede.</span><span class="sxs-lookup"><span data-stu-id="6769a-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="6769a-108">Este artigo explica como usar a Atualização de Firmware do Microsoft Surface Dock para instalar e gerenciar o firmware no Surface Dock 1 original.</span><span class="sxs-lookup"><span data-stu-id="6769a-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="6769a-109">Quando instalado no dispositivo Surface, ele atualizará os dispositivos Surface Dock 1 conectados ao dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6769a-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="6769a-110">Este artigo não se aplica ao Surface Dock 2, que recebe atualizações automaticamente por meio do Windows Update ou usando o Microsoft Endpoint Configuration Manager ou outras ferramentas de implantação MSI.</span><span class="sxs-lookup"><span data-stu-id="6769a-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="6769a-111">Para saber mais, confira [Novidades no Surface Dock.](surface-dock-whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="6769a-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="6769a-112">Essa ferramenta sobressupa a ferramenta Anterior do Microsoft Surface Dock Updater, disponível anteriormente para download como parte das Ferramentas do Surface para IT.</span><span class="sxs-lookup"><span data-stu-id="6769a-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="6769a-113">A ferramenta anterior foi nomeada Surface_Dock_Updater_vx.xx.xxx.x.msi (onde x indica o número da versão) e não está mais disponível para download e não deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="6769a-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <a name="install-the-surface-dock-firmware-update"></a><span data-ttu-id="6769a-114">Instalar a Atualização do Firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="6769a-115">Esta seção descreve como instalar manualmente a atualização de firmware.</span><span class="sxs-lookup"><span data-stu-id="6769a-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="6769a-116">A Microsoft lança periodicamente novas versões da Atualização do Firmware do Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="6769a-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="6769a-117">O arquivo MSI não está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="6769a-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="6769a-118">Se você tiver implantado o MSI em dispositivos Surface e uma nova versão do firmware for lançada, será necessário implantar a nova versão.</span><span class="sxs-lookup"><span data-stu-id="6769a-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="6769a-119">Baixe e instale a [Atualização de Firmware do Microsoft Surface Dock.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="6769a-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="6769a-120">A atualização requer um dispositivo Surface que executa o Windows 10, versão 1803 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6769a-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="6769a-121">A instalação do arquivo MSI pode solicitar que você reinicie o Surface.</span><span class="sxs-lookup"><span data-stu-id="6769a-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="6769a-122">No entanto, não é necessário reiniciar para executar a atualização.</span><span class="sxs-lookup"><span data-stu-id="6769a-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="6769a-123">Desconecte o dispositivo Surface do Surface Dock, aguarde cerca de 5 segundos e reconecte-se.</span><span class="sxs-lookup"><span data-stu-id="6769a-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="6769a-124">A Atualização do Firmware do Surface Dock atualizará o encaixe silenciosamente em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6769a-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="6769a-125">O processo pode levar alguns minutos para ser concluído e continuará mesmo se interrompido.</span><span class="sxs-lookup"><span data-stu-id="6769a-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <a name="monitor-the-surface-dock-firmware-update"></a><span data-ttu-id="6769a-126">Monitorar a atualização do firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="6769a-127">Esta seção é opcional e fornece uma visão geral de como monitorar a instalação da atualização do firmware.</span><span class="sxs-lookup"><span data-stu-id="6769a-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="6769a-128">Para monitorar a atualização:</span><span class="sxs-lookup"><span data-stu-id="6769a-128">To monitor the update:</span></span>

1. <span data-ttu-id="6769a-129">Abra o Visualizador de Eventos, navegue até Logs \*\*\*\* do **Windows > Aplicativo**e, em Ações no painel direito, \*\*\*\* clique em Filtrar **Log**Atual, insira **SurfaceDockFwUpdate** ao lado das fontes de eventos e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="6769a-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="6769a-130">Digite o seguinte comando em um prompt de comando com elevação:</span><span class="sxs-lookup"><span data-stu-id="6769a-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="6769a-131">Instale a atualização conforme descrito na [próxima seção](#install-the-surface-dock-firmware-update) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="6769a-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="6769a-132">O evento 2007 com o seguinte texto indica uma atualização bem-sucedida: Atualização de **firmware concluída. hr=0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="6769a-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="6769a-133">Se a atualização não for bem-sucedida, a ID do evento 2007 será exibida como um evento **Error** em vez de **Informações.**</span><span class="sxs-lookup"><span data-stu-id="6769a-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="6769a-134">Além disso, a versão relatada no Registro do Windows não será atual.</span><span class="sxs-lookup"><span data-stu-id="6769a-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="6769a-135">Quando a atualização for concluída, os valores DWORD atualizados serão exibidos no Registro do Windows, correspondentes à versão atual da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="6769a-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="6769a-136">Consulte a [seção de referência](#versions-reference) de versões neste artigo para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="6769a-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="6769a-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6769a-137">For example:</span></span>

    - <span data-ttu-id="6769a-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="6769a-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="6769a-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="6769a-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="6769a-140">Se você vir "A descrição da ID de evento xxxx da origem SurfaceDockFwUpdate não pode ser encontrada" no texto do evento, isso é esperado e pode ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="6769a-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="6769a-141">Consulte também as seções a seguir neste artigo:</span><span class="sxs-lookup"><span data-stu-id="6769a-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="6769a-142">Como verificar a conclusão da atualização de firmware</span><span class="sxs-lookup"><span data-stu-id="6769a-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="6769a-143">Log de eventos</span><span class="sxs-lookup"><span data-stu-id="6769a-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="6769a-144">Dicas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6769a-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="6769a-145">Referência de versões</span><span class="sxs-lookup"><span data-stu-id="6769a-145">Versions reference</span></span>](#versions-reference)

## <a name="network-deployment"></a><span data-ttu-id="6769a-146">Implantação de rede</span><span class="sxs-lookup"><span data-stu-id="6769a-146">Network deployment</span></span>

<span data-ttu-id="6769a-147">Você pode usar comandos do Windows Installer (Msiexec.exe) para implantar a Atualização do Firmware do Surface Dock em vários dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="6769a-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="6769a-148">Ao usar o Microsoft Endpoint Configuration Manager ou outra ferramenta de implantação, insira a seguinte sintaxe para garantir que a instalação seja silenciosa:</span><span class="sxs-lookup"><span data-stu-id="6769a-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="6769a-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span><span class="sxs-lookup"><span data-stu-id="6769a-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="6769a-150">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6769a-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="6769a-151">Um arquivo de log não é criado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6769a-151">A log file is not created by default.</span></span> <span data-ttu-id="6769a-152">Para criar um arquivo de log, você precisará anexar "/l*v [caminho]". Por exemplo: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span><span class="sxs-lookup"><span data-stu-id="6769a-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="6769a-153">Para obter mais informações, consulte a [documentação de opções de linha de](https://docs.microsoft.com/windows/win32/msi/command-line-options) comando.</span><span class="sxs-lookup"><span data-stu-id="6769a-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6769a-154">Se você quiser manter o Surface Dock atualizado usando qualquer outro método, consulte [Atualizar o Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="6769a-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <a name="intune-deployment"></a><span data-ttu-id="6769a-155">Implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="6769a-155">Intune deployment</span></span>

<span data-ttu-id="6769a-156">Você pode usar o Intune para distribuir a Atualização do Firmware do Surface Dock para seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6769a-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="6769a-157">Primeiro, você precisará converter o arquivo MSI para o formato .intunewin, conforme descrito na seguinte documentação: Intune Autônomo - gerenciamento de [aplicativos Win32.](https://docs.microsoft.com/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="6769a-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="6769a-158">Use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6769a-158">Use the following command:</span></span>
  - **<span data-ttu-id="6769a-159">msiexec /i \<path to msi file\> /quiet /q</span><span class="sxs-lookup"><span data-stu-id="6769a-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <a name="how-to-verify-completion-of-the-firmware-update"></a><span data-ttu-id="6769a-160">Como verificar a conclusão da atualização do firmware</span><span class="sxs-lookup"><span data-stu-id="6769a-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="6769a-161">O firmware do Surface Dock consiste em dois componentes:</span><span class="sxs-lookup"><span data-stu-id="6769a-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="6769a-162">**Component10:** Firmware da unidade de micro controlador (MCU)</span><span class="sxs-lookup"><span data-stu-id="6769a-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="6769a-163">**Component20:** Firmware de porta de exibição (DP).</span><span class="sxs-lookup"><span data-stu-id="6769a-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="6769a-164">A conclusão bem-sucedida da Atualização do Firmware do Surface Dock resulta em novos valores de chave do Registro para esses componentes de firmware.</span><span class="sxs-lookup"><span data-stu-id="6769a-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="6769a-165">Para verificar as atualizações:</span><span class="sxs-lookup"><span data-stu-id="6769a-165">To verify updates:</span></span>**

1. <span data-ttu-id="6769a-166">Abra Regedit e navegue até o seguinte caminho do Registro:</span><span class="sxs-lookup"><span data-stu-id="6769a-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="6769a-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="6769a-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="6769a-168">Procure as chaves do Registro: **Component10CurrentFwVersion e Component20CurrentFwVersion**, que se referem ao firmware que está atualmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6769a-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Processo de instalação da Atualização do Firmware do Surface Dock](images/regeditDock.png)

3. <span data-ttu-id="6769a-170">Verifique se os novos valores de chave do Registro corresponderão aos valores de chave do Registro atualizados listados na referência Versões no final deste documento.</span><span class="sxs-lookup"><span data-stu-id="6769a-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="6769a-171">Se os valores corresponderem, o firmware foi atualizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="6769a-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="6769a-172">Se não for possível verificar, revise o log de eventos e as dicas de solução de problemas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="6769a-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <a name="event-logging"></a><span data-ttu-id="6769a-173">Log de eventos</span><span class="sxs-lookup"><span data-stu-id="6769a-173">Event logging</span></span>

**<span data-ttu-id="6769a-174">Tabela 1.</span><span class="sxs-lookup"><span data-stu-id="6769a-174">Table 1.</span></span> <span data-ttu-id="6769a-175">Arquivos de log da Atualização do Firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="6769a-176">Log</span><span class="sxs-lookup"><span data-stu-id="6769a-176">Log</span></span>                              | <span data-ttu-id="6769a-177">Location</span><span class="sxs-lookup"><span data-stu-id="6769a-177">Location</span></span>                               | <span data-ttu-id="6769a-178">Observações</span><span class="sxs-lookup"><span data-stu-id="6769a-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="6769a-179">Log de Atualização do Firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="6769a-180">O caminho precisa ser especificado (consulte a observação)</span><span class="sxs-lookup"><span data-stu-id="6769a-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="6769a-181">Versões anteriores desta ferramenta escreveram eventos nos Logs de Aplicativos e Serviços\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="6769a-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="6769a-182">Log de instalação de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="6769a-182">Windows Device Install log</span></span>       | <span data-ttu-id="6769a-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="6769a-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="6769a-184">Para obter mais informações sobre como usar o Log de Instalação de Dispositivo, consulte a documentação de [Log de SetupAPI.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)</span><span class="sxs-lookup"><span data-stu-id="6769a-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="6769a-185">Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="6769a-185">Table 2.</span></span> <span data-ttu-id="6769a-186">IDs do log de eventos para a Atualização do Firmware do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="6769a-187">Os eventos são registrados no Log de Eventos do Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6769a-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="6769a-188">Observação: as versões anteriores desta ferramenta escreveram eventos nos Logs de Aplicativos e Serviços\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="6769a-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="6769a-189">Event ID</span><span class="sxs-lookup"><span data-stu-id="6769a-189">Event ID</span></span> | <span data-ttu-id="6769a-190">Event type</span><span class="sxs-lookup"><span data-stu-id="6769a-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="6769a-191">2001</span><span class="sxs-lookup"><span data-stu-id="6769a-191">2001</span></span>     | <span data-ttu-id="6769a-192">A atualização do firmware do Dock foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="6769a-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="6769a-193">2002</span><span class="sxs-lookup"><span data-stu-id="6769a-193">2002</span></span>     | <span data-ttu-id="6769a-194">Atualização do firmware do Dock ignorada porque o dock é conhecido por estar atualizado.</span><span class="sxs-lookup"><span data-stu-id="6769a-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="6769a-195">2003</span><span class="sxs-lookup"><span data-stu-id="6769a-195">2003</span></span>     | <span data-ttu-id="6769a-196">Falha ao obter a versão do firmware da atualização do firmware do Dock.</span><span class="sxs-lookup"><span data-stu-id="6769a-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="6769a-197">2004</span><span class="sxs-lookup"><span data-stu-id="6769a-197">2004</span></span>     | <span data-ttu-id="6769a-198">Consultando a versão do firmware.</span><span class="sxs-lookup"><span data-stu-id="6769a-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="6769a-199">2005</span><span class="sxs-lookup"><span data-stu-id="6769a-199">2005</span></span>     | <span data-ttu-id="6769a-200">Falha do firmware do Dock ao iniciar a atualização.</span><span class="sxs-lookup"><span data-stu-id="6769a-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="6769a-201">2006</span><span class="sxs-lookup"><span data-stu-id="6769a-201">2006</span></span>     | <span data-ttu-id="6769a-202">Falha ao enviar pares de oferta/carga.</span><span class="sxs-lookup"><span data-stu-id="6769a-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="6769a-203">2007</span><span class="sxs-lookup"><span data-stu-id="6769a-203">2007</span></span>     | <span data-ttu-id="6769a-204">Atualização do firmware concluída.</span><span class="sxs-lookup"><span data-stu-id="6769a-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="6769a-205">2008</span><span class="sxs-lookup"><span data-stu-id="6769a-205">2008</span></span>     | <span data-ttu-id="6769a-206">Telemetria begin dock.</span><span class="sxs-lookup"><span data-stu-id="6769a-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="6769a-207">2011</span><span class="sxs-lookup"><span data-stu-id="6769a-207">2011</span></span>     | <span data-ttu-id="6769a-208">Telemetria do encaixe FINAL.</span><span class="sxs-lookup"><span data-stu-id="6769a-208">END dock telemetry.</span></span>                                                  |

## <a name="troubleshooting-tips"></a><span data-ttu-id="6769a-209">Dicas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6769a-209">Troubleshooting tips</span></span>

- <span data-ttu-id="6769a-210">Desconecte completamente a energia do Surface Dock da energia CA para redefinir o Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="6769a-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="6769a-211">Desconecte todos os periféricos, exceto o Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="6769a-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="6769a-212">Desinstale qualquer Atualização atual do firmware do Surface Dock e instale a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="6769a-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="6769a-213">Verifique se o Surface Dock está desconectado e, em seguida, deixe tempo suficiente para que a atualização seja concluída conforme monitorado por meio de um LED na porta Ethernet do encaixe.</span><span class="sxs-lookup"><span data-stu-id="6769a-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="6769a-214">Aguarde até que o LED pare de piscar antes de desconectar o Surface Dock da energia.</span><span class="sxs-lookup"><span data-stu-id="6769a-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="6769a-215">Conecte o Surface Dock a um dispositivo diferente para ver se ele é capaz de atualizar o encaixe.</span><span class="sxs-lookup"><span data-stu-id="6769a-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <a name="versions-reference"></a><span data-ttu-id="6769a-216">Referência de versões</span><span class="sxs-lookup"><span data-stu-id="6769a-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="6769a-217">O arquivo de instalação é lançado com o seguinte formato de nomeação: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (por exemplo: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) e é instalado por padrão em C:\Arquivos de Programas\SurfaceUpdate.</span><span class="sxs-lookup"><span data-stu-id="6769a-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <a name="version-1.53.139.0"></a><span data-ttu-id="6769a-218">Versão 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="6769a-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="6769a-219">Data do lançamento: 4 de agosto de 2020</span><span class="sxs-lookup"><span data-stu-id="6769a-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="6769a-220">Esta versão da Atualização do Firmware do Surface Dock inclui correções de bugs e suporte para:</span><span class="sxs-lookup"><span data-stu-id="6769a-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="6769a-221">Atualizando o Surface Dock 1 usando o Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="6769a-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="6769a-222">Se você estiver executando o Surface Pro X, baixe o . Build ARM64.</span><span class="sxs-lookup"><span data-stu-id="6769a-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="6769a-223">Para todos os outros dispositivos, use a com build AMD64.</span><span class="sxs-lookup"><span data-stu-id="6769a-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="6769a-224">Valores de chave do Registro</span><span class="sxs-lookup"><span data-stu-id="6769a-224">Registry key values</span></span>

<span data-ttu-id="6769a-225">Os valores do Registro que indicam o status das atualizações de firmware não foram alterados em relação à versão anterior desta ferramenta:</span><span class="sxs-lookup"><span data-stu-id="6769a-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="6769a-226">Component10CurrentFwVersion atualizado para **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="6769a-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="6769a-227">Component20CurrentFwVersion atualizado para **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="6769a-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <a name="version-1.42.139"></a><span data-ttu-id="6769a-228">Versão 1.42.139</span><span class="sxs-lookup"><span data-stu-id="6769a-228">Version 1.42.139</span></span> 
*<span data-ttu-id="6769a-229">Data do lançamento: 18 de setembro de 2019</span><span class="sxs-lookup"><span data-stu-id="6769a-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="6769a-230">Essa versão, contida no Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, atualiza o firmware em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6769a-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="6769a-231">Valores de chave do Registro atualizados</span><span class="sxs-lookup"><span data-stu-id="6769a-231">Updated registry key values</span></span>

- <span data-ttu-id="6769a-232">Component10CurrentFwVersion atualizado para **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="6769a-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="6769a-233">Component20CurrentFwVersion atualizado para **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="6769a-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="6769a-234">Ele adiciona suporte para o Surface Pro 7 e o Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="6769a-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <a name="legacy-versions"></a><span data-ttu-id="6769a-235">Versões herdadas</span><span class="sxs-lookup"><span data-stu-id="6769a-235">Legacy versions</span></span>

### <a name="version-2.23.139.0"></a><span data-ttu-id="6769a-236">Versão 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="6769a-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="6769a-237">Data do lançamento: 10 de outubro de 2018</span><span class="sxs-lookup"><span data-stu-id="6769a-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="6769a-238">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="6769a-239">Adicionar suporte para o Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="6769a-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="6769a-240">Adicionar suporte para o Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="6769a-240">Add support for Surface Laptop 2</span></span>


### <a name="version-2.22.139.0"></a><span data-ttu-id="6769a-241">Versão 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="6769a-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="6769a-242">Data do lançamento: 26 de julho de 2018</span><span class="sxs-lookup"><span data-stu-id="6769a-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="6769a-243">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="6769a-244">Aumentar a confiabilidade da atualização</span><span class="sxs-lookup"><span data-stu-id="6769a-244">Increase update reliability</span></span>
- <span data-ttu-id="6769a-245">Adicionar suporte para o Surface Go</span><span class="sxs-lookup"><span data-stu-id="6769a-245">Add support for Surface Go</span></span>

### <a name="version-2.12.136.0"></a><span data-ttu-id="6769a-246">Versão2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="6769a-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="6769a-247">Data do lançamento: 29 de janeiro de 2018</span><span class="sxs-lookup"><span data-stu-id="6769a-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="6769a-248">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="6769a-249">Atualização do firmware do chipset principal do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="6769a-250">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="6769a-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="6769a-251">Estabilidade aprimorada para vídeos externos quando usados com o Surface Book ou o Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="6769a-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="6769a-252">Além disso, a instalação desta versão do Surface Dock Updater em dispositivos Surface Book inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="6769a-253">Atualização do firmware da Base do Surface Book</span><span class="sxs-lookup"><span data-stu-id="6769a-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="6769a-254">Adição de suporte para atualizações do firmware do Surface Dock com melhorias direcionadas a dispositivos Surface Book</span><span class="sxs-lookup"><span data-stu-id="6769a-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <a name="version-2.9.136.0"></a><span data-ttu-id="6769a-255">Versão2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="6769a-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="6769a-256">Data do lançamento: 3 de novembro de 2017</span><span class="sxs-lookup"><span data-stu-id="6769a-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="6769a-257">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="6769a-258">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="6769a-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="6769a-259">Resolve um problema de áudio sobre adaptadores de porta de exibição passiva</span><span class="sxs-lookup"><span data-stu-id="6769a-259">Resolves an issue with audio over passive display port adapters</span></span>

### <a name="version-2.1.15.0"></a><span data-ttu-id="6769a-260">Versão2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="6769a-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="6769a-261">Data do lançamento: 19 de junho de 2017</span><span class="sxs-lookup"><span data-stu-id="6769a-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="6769a-262">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="6769a-263">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="6769a-263">Surface Laptop</span></span>
* <span data-ttu-id="6769a-264">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="6769a-264">Surface Pro</span></span>

### <a name="version-2.1.6.0"></a><span data-ttu-id="6769a-265">Versão2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="6769a-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="6769a-266">Data do lançamento: 7 de abril de 2017</span><span class="sxs-lookup"><span data-stu-id="6769a-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="6769a-267">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="6769a-268">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="6769a-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="6769a-269">Requer o Windows 10</span><span class="sxs-lookup"><span data-stu-id="6769a-269">Requires Windows 10</span></span>

### <a name="version-2.0.22.0"></a><span data-ttu-id="6769a-270">Versão2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="6769a-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="6769a-271">Data do lançamento: 21 de outubro de 2016</span><span class="sxs-lookup"><span data-stu-id="6769a-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="6769a-272">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="6769a-273">Atualização do firmware do Surface Dock USB</span><span class="sxs-lookup"><span data-stu-id="6769a-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="6769a-274">Maior confiabilidade de portas Ethernet, áudio e USB</span><span class="sxs-lookup"><span data-stu-id="6769a-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <a name="version-1.0.8.0"></a><span data-ttu-id="6769a-275">Versão1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="6769a-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="6769a-276">Data do lançamento: 26 de abril de 2016</span><span class="sxs-lookup"><span data-stu-id="6769a-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="6769a-277">Esta versão do Surface Dock Updater adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6769a-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="6769a-278">Atualização do firmware do chipset principal do Surface Dock</span><span class="sxs-lookup"><span data-stu-id="6769a-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="6769a-279">Atualização do firmware do Surface Dock DisplayPort</span><span class="sxs-lookup"><span data-stu-id="6769a-279">Update for Surface Dock DisplayPort firmware</span></span>

