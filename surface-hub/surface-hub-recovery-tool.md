---
title: Uso da Ferramenta de Recuperação do Surface Hub
description: Como usar a ferramenta de recuperação do Surface Hub para recriar a imagem do SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gerenciar o Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831155"
---
# <span data-ttu-id="2cfd4-104">Uso da Ferramenta de Recuperação do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2cfd4-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="2cfd4-105">A [ferramenta de recuperação do Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) ajuda você a recriar uma nova imagem da unidade de estado sólido (SSD) do Hub Surface usando um dispositivo de desktop do Windows 10, sem ligar para o suporte ou para substituir a SSD.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="2cfd4-106">Com essa ferramenta, você pode renovar uma imagem do SSD com uma senha de administrador desconhecida, erros de inicialização, não foi possível concluir uma recuperação na nuvem ou para um dispositivo que tenha uma versão mais antiga do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="2cfd4-107">A ferramenta não corrigirá o SSDs fisicamente danificado.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="2cfd4-108">Para recriar a imagem da SSD do Surface Hub usando a ferramenta de recuperação, você precisará remover a SSD do Surface Hub, conectar a unidade ao cabo USB-para-SATA e conectar o cabo ao computador desktop no qual a ferramenta de recuperação está instalada.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="2cfd4-109">Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte [substituição da SSD do Surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="2cfd4-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cfd4-110">Não deixe que o dispositivo vá para o modo de suspensão ou interrompa o download do arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="2cfd4-111">Se a ferramenta não conseguir reportar sua unidade, entre em contato com o [suporte do Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="2cfd4-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="2cfd4-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2cfd4-112">Prerequisites</span></span>

### <span data-ttu-id="2cfd4-113">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="2cfd4-113">Mandatory</span></span>

- <span data-ttu-id="2cfd4-114">PC host executando a versão de 64 bits do Windows 10, versão 1607 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="2cfd4-115">Acesso à rede e à Internet</span><span class="sxs-lookup"><span data-stu-id="2cfd4-115">Internet access</span></span>
- <span data-ttu-id="2cfd4-116">Abrir porta USB 2,0 ou superior</span><span class="sxs-lookup"><span data-stu-id="2cfd4-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="2cfd4-117">Cabo USB-para-SATA</span><span class="sxs-lookup"><span data-stu-id="2cfd4-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="2cfd4-118">10 GB de espaço livre em disco no computador host</span><span class="sxs-lookup"><span data-stu-id="2cfd4-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="2cfd4-119">O SSDs é fornecido com o Surface Hub ou um SSD fornecido pelo suporte como substituto.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="2cfd4-120">Não há suporte para o SSDs não fornecido pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="2cfd4-121">Recomendações</span><span class="sxs-lookup"><span data-stu-id="2cfd4-121">Recommended</span></span>

- <span data-ttu-id="2cfd4-122">Conexão à Internet de alta velocidade</span><span class="sxs-lookup"><span data-stu-id="2cfd4-122">High-speed Internet connection</span></span>
- <span data-ttu-id="2cfd4-123">Porta USB 3,0 aberta</span><span class="sxs-lookup"><span data-stu-id="2cfd4-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="2cfd4-124">Cabo USB 3,0 ou superior USB para SATA</span><span class="sxs-lookup"><span data-stu-id="2cfd4-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="2cfd4-125">A ferramenta de imagem foi testada com a marca e o modelo de cabos a seguir:</span><span class="sxs-lookup"><span data-stu-id="2cfd4-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="2cfd4-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="2cfd4-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="2cfd4-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="2cfd4-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="2cfd4-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="2cfd4-128">Ugreen 20231</span></span>

## <span data-ttu-id="2cfd4-129">Baixar a ferramenta de recuperação do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2cfd4-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="2cfd4-130">A ferramenta de recuperação do Surface Hub está disponível para download em [Ferramentas do Surface Hub para ele](https://www.microsoft.com/download/details.aspx?id=52210) sob o nome do arquivo **SurfaceHub_Recovery_v1.14.137.0.msi**.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v1.14.137.0.msi**.</span></span>

<span data-ttu-id="2cfd4-131">Para iniciar o download, clique em **baixar**, escolha **SurfaceHub_Recovery_v1.14.137.0.msi** na lista e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v1.14.137.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="2cfd4-132">No menu pop-up, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="2cfd4-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="2cfd4-133">Clique em **executar** para iniciar a instalação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="2cfd4-134">Clique em **salvar** para copiar o download para o seu computador para instalação posterior.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="2cfd4-135">Instale a ferramenta de recuperação do Surface Hub no PC host.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="2cfd4-136">Executar a ferramenta de recuperação do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2cfd4-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="2cfd4-137">No PC host, selecione o botão **Iniciar** , Role pela lista em ordem alfabética à esquerda e selecione o atalho da ferramenta de recuperação.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Atalho da ferramenta de recuperação do Microsoft Surface Hub](images/shrt-shortcut.png)

2. <span data-ttu-id="2cfd4-139">Clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-139">Click **Start**.</span></span>

    ![Botão Iniciar da ferramenta de recuperação](images/shrt-start.png)

3. <span data-ttu-id="2cfd4-141">Na janela **orientação** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-141">In the **Guidance** window, click **Next**.</span></span>

    ![Não deixe que sua máquina vá para a orientação de repouso](images/shrt-guidance.png)

4. <span data-ttu-id="2cfd4-143">clique em **Sim** para baixar a imagem.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-143">click **Yes** to download the image.</span></span> <span data-ttu-id="2cfd4-144">O tempo para baixar a imagem de recuperação depende de velocidades de conexão à Internet.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-144">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="2cfd4-145">Em uma conexão corporativa média, pode levar até uma hora para baixar o arquivo de imagem 8 GB.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-145">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Baixar a imagem?](images/shrt-download.png)

5. <span data-ttu-id="2cfd4-147">Quando o download estiver concluído, a ferramenta instruirá você a conectar uma unidade SSD.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-147">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="2cfd4-148">Se a ferramenta não conseguir localizar a unidade anexada, há uma boa chance de que o cabo que está sendo usado não relate o nome da SSD para Windows.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-148">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="2cfd4-149">A ferramenta de geração de imagens deve encontrar o nome da unidade como "dispositivo USB LITEON L CH-128V2S" para poder continuar.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-149">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="2cfd4-150">Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte [substituição da SSD do Surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="2cfd4-150">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Conexão SSD](images/shrt-drive.png)

6. <span data-ttu-id="2cfd4-152">Quando a unidade for reconhecida, clique em **Iniciar** para começar o processo de recriação de imagens.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-152">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="2cfd4-153">No aviso de que todos os dados na unidade serão apagados, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-153">On the warning that all data on the drive will be erased, click **OK**.</span></span>

    ![Iniciar a recriação da imagem do SSD](images/shrt-drive-start.png)

    <span data-ttu-id="2cfd4-155">Antes de aplicar a imagem do sistema à unidade, a SSD é reparticionada e formatada.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="2cfd4-156">Copiar os binários do sistema levará aproximadamente 30 minutos, mas poderá demorar mais dependendo da velocidade do barramento USB, do cabo que está sendo usado ou do software antivírus instalado no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>

    ![Cópia concluída](images/shrt-done.png)

    ![Recriação de imagem concluída](images/shrt-complete.png)

## <span data-ttu-id="2cfd4-159">Solução de problemas e problemas comuns</span><span class="sxs-lookup"><span data-stu-id="2cfd4-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="2cfd4-160">Problema</span><span class="sxs-lookup"><span data-stu-id="2cfd4-160">Issue</span></span> | <span data-ttu-id="2cfd4-161">Observações</span><span class="sxs-lookup"><span data-stu-id="2cfd4-161">Notes</span></span>
--- | ---
<span data-ttu-id="2cfd4-162">A ferramenta falha ao fazer a imagem do SSD</span><span class="sxs-lookup"><span data-stu-id="2cfd4-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="2cfd4-163">Certifique-se de que você esteja usando uma SSD fornecida na fábrica e um dos cabos testados.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="2cfd4-164">O processo de recriação de imagem parece interrompido/congelado</span><span class="sxs-lookup"><span data-stu-id="2cfd4-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="2cfd4-165">É seguro fechar e reiniciar a ferramenta de recuperação do Surface Hub sem nenhum efeito ineficiente na SSD.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="2cfd4-166">A unidade não é reconhecida pela ferramenta</span><span class="sxs-lookup"><span data-stu-id="2cfd4-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="2cfd4-167">Verifique se a SSD do Surface Hub é enumerada como uma unidade Lite, "LITEON L CH-128V2S USB Device".</span><span class="sxs-lookup"><span data-stu-id="2cfd4-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="2cfd4-168">Se a unidade for reconhecida como outro dispositivo nomeado, o cabo atual não será compatível.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="2cfd4-169">Tente outro cabo ou um dos cabos testados listados acima.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="2cfd4-170">Erro:-2147024809</span><span class="sxs-lookup"><span data-stu-id="2cfd4-170">Error: -2147024809</span></span> | <span data-ttu-id="2cfd4-171">Abra o Gerenciador de disco e remova as partições na unidade do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="2cfd4-172">Desconecte e reconecte a unidade ao computador host.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="2cfd4-173">Reinicie a ferramenta de imagem.</span><span class="sxs-lookup"><span data-stu-id="2cfd4-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="2cfd4-174">Se a ferramenta não conseguir reportar sua unidade, entre em contato com o [suporte do Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="2cfd4-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>
