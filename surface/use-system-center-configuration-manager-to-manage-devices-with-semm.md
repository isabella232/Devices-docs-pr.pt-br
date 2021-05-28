---
title: Usar o Gerenciador de configuração do Microsoft Endpoint para gerenciar dispositivos com o SEMM (Surface)
description: Saiba como gerenciar o modo de gerenciamento do Microsoft Surface Enterprise (SEMM) com o Endpoint Configuration Manager.
keywords: registrar, atualizar, scripts, configurações
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 2d31f520d8c4da54f47b2b89b58b43e2cb983f1a
ms.sourcegitcommit: 7f5b97275fe301ef700f9c77954a1054e2e8d046
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145612"
---
# <span data-ttu-id="bfcdf-104">Usar o Microsoft Endpoint Configuration Manager para gerenciar dispositivos com SEMM</span><span class="sxs-lookup"><span data-stu-id="bfcdf-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="bfcdf-105">O recurso SEMM (Microsoft Surface Enterprise Management Mode) de dispositivos da Surface UEFI permite que os administradores gerenciem e ajudem a proteger a configuração das configurações de controle de superfície.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="bfcdf-106">Para a maioria das organizações, esse processo é realizado criando pacotes do Windows Installer (. msi) com a ferramenta Microsoft Surface UEFI Configuration.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="bfcdf-107">Esses pacotes são, em seguida, executados ou implantados nos dispositivos de superfície do cliente para registrar os dispositivos no SEMM e atualizar a configuração de configurações de UEFI da superfície.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="bfcdf-108">Para organizações com o Gerenciador de configuração do Microsoft EndPoint, há uma alternativa em usar o processo Microsoft Surface UEFI Configurator. msi para implantar e administrar o SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="bfcdf-109">O Microsoft Surface UEFI Manager é um instalador leve que torna assemblies necessários para o gerenciamento do SEMM disponível em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="bfcdf-110">Ao instalar esses assemblies com o Microsoft Surface UEFI Manager em um cliente gerenciado, o SEMM pode ser administrado pelo Configuration Manager com scripts do PowerShell, implantados como aplicativos.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="bfcdf-111">Com esse processo, o gerenciamento de SEMM é executado no Configuration Manager, que elimina a necessidade da ferramenta Microsoft Surface UEFI configuradora externa.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="bfcdf-112">Embora o processo descrito neste artigo possa funcionar com versões anteriores do Endpoint Configuration Manager ou com outras soluções de gerenciamento de terceiros, o gerenciamento de SEMM com o Microsoft Surface UEFI Manager e o PowerShell só tem suporte com o Branch atual do Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="bfcdf-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bfcdf-113">Prerequisites</span></span>

<span data-ttu-id="bfcdf-114">Antes de começar o processo descrito neste artigo, familiarize-se com as seguintes tecnologias e ferramentas:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="bfcdf-115">UEFI da superfície</span><span class="sxs-lookup"><span data-stu-id="bfcdf-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="bfcdf-116">Surface Enterprise Management Mode (SEMM)</span><span class="sxs-lookup"><span data-stu-id="bfcdf-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="bfcdf-117">Script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfcdf-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="bfcdf-118">Implantação de aplicativo do System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bfcdf-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="bfcdf-119">Gerenciamento de certificados</span><span class="sxs-lookup"><span data-stu-id="bfcdf-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="bfcdf-120">Também será necessário acessar o certificado que você pretende usar para proteger o SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="bfcdf-121">Para obter detalhes sobre os requisitos para esse certificado, consulte [requisitos de certificado do modo de gerenciamento da empresa Surface](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="bfcdf-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="bfcdf-122">É muito importante que esse certificado seja mantido em um local seguro e backup adequado.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="bfcdf-123">Se esse certificado ficar perdido ou não ser usado, não será possível redefinir o recurso de UEFI, alterar as configurações de UEFI de superfície gerenciada ou remover SEMM de um dispositivo de superfície inscrito.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="bfcdf-124">Baixar o Microsoft Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="bfcdf-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="bfcdf-125">O gerenciamento de SEMM com o Configuration Manager requer a instalação do Microsoft Surface UEFI Manager em cada dispositivo de superfície de cliente.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="bfcdf-126">Você pode baixar o Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) na página [Surface Tools para it](https://www.microsoft.com/download/details.aspx?id=46703) no centro de download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="bfcdf-127">Baixar scripts SEMM para o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bfcdf-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="bfcdf-128">Após o Microsoft Surface UEFI Manager ser instalado no dispositivo de superfície do cliente, o SEMM é implantado e gerenciado com scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="bfcdf-129">Você pode baixar exemplos dos [scripts de gerenciamento do Semm](https://www.microsoft.com/download/details.aspx?id=46703) a partir do centro de download.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <a name="deploy-microsoft-surface-uefi-manager"></a><span data-ttu-id="bfcdf-130">Implantar o Microsoft Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="bfcdf-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="bfcdf-131">A implantação do Microsoft Surface UEFI Manager é uma implantação de aplicativo típica.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="bfcdf-132">O arquivo do instalador do Microsoft Surface UEFI Manager é um arquivo padrão do Windows Installer que você pode instalar com a [opção silencioso padrão](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span><span class="sxs-lookup"><span data-stu-id="bfcdf-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="bfcdf-133">O comando para instalar o Microsoft Surface UEFI Manager é o seguinte.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="bfcdf-134">O comando para desinstalar o Microsoft Surface UEFI Manager é o seguinte.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="bfcdf-135">Para criar um novo aplicativo e implantá-lo em uma coleção que contenha seus dispositivos de superfície, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="bfcdf-136">Abra o console do Configuration Manager na tela **inicial** ou no menu **Iniciar** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="bfcdf-137">Selecione **biblioteca de software** no canto inferior esquerdo da janela.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="bfcdf-138">Expanda o nó **Gerenciamento de aplicativos** da biblioteca de software e selecione **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="bfcdf-139">Selecione o botão **criar aplicativo** na guia **página inicial** , na parte superior da janela.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="bfcdf-140">Isso inicia o assistente para criação de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="bfcdf-141">O assistente criar aplicativo apresenta uma série de etapas:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="bfcdf-142">**Geral** – a opção **detectar automaticamente informações sobre este aplicativo a partir de arquivos de instalação** está marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="bfcdf-143">No campo **tipo** , o **Windows Installer (arquivo. msi)** também é selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="bfcdf-144">Selecione **procurar** para navegar e selecionar **SurfaceUEFIManagerSetup.msi**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="bfcdf-145">O local do SurfaceUEFIManagerSetup.msi deve estar em um compartilhamento de rede e localizado em uma pasta que não contenha outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="bfcdf-146">Não é possível usar um local de arquivo local.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="bfcdf-147">**Importar informações** – o assistente de criação de aplicativos analisará o arquivo. msi e lerá o **nome do aplicativo** e o **código do produto**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="bfcdf-148">SurfaceUEFIManagerSetup.msi deve ser listado como o único arquivo sob os **arquivos de conteúdo**de linha, conforme mostrado na Figura 1.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="bfcdf-149">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-149">Select **Next** to proceed.</span></span>

      ![As informações da configuração do Surface Manager do Surface são automaticamente analisadas](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="bfcdf-151">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-151">Figure 1.</span></span> <span data-ttu-id="bfcdf-152">As informações da configuração do Microsoft Surface UEFI Manager são automaticamente analisadas</span><span class="sxs-lookup"><span data-stu-id="bfcdf-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="bfcdf-153">**Informações gerais** – você pode modificar o nome do aplicativo e informações sobre o Publisher e a versão ou adicionar comentários nesta página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="bfcdf-154">O comando de instalação do Microsoft Surface UEFI Manager é exibido no campo programa de instalação.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="bfcdf-155">O comportamento de instalação padrão da instalação do sistema permitirá que o Microsoft Surface UEFI Manager instale os assemblies necessários para o SEMM mesmo se um usuário não estiver conectado ao dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="bfcdf-156">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="bfcdf-157">**Resumo** – as informações analisadas na etapa informações de **importação** e suas seleções da etapa **informações gerais** são exibidas nesta página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="bfcdf-158">Selecione **Avançar** para confirmar suas seleções e criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="bfcdf-159">**Progresso** – exibe uma barra de progresso e o status conforme o aplicativo é importado e adicionado à biblioteca de software.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="bfcdf-160">**Conclusão** – a confirmação da criação bem-sucedida do aplicativo é exibida quando o processo de criação do aplicativo é concluído.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="bfcdf-161">Selecione **fechar** para concluir o assistente de criação de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="bfcdf-162">Após a criação do aplicativo no Configuration Manager, você pode distribuí-lo aos seus pontos de distribuição e implantá-lo nas coleções, incluindo os dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="bfcdf-163">Este aplicativo não instalará ou habilitará o SEMM no dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="bfcdf-164">Ele somente fornece os assemblies necessários para que o SEMM seja habilitado usando o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="bfcdf-165">Se você não quiser instalar os assemblies do Gerenciador de Microsoft Surface UEFI em dispositivos que não serão gerenciados com o SEMM, é possível configurar o Gerenciador da Microsoft Surface UEFI como uma dependência dos scripts do Gerenciador de configuração do SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="bfcdf-166">Esse cenário é abordado na seção [implantar scripts do Gerenciador de configuração Semm](#deploy-semm-configuration-manager-scripts) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a><span data-ttu-id="bfcdf-167">Criar ou modificar os scripts do Gerenciador de configuração do SEMM</span><span class="sxs-lookup"><span data-stu-id="bfcdf-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="bfcdf-168">Depois que os assemblies necessários tiverem sido instalados nos dispositivos, o processo de registrar os dispositivos no SEMM e configurar o Surface UEFI será feito com os scripts do PowerShell e implantados como uma aplicação de script com o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="bfcdf-169">Esses scripts podem ser modificados de acordo com as necessidades da sua organização e do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="bfcdf-170">Por exemplo, você pode criar várias configurações para dispositivos de superfície gerenciados em diferentes departamentos ou funções.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="bfcdf-171">Você pode baixar exemplos dos scripts do SEMM e do Configuration Manager no link na seção [pré-requisitos](#prerequisites) no início deste artigo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="bfcdf-172">Há dois scripts principais necessários para realizar uma implantação do SEMM com o Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="bfcdf-173">**ConfigureSEMM.ps1** – Use este script para criar pacotes de configuração para seus dispositivos Surface com as configurações de configuração de superfície desejadas para aplicar as configurações especificadas a um dispositivo Surface, para registrar o dispositivo no Semm e para definir uma chave do Registro usada para identificar o registro do dispositivo no Semm.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="bfcdf-174">**ResetSEMM.ps1** – Use este script para redefinir o Semm em um dispositivo Surface, que o cadastra do Semm e remove o controle sobre as configurações de controle de superfície.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="bfcdf-175">Os scripts de exemplo incluem exemplos de como definir as configurações da superfície UEFI e como controlar as permissões para essas configurações.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="bfcdf-176">Essas configurações podem ser modificadas para garantir a UEFI de segurança da superfície e definir configurações da superfície UEFI de acordo com as necessidades do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="bfcdf-177">As seções a seguir deste artigo explicam o ConfigureSEMM.ps1 script e exploram as modificações que você precisa fazer ao script para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="bfcdf-178">Os scripts do Gerenciador de configuração do SEMM e o arquivo de certificado SEMM exportado (. pfx) devem ser colocados na mesma pasta sem outros arquivos antes de serem adicionados ao Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <a name="specify-certificate-and-package-names"></a><span data-ttu-id="bfcdf-179">Especificar nomes de certificado e pacote</span><span class="sxs-lookup"><span data-stu-id="bfcdf-179">Specify certificate and package names</span></span>

<span data-ttu-id="bfcdf-180">A primeira região do script que você precisa modificar é a parte que especifica e carrega o certificado SEMM, e também indica a versão SurfaceUEFIManager e os nomes do pacote de configuração do SEMM e do pacote de redefinição do SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="bfcdf-181">O nome do certificado e a versão do SurfaceUEFIManager são especificados nas linhas de 56 a 73 no script ConfigureSEMM.ps1.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="bfcdf-182">Substitua o valor **FabrikamSEMMSample. pfx** da variável **$certName** com o nome do seu arquivo de certificado Semm na linha 58.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="bfcdf-183">O script criará um diretório de trabalho (chamado config) na pasta em que os seus scripts estão localizados e, em seguida, copiará o arquivo de certificado para este diretório de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="bfcdf-184">O pacote de proprietário e o pacote de redefinição também serão criados no diretório de configuração e armazenarão a configuração para as permissões de controle de superfície e permissões geradas pelo script.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="bfcdf-185">Na linha 73, substitua o valor da variável **$password** , do **1234** à senha do seu arquivo de certificado.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="bfcdf-186">Se não for necessária uma senha, exclua o texto do **1234** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="bfcdf-187">Os dois últimos caracteres da impressão digital do certificado são necessários para registrar um dispositivo no SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="bfcdf-188">Esse script exibirá esses dígitos para o usuário, o que permite que o usuário ou o técnico grave esses dígitos antes de o sistema ser reiniciado para registrar o dispositivo no SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="bfcdf-189">O script usa o código a seguir, encontrado nas linhas 150-155, para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Os administradores com acesso ao arquivo de certificado (. pfx) podem ler a impressão digital a qualquer momento abrindo o arquivo. pfx em CertMgr. <span data-ttu-id="bfcdf-191">Para exibir a impressão digital com o CertMgr, siga este processo:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="bfcdf-192">Clique com o botão direito do mouse no arquivo. pfx e selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="bfcdf-193">Expanda a pasta no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="bfcdf-194">Selecione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="bfcdf-195">Clique com o botão direito do mouse no certificado no painel principal e selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="bfcdf-196">Selecione a guia **detalhes** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="bfcdf-197">**Todas as** **Propriedades ou somente** devem ser selecionadas no menu suspenso **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="bfcdf-198">Selecione a **impressão digital**do campo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="bfcdf-199">O nome de certificado e a senha do SEMM também devem ser inseridos nesta seção do script ResetSEMM.ps1 para permitir que o Configuration Manager remova SEMM do dispositivo com a ação de desinstalação.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <a name="configure-permissions"></a><span data-ttu-id="bfcdf-200">Configurar permissões</span><span class="sxs-lookup"><span data-stu-id="bfcdf-200">Configure permissions</span></span>

<span data-ttu-id="bfcdf-201">A primeira região do script em que você especificará a configuração do Surface UEFI é a região **configurar permissões** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="bfcdf-202">Esta região começa na linha 210 do script de exemplo com o comentário **# Configure permissões** e continua para a linha 247.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="bfcdf-203">O fragmento de código a seguir define permissões para todas as configurações de Surface UEFI para que elas possam ser modificadas apenas por SEMM e, em seguida, adicionam permissões explícitas para permitir que o usuário local modifique a senha UEFI da superfície, TPM e câmeras frontais e posteriores.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="bfcdf-204">Cada variável **$uefiV 2** identifica uma configuração de Surface UEFI definindo o nome ou a ID e, em seguida, configura as permissões para um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="bfcdf-205">**$ownerOnly** – a permissão para modificar essa configuração é concedida somente a Semm.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="bfcdf-206">**$ownerAndLocalUser** – a permissão para modificar essa configuração é concedida a uma inicialização de usuário local para a UEFI da superfície, bem como Semm.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="bfcdf-207">Você pode encontrar informações sobre os nomes e IDs de configurações disponíveis para a identificação de superfície na seção [nomes e IDs de configurações](#settings-names-and-ids) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <a name="configure-settings"></a><span data-ttu-id="bfcdf-208">Definir configurações</span><span class="sxs-lookup"><span data-stu-id="bfcdf-208">Configure settings</span></span>

<span data-ttu-id="bfcdf-209">A segunda região do script em que você especificará a configuração de Surface UEFI é a região de **configurações** de configuração do script ConfigureSEMM.ps1, que define se cada configuração está habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="bfcdf-210">O script de exemplo inclui instruções para definir todos os valores padrão de todas as configurações.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="bfcdf-211">Em seguida, o script fornece instruções explícitas para desabilitar o IPv6 para inicialização PXE e deixar a senha do administrador da superfície UEFI inalterada.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="bfcdf-212">Você pode encontrar essa região começando com o comentário de **# Configurar configurações** na linha 291 até a linha 335 no script de exemplo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="bfcdf-213">A região aparece da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="bfcdf-214">Assim como as permissões definidas na seção **configurar permissões** do script, a configuração de cada configuração de Surface UEFI é realizada definindo a variável **$uefiV 2** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="bfcdf-215">Para cada linha que define a variável **$uefiV 2** , uma configuração de Surface UEFI é identificada pela configuração de Name ou ID e o valor configurado é definido como **Enabled** ou **Disabled**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="bfcdf-216">Se você não quiser alterar a configuração de uma configuração de superfície UEFI, por exemplo, para garantir que a senha do administrador do Surface não seja desmarcada pela ação de redefinir todas as configurações da superfície UEFI para o padrão, você pode usar **ClearConfiguredValue ()** para impor que essa configuração não será alterada.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="bfcdf-217">No script de exemplo, ele é usado na linha 323 para impedir a limpeza da senha de administrador da superfície UEFI, identificada no script de exemplo por sua ID de configuração, **501**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="bfcdf-218">Você pode encontrar informações sobre os nomes e IDs de configurações disponíveis para a identificação do Surface na seção [nomes e IDs de configurações](#settings-names-and-ids) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <a name="settings-registry-key"></a><span data-ttu-id="bfcdf-219">Chave do registro de configurações</span><span class="sxs-lookup"><span data-stu-id="bfcdf-219">Settings registry key</span></span>

<span data-ttu-id="bfcdf-220">Para identificar sistemas registrados para o Configuration Manager, o script ConfigureSEMM.ps1 grava as chaves do registro que podem ser usadas para identificar sistemas registrados como se tivessem sido instalados com o script de configuração SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="bfcdf-221">Essas chaves podem ser encontradas no local a seguir.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="bfcdf-222">O fragmento de código a seguir, encontrado nas linhas 380-477, é usado para gravar essas chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <a name="settings-names-and-ids"></a><span data-ttu-id="bfcdf-223">Nomes e IDs de configurações</span><span class="sxs-lookup"><span data-stu-id="bfcdf-223">Settings names and IDs</span></span>

<span data-ttu-id="bfcdf-224">Para definir as configurações de Surface UEFI ou permissões para configurações de Surface UEFI, você deve se referir a cada configuração por meio do nome da configuração ou da ID de configuração.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="bfcdf-225">As novas configurações podem ser adicionadas a cada nova atualização para o Surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="bfcdf-226">A melhor maneira de obter uma lista completa das configurações disponíveis em um dispositivo de superfície, juntamente com as IDs de nomes e configurações, é usar o script ShowSettingsOptions.ps1 de SEMM_Powershell.zip em [ferramentas de superfície para downloads de ti](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="bfcdf-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="bfcdf-227">O computador em que o ShowSettingsOptions.ps1 é executado deve ter o Microsoft Surface UEFI Manager instalado, mas o script não requer um dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>


## <a name="deploy-semm-configuration-manager-scripts"></a><span data-ttu-id="bfcdf-228">Implantar scripts do SEMM Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bfcdf-228">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="bfcdf-229">Depois que seus scripts estiverem preparados para configurar e habilitar o SEMM no dispositivo cliente, a próxima etapa será adicionar esses scripts como um aplicativo no Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-229">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="bfcdf-230">Antes de abrir o Configuration Manager, verifique se os seguintes arquivos estão em uma pasta compartilhada que não inclui outros arquivos:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-230">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="bfcdf-231">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="bfcdf-231">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="bfcdf-232">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="bfcdf-232">ResetSEMM.ps1</span></span>
* <span data-ttu-id="bfcdf-233">Seu certificado SEMM (por exemplo SEMMCertificate. pfx)</span><span class="sxs-lookup"><span data-stu-id="bfcdf-233">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="bfcdf-234">Os scripts do Gerenciador de configuração do SEMM serão adicionados ao Configuration Manager como um aplicativo de script.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-234">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="bfcdf-235">O comando para instalar o SEMM com ConfigureSEMM.ps1 é o seguinte.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-235">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="bfcdf-236">O comando para desinstalar o SEMM com ResetSEMM.ps1 é o seguinte.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-236">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="bfcdf-237">Para adicionar os scripts do Gerenciador de configuração SEMM ao Configuration Manager como um aplicativo, use o seguinte processo:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-237">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="bfcdf-238">Inicie o assistente de criação de aplicativos usando a etapa 1 até a etapa 5 da seção [implantar o Gerenciador de Microsoft Surface UEFI](#deploy-microsoft-surface-uefi-manager) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-238">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="bfcdf-239">Prossiga pelo assistente de criação de aplicativos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-239">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="bfcdf-240">**Geral** – selecione **especificar manualmente as informações do aplicativo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-240">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="bfcdf-241">**Informações gerais** – Insira um nome para o aplicativo (por exemplo, Semm) e qualquer outra informação que você queira, como o Publisher, versão ou comentários nesta página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-241">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="bfcdf-242">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-242">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="bfcdf-243">**Catálogo de aplicativos** – os campos nessa página podem ser deixados com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-243">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="bfcdf-244">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-244">Select **Next**.</span></span>

   - <span data-ttu-id="bfcdf-245">**Tipos de implantação** – selecione **Adicionar** para iniciar o assistente criar tipo de implantação.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-245">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="bfcdf-246">Siga as etapas do assistente para criação de tipo de implantação, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-246">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="bfcdf-247">**Geral** – selecione **instalador de script** no menu suspenso **tipo** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-247">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="bfcdf-248">A opção **especificar manualmente a opção informações do tipo de implantação** será selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-248">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="bfcdf-249">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-249">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="bfcdf-250">**Informações gerais** – Insira um nome para o tipo de implantação (por exemplo, scripts de configuração Semm) e, em seguida, selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-250">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="bfcdf-251">**Conteúdo** – selecione **procurar** ao lado do campo **local do conteúdo** e, em seguida, selecione a pasta onde os seus scripts do Semm Configuration Manager estão localizados.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-251">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="bfcdf-252">No campo **programa de instalação** , digite o [comando de instalação](#deploy-semm-configuration-manager-scripts) encontrado anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-252">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="bfcdf-253">No campo **desinstalar programa** , digite o [comando de desinstalação](#deploy-semm-configuration-manager-scripts) encontrado anteriormente neste artigo (mostrado na Figura 2).</span><span class="sxs-lookup"><span data-stu-id="bfcdf-253">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="bfcdf-254">Selecione **Avançar** para ir para a próxima página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-254">Select **Next** to move to the next page.</span></span>
    
     ![Definir os scripts do Gerenciador de configuração SEMM como os comandos instalar e desinstalar](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="bfcdf-256">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-256">Figure 2.</span></span> <span data-ttu-id="bfcdf-257">Definir os scripts do Gerenciador de configuração SEMM como os comandos instalar e desinstalar</span><span class="sxs-lookup"><span data-stu-id="bfcdf-257">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="bfcdf-258">**Método de detecção** – selecione **Adicionar cláusula** para adicionar a regra de detecção de chave do registro de script do Configuration Manager do Semm.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-258">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="bfcdf-259">A janela **regra de detecção** é exibida, conforme mostrado na Figura 3.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-259">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="bfcdf-260">Use as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="bfcdf-260">Use the following settings:</span></span>

       - <span data-ttu-id="bfcdf-261">Selecione **registro** no menu suspenso **tipo de configuração** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-261">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="bfcdf-262">Selecione **HKEY_LOCAL_MACHINE** no menu suspenso **Hive** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-262">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="bfcdf-263">Digite **SOFTWARE\Microsoft\Surface\SEMM** no campo **chave** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-263">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="bfcdf-264">Insira **CertName** no campo **Value** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-264">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="bfcdf-265">Selecione **cadeia de caracteres** no menu suspenso **tipo de dados** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-265">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="bfcdf-266">Selecione a **seguinte configuração do registro deve satisfazer a seguinte regra para indicar o botão presença deste aplicativo** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-266">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="bfcdf-267">Digite o nome do certificado que você digitou na linha 58 do script no campo **valor** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-267">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="bfcdf-268">Selecione **OK** para fechar a janela de **regra de detecção** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-268">Select **OK** to close the **Detection Rule** window.</span></span>

     ![Usar uma chave do registro para identificar os dispositivos registrados no SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="bfcdf-270">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-270">Figure 3.</span></span> <span data-ttu-id="bfcdf-271">Usar uma chave do registro para identificar os dispositivos registrados no SEMM</span><span class="sxs-lookup"><span data-stu-id="bfcdf-271">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="bfcdf-272">Selecione **Avançar** para ir para a próxima página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-272">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="bfcdf-273">**Experiência do usuário** – selecione **instalar para o sistema** no menu suspenso comportamento de **instalação** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-273">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="bfcdf-274">Se você quiser que os usuários registrem e insiram a impressão digital do certificado, deixe o requisito de logon definido como **somente quando um usuário estiver conectado**.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-274">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="bfcdf-275">Se quiser que os administradores insiram a impressão digital para os usuários e os usuários não precisem ver a impressão digital, selecione **se o usuário está ou não conectado** do menu suspenso de **requisitos de logon** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-275">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="bfcdf-276">**Requisitos** – o script ConfigureSEMM.ps1 verifica automaticamente se o dispositivo é um dispositivo Surface antes de tentar habilitar o Semm.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-276">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="bfcdf-277">No entanto, se você pretende implantar esse aplicativo de script em uma coleção com dispositivos diferentes daqueles a serem gerenciados com o SEMM, você pode adicionar requisitos aqui para garantir que esse aplicativo seria executado apenas em dispositivos de superfície ou dispositivos que você pretende gerenciar com o SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-277">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="bfcdf-278">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-278">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="bfcdf-279">**Dependências** – selecione **Adicionar** para abrir a janela **Adicionar dependência** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-279">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="bfcdf-280">Selecione **Adicionar** para abrir a janela **especificar aplicativo necessário** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-280">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="bfcdf-281">Insira um nome para as dependências do SEMM no campo **nome do grupo de dependências** (por exemplo, *Semm assemblys*).</span><span class="sxs-lookup"><span data-stu-id="bfcdf-281">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="bfcdf-282">Selecione **Microsoft Surface UEFI Manager** na lista de **aplicativos disponíveis** e o tipo de implantação msi e, em seguida, selecione **OK** para fechar a janela **especificar aplicativo necessário** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-282">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="bfcdf-283">Mantenha a caixa de seleção **instalação automática** marcada se desejar que o Microsoft Surface UEFI Manager seja instalado automaticamente em dispositivos quando você tentar habilitar o Semm com os scripts do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-283">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="bfcdf-284">Selecione **OK** para fechar a janela **Adicionar dependência** .</span><span class="sxs-lookup"><span data-stu-id="bfcdf-284">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="bfcdf-285">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-285">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="bfcdf-286">**Resumo** – as informações que você digitou em todo o assistente para criar tipo de implantação são exibidas nesta página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-286">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="bfcdf-287">Selecione **Avançar** para confirmar suas seleções.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-287">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="bfcdf-288">**Progresso** – uma barra de progresso e status como o tipo de implantação é adicionado para o aplicativo de script Semm é exibido nesta página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-288">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="bfcdf-289">**Conclusão** – a confirmação da criação do tipo de implantação é exibida quando o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-289">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="bfcdf-290">Selecione **fechar** para concluir o assistente para criar tipo de implantação.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-290">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="bfcdf-291">**Resumo** – as informações que você inseriu em todo o assistente para criar aplicativos são exibidas.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-291">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="bfcdf-292">Selecione **Avançar** para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-292">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="bfcdf-293">**Progresso** – uma barra de progresso e o status conforme o aplicativo é adicionado à biblioteca de software são exibidos nesta página.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-293">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="bfcdf-294">**Conclusão** – a confirmação da criação bem-sucedida do aplicativo é exibida quando o processo de criação do aplicativo é concluído.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-294">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="bfcdf-295">Selecione **fechar** para concluir o assistente de criação de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-295">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="bfcdf-296">Depois que o aplicativo de script estiver disponível na biblioteca de software do Configuration Manager, você poderá distribuir e implantar o SEMM usando os scripts preparados para dispositivos ou coleções.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-296">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="bfcdf-297">Se você configurou os assemblies do Gerenciador de Microsoft Surface UEFI como uma dependência que será instalada automaticamente, você pode implantar o SEMM em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-297">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="bfcdf-298">Se você não configurou os assemblies como uma dependência, eles devem ser instalados nos dispositivos que você pretende gerenciar antes de habilitar o SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-298">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="bfcdf-299">Ao implantar o SEMM usando esse aplicativo de script e uma configuração visível para o usuário final, o script do PowerShell será iniciado e a impressão digital do certificado será exibida pela janela do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-299">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="bfcdf-300">Você pode fazer seus usuários gravarem essa impressão digital e digitá-la quando solicitado pela UEFI de Surface após a reinicialização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-300">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="bfcdf-301">Você também pode configurar a instalação do aplicativo para reinicializar automaticamente e instalar invisivelmente para o usuário.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-301">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="bfcdf-302">Nesse cenário, um técnico será solicitado a inserir a impressão digital em cada dispositivo à medida que ele for reinicializado.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-302">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="bfcdf-303">Qualquer técnico com acesso ao arquivo de certificado pode ler a impressão digital exibindo o certificado com CertMgr.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-303">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="bfcdf-304">Instruções para exibir a impressão digital com CertMgr estão na seção [criar ou modificar os scripts do Gerenciador de configuração Semm](#create-or-modify-the-semm-configuration-manager-scripts) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-304">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="bfcdf-305">A remoção de SEMM de um dispositivo implantado com o Configuration Manager usando esses scripts é tão fácil quanto desinstalar o aplicativo com o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-305">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="bfcdf-306">Essa ação inicia o script ResetSEMM.ps1 e corretamente cancelar o registro do dispositivo com o mesmo arquivo de certificado usado durante a implantação do SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-306">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="bfcdf-307">A Microsoft Surface recomenda que você crie pacotes de redefinição somente quando precisar cancelar o registro de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-307">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="bfcdf-308">Esses pacotes de redefinição geralmente são válidos para apenas um dispositivo, identificado pelo seu número de série.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-308">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="bfcdf-309">No entanto, você pode criar um pacote de redefinição universal que funcionaria para qualquer dispositivo registrado no SEMM com esse certificado.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-309">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="bfcdf-310">É altamente recomendável que você proteja seu pacote de restauração universal com cuidado com o certificado que usou para inscrever dispositivos no SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-310">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="bfcdf-311">Lembre-se de que, assim como o próprio certificado, este pacote universal de restauração pode ser usado para cancelar a inscrição de todos os dispositivos de superfície da sua organização do SEMM.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-311">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="bfcdf-312">Quando você instala um pacote de redefinição, o menor valor com suporte (LSV) é redefinido para um valor de 1.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-312">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="bfcdf-313">Você pode reinscrever um dispositivo usando um pacote de configuração existente.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-313">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="bfcdf-314">O dispositivo solicitará a impressão digital do certificado antes que a propriedade seja tirada.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-314">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="bfcdf-315">Por esse motivo, a reinscrição de um dispositivo no SEMM exigiria um novo pacote a ser criado e instalado nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-315">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="bfcdf-316">Como essa ação é uma nova inscrição e não uma alteração na configuração em um dispositivo já registrado no SEMM, o dispositivo solicitará a impressão digital do certificado antes de a propriedade ser executada.</span><span class="sxs-lookup"><span data-stu-id="bfcdf-316">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>
