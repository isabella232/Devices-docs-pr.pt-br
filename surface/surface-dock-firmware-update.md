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
# Atualização do firmware do Microsoft Surface Dock

> [!IMPORTANT]
> Este artigo contém instruções técnicas para administradores de IT. Se você for um usuário local, veja como atualizar [o firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)do Surface Dock no site de suporte da   Microsoft. As instruções no site de suporte são as mesmas das etapas gerais de instalação abaixo, mas este artigo tem informações adicionais para monitoramento, verificação e implantação da atualização em vários dispositivos em uma rede.

Este artigo explica como usar a Atualização de Firmware do Microsoft Surface Dock para instalar e gerenciar o firmware no Surface Dock 1 original. Quando instalado no dispositivo Surface, ele atualizará os dispositivos Surface Dock 1 conectados ao dispositivo Surface.

> [!NOTE]
> Este artigo não se aplica ao Surface Dock 2, que recebe atualizações automaticamente por meio do Windows Update ou usando o Microsoft Endpoint Configuration Manager ou outras ferramentas de implantação MSI. Para saber mais, confira [Novidades no Surface Dock.](surface-dock-whats-new.md)

Essa ferramenta sobressupa a ferramenta Anterior do Microsoft Surface Dock Updater, disponível anteriormente para download como parte das Ferramentas do Surface para IT. A ferramenta anterior foi nomeada Surface_Dock_Updater_vx.xx.xxx.x.msi (onde x indica o número da versão) e não está mais disponível para download e não deve ser usada.

## Instalar a Atualização do Firmware do Surface Dock

Esta seção descreve como instalar manualmente a atualização de firmware.

> [!NOTE]
> A Microsoft lança periodicamente novas versões da Atualização do Firmware do Surface Dock. O arquivo MSI não está sendo atualizado. Se você tiver implantado o MSI em dispositivos Surface e uma nova versão do firmware for lançada, será necessário implantar a nova versão.

1. Baixe e instale a [Atualização de Firmware do Microsoft Surface Dock.](https://www.microsoft.com/download/details.aspx?id=46703)
    - A atualização requer um dispositivo Surface que executa o Windows 10, versão 1803 ou posterior.
    - A instalação do arquivo MSI pode solicitar que você reinicie o Surface. No entanto, não é necessário reiniciar para executar a atualização.

2. Desconecte o dispositivo Surface do Surface Dock, aguarde cerca de 5 segundos e reconecte-se. A Atualização do Firmware do Surface Dock atualizará o encaixe silenciosamente em segundo plano. O processo pode levar alguns minutos para ser concluído e continuará mesmo se interrompido. 

## Monitorar a atualização do firmware do Surface Dock

Esta seção é opcional e fornece uma visão geral de como monitorar a instalação da atualização do firmware. 

Para monitorar a atualização:

1. Abra o Visualizador de Eventos, navegue até Logs **** do **Windows > Aplicativo**e, em Ações no painel direito, **** clique em Filtrar **Log**Atual, insira **SurfaceDockFwUpdate** ao lado das fontes de eventos e clique em **OK.**

2. Digite o seguinte comando em um prompt de comando com elevação:

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. Instale a atualização conforme descrito na [próxima seção](#install-the-surface-dock-firmware-update) deste artigo.

4. O evento 2007 com o seguinte texto indica uma atualização bem-sucedida: Atualização de **firmware concluída. hr=0 DriverTelementry EventCode = 2007**. 

   Se a atualização não for bem-sucedida, a ID do evento 2007 será exibida como um evento **Error** em vez de **Informações.** Além disso, a versão relatada no Registro do Windows não será atual.
   
5. Quando a atualização for concluída, os valores DWORD atualizados serão exibidos no Registro do Windows, correspondentes à versão atual da ferramenta. Consulte a [seção de referência](#versions-reference) de versões neste artigo para obter detalhes. Por exemplo:

    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Se você vir "A descrição da ID de evento xxxx da origem SurfaceDockFwUpdate não pode ser encontrada" no texto do evento, isso é esperado e pode ser ignorado.

Consulte também as seções a seguir neste artigo: 
  - [Como verificar a conclusão da atualização de firmware](#how-to-verify-completion-of-the-firmware-update)
  - [Log de eventos](#event-logging)
  - [Dicas para solução de problemas](#troubleshooting-tips)
  - [Referência de versões](#versions-reference)

## Implantação de rede

Você pode usar comandos do Windows Installer (Msiexec.exe) para implantar a Atualização do Firmware do Surface Dock em vários dispositivos em sua rede. Ao usar o Microsoft Endpoint Configuration Manager ou outra ferramenta de implantação, insira a seguinte sintaxe para garantir que a instalação seja silenciosa:

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart** 

Por exemplo:

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> Um arquivo de log não é criado por padrão. Para criar um arquivo de log, você precisará anexar "/l*v [caminho]". Por exemplo: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"

Para obter mais informações, consulte a [documentação de opções de linha de](https://docs.microsoft.com/windows/win32/msi/command-line-options) comando.

> [!IMPORTANT]
> Se você quiser manter o Surface Dock atualizado usando qualquer outro método, consulte [Atualizar o Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obter detalhes.

## Implantação do Intune

Você pode usar o Intune para distribuir a Atualização do Firmware do Surface Dock para seus dispositivos. Primeiro, você precisará converter o arquivo MSI para o formato .intunewin, conforme descrito na seguinte documentação: Intune Autônomo - gerenciamento de [aplicativos Win32.](https://docs.microsoft.com/intune/apps/apps-win32-app-management)

Use o seguinte comando:
  - **msiexec /i \<path to msi file\> /quiet /q**

## Como verificar a conclusão da atualização do firmware

O firmware do Surface Dock consiste em dois componentes:

- **Component10:** Firmware da unidade de micro controlador (MCU)
- **Component20:** Firmware de porta de exibição (DP).

A conclusão bem-sucedida da Atualização do Firmware do Surface Dock resulta em novos valores de chave do Registro para esses componentes de firmware.

**Para verificar as atualizações:**

1. Abra Regedit e navegue até o seguinte caminho do Registro:

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Procure as chaves do Registro: **Component10CurrentFwVersion e Component20CurrentFwVersion**, que se referem ao firmware que está atualmente no dispositivo.

   ![Processo de instalação da Atualização do Firmware do Surface Dock](images/regeditDock.png)

3. Verifique se os novos valores de chave do Registro corresponderão aos valores de chave do Registro atualizados listados na referência Versões no final deste documento. Se os valores corresponderem, o firmware foi atualizado com êxito.

4. Se não for possível verificar, revise o log de eventos e as dicas de solução de problemas na próxima seção.

## Log de eventos

**Tabela 1. Arquivos de log da Atualização do Firmware do Surface Dock**

| Log                              | Location                               | Observações                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Log de Atualização do Firmware do Surface Dock | O caminho precisa ser especificado (consulte a observação) | Versões anteriores desta ferramenta escreveram eventos nos Logs de Aplicativos e Serviços\Microsoft Surface Dock Updater.                                                                                                  |
| Log de instalação de dispositivos Windows       | %windir%\inf\setupapi.dev.log           | Para obter mais informações sobre como usar o Log de Instalação de Dispositivo, consulte a documentação de [Log de SetupAPI.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) |


**Tabela 2. IDs do log de eventos para a Atualização do Firmware do Surface Dock**<br>
Os eventos são registrados no Log de Eventos do Aplicativo.  Observação: as versões anteriores desta ferramenta escreveram eventos nos Logs de Aplicativos e Serviços\Microsoft Surface Dock Updater.

| Event ID | Event type                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | A atualização do firmware do Dock foi iniciada.                                    |
| 2002     | Atualização do firmware do Dock ignorada porque o dock é conhecido por estar atualizado. |
| 2003     | Falha ao obter a versão do firmware da atualização do firmware do Dock.                 |
| 2004     | Consultando a versão do firmware.                                       |
| 2005     | Falha do firmware do Dock ao iniciar a atualização.                                |
| 2006     | Falha ao enviar pares de oferta/carga.                                  |
| 2007     | Atualização do firmware concluída.                                            |
| 2008     | Telemetria begin dock.                                                |
| 2011     | Telemetria do encaixe FINAL.                                                  |

## Dicas para solução de problemas

- Desconecte completamente a energia do Surface Dock da energia CA para redefinir o Surface Dock.
- Desconecte todos os periféricos, exceto o Surface Dock.
- Desinstale qualquer Atualização atual do firmware do Surface Dock e instale a versão mais recente.
- Verifique se o Surface Dock está desconectado e, em seguida, deixe tempo suficiente para que a atualização seja concluída conforme monitorado por meio de um LED na porta Ethernet do encaixe. Aguarde até que o LED pare de piscar antes de desconectar o Surface Dock da energia.
- Conecte o Surface Dock a um dispositivo diferente para ver se ele é capaz de atualizar o encaixe.

## Referência de versões

>[!NOTE]
>O arquivo de instalação é lançado com o seguinte formato de nomeação: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (por exemplo: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) e é instalado por padrão em C:\Arquivos de Programas\SurfaceUpdate.

### Versão 1.53.139.0
*Data do lançamento: 4 de agosto de 2020*

Esta versão da Atualização do Firmware do Surface Dock inclui correções de bugs e suporte para:
- Atualizando o Surface Dock 1 usando o Surface Pro X. 
   > [!NOTE]
   > Se você estiver executando o Surface Pro X, baixe o . Build ARM64. Para todos os outros dispositivos, use a com build AMD64. 

#### Valores de chave do Registro

Os valores do Registro que indicam o status das atualizações de firmware não foram alterados em relação à versão anterior desta ferramenta: 

- Component10CurrentFwVersion atualizado para **4ac3970**.
- Component20CurrentFwVersion atualizado para **4a1d570**.
 
### Versão 1.42.139 
*Data do lançamento: 18 de setembro de 2019*

Essa versão, contida no Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, atualiza o firmware em segundo plano. 

#### Valores de chave do Registro atualizados

- Component10CurrentFwVersion atualizado para **4ac3970**.
- Component20CurrentFwVersion atualizado para **4a1d570**.

Ele adiciona suporte para o Surface Pro 7 e o Surface Laptop 3.

## Versões herdadas

### Versão 2.23.139.0
*Data do lançamento: 10 de outubro de 2018*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Adicionar suporte para o Surface Pro 6
- Adicionar suporte para o Surface Laptop 2


### Versão 2.22.139.0
*Data do lançamento: 26 de julho de 2018*

Esta versão do Surface Dock Updater adiciona suporte para o seguinte:

- Aumentar a confiabilidade da atualização
- Adicionar suporte para o Surface Go

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

