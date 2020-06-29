---
title: Wake on LAN para dispositivos Surface (Surface)
description: Veja como você pode usar o Wake on LAN para ativar dispositivos remotamente para executar tarefas de gerenciamento ou manutenção ou para habilitar as soluções de gerenciamento automaticamente – mesmo se os dispositivos estiverem desligados.
keywords: atualização, implantação, Driver, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830480"
---
# Wake On LAN para dispositivos Surface

Dispositivos Surface que executam o Windows 10, versão 1607 (também conhecida como atualização de aniversário do Windows 10) ou posterior e usam um adaptador Ethernet Surface para se conectar a uma rede com fio, são capazes de Wake on LAN (WOL) do modo de espera conectado. Com o WOL, você pode ativar dispositivos remotamente para executar tarefas de gerenciamento ou manutenção ou habilitar soluções de gerenciamento (como o Microsoft Endpoint Configuration Manager) automaticamente. Por exemplo, você pode implantar aplicativos em dispositivos de superfície à esquerda encaixados com um Dock Dock ou Surface Pro 3 Docking Station usando o Gerenciador de configuração do Microsoft Endpoint durante uma janela no meio da noite, quando o escritório está vazio.

>[!NOTE]
>Os dispositivos Surface devem estar conectados à alimentação CA e no modo de espera conectado (Sleep) para dar suporte ao WOL. O WOL não é possível em dispositivos que estejam em hibernação ou desligado.

## Dispositivos com suporte

Os seguintes dispositivos são compatíveis com o WOL:

* Adaptador Ethernet Surface
* Surface USB-C para Ethernet e adaptador USB
* Encaixe do Surface
* Estação de acoplamento Surface para Surface Pro 3
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface pro (5ª gen)
* Surface pro (5ª geração) com LTE Advanced
* Surface Book
* Laptop Surface (1ª gen)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go com LTE Avançado
* Surface Studio 2 (veja as instruções do Surface Studio 2 abaixo)
* Surface Pro 7
* Laptop Surface 3

## Driver WOL

Para habilitar o suporte a WOL em dispositivos Surface, é necessário um driver específico para o adaptador de Ethernet Surface. Este driver não está incluído no driver padrão e no pacote de firmware para dispositivos Surface – você deve baixá-lo e instalá-lo separadamente. Você pode baixar o driver WOL de Surface (SurfaceWOL.msi) na página [Surface Tools para it](https://www.microsoft.com/download/details.aspx?id=46703) no centro de download da Microsoft.

Você pode executar este arquivo do Microsoft Windows Installer (. msi) em um dispositivo Surface para instalar o driver WOL de Surface, ou pode distribuí-lo a dispositivos Surface com uma solução de implantação de aplicativo, como o Microsoft Endpoint Configuration Manager. Para incluir o driver WOL de Surface durante a implantação, você pode instalar o arquivo. msi como um aplicativo durante o processo de implantação. Você também pode extrair os arquivos de driver WOL da superfície para incluí-los no processo de implantação. Por exemplo, você pode incluí-los em seu compartilhamento de implantação do Microsoft Deployment Toolkit (MDT). Você pode ler mais sobre a implantação de superfície com [o MDT em implantar o Windows 10 em dispositivos de superfície com o kit de ferramentas de implantação da Microsoft](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).

> [!NOTE]
> Durante a instalação do SurfaceWOL.msi, a chave do registro a seguir é definida como um valor 1, que permite a fácil identificação de sistemas em que o driver WOL foi instalado. Se você optou por extrair e instalar esses drivers separadamente durante a implantação, essa chave do registro não será configurada e deve ser configurada manualmente ou com um script.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Para extrair o conteúdo de SurfaceWOL.msi, use a opção de instalação administrativa do MSIExec (**/a**), conforme mostrado no exemplo a seguir, para extrair o conteúdo para a pasta C:\WOL\:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Instruções do Surface Studio 2

Para habilitar o WOL no Surface Studio 2, você deve usar o procedimento a seguir

1. Crie as seguintes chaves do registro:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Execute o seguinte comando

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Usando o WOL da superfície

O driver WOL de Surface está em conformidade com o padrão WOL, no qual o dispositivo é wokendo por uma comunicação de rede especial conhecida como pacote mágico. O pacote mágico consiste em 6 bytes de 255 (ou FF em hexadecimal) seguido por 16 repetições do endereço MAC do computador de destino. Você pode ler mais sobre o pacote mágico e o padrão WOL na [Wikipédia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).

>[!NOTE]
>Para enviar um pacote mágico e ativar um dispositivo usando o WOL, você precisa saber o endereço MAC do dispositivo de destino e do adaptador Ethernet. Como o pacote mágico não usa o protocolo de rede IP, não é possível usar o endereço IP ou o nome DNS do dispositivo.

Muitas soluções de gerenciamento, como o Configuration Manager, fornecem suporte interno para WOL. Também há muitas soluções, incluindo aplicativos da Microsoft Store, módulos do PowerShell, aplicativos de terceiros e soluções de gerenciamento de terceiros que permitem que você envie um pacote mágico para ativar um dispositivo. Por exemplo, você pode usar o [módulo do PowerShell Wake on LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) a partir do TechNet Script Center. 

>[!NOTE]
>Depois que um dispositivo foi wokendo com um pacote mágico, o dispositivo retornará ao estado de suspensão se um aplicativo não estiver bloqueando ativamente a suspensão no sistema ou se a chave do registro AllowSystemRequiredPowerRequests não estiver configurada como 1, o que permite que os aplicativos impeçam a suspensão. Consulte a seção [Driver WOL](#wol-driver) deste artigo para obter mais informações sobre essa chave do registro.
