---
title: Wake On LAN para dispositivos Surface (Surface)
description: Veja como você pode usar o Wake On LAN para acioná-los remotamente para realizar tarefas de gerenciamento ou manutenção ou para habilitar soluções de gerenciamento automaticamente, mesmo que os dispositivos sejam desligados.
keywords: atualizar, implantar, driver, ltd, wake-on-lan
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
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271118"
---
# Wake On LAN para dispositivos Surface

Dispositivos Surface que executem o Windows 10, versão 1607 (também conhecido como Atualização de Aniversário do Windows 10) ou posterior e usam um adaptador Ethernet do Surface para se conectar a uma rede com fio, são capazes de Wake On LAN (ETHERNET) do Modo de Espera Conectado. Com o DRAG, você pode ativar remotamente os dispositivos para executar tarefas de gerenciamento ou manutenção ou habilitar soluções de gerenciamento (como o Microsoft Endpoint Configuration Manager) automaticamente. Por exemplo, você pode implantar aplicativos em dispositivos Surface à esquerda encaixados com um Surface Dock ou Uma Base de Encaixe do Surface Pro 3 usando o Microsoft Endpoint Configuration Manager durante uma janela no meio da noite, quando o escritório estiver vazio.

>[!NOTE]
>Os dispositivos Surface devem estar conectados à alimentação AC e em modo de espera conectado ( sleep) para dar suporte a BLUETOOTH. NÃO é possível com dispositivos que estão em hibernação ou desligados.

## Dispositivos com suporte

Os seguintes dispositivos são compatíveis com o BLUETOOTH:

* Adaptador Ethernet Surface
* Surface USB-C para Ethernet e adaptador USB
* Encaixe do Surface
* Base de Encaixe do Surface para Surface Pro 3
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (5ª geração)
* Surface Pro (5ª geração) com LTE Avançado
* Surface Book
* Surface Laptop (1ª geração)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go com LTE Avançado
* Surface Studio 2 (consulte as instruções do Surface Studio 2 abaixo)
* Surface Pro 7
* Surface Laptop 3
* Surface Laptop Go
* Surface Pro 7+

## Driver DELM

Para habilitar o suporte a ETHERNET em dispositivos Surface, é necessário um driver específico para o adaptador Ethernet do Surface. Esse driver não está incluído no pacote de firmware e driver padrão para dispositivos Surface – você deve baixá-lo e instalá-lo separadamente. Você pode baixar o driver SURFACE SURFACE (SurfaceWOL.msi) na página Ferramentas do [Surface para](https://www.microsoft.com/download/details.aspx?id=46703) TI no Centro de Download da Microsoft.

Você pode executar esse arquivo do Microsoft Windows Installer (.msi) em um dispositivo Surface para instalar o driver SURFACE USB ou distribuí-lo para dispositivos Surface com uma solução de implantação de aplicativo, como o Microsoft Endpoint Configuration Manager. Para incluir o driver DO SURFACE SURFACE DURANTE A implantação, você pode instalar o arquivo .msi como um aplicativo durante o processo de implantação. Você também pode extrair os arquivos de driver DO SURFACE LTD para incluí-los no processo de implantação. Por exemplo, você pode incluí-los no compartilhamento de implantação do Microsoft Deployment Toolkit (MDT). Você pode ler mais sobre a implantação do Surface com o MDT em Implantar o Windows 10 em dispositivos [Surface com o Microsoft Deployment Toolkit.](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)

> [!NOTE]
> Durante a instalação do SurfaceWOL.msi, a chave do Registro a seguir é definida como um valor 1, o que permite a identificação fácil de sistemas em que o driver DOLS foi instalado. Se você optar por extrair e instalar esses drivers separadamente durante a implantação, essa chave do Registro não será configurada e deverá ser configurada manualmente ou com um script.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Para extrair o conteúdo do SurfaceWOL.msi, use a opção de instalação administrativa MSIExec (**/a**), conforme mostrado no exemplo a seguir, para extrair o conteúdo para a pasta C:\IBM\:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Instruções do Surface Studio 2

Para habilitar o RECURSO NO Surface Studio 2, você deve usar o procedimento a seguir

1. Crie as seguintes chaves do Registro:

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

## Usando o Surface SURFACE SURFACE

O driver SURFACEFORM está em conformidade com o padrão PORTAL, por meio do qual o dispositivo é comunicado por uma comunicação de rede especial conhecida como um pacote mágico. O pacote clássico consiste em 6 bytes de 255 (ou FF em hexadecimal) seguidos por 16 repetições do endereço MAC do computador de destino. Você pode ler mais sobre o pacote clássico e o padrão DELM na [Wikipédia.](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)

>[!NOTE]
>Para enviar um pacote clássico e apertá-lo usando o ETHERNET, você deve saber o endereço MAC do dispositivo de destino e do adaptador Ethernet. Como o pacote sujo não usa o protocolo de rede IP, não é possível usar o endereço IP ou o nome DNS do dispositivo.

Muitas soluções de gerenciamento, como o Configuration Manager, fornecem suporte integrado para o TAMBÉM. Há também muitas soluções, incluindo aplicativos da Microsoft Store, módulos do PowerShell, aplicativos de terceiros e soluções de gerenciamento de terceiros que permitem que você envie um pacote mágico para apertá-lo. Por exemplo, você pode usar o [módulo Wake On LAN PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) do TechNet Script Center. 

>[!NOTE]
>Depois que um dispositivo tiver sido reatado com um pacote mágico, o dispositivo retornará ao sleep se um aplicativo não estiver ativamente impedindo o sleep no sistema ou se a chave do Registro AllowSystemRequiredPowerRequests não estiver configurada como 1, o que permite que os aplicativos impeçam o sleep. Consulte a [seção do driver DELLs](#wol-driver) deste artigo para obter mais informações sobre essa chave do Registro.
