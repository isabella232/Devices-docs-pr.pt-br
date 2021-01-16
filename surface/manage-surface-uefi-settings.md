---
title: Gerenciar configurações de UEFI do Surface
description: Use as configurações de UEFI do Surface para habilitar ou desabilitar dispositivos ou componentes, definir configurações de segurança e ajustar as configurações de inicialização do dispositivo Surface.
keywords: firmware, segurança, recursos, configurar, hardware
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/15/2021
ms.openlocfilehash: d8d47db3bd6f69783670b285a797337373e02d72
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271425"
---
# <span data-ttu-id="fe294-104">Gerenciar configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="fe294-105">Todas as gerações atuais e futuras dos dispositivos Surface usam uma UEFI (Unified Extensible Firmware Interface) exclusiva criada pela Microsoft especificamente para esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fe294-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="fe294-106">As configurações de UEFI do Surface fornecem a capacidade de habilitar ou desabilitar dispositivos e componentes internos, proteger as configurações de UEFI contra alterações e ajustar as configurações de inicialização do dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="fe294-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="fe294-107">Produtos com suporte</span><span class="sxs-lookup"><span data-stu-id="fe294-107">Supported products</span></span>

<span data-ttu-id="fe294-108">O gerenciamento UEFI é suportado no seguinte:</span><span class="sxs-lookup"><span data-stu-id="fe294-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="fe294-109">Surface Pro 4, Surface Pro (5ª geração), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="fe294-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="fe294-110">Surface Laptop (1ª geração), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="fe294-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="fe294-111">Surface Studio (1ª geração), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="fe294-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="fe294-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="fe294-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="fe294-113">Surface Go, Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="fe294-113">Surface Go, Surface Go 2</span></span>

## <span data-ttu-id="fe294-114">Suporte para gerenciamento baseado em nuvem</span><span class="sxs-lookup"><span data-stu-id="fe294-114">Support for cloud-based management</span></span>

<span data-ttu-id="fe294-115">Com perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados ao Microsoft Intune (agora disponível na visualização pública), o gerenciamento de UEFI do Surface estende a pilha de gerenciamento moderna até o nível de hardware UEFI.</span><span class="sxs-lookup"><span data-stu-id="fe294-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="fe294-116">O DFCI dá suporte ao provisionamento com zero toque, elimina senhas do BIOS, fornece controle das configurações de segurança, incluindo opções de inicialização e periféricos integrados, e dispõe a base para cenários de segurança avançados no futuro.</span><span class="sxs-lookup"><span data-stu-id="fe294-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="fe294-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  Para obter mais informações, consulte o [gerenciamento do Intune de configurações UEFI do Surface.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="fe294-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="fe294-118">Abrir o menu UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="fe294-119">Para ajustar as configurações de UEFI durante a inicialização do sistema:</span><span class="sxs-lookup"><span data-stu-id="fe294-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="fe294-120">Desligue o Surface e aguarde cerca de 10 segundos para garantir que ele está desligado.</span><span class="sxs-lookup"><span data-stu-id="fe294-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="fe294-121">Pressione e segure o **botão aumentar o volume** e, ao mesmo tempo, pressione e solte o botão **Ligar/Desligar.**</span><span class="sxs-lookup"><span data-stu-id="fe294-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="fe294-122">Como o logotipo da Microsoft ou do Surface aparece na tela, continue a manter o **botão Aumentar** o volume até que a tela UEFI apareça.</span><span class="sxs-lookup"><span data-stu-id="fe294-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="fe294-123">Página de informações do computador UEFI</span><span class="sxs-lookup"><span data-stu-id="fe294-123">UEFI PC information page</span></span>

<span data-ttu-id="fe294-124">A página de informações do computador inclui informações detalhadas sobre o dispositivo Surface:</span><span class="sxs-lookup"><span data-stu-id="fe294-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="fe294-125">**Modelo** – o modelo do dispositivo Surface será exibido aqui, como o Surface Book 2 ou o Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="fe294-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="fe294-126">A configuração exata de seu dispositivo não é exibida, (como processador, tamanho do disco ou tamanho da memória).</span><span class="sxs-lookup"><span data-stu-id="fe294-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="fe294-127">**UUID** – esse número de identificação universalmente exclusivo é específico de seu dispositivo e usado para identificar o dispositivo durante a implantação ou gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="fe294-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="fe294-128">**Número de Série** – esse número é usado para identificar esse dispositivo Surface específico para cenários de marcação de ativos e suporte.</span><span class="sxs-lookup"><span data-stu-id="fe294-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="fe294-129">**Marca do Ativo** – a marca do ativo é atribuída ao dispositivo Surface com a [Ferramenta de Marca do Ativo](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="fe294-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="fe294-130">Você também encontrará informações detalhadas sobre o firmware de seu dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="fe294-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="fe294-131">Os dispositivos Surface têm vários componentes internos que executam diferentes versões do firmware.</span><span class="sxs-lookup"><span data-stu-id="fe294-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="fe294-132">A versão do firmware de cada um dos seguintes dispositivos é exibida na página **Informações do computador** (como mostrado na Figura 1):</span><span class="sxs-lookup"><span data-stu-id="fe294-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="fe294-133">Sistema UEFI</span><span class="sxs-lookup"><span data-stu-id="fe294-133">System UEFI</span></span> 

- <span data-ttu-id="fe294-134">Controlador SAM</span><span class="sxs-lookup"><span data-stu-id="fe294-134">SAM Controller</span></span> 

- <span data-ttu-id="fe294-135">Intel Management Engine</span><span class="sxs-lookup"><span data-stu-id="fe294-135">Intel Management Engine</span></span> 

- <span data-ttu-id="fe294-136">Controlador Incorporado do Sistema</span><span class="sxs-lookup"><span data-stu-id="fe294-136">System Embedded Controller</span></span> 

- <span data-ttu-id="fe294-137">Firmware de Toque</span><span class="sxs-lookup"><span data-stu-id="fe294-137">Touch Firmware</span></span> 

![Informações do sistema e informações de versão do firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="fe294-139">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="fe294-139">Figure 1.</span></span> <span data-ttu-id="fe294-140">Informações do sistema e informações de versão do firmware</span><span class="sxs-lookup"><span data-stu-id="fe294-140">System information and firmware version information</span></span>*

<span data-ttu-id="fe294-141">Você pode encontrar informações atualizadas sobre a versão mais recente do firmware para o dispositivo Surface no [Histórico de Atualizações do Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe294-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="fe294-142">Página segurança uefi</span><span class="sxs-lookup"><span data-stu-id="fe294-142">UEFI Security page</span></span> 

![Definir configurações de segurança de UEFI do Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="fe294-144">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="fe294-144">Figure 2.</span></span> <span data-ttu-id="fe294-145">Definir configurações de segurança de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="fe294-146">A página Segurança permite definir uma senha para proteger as configurações de UEFI.</span><span class="sxs-lookup"><span data-stu-id="fe294-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="fe294-147">Essa senha deve ser inserida quando você inicializa o dispositivo Surface para UEFI.</span><span class="sxs-lookup"><span data-stu-id="fe294-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="fe294-148">A senha pode conter os seguintes caracteres (conforme mostrado na Figura 3):</span><span class="sxs-lookup"><span data-stu-id="fe294-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="fe294-149">Letras maiúsculas: A-Z</span><span class="sxs-lookup"><span data-stu-id="fe294-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="fe294-150">Letras minúsculas: a-z</span><span class="sxs-lookup"><span data-stu-id="fe294-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="fe294-151">Números: 1-0</span><span class="sxs-lookup"><span data-stu-id="fe294-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="fe294-152">Caracteres especiais: !@#$%^&\*()?<>{} []-_=+|.,;:''"</span><span class="sxs-lookup"><span data-stu-id="fe294-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="fe294-153">A senha deve ter pelo menos 6 caracteres e diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fe294-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![Adicionar uma senha para proteger as configurações de UEFI do Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="fe294-155">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="fe294-155">Figure 3.</span></span> <span data-ttu-id="fe294-156">Adicionar uma senha para proteger as configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="fe294-157">Na página Segurança também é possível alterar a configuração de Inicialização Segura no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="fe294-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="fe294-158">A tecnologia de Inicialização Segura impede que o código de inicialização não autorizado inicialize no dispositivo Surface, o que protege contra infecções por malware do tipo bootkit e rootkit.</span><span class="sxs-lookup"><span data-stu-id="fe294-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="fe294-159">Você pode desabilitar a Inicialização Segura para permitir que o dispositivo Surface inicialize sistemas operacionais de terceiros ou mídia inicializável.</span><span class="sxs-lookup"><span data-stu-id="fe294-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="fe294-160">Você também pode configurar a Inicialização Segura para funcionar com certificados de terceiros, conforme mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="fe294-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="fe294-161">Leia mais sobre a [Inicialização Segura](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) na Biblioteca do TechNet.</span><span class="sxs-lookup"><span data-stu-id="fe294-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurar a Inicialização Segura](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="fe294-163">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="fe294-163">Figure 4.</span></span> <span data-ttu-id="fe294-164">Configurar a Inicialização Segura</span><span class="sxs-lookup"><span data-stu-id="fe294-164">Configure Secure Boot</span></span>*

<span data-ttu-id="fe294-165">Dependendo do dispositivo, você também poderá ver se o TPM está habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fe294-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="fe294-166">Se você não vir a configuração Habilitar **TPM,**  abra tpm.msc no Windows para verificar o status, conforme mostrado na Figura 5.</span><span class="sxs-lookup"><span data-stu-id="fe294-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="fe294-167">O TPM é usado para autenticar a criptografia dos dados de seu dispositivo com o BitLocker.</span><span class="sxs-lookup"><span data-stu-id="fe294-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="fe294-168">Para saber mais, consulte a [visão geral do BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)</span><span class="sxs-lookup"><span data-stu-id="fe294-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Console do TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="fe294-170">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="fe294-170">Figure 5.</span></span> <span data-ttu-id="fe294-171">Console do TPM</span><span class="sxs-lookup"><span data-stu-id="fe294-171">TPM console</span></span>*


## <span data-ttu-id="fe294-172">Menu UEFI: Dispositivos</span><span class="sxs-lookup"><span data-stu-id="fe294-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="fe294-173">A página Dispositivos permite habilitar ou desabilitar dispositivos e componentes específicos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="fe294-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="fe294-174">Encaixe e portas USB</span><span class="sxs-lookup"><span data-stu-id="fe294-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="fe294-175">Slot de cartão MicroSD ou SD</span><span class="sxs-lookup"><span data-stu-id="fe294-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="fe294-176">Câmera Traseira</span><span class="sxs-lookup"><span data-stu-id="fe294-176">Rear Camera</span></span> 

- <span data-ttu-id="fe294-177">Câmera Frontal</span><span class="sxs-lookup"><span data-stu-id="fe294-177">Front Camera</span></span> 

- <span data-ttu-id="fe294-178">Câmera de infravermelho (IV)</span><span class="sxs-lookup"><span data-stu-id="fe294-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="fe294-179">Wi-Fi e Bluetooth</span><span class="sxs-lookup"><span data-stu-id="fe294-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="fe294-180">Áudio integrado (alto-falantes e microfone)</span><span class="sxs-lookup"><span data-stu-id="fe294-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="fe294-181">Cada dispositivo é listado com um botão \*\*\*\* de controle deslizante que você pode mover para a posição Ativado (habilitado) ou Desativado (desabilitado), conforme mostrado na Figura 6. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fe294-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Habilitar e desabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="fe294-183">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="fe294-183">Figure 6.</span></span> <span data-ttu-id="fe294-184">Habilitar e desabilitar dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="fe294-184">Enable and disable specific devices</span></span>*

## <span data-ttu-id="fe294-185">Menu UEFI: Configuração de inicialização</span><span class="sxs-lookup"><span data-stu-id="fe294-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="fe294-186">A página Configuração de Inicialização permite alterar a ordem dos dispositivos de inicialização, bem como habilitar ou desabilitar a inicialização dos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="fe294-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="fe294-187">Gerenciador de Inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="fe294-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="fe294-188">Armazenamento USB</span><span class="sxs-lookup"><span data-stu-id="fe294-188">USB Storage</span></span> 

- <span data-ttu-id="fe294-189">Rede PXE</span><span class="sxs-lookup"><span data-stu-id="fe294-189">PXE Network</span></span> 

- <span data-ttu-id="fe294-190">Armazenamento interno</span><span class="sxs-lookup"><span data-stu-id="fe294-190">Internal Storage</span></span> 

<span data-ttu-id="fe294-191">Você pode inicializar a partir de um dispositivo específico imediatamente ou pode passar o dedo para a esquerda na entrada desse dispositivo na lista usando a tela touch.</span><span class="sxs-lookup"><span data-stu-id="fe294-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="fe294-192">Você também pode inicializar imediatamente em um dispositivo USB ou um adaptador de Ethernet USB quando o dispositivo Surface está desligado, pressionando o botão de **Diminuir o Volume** e o botão **Ligar/Desligar** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="fe294-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="fe294-193">Para que a ordem de inicialização especificada \*\*\*\* entre em vigor, você deve definir a opção Habilitar Sequência de Inicialização Alternativa como **Ativada,** conforme mostrado na Figura 7.</span><span class="sxs-lookup"><span data-stu-id="fe294-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurar a ordem de inicialização para o dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="fe294-195">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="fe294-195">Figure 7.</span></span> <span data-ttu-id="fe294-196">Configurar a ordem de inicialização para o dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="fe294-197">Você também pode ativar e desativar o suporte a IPv6 para PXE com a opção **Habilitar IPv6 para Inicialização de Rede PXE**, por exemplo, ao executar uma implantação do Windows usando o PXE, onde o servidor PXE é configurado somente para IPv4.</span><span class="sxs-lookup"><span data-stu-id="fe294-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="fe294-198">Menu UEFI: Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="fe294-198">UEFI menu: Management</span></span>
<span data-ttu-id="fe294-199">A página gerenciamento permite que você gerencie o uso do Gerenciamento DE UEFI Zero Touch e outros recursos em dispositivos qualificados, incluindo Surface Pro 7, Surface Pro X e Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="fe294-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="fe294-200">Gerenciar o acesso ao Gerenciamento DE UEFI Zero Touch e outros recursos ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Figura 8. Gerenciar o acesso ao Gerenciamento DE UEFI Zero Touch e outros recursos*</span><span class="sxs-lookup"><span data-stu-id="fe294-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="fe294-201">O Gerenciamento DE UEFI Zero Touch permite gerenciar remotamente as configurações de UEFI usando um perfil de dispositivo no Intune chamado Interface de Configuração do Firmware de Dispositivo (DFCI).</span><span class="sxs-lookup"><span data-stu-id="fe294-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="fe294-202">Se você não definir essa configuração, a capacidade de gerenciar dispositivos qualificados com DFCI será definida como **Pronto.**</span><span class="sxs-lookup"><span data-stu-id="fe294-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="fe294-203">Para impedir DFCI, selecione **Opt-Out**.</span><span class="sxs-lookup"><span data-stu-id="fe294-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="fe294-204">A página de configurações de Gerenciamento UEFI e o uso de DFCI estão disponíveis atualmente para o Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 e Surface Pro X. Para saber mais, consulte [Gerenciamento do Intune de configurações UEFI do Surface.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="fe294-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="fe294-205">Menu UEFI: Sair</span><span class="sxs-lookup"><span data-stu-id="fe294-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="fe294-206">Use o **botão Reiniciar Agora** na página **Sair** para sair das configurações UEFI, conforme mostrado na Figura 9.</span><span class="sxs-lookup"><span data-stu-id="fe294-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Sair do UEFI do Surface e reiniciar o dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="fe294-208">Figura 9.</span><span class="sxs-lookup"><span data-stu-id="fe294-208">Figure 9.</span></span> <span data-ttu-id="fe294-209">Clique em Reiniciar Agora para sair do UEFI do Surface e reiniciar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="fe294-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="fe294-210">Telas de inicialização UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="fe294-211">Quando você atualiza o firmware do dispositivo Surface, usando o Windows Update ou instalação manual, as atualizações não são aplicadas imediatamente para o dispositivo, só durante o próximo ciclo de reinicialização.</span><span class="sxs-lookup"><span data-stu-id="fe294-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="fe294-212">Você pode saber mais sobre o processo de atualização do firmware do Surface no [Gerenciar atualizações de driver e firmware do Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="fe294-212">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="fe294-213">O progresso da atualização do firmware é exibido em uma tela com barras de progresso de cores diferentes para indicar o firmware para cada componente.</span><span class="sxs-lookup"><span data-stu-id="fe294-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="fe294-214">A barra de progresso de cada componente é mostrada nas Figuras 9 a 18.</span><span class="sxs-lookup"><span data-stu-id="fe294-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Atualização de firmware UEFI Surface com barra de progresso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="fe294-216">Figura 10.</span><span class="sxs-lookup"><span data-stu-id="fe294-216">Figure 10.</span></span> <span data-ttu-id="fe294-217">A atualização do firmware UEFI do Surface exibe uma barra de progresso azul</span><span class="sxs-lookup"><span data-stu-id="fe294-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Firmware de controlador incorporado do sistema com a barra de progresso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="fe294-219">Figura 11.</span><span class="sxs-lookup"><span data-stu-id="fe294-219">Figure 11.</span></span> <span data-ttu-id="fe294-220">A atualização de firmware de controlador incorporado no sistema exibe uma barra de progresso verde</span><span class="sxs-lookup"><span data-stu-id="fe294-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Atualização do firmware de SAM Controller com barra de progresso laranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="fe294-222">Figura 12.</span><span class="sxs-lookup"><span data-stu-id="fe294-222">Figure 12.</span></span> <span data-ttu-id="fe294-223">A atualização do firmware de SAM Controller exibe uma barra de progresso laranja</span><span class="sxs-lookup"><span data-stu-id="fe294-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Firmware do Intel Management Engine com barra de progresso vermelho](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="fe294-225">Figura 13.</span><span class="sxs-lookup"><span data-stu-id="fe294-225">Figure 13.</span></span> <span data-ttu-id="fe294-226">A atualização de firmware da Intel Management Engine exibe uma barra de progresso vermelho</span><span class="sxs-lookup"><span data-stu-id="fe294-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Toque Surface firmware com barra de progresso cinza](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="fe294-228">Figura 14.</span><span class="sxs-lookup"><span data-stu-id="fe294-228">Figure 14.</span></span> <span data-ttu-id="fe294-229">A atualização de firmware do Surface toque exibe uma barra de progresso cinza</span><span class="sxs-lookup"><span data-stu-id="fe294-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![Firmware DO SURFACE (SURFACE) com barra de progresso verde claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="fe294-231">Figura 15.</span><span class="sxs-lookup"><span data-stu-id="fe294-231">Figure 15.</span></span> <span data-ttu-id="fe294-232">A atualização de firmware do Surface FIRMWARE DO SURFACE exibe uma barra de progresso verde claro</span><span class="sxs-lookup"><span data-stu-id="fe294-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Surface ISH firmware with pink progress bar](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="fe294-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span><span class="sxs-lookup"><span data-stu-id="fe294-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Firmware do Surface Trackpad com barra de progresso cinza](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="fe294-236">Figura 17.</span><span class="sxs-lookup"><span data-stu-id="fe294-236">Figure 17.</span></span> <span data-ttu-id="fe294-237">A atualização do firmware do Surface Trackpad exibe uma barra de progresso rosa</span><span class="sxs-lookup"><span data-stu-id="fe294-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Firmware TCON do Surface com barra de progresso cinza claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="fe294-239">Figura 18.</span><span class="sxs-lookup"><span data-stu-id="fe294-239">Figure 18.</span></span> <span data-ttu-id="fe294-240">A atualização do firmware do Surface TCON exibe uma barra de progresso cinza claro</span><span class="sxs-lookup"><span data-stu-id="fe294-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Firmware do TPM do Surface com barra de progresso púrpura clara](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="fe294-242">Figura 19.</span><span class="sxs-lookup"><span data-stu-id="fe294-242">Figure 19.</span></span> <span data-ttu-id="fe294-243">A atualização do firmware do TPM do Surface exibe uma barra de progresso roxo</span><span class="sxs-lookup"><span data-stu-id="fe294-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="fe294-244">Uma mensagem de aviso adicional que indica que a Inicialização Segura está desabilitada é exibida, conforme mostrado na Figura 19.</span><span class="sxs-lookup"><span data-stu-id="fe294-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Tela de inicialização do Surface que indica que a inicialização segura foi desabilitada](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="fe294-246">Figura 20.</span><span class="sxs-lookup"><span data-stu-id="fe294-246">Figure 20.</span></span> <span data-ttu-id="fe294-247">Tela de inicialização do Surface que indica que a inicialização segura foi desativada nas configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="fe294-248">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fe294-248">Related topics</span></span>

- [<span data-ttu-id="fe294-249">Gerenciamento pelo Intune das configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-249">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="fe294-250">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="fe294-250">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
