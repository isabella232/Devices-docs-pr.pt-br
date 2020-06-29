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
ms.openlocfilehash: 9460b4a5e8b44cbf4b6af57d01aab3b09afb49de
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830290"
---
# <span data-ttu-id="d7bb4-104">Recursos avançados de segurança UEFI para o Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d7bb4-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="d7bb4-105">Este artigo descreve como instalar e configurar a atualização UEFI v3.11.760.0 para habilitar opções de segurança adicionais para dispositivos Surface Pro 3.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="d7bb4-106">Para abordar o controle mais granular sobre a segurança dos dispositivos Surface, a atualização UEFI v3.11.760.0 fornece opções de segurança adicionais que permitem desabilitar dispositivos de hardware específicos ou evitar a inicialização por meio desses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="d7bb4-107">Após a atualização UEFI ser instalada em um dispositivo, você pode configurá-la manualmente ou automaticamente executando um script.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="d7bb4-108">Instalar manualmente a atualização UEFI</span><span class="sxs-lookup"><span data-stu-id="d7bb4-108">Manually install the UEFI update</span></span>


<span data-ttu-id="d7bb4-109">Para poder configurar os recursos de segurança avançados do dispositivo Surface, primeiro você deve instalar a atualização UEFI v3.11.760.0.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="d7bb4-110">Essa atualização será instalada automaticamente se você receber as atualizações do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="d7bb4-111">Para obter mais informações sobre como configurar o Windows para ser atualizado automaticamente usando o Windows Update, consulte [Como configurar e usar Atualizações Automáticas no Windows](https://support.microsoft.com/kb/306525).</span><span class="sxs-lookup"><span data-stu-id="d7bb4-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="d7bb4-112">Para atualizar a UEFI no Surface Pro 3, você pode baixar e instalar as atualizações UEFI do Surface como parte do pacote de firmware e driver do Surface Pro 3.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="d7bb4-113">Esses pacotes de firmware e driver estão disponíveis na [página do Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="d7bb4-114">Você pode saber mais sobre os pacotes de firmware e driver em [Baixar o firmware e os drivers mais recentes para dispositivos Surface](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="d7bb4-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="d7bb4-115">Os pacotes de firmware e driver estão disponíveis em formatos do Windows Installer (.msi) e de arquivo (.zip) independentes.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="d7bb4-116">Você pode saber mais sobre esses dois formatos e como pode usá-los para atualizar seus drivers em [Gerenciar atualizações de driver e firmware do Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="d7bb4-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="d7bb4-117">Definir configurações de segurança adicionais manualmente</span><span class="sxs-lookup"><span data-stu-id="d7bb4-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="d7bb4-118">Para entrar na configuração de firmware em um dispositivo Surface, comece com o dispositivo desligado. Pressione e segure o botão **Volume**, pressione e solte o botão de **Energia** e solte o botão **Volume** depois que o dispositivo começar a ser inicializado.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="d7bb4-119">Após a atualização UEFI v3.11.760.0 ser instalada em um dispositivo Surface, um menu UEFI adicional chamado **Segurança Avançada de Dispositivo** fica disponível.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="d7bb4-120">Se você clicar nesse menu, serão exibidas as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d7bb4-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="d7bb4-121">Opção</span><span class="sxs-lookup"><span data-stu-id="d7bb4-121">Option</span></span>         | <span data-ttu-id="d7bb4-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7bb4-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="d7bb4-123">Configurações disponíveis (padrão listado em negrito)</span><span class="sxs-lookup"><span data-stu-id="d7bb4-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="d7bb4-124">Inicialização de rede</span><span class="sxs-lookup"><span data-stu-id="d7bb4-124">Network Boot</span></span>   | <span data-ttu-id="d7bb4-125">Habilita ou desabilita a capacidade do dispositivo Surface de ser inicializado da rede (o que também é conhecido como inicialização PXE).</span><span class="sxs-lookup"><span data-stu-id="d7bb4-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="d7bb4-126">**Habilitada**, Não Inicializável</span><span class="sxs-lookup"><span data-stu-id="d7bb4-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="d7bb4-127">USB Lateral</span><span class="sxs-lookup"><span data-stu-id="d7bb4-127">Side USB</span></span>       | <span data-ttu-id="d7bb4-128">Habilita ou desabilita a porta USB na lateral do dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="d7bb4-129">Além disso, a porta USB pode ser habilitada, mas não pode permitir a inicialização.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="d7bb4-130">**Habilitada**, Não Inicializável, Desabilitada</span><span class="sxs-lookup"><span data-stu-id="d7bb4-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="d7bb4-131">Porta de Encaixe</span><span class="sxs-lookup"><span data-stu-id="d7bb4-131">Docking Port</span></span>   | <span data-ttu-id="d7bb4-132">Habilita ou desabilita as portas na base de encaixe do Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="d7bb4-133">Além disso, a porta de encaixe pode ser habilitada, mas bloquear a inicialização por meio de qualquer porta Ethernet ou USB na base de encaixe.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="d7bb4-134">**Habilitada**, Não Inicializável, Desabilitada</span><span class="sxs-lookup"><span data-stu-id="d7bb4-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="d7bb4-135">Câmera Frontal</span><span class="sxs-lookup"><span data-stu-id="d7bb4-135">Front Camera</span></span>   | <span data-ttu-id="d7bb4-136">Habilita ou desabilita a câmera na parte da frente do dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="d7bb4-137">**Habilitada**, Desabilitada</span><span class="sxs-lookup"><span data-stu-id="d7bb4-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="d7bb4-138">Câmera Traseira</span><span class="sxs-lookup"><span data-stu-id="d7bb4-138">Rear Camera</span></span>    | <span data-ttu-id="d7bb4-139">Habilita ou desabilita a câmera na parte de trás do dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="d7bb4-140">**Habilitada**, Desabilitada</span><span class="sxs-lookup"><span data-stu-id="d7bb4-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="d7bb4-141">Áudio Integrado</span><span class="sxs-lookup"><span data-stu-id="d7bb4-141">On Board Audio</span></span> | <span data-ttu-id="d7bb4-142">Habilita ou desabilita o áudio no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="d7bb4-143">**Habilitado**, Desabilitado</span><span class="sxs-lookup"><span data-stu-id="d7bb4-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="d7bb4-144">microSD</span><span class="sxs-lookup"><span data-stu-id="d7bb4-144">microSD</span></span>        | <span data-ttu-id="d7bb4-145">Habilita ou desabilita o slot para microSD no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="d7bb4-146">**Habilitado**, Desabilitado</span><span class="sxs-lookup"><span data-stu-id="d7bb4-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="d7bb4-147">WiFi</span><span class="sxs-lookup"><span data-stu-id="d7bb4-147">WiFi</span></span>           | <span data-ttu-id="d7bb4-148">Habilita ou desabilita o transceptor de Wi-Fi interno no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="d7bb4-149">Isso também desabilita o Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="d7bb4-150">**Habilitado**, Desabilitado</span><span class="sxs-lookup"><span data-stu-id="d7bb4-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="d7bb4-151">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="d7bb4-151">Bluetooth</span></span>      | <span data-ttu-id="d7bb4-152">Habilita ou desabilita o transceptor de Bluetooth interno no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="d7bb4-153">**Habilitado**, Desabilitado</span><span class="sxs-lookup"><span data-stu-id="d7bb4-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="d7bb4-154">Automatizar configurações de segurança adicionais</span><span class="sxs-lookup"><span data-stu-id="d7bb4-154">Automate additional security settings</span></span>


<span data-ttu-id="d7bb4-155">Como profissional de TI com privilégios administrativos, você pode automatizar a configuração da UEFI utilizando as [Ferramentas de firmware do Surface Pro 3 (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) disponíveis no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="d7bb4-156">Essas ferramentas instalam um assembly .NET que pode ser chamado de qualquer aplicativo ou script personalizado.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="d7bb4-157">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d7bb4-157">Prerequisites</span></span>**

-   <span data-ttu-id="d7bb4-158">Os scripts de exemplo a seguir aproveitam a extensão mencionada anteriormente e, assim, pressupõem que a ferramenta tenha sido instalada no dispositivo que está sendo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="d7bb4-159">Os scripts devem ser executados com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="d7bb4-160">O comando do Windows PowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) deve ser chamado antes da execução de scripts de exemplo, caso eles não estejam assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="d7bb4-161">Scripts de exemplo</span><span class="sxs-lookup"><span data-stu-id="d7bb4-161">Sample scripts</span></span>**

><span data-ttu-id="d7bb4-162">**Observação**:&nbsp;&nbsp;A senha UEFI usada nos scripts de exemplo a seguir é apresentada em texto não criptografado.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-162">**Note**:&nbsp;&nbsp;The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="d7bb4-163">É altamente recomendável salvar os scripts em um local protegido e executá-los em um ambiente controlado.</span><span class="sxs-lookup"><span data-stu-id="d7bb4-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="d7bb4-164">Mostrar todas as opções configuráveis:</span><span class="sxs-lookup"><span data-stu-id="d7bb4-164">Show all configurable options:</span></span>

```
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

<span data-ttu-id="d7bb4-165">Definir ou alterar a senha UEFI:</span><span class="sxs-lookup"><span data-stu-id="d7bb4-165">Set or change UEFI password:</span></span>

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

<span data-ttu-id="d7bb4-166">Verificar o status das alterações propostas:</span><span class="sxs-lookup"><span data-stu-id="d7bb4-166">Check status of proposed changes:</span></span>

```
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

<span data-ttu-id="d7bb4-167">Reverter UEFI para valores padrão:</span><span class="sxs-lookup"><span data-stu-id="d7bb4-167">Revert UEFI to default values:</span></span>

```
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

<span data-ttu-id="d7bb4-168">Interpretação de código de status</span><span class="sxs-lookup"><span data-stu-id="d7bb4-168">Status code interpretation</span></span>

-   <span data-ttu-id="d7bb4-169">00 - a atualização proposta teve êxito</span><span class="sxs-lookup"><span data-stu-id="d7bb4-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="d7bb4-170">02 - um dos valores propostos tinha um valor inválido</span><span class="sxs-lookup"><span data-stu-id="d7bb4-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="d7bb4-171">03 - havia um conjunto de valores proposto que não foi reconhecido</span><span class="sxs-lookup"><span data-stu-id="d7bb4-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="d7bb4-172">0F - a senha de desbloqueio não correspondia à senha definida atualmente</span><span class="sxs-lookup"><span data-stu-id="d7bb4-172">0F - The unlock password did not match currently set password</span></span>

 

 





