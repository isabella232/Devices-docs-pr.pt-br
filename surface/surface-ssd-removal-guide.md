---
title: Remoção de SSD em dispositivos de superfície compatíveis
description: Este artigo, destinado a técnicos de ti qualificados, descreve as práticas recomendadas para a remoção e substituição do SSDs no laptop Surface 3, Surface Pro X e Surface laptop go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133166"
---
# <span data-ttu-id="c0628-103">Práticas recomendadas para remoção de SSD de dispositivos de superfície compatíveis</span><span class="sxs-lookup"><span data-stu-id="c0628-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0628-104">Este artigo destina-se a usar técnicos de ti qualificados apenas em uma organização corporativa.</span><span class="sxs-lookup"><span data-stu-id="c0628-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="c0628-105">Ele descreve as práticas recomendadas recomendadas para uso por técnicos de ti qualificados na remoção e substituição de SSDs nos seguintes dispositivos da superfície compatível:</span><span class="sxs-lookup"><span data-stu-id="c0628-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="c0628-106">Laptop Surface 3</span><span class="sxs-lookup"><span data-stu-id="c0628-106">Surface Laptop 3</span></span> 
- <span data-ttu-id="c0628-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="c0628-107">Surface Pro X</span></span> 
- <span data-ttu-id="c0628-108">Usar o laptop Surface</span><span class="sxs-lookup"><span data-stu-id="c0628-108">Surface Laptop Go</span></span>

> [!WARNING]
> <span data-ttu-id="c0628-109">Abrir dispositivos e substituir componentes de dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndios e riscos de ferimentos pessoais e outros riscos.</span><span class="sxs-lookup"><span data-stu-id="c0628-109">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="c0628-110">Use sempre um cuidado ao realizar tais atividades.</span><span class="sxs-lookup"><span data-stu-id="c0628-110">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="c0628-111">Siga as precauções e os procedimentos de segurança identificados no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="c0628-111">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="c0628-112">Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "guia de remoção do rSSD para empresas".</span><span class="sxs-lookup"><span data-stu-id="c0628-112">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="c0628-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c0628-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0628-114">Este artigo pressupõe que você compreenda as precauções gerais de segurança e as políticas de segurança e os procedimentos descritos no guia de remoção do rSSD para empresas.</span><span class="sxs-lookup"><span data-stu-id="c0628-114">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="c0628-115">Preparar a remoção do SSD</span><span class="sxs-lookup"><span data-stu-id="c0628-115">Prepare for SSD removal</span></span> 

### <span data-ttu-id="c0628-116">Instalar as atualizações mais recentes</span><span class="sxs-lookup"><span data-stu-id="c0628-116">Install the latest updates</span></span> 

<span data-ttu-id="c0628-117">Antes de começar, verifique se a sua versão do Windows tem as atualizações mais recentes instaladas:</span><span class="sxs-lookup"><span data-stu-id="c0628-117">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="c0628-118">Vá para **Iniciar**  >  **configurações**  >  **Atualizar & segurança**e selecione **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="c0628-118">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="c0628-119">Instale todas as atualizações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c0628-119">Install all available updates.</span></span>
3. <span data-ttu-id="c0628-120">Verifique as senhas necessárias para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0628-120">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="c0628-121">Gerenciar o BitLocker</span><span class="sxs-lookup"><span data-stu-id="c0628-121">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="c0628-122">Esta seção inclui recomendações para organizações que ativaram a criptografia BitLocker para discos rígidos.</span><span class="sxs-lookup"><span data-stu-id="c0628-122">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="c0628-123">Para obter mais informações, consulte  [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="c0628-123">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="c0628-124">Se a criptografia do BitLocker estiver desabilitada durante a remoção e a substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="c0628-124">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="c0628-125">Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:</span><span class="sxs-lookup"><span data-stu-id="c0628-125">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="c0628-126">Em **configurações**, digite **BitLocker** e, em seguida, selecione **gerenciar o BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="c0628-126">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="c0628-127">Selecione desativar **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="c0628-127">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="c0628-128">Desligue o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0628-128">Power down the device.</span></span> 

### <span data-ttu-id="c0628-129">Se a criptografia do BitLocker estiver habilitada durante a remoção e a substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="c0628-129">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="c0628-130">Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:</span><span class="sxs-lookup"><span data-stu-id="c0628-130">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="c0628-131">Em **configurações**, digite **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="c0628-131">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="c0628-132">Selecione **gerenciar o BitLocker**  > **gerar a chave de recuperação do BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="c0628-132">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="c0628-133">Insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="c0628-133">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="c0628-134">Salve a chave de recuperação em armazenamento USB.</span><span class="sxs-lookup"><span data-stu-id="c0628-134">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="c0628-135">Remova a unidade USB.</span><span class="sxs-lookup"><span data-stu-id="c0628-135">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="c0628-136">Desligue o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0628-136">Power down the device.</span></span> 

## <span data-ttu-id="c0628-137">Remover e substituir SSD</span><span class="sxs-lookup"><span data-stu-id="c0628-137">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="c0628-138">Remova a SSD usando as instruções no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="c0628-138">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="c0628-139">Coloque a SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão com a Internet com fio.</span><span class="sxs-lookup"><span data-stu-id="c0628-139">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="c0628-140">Ligue o novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0628-140">Power on the new device.</span></span> <span data-ttu-id="c0628-141">O dispositivo pode passar por uma atualização de firmware durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="c0628-141">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="c0628-142">Após remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="c0628-142">After SSD removal and replacement</span></span>

### <span data-ttu-id="c0628-143">Gerenciar SSDs não criptografados</span><span class="sxs-lookup"><span data-stu-id="c0628-143">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="c0628-144">Se a SSD não for criptografada durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c0628-144">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="c0628-145">Acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="c0628-145">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="c0628-146">Digite a senha e entre na conclusão pendente de autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="c0628-146">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="c0628-147">Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="c0628-147">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="c0628-148">Conecte-se novamente usando a senha e configure o Windows Hello e um PIN quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="c0628-148">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="c0628-149">Se o dispositivo tiver o BitLocker desabilitado para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, vá para **BitLocker**  >  **gerenciar BitLocker**  >  **retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="c0628-149">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="c0628-150">Execute o [Kit de ferramentas de diagnóstico do Surface da Microsoft para empresas](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0628-150">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="c0628-151">Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="c0628-151">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="c0628-152">Se você vir mensagens de erro, selecione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="c0628-152">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="c0628-153">Verifique a conta do Office abrindo o **aplicativo do Office**, navegue até **arquivo**  >  **conta** e verifique se há mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="c0628-153">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="c0628-154">Gerenciando o SSDs criptografado</span><span class="sxs-lookup"><span data-stu-id="c0628-154">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="c0628-155">Será necessário ter um segundo dispositivo para ler a chave de recuperação do BitLocker que foi salva na unidade USB.</span><span class="sxs-lookup"><span data-stu-id="c0628-155">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="c0628-156">Se a SSD for criptografada durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c0628-156">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="c0628-157">Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0628-157">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="c0628-158">Abra o arquivo. txt que contém a chave de recuperação do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="c0628-158">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="c0628-159">Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.</span><span class="sxs-lookup"><span data-stu-id="c0628-159">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="c0628-160">Depois de inserir a chave de recuperação do BitLocker com êxito, acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="c0628-160">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="c0628-161">Digite a senha e conecte-se à conclusão pendente da autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="c0628-161">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="c0628-162">Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="c0628-162">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="c0628-163">Entre novamente usando a senha e, em seguida, configure o Windows Hello e adicione um PIN.</span><span class="sxs-lookup"><span data-stu-id="c0628-163">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="c0628-164">Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para **configurações**  >  **BitLocker**  >  **gerenciar**BitLocker  >  **retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="c0628-164">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="c0628-165">Execute o **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0628-165">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="c0628-166">Para verificar a ativação do Windows, selecione ativação de **configurações**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="c0628-166">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="c0628-167">Se você vir mensagens de erro, selecione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="c0628-167">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="c0628-168">Para verificar o status da conta do Office, abra o **aplicativo do Office**e, em seguida, vá para a **File**  >  **conta** arquivo para verificar se há mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="c0628-168">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="c0628-169">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="c0628-169">Learn more</span></span>

- [<span data-ttu-id="c0628-170">Guia de remoção do rSSD para empresas</span><span class="sxs-lookup"><span data-stu-id="c0628-170">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="c0628-171">Guia de recuperação do BitLocker</span><span class="sxs-lookup"><span data-stu-id="c0628-171">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="c0628-172">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="c0628-172">Still need help?</span></span> <span data-ttu-id="c0628-173">Vá para [comunidade da Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c0628-173">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>