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
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830566"
---
# <span data-ttu-id="0ec55-104">Gerenciar configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="0ec55-105">Todas as gerações atuais e futuras de dispositivos Surface usam uma Unified Extensible Firmware Interface (UEFI) exclusiva pela Microsoft, especificamente para esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ec55-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="0ec55-106">As configurações de Surface UEFI fornecem a capacidade de habilitar ou desabilitar dispositivos e componentes internos, impedir que as configurações de UEFI sejam alteradas e ajustar as configurações de inicialização do dispositivo de superfície.</span><span class="sxs-lookup"><span data-stu-id="0ec55-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="0ec55-107">Suporte para gerenciamento baseado em nuvem</span><span class="sxs-lookup"><span data-stu-id="0ec55-107">Support for cloud-based management</span></span>

<span data-ttu-id="0ec55-108">Com os perfis da interface de configuração do firmware do dispositivo (DFCI) incorporados ao Microsoft Intune (agora disponível no modo de visualização pública), o gerenciamento de UEFI da superfície estende a pilha de gerenciamento moderno para o nível de hardware UEFI.</span><span class="sxs-lookup"><span data-stu-id="0ec55-108">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="0ec55-109">O DFCI é compatível com o provisionamento de Zero Touch, elimina as senhas do BIOS, fornece o controle das configurações de segurança, incluindo opções de inicialização e periféricos incorporados, e prepara a base para cenários de segurança avançada no futuro.</span><span class="sxs-lookup"><span data-stu-id="0ec55-109">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="0ec55-110">O DFCI está disponível atualmente para o Surface Pro 7, Surface Pro X e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="0ec55-110">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="0ec55-111">Para obter mais informações, consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="0ec55-111">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="0ec55-112">Menu UEFI de abertura de superfície</span><span class="sxs-lookup"><span data-stu-id="0ec55-112">Open Surface UEFI menu</span></span>

<span data-ttu-id="0ec55-113">Para ajustar as configurações de UEFI durante a inicialização do sistema:</span><span class="sxs-lookup"><span data-stu-id="0ec55-113">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="0ec55-114">Desligue sua superfície e aguarde cerca de 10 segundos para ter certeza de que está desligado.</span><span class="sxs-lookup"><span data-stu-id="0ec55-114">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="0ec55-115">Pressione e mantenha pressionado o botão **volume-up** e-ao mesmo tempo-pressione e libere o **botão de energia.**</span><span class="sxs-lookup"><span data-stu-id="0ec55-115">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="0ec55-116">Quando o logotipo da Microsoft ou do Surface aparecer na tela, continue a manter o botão **volume-up** até que a tela UEFI seja exibida.</span><span class="sxs-lookup"><span data-stu-id="0ec55-116">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="0ec55-117">Página de informações do PC UEFI</span><span class="sxs-lookup"><span data-stu-id="0ec55-117">UEFI PC information page</span></span>

<span data-ttu-id="0ec55-118">A página informações do PC inclui informações detalhadas sobre o seu dispositivo Surface:</span><span class="sxs-lookup"><span data-stu-id="0ec55-118">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="0ec55-119">**Modelo** – o modelo do seu dispositivo de superfície será exibido aqui, como o Surface Book 2 ou Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="0ec55-119">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="0ec55-120">A configuração exata de seu dispositivo não é exibida, (como processador, tamanho do disco ou tamanho da memória).</span><span class="sxs-lookup"><span data-stu-id="0ec55-120">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="0ec55-121">**UUID** – esse número de identificação universalmente exclusivo é específico de seu dispositivo e usado para identificar o dispositivo durante a implantação ou gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="0ec55-121">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="0ec55-122">**Número de Série** – esse número é usado para identificar esse dispositivo Surface específico para cenários de marcação de ativos e suporte.</span><span class="sxs-lookup"><span data-stu-id="0ec55-122">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="0ec55-123">**Marca do Ativo** – a marca do ativo é atribuída ao dispositivo Surface com a [Ferramenta de Marca do Ativo](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="0ec55-123">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="0ec55-124">Você também encontrará informações detalhadas sobre o firmware de seu dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="0ec55-124">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="0ec55-125">Os dispositivos Surface têm vários componentes internos que executam diferentes versões do firmware.</span><span class="sxs-lookup"><span data-stu-id="0ec55-125">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="0ec55-126">A versão do firmware de cada um dos seguintes dispositivos é exibida na página **Informações do computador** (como mostrado na Figura 1):</span><span class="sxs-lookup"><span data-stu-id="0ec55-126">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="0ec55-127">Sistema UEFI</span><span class="sxs-lookup"><span data-stu-id="0ec55-127">System UEFI</span></span> 

- <span data-ttu-id="0ec55-128">Controlador SAM</span><span class="sxs-lookup"><span data-stu-id="0ec55-128">SAM Controller</span></span> 

- <span data-ttu-id="0ec55-129">Intel Management Engine</span><span class="sxs-lookup"><span data-stu-id="0ec55-129">Intel Management Engine</span></span> 

- <span data-ttu-id="0ec55-130">Controlador Incorporado do Sistema</span><span class="sxs-lookup"><span data-stu-id="0ec55-130">System Embedded Controller</span></span> 

- <span data-ttu-id="0ec55-131">Firmware de Toque</span><span class="sxs-lookup"><span data-stu-id="0ec55-131">Touch Firmware</span></span> 

![Informações do sistema e informações de versão do firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="0ec55-133">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="0ec55-133">Figure 1.</span></span> <span data-ttu-id="0ec55-134">Informações do sistema e informações de versão do firmware</span><span class="sxs-lookup"><span data-stu-id="0ec55-134">System information and firmware version information</span></span>*

<span data-ttu-id="0ec55-135">Você pode encontrar informações atualizadas sobre a versão mais recente do firmware para o dispositivo Surface no [Histórico de Atualizações do Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ec55-135">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="0ec55-136">Página de segurança UEFI</span><span class="sxs-lookup"><span data-stu-id="0ec55-136">UEFI Security page</span></span> 

![Definir configurações de segurança de UEFI do Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="0ec55-138">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="0ec55-138">Figure 2.</span></span> <span data-ttu-id="0ec55-139">Definir configurações de segurança de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-139">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="0ec55-140">A página segurança permite definir uma senha para proteger as configurações de UEFI.</span><span class="sxs-lookup"><span data-stu-id="0ec55-140">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="0ec55-141">Essa senha deve ser inserida quando você inicializa o dispositivo Surface para UEFI.</span><span class="sxs-lookup"><span data-stu-id="0ec55-141">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="0ec55-142">A senha pode conter os seguintes caracteres (conforme mostrado na Figura 3):</span><span class="sxs-lookup"><span data-stu-id="0ec55-142">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="0ec55-143">Letras maiúsculas: A-Z</span><span class="sxs-lookup"><span data-stu-id="0ec55-143">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="0ec55-144">Letras minúsculas: a-z</span><span class="sxs-lookup"><span data-stu-id="0ec55-144">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="0ec55-145">Números: 1-0</span><span class="sxs-lookup"><span data-stu-id="0ec55-145">Numbers: 1-0</span></span> 

- <span data-ttu-id="0ec55-146">Caracteres especiais:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: ' ' "</span><span class="sxs-lookup"><span data-stu-id="0ec55-146">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="0ec55-147">A senha deve ter pelo menos 6 caracteres e diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0ec55-147">The password must be at least 6 characters and is case sensitive.</span></span> 

![Adicionar uma senha para proteger as configurações de UEFI do Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="0ec55-149">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="0ec55-149">Figure 3.</span></span> <span data-ttu-id="0ec55-150">Adicionar uma senha para proteger as configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-150">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="0ec55-151">Na página Segurança também é possível alterar a configuração de Inicialização Segura no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="0ec55-151">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="0ec55-152">A tecnologia de Inicialização Segura impede que o código de inicialização não autorizado inicialize no dispositivo Surface, o que protege contra infecções por malware do tipo bootkit e rootkit.</span><span class="sxs-lookup"><span data-stu-id="0ec55-152">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="0ec55-153">Você pode desabilitar a Inicialização Segura para permitir que o dispositivo Surface inicialize sistemas operacionais de terceiros ou mídia inicializável.</span><span class="sxs-lookup"><span data-stu-id="0ec55-153">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="0ec55-154">Você também pode configurar o Secure boot para funcionar com certificados de terceiros, como mostrado na Figura 4.</span><span class="sxs-lookup"><span data-stu-id="0ec55-154">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="0ec55-155">Leia mais sobre a [Inicialização Segura](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) na Biblioteca do TechNet.</span><span class="sxs-lookup"><span data-stu-id="0ec55-155">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurar a Inicialização Segura](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="0ec55-157">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="0ec55-157">Figure 4.</span></span> <span data-ttu-id="0ec55-158">Configurar a Inicialização Segura</span><span class="sxs-lookup"><span data-stu-id="0ec55-158">Configure Secure Boot</span></span>*

<span data-ttu-id="0ec55-159">Dependendo do seu dispositivo, também é possível ver se o seu TPM está habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="0ec55-159">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="0ec55-160">Se você não vir a configuração **habilitar TPM** , abra TPM. msc no Windows para verificar o status, conforme mostrado na Figura 5.</span><span class="sxs-lookup"><span data-stu-id="0ec55-160">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="0ec55-161">O TPM é usado para autenticar a criptografia dos dados de seu dispositivo com o BitLocker.</span><span class="sxs-lookup"><span data-stu-id="0ec55-161">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="0ec55-162">Para saber mais, consulte [visão geral do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="0ec55-162">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Console TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="0ec55-164">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="0ec55-164">Figure 5.</span></span> <span data-ttu-id="0ec55-165">Console TPM</span><span class="sxs-lookup"><span data-stu-id="0ec55-165">TPM console</span></span>*


## <span data-ttu-id="0ec55-166">Menu UEFI: dispositivos</span><span class="sxs-lookup"><span data-stu-id="0ec55-166">UEFI menu: Devices</span></span> 

<span data-ttu-id="0ec55-167">A página dispositivos permite habilitar ou desabilitar dispositivos e componentes específicos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="0ec55-167">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="0ec55-168">Encaixe e portas USB</span><span class="sxs-lookup"><span data-stu-id="0ec55-168">Docking and USB Ports</span></span> 

- <span data-ttu-id="0ec55-169">Slot de cartão MicroSD ou SD</span><span class="sxs-lookup"><span data-stu-id="0ec55-169">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="0ec55-170">Câmera Traseira</span><span class="sxs-lookup"><span data-stu-id="0ec55-170">Rear Camera</span></span> 

- <span data-ttu-id="0ec55-171">Câmera Frontal</span><span class="sxs-lookup"><span data-stu-id="0ec55-171">Front Camera</span></span> 

- <span data-ttu-id="0ec55-172">Câmera de infravermelho (IV)</span><span class="sxs-lookup"><span data-stu-id="0ec55-172">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="0ec55-173">Wi-Fi e Bluetooth</span><span class="sxs-lookup"><span data-stu-id="0ec55-173">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="0ec55-174">Áudio integrado (alto-falantes e microfone)</span><span class="sxs-lookup"><span data-stu-id="0ec55-174">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="0ec55-175">Cada dispositivo é listado com um botão deslizante que você pode mover para a posição **ativado** (ativado) ou **desativado** (desabilitado), conforme mostrado na Figura 6.</span><span class="sxs-lookup"><span data-stu-id="0ec55-175">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Habilitar e desabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="0ec55-177">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="0ec55-177">Figure 6.</span></span> <span data-ttu-id="0ec55-178">Habilitar e desabilitar dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="0ec55-178">Enable and disable specific devices</span></span>*

## <span data-ttu-id="0ec55-179">Menu UEFI: configuração de inicialização</span><span class="sxs-lookup"><span data-stu-id="0ec55-179">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="0ec55-180">A página de configuração de inicialização permite alterar a ordem dos dispositivos de inicialização, bem como habilitar ou desabilitar a inicialização dos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="0ec55-180">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="0ec55-181">Gerenciador de Inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="0ec55-181">Windows Boot Manager</span></span> 

- <span data-ttu-id="0ec55-182">Armazenamento USB</span><span class="sxs-lookup"><span data-stu-id="0ec55-182">USB Storage</span></span> 

- <span data-ttu-id="0ec55-183">Rede PXE</span><span class="sxs-lookup"><span data-stu-id="0ec55-183">PXE Network</span></span> 

- <span data-ttu-id="0ec55-184">Armazenamento interno</span><span class="sxs-lookup"><span data-stu-id="0ec55-184">Internal Storage</span></span> 

<span data-ttu-id="0ec55-185">Você pode inicializar a partir de um dispositivo específico imediatamente ou pode passar o dedo para a esquerda na entrada desse dispositivo na lista usando a tela touch.</span><span class="sxs-lookup"><span data-stu-id="0ec55-185">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="0ec55-186">Você também pode inicializar imediatamente em um dispositivo USB ou um adaptador de Ethernet USB quando o dispositivo Surface está desligado, pressionando o botão de **Diminuir o Volume** e o botão **Ligar/Desligar** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="0ec55-186">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="0ec55-187">Para que a ordem de inicialização especificada entre em vigor, você deve definir a opção **habilitar sequência de inicialização alternativa** como **ativa**, conforme mostrado na Figura 7.</span><span class="sxs-lookup"><span data-stu-id="0ec55-187">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurar a ordem de inicialização para o dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="0ec55-189">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="0ec55-189">Figure 7.</span></span> <span data-ttu-id="0ec55-190">Configurar a ordem de inicialização para o dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-190">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="0ec55-191">Você também pode ativar e desativar o suporte a IPv6 para PXE com a opção **Habilitar IPv6 para Inicialização de Rede PXE**, por exemplo, ao executar uma implantação do Windows usando o PXE, onde o servidor PXE é configurado somente para IPv4.</span><span class="sxs-lookup"><span data-stu-id="0ec55-191">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="0ec55-192">Menu UEFI: gerenciamento</span><span class="sxs-lookup"><span data-stu-id="0ec55-192">UEFI menu: Management</span></span>
<span data-ttu-id="0ec55-193">A página Gerenciamento permite que você gerencie o uso do gerenciamento de UEFI de toque zero e outros recursos em dispositivos qualificados, incluindo Surface Pro 7, Surface Pro X e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="0ec55-193">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="0ec55-194">Gerencie o acesso a Zero Touch Management e outros recursos ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Figura 8. Gerenciar o acesso a Zero Touch Management e outros recursos*</span><span class="sxs-lookup"><span data-stu-id="0ec55-194">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="0ec55-195">O gerenciamento de UEFI de Zero Touch permite que você gerencie remotamente as configurações de UEFI usando um perfil de dispositivo dentro do Intune chamado interface de configuração do firmware do dispositivo (DFCI).</span><span class="sxs-lookup"><span data-stu-id="0ec55-195">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="0ec55-196">Se você não definir essa configuração, a capacidade de gerenciar dispositivos qualificados com o DFCI será definida como **pronto**.</span><span class="sxs-lookup"><span data-stu-id="0ec55-196">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="0ec55-197">Para impedir o DFCI, escolha **recusar**.</span><span class="sxs-lookup"><span data-stu-id="0ec55-197">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="0ec55-198">A página de configurações de gerenciamento de UEFI e o uso de DFCI só estão disponíveis no Surface Pro 7, Surface Pro X e Surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="0ec55-198">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="0ec55-199">Para obter mais informações, consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="0ec55-199">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="0ec55-200">Menu UEFI: sair</span><span class="sxs-lookup"><span data-stu-id="0ec55-200">UEFI menu: Exit</span></span> 

<span data-ttu-id="0ec55-201">Use o botão **reiniciar agora** na página **sair** para sair das configurações de UEFI, conforme mostrado na Figura 9.</span><span class="sxs-lookup"><span data-stu-id="0ec55-201">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Sair do UEFI do Surface e reiniciar o dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="0ec55-203">Figura 9.</span><span class="sxs-lookup"><span data-stu-id="0ec55-203">Figure 9.</span></span> <span data-ttu-id="0ec55-204">Clique em Reiniciar Agora para sair do UEFI do Surface e reiniciar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="0ec55-204">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="0ec55-205">Telas de inicialização UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-205">Surface UEFI boot screens</span></span>

<span data-ttu-id="0ec55-206">Quando você atualiza o firmware do dispositivo Surface, usando o Windows Update ou instalação manual, as atualizações não são aplicadas imediatamente para o dispositivo, só durante o próximo ciclo de reinicialização.</span><span class="sxs-lookup"><span data-stu-id="0ec55-206">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="0ec55-207">Você pode saber mais sobre o processo de atualização do firmware do Surface no [Gerenciar atualizações de driver e firmware do Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="0ec55-207">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="0ec55-208">O progresso da atualização do firmware é exibido em uma tela com barras de progresso de cores diferentes para indicar o firmware para cada componente.</span><span class="sxs-lookup"><span data-stu-id="0ec55-208">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="0ec55-209">A barra de progresso de cada componente é mostrada nos números de 9 a 18.</span><span class="sxs-lookup"><span data-stu-id="0ec55-209">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Atualização de firmware UEFI Surface com barra de progresso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="0ec55-211">Figura 10.</span><span class="sxs-lookup"><span data-stu-id="0ec55-211">Figure 10.</span></span> <span data-ttu-id="0ec55-212">A atualização do firmware UEFI do Surface exibe uma barra de progresso azul</span><span class="sxs-lookup"><span data-stu-id="0ec55-212">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Firmware de controlador incorporado do sistema com a barra de progresso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="0ec55-214">Figura 11.</span><span class="sxs-lookup"><span data-stu-id="0ec55-214">Figure 11.</span></span> <span data-ttu-id="0ec55-215">A atualização de firmware de controlador incorporado no sistema exibe uma barra de progresso verde</span><span class="sxs-lookup"><span data-stu-id="0ec55-215">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Atualização do firmware de SAM Controller com barra de progresso laranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="0ec55-217">Figura 12.</span><span class="sxs-lookup"><span data-stu-id="0ec55-217">Figure 12.</span></span> <span data-ttu-id="0ec55-218">A atualização do firmware de SAM Controller exibe uma barra de progresso laranja</span><span class="sxs-lookup"><span data-stu-id="0ec55-218">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Firmware do Intel Management Engine com barra de progresso vermelho](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="0ec55-220">Figura 13.</span><span class="sxs-lookup"><span data-stu-id="0ec55-220">Figure 13.</span></span> <span data-ttu-id="0ec55-221">A atualização de firmware da Intel Management Engine exibe uma barra de progresso vermelho</span><span class="sxs-lookup"><span data-stu-id="0ec55-221">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Toque Surface firmware com barra de progresso cinza](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="0ec55-223">Figura 14.</span><span class="sxs-lookup"><span data-stu-id="0ec55-223">Figure 14.</span></span> <span data-ttu-id="0ec55-224">A atualização de firmware do Surface toque exibe uma barra de progresso cinza</span><span class="sxs-lookup"><span data-stu-id="0ec55-224">The Surface touch firmware update displays a gray progress bar</span></span>*

![Firmware do Surface KIP com barra de progresso verde claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="0ec55-226">Figura 15.</span><span class="sxs-lookup"><span data-stu-id="0ec55-226">Figure 15.</span></span> <span data-ttu-id="0ec55-227">A atualização do firmware do Surface KIP exibe uma barra de progresso verde claro</span><span class="sxs-lookup"><span data-stu-id="0ec55-227">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Firmware do Surface ISH com barra de progresso rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="0ec55-229">Figura 16 a atualização do firmware do Surface ISH exibe uma barra de progresso rosa clara</span><span class="sxs-lookup"><span data-stu-id="0ec55-229">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Firmware do Surface trackpad com barra de progresso cinza](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="0ec55-231">Figura 17.</span><span class="sxs-lookup"><span data-stu-id="0ec55-231">Figure 17.</span></span> <span data-ttu-id="0ec55-232">A atualização do firmware do Surface trackpad exibe uma barra de progresso rosa</span><span class="sxs-lookup"><span data-stu-id="0ec55-232">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Firmware do Surface TCON com barra de progresso cinza claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="0ec55-234">Figura 18.</span><span class="sxs-lookup"><span data-stu-id="0ec55-234">Figure 18.</span></span> <span data-ttu-id="0ec55-235">A atualização do firmware do Surface TCON exibe uma barra de progresso cinza claro</span><span class="sxs-lookup"><span data-stu-id="0ec55-235">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Firmware de Surface TPM com barra de progresso roxo claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="0ec55-237">Figura 19.</span><span class="sxs-lookup"><span data-stu-id="0ec55-237">Figure 19.</span></span> <span data-ttu-id="0ec55-238">A atualização do firmware de Surface TPM exibe uma barra de progresso roxa</span><span class="sxs-lookup"><span data-stu-id="0ec55-238">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="0ec55-239">Uma mensagem de aviso adicional que indica que a inicialização segura está desabilitada é exibida, conforme mostrado na Figura 19.</span><span class="sxs-lookup"><span data-stu-id="0ec55-239">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Tela de inicialização do Surface que indica que a inicialização segura foi desabilitada](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="0ec55-241">Figura 20.</span><span class="sxs-lookup"><span data-stu-id="0ec55-241">Figure 20.</span></span> <span data-ttu-id="0ec55-242">Tela de inicialização do Surface que indica que a inicialização segura foi desativada nas configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-242">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="0ec55-243">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0ec55-243">Related topics</span></span>

- [<span data-ttu-id="0ec55-244">Gerenciamento pelo Intune das configurações de UEFI do Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-244">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="0ec55-245">Modo de gerenciamento empresarial do Surface</span><span class="sxs-lookup"><span data-stu-id="0ec55-245">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
