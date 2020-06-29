---
title: Proteger e gerenciar Surface Hub 2S com SEMM
description: Saiba mais sobre a proteção do Surface Hub 2S com o SEMM.
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830420"
---
# <span data-ttu-id="91d16-104">Proteger e gerenciar o Surface Hub 2S com SEMM e UEFI</span><span class="sxs-lookup"><span data-stu-id="91d16-104">Secure and manage Surface Hub 2S with SEMM and UEFI</span></span>

<span data-ttu-id="91d16-105">Novo no Surface Hub 2S, você pode usar SEMM para gerenciar a configuração de UEFI do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91d16-105">New in Surface Hub 2S, you can use SEMM to manage the UEFI setting of the device.</span></span>
<span data-ttu-id="91d16-106">Use o configurador UEFI da Microsoft Surface para controlar os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="91d16-106">Use the Microsoft Surface UEFI Configurator to control the following components:</span></span>

- <span data-ttu-id="91d16-107">LAN com fio</span><span class="sxs-lookup"><span data-stu-id="91d16-107">Wired LAN</span></span>
- <span data-ttu-id="91d16-108">Câmeras</span><span class="sxs-lookup"><span data-stu-id="91d16-108">Cameras</span></span>
- <span data-ttu-id="91d16-109">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="91d16-109">Bluetooth</span></span>
- <span data-ttu-id="91d16-110">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="91d16-110">Wi-Fi</span></span>
- <span data-ttu-id="91d16-111">Sensor de ocupação</span><span class="sxs-lookup"><span data-stu-id="91d16-111">Occupancy sensor</span></span>

<span data-ttu-id="91d16-112">Use o configurador UEFI da Microsoft Surface para ativar ou desativar as seguintes configurações de UEFI:</span><span class="sxs-lookup"><span data-stu-id="91d16-112">Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:</span></span>

- <span data-ttu-id="91d16-113">Iniciar</span><span class="sxs-lookup"><span data-stu-id="91d16-113">Boot</span></span>

    - <span data-ttu-id="91d16-114">Inicialização de IPv6 para PXE</span><span class="sxs-lookup"><span data-stu-id="91d16-114">IPv6 for PXE Boot</span></span>
    - <span data-ttu-id="91d16-115">Inicialização alternativa</span><span class="sxs-lookup"><span data-stu-id="91d16-115">Alternate Boot</span></span>
    - <span data-ttu-id="91d16-116">Bloqueio da ordem de inicialização</span><span class="sxs-lookup"><span data-stu-id="91d16-116">Boot Order Lock</span></span>
    - <span data-ttu-id="91d16-117">Inicialização USB</span><span class="sxs-lookup"><span data-stu-id="91d16-117">USB Boot</span></span>
- <span data-ttu-id="91d16-118">Página inicial da UEFI</span><span class="sxs-lookup"><span data-stu-id="91d16-118">UEFI Front Page</span></span>

    - <span data-ttu-id="91d16-119">Devices</span><span class="sxs-lookup"><span data-stu-id="91d16-119">Devices</span></span>
    - <span data-ttu-id="91d16-120">Iniciar</span><span class="sxs-lookup"><span data-stu-id="91d16-120">Boot</span></span>
    - <span data-ttu-id="91d16-121">Data/Hora</span><span class="sxs-lookup"><span data-stu-id="91d16-121">Date/Time</span></span>

## <span data-ttu-id="91d16-122">Criar a imagem de configuração UEFI</span><span class="sxs-lookup"><span data-stu-id="91d16-122">Create UEFI configuration image</span></span>

<span data-ttu-id="91d16-123">Ao contrário de outros dispositivos de superfície, você não pode usar um arquivo MSI ou uma imagem do PE PE para aplicar essas configurações no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="91d16-123">Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub 2S.</span></span> <span data-ttu-id="91d16-124">Em vez disso, você precisa criar uma imagem USB para carregar no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91d16-124">Instead, you need to create a USB image to load into the device.</span></span> <span data-ttu-id="91d16-125">Para criar uma imagem de configuração UEFI do Surface Hub 2S, baixe e instale a versão mais recente do Microsoft Surface UEFI Configuration da página [Surface Tools para it](https://www.microsoft.com/download/details.aspx?id=46703) no centro de download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91d16-125">To create a Surface Hub 2S UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span> <span data-ttu-id="91d16-126">Para obter mais informações sobre como usar UEFI e SEMM, consulte [modo de gerenciamento do Microsoft Surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span><span class="sxs-lookup"><span data-stu-id="91d16-126">For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="91d16-127">Para configurar o UEFI no Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="91d16-127">To configure UEFI on Surface Hub 2S</span></span>

1. <span data-ttu-id="91d16-128">Inicie o configurador UEFI e, na primeira tela, escolha **pacote de configuração**.</span><span class="sxs-lookup"><span data-stu-id="91d16-128">Start the UEFI Configurator and on the first screen, choose **Configuration Package**.</span></span><br><br>
![\* Iniciar o configurador UEFI e escolher pacote de configuração \*](images/sh2-uefi1.png) <br> <br>
2. <span data-ttu-id="91d16-130">Para adicionar o certificado ao seu pacote, você deve ter um certificado válido com a chave privada em um formato de arquivo. pfx para assinar e proteger o pacote.</span><span class="sxs-lookup"><span data-stu-id="91d16-130">To add the certificate to your package, you must have a valid certificate with the private key in a .pfx file format to sign and protect the package.</span></span> <span data-ttu-id="91d16-131">Selecione **+ proteção de certificado.**</span><span class="sxs-lookup"><span data-stu-id="91d16-131">Select **+ Certificate Protection.**</span></span> <br>
![\* Selecionar + proteção de certificado \*](images/sh2-uefi2.png) <br><br>
3. <span data-ttu-id="91d16-133">Digite a senha da chave privada do certificado.</span><span class="sxs-lookup"><span data-stu-id="91d16-133">Enter the certificate’s private key’s password.</span></span><br>
![\* Insira a senha da chave privada do certificado \*](images/sh2-uefi3.png) <br><br>
4. <span data-ttu-id="91d16-135">Após importar a chave privada, continue a criar o pacote.</span><span class="sxs-lookup"><span data-stu-id="91d16-135">After importing the private key, continue creating the package.</span></span><br>
![\* Continuar a criar o pacote \*](images/sh2-uefi4.png) <br><br>
5. <span data-ttu-id="91d16-137">Escolha **Hub** e **Surface Hub 2s** como o destino para o pacote de configuração UEFI.</span><span class="sxs-lookup"><span data-stu-id="91d16-137">Choose **Hub** and **Surface Hub 2S** as the target for the UEFI configuration package.</span></span><br>
![\* Escolha Hub e Surface Hub 2S como o destino para o pacote de configuração UEFI \*](images/sh2-uefi5.png) <br><br>
6. <span data-ttu-id="91d16-139">Escolha os componentes e configurações que você deseja ativar ou desativar no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="91d16-139">Choose the components and settings you want to activate or deactivate on Surface Hub 2S.</span></span><br>
![\* Escolha os componentes e configurações que você deseja ativar ou desativar \*](images/sh2-uefi6.png) <br><br>
7. <span data-ttu-id="91d16-141">Use a opção USB para exportar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="91d16-141">Use the USB option to export the file.</span></span><br>
![\* Use a opção USB para exportar o arquivo \*](images/sh2-uefi8.png) <br><br>
8. <span data-ttu-id="91d16-143">Insira e escolha a unidade USB que você deseja usar para este pacote.</span><span class="sxs-lookup"><span data-stu-id="91d16-143">Insert and choose the USB drive you’d like to use for this package.</span></span> <span data-ttu-id="91d16-144">A unidade USB será formatada e você perderá as informações que elas contêm.</span><span class="sxs-lookup"><span data-stu-id="91d16-144">The USB drive will be formatted and you lose any information you have on it.</span></span><br>
![\* Insira e escolha a unidade USB para seu pacote \*](images/sh2-uefi9.png) <br><br>
9. <span data-ttu-id="91d16-146">Após a criação bem-sucedida do pacote, o configurador mostrará os dois últimos caracteres da impressão digital do seu certificado.</span><span class="sxs-lookup"><span data-stu-id="91d16-146">Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint.</span></span> <span data-ttu-id="91d16-147">Você precisa desses caracteres ao importar para a configuração para o Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="91d16-147">You need these characters when you import to the configuration to Surface Hub 2S.</span></span><br>
![\* Configuração bem-sucedida do pacote \*](images/sh2-uefi10.png) <br>

## <span data-ttu-id="91d16-149">Para inicializar na UEFI</span><span class="sxs-lookup"><span data-stu-id="91d16-149">To boot into UEFI</span></span>

<span data-ttu-id="91d16-150">Desative o Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="91d16-150">Turn off Surface Hub 2S.</span></span> <span data-ttu-id="91d16-151">Pressione e mantenha pressionado o botão **volume up** e pressione o botão de **energia** .</span><span class="sxs-lookup"><span data-stu-id="91d16-151">Press and hold the **Volume Up** button and press the **Power** Button.</span></span> <span data-ttu-id="91d16-152">Mantenha pressionado o botão aumentar volume até que o menu UEFI seja exibido.</span><span class="sxs-lookup"><span data-stu-id="91d16-152">Keep holding the Volume Up button until the UEFI menu appears.</span></span>
