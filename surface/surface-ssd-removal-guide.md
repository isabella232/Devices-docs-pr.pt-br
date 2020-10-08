---
title: Remoção de SSD em dispositivos de superfície compatíveis
description: Como transferir uma SSD de um dispositivo de superfície para outro.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 00109e4e1bb3873fc2914b2044f58e6fa3b6c211
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104803"
---
# <span data-ttu-id="11788-103">Práticas recomendadas para remoção de SSD de dispositivos de superfície compatíveis</span><span class="sxs-lookup"><span data-stu-id="11788-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11788-104">Este artigo destina-se a usar técnicos de ti qualificados apenas em uma organização corporativa.</span><span class="sxs-lookup"><span data-stu-id="11788-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="11788-105">Ele descreve as práticas recomendadas recomendadas para uso por técnicos de ti qualificados na remoção e substituição de SSDs no laptop de Surface 3 ou Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="11788-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in Surface Laptop 3 or Surface Pro X only.</span></span> 

> [!WARNING]
> <span data-ttu-id="11788-106">Abrir dispositivos e substituir componentes de dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndios e riscos de ferimentos pessoais e outros riscos.</span><span class="sxs-lookup"><span data-stu-id="11788-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="11788-107">Use sempre um cuidado ao realizar tais atividades.</span><span class="sxs-lookup"><span data-stu-id="11788-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="11788-108">Siga as precauções e os procedimentos de segurança identificados no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="11788-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="11788-109">Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "guia de remoção do rSSD para empresas".</span><span class="sxs-lookup"><span data-stu-id="11788-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="11788-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="11788-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11788-111">Este artigo pressupõe que você compreenda as precauções gerais de segurança e as políticas de segurança e os procedimentos descritos no guia de remoção do rSSD para empresas.</span><span class="sxs-lookup"><span data-stu-id="11788-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="11788-112">Preparar a remoção do SSD</span><span class="sxs-lookup"><span data-stu-id="11788-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="11788-113">Instalar as atualizações mais recentes</span><span class="sxs-lookup"><span data-stu-id="11788-113">Install the latest updates</span></span> 

<span data-ttu-id="11788-114">Antes de começar, verifique se a sua versão do Windows tem as atualizações mais recentes em atualização:</span><span class="sxs-lookup"><span data-stu-id="11788-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="11788-115">Vá para **Iniciar**  >  **configurações**  >  **Atualizar & segurança**e selecione **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="11788-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="11788-116">Instale todas as atualizações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="11788-116">Install all available updates.</span></span> 
2. <span data-ttu-id="11788-117">Instale todas as atualizações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="11788-117">Install all available updates.</span></span>
3. <span data-ttu-id="11788-118">Verifique se você tem senhas necessárias para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11788-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="11788-119">Gerenciar o BitLocker</span><span class="sxs-lookup"><span data-stu-id="11788-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="11788-120">Esta seção inclui recomendações para organizações que ativaram a criptografia BitLocker para discos rígidos.</span><span class="sxs-lookup"><span data-stu-id="11788-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="11788-121">Para obter mais informações, consulte o [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="11788-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="11788-122">Se a criptografia do BitLocker estiver desabilitada durante a remoção e a substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="11788-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="11788-123">Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:</span><span class="sxs-lookup"><span data-stu-id="11788-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="11788-124">Em **configurações**, digite **BitLocker**e, em seguida, selecione **gerenciar o BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="11788-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="11788-125">Selecione desativar **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="11788-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="11788-126">Desligue o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11788-126">Power down the device.</span></span> 

### <span data-ttu-id="11788-127">Se a criptografia do BitLocker estiver habilitada durante a remoção e a substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="11788-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="11788-128">Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:</span><span class="sxs-lookup"><span data-stu-id="11788-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="11788-129">Em **configurações**, digite **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="11788-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="11788-130">Selecione **gerenciar o BitLocker**  > **gerar a chave de recuperação do BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="11788-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="11788-131">Insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="11788-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="11788-132">Salve a chave de recuperação em armazenamento USB.</span><span class="sxs-lookup"><span data-stu-id="11788-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="11788-133">Remova a unidade USB.</span><span class="sxs-lookup"><span data-stu-id="11788-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="11788-134">Desligue o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11788-134">Power down the device.</span></span> 

## <span data-ttu-id="11788-135">Remover e substituir a SSD</span><span class="sxs-lookup"><span data-stu-id="11788-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="11788-136">Remova a SSD usando as instruções no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="11788-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="11788-137">Coloque a SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão com a Internet com fio.</span><span class="sxs-lookup"><span data-stu-id="11788-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="11788-138">Ligue o novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11788-138">Power on the new device.</span></span> <span data-ttu-id="11788-139">O dispositivo pode passar por uma atualização de firmware durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="11788-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="11788-140">Após remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="11788-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="11788-141">Gerenciar SSDs não criptografados</span><span class="sxs-lookup"><span data-stu-id="11788-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="11788-142">Se a SSD permanecer sem criptografia durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="11788-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="11788-143">Acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="11788-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="11788-144">Digite a senha e entre na conclusão pendente da autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="11788-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="11788-145">Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="11788-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="11788-146">Entre novamente usando a senha e configure o Windows Hello e um PIN quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="11788-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="11788-147">Se o dispositivo tiver o BitLocker desabilitado para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, vá para **BitLocker**  >  **gerenciar BitLocker**  >  **retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="11788-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="11788-148">Execute o kit de ferramentas de diagnóstico do Surface da Microsoft para empresas (SDT) para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11788-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="11788-149">Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="11788-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="11788-150">Se você vir mensagens de erro, selecione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="11788-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="11788-151">Verifique a conta do Office abrindo o **aplicativo do Office**, navegue até **arquivo**  >  **conta** e verifique se há mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="11788-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="11788-152">Gerenciando o SSDs criptografado</span><span class="sxs-lookup"><span data-stu-id="11788-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="11788-153">Será necessário ter um segundo dispositivo para ler a chave de recuperação do BitLocker que foi salva na unidade USB.</span><span class="sxs-lookup"><span data-stu-id="11788-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="11788-154">Se a SSD permanecia criptografada durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="11788-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="11788-155">Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11788-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="11788-156">Abra o arquivo. txt que contém a chave de recuperação do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="11788-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="11788-157">Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.</span><span class="sxs-lookup"><span data-stu-id="11788-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="11788-158">Depois de inserir a chave de recuperação do BitLocker com êxito, acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="11788-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="11788-159">Digite a senha e conecte-se à conclusão pendente da autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="11788-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="11788-160">Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.</span><span class="sxs-lookup"><span data-stu-id="11788-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="11788-161">Entre novamente usando a senha e, em seguida, configure o Windows Hello e adicione um PIN.</span><span class="sxs-lookup"><span data-stu-id="11788-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="11788-162">Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para **configurações**  >  **BitLocker**  >  **gerenciar**BitLocker  >  **retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="11788-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="11788-163">Execute o **SDT** para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11788-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="11788-164">Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="11788-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="11788-165">Se você vir mensagens de erro, selecione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="11788-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="11788-166">Para verificar o status da conta do Office, abra o **aplicativo do Office**e, em seguida, vá para a **File**  >  **conta** arquivo para verificar se há mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="11788-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="11788-167">Mais informações</span><span class="sxs-lookup"><span data-stu-id="11788-167">More information</span></span> 

<span data-ttu-id="11788-168">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="11788-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="11788-169">Guia de remoção do rSSD para empresas</span><span class="sxs-lookup"><span data-stu-id="11788-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="11788-170">Guia de recuperação do BitLocker</span><span class="sxs-lookup"><span data-stu-id="11788-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="11788-171">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="11788-171">Still need help?</span></span> <span data-ttu-id="11788-172">Vá para [comunidade da Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="11788-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>