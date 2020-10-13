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
ms.date: 10/12/2020
ms.openlocfilehash: 218f98b23adcb7bae2af92655d85144c6e5665e6
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114719"
---
# <span data-ttu-id="f10ee-104">Gerenciar configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="f10ee-105">Todas as gerações atuais e futuras de dispositivos Surface usam uma Unified Extensible Firmware Interface (UEFI) exclusiva pela Microsoft, especificamente para esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f10ee-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="f10ee-106">As configurações de Surface UEFI fornecem a capacidade de habilitar ou desabilitar dispositivos e componentes internos, impedir que as configurações de UEFI sejam alteradas e ajustar as configurações de inicialização do dispositivo de superfície.</span><span class="sxs-lookup"><span data-stu-id="f10ee-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="f10ee-107">Produtos compatíveis</span><span class="sxs-lookup"><span data-stu-id="f10ee-107">Supported products</span></span>

<span data-ttu-id="f10ee-108">O gerenciamento de UEFI tem suporte nos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="f10ee-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="f10ee-109">Surface Pro 4, Surface pro (5ª gen), Surface pro 6, Surface Pro 7, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="f10ee-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro X</span></span>
- <span data-ttu-id="f10ee-110">Laptop Surface (1ª gen), Surface laptop 2, Surface laptop 3, Surface laptop go</span><span class="sxs-lookup"><span data-stu-id="f10ee-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="f10ee-111">Surface Studio (1ª gen), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="f10ee-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="f10ee-112">Livro de superfície, livro Surface 2, livro Surface 3</span><span class="sxs-lookup"><span data-stu-id="f10ee-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="f10ee-113">Surface Go, Surface go 2</span><span class="sxs-lookup"><span data-stu-id="f10ee-113">Surface Go, Surface Go 2</span></span>

## <span data-ttu-id="f10ee-114">Suporte para gerenciamento baseado em nuvem</span><span class="sxs-lookup"><span data-stu-id="f10ee-114">Support for cloud-based management</span></span>

<span data-ttu-id="f10ee-115">Com os perfis da interface de configuração do firmware do dispositivo (DFCI) incorporados ao Microsoft Intune (agora disponível no modo de visualização pública), o gerenciamento de UEFI da superfície estende a pilha de gerenciamento moderno para o nível de hardware UEFI.</span><span class="sxs-lookup"><span data-stu-id="f10ee-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="f10ee-116">O DFCI é compatível com o provisionamento de Zero Touch, elimina as senhas do BIOS, fornece o controle das configurações de segurança, incluindo opções de inicialização e periféricos incorporados, e prepara a base para cenários de segurança avançada no futuro.</span><span class="sxs-lookup"><span data-stu-id="f10ee-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="f10ee-117">O DFCI está disponível atualmente para o Surface Pro 7, Surface Pro X e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="f10ee-117">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="f10ee-118">Para obter mais informações, consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="f10ee-118">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="f10ee-119">Menu UEFI de abertura de superfície</span><span class="sxs-lookup"><span data-stu-id="f10ee-119">Open Surface UEFI menu</span></span>

<span data-ttu-id="f10ee-120">Para ajustar as configurações de UEFI durante a inicialização do sistema:</span><span class="sxs-lookup"><span data-stu-id="f10ee-120">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="f10ee-121">Desligue sua superfície e aguarde cerca de 10 segundos para ter certeza de que está desligado.</span><span class="sxs-lookup"><span data-stu-id="f10ee-121">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="f10ee-122">Pressione e mantenha pressionado o botão **volume-up** e-ao mesmo tempo-pressione e libere o **botão de energia.**</span><span class="sxs-lookup"><span data-stu-id="f10ee-122">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="f10ee-123">Quando o logotipo da Microsoft ou do Surface aparecer na tela, continue a manter o botão **volume-up** até que a tela UEFI seja exibida.</span><span class="sxs-lookup"><span data-stu-id="f10ee-123">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="f10ee-124">Página de informações do PC UEFI</span><span class="sxs-lookup"><span data-stu-id="f10ee-124">UEFI PC information page</span></span>

<span data-ttu-id="f10ee-125">A página informações do PC inclui informações detalhadas sobre o seu dispositivo Surface:</span><span class="sxs-lookup"><span data-stu-id="f10ee-125">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="f10ee-126">**Modelo** – o modelo do seu dispositivo de superfície será exibido aqui, como o Surface Book 2 ou Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="f10ee-126">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="f10ee-127">A configuração exata de seu dispositivo não é exibida, (como processador, tamanho do disco ou tamanho da memória).</span><span class="sxs-lookup"><span data-stu-id="f10ee-127">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="f10ee-128">**UUID** – esse número de identificação universalmente exclusivo é específico de seu dispositivo e usado para identificar o dispositivo durante a implantação ou gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f10ee-128">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="f10ee-129">**Número de Série** – esse número é usado para identificar esse dispositivo Surface específico para cenários de marcação de ativos e suporte.</span><span class="sxs-lookup"><span data-stu-id="f10ee-129">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="f10ee-130">**Marca do Ativo** – a marca do ativo é atribuída ao dispositivo Surface com a [Ferramenta de Marca do Ativo](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="f10ee-130">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="f10ee-131">Você também encontrará informações detalhadas sobre o firmware de seu dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="f10ee-131">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="f10ee-132">Os dispositivos Surface têm vários componentes internos que executam diferentes versões do firmware.</span><span class="sxs-lookup"><span data-stu-id="f10ee-132">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="f10ee-133">A versão do firmware de cada um dos seguintes dispositivos é exibida na página **Informações do computador** (como mostrado na Figura 1):</span><span class="sxs-lookup"><span data-stu-id="f10ee-133">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="f10ee-134">Sistema UEFI</span><span class="sxs-lookup"><span data-stu-id="f10ee-134">System UEFI</span></span> 

- <span data-ttu-id="f10ee-135">Controlador SAM</span><span class="sxs-lookup"><span data-stu-id="f10ee-135">SAM Controller</span></span> 

- <span data-ttu-id="f10ee-136">Intel Management Engine</span><span class="sxs-lookup"><span data-stu-id="f10ee-136">Intel Management Engine</span></span> 

- <span data-ttu-id="f10ee-137">Controlador Incorporado do Sistema</span><span class="sxs-lookup"><span data-stu-id="f10ee-137">System Embedded Controller</span></span> 

- <span data-ttu-id="f10ee-138">Firmware de Toque</span><span class="sxs-lookup"><span data-stu-id="f10ee-138">Touch Firmware</span></span> 

![Informações do sistema e informações de versão do firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="f10ee-140">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="f10ee-140">Figure 1.</span></span> <span data-ttu-id="f10ee-141">Informações do sistema e informações de versão do firmware</span><span class="sxs-lookup"><span data-stu-id="f10ee-141">System information and firmware version information</span></span>*

<span data-ttu-id="f10ee-142">Você pode encontrar informações atualizadas sobre a versão mais recente do firmware para o dispositivo Surface no [Histórico de Atualizações do Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f10ee-142">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="f10ee-143">Página de segurança UEFI</span><span class="sxs-lookup"><span data-stu-id="f10ee-143">UEFI Security page</span></span> 

![Definir configurações de segurança de UEFI do Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="f10ee-145">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="f10ee-145">Figure 2.</span></span> <span data-ttu-id="f10ee-146">Definir configurações de segurança de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-146">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="f10ee-147">A página segurança permite definir uma senha para proteger as configurações de UEFI.</span><span class="sxs-lookup"><span data-stu-id="f10ee-147">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="f10ee-148">Essa senha deve ser inserida quando você inicializa o dispositivo Surface para UEFI.</span><span class="sxs-lookup"><span data-stu-id="f10ee-148">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="f10ee-149">A senha pode conter os seguintes caracteres (conforme mostrado na Figura 3):</span><span class="sxs-lookup"><span data-stu-id="f10ee-149">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="f10ee-150">Letras maiúsculas: A-Z</span><span class="sxs-lookup"><span data-stu-id="f10ee-150">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="f10ee-151">Letras minúsculas: a-z</span><span class="sxs-lookup"><span data-stu-id="f10ee-151">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="f10ee-152">Números: 1-0</span><span class="sxs-lookup"><span data-stu-id="f10ee-152">Numbers: 1-0</span></span> 

- <span data-ttu-id="f10ee-153">Caracteres especiais:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: ' ' "</span><span class="sxs-lookup"><span data-stu-id="f10ee-153">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="f10ee-154">A senha deve ter pelo menos 6 caracteres e diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f10ee-154">The password must be at least 6 characters and is case sensitive.</span></span> 

![Adicionar uma senha para proteger as configurações de UEFI do Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="f10ee-156">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="f10ee-156">Figure 3.</span></span> <span data-ttu-id="f10ee-157">Adicionar uma senha para proteger as configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-157">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="f10ee-158">Na página Segurança também é possível alterar a configuração de Inicialização Segura no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="f10ee-158">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="f10ee-159">A tecnologia de Inicialização Segura impede que o código de inicialização não autorizado inicialize no dispositivo Surface, o que protege contra infecções por malware do tipo bootkit e rootkit.</span><span class="sxs-lookup"><span data-stu-id="f10ee-159">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="f10ee-160">Você pode desabilitar a Inicialização Segura para permitir que o dispositivo Surface inicialize sistemas operacionais de terceiros ou mídia inicializável.</span><span class="sxs-lookup"><span data-stu-id="f10ee-160">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="f10ee-161">Você também pode configurar o Secure boot para funcionar com certificados de terceiros, como mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="f10ee-161">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="f10ee-162">Leia mais sobre a [Inicialização Segura](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) na Biblioteca do TechNet.</span><span class="sxs-lookup"><span data-stu-id="f10ee-162">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurar a Inicialização Segura](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="f10ee-164">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="f10ee-164">Figure 4.</span></span> <span data-ttu-id="f10ee-165">Configurar a Inicialização Segura</span><span class="sxs-lookup"><span data-stu-id="f10ee-165">Configure Secure Boot</span></span>*

<span data-ttu-id="f10ee-166">Dependendo do seu dispositivo, também é possível ver se o seu TPM está habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="f10ee-166">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="f10ee-167">Se você não vir a configuração **habilitar TPM**  , abra TPM. msc no Windows para verificar o status, conforme mostrado na Figura 5.</span><span class="sxs-lookup"><span data-stu-id="f10ee-167">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="f10ee-168">O TPM é usado para autenticar a criptografia dos dados de seu dispositivo com o BitLocker.</span><span class="sxs-lookup"><span data-stu-id="f10ee-168">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="f10ee-169">Para saber mais, consulte [visão geral do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="f10ee-169">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Console TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="f10ee-171">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="f10ee-171">Figure 5.</span></span> <span data-ttu-id="f10ee-172">Console TPM</span><span class="sxs-lookup"><span data-stu-id="f10ee-172">TPM console</span></span>*


## <span data-ttu-id="f10ee-173">Menu UEFI: dispositivos</span><span class="sxs-lookup"><span data-stu-id="f10ee-173">UEFI menu: Devices</span></span> 

<span data-ttu-id="f10ee-174">A página dispositivos permite habilitar ou desabilitar dispositivos e componentes específicos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="f10ee-174">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="f10ee-175">Encaixe e portas USB</span><span class="sxs-lookup"><span data-stu-id="f10ee-175">Docking and USB Ports</span></span> 

- <span data-ttu-id="f10ee-176">Slot de cartão MicroSD ou SD</span><span class="sxs-lookup"><span data-stu-id="f10ee-176">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="f10ee-177">Câmera Traseira</span><span class="sxs-lookup"><span data-stu-id="f10ee-177">Rear Camera</span></span> 

- <span data-ttu-id="f10ee-178">Câmera Frontal</span><span class="sxs-lookup"><span data-stu-id="f10ee-178">Front Camera</span></span> 

- <span data-ttu-id="f10ee-179">Câmera de infravermelho (IV)</span><span class="sxs-lookup"><span data-stu-id="f10ee-179">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="f10ee-180">Wi-Fi e Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f10ee-180">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="f10ee-181">Áudio integrado (alto-falantes e microfone)</span><span class="sxs-lookup"><span data-stu-id="f10ee-181">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="f10ee-182">Cada dispositivo é listado com um botão deslizante que você pode mover para a posição **ativado** (ativado) ou **desativado** (desabilitado), conforme mostrado na Figura 6.</span><span class="sxs-lookup"><span data-stu-id="f10ee-182">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Habilitar e desabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="f10ee-184">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="f10ee-184">Figure 6.</span></span> <span data-ttu-id="f10ee-185">Habilitar e desabilitar dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="f10ee-185">Enable and disable specific devices</span></span>*

## <span data-ttu-id="f10ee-186">Menu UEFI: configuração de inicialização</span><span class="sxs-lookup"><span data-stu-id="f10ee-186">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="f10ee-187">A página de configuração de inicialização permite alterar a ordem dos dispositivos de inicialização, bem como habilitar ou desabilitar a inicialização dos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f10ee-187">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="f10ee-188">Gerenciador de Inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="f10ee-188">Windows Boot Manager</span></span> 

- <span data-ttu-id="f10ee-189">Armazenamento USB</span><span class="sxs-lookup"><span data-stu-id="f10ee-189">USB Storage</span></span> 

- <span data-ttu-id="f10ee-190">Rede PXE</span><span class="sxs-lookup"><span data-stu-id="f10ee-190">PXE Network</span></span> 

- <span data-ttu-id="f10ee-191">Armazenamento interno</span><span class="sxs-lookup"><span data-stu-id="f10ee-191">Internal Storage</span></span> 

<span data-ttu-id="f10ee-192">Você pode inicializar a partir de um dispositivo específico imediatamente ou pode passar o dedo para a esquerda na entrada desse dispositivo na lista usando a tela touch.</span><span class="sxs-lookup"><span data-stu-id="f10ee-192">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="f10ee-193">Você também pode inicializar imediatamente em um dispositivo USB ou um adaptador de Ethernet USB quando o dispositivo Surface está desligado, pressionando o botão de **Diminuir o Volume** e o botão **Ligar/Desligar** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f10ee-193">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="f10ee-194">Para que a ordem de inicialização especificada entre em vigor, você deve definir a opção **habilitar sequência de inicialização alternativa** como **ativa**, conforme mostrado na Figura 7.</span><span class="sxs-lookup"><span data-stu-id="f10ee-194">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurar a ordem de inicialização para o dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="f10ee-196">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="f10ee-196">Figure 7.</span></span> <span data-ttu-id="f10ee-197">Configurar a ordem de inicialização para o dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-197">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="f10ee-198">Você também pode ativar e desativar o suporte a IPv6 para PXE com a opção **Habilitar IPv6 para Inicialização de Rede PXE**, por exemplo, ao executar uma implantação do Windows usando o PXE, onde o servidor PXE é configurado somente para IPv4.</span><span class="sxs-lookup"><span data-stu-id="f10ee-198">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="f10ee-199">Menu UEFI: gerenciamento</span><span class="sxs-lookup"><span data-stu-id="f10ee-199">UEFI menu: Management</span></span>
<span data-ttu-id="f10ee-200">A página Gerenciamento permite que você gerencie o uso do gerenciamento de UEFI de toque zero e outros recursos em dispositivos qualificados, incluindo Surface Pro 7, Surface Pro X e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="f10ee-200">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="f10ee-201">Gerencie o acesso a Zero Touch Management e outros recursos ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Figura 8. Gerenciar o acesso a Zero Touch Management e outros recursos*</span><span class="sxs-lookup"><span data-stu-id="f10ee-201">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="f10ee-202">O gerenciamento de UEFI de Zero Touch permite que você gerencie remotamente as configurações de UEFI usando um perfil de dispositivo dentro do Intune chamado interface de configuração do firmware do dispositivo (DFCI).</span><span class="sxs-lookup"><span data-stu-id="f10ee-202">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="f10ee-203">Se você não definir essa configuração, a capacidade de gerenciar dispositivos qualificados com o DFCI será definida como **pronto**.</span><span class="sxs-lookup"><span data-stu-id="f10ee-203">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="f10ee-204">Para impedir o DFCI, escolha **recusar**.</span><span class="sxs-lookup"><span data-stu-id="f10ee-204">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="f10ee-205">A página de configurações de gerenciamento de UEFI e o uso de DFCI só estão disponíveis no Surface Pro 7, Surface Pro X e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="f10ee-205">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="f10ee-206">Para obter mais informações, consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="f10ee-206">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="f10ee-207">Menu UEFI: sair</span><span class="sxs-lookup"><span data-stu-id="f10ee-207">UEFI menu: Exit</span></span> 

<span data-ttu-id="f10ee-208">Use o botão **reiniciar agora** na página **sair** para sair das configurações de UEFI, conforme mostrado na Figura 9.</span><span class="sxs-lookup"><span data-stu-id="f10ee-208">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Sair do UEFI do Surface e reiniciar o dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="f10ee-210">Figura 9.</span><span class="sxs-lookup"><span data-stu-id="f10ee-210">Figure 9.</span></span> <span data-ttu-id="f10ee-211">Clique em Reiniciar Agora para sair do UEFI do Surface e reiniciar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="f10ee-211">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="f10ee-212">Telas de inicialização UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-212">Surface UEFI boot screens</span></span>

<span data-ttu-id="f10ee-213">Quando você atualiza o firmware do dispositivo Surface, usando o Windows Update ou instalação manual, as atualizações não são aplicadas imediatamente para o dispositivo, só durante o próximo ciclo de reinicialização.</span><span class="sxs-lookup"><span data-stu-id="f10ee-213">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="f10ee-214">Você pode saber mais sobre o processo de atualização do firmware do Surface no [Gerenciar atualizações de driver e firmware do Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="f10ee-214">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="f10ee-215">O progresso da atualização do firmware é exibido em uma tela com barras de progresso de cores diferentes para indicar o firmware para cada componente.</span><span class="sxs-lookup"><span data-stu-id="f10ee-215">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="f10ee-216">A barra de progresso de cada componente é mostrada nos números de 9 a 18.</span><span class="sxs-lookup"><span data-stu-id="f10ee-216">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Atualização de firmware UEFI Surface com barra de progresso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="f10ee-218">Figura 10.</span><span class="sxs-lookup"><span data-stu-id="f10ee-218">Figure 10.</span></span> <span data-ttu-id="f10ee-219">A atualização do firmware UEFI do Surface exibe uma barra de progresso azul</span><span class="sxs-lookup"><span data-stu-id="f10ee-219">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Firmware de controlador incorporado do sistema com a barra de progresso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="f10ee-221">Figura 11.</span><span class="sxs-lookup"><span data-stu-id="f10ee-221">Figure 11.</span></span> <span data-ttu-id="f10ee-222">A atualização de firmware de controlador incorporado no sistema exibe uma barra de progresso verde</span><span class="sxs-lookup"><span data-stu-id="f10ee-222">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Atualização do firmware de SAM Controller com barra de progresso laranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="f10ee-224">Figura 12.</span><span class="sxs-lookup"><span data-stu-id="f10ee-224">Figure 12.</span></span> <span data-ttu-id="f10ee-225">A atualização do firmware de SAM Controller exibe uma barra de progresso laranja</span><span class="sxs-lookup"><span data-stu-id="f10ee-225">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Firmware do Intel Management Engine com barra de progresso vermelho](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="f10ee-227">Figura 13.</span><span class="sxs-lookup"><span data-stu-id="f10ee-227">Figure 13.</span></span> <span data-ttu-id="f10ee-228">A atualização de firmware da Intel Management Engine exibe uma barra de progresso vermelho</span><span class="sxs-lookup"><span data-stu-id="f10ee-228">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Toque Surface firmware com barra de progresso cinza](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="f10ee-230">Figura 14.</span><span class="sxs-lookup"><span data-stu-id="f10ee-230">Figure 14.</span></span> <span data-ttu-id="f10ee-231">A atualização de firmware do Surface toque exibe uma barra de progresso cinza</span><span class="sxs-lookup"><span data-stu-id="f10ee-231">The Surface touch firmware update displays a gray progress bar</span></span>*

![Firmware do Surface KIP com barra de progresso verde claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="f10ee-233">Figura 15.</span><span class="sxs-lookup"><span data-stu-id="f10ee-233">Figure 15.</span></span> <span data-ttu-id="f10ee-234">A atualização do firmware do Surface KIP exibe uma barra de progresso verde claro</span><span class="sxs-lookup"><span data-stu-id="f10ee-234">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Firmware do Surface ISH com barra de progresso rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="f10ee-236">Figura 16 a atualização do firmware do Surface ISH exibe uma barra de progresso rosa clara</span><span class="sxs-lookup"><span data-stu-id="f10ee-236">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Firmware do Surface trackpad com barra de progresso cinza](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="f10ee-238">Figura 17.</span><span class="sxs-lookup"><span data-stu-id="f10ee-238">Figure 17.</span></span> <span data-ttu-id="f10ee-239">A atualização do firmware do Surface trackpad exibe uma barra de progresso rosa</span><span class="sxs-lookup"><span data-stu-id="f10ee-239">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Firmware do Surface TCON com barra de progresso cinza claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="f10ee-241">Figura 18.</span><span class="sxs-lookup"><span data-stu-id="f10ee-241">Figure 18.</span></span> <span data-ttu-id="f10ee-242">A atualização do firmware do Surface TCON exibe uma barra de progresso cinza claro</span><span class="sxs-lookup"><span data-stu-id="f10ee-242">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Firmware de Surface TPM com barra de progresso roxo claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="f10ee-244">Figura 19.</span><span class="sxs-lookup"><span data-stu-id="f10ee-244">Figure 19.</span></span> <span data-ttu-id="f10ee-245">A atualização do firmware de Surface TPM exibe uma barra de progresso roxa</span><span class="sxs-lookup"><span data-stu-id="f10ee-245">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="f10ee-246">Uma mensagem de aviso adicional que indica que a inicialização segura está desabilitada é exibida, conforme mostrado na Figura 19.</span><span class="sxs-lookup"><span data-stu-id="f10ee-246">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Tela de inicialização do Surface que indica que a inicialização segura foi desabilitada](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="f10ee-248">Figura 20.</span><span class="sxs-lookup"><span data-stu-id="f10ee-248">Figure 20.</span></span> <span data-ttu-id="f10ee-249">Tela de inicialização do Surface que indica que a inicialização segura foi desativada nas configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-249">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="f10ee-250">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f10ee-250">Related topics</span></span>

- [<span data-ttu-id="f10ee-251">Gerenciamento pelo Intune das configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="f10ee-252">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="f10ee-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
