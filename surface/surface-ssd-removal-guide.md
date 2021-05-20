---
title: Remoção de SSD em dispositivos Surface compatíveis
description: Este artigo, destinado a técnicos de IT qualificados, descreve as práticas recomendadas para a remoção e substituição de SSDs no Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X e Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576901"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a><span data-ttu-id="74513-103">Práticas recomendadas para remoção de SSD de dispositivos Surface compatíveis</span><span class="sxs-lookup"><span data-stu-id="74513-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74513-104">Este artigo destina-se apenas a ser usado por técnicos de IT qualificados em uma organização corporativa.</span><span class="sxs-lookup"><span data-stu-id="74513-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="74513-105">Ele descreve as práticas recomendadas recomendadas para uso por técnicos de IT qualificados na remoção e substituição de SSDs nos seguintes dispositivos Surface compatíveis:</span><span class="sxs-lookup"><span data-stu-id="74513-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="74513-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="74513-106">Surface Pro 7+</span></span>
- <span data-ttu-id="74513-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="74513-107">Surface Pro X</span></span>
- <span data-ttu-id="74513-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="74513-108">Surface Laptop Go</span></span>
- <span data-ttu-id="74513-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="74513-109">Surface Laptop 3</span></span>
- <span data-ttu-id="74513-110">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="74513-110">Surface Laptop 4</span></span>

> [!WARNING]
> <span data-ttu-id="74513-111">Abrir dispositivos e substituir componentes do dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndio e riscos de danos pessoais e outros riscos.</span><span class="sxs-lookup"><span data-stu-id="74513-111">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="74513-112">Sempre use cuidado ao realizar essas atividades.</span><span class="sxs-lookup"><span data-stu-id="74513-112">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="74513-113">Siga as precauções e os procedimentos de segurança identificados no Guia de Remoção [do rSSD para Enterprise](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="74513-113">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="74513-114">Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "Guia de Remoção do rSSD para Enterprise".</span><span class="sxs-lookup"><span data-stu-id="74513-114">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prerequisites"></a><span data-ttu-id="74513-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="74513-115">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74513-116">Este artigo pressupôs que você compreende as políticas e procedimentos gerais de segurança e precauções de segurança descritos no "Guia de Remoção do rSSD para Enterprise".</span><span class="sxs-lookup"><span data-stu-id="74513-116">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prepare-for-ssd-removal"></a><span data-ttu-id="74513-117">Preparar para remoção do SSD</span><span class="sxs-lookup"><span data-stu-id="74513-117">Prepare for SSD removal</span></span> 

### <a name="install-the-latest-updates"></a><span data-ttu-id="74513-118">Instalar as atualizações mais recentes</span><span class="sxs-lookup"><span data-stu-id="74513-118">Install the latest updates</span></span> 

<span data-ttu-id="74513-119">Antes de começar, certifique-se de que sua versão do Windows tenha as atualizações mais recentes instaladas:</span><span class="sxs-lookup"><span data-stu-id="74513-119">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="74513-120">Vá para **Iniciar**  >  **Configurações**  >  **Atualização & Segurança**e selecione Verificar se há **atualizações**.</span><span class="sxs-lookup"><span data-stu-id="74513-120">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="74513-121">Instale todas as atualizações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="74513-121">Install all available updates.</span></span>
3. <span data-ttu-id="74513-122">Verifique as senhas necessárias para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74513-122">Verify any passwords that are necessary to access the device.</span></span>  
 
## <a name="manage-bitlocker"></a><span data-ttu-id="74513-123">Gerenciar o BitLocker</span><span class="sxs-lookup"><span data-stu-id="74513-123">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="74513-124">Esta seção inclui recomendações para organizações que tenham habilitado BitLocker criptografia para discos rígidos.</span><span class="sxs-lookup"><span data-stu-id="74513-124">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="74513-125">Para obter mais informações, [consulte BitLocker Guia de Recuperação.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="74513-125">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="74513-126">Se BitLocker criptografia for desabilitada durante a remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="74513-126">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="74513-127">Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar BitLocker:</span><span class="sxs-lookup"><span data-stu-id="74513-127">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="74513-128">Em **Configurações**, digite **BitLocker** e selecione **Gerenciar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="74513-128">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="74513-129">Selecione **Desativar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="74513-129">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="74513-130">Alimente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74513-130">Power down the device.</span></span> 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="74513-131">Se BitLocker criptografia estiver habilitada durante a remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="74513-131">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="74513-132">Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave BitLocker de recuperação e salvá-lo no armazenamento USB:</span><span class="sxs-lookup"><span data-stu-id="74513-132">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="74513-133">Em **Configurações,** digite **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="74513-133">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="74513-134">Selecione **Gerenciar BitLocker**Gerar BitLocker Chave de  > **Recuperação**.</span><span class="sxs-lookup"><span data-stu-id="74513-134">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="74513-135">Insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="74513-135">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="74513-136">Salve a chave de recuperação no armazenamento USB.</span><span class="sxs-lookup"><span data-stu-id="74513-136">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="74513-137">Remova a unidade USB.</span><span class="sxs-lookup"><span data-stu-id="74513-137">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="74513-138">Alimente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74513-138">Power down the device.</span></span> 

## <a name="remove-and-replace-ssd"></a><span data-ttu-id="74513-139">Remover e substituir SSD</span><span class="sxs-lookup"><span data-stu-id="74513-139">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="74513-140">Remova o SSD usando as instruções apropriadas para seu dispositivo incluído no Guia de Remoção [do rSSD para](https://www.microsoft.com/download/100440)Enterprise .</span><span class="sxs-lookup"><span data-stu-id="74513-140">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="74513-141">Coloque o SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão de internet com fio.</span><span class="sxs-lookup"><span data-stu-id="74513-141">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="74513-142">Power on the new device.</span><span class="sxs-lookup"><span data-stu-id="74513-142">Power on the new device.</span></span> <span data-ttu-id="74513-143">O dispositivo pode passar por uma atualização de firmware durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="74513-143">The device may go through a firmware update during startup.</span></span>  
 
## <a name="after-ssd-removal-and-replacement"></a><span data-ttu-id="74513-144">Após a remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="74513-144">After SSD removal and replacement</span></span>

### <a name="manage-unencrypted-ssds"></a><span data-ttu-id="74513-145">Gerenciar SSDs não criptografados</span><span class="sxs-lookup"><span data-stu-id="74513-145">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="74513-146">Se o SSD for descriptografado durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="74513-146">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="74513-147">Vá para **Senha de Opções de**  >  **Login** (representado pelo ícone da chave no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="74513-147">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="74513-148">Insira a senha e entre aguardando a conclusão da autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="74513-148">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="74513-149">Depois de entrar totalmente, vá para **Iniciar**a Saída  >  \*\*\*\*  >  **da Conta**.</span><span class="sxs-lookup"><span data-stu-id="74513-149">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="74513-150">Entre novamente usando a senha e configurar o Windows Hello e um PIN quando você for solicitado.</span><span class="sxs-lookup"><span data-stu-id="74513-150">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="74513-151">Se o dispositivo foi BitLocker desabilitado para facilitar a remoção e a substituição do SSD e você deseja habilitar o BitLocker após a substituição, vá para **BitLocker Gerenciar**BitLocker  >  \*\*\*\*  >  **Retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="74513-151">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="74513-152">Execute o [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74513-152">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="74513-153">Verifique se Windows ativação navegando para **Configurações**  >  **Ativação**.</span><span class="sxs-lookup"><span data-stu-id="74513-153">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="74513-154">Se você vir mensagens de erro, selecione **Solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="74513-154">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="74513-155">Verifique a Office ao abrir o aplicativo **Office,** navegue até **Conta**de Arquivo e verifique se há mensagens  >  \*\*\*\* de erro.</span><span class="sxs-lookup"><span data-stu-id="74513-155">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <a name="managing-encrypted-ssds"></a><span data-ttu-id="74513-156">Gerenciando SSDs criptografados</span><span class="sxs-lookup"><span data-stu-id="74513-156">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="74513-157">Você terá que ter um segundo dispositivo para ler a chave de recuperação BitLocker que foi salva na unidade USB.</span><span class="sxs-lookup"><span data-stu-id="74513-157">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="74513-158">Se o SSD for criptografado durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="74513-158">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="74513-159">Insira a unidade USB que contém a chave BitLocker de recuperação no segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74513-159">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="74513-160">Abra o .txt que contém a chave de recuperação Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="74513-160">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="74513-161">Insira manualmente a BitLocker chave de recuperação no novo dispositivo que contém o SSD original.</span><span class="sxs-lookup"><span data-stu-id="74513-161">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="74513-162">Depois de ter inserido com êxito a BitLocker de recuperação, vá para **Senha**de Opções de Entrada (representada pelo ícone de tecla  >  \*\*\*\* no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="74513-162">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="74513-163">Insira a senha e entre, aguardando a conclusão da autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="74513-163">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="74513-164">Depois de entrar totalmente, vá para **Iniciar**a Saída  >  \*\*\*\*  >  **da Conta**.</span><span class="sxs-lookup"><span data-stu-id="74513-164">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="74513-165">Entre novamente usando a senha e, em seguida, configurar Windows Hello e adicionar um PIN.</span><span class="sxs-lookup"><span data-stu-id="74513-165">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="74513-166">Se o dispositivo foi BitLocker desabilitado para facilitar a remoção e a substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para **Configurações**  >  **BitLocker**  >  **Gerenciar**BitLocker  >  **Retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="74513-166">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="74513-167">Execute **[o SDT](surface-diagnostic-toolkit-for-business-intro.md)** para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74513-167">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="74513-168">Para verificar Windows ativação, selecione **Configurações**  >  **Ativação**.</span><span class="sxs-lookup"><span data-stu-id="74513-168">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="74513-169">Se você vir mensagens de erro, selecione **Solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="74513-169">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="74513-170">Para verificar o status da conta Office, abra o aplicativo Office **,** em seguida, vá para **Conta**de Arquivo para verificar se há mensagens  >  \*\*\*\* de erro.</span><span class="sxs-lookup"><span data-stu-id="74513-170">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <a name="learn-more"></a><span data-ttu-id="74513-171">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="74513-171">Learn more</span></span>

- [<span data-ttu-id="74513-172">Guia de Remoção do rSSD para Enterprise</span><span class="sxs-lookup"><span data-stu-id="74513-172">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="74513-173">Guia de recuperação do BitLocker</span><span class="sxs-lookup"><span data-stu-id="74513-173">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="74513-174">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="74513-174">Still need help?</span></span> <span data-ttu-id="74513-175">Vá para [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="74513-175">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>