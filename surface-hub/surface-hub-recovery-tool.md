---
title: Uso da Ferramenta de Recuperação do Surface Hub
description: Como usar a Ferramenta de Recuperação do Surface Hub para fazer uma nova imagem do SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gerenciar o Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/18/2020
ms.localizationpriority: medium
ms.openlocfilehash: 9df9de731ac5c8f8acb393db3d4b16e9d1c98a9e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312027"
---
# <span data-ttu-id="6bbfb-104">Uso da Ferramenta de Recuperação do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6bbfb-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="6bbfb-105">A Ferramenta de Recuperação do [Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) ajuda você a fazer a imagem da unidade de estado sólido (SSD) do Surface Hub usando um dispositivo de área de trabalho do Windows 10, sem chamar o suporte ou substituir o SSD.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="6bbfb-106">Com essa ferramenta, você pode reimager um SSD que tenha uma senha de Administrador desconhecida, erros de inicialização, não foi possível concluir uma recuperação na nuvem ou para um dispositivo que tenha uma versão mais antiga do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="6bbfb-107">A ferramenta não corrigirá SSDs fisicamente danificados.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="6bbfb-108">Para fazer uma nova imagem do SSD do Surface Hub usando a Ferramenta de Recuperação, você precisará remover o SSD do Surface Hub, conectar a unidade ao cabo USB para SATA e conectar o cabo ao computador desktop no qual a Ferramenta de Recuperação está instalada.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="6bbfb-109">Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte Substituição [de SSD do Surface Hub.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="6bbfb-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6bbfb-110">Não deixe o dispositivo entrar em sleep ou interromper o download do arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="6bbfb-111">Se a ferramenta não tiver êxito na imagem da unidade, entre em contato com o [Suporte do Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="6bbfb-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="6bbfb-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6bbfb-112">Prerequisites</span></span>

### <span data-ttu-id="6bbfb-113">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="6bbfb-113">Mandatory</span></span>

- <span data-ttu-id="6bbfb-114">Computador host executando a versão de 64 bits do Windows 10, versão 1607 ou superior.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="6bbfb-115">Acesso à rede e à Internet</span><span class="sxs-lookup"><span data-stu-id="6bbfb-115">Internet access</span></span>
- <span data-ttu-id="6bbfb-116">Abrir porta USB 2.0 ou superior</span><span class="sxs-lookup"><span data-stu-id="6bbfb-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="6bbfb-117">Cabo USB para SATA</span><span class="sxs-lookup"><span data-stu-id="6bbfb-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="6bbfb-118">10 GB de espaço livre em disco no computador host</span><span class="sxs-lookup"><span data-stu-id="6bbfb-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="6bbfb-119">SSDs fornecidos com o Surface Hub ou um SSD fornecido pelo Suporte como um substituto.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="6bbfb-120">Não há suporte para SSDs fornecidos pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="6bbfb-121">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6bbfb-121">Recommended</span></span>

- <span data-ttu-id="6bbfb-122">Conexão com a Internet de alta velocidade</span><span class="sxs-lookup"><span data-stu-id="6bbfb-122">High-speed Internet connection</span></span>
- <span data-ttu-id="6bbfb-123">Abrir porta USB 3.0</span><span class="sxs-lookup"><span data-stu-id="6bbfb-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="6bbfb-124">Cabo USB 3.0 ou superior USB para SATA</span><span class="sxs-lookup"><span data-stu-id="6bbfb-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="6bbfb-125">A ferramenta de imagem foi testada com a seguinte make e modelo de cabos:</span><span class="sxs-lookup"><span data-stu-id="6bbfb-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="6bbfb-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="6bbfb-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="6bbfb-127">Blackwill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="6bbfb-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="6bbfb-128">Ugrren 20231</span><span class="sxs-lookup"><span data-stu-id="6bbfb-128">Ugreen 20231</span></span>

## <span data-ttu-id="6bbfb-129">Baixar a Ferramenta de Recuperação do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6bbfb-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="6bbfb-130">A Ferramenta de Recuperação do Surface Hub está disponível para download das Ferramentas [do Surface Hub para IT](https://www.microsoft.com/download/details.aspx?id=52210)  sob o nome de arquivo **SurfaceHub_Recovery_v2.0.139.0.msi**.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.0.139.0.msi**.</span></span>

<span data-ttu-id="6bbfb-131">Para iniciar o download, clique em **Baixar,** **SurfaceHub_Recovery_v2.0.139.0.msi** na lista e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="6bbfb-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.0.139.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="6bbfb-132">No pop-up, escolha uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="6bbfb-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="6bbfb-133">Clique **em Executar** para iniciar a instalação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="6bbfb-134">Clique **em Salvar** para copiar o download para o computador para instalação posterior.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="6bbfb-135">Instale a Ferramenta de Recuperação do Surface Hub no computador host.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="6bbfb-136">Executar a Ferramenta de Recuperação do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6bbfb-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="6bbfb-137">No computador host, selecione o **botão** Iniciar, role pela lista alfabética à esquerda e selecione o atalho da ferramenta de recuperação.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Atalho da Ferramenta de Recuperação do Microsoft Surface Hub](images/shrt-shortcut.png)

2. <span data-ttu-id="6bbfb-139">Clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-139">Click **Start**.</span></span>

    ![Botão Iniciar da Ferramenta de Recuperação](images/shrt-start.png)


3. <span data-ttu-id="6bbfb-141">Na janela **Diretrizes,** clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="6bbfb-141">In the **Guidance** window, click **Next**.</span></span>

    ![Não deixe seu computador ir para as diretrizes de sleep](images/shrt-guidance.png)

4. <span data-ttu-id="6bbfb-143">Na janela Selecionar imagem, clique em **RS2** ou em seu sucessor **20H2,** selecione Continuar e, em **seguida,** selecione **Baixar imagem.**</span><span class="sxs-lookup"><span data-stu-id="6bbfb-143">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="6bbfb-144">![Imagem de download da Ferramenta de ](images/shrt-select-image.png) ![ Recuperação Selecionar imagem](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="6bbfb-144">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="6bbfb-145">O tempo para baixar a imagem de recuperação depende das velocidades de conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-145">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="6bbfb-146">Em uma conexão corporativa média, pode levar até uma hora para baixar o arquivo de imagem de 8 GB.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-146">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Baixando imagem](images/shrt-download.png)



5. <span data-ttu-id="6bbfb-148">Quando o download for concluído, a ferramenta instrui você a conectar uma unidade SSD.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-148">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="6bbfb-149">Se a ferramenta não conseguir localizar a unidade anexada, é possível que o cabo que está sendo usado não reporte o nome do SSD para o Windows.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-149">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="6bbfb-150">A ferramenta de imagem deve encontrar o nome da unidade como "LITEON L CH-128V2S USB Device" antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-150">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="6bbfb-151">Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte Substituição [de SSD do Surface Hub.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="6bbfb-151">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Conectar SSD](images/shrt-drive.png)

6. <span data-ttu-id="6bbfb-153">Quando a unidade for reconhecida, clique em **Iniciar** para iniciar o processo de re-imagem.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-153">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="6bbfb-154">No aviso de que todos os dados na unidade serão apagados, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="6bbfb-154">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="6bbfb-155">Antes de aplicar a imagem do sistema à unidade, o SSD é reparticionado e formatado.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="6bbfb-156">Copiar os binários do sistema levará aproximadamente 30 minutos, mas pode demorar mais, dependendo da velocidade do barramento USB, do cabo que está sendo usado ou do software antivírus instalado no sistema.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="6bbfb-157">Solução de problemas e problemas comuns</span><span class="sxs-lookup"><span data-stu-id="6bbfb-157">Troubleshooting and common problems</span></span>

<span data-ttu-id="6bbfb-158">Problema</span><span class="sxs-lookup"><span data-stu-id="6bbfb-158">Issue</span></span> | <span data-ttu-id="6bbfb-159">Observações</span><span class="sxs-lookup"><span data-stu-id="6bbfb-159">Notes</span></span>
--- | ---
<span data-ttu-id="6bbfb-160">A ferramenta falha ao imagem do SSD</span><span class="sxs-lookup"><span data-stu-id="6bbfb-160">The tool fails to image the SSD</span></span> | <span data-ttu-id="6bbfb-161">Certifique-se de que você está usando um SSD fornecido por fábrica e um dos cabos testados.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-161">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="6bbfb-162">O processo de re-imagem aparece interrompido/congelado</span><span class="sxs-lookup"><span data-stu-id="6bbfb-162">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="6bbfb-163">É seguro fechar e reiniciar a Ferramenta de Recuperação do Surface Hub sem nenhum efeito no SSD.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-163">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="6bbfb-164">A unidade não é reconhecida pela ferramenta</span><span class="sxs-lookup"><span data-stu-id="6bbfb-164">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="6bbfb-165">Verifique se o SSD do Surface Hub está enumerado como uma unidade Lite-On, "LITEON L CH-128V2S USB Device".</span><span class="sxs-lookup"><span data-stu-id="6bbfb-165">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="6bbfb-166">Se a unidade for reconhecida como outro dispositivo nomeado, seu cabo atual não será compatível.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-166">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="6bbfb-167">Tente outro cabo ou um dos cabos testados listados acima.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-167">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="6bbfb-168">Erro: -2147024809</span><span class="sxs-lookup"><span data-stu-id="6bbfb-168">Error: -2147024809</span></span> | <span data-ttu-id="6bbfb-169">Abra o Gerenciador de Disco e remova as partições na unidade do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-169">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="6bbfb-170">Desconecte e reconecte a unidade ao computador host.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-170">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="6bbfb-171">Reinicie a ferramenta de imagem novamente.</span><span class="sxs-lookup"><span data-stu-id="6bbfb-171">Restart the imaging tool again.</span></span>

<span data-ttu-id="6bbfb-172">Se a ferramenta não tiver êxito na imagem da unidade, entre em contato com o [Suporte do Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="6bbfb-172">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="6bbfb-173">Histórico de versões</span><span class="sxs-lookup"><span data-stu-id="6bbfb-173">Version history</span></span>

### <span data-ttu-id="6bbfb-174">Versão v2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="6bbfb-174">Version v2.0.139.0</span></span>

*<span data-ttu-id="6bbfb-175">Data do lançamento: 18 de dezembro de 2020</span><span class="sxs-lookup"><span data-stu-id="6bbfb-175">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="6bbfb-176">Esta versão da Ferramenta de Recuperação do Surface Hub adiciona suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6bbfb-176">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="6bbfb-177">Atualização para dar suporte ao Windows 10 Team 2020 Update (20H2)</span><span class="sxs-lookup"><span data-stu-id="6bbfb-177">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="6bbfb-178">Melhorias na experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="6bbfb-178">User experience improvements</span></span>
- <span data-ttu-id="6bbfb-179">Alterações de arquitetura</span><span class="sxs-lookup"><span data-stu-id="6bbfb-179">Architectural changes</span></span>
- <span data-ttu-id="6bbfb-180">Adições de telemetria</span><span class="sxs-lookup"><span data-stu-id="6bbfb-180">Telemetry additions</span></span>

