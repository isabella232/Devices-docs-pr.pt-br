---
title: Atualização de firmware do Microsoft Surface Dock 1
description: Este artigo explica como usar a Atualização de Firmware do Microsoft Surface Dock para instalar e gerenciar o firmware no Surface Dock 1 original. Quando instalado em seu dispositivo Surface, ele atualizará os dispositivos Surface Dock 1 anexados ao dispositivo Surface.
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
ms.date: 10/25/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 8d714ad9e7d301b4691655faaf9e39b0f4147301
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449374"
---
# <a name="surface-dock-1-firmware-update"></a>Atualização de firmware do Surface Dock 1

Este artigo explica como usar a Atualização de Firmware do Microsoft Surface Dock 1 para instalar e gerenciar o firmware no Surface Dock 1 original. Quando instalado em seu dispositivo Surface, ele atualizará os dispositivos Surface Dock 1 anexados ao dispositivo Surface.

> [!NOTE]
> Este artigo não se aplica ao [Surface Dock 2](surface-dock-whats-new.md), que recebe atualizações automaticamente por meio do Windows Update ou usando Microsoft Endpoint Configuration Manager ou outras ferramentas de implantação MSI.

Essa ferramenta sobressupa a ferramenta anterior do Microsoft Surface Dock Updater, disponível anteriormente para download como parte do Surface Tools para IT. A ferramenta anterior foi nomeada Surface_Dock_Updater_vx.xx.xxx.x.msi (onde x indica o número da versão) e não está mais disponível para download e não deve ser usada.

> [!IMPORTANT]
> Este artigo contém instruções técnicas para administradores de IT. Se você for um usuário de residência, confira [Como atualizar seu Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)  do Surface Dock no site de Suporte da Microsoft. As instruções no site de suporte são as mesmas das etapas gerais de instalação abaixo, mas este artigo tem informações adicionais para monitoramento, verificação e implantação da atualização em vários dispositivos em uma rede.

## <a name="supported-devices"></a>Dispositivos com suporte

A Atualização de Firmware do Surface Dock 1 tem suporte nos seguintes dispositivos:

- Surface Pro 3 e posterior
- Surface Pro X (todas as gerações)
- Surface 3
- Surface Book (todas as gerações)
- Surface Laptop Studio
- Surface Studio (todas as gerações)
- Surface Laptop (todas as gerações)
- Surface Laptop Go
- Surface Go (todas as gerações)

### <a name="minimum-os-requirement"></a>Requisito mínimo do sistema operacional

- Windows 10, versão 1803 ou posterior

## <a name="install-surface-dock-1-firmware-update"></a>Instalar a Atualização de Firmware do Surface Dock 1

Esta seção descreve como instalar manualmente a atualização de firmware no Surface Dock 1.

> [!TIP]
> A Microsoft lança periodicamente novas versões do Surface Dock 1 Firmware Update. O arquivo MSI não está se atualizando. Se você tiver implantado o MSI em dispositivos Surface e uma nova versão do firmware for lançada, será necessário implantar a nova versão.

1. Vá para [o Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) e baixe e instale o arquivo .msi chamado **Surface_Dock_FwUpdate..**, seguido pela versão apropriada. Se você estiver executando Surface Pro X, baixe a com build **.arm64**. Para todos os outros dispositivos, use a **com build .amd64** .  

    - A atualização requer um dispositivo Surface executando Windows 10, versão 1803 ou posterior.
    - Instalar o arquivo MSI pode solicitar que você reinicie o Surface. No entanto, a reinicialização não é necessária para executar a atualização.

2. Desconecte o dispositivo Surface do Surface Dock, aguarde ~5 segundos e reconectar. A Atualização de Firmware do Surface Dock 1 atualizará o encaixe silenciosamente em segundo plano. O processo pode levar alguns minutos para ser concluído e continuará mesmo que interrompido.

## <a name="monitor-the-surface-dock-1-firmware-update"></a>Monitorar a Atualização de Firmware do Surface Dock 1

Esta seção é opcional e fornece uma visão geral de como monitorar a instalação da atualização de firmware.

Para monitorar a atualização:

1. Abra o Visualizador de Eventos, navegue até Windows **Logs > Application** e, em Ações no painel direito****, clique em Filtrar **Log** Atual, insira **SurfaceDockFwUpdate** ao lado de Fontes de Eventos e **** clique em **OK**.

2. Digite o seguinte comando em um prompt de comando elevado:

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```

3. Instale a atualização conforme descrito na [próxima seção](#install-surface-dock-1-firmware-update) deste artigo.

4. O evento 2007 com o seguinte texto indica uma atualização bem-sucedida: **atualização de firmware concluída. hr=0 DriverTelementry EventCode = 2007**.

   Se a atualização não for bem-sucedida, a ID do evento 2007 será exibida como um evento **Error** em vez de **Informações**. Além disso, a versão relatada na Windows Registro não será atual.

5. Quando a atualização for concluída, os valores DWORD atualizados serão exibidos no Registro Windows, correspondendo à versão atual da ferramenta. Consulte a [seção de referência](#versions-reference) Versões deste artigo para obter detalhes. Por exemplo:

    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Se você vir "A descrição da ID do Evento xxxx da origem SurfaceDockFwUpdate não pode ser encontrada" no texto do evento, isso é esperado e pode ser ignorado.

Consulte também as seguintes seções neste artigo:

- [Como verificar a conclusão da atualização de firmware](#how-to-verify-completion-of-the-firmware-update)
  - [Log de eventos](#event-logging)
  - [Dicas para solução de problemas](#troubleshooting-tips)
  - [Referência de versões](#versions-reference)

## <a name="network-deployment"></a>Implantação de rede

Você pode usar Windows comandos do Instalador (Msiexec.exe) para implantar a Atualização de Firmware do Surface Dock 1 em vários dispositivos em sua rede. Ao usar Microsoft Endpoint Configuration Manager ou outra ferramenta de implantação, insira a seguinte sintaxe para garantir que a instalação seja silenciosa:

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart**

Por exemplo:

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> Um arquivo de log não é criado por padrão. Para criar um arquivo de log, você precisará anexar "/*lv [caminho]". Por exemplo: Msiexec.exe /i /lv \<path to msi file\>*%windir%\logs\ SurfaceDockFWI.log"

Para obter mais informações, consulte a [documentação de opções de linha de](/windows/win32/msi/command-line-options) comando.

> [!IMPORTANT]
> Se você quiser manter o Surface Dock atualizado usando qualquer outro método, consulte [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obter detalhes.

## <a name="intune-deployment"></a>Implantação do Intune

Você pode usar o Intune para distribuir a Atualização de Firmware do Surface Dock 1 para seus dispositivos. Primeiro, você precisará converter o arquivo MSI no formato .intunewin, conforme descrito na documentação a seguir: Gerenciamento de aplicativos [Do Intune Autônomo - Win32](/intune/apps/apps-win32-app-management).

Use o seguinte comando:

- **msiexec /i \<path to msi file\> /quiet /q**

## <a name="how-to-verify-completion-of-the-firmware-update"></a>Como verificar a conclusão da atualização de firmware

O firmware do surface dock consiste em dois componentes:

- **Component10:** Firmware da unidade de micro controlador (MCU)
- **Component20:** Firmware de porta de exibição (DP).

A conclusão bem-sucedida da Atualização de Firmware do Surface Dock 1 resulta em novos valores principais do Registro para esses componentes de firmware.

### <a name="to-verify-updates"></a>Para verificar atualizações

1. Abra Regedit e navegue até o seguinte caminho do Registro:

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Procure as chaves do Registro: **Component10CurrentFwVersion e Component20CurrentFwVersion**, que se referem ao firmware que está atualmente no dispositivo.

   ![Processo de instalação do Surface Dock 1 Firmware Update.](images/regeditDock.png)

3. Verifique se os novos valores de chave do Registro corresponderão aos valores de chave do Registro atualizados listados na referência Versões no final deste documento. Se os valores corresponderem, o firmware foi atualizado com êxito.

4. Se não for possível verificar, revise o log de eventos e as dicas de solução de problemas na próxima seção.

## <a name="event-logging"></a>Log de eventos

### <a name="table-1-log-files-for-surface-dock-1-firmware-update"></a>Tabela 1. Arquivos de log para Atualização de Firmware do Surface Dock 1

| Log                              | Location                               | Observações                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Log de Atualização de Firmware do Surface Dock 1 | O caminho precisa ser especificado (consulte observação) | Versões anteriores desta ferramenta escreveram eventos para Logs de Aplicativos e Serviços\Microsoft Surface Dock Updater.                                                                                                  |
| Windows de instalação de dispositivo       | %windir%\inf\setupapi.dev.log           | Para obter mais informações sobre como usar o Log de Instalação do Dispositivo, consulte a [documentação de Registro em Log de InstalaçãoAPI](/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) . |

### <a name="table-2-event-log-ids-for-surface-dock-1-firmware-update"></a>Tabela 2. IDs de log de eventos para Atualização de Firmware do Surface Dock 1

Os eventos são registrados no Log de Eventos do Aplicativo.  Observação: versões anteriores desta ferramenta escreveram eventos para Logs de Aplicativos e Serviços\Microsoft Surface Dock Updater.

| Event ID | Event type                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | A atualização de firmware do dock foi iniciada.                                    |
| 2002     | Atualização de firmware do dock ignorada porque o dock é conhecido por estar atualizado. |
| 2003     | A atualização de firmware do dock falhou ao obter a versão do firmware.                 |
| 2004     | Consultando a versão do firmware.                                       |
| 2005     | Falha ao iniciar a atualização do firmware do dock.                                |
| 2006     | Falha ao enviar pares de oferta/carga.                                  |
| 2007     | Atualização de firmware concluída.                                            |
| 2008     | Telemetria de encaixe BEGIN.                                                |
| 2011     | Telemetria do dock END.                                                  |

## <a name="troubleshooting-tips"></a>Dicas para solução de problemas

- Desconecte completamente a energia do encaixe Surface da energia ac para redefinir o Surface Dock.
- Desconecte todos os periféricos, exceto o Surface Dock.
- Desinstale qualquer Atualização de Firmware atual do Surface Dock 1 e instale a versão mais recente.
- Verifique se o Surface Dock está desconectado e, em seguida, permita tempo suficiente para que a atualização seja concluída como monitorada por meio de um LED na porta Ethernet do dock. Aguarde até que o LED pare de piscar antes de desligar o Surface Dock da energia.
- Conexão o Surface Dock para um dispositivo diferente para ver se ele é capaz de atualizar o dock.

## <a name="versions-reference"></a>Referência de versões

>[!NOTE]
>O arquivo de instalação é lançado com o seguinte formato de nome: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) e é instalado por padrão em C:\Program Files\SurfaceUpdate.

### <a name="version-1531390"></a>Versão 1.53.139.0

#### <a name="release-date-august-4-2020"></a>Data de lançamento: 4 de agosto de 2020

Esta versão da Atualização de Firmware do Surface Dock 1 inclui correções de bugs e suporte para:

- Atualizando o Surface Dock 1 usando Surface Pro X.

#### <a name="registry-key-values"></a>Valores principais do Registro

Os valores do Registro que indicam o status das atualizações de firmware não são alterados da versão anterior desta ferramenta:

- Component10CurrentFwVersion atualizado para **4ac3970**.
- Component20CurrentFwVersion atualizado para **4a1d570**.

### <a name="version-142139"></a>Versão 1.42.139

#### <a name="release-date-september-18-2019"></a>Data do lançamento: 18 de setembro de 2019

Esta versão, contida no Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, atualiza o firmware em segundo plano.

#### <a name="updated-registry-key-values"></a>Valores de chave do Registro atualizados

- Component10CurrentFwVersion atualizado para **4ac3970**.
- Component20CurrentFwVersion atualizado para **4a1d570**.

Ele adiciona suporte para Surface Pro 7 e Surface Laptop 3.

## <a name="legacy-versions"></a>Versões herdadas

### <a name="version-2231390"></a>Versão 2.23.139.0

#### <a name="release-date-10-october-2018"></a>Data do lançamento: 10 de outubro de 2018

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Adicionar suporte para Surface Pro 6
- Adicionar suporte para Surface Laptop 2

### <a name="version-2221390"></a>Versão 2.22.139.0

#### <a name="release-date-26-july-2018"></a>Data do lançamento: 26 de julho de 2018

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Aumentar a confiabilidade da atualização
- Adicionar suporte ao Surface Go

### <a name="version-2121360"></a>Versão2.12.136.0

#### <a name="release-date-29-january-2018"></a>Data do lançamento: 29 de janeiro de 2018

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Atualização do firmware do chipset principal do Surface Dock

- Atualização do firmware do Surface Dock DisplayPort

- Estabilidade aprimorada para vídeos externos quando usados com o Surface Book ou o Surface Book 2

Além disso, a instalação desta versão do Surface Dock Updater em dispositivos Surface Book inclui o seguinte:

- Atualização do firmware da Base do Surface Book

- Adição de suporte para atualizações do firmware do Surface Dock com melhorias direcionadas a dispositivos Surface Book

### <a name="version-291360"></a>Versão2.9.136.0

#### <a name="release-date-november-3-2017"></a>Data do lançamento: 3 de novembro de 2017

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Atualização do firmware do Surface Dock DisplayPort

- Resolve um problema de áudio sobre adaptadores de porta de exibição passiva

### <a name="version-21150"></a>Versão2.1.15.0

#### <a name="release-date-june-19-2017"></a>Data do lançamento: 19 de junho de 2017

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Surface Laptop

- Surface Pro

### <a name="version-2160"></a>Versão2.1.6.0

#### <a name="release-date-april-7-2017"></a>Data do lançamento: 7 de abril de 2017

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Atualização do firmware do Surface Dock DisplayPort

- Requer o Windows 10

### <a name="version-20220"></a>Versão2.0.22.0

#### <a name="release-date-october-21-2016"></a>Data do lançamento: 21 de outubro de 2016

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Atualização do firmware do Surface Dock USB

- Maior confiabilidade de portas Ethernet, áudio e USB

### <a name="version-1080"></a>Versão1.0.8.0

#### <a name="release-date-april-26-2016"></a>Data do lançamento: 26 de abril de 2016

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Atualização do firmware do chipset principal do Surface Dock

- Atualização do firmware do Surface Dock DisplayPort
