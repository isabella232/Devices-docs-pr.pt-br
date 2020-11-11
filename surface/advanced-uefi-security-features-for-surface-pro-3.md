---
title: Recursos avançados de segurança UEFI para o Surface Pro 3 (Surface)
description: Este artigo descreve como instalar e configurar a atualização UEFI v3.11.760.0 para habilitar opções de segurança adicionais para dispositivos Surface Pro 3.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: segurança, recursos, configurar, hardware, dispositivo, personalizado, script, atualizar
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163180"
---
# Recursos avançados de segurança UEFI para o Surface Pro 3


Este artigo descreve como instalar e configurar a atualização UEFI v3.11.760.0 para habilitar opções de segurança adicionais para dispositivos Surface Pro 3.

Para abordar o controle mais granular sobre a segurança dos dispositivos Surface, a atualização UEFI v3.11.760.0 fornece opções de segurança adicionais que permitem desabilitar dispositivos de hardware específicos ou evitar a inicialização por meio desses dispositivos. Após a atualização UEFI ser instalada em um dispositivo, você pode configurá-la manualmente ou automaticamente executando um script.

## Instalar manualmente a atualização UEFI


Para poder configurar os recursos de segurança avançados do dispositivo Surface, primeiro você deve instalar a atualização UEFI v3.11.760.0. Essa atualização será instalada automaticamente se você receber as atualizações do Windows Update. Para obter mais informações sobre como configurar o Windows para ser atualizado automaticamente usando o Windows Update, consulte [Como configurar e usar Atualizações Automáticas no Windows](https://support.microsoft.com/kb/306525).

Para atualizar a UEFI no Surface Pro 3, você pode baixar e instalar as atualizações UEFI do Surface como parte do pacote de firmware e driver do Surface Pro 3. Esses pacotes de firmware e driver estão disponíveis na [página do Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) no Centro de Download da Microsoft. Você pode saber mais sobre os pacotes de firmware e driver em [Baixar o firmware e os drivers mais recentes para dispositivos Surface](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices). Os pacotes de firmware e driver estão disponíveis em formatos do Windows Installer (.msi) e de arquivo (.zip) independentes. Você pode saber mais sobre esses dois formatos e como pode usá-los para atualizar seus drivers em [Gerenciar atualizações de driver e firmware do Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).

## Definir configurações de segurança adicionais manualmente


>[!NOTE]
>Para entrar na configuração de firmware em um dispositivo Surface, comece com o dispositivo desligado. Pressione e segure o botão **Volume**, pressione e solte o botão de **Energia** e solte o botão **Volume** depois que o dispositivo começar a ser inicializado.

Após a atualização UEFI v3.11.760.0 ser instalada em um dispositivo Surface, um menu UEFI adicional chamado **Segurança Avançada de Dispositivo** fica disponível. Se você clicar nesse menu, serão exibidas as seguintes opções:

| Opção         | Descrição                                                                                                                                                                          | Configurações disponíveis (padrão listado em negrito) |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| Inicialização de rede   | Habilita ou desabilita a capacidade do dispositivo Surface de ser inicializado da rede (o que também é conhecido como inicialização PXE).                                                                            | **Habilitada**, Não Inicializável                   |
| USB Lateral       | Habilita ou desabilita a porta USB na lateral do dispositivo Surface. Além disso, a porta USB pode ser habilitada, mas não pode permitir a inicialização.                                                | **Habilitada**, Não Inicializável, Desabilitada         |
| Porta de Encaixe   | Habilita ou desabilita as portas na base de encaixe do Surface. Além disso, a porta de encaixe pode ser habilitada, mas bloquear a inicialização por meio de qualquer porta Ethernet ou USB na base de encaixe. | **Habilitada**, Não Inicializável, Desabilitada         |
| Câmera Frontal   | Habilita ou desabilita a câmera na parte da frente do dispositivo Surface.                                                                                                                   | **Habilitada**, Desabilitada                       |
| Câmera Traseira    | Habilita ou desabilita a câmera na parte de trás do dispositivo Surface.                                                                                                                    | **Habilitada**, Desabilitada                       |
| Áudio Integrado | Habilita ou desabilita o áudio no dispositivo Surface.                                                                                                                                     | **Habilitado**, Desabilitado                       |
| microSD        | Habilita ou desabilita o slot para microSD no dispositivo Surface.                                                                                                                          | **Habilitado**, Desabilitado                       |
| WiFi           | Habilita ou desabilita o transceptor de Wi-Fi interno no dispositivo Surface. Isso também desabilita o Bluetooth.                                                                              | **Habilitado**, Desabilitado                       |
| Bluetooth      | Habilita ou desabilita o transceptor de Bluetooth interno no dispositivo Surface.                                                                                                        | **Habilitado**, Desabilitado                       |

 

## Automatizar configurações de segurança adicionais


Como profissional de TI com privilégios administrativos, você pode automatizar a configuração da UEFI utilizando as [Ferramentas de firmware do Surface Pro 3 (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) disponíveis no Centro de Download da Microsoft. Essas ferramentas instalam um assembly .NET que pode ser chamado de qualquer aplicativo ou script personalizado.

**Pré-requisitos**

-   Os scripts de exemplo a seguir aproveitam a extensão mencionada anteriormente e, assim, pressupõem que a ferramenta tenha sido instalada no dispositivo que está sendo gerenciado.
-   Os scripts devem ser executados com privilégios administrativos.
-   O comando do Windows PowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) deve ser chamado antes da execução de scripts de exemplo, caso eles não estejam assinados digitalmente.

**Scripts de exemplo**

> [!NOTE]
> A senha UEFI usada nos scripts de exemplo a seguir é apresentada em texto não criptografado. É altamente recomendável salvar os scripts em um local protegido e executá-los em um ambiente controlado.


Mostrar todas as opções configuráveis:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

Definir ou alterar a senha UEFI:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

Verificar o status das alterações propostas:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

Reverter UEFI para valores padrão:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

Interpretação de código de status

-   00 - a atualização proposta teve êxito
-   02 - um dos valores propostos tinha um valor inválido
-   03 - havia um conjunto de valores proposto que não foi reconhecido
-   0F - a senha de desbloqueio não correspondia à senha definida atualmente

 
