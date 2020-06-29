---
title: Redefinição e recuperação para Surface Hub 2S
description: Saiba como recuperar e redefinir o Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830431"
---
# <span data-ttu-id="278e7-104">Redefinição e recuperação para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="278e7-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="278e7-105">Se você encontrar problemas com o Surface Hub 2S, pode redefinir o dispositivo para configurações de fábrica ou restaurar usando uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="278e7-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="278e7-106">Para começar, entre no Surface Hub 2S com as credenciais de administrador, abra o aplicativo **configurações** , selecione **Atualizar & segurança**e, em seguida, selecione **recuperação**.</span><span class="sxs-lookup"><span data-stu-id="278e7-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="278e7-107">Redefinir o dispositivo</span><span class="sxs-lookup"><span data-stu-id="278e7-107">Reset the device</span></span>

1. <span data-ttu-id="278e7-108">Para redefinir o dispositivo **, selecione começar**.</span><span class="sxs-lookup"><span data-stu-id="278e7-108">To reset the device, select **Get Started**.</span></span>
2. <span data-ttu-id="278e7-109">Quando a janela **pronto para redefinir este dispositivo** for exibida, selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="278e7-109">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
  >[!NOTE]
  ><span data-ttu-id="278e7-110">Surface Hub 2S reinstala o sistema operacional da partição de recuperação.</span><span class="sxs-lookup"><span data-stu-id="278e7-110">Surface Hub 2S reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="278e7-111">Isso pode levar até uma hora para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="278e7-111">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="278e7-112">Para reconfigurar o dispositivo, execute o programa de instalação pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="278e7-112">To reconfigure the device, run the first-time Setup program.</span></span>
4. <span data-ttu-id="278e7-113">Se você gerenciar o dispositivo usando o Microsoft Intune ou outra solução de gerenciamento de dispositivo móvel, desative e exclua o registro anterior e, em seguida, registre novamente o novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="278e7-113">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="278e7-114">Para obter mais informações, consulte [remover dispositivos usando apagar, desativar ou cancelar o registro manual do dispositivo](https://docs.microsoft.com/intune/devices-wipe).</span><span class="sxs-lookup"><span data-stu-id="278e7-114">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

![\* Redefinição e recuperação para Surface Hub 2S \*](images/sh2-reset.png)<br>
*<span data-ttu-id="278e7-116">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="278e7-116">Figure 1.</span></span> <span data-ttu-id="278e7-117">Redefinição e recuperação para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="278e7-117">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="278e7-118">Recuperar o Surface Hub 2S usando uma unidade de recuperação USB</span><span class="sxs-lookup"><span data-stu-id="278e7-118">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="278e7-119">Novo no Surface Hub 2S, agora você pode reinstalar o dispositivo usando uma imagem de recuperação.</span><span class="sxs-lookup"><span data-stu-id="278e7-119">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="278e7-120">Recuperação de uma unidade USB</span><span class="sxs-lookup"><span data-stu-id="278e7-120">Recovery from a USB drive</span></span>

<span data-ttu-id="278e7-121">Usando o Surface Hub 2S, você pode reinstalar o dispositivo usando uma imagem de recuperação.</span><span class="sxs-lookup"><span data-stu-id="278e7-121">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="278e7-122">Ao fazer isso, você pode reinstalar o dispositivo nas configurações de fábrica se perdeu a chave do BitLocker ou se não tiver mais as credenciais de administrador para o aplicativo configurações.</span><span class="sxs-lookup"><span data-stu-id="278e7-122">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="278e7-123">Use uma unidade USB 3,0 com 8 GB ou 16 GB de armazenamento, formatada como FAT32.</span><span class="sxs-lookup"><span data-stu-id="278e7-123">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="278e7-124">Em um computador separado, baixe a imagem de recuperação de arquivo. zip do [site de recuperação de superfície](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) e, em seguida, retorne a estas instruções.</span><span class="sxs-lookup"><span data-stu-id="278e7-124">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 
1. <span data-ttu-id="278e7-125">Descompacte o arquivo baixado na raiz da unidade USB.</span><span class="sxs-lookup"><span data-stu-id="278e7-125">Unzip the downloaded file onto the root of the USB drive.</span></span>  
1. <span data-ttu-id="278e7-126">Conecte a unidade USB a qualquer porta USB-C ou USB-A no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="278e7-126">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>
1. <span data-ttu-id="278e7-127">Desative o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="278e7-127">Turn off the device:</span></span>
   1. <span data-ttu-id="278e7-128">Mantenha pressionado o botão baixo volume, pressione o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="278e7-128">While holding down the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="278e7-129">Mantenha os dois botões pressionados até ver o logotipo do Windows.</span><span class="sxs-lookup"><span data-stu-id="278e7-129">Keep holding both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="278e7-130">Solte o botão de energia, mas continue a manter o volume até que a interface do usuário de instalação comece.</span><span class="sxs-lookup"><span data-stu-id="278e7-130">Release the Power button but continue to hold the Volume until the Install UI begins.</span></span>

    ![\* Use os botões baixo de volume e energia para iniciar a recuperação \*](images/sh2-keypad.png) <br>
   **<span data-ttu-id="278e7-132">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="278e7-132">Figure 2.</span></span> <span data-ttu-id="278e7-133">Botões de volume e energia</span><span class="sxs-lookup"><span data-stu-id="278e7-133">Volume and Power buttons</span></span>**

1. <span data-ttu-id="278e7-134">Na tela seleção de idioma, selecione o idioma de exibição do Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="278e7-134">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>
1. <span data-ttu-id="278e7-135">Selecione **recuperar de uma unidade** e **limpe completamente a unidade**e, em seguida, selecione **recuperar**.</span><span class="sxs-lookup"><span data-stu-id="278e7-135">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="278e7-136">Se você for solicitado a fornecer uma chave BitLocker, selecione **ignorar esta unidade**.</span><span class="sxs-lookup"><span data-stu-id="278e7-136">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="278e7-137">O Surface Hub 2S é reinicializado várias vezes e leva aproximadamente 30 minutos para concluir o processo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="278e7-137">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="278e7-138">Quando a tela instalação inicial for exibida, remova a unidade USB.</span><span class="sxs-lookup"><span data-stu-id="278e7-138">When the first-time setup screen appears,remove the USB drive.</span></span>

## <span data-ttu-id="278e7-139">Contatar o Suporte</span><span class="sxs-lookup"><span data-stu-id="278e7-139">Contact Support</span></span>

<span data-ttu-id="278e7-140">Se tiver dúvidas ou precisar de ajuda, você pode [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="278e7-140">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
