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
ms.date: 04/13/2021
ms.openlocfilehash: ea995eda277ecf235eedd92f3af6edb0b60ae68a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576501"
---
# <a name="manage-surface-uefi-settings"></a><span data-ttu-id="bc61a-104">Gerenciar configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-104">Manage Surface UEFI settings</span></span>

 <span data-ttu-id="bc61a-105">Os dispositivos Surface PC foram projetados para utilizar uma UEFI (Interface de Firmware Extensível Unificada) exclusiva projetada pela Microsoft especificamente para esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bc61a-105">Surface PC devices are designed to utilize a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="bc61a-106">As configurações da UEFI do Surface fornecem a capacidade de habilitar ou desabilitar dispositivos e componentes internos, proteger as configurações da UEFI de serem alteradas e ajustar as configurações de inicialização do dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="bc61a-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <a name="supported-products"></a><span data-ttu-id="bc61a-107">Produtos com suporte</span><span class="sxs-lookup"><span data-stu-id="bc61a-107">Supported products</span></span>

<span data-ttu-id="bc61a-108">O gerenciamento UEFI tem suporte no seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc61a-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="bc61a-109">Surface Pro 4, Surface Pro (5ª Geração), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="bc61a-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="bc61a-110">Surface Laptop (1ª Geração), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="bc61a-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4</span></span>
- <span data-ttu-id="bc61a-111">Surface Studio (1ª Geração), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="bc61a-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="bc61a-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="bc61a-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="bc61a-113">Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)</span><span class="sxs-lookup"><span data-stu-id="bc61a-113">Surface Go, Surface Go 2[<sup>1</sup>](#references)</span></span>

## <a name="support-for-cloud-based-management"></a><span data-ttu-id="bc61a-114">Suporte para gerenciamento baseado em nuvem</span><span class="sxs-lookup"><span data-stu-id="bc61a-114">Support for cloud-based management</span></span>

<span data-ttu-id="bc61a-115">Com perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados Microsoft Intune (agora disponíveis na visualização pública), o gerenciamento uefi do Surface estende a pilha de gerenciamento moderna até o nível de hardware UEFI.</span><span class="sxs-lookup"><span data-stu-id="bc61a-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="bc61a-116">O DFCI dá suporte ao provisionamento de toque zero, elimina senhas de BIOS, fornece controle de configurações de segurança, incluindo opções de inicialização e periféricos integrados, e estabelece as bases para cenários avançados de segurança no futuro.</span><span class="sxs-lookup"><span data-stu-id="bc61a-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="bc61a-117">O DFCI está disponível para o Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 e Surface Pro X.  Para obter mais informações, consulte [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="bc61a-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="open-surface-uefi-menu"></a><span data-ttu-id="bc61a-118">Menu Abrir UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="bc61a-119">Para ajustar as configurações da UEFI durante a inicialização do sistema:</span><span class="sxs-lookup"><span data-stu-id="bc61a-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="bc61a-120">Desligue o Surface e aguarde cerca de 10 segundos para garantir que ele está desligado.</span><span class="sxs-lookup"><span data-stu-id="bc61a-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="bc61a-121">Pressione e segure o **botão Volume-up** e , ao mesmo tempo, pressione e solte o **botão Ligar.**</span><span class="sxs-lookup"><span data-stu-id="bc61a-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="bc61a-122">À medida que o logotipo da Microsoft ou do Surface aparecer na tela, continue a segurar o **botão Volume-up** até que a tela UEFI apareça.</span><span class="sxs-lookup"><span data-stu-id="bc61a-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <a name="uefi-pc-information-page"></a><span data-ttu-id="bc61a-123">Página de informações do computador UEFI</span><span class="sxs-lookup"><span data-stu-id="bc61a-123">UEFI PC information page</span></span>

<span data-ttu-id="bc61a-124">A página de informações do computador inclui informações detalhadas sobre seu dispositivo Surface:</span><span class="sxs-lookup"><span data-stu-id="bc61a-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="bc61a-125">**Modelo** – O modelo do dispositivo Surface será exibido aqui, como Surface Book 2 ou Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="bc61a-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="bc61a-126">A configuração exata de seu dispositivo não é exibida, (como processador, tamanho do disco ou tamanho da memória).</span><span class="sxs-lookup"><span data-stu-id="bc61a-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="bc61a-127">**UUID** – esse número de identificação universalmente exclusivo é específico de seu dispositivo e usado para identificar o dispositivo durante a implantação ou gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bc61a-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="bc61a-128">**Número de Série** – esse número é usado para identificar esse dispositivo Surface específico para cenários de marcação de ativos e suporte.</span><span class="sxs-lookup"><span data-stu-id="bc61a-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="bc61a-129">**Marca do Ativo** – a marca do ativo é atribuída ao dispositivo Surface com a [Ferramenta de Marca do Ativo](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="bc61a-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="bc61a-130">Você também encontrará informações detalhadas sobre o firmware de seu dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="bc61a-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="bc61a-131">Os dispositivos Surface têm vários componentes internos que executam diferentes versões do firmware.</span><span class="sxs-lookup"><span data-stu-id="bc61a-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="bc61a-132">A versão do firmware de cada um dos seguintes dispositivos é exibida na página **Informações do computador** (como mostrado na Figura 1):</span><span class="sxs-lookup"><span data-stu-id="bc61a-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="bc61a-133">Sistema UEFI</span><span class="sxs-lookup"><span data-stu-id="bc61a-133">System UEFI</span></span> 

- <span data-ttu-id="bc61a-134">Controlador SAM</span><span class="sxs-lookup"><span data-stu-id="bc61a-134">SAM Controller</span></span> 

- <span data-ttu-id="bc61a-135">Intel Management Engine</span><span class="sxs-lookup"><span data-stu-id="bc61a-135">Intel Management Engine</span></span> 

- <span data-ttu-id="bc61a-136">Controlador Incorporado do Sistema</span><span class="sxs-lookup"><span data-stu-id="bc61a-136">System Embedded Controller</span></span> 

- <span data-ttu-id="bc61a-137">Firmware de Toque</span><span class="sxs-lookup"><span data-stu-id="bc61a-137">Touch Firmware</span></span> 

![Informações do sistema e informações de versão do firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="bc61a-139">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="bc61a-139">Figure 1.</span></span> <span data-ttu-id="bc61a-140">Informações do sistema e informações de versão do firmware</span><span class="sxs-lookup"><span data-stu-id="bc61a-140">System information and firmware version information</span></span>*

<span data-ttu-id="bc61a-141">Você pode encontrar informações atualizadas sobre a versão mais recente do firmware para o dispositivo Surface no [Histórico de Atualizações do Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bc61a-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <a name="uefi-security-page"></a><span data-ttu-id="bc61a-142">Página Segurança uefi</span><span class="sxs-lookup"><span data-stu-id="bc61a-142">UEFI Security page</span></span> 

![Definir configurações de segurança de UEFI do Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="bc61a-144">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="bc61a-144">Figure 2.</span></span> <span data-ttu-id="bc61a-145">Definir configurações de segurança de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="bc61a-146">A página Segurança permite definir uma senha para proteger as configurações uefi.</span><span class="sxs-lookup"><span data-stu-id="bc61a-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="bc61a-147">Essa senha deve ser inserida quando você inicializa o dispositivo Surface para UEFI.</span><span class="sxs-lookup"><span data-stu-id="bc61a-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="bc61a-148">A senha pode conter os seguintes caracteres (conforme mostrado na Figura 3):</span><span class="sxs-lookup"><span data-stu-id="bc61a-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="bc61a-149">Letras maiúsculas: A-Z</span><span class="sxs-lookup"><span data-stu-id="bc61a-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="bc61a-150">Letras minúsculas: a-z</span><span class="sxs-lookup"><span data-stu-id="bc61a-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="bc61a-151">Números: 1-0</span><span class="sxs-lookup"><span data-stu-id="bc61a-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="bc61a-152">Caracteres especiais: !@#$%^&\*()?<>{} []-_=+|.,;''"</span><span class="sxs-lookup"><span data-stu-id="bc61a-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="bc61a-153">A senha deve ter pelo menos 6 caracteres e diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bc61a-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![Adicionar uma senha para proteger as configurações de UEFI do Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="bc61a-155">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="bc61a-155">Figure 3.</span></span> <span data-ttu-id="bc61a-156">Adicionar uma senha para proteger as configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="bc61a-157">Na página Segurança também é possível alterar a configuração de Inicialização Segura no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="bc61a-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="bc61a-158">A tecnologia de Inicialização Segura impede que o código de inicialização não autorizado inicialize no dispositivo Surface, o que protege contra infecções por malware do tipo bootkit e rootkit.</span><span class="sxs-lookup"><span data-stu-id="bc61a-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="bc61a-159">Você pode desabilitar a Inicialização Segura para permitir que o dispositivo Surface inicialize sistemas operacionais de terceiros ou mídia inicializável.</span><span class="sxs-lookup"><span data-stu-id="bc61a-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="bc61a-160">Você também pode configurar a Inicialização Segura para funcionar com certificados de terceiros, conforme mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="bc61a-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="bc61a-161">Leia mais sobre a [Inicialização Segura](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) na Biblioteca do TechNet.</span><span class="sxs-lookup"><span data-stu-id="bc61a-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurar a Inicialização Segura](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="bc61a-163">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="bc61a-163">Figure 4.</span></span> <span data-ttu-id="bc61a-164">Configurar a Inicialização Segura</span><span class="sxs-lookup"><span data-stu-id="bc61a-164">Configure Secure Boot</span></span>*

<span data-ttu-id="bc61a-165">Dependendo do dispositivo, você também pode ver se o TPM está habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="bc61a-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="bc61a-166">Se você não vir a configuração **Habilitar TPM,** abra tpm.msc no Windows para verificar o status, conforme mostrado na Figura 5.</span><span class="sxs-lookup"><span data-stu-id="bc61a-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="bc61a-167">O TPM é usado para autenticar a criptografia dos dados de seu dispositivo com o BitLocker.</span><span class="sxs-lookup"><span data-stu-id="bc61a-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="bc61a-168">Para saber mais, confira [BitLocker visão geral](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="bc61a-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Console TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="bc61a-170">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="bc61a-170">Figure 5.</span></span> <span data-ttu-id="bc61a-171">Console TPM</span><span class="sxs-lookup"><span data-stu-id="bc61a-171">TPM console</span></span>*


## <a name="uefi-menu-devices"></a><span data-ttu-id="bc61a-172">Menu UEFI: Dispositivos</span><span class="sxs-lookup"><span data-stu-id="bc61a-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="bc61a-173">A página Dispositivos permite habilitar ou desabilitar dispositivos e componentes específicos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="bc61a-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="bc61a-174">Encaixe e portas USB</span><span class="sxs-lookup"><span data-stu-id="bc61a-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="bc61a-175">Slot de cartão MicroSD ou SD</span><span class="sxs-lookup"><span data-stu-id="bc61a-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="bc61a-176">Câmera Traseira</span><span class="sxs-lookup"><span data-stu-id="bc61a-176">Rear Camera</span></span> 

- <span data-ttu-id="bc61a-177">Câmera Frontal</span><span class="sxs-lookup"><span data-stu-id="bc61a-177">Front Camera</span></span> 

- <span data-ttu-id="bc61a-178">Câmera de infravermelho (IV)</span><span class="sxs-lookup"><span data-stu-id="bc61a-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="bc61a-179">Wi-Fi e Bluetooth</span><span class="sxs-lookup"><span data-stu-id="bc61a-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="bc61a-180">Áudio integrado (alto-falantes e microfone)</span><span class="sxs-lookup"><span data-stu-id="bc61a-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="bc61a-181">Cada dispositivo é listado com um botão de controle deslizante que você pode mover para **a** posição Ativado (habilitado) ou Desativado (desabilitado), conforme mostrado na Figura 6. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc61a-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Habilitar e desabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="bc61a-183">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="bc61a-183">Figure 6.</span></span> <span data-ttu-id="bc61a-184">Habilitar e desabilitar dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="bc61a-184">Enable and disable specific devices</span></span>*

## <a name="uefi-menu-boot-configuration"></a><span data-ttu-id="bc61a-185">Menu UEFI: Configuração de inicialização</span><span class="sxs-lookup"><span data-stu-id="bc61a-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="bc61a-186">A página Configuração de Inicialização permite alterar a ordem dos dispositivos de inicialização, bem como habilitar ou desabilitar a inicialização dos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="bc61a-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="bc61a-187">Gerenciador de Inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="bc61a-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="bc61a-188">Armazenamento USB</span><span class="sxs-lookup"><span data-stu-id="bc61a-188">USB Storage</span></span> 

- <span data-ttu-id="bc61a-189">Rede PXE</span><span class="sxs-lookup"><span data-stu-id="bc61a-189">PXE Network</span></span> 

- <span data-ttu-id="bc61a-190">Armazenamento interno</span><span class="sxs-lookup"><span data-stu-id="bc61a-190">Internal Storage</span></span> 

<span data-ttu-id="bc61a-191">Você pode inicializar a partir de um dispositivo específico imediatamente ou pode passar o dedo para a esquerda na entrada desse dispositivo na lista usando a tela touch.</span><span class="sxs-lookup"><span data-stu-id="bc61a-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="bc61a-192">Você também pode inicializar imediatamente em um dispositivo USB ou um adaptador de Ethernet USB quando o dispositivo Surface está desligado, pressionando o botão de **Diminuir o Volume** e o botão **Ligar/Desligar** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="bc61a-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="bc61a-193">Para que a ordem de inicialização especificada entre em vigor, você deve definir a opção Habilitar Sequência de **Inicialização** Alternativa como **Ativado**, conforme mostrado na Figura 7.</span><span class="sxs-lookup"><span data-stu-id="bc61a-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurar a ordem de inicialização para o dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="bc61a-195">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="bc61a-195">Figure 7.</span></span> <span data-ttu-id="bc61a-196">Configurar a ordem de inicialização para o dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="bc61a-197">Você também pode ativar e desativar o suporte a IPv6 para PXE com a opção **Habilitar IPv6 para Inicialização de Rede PXE**, por exemplo, ao executar uma implantação do Windows usando o PXE, onde o servidor PXE é configurado somente para IPv4.</span><span class="sxs-lookup"><span data-stu-id="bc61a-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <a name="uefi-menu-management"></a><span data-ttu-id="bc61a-198">Menu UEFI: Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="bc61a-198">UEFI menu: Management</span></span>
<span data-ttu-id="bc61a-199">A página Gerenciamento permite gerenciar o uso do Gerenciamento UEFI zero touch e outros recursos em dispositivos qualificados, incluindo Surface Pro 7, Surface Pro X e Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="bc61a-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="bc61a-200">Gerencie o acesso ao Gerenciamento UEFI do Zero Touch e outros recursos ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Figura 8. Gerenciar o acesso ao Gerenciamento uefi zero toque e outros recursos*</span><span class="sxs-lookup"><span data-stu-id="bc61a-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="bc61a-201">O Gerenciamento uefi de toque zero permite gerenciar remotamente as configurações da UEFI usando um perfil de dispositivo no Intune chamado Interface de Configuração de Firmware de Dispositivo (DFCI).</span><span class="sxs-lookup"><span data-stu-id="bc61a-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="bc61a-202">Se você não configurar essa configuração, a capacidade de gerenciar dispositivos qualificados com DFCI será definida como **Pronto**.</span><span class="sxs-lookup"><span data-stu-id="bc61a-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="bc61a-203">Para impedir o DFCI, selecione **Opt-Out**.</span><span class="sxs-lookup"><span data-stu-id="bc61a-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="bc61a-204">A página de configurações de Gerenciamento da UEFI e o uso do DFCI estão disponíveis no momento para o Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7 e Surface Pro X. Para saber mais, confira [Gerenciamento do Intune das configurações uefi do Surface](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="bc61a-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="uefi-menu-exit"></a><span data-ttu-id="bc61a-205">Menu UEFI: Exit</span><span class="sxs-lookup"><span data-stu-id="bc61a-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="bc61a-206">Use o **botão Reiniciar Agora** na página **Sair** para sair das configurações uefi, conforme mostrado na Figura 9.</span><span class="sxs-lookup"><span data-stu-id="bc61a-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Sair do UEFI do Surface e reiniciar o dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="bc61a-208">Figura 9.</span><span class="sxs-lookup"><span data-stu-id="bc61a-208">Figure 9.</span></span> <span data-ttu-id="bc61a-209">Clique em Reiniciar Agora para sair do UEFI do Surface e reiniciar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="bc61a-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <a name="surface-uefi-boot-screens"></a><span data-ttu-id="bc61a-210">Telas de inicialização UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="bc61a-211">Quando você atualiza o firmware do dispositivo Surface, usando o Windows Update ou instalação manual, as atualizações não são aplicadas imediatamente para o dispositivo, só durante o próximo ciclo de reinicialização.</span><span class="sxs-lookup"><span data-stu-id="bc61a-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="bc61a-212">Você pode saber mais sobre o processo de atualização de firmware do Surface em [Gerenciar e implantar atualizações](manage-surface-driver-and-firmware-updates.md)de firmware e driver do Surface.</span><span class="sxs-lookup"><span data-stu-id="bc61a-212">You can find out more about the Surface firmware update process in [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="bc61a-213">O progresso da atualização do firmware é exibido em uma tela com barras de progresso de cores diferentes para indicar o firmware para cada componente.</span><span class="sxs-lookup"><span data-stu-id="bc61a-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="bc61a-214">A barra de progresso de cada componente é mostrada nas Figuras 9 a 18.</span><span class="sxs-lookup"><span data-stu-id="bc61a-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Atualização de firmware UEFI Surface com barra de progresso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="bc61a-216">Figura 10.</span><span class="sxs-lookup"><span data-stu-id="bc61a-216">Figure 10.</span></span> <span data-ttu-id="bc61a-217">A atualização do firmware UEFI do Surface exibe uma barra de progresso azul</span><span class="sxs-lookup"><span data-stu-id="bc61a-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Firmware de controlador incorporado do sistema com a barra de progresso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="bc61a-219">Figura 11.</span><span class="sxs-lookup"><span data-stu-id="bc61a-219">Figure 11.</span></span> <span data-ttu-id="bc61a-220">A atualização de firmware de controlador incorporado no sistema exibe uma barra de progresso verde</span><span class="sxs-lookup"><span data-stu-id="bc61a-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Atualização do firmware de SAM Controller com barra de progresso laranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="bc61a-222">Figura 12.</span><span class="sxs-lookup"><span data-stu-id="bc61a-222">Figure 12.</span></span> <span data-ttu-id="bc61a-223">A atualização do firmware de SAM Controller exibe uma barra de progresso laranja</span><span class="sxs-lookup"><span data-stu-id="bc61a-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Firmware do Intel Management Engine com barra de progresso vermelho](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="bc61a-225">Figura 13.</span><span class="sxs-lookup"><span data-stu-id="bc61a-225">Figure 13.</span></span> <span data-ttu-id="bc61a-226">A atualização de firmware da Intel Management Engine exibe uma barra de progresso vermelho</span><span class="sxs-lookup"><span data-stu-id="bc61a-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Toque Surface firmware com barra de progresso cinza](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="bc61a-228">Figura 14.</span><span class="sxs-lookup"><span data-stu-id="bc61a-228">Figure 14.</span></span> <span data-ttu-id="bc61a-229">A atualização de firmware do Surface toque exibe uma barra de progresso cinza</span><span class="sxs-lookup"><span data-stu-id="bc61a-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![Firmware do Surface KIP com barra de progresso verde claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="bc61a-231">Figura 15.</span><span class="sxs-lookup"><span data-stu-id="bc61a-231">Figure 15.</span></span> <span data-ttu-id="bc61a-232">A atualização de firmware DO SURFACE KIM exibe uma barra de progresso verde claro</span><span class="sxs-lookup"><span data-stu-id="bc61a-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Firmware do SURFACE ISH com barra de progresso rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="bc61a-234">Figura 16 A atualização de firmware do SURFACE ISH exibe uma barra de progresso rosa claro</span><span class="sxs-lookup"><span data-stu-id="bc61a-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Firmware do Surface Trackpad com barra de progresso cinza](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="bc61a-236">Figura 17.</span><span class="sxs-lookup"><span data-stu-id="bc61a-236">Figure 17.</span></span> <span data-ttu-id="bc61a-237">A atualização de firmware do Surface Trackpad exibe uma barra de progresso rosa</span><span class="sxs-lookup"><span data-stu-id="bc61a-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Firmware do Surface TCON com barra de progresso cinza claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="bc61a-239">Figura 18.</span><span class="sxs-lookup"><span data-stu-id="bc61a-239">Figure 18.</span></span> <span data-ttu-id="bc61a-240">A atualização de firmware do Surface TCON exibe uma barra de progresso cinza claro</span><span class="sxs-lookup"><span data-stu-id="bc61a-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Firmware do Surface TPM com barra de progresso roxo claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="bc61a-242">Figura 19.</span><span class="sxs-lookup"><span data-stu-id="bc61a-242">Figure 19.</span></span> <span data-ttu-id="bc61a-243">A atualização de firmware do Surface TPM exibe uma barra de progresso roxo</span><span class="sxs-lookup"><span data-stu-id="bc61a-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="bc61a-244">Uma mensagem de aviso adicional que indica que a Inicialização Segura está desabilitada, conforme mostrado na Figura 19.</span><span class="sxs-lookup"><span data-stu-id="bc61a-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Tela de inicialização do Surface que indica que a inicialização segura foi desabilitada](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="bc61a-246">Figura 20.</span><span class="sxs-lookup"><span data-stu-id="bc61a-246">Figure 20.</span></span> <span data-ttu-id="bc61a-247">Tela de inicialização do Surface que indica que a inicialização segura foi desativada nas configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <a name="references"></a><span data-ttu-id="bc61a-248">Referências</span><span class="sxs-lookup"><span data-stu-id="bc61a-248">References</span></span>

1. <span data-ttu-id="bc61a-249">Surface Go e Surface Go 2 usam uma UEFI de terceiros e não suportam DFCI.</span><span class="sxs-lookup"><span data-stu-id="bc61a-249">Surface Go and Surface Go 2 use a third-party UEFI and do not support DFCI.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="bc61a-250">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bc61a-250">Related topics</span></span>

- [<span data-ttu-id="bc61a-251">Gerenciamento pelo Intune das configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="bc61a-252">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="bc61a-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
