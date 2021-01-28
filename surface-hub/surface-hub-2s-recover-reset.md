---
title: Redefinir e recuperar para o Surface Hub 2S
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
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304804"
---
# <span data-ttu-id="e0cbc-104">Redefinir e recuperar para o Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="e0cbc-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="e0cbc-105">Se você tiver problemas com o Surface Hub 2S, poderá redefinir o dispositivo para as configurações de fábrica ou restaurá-lo usando uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="e0cbc-106">Para começar, entre no Surface Hub 2S com \*\*\*\* credenciais de administrador, abra o aplicativo Configurações, selecione **Atualizar**& segurança e, em seguida, selecione **Recuperação**.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="e0cbc-107">Redefina o dispositivo</span><span class="sxs-lookup"><span data-stu-id="e0cbc-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e0cbc-108">Verifique se sua chave do BitLocker está disponível antes de redefinir o dispositivo, pois ela será solicitado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="e0cbc-109">Para saber mais, confira [Salvar sua chave do BitLocker.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="e0cbc-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="e0cbc-110">Para redefinir o dispositivo, selecione **Começar.**</span><span class="sxs-lookup"><span data-stu-id="e0cbc-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="e0cbc-111">Quando a **janela Pronto para redefinir este dispositivo** for exibida, selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="e0cbc-112">Quando o Hub for reiniciado para a partição de recuperação, ele solicitará que você insira a chave do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="e0cbc-113">Ignorar esse prompt causará falha na redefinição.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="e0cbc-114">Depois de inserir a chave do BitLocker, o Hub reinstala o sistema operacional a partir da partição de recuperação.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="e0cbc-115">Isso pode levar até uma hora para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="e0cbc-116">Para reconfigurar o dispositivo, execute o programa de Instalação pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="e0cbc-117">Se você gerenciar o dispositivo usando o Microsoft Intune ou outra solução de gerenciamento de dispositivo móvel, retire e exclua o registro anterior e, em seguida, inscreva o novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="e0cbc-118">Para obter mais informações, consulte Remover dispositivos usando apagar, retirar ou [desemrollar manualmente o dispositivo.](https://docs.microsoft.com/intune/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="e0cbc-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Redefinir e recuperar para o Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="e0cbc-120">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-120">Figure 1.</span></span> <span data-ttu-id="e0cbc-121">Redefinir e recuperar para o Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="e0cbc-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="e0cbc-122">Recuperar o Surface Hub 2S usando uma unidade de recuperação USB</span><span class="sxs-lookup"><span data-stu-id="e0cbc-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="e0cbc-123">Novidade no Surface Hub 2S, agora você pode reinstalar o dispositivo usando uma imagem de recuperação.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="e0cbc-124">Recuperação de uma unidade USB</span><span class="sxs-lookup"><span data-stu-id="e0cbc-124">Recovery from a USB drive</span></span>

<span data-ttu-id="e0cbc-125">Usando o Surface Hub 2S, você pode reinstalar o dispositivo usando uma imagem de recuperação.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="e0cbc-126">Ao fazer isso, você pode reinstalar o dispositivo nas configurações de fábrica se tiver perdido a chave do BitLocker ou se não tiver mais credenciais de administrador para o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="e0cbc-127">Use uma unidade USB 3.0 com 8 GB ou 16 GB de armazenamento, formatada como FAT32.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="e0cbc-128">Em um computador separado, baixe a imagem de recuperação de arquivo .zip do [site do Surface Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) e retorne a essas instruções.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="e0cbc-129">Descompar o arquivo baixado na raiz da unidade USB.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-129">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="e0cbc-130">Conecte a unidade USB a qualquer porta USB-C ou USB-A no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-130">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="e0cbc-131">Desligue o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="e0cbc-131">Turn off the device:</span></span>

   1. <span data-ttu-id="e0cbc-132">Enquanto pressiona o botão Aumentar o volume para baixo, pressione o botão Ligar/Desligar.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-132">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="e0cbc-133">Continue pressionando os dois botões até ver o logotipo do Windows.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-133">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="e0cbc-134">Solte o botão Ligar/Desligar, mas continue a manter o botão De volume para baixo até que a interface do usuário de instalação comece.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-134">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Use botões de baixo volume e ligar/desligar para iniciar a recuperação*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="e0cbc-136">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-136">Figure 2.</span></span> <span data-ttu-id="e0cbc-137">Botões De Volume e Ligar/Desligar</span><span class="sxs-lookup"><span data-stu-id="e0cbc-137">Volume and Power buttons</span></span>*

1. <span data-ttu-id="e0cbc-138">Na tela de seleção de idioma, selecione o idioma de exibição do Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-138">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="e0cbc-139">Selecione **Recuperar de uma unidade,** limpe totalmente a **unidade**e, em seguida, **selecione Recuperar.**</span><span class="sxs-lookup"><span data-stu-id="e0cbc-139">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="e0cbc-140">Se você for solicitado a solicitar uma chave do BitLocker, selecione **Ignorar esta unidade.**</span><span class="sxs-lookup"><span data-stu-id="e0cbc-140">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="e0cbc-141">O Surface Hub 2S reinicia várias vezes e leva aproximadamente 30 minutos para concluir o processo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-141">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="e0cbc-142">Quando a tela de instalação pela primeira vez for exibida, remova a unidade USB.</span><span class="sxs-lookup"><span data-stu-id="e0cbc-142">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="e0cbc-143">Contate o Suporte</span><span class="sxs-lookup"><span data-stu-id="e0cbc-143">Contact Support</span></span>

<span data-ttu-id="e0cbc-144">Se você tiver dúvidas ou precisar de ajuda, poderá [criar uma solicitação de suporte.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="e0cbc-144">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
