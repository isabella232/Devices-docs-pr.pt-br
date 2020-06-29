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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831164"
---
# <span data-ttu-id="62a12-104">Criar pacotes de provisionamento para o Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="62a12-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="62a12-105">Você pode usar o Windows Configuration designer (WCD) para criar pacotes de provisionamento para automatizar o processo de implantação do Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="62a12-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="62a12-106">Use pacotes de provisionamento para adicionar certificados, configurar proxies, configurar administradores de dispositivos e contas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="62a12-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="62a12-107">Você também pode usar pacotes de provisionamento juntamente com um arquivo de configuração para implantar vários hubs de superfície com um único pen drive USB.</span><span class="sxs-lookup"><span data-stu-id="62a12-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="62a12-108">Instalar o Designer de Configuração do Windows</span><span class="sxs-lookup"><span data-stu-id="62a12-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="62a12-109">Instale o designer de configuração do Windows a partir do kit de avaliação e implantação do Windows (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="62a12-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="62a12-110">Baixe e instale o [ADK para Windows 10, versão 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span><span class="sxs-lookup"><span data-stu-id="62a12-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="62a12-111">Para obter mais informações, consulte [baixar e instalar o Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="62a12-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="62a12-112">Adicionar certificados</span><span class="sxs-lookup"><span data-stu-id="62a12-112">Add certificates</span></span>

<span data-ttu-id="62a12-113">Você pode importar certificados de autoridade de certificação para o Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="62a12-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="62a12-114">Para adicionar certificados ao Surface Hub 2S, você precisa de uma cópia de cada certificado como X. 509 no formato. cer.</span><span class="sxs-lookup"><span data-stu-id="62a12-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="62a12-115">Você não pode importar. CRT,. pfx, ou outros formatos de contêiner.</span><span class="sxs-lookup"><span data-stu-id="62a12-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="62a12-116">Os certificados devem ser importados para o designer de configuração do Windows e organizados por hierarquia:</span><span class="sxs-lookup"><span data-stu-id="62a12-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![Adicionar certificados](images/sh2-wcd.png)

### <span data-ttu-id="62a12-118">Configurar proxy durante OOBE</span><span class="sxs-lookup"><span data-stu-id="62a12-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="62a12-119">No designer de configuração do Windows, vá para a guia Configurar configurações de proxy e insira as configurações apropriadas, conforme mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="62a12-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![Configurar as definições do proxy](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="62a12-121">Ao definir as configurações de proxy, desative **as configurações de detecção automática** se você pretende usar um script de instalação ou um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="62a12-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="62a12-122">Você pode usar um script de configuração *ou* um servidor proxy, não ambos.</span><span class="sxs-lookup"><span data-stu-id="62a12-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="62a12-123">Hub de superfície do associado 2S com o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="62a12-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="62a12-124">Você pode afiliar o Surface Hub 2S ao Azure Active Directory usando um pacote de provisionamento: como um administrador global do Azure Active Directory, você pode ingressar em grandes números de dispositivos novos do Windows para o Azure Active Directory e o Intune usando um token em massa.</span><span class="sxs-lookup"><span data-stu-id="62a12-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="62a12-125">Para criar um token em massa, dê a ele um nome amigável, configure a data de expiração (máximo de 30 dias) e use as credenciais de administrador para adquirir o token conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="62a12-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![Configurar administradores de dispositivo](images/sh2-token.png) <br><br>
 ![Configurar administradores de dispositivo](images/sh2-token2.png) <br><br>
 ![Configurar administradores de dispositivo](images/sh2-token3.png) <br><br>

### <span data-ttu-id="62a12-129">Provisionando vários dispositivos (arquivo. csv)</span><span class="sxs-lookup"><span data-stu-id="62a12-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="62a12-130">Além do pacote de provisionamento, você pode usar um arquivo de configuração do Surface Hub para facilitar ainda mais a configuração de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="62a12-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="62a12-131">Um arquivo de configuração do Surface Hub contém uma lista de contas de dispositivo e nomes amigáveis para a projeção sem fio.</span><span class="sxs-lookup"><span data-stu-id="62a12-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="62a12-132">Durante a primeira execução, você tem a opção de escolher uma conta de dispositivo e um nome amigável a partir de um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="62a12-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="62a12-133">Para criar um arquivo de configuração do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="62a12-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="62a12-134">Usando o Microsoft Excel ou outro editor de CSV, crie um arquivo CSV chamado: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="62a12-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="62a12-135">Insira uma lista de contas de dispositivo e nomes amigáveis neste formato:</span><span class="sxs-lookup"><span data-stu-id="62a12-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="62a12-136">Salve o arquivo na raiz da unidade do Thumb USB em que você copiou o arquivo PPKG.</span><span class="sxs-lookup"><span data-stu-id="62a12-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![Exemplo de arquivo de configuração](images/sh2-config-file.png)
