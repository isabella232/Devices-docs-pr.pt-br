---
title: Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2
description: Este artigo descreve o processo de migração da equipe do Windows 10 no Surface Hub 2 para o Windows 10 pro ou o Windows 10 Enterprise.
keywords: Área de trabalho do Surface Hub, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/11/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 44e7ca08ca4b8c077d430cba2a8cb4b674b68631
ms.sourcegitcommit: ae0dae16e0b7bb9c906de78095634c3070a58c61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/11/2020
ms.locfileid: "11013431"
---
# <span data-ttu-id="fdaf1-104">Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

## <span data-ttu-id="fdaf1-105">Introdução</span><span class="sxs-lookup"><span data-stu-id="fdaf1-105">Introduction</span></span>

<span data-ttu-id="fdaf1-106">O Surface Hub 2S vem pré-instalado com o Windows 10 Team, uma edição personalizada do Windows 10 desenvolvida para facilitar a colaboração em ambientes de sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-106">Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments.</span></span> <span data-ttu-id="fdaf1-107">Agora você tem a opção de executar o Windows 10 pro ou Enterprise para usar o Surface Hub 2S da mesma forma que qualquer outro computador.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="fdaf1-108">Ao contrário de uma atualização ou migração típica, esse processo requer que você siga um procedimento prescritiva, conforme descrito nesta página.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page.</span></span> <span data-ttu-id="fdaf1-109">Examine os [componentes da solução](#solution-components) e a [migração e o fluxo de trabalho de instalação](#migration-and-installation-workflow-summary) antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before proceeding.</span></span>

<span data-ttu-id="fdaf1-110">Você inicia a migração da equipe do Windows 10 usando um computador separado e uma ferramenta para download-- **Surface configurador UEFI** --para criar um pacote contendo uma nova configuração de UEFI que você aplica ao Surface Hub 2s.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-110">You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.</span></span>  <span data-ttu-id="fdaf1-111">O configurador UEFI do Surface funciona como uma interface no modo de gerenciamento do Surface Enterprise (SEMM), projetado para facilitar o gerenciamento centralizado das configurações de firmware em dispositivos de superfície em um ambiente corporativo.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-111">Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="fdaf1-112">Para saber mais sobre o SEMM, confira [documentação do modo de gerenciamento do Surface Enterprise da Microsoft](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-112">To learn more about SEMM, see [Microsoft Surface Enterprise Management Mode documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="fdaf1-113">Componentes da solução</span><span class="sxs-lookup"><span data-stu-id="fdaf1-113">Solution Components</span></span>

- <span data-ttu-id="fdaf1-114">Dispositivo Surface Hub 2S executando o sistema operacional de equipe do Windows 10</span><span class="sxs-lookup"><span data-stu-id="fdaf1-114">Surface Hub 2S device running Windows 10 Team operating system</span></span>
- <span data-ttu-id="fdaf1-115">Dispositivo separado executando o Windows 10</span><span class="sxs-lookup"><span data-stu-id="fdaf1-115">Separate device running Windows 10</span></span>
- <span data-ttu-id="fdaf1-116">Ferramenta configurador UEFI da Surface</span><span class="sxs-lookup"><span data-stu-id="fdaf1-116">Surface UEFI Configurator tool</span></span>
- <span data-ttu-id="fdaf1-117">Imagem do Windows 10 pro ou Enterprise OS, versão 1903 ou posterior</span><span class="sxs-lookup"><span data-stu-id="fdaf1-117">Windows 10 Pro or Enterprise OS image, version 1903 or greater</span></span>
- <span data-ttu-id="fdaf1-118">Duas unidades USB com 16 GB de armazenamento, formato FAT32</span><span class="sxs-lookup"><span data-stu-id="fdaf1-118">Two USB drives with 16GB of storage, FAT32 format</span></span>
- <span data-ttu-id="fdaf1-119">Drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2, Windows Installer. Arquivo MSI</span><span class="sxs-lookup"><span data-stu-id="fdaf1-119">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2, Windows Installer .MSI file</span></span>
- <span data-ttu-id="fdaf1-120">Conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="fdaf1-120">Internet connection</span></span>
- <span data-ttu-id="fdaf1-121">Solução de imagem (opcional)</span><span class="sxs-lookup"><span data-stu-id="fdaf1-121">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="fdaf1-122">Resumo do fluxo de trabalho de migração e instalação</span><span class="sxs-lookup"><span data-stu-id="fdaf1-122">Migration and installation workflow summary</span></span>

| <span data-ttu-id="fdaf1-123">Etapa</span><span class="sxs-lookup"><span data-stu-id="fdaf1-123">Step</span></span>  | <span data-ttu-id="fdaf1-124">Ação</span><span class="sxs-lookup"><span data-stu-id="fdaf1-124">Action</span></span>                                                                                                 | <span data-ttu-id="fdaf1-125">Resumo</span><span class="sxs-lookup"><span data-stu-id="fdaf1-125">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="fdaf1-126">um</span><span class="sxs-lookup"><span data-stu-id="fdaf1-126">1</span></span> | [<span data-ttu-id="fdaf1-127">Verifique se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos</span><span class="sxs-lookup"><span data-stu-id="fdaf1-127">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="fdaf1-128">Certifique-se de que a versão UEFI seja 694.2938.768.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-128">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="fdaf1-129">2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-129">2</span></span> | [<span data-ttu-id="fdaf1-130">Baixar os drivers e o firmware da Surface configuradora do Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-130">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="fdaf1-131">Baixe o [configurador UEFI da Surface](https://www.microsoft.com/download/details.aspx?id=46703) do Surface Tools para ele e instale-o em um computador separado.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-131">Download [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT and install it on a separate PC.</span></span> <span data-ttu-id="fdaf1-132">Baixe [drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. MSI](https://www.microsoft.com/download/details.aspx?id=101974) e salve o arquivo para usá-lo para uso na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-132">Download [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5.</span></span> |
| <span data-ttu-id="fdaf1-133">3D</span><span class="sxs-lookup"><span data-stu-id="fdaf1-133">3</span></span> | [<span data-ttu-id="fdaf1-134">Preparar certificado SEMM</span><span class="sxs-lookup"><span data-stu-id="fdaf1-134">Prepare SEMM certificate</span></span>](#prepare-semm-certificate)                                                                          | <span data-ttu-id="fdaf1-135">Prepare o certificado obrigatório para executar o configurador UEFI de Surface ou use seu certificado atual.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-135">Prepare required certificate for running Surface UEFI Configurator or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="fdaf1-136">4</span><span class="sxs-lookup"><span data-stu-id="fdaf1-136">4</span></span> | [<span data-ttu-id="fdaf1-137">Criar pacote SEMM</span><span class="sxs-lookup"><span data-stu-id="fdaf1-137">Create SEMM package</span></span>](#create-semm-package)                                                                               | <span data-ttu-id="fdaf1-138">Inicie o configurador UEFI da Surface para criar um pacote SEMM em uma unidade USB que conterá os arquivos de configuração necessários para aplicar no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-138">Launch Surface UEFI Configurator to create a SEMM package on a USB drive which will contain the required configuration files to apply on Surface Hub 2S.</span></span> <span data-ttu-id="fdaf1-139">Copie esses arquivos de pacote SEMM para uma pasta em seu computador.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-139">Copy these SEMM package  files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="fdaf1-140">5</span><span class="sxs-lookup"><span data-stu-id="fdaf1-140">5</span></span> | [<span data-ttu-id="fdaf1-141">Preparar a unidade flash USB contendo a imagem do Windows 10, o pacote SEMM e os drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-141">Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="fdaf1-142">Crie uma única unidade USB (chamada **BOOTME** neste exemplo) contendo uma imagem do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-142">Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image.</span></span> <span data-ttu-id="fdaf1-143">Adicione seus drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2 (etapa 2) e SEMM arquivos de pacote (etapa 4) à unidade **BOOTME** .</span><span class="sxs-lookup"><span data-stu-id="fdaf1-143">Add your Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="fdaf1-144">5</span><span class="sxs-lookup"><span data-stu-id="fdaf1-144">6</span></span> | [<span data-ttu-id="fdaf1-145">Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="fdaf1-145">Update UEFI on Surface Hub 2S to enable OS migration</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="fdaf1-146">Use a unidade **BOOTME** para inicializar o Surface Hub 2s ao menu UEFI e instalar o pacote Semm.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-146">Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.</span></span>|
| <span data-ttu-id="fdaf1-147">7</span><span class="sxs-lookup"><span data-stu-id="fdaf1-147">7</span></span> | [<span data-ttu-id="fdaf1-148">Instalar o Windows 10 pro ou Enterprise versão 1903 ou posterior</span><span class="sxs-lookup"><span data-stu-id="fdaf1-148">Install Windows 10 Pro or Enterprise version 1903 or later</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="fdaf1-149">Use a unidade **BOOTME** para instalar o **Windows 10 pro ou Enterprise** versão 1903 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-149">Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="fdaf1-150">08</span><span class="sxs-lookup"><span data-stu-id="fdaf1-150">8</span></span> | [<span data-ttu-id="fdaf1-151">Instalar drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-151">Install Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="fdaf1-152">Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale [drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. Arquivo MSI](https://www.microsoft.com/download/details.aspx?id=101974)</span><span class="sxs-lookup"><span data-stu-id="fdaf1-152">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974)</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="fdaf1-153">222</span><span class="sxs-lookup"><span data-stu-id="fdaf1-153">9</span></span> | [<span data-ttu-id="fdaf1-154">Configurar completamente o Surface Hub 2S como um dispositivo de produtividade pessoal</span><span class="sxs-lookup"><span data-stu-id="fdaf1-154">Fully configure Surface Hub 2S as a personal productivity device</span></span>](#next-steps)                                        |  <span data-ttu-id="fdaf1-155">Habilite o conjunto de aplicativos e configurações recomendadas para otimizar o uso do Surface Hub 2S como um dispositivo de produtividade pessoal.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-155">Enable the set of recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="fdaf1-156">Verifique se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos</span><span class="sxs-lookup"><span data-stu-id="fdaf1-156">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="fdaf1-157">A versão UEFI mínima exigida antes da migração do Surface Hub da equipe do Windows 10 para a área de trabalho do Windows 10 é **694.2938.768.0**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-157">The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.</span></span>
 
**<span data-ttu-id="fdaf1-158">Para verificar a versão UEFI atual em seu sistema:</span><span class="sxs-lookup"><span data-stu-id="fdaf1-158">To verify the current UEFI version on your system:</span></span>**

1. <span data-ttu-id="fdaf1-159">Na tela inicial do Surface Hub 2s, selecione **Iniciar** e abra a **SurfaceApp** (toda a superfície de**aplicativos**  >  **Surface**).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-159">On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="fdaf1-160">Selecione **sua superfície** para exibir informações sobre o Surface Hub, incluindo a versão atual do UEFI no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-160">Select **Your Surface** to display information about the Surface Hub, including the current version of the UEFI on the device.</span></span> <span data-ttu-id="fdaf1-161">Se a versão UEFI for **694.2938.768.0** ou posterior, conforme mostrado abaixo, a UEFI estará qualificada para que você crie o pacote Semm para habilitar a migração do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-161">If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.</span></span>

    ![Abrir o aplicativo Surface & selecionar sua superfície](images/shm-fig1.png)
 
3. <span data-ttu-id="fdaf1-163">Se a versão UEFI for anterior à versão **694.2938.768.0**, será necessário obter uma versão atual usando o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-163">If the UEFI version is earlier than version **694.2938.768.0**, you will need to obtain a current version using Windows Update.</span></span>

**<span data-ttu-id="fdaf1-164">Para atualizar a UEFI a partir do Windows Update:</span><span class="sxs-lookup"><span data-stu-id="fdaf1-164">To update UEFI from Windows Update:</span></span>**
1. <span data-ttu-id="fdaf1-165">No Surface Hub 2s, entre como **administrador**, vá para todas as configurações de **aplicativos**  >  **Settings** >  **atualização e segurança**  >  do**Windows Update** e instale todas as atualizações e, em seguida, reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-165">On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings**> **Update and Security** > **Windows Update** and install all updates, then restart the device.</span></span> <span data-ttu-id="fdaf1-166">Verifique a versão UEFI usando o aplicativo Surface.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-166">Verify the UEFI version using the Surface App.</span></span> <span data-ttu-id="fdaf1-167">Observação: se você não souber seu nome de usuário ou senha de administrador, será necessário redefinir o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-167">Note: If you do not know your username or admin password, you will need to reset the device.</span></span> <span data-ttu-id="fdaf1-168">Para saber mais, consulte [redefinir e recuperar para Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-168">To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

2. <span data-ttu-id="fdaf1-169">Repita essas etapas até que a versão de UEFI seja **694.2938.768.0** ou posterior.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-169">Repeat these steps until the UEFI version is **694.2938.768.0** or later.</span></span>

3. <span data-ttu-id="fdaf1-170">Se você ainda não vir o UEFI atualizado após várias tentativas, verifique o **histórico de atualização** e procure por quaisquer instâncias de instalações de firmware com falha.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-170">If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="fdaf1-171">Talvez seja necessário redefinir o dispositivo (atualização de**configurações**  >  **&**  >  **dispositivo de redefinição**de segurança).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-171">You may need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="fdaf1-172">Baixar os drivers e o firmware da Surface configuradora do Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-172">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="fdaf1-173">Em um computador separado:</span><span class="sxs-lookup"><span data-stu-id="fdaf1-173">On a separate PC:</span></span>

- <span data-ttu-id="fdaf1-174">Baixe e instale o Microsoft [Surface UEFI configurate](https://www.microsoft.com/download/details.aspx?id=46703) de ferramentas Surface para ele.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-174">Download and install Microsoft [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT.</span></span> <span data-ttu-id="fdaf1-175">O configurador UEFI de Surface não pode ser executado no Surface Hub 2S, enquanto a equipe do Windows 10 está instalada.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-175">Surface UEFI Configurator cannot be run on Surface Hub 2S, while Windows 10 Team is installed.</span></span>

- <span data-ttu-id="fdaf1-176">Baixe [drivers Surface Hub 2 e firmware Windows Installer. Arquivo MSI](https://www.microsoft.com/download/details.aspx?id=101974) a ser aplicado ao instalar o novo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-176">Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.</span></span>

### <span data-ttu-id="fdaf1-177">Preparar certificado SEMM</span><span class="sxs-lookup"><span data-stu-id="fdaf1-177">Prepare SEMM certificate</span></span>

<span data-ttu-id="fdaf1-178">Se esta for a primeira vez que você usa o configurador UEFI da Surface, você precisará preparar um certificado.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-178">If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate.</span></span> <span data-ttu-id="fdaf1-179">Esse certificado garante que depois que um dispositivo é registrado no SEMM, somente pacotes criados com o certificado aprovado podem ser usados para modificar as configurações de UEFI.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-179">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings.</span></span> <span data-ttu-id="fdaf1-180">A forma como você adquire um certificado pode variar dependendo do tamanho ou da complexidade da sua organização:</span><span class="sxs-lookup"><span data-stu-id="fdaf1-180">How you acquire a certificate may vary depending on the size or complexity of your organization:</span></span>

- <span data-ttu-id="fdaf1-181">Geralmente, grandes organizações corporativas mantêm sua própria infraestrutura de certificado para gerar certificados por práticas de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-181">Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.</span></span>

- <span data-ttu-id="fdaf1-182">Empresas de médio porte e outras pessoas podem optar por obter um certificado de provedores de terceiros.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-182">Medium-sized businesses and others may choose to obtain a certificate from third party providers.</span></span> <span data-ttu-id="fdaf1-183">Esta é a opção recomendada para organizações sem conhecimento de ti suficiente ou equipe de segurança de ti dedicada.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-183">This is the recommended option for organizations without sufficient IT expertise or dedicated IT security team.</span></span>

- <span data-ttu-id="fdaf1-184">Você também pode gerar um certificado autoassinado com um script do PowerShell, de acordo com a documentação a seguir: [requisitos de certificado do modo de gerenciamento empresarial Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-184">Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="fdaf1-185">Ou use o PowerShell para criar seu próprio certificado por meio da seguinte documentação: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-185">Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps).</span></span>

<span data-ttu-id="fdaf1-186">O pacote SEMM deve ser protegido com um certificado para verificar a assinatura de arquivos de configuração antes que as configurações de UEFI possam ser aplicadas.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-186">The SEMM package must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="fdaf1-187">Para saber mais, consulte documentação do [modo de gerenciamento da empresa Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode) .</span><span class="sxs-lookup"><span data-stu-id="fdaf1-187">To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
 
### <span data-ttu-id="fdaf1-188">Criar pacote SEMM</span><span class="sxs-lookup"><span data-stu-id="fdaf1-188">Create SEMM package</span></span>

1. <span data-ttu-id="fdaf1-189">Abra o **configurador UEFI da superfície** e selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-189">Open **Surface UEFI Configurator** and select **Start**.</span></span>

   ![Configurador UEFI do Open Surface](images/shm-fig2.png)
   
2. <span data-ttu-id="fdaf1-191">Selecione **Surface Devices** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-191">Select **Surface Devices** and then select **Next**.</span></span>

   ![Selecionar dispositivos de superfície](images/shm-fig3.png)
  
3. <span data-ttu-id="fdaf1-193">Selecione **pacote de configuração**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-193">Select **Configuration Package**.</span></span>

   ![Selecionar pacote de configuração](images/shm-fig4.png)
  
4. <span data-ttu-id="fdaf1-195">Selecione **proteção de certificado**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-195">Select **Certificate Protection**.</span></span>

   ![Selecionar proteção de certificado](images/shm-fig5.png)

5. <span data-ttu-id="fdaf1-197">Você será solicitado a adicionar seu arquivo. pfx de certificado.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-197">You will be prompted to add your certificate .pfx file.</span></span>

   ![Você será solicitado a adicionar seu certificado](images/shm-fig6.png)
   
6. <span data-ttu-id="fdaf1-199">Digite sua **senha de certificado** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-199">Enter your **Certificate password** and select **OK**.</span></span>

   ![Digite sua senha de certificado e selecione OK](images/shm-fig7.png)

7. <span data-ttu-id="fdaf1-201">Selecione **proteção por senha** para adicionar uma senha à UEFI da superfície.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-201">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="fdaf1-202">Esta senha será necessária sempre que você inicializar o UEFI.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-202">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="fdaf1-203">É **altamente recomendável** definir uma senha UEFI que será usada no Surface Hub 2s.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-203">It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.</span></span>

   ![Clique em proteção por senha](images/shm-fig8.png)
   
8. <span data-ttu-id="fdaf1-205">Defina uma **senha UEFI** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-205">Set a **UEFI password** and select **OK**.</span></span>

   ![Digite sua senha UEFI](images/shm-fig9.png)

   > [!IMPORTANT]
   > <span data-ttu-id="fdaf1-207">Anote sua senha.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-207">Make a note of your password.</span></span> <span data-ttu-id="fdaf1-208">Se você esquecer ou perder a senha, não há processo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-208">If you forget or lose your password, there is no recovery process.</span></span> 

9. <span data-ttu-id="fdaf1-209">Selecione **Surface Hub 2s** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-209">Select **Surface Hub 2S** and then select **Next**.</span></span>

   ![Selecionar Surface Hub 2S](images/shm-fig10.png)
   
10. <span data-ttu-id="fdaf1-211">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-211">Select **Next**.</span></span>

    ![Selecione Avançar](images/shm-fig10a.png)

11. <span data-ttu-id="fdaf1-213">Para permitir a instalação do Windows 10 pro ou Enterprise, selecione **EnableOsMigration.**</span><span class="sxs-lookup"><span data-stu-id="fdaf1-213">To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**</span></span>

    ![Selecione habilitar a migração do sistema operacional](images/shm-fig11.png)
    
12. <span data-ttu-id="fdaf1-215">Defina **EnableOSMigration** como **ativado** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-215">Set **EnableOSMigration** to **On** and select **Next**.</span></span>

    ![Definir habilitar migração do sistema operacional como ativado](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="fdaf1-217">Depois de aplicar um pacote SEMM, todas as configurações de UEFI serão exibidas como acinzentadas (bloqueadas) no menu UEFI do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-217">After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device.</span></span> <span data-ttu-id="fdaf1-218">Isso inclui valores padrão para outras configurações, como IPv6 para inicialização PXE.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-218">This includes default values for other settings such as IPv6 for PXE Boot.</span></span> <span data-ttu-id="fdaf1-219">Para modificar as configurações de UEFI, você precisará aplicar outro pacote SEMM ou cancelar o registro do dispositivo do SEMM.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-219">To modify UEFI settings, you will need to apply another SEMM package or unenroll the device from SEMM.</span></span>

#### <span data-ttu-id="fdaf1-220">Salvar pacote SEMM na unidade USB</span><span class="sxs-lookup"><span data-stu-id="fdaf1-220">Save SEMM package to USB drive</span></span>

1. <span data-ttu-id="fdaf1-221">Conecte uma unidade USB ao seu computador.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-221">Connect a USB Drive to your PC.</span></span> <span data-ttu-id="fdaf1-222">Escolha **Hub 2s** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-222">Choose **Hub 2S** and then select **Next**.</span></span>

   ![Selecionar USB](images/shm-fig13.png)
   
2. <span data-ttu-id="fdaf1-224">Selecione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-224">Select **Build**.</span></span>

   ![Selecione criar](images/shm-fig14.png)

3. <span data-ttu-id="fdaf1-226">Capture uma captura de tela desta página e selecione **terminar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-226">Capture a screenshot of this page and then select **End**.</span></span> <span data-ttu-id="fdaf1-227">Seu pacote SEMM agora está pronto e contém o pacote SEMM **DfciUpdate. DFI** e um arquivo de texto com a impressão digital Semm (os dois últimos caracteres da impressão digital do certificado).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-227">Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).</span></span>

   ![Selecione encerrar](images/shm-fig15.png)
   
4. <span data-ttu-id="fdaf1-229">Salve os últimos 2 caracteres da impressão digital do certificado, o que é necessário para ativar o SEMM ao aplicar o pacote no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-229">Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="fdaf1-230">Preparar a unidade flash USB contendo a imagem do Windows 10, o pacote SEMM e os drivers e o firmware do Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-230">Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="fdaf1-231">Você pode instalar uma imagem do Windows 10 pro ou Enterprise (versão 1903 ou posterior) usando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fdaf1-231">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:</span></span>

- <span data-ttu-id="fdaf1-232">Sua solução atual para imagens.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-232">Your current imaging solution.</span></span>

- <span data-ttu-id="fdaf1-233">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) permite que você crie uma imagem inicializável do Windows 10, que pode incluir todas as atualizações atuais do Windows 10, o Office, outros aplicativos de sua escolha, bem como os drivers e o firmware obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-233">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all of the current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware.</span></span> 

- <span data-ttu-id="fdaf1-234">Unidade flash USB com o Windows 10 pro ou a imagem empresarial, seguida  [da instalação de drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-234">USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 

<span data-ttu-id="fdaf1-235">Este procedimento descreve como criar uma unidade flash USB da mídia de instalação e adicionar os arquivos de pacote SEMM e drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. Arquivo MSI.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-235">This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file.</span></span> <span data-ttu-id="fdaf1-236">Se você estiver usando outros métodos de implantação, vá para a seção a seguir: [atualizar a UEFI no Surface Hub 2s para habilitar a migração do sistema operacional](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-236">If you’re using other deployment methods, proceed to the following section: [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="fdaf1-237">Uma vez instalado, você precisará de uma licença válida para o Windows 10 pro ou o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-237">Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise.</span></span>

1. <span data-ttu-id="fdaf1-238">Para criar uma instalação do Windows 10 pro, siga as instruções na página [baixar o Windows 10](https://www.microsoft.com/software-download/windows10) para usar a ferramenta de **criação de mídia** .</span><span class="sxs-lookup"><span data-stu-id="fdaf1-238">To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool.</span></span> <span data-ttu-id="fdaf1-239">Para baixar o Windows 10 Enterprise, vá para o [centro de serviços de licenciamento por volume da Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="fdaf1-239">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="fdaf1-240">Insira uma nova unidade de **armazenamento USB** .</span><span class="sxs-lookup"><span data-stu-id="fdaf1-240">Insert a new **USB storage** drive.</span></span> <span data-ttu-id="fdaf1-241">Inicie a ferramenta de **criação de mídia** , selecione **criar mídia de instalação** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-241">Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.</span></span>

   ![Criar mídia de instalação](images/shm-fig16.png)
   
3. <span data-ttu-id="fdaf1-243">Selecione idioma, Windows 10 e 64 bits (x64) e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-243">Select language, Windows 10, and 64-bit (x64) and then select **Next**.</span></span>

   ![Selecione o idioma, o Windows 10 e o 64 bits & Selecione Avançar](images/shm-fig17.png)
   
4. <span data-ttu-id="fdaf1-245">Selecione **unidade flash USB** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-245">Select **USB flash drive** and select **Next**.</span></span>

   ![Selecione unidade flash USB e selecione avançar](images/shm-fig18.png)
   
5. <span data-ttu-id="fdaf1-247">Quando o download for concluído, selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-247">When the download completes, select **Finish**.</span></span>

   ![Selecionar concluir](images/shm-fig19.png)
   
6. <span data-ttu-id="fdaf1-249">Copie os arquivos de pacote SEMM e drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. MSI para a unidade flash USB (**BOOTME**) que contém a imagem do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="fdaf1-249">Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI to the USB flash drive (**BOOTME**) containing your Windows 10 image:</span></span>

    - <span data-ttu-id="fdaf1-250">DfciUpdate. DFI</span><span class="sxs-lookup"><span data-stu-id="fdaf1-250">DfciUpdate.dfi</span></span>
    - <span data-ttu-id="fdaf1-251">Arquivo de texto com a impressão digital SEMM.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-251">Text file with the SEMM thumbprint.</span></span> <span data-ttu-id="fdaf1-252">(Neste exemplo: SurfaceUEFI_2020Aug25_1058.txt)</span><span class="sxs-lookup"><span data-stu-id="fdaf1-252">(In this example: SurfaceUEFI_2020Aug25_1058.txt)</span></span>
    - <span data-ttu-id="fdaf1-253">Drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span><span class="sxs-lookup"><span data-stu-id="fdaf1-253">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span></span>

### <span data-ttu-id="fdaf1-254">Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="fdaf1-254">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

<span data-ttu-id="fdaf1-255">Use a unidade **BOOTME** para instalar os arquivos de pacote do Semm e atualizar a UEFI, habilitando o Surface Hub para executar o Windows 10 pro ou Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-255">Use your **BOOTME** drive to install the SEMM package files and update the UEFI, enabling Surface Hub to run Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="fdaf1-256">Em seguida, inicialize a partir da unidade **BOOTME** para instalar o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-256">Then boot from the **BOOTME** drive to install Windows 10.</span></span>

1. <span data-ttu-id="fdaf1-257">Insira sua unidade **BOOTME** contendo arquivos de pacote do Semm, drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. MSI e Windows 10 instalam arquivos na porta USB-A no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-257">Insert your **BOOTME** drive containing SEMM package files, Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI, and Windows 10 install files into the USB-A port on Surface Hub 2S.</span></span>  

2. <span data-ttu-id="fdaf1-258">Para inicializar o UEFI:</span><span class="sxs-lookup"><span data-stu-id="fdaf1-258">To boot into UEFI:</span></span>

   1. <span data-ttu-id="fdaf1-259">Primeira desligamento (desligar) seu Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-259">First power off (shutdown) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="fdaf1-260">Pressione e mantenha pressionado o **volume +** e, em seguida, pressione e libere o botão de **energia** .</span><span class="sxs-lookup"><span data-stu-id="fdaf1-260">Press and hold **Volume +** and then press and release the **Power** button.</span></span>
   1. <span data-ttu-id="fdaf1-261">Mantenha a retenção do **volume +** até que o menu UEFI seja exibido.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-261">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![Mantenha a retenção do volume + até que o menu UEFI seja exibido](images/shm-fig20.png)
      
3. <span data-ttu-id="fdaf1-263">Quando o dispositivo for reiniciado, insira a senha UEFI que você criou anteriormente, se aplicável (altamente recomendado).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-263">When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).</span></span>

   ![Quando o dispositivo for reiniciado, insira seu paassword UEFI](images/shm-fig22.png)
   
4. <span data-ttu-id="fdaf1-265">No menu UEFI, selecione **Management**  >  **instalação de gerenciamento do USB**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-265">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![Selecionar gerenciamento & instalar a partir do USB](images/shm-fig21.png)
   
5. <span data-ttu-id="fdaf1-267">Selecione **reiniciar agora**, como mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-267">Select **Restart now**, as shown below.</span></span> <span data-ttu-id="fdaf1-268">O dispositivo será reiniciado e exibirá o logotipo branco de 4 quadrados no meio da tela e ele será desligado.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-268">The device will reboot and display the white 4-square logo in the middle of screen and then it will shut down.</span></span>

   ![Selecione reiniciar agora](images/shm-fig25.png)
   
6. <span data-ttu-id="fdaf1-270">Pressione e solte o botão de energia, uma tela vermelha será exibida solicitando que você ative o modo de gerenciamento do Surface Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-270">Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="fdaf1-271">Insira sua **impressão digital**de dois caracteres, sua **senha de configurações de UEFI** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-271">Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.</span></span>

   ![Digite a impressão digital do certificado de 2 caracteres](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="fdaf1-273">Depois de ativar o SEMM em seu dispositivo, a nova configuração de **EnableOSMigration** de UEFI será aplicada.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-273">Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="fdaf1-274">Você não poderá mais acessar a equipe do Windows 10 e deve passar para a próxima etapa e instalar o Windows 10 pro ou o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-274">You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

8. <span data-ttu-id="fdaf1-275">O dispositivo será reinicializado, exibirá o logotipo branco de quatro quadrados no meio da tela e, em seguida, novamente será desligado</span><span class="sxs-lookup"><span data-stu-id="fdaf1-275">The device will reboot, display the white 4-square logo in the middle of the screen, and then again it will shut down</span></span>

### <span data-ttu-id="fdaf1-276">Instalar o Windows 10 pro ou Enterprise</span><span class="sxs-lookup"><span data-stu-id="fdaf1-276">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="fdaf1-277">Se a unidade Windows 10 pro ou Enterprise inicializável ainda não estiver na porta do Surface Hub 2 USB-A, insira-a agora e, em seguida, pressione e libere o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-277">If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.</span></span>

2. <span data-ttu-id="fdaf1-278">O dispositivo será iniciado, você verá o branco 4 quadrado no meio da tela e verá um círculo girando abaixo do logotipo branco de quatro quadrados.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-278">The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.</span></span>

3. <span data-ttu-id="fdaf1-279">Se o dispositivo não inicializar automaticamente na unidade USB, desligue o dispositivo (desconecte o cabo de alimentação e conecte-o novamente).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-279">If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in).</span></span> <span data-ttu-id="fdaf1-280">Após conectar o cabo de alimentação novamente, o dispositivo deve ser inicializado após alguns segundos para o logotipo branco de 4 quadrados no meio da tela, ou você pode pressionar e liberar o botão de energia para ligar o dispositivo novamente.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-280">After plugging the power cord back in, the device should boot after a few seconds to the white 4-square logo in the middle of screen, or you can press and release the power button to turn the device back on.</span></span> <span data-ttu-id="fdaf1-281">Logo após ver o logotipo de quatro quadrados no meio da tela, pressione e mantenha pressionado o botão para baixo volume até ver o círculo girando abaixo do logotipo branco de quatro quadrados.</span><span class="sxs-lookup"><span data-stu-id="fdaf1-281">Immediately after you see the 4-square logo in the middle of the screen, press and hold the volume down button until you see the spinning circle below the white four-square logo.</span></span>
 
   ![Inicializar no Windows 10 a partir do USB](images/shm-fig26.png)
   
4. <span data-ttu-id="fdaf1-283">Quando a instalação do OOBE (configuração inicial da caixa) for iniciada, siga as instruções para instalar o Windows 10 pro ou Enterprise (versão 1903 ou posterior).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-283">When the out of box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="fdaf1-284">Instalar drivers e firmware do Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="fdaf1-284">Install Surface Hub 2 drivers and firmware</span></span>

 - <span data-ttu-id="fdaf1-285">Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale [drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-285">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
### <span data-ttu-id="fdaf1-286">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fdaf1-286">Next steps</span></span>

<span data-ttu-id="fdaf1-287">Para configurar completamente o Surface Hub 2S como um dispositivo de produtividade pessoal, consulte [Configurar o Windows 10 pro ou Enterprise no Surface Hub 2](surface-hub-2-post-install.md).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-287">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="fdaf1-288">Se seguir as etapas descritas neste documento não tiver êxito em migrar seu dispositivo para o Windows 10 pro ou Enterprise para Surface Hub 2, entre em contato com o [suporte do Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="fdaf1-288">If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

### <span data-ttu-id="fdaf1-289">Retornando à equipe do Windows 10</span><span class="sxs-lookup"><span data-stu-id="fdaf1-289">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="fdaf1-290">Se você quiser restaurar seu dispositivo para a equipe do Windows 10, consulte [redefinir e recuperar para Surface Hub 2s](surface-hub-2s-recover-reset.md)</span><span class="sxs-lookup"><span data-stu-id="fdaf1-290">If you would Like to restore your device to Windows 10 Team, refer to [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md)</span></span>

