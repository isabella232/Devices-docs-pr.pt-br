---
title: Criar pacotes de provisionamento para o Surface Hub 2S
description: Esta página descreve como implantar o Surface Hub 2S usando pacotes de provisionamento e outras ferramentas.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576861"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a><span data-ttu-id="0770e-104">Criar pacotes de provisionamento para o Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="0770e-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="0770e-105">Você pode usar Windows Configuration Designer (WCD) para criar pacotes de provisionamento para automatizar a implantação do Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="0770e-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate deployment of Surface Hub 2S.</span></span> <span data-ttu-id="0770e-106">Use pacotes de provisionamento para adicionar certificados, configurar proxies, configurar administradores de dispositivos e contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0770e-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="0770e-107">Você também pode usar pacotes de provisionamento juntamente com um arquivo de configuração para implantar vários Surface Hubs com uma única unidade de pen drive USB.</span><span class="sxs-lookup"><span data-stu-id="0770e-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <a name="install-windows-configuration-designer"></a><span data-ttu-id="0770e-108">Instalar o Designer de Configuração do Windows</span><span class="sxs-lookup"><span data-stu-id="0770e-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="0770e-109">Instale Windows Designer de Configuração Windows ADK (Kit de Avaliação e Implantação) Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0770e-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="0770e-110">Baixe e instale o [ADK para Windows 10, versão 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span><span class="sxs-lookup"><span data-stu-id="0770e-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="0770e-111">Para mais informações, consulte [Baixe e instale o Kit de Avaliação e Implantação do Windows](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="0770e-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <a name="add-certificates"></a><span data-ttu-id="0770e-112">Adicionar certificados</span><span class="sxs-lookup"><span data-stu-id="0770e-112">Add certificates</span></span>

<span data-ttu-id="0770e-113">Você pode importar certificados de Autoridade de Certificação para Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="0770e-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="0770e-114">Para adicionar certificados ao Surface Hub 2S, você precisa de uma cópia de cada certificado como X.509 no formato .cer.</span><span class="sxs-lookup"><span data-stu-id="0770e-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="0770e-115">Não é possível importar .crt, .pfx ou outros formatos de contêiner.</span><span class="sxs-lookup"><span data-stu-id="0770e-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="0770e-116">Os certificados devem ser importados para Windows Designer de Configuração e organizados pela hierarquia:</span><span class="sxs-lookup"><span data-stu-id="0770e-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

> [!div class="mx-imgBorder"]
> ![Adicionar certificados](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a><span data-ttu-id="0770e-118">Configurar proxy durante o OOBE</span><span class="sxs-lookup"><span data-stu-id="0770e-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="0770e-119">Em Windows Designer de Configuração, vá para a guia Configurar configurações de proxy e insira as configurações apropriadas, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="0770e-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

> [!div class="mx-imgBorder"]
> ![Configurar as definições do proxy](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="0770e-121">Ao configurar configurações de \*\*\*\* proxy, desligue Automaticamente as configurações de detecção se você pretende usar um script de instalação ou um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="0770e-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="0770e-122">Você pode usar um script de instalação *ou um* servidor proxy, não ambos.</span><span class="sxs-lookup"><span data-stu-id="0770e-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a><span data-ttu-id="0770e-123">Afiliada Surface Hub 2S com Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0770e-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="0770e-124">Você pode associar o Surface Hub 2S ao Azure Active Directory usando um pacote de provisionamento: como administrador global do Azure Active Directory, você pode associar um grande número de novos dispositivos Windows ao Azure Active Directory e ao Intune usando um token em massa.</span><span class="sxs-lookup"><span data-stu-id="0770e-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="0770e-125">Para criar um token em massa, dê um nome amigável, configure a data de expiração (máximo de 30 dias) e use suas credenciais de Administrador para adquirir o token, conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="0770e-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

> [!div class="mx-imgBorder"]
> ![Configurar administradores de dispositivos exemplo 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Configurar administradores de dispositivos exemplo 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Configurar administradores de dispositivos exemplo 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a><span data-ttu-id="0770e-129">Provisionamento de vários dispositivos (.csv arquivo)</span><span class="sxs-lookup"><span data-stu-id="0770e-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="0770e-130">Além do pacote de provisionamento, você pode usar um arquivo de configuração Surface Hub para facilitar ainda mais a configuração de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0770e-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="0770e-131">Um Surface Hub de configuração contém uma lista de contas de dispositivo e nomes amigáveis para projeção sem fio.</span><span class="sxs-lookup"><span data-stu-id="0770e-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="0770e-132">Durante a primeira execução, você tem a opção de escolher uma conta de dispositivo e um nome amigável de um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="0770e-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <a name="to-create-a-surface-hub-configuration-file"></a><span data-ttu-id="0770e-133">Para criar um arquivo Surface Hub configuração</span><span class="sxs-lookup"><span data-stu-id="0770e-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="0770e-134">Usando Microsoft Excel ou outro editor CSV, crie um arquivo CSV chamado: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="0770e-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>

2. <span data-ttu-id="0770e-135">Insira uma lista de contas de dispositivo e nomes amigáveis neste formato:</span><span class="sxs-lookup"><span data-stu-id="0770e-135">Enter a list of device accounts and friendly names in this format:</span></span>

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. <span data-ttu-id="0770e-136">Salve o arquivo na raiz da unidade de polegar USB onde você copiou o arquivo PPKG.</span><span class="sxs-lookup"><span data-stu-id="0770e-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exemplo de arquivo de configuração](images/sh2-config-file.png)
