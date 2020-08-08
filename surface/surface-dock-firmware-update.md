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
ms.date: 8/07/2020
ms.openlocfilehash: 159eb4ca27bb867623020936276470ba9897f3b8
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918931"
---
# Atualização do firmware do Dock Surface da Microsoft: informações técnicas para administradores de ti

> [!IMPORTANT]
> Este artigo contém instruções técnicas para administradores de ti. Se você for um usuário doméstico, consulte [como atualizar o firmware do Dock Surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   no site de suporte da Microsoft. As instruções no site de suporte são as mesmas etapas gerais de instalação, mas este artigo tem informações adicionais para monitorar, verificar e implantar a atualização em vários dispositivos em uma rede.

Este artigo explica como usar a atualização do firmware do ensurface Dock da Microsoft para atualizar o firmware do Dock Surface. Quando instalado em seu dispositivo Surface, ele atualizará qualquer encaixe de superfície anexado ao seu dispositivo Surface. 

Esta ferramenta substitui a ferramenta anterior do atualizador do Microsoft Surface Dock, anteriormente disponível para download como parte das ferramentas de superfície para isso. A ferramenta anterior foi nomeada Surface_Dock_Updater_vx.xx.xxx.x.msi (em que x indica o número da versão) e não está mais disponível para download e não deve ser usada.

## Instalar a atualização do firmware do Surface Dock

Esta seção descreve como instalar manualmente a atualização de firmware.

> [!NOTE]
> A Microsoft lança periodicamente novas versões da atualização do firmware do Surface Dock. O arquivo MSI não está autoatualizável. Se você implantou o MSI em dispositivos de superfície e uma nova versão do firmware estiver liberada, será necessário implantar a nova versão.

1. Baixe e instale a [atualização do firmware do Microsoft Surface Dock](https://www.microsoft.com/download/details.aspx?id=46703).
    - A atualização requer um dispositivo de superfície executando o Windows 10, versão 1803 ou posterior.
    - Instalar o arquivo MSI pode solicitar que você reinicie a superfície. No entanto, não é necessário reiniciar para executar a atualização.

2. Desconecte o dispositivo Surface do Dock Dock, aguarde cerca de 5 segundos e, em seguida, reconecte-se. A atualização do firmware do Surface Dock atualizará o encaixe em modo silencioso em segundo plano. O processo pode levar alguns minutos para ser concluído e continuará mesmo que seja interrompido. 

## Monitorar a atualização do firmware do Surface Dock

Esta seção é opcional e fornece uma visão geral de como monitorar a instalação da atualização de firmware. 

Para monitorar a atualização:

1. Abra o Visualizador de eventos, navegue até **logs do Windows > aplicativo**e, em **ações** no painel à direita, clique em **Filtrar log atual**, digite **SurfaceDockFwUpdate** ao lado de **origens do evento**e clique em **OK**.

2. Digite o seguinte comando em um prompt de comando elevado:

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. Instale a atualização conforme descrito na [próxima seção](#install-the-surface-dock-firmware-update) deste artigo.
4. O evento 2007 com o seguinte texto indica uma atualização bem-sucedida: **atualização do firmware concluída. hr = 0 DriverTelementry EventCode = 2007**. 
    - Se a atualização não for bem-sucedida, a ID do evento 2007 será exibida como um evento de **erro** em vez de **informações**. Além disso, a versão relatada no registro do Windows não será atual.
5. Quando a atualização estiver completa, os valores DWORD atualizados serão exibidos no registro do Windows, correspondente à versão atual da ferramenta. Consulte a seção de [referência de versões](#versions-reference) neste artigo para obter detalhes. Por exemplo:
    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Se você vir "a descrição para a identificação do evento xxxx do SurfaceDockFwUpdate de origem não pode ser encontrado" no texto do evento, isso é esperado e pode ser ignorado.

Além disso, Confira as seções a seguir neste artigo: 
  - [Como verificar a conclusão da atualização do firmware](#how-to-verify-completion-of-the-firmware-update)
  - [Log de eventos](#event-logging)
  - [Dicas para solução de problemas](#troubleshooting-tips)
  - [Referência de versões](#versions-reference)

## Implantação de rede

Você pode usar os comandos do Windows Installer (Msiexec.exe) para implantar a atualização do firmware do Surface Dock em vários dispositivos em sua rede. Ao usar o Gerenciador de configuração do Microsoft Endpoint ou outra ferramenta de implantação, insira a seguinte sintaxe para garantir que a instalação seja silenciosa:

- **Msiexec.exe/i \<path to msi file\> /quiet/norestart** 

  Por exemplo:
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > Um arquivo de log não é criado por padrão. Para criar um arquivo de log, você precisará acrescentar "/l*v [caminho]". Por exemplo: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI. log "

  Para obter mais informações, consulte a documentação de [Opções de linha de comando](https://docs.microsoft.com/windows/win32/msi/command-line-options) .

> [!IMPORTANT]
> Se você quiser manter o encaixe de superfície atualizado usando qualquer outro método, consulte [atualizar seu Dock Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obter detalhes.

## Implantação do Intune

Você pode usar o Intune para distribuir a atualização do firmware do Surface Dock para seus dispositivos. Primeiro, você precisará converter o arquivo MSI no formato. intunewin, conforme descrito na documentação a seguir: [Intune standalone-gerenciamento de aplicativos Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).

Use o seguinte comando:
  - **msiexec/i \<path to msi file\> /Quiet/q**

## Como verificar a conclusão da atualização do firmware

O firmware do Dock Surface consiste em dois componentes:

- **Component10:** Firmware da micro controller Unit (MCU)
- **Component20:** Firmware de porta de vídeo (DP).

A conclusão bem-sucedida da atualização do firmware do Surface Dock resulta em novos valores de chave do registro para estes componentes de firmware.

**Para verificar as atualizações:**

1. Abra o regedit e navegue até o seguinte caminho de registro:

    - **HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Procure as chaves do registro: **Component10CurrentFwVersion e Component20CurrentFwVersion**, que se referem ao firmware que está atualmente no dispositivo.

   ![Processo de instalação da atualização do firmware do Surface Dock](images/regeditDock.png)

3. Verifique se os novos valores da chave do registro correspondem aos valores de chave do registro atualizados listados na referência versões no final deste documento. Se os valores corresponderem, o firmware foi atualizado com êxito.

4. Se não for possível verificar, revise as dicas de solução de problemas e log de eventos na próxima seção.

## Log de eventos

**Tabela 1. Arquivos de log para atualização do firmware do Surface Dock**

| Log                              | Location                               | Observações                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Log de atualização do firmware do Surface Dock | O caminho deve ser especificado (veja a observação) | Versões anteriores dessa ferramenta escreveram eventos para aplicativos e serviços que o Logs\Microsoft Surface Dock para o Updater.                                                                                                  |
| Log de instalação do dispositivo do Windows       | %windir%\inf\setupapi.dev.log           | Para obter mais informações sobre como usar o log de instalação do dispositivo, consulte documentação de [log setupapi](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) . |


**Tabela 2. IDs de log de eventos para atualização do firmware do Surface Dock**<br>
Os eventos são registrados no log de eventos do aplicativo.  Observação: as versões anteriores dessa ferramenta escreveram eventos para aplicativos e serviços que o Logs\Microsoft Surface Dock redater.

| Event ID | Event type                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | A atualização de firmware Dock foi iniciada.                                    |
| 2002     | Encaixar atualização de firmware ignorada porque o encaixe é conhecido como atualizado. |
| 2003     | Falha na atualização do firmware Dock para obter a versão do firmware.                 |
| 2004     | Consultando a versão do firmware.                                       |
| 2005     | Falha no firmware Dock ao iniciar a atualização.                                |
| 2006     | Falha ao enviar pares de oferta/carga.                                  |
| 2007     | Atualização do firmware concluída.                                            |
| 2008     | Comece a encaixar telemetria.                                                |
| 2011     | Encaixar telemetria encaixada.                                                  |

## Dicas para solução de problemas

- Desconecte completamente a alimentação do Surface Dock da alimentação CA para redefinir o Dock Surface.
- Desconecte todos os periféricos, exceto para o encaixe de superfície.
- Desinstale qualquer atualização de firmware do Dock Surface atual e instale a versão mais recente.
- Verifique se o cais Surface está desconectado e, em seguida, deixe tempo suficiente para que a atualização seja concluída conforme monitorado via LED na porta Ethernet do Dock. Aguarde até que o LED pare de piscar antes de desconectar o encaixe de superfície da energia.
- Conecte o encaixe de superfície a um dispositivo diferente para ver se ele pode atualizar o Dock.

## Referência de versões

>[!NOTE]
>O arquivo de instalação é lançado com o seguinte formato de nomenclatura: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) e é instalado por padrão para C:\Program Files\SurfaceUpdate.

### Versão 1.53.139.0
*Data do lançamento: 4 de agosto de 2020*

Esta versão da atualização do firmware do Surface Dock inclui correções de bugs e suporte para:
- Atualização do Surface Dock 1 usando Surface Pro X. 
   > [!NOTE]
   > Se você estiver executando o Surface Pro X, baixe o. Compilação ARM64. Para todos os outros dispositivos, use a compilação AMD64. 
 


### Versão 1.42.139 
*Data do lançamento: setembro de 18 2019*

Esta versão, contida em Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, atualiza o firmware em segundo plano. 
**Valores atualizados da chave do registro:**<br>

- Component10CurrentFwVersion atualizado para **4ac3970**.
- Component20CurrentFwVersion atualizado para **4a1d570**.

Ele adiciona suporte para Surface Pro 7 e Surface laptop 3.

## Versões herdadas

### Versão 2.23.139.0
*Data do lançamento: 10 de outubro de 2018*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Adicionar suporte para Surface pro 6
- Adicionar suporte para o laptop 2 Surface


### Versão 2.22.139.0
*Data do lançamento: 26 de julho de 2018*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Aumentar a confiabilidade da atualização
- Adicionar suporte para a superfície go

### Versão2.12.136.0
*Data do lançamento: 29 de janeiro de 2018*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:
* Atualização do firmware do chipset principal do Surface Dock
* Atualização do firmware do Surface Dock DisplayPort
* Estabilidade aprimorada para vídeos externos quando usados com o Surface Book ou o Surface Book 2

Além disso, a instalação desta versão do Surface Dock Updater em dispositivos Surface Book inclui o seguinte:
* Atualização do firmware da Base do Surface Book
* Adição de suporte para atualizações do firmware do Surface Dock com melhorias direcionadas a dispositivos Surface Book


### Versão2.9.136.0
*Data do lançamento: 3 de novembro de 2017*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

* Atualização do firmware do Surface Dock DisplayPort
* Resolve um problema de áudio sobre adaptadores de porta de exibição passiva

### Versão2.1.15.0
*Data do lançamento: 19 de junho de 2017*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

* Surface Laptop
* Surface Pro

### Versão2.1.6.0
*Data do lançamento: 7 de abril de 2017*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

* Atualização do firmware do Surface Dock DisplayPort
* Requer o Windows 10

### Versão2.0.22.0
*Data do lançamento: 21 de outubro de 2016*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

* Atualização do firmware do Surface Dock USB
* Maior confiabilidade de portas Ethernet, áudio e USB

### Versão1.0.8.0
*Data do lançamento: 26 de abril de 2016*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

* Atualização do firmware do chipset principal do Surface Dock
* Atualização do firmware do Surface Dock DisplayPort

