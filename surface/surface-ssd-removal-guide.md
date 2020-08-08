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
ms.date: 8/7/2020
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
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918942"
---
# <span data-ttu-id="3637d-103">Práticas recomendadas para remoção do SSD em dispositivos de superfície compatíveis</span><span class="sxs-lookup"><span data-stu-id="3637d-103">Best practices for SSD removal in compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3637d-104">Este artigo destina-se a usar técnicos de ti qualificados apenas em uma organização corporativa.</span><span class="sxs-lookup"><span data-stu-id="3637d-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="3637d-105">Ele descreve as práticas recomendadas a serem usadas por técnicos de ti qualificados ao remover e substituir o SSDs em dispositivos de superfície com SSDs removível.</span><span class="sxs-lookup"><span data-stu-id="3637d-105">It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="3637d-106">Abrir dispositivos e substituir componentes de dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndios e riscos de ferimentos pessoais e outros riscos.</span><span class="sxs-lookup"><span data-stu-id="3637d-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="3637d-107">Sempre use cuidado ao realizar tais atividades.</span><span class="sxs-lookup"><span data-stu-id="3637d-107">Always use caution when undertaking such activities.</span></span> <span data-ttu-id="3637d-108">Siga as precauções de segurança e os procedimentos identificados no guia de remoção do rSSD para empresas.</span><span class="sxs-lookup"><span data-stu-id="3637d-108">Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise.</span></span> <span data-ttu-id="3637d-109">A Microsoft recomenda que você busque assistência profissional se não conseguir seguir as precauções e os procedimentos de segurança especificados no guia de remoção do rSSD para empresas.</span><span class="sxs-lookup"><span data-stu-id="3637d-109">Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise.</span></span> 

## <span data-ttu-id="3637d-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3637d-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3637d-111">Este artigo pressupõe que você compreenda as precauções gerais de segurança e os procedimentos e políticas de segurança descritos no [Guia de remoção rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="3637d-111">This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span>

## <span data-ttu-id="3637d-112">Preparar a remoção do SSD</span><span class="sxs-lookup"><span data-stu-id="3637d-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="3637d-113">Instalar as atualizações mais recentes</span><span class="sxs-lookup"><span data-stu-id="3637d-113">Install the latest updates</span></span> 

<span data-ttu-id="3637d-114">Antes de começar, verifique se a sua versão do Windows tem as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="3637d-114">Before you begin, make sure your version of Windows has the latest updates.</span></span>

1.  <span data-ttu-id="3637d-115">Vá para **Iniciar**  >  **configurações**  >  **Atualizar & segurança** e selecione **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="3637d-115">Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**.</span></span> <span data-ttu-id="3637d-116">Instale todas as atualizações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3637d-116">Install all available updates.</span></span>  

2.  <span data-ttu-id="3637d-117">Confirme se você tem qualquer senha necessária para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3637d-117">Confirm that you have any passwords needed to access the device.</span></span>  
 
## <span data-ttu-id="3637d-118">Gerenciar o BitLocker</span><span class="sxs-lookup"><span data-stu-id="3637d-118">Manage Bitlocker</span></span> 

> [!NOTE]
> <span data-ttu-id="3637d-119">Esta seção inclui recomendações para organizações que ativaram a criptografia BitLocker para discos rígidos.</span><span class="sxs-lookup"><span data-stu-id="3637d-119">This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives.</span></span> <span data-ttu-id="3637d-120">Para obter mais informações, consulte o [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="3637d-120">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="3637d-121">Se a criptografia do BitLocker estiver desabilitada durante a remoção e a substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="3637d-121">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="3637d-122">Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:</span><span class="sxs-lookup"><span data-stu-id="3637d-122">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="3637d-123">Em **configurações**, digite **BitLocker** e selecione **gerenciar o BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3637d-123">In **Settings**, type **Bitlocker** and select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="3637d-124">Selecione desativar **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3637d-124">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="3637d-125">Desligue o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3637d-125">Power down the device.</span></span> 

### <span data-ttu-id="3637d-126">Se a criptografia do BitLocker estiver habilitada durante a remoção e a substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="3637d-126">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="3637d-127">Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:</span><span class="sxs-lookup"><span data-stu-id="3637d-127">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="3637d-128">Vá para **configurações** e digite **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3637d-128">Go to **Settings** and type **Bitlocker**.</span></span>
2. <span data-ttu-id="3637d-129">Selecione **gerenciar o BitLocker**  > **gerar a chave de recuperação do BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3637d-129">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="3637d-130">Insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="3637d-130">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="3637d-131">Salve a chave de recuperação em armazenamento USB.</span><span class="sxs-lookup"><span data-stu-id="3637d-131">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="3637d-132">Remova a unidade USB.</span><span class="sxs-lookup"><span data-stu-id="3637d-132">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="3637d-133">Desligue o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3637d-133">Power down the device.</span></span> 

## <span data-ttu-id="3637d-134">Remover e substituir a SSD</span><span class="sxs-lookup"><span data-stu-id="3637d-134">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="3637d-135">Remova a SSD usando as instruções no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="3637d-135">Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="3637d-136">Coloque a SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão com a Internet com fio.</span><span class="sxs-lookup"><span data-stu-id="3637d-136">Place the original SSD in a new device and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="3637d-137">Ligue o novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3637d-137">Power on the new device.</span></span> <span data-ttu-id="3637d-138">O dispositivo pode passar por uma atualização de firmware durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="3637d-138">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="3637d-139">Após remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="3637d-139">After SSD removal and replacement</span></span>

### <span data-ttu-id="3637d-140">Gerenciar SSDs não criptografados</span><span class="sxs-lookup"><span data-stu-id="3637d-140">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="3637d-141">Se a SSD permanecer sem criptografia durante a transferência, conclua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3637d-141">If the SSD remains unencrypted during the transfer, complete the following:</span></span> 

1.  <span data-ttu-id="3637d-142">Acesse a senha de **Opções de entrada**  >  **Password** (representada como o ícone de chave no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="3637d-142">Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).</span></span>  
2.  <span data-ttu-id="3637d-143">Digite a senha e entre na conclusão pendente de autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="3637d-143">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="3637d-144">Uma vez conectado completamente, acesse **Iniciar**  >  **conta**  >  **sair**.</span><span class="sxs-lookup"><span data-stu-id="3637d-144">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="3637d-145">Conecte-se novamente com a senha e configure o Windows Hello e um PIN quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="3637d-145">Sign back in with the password and set up Windows Hello and a PIN when prompted.</span></span> 
    - <span data-ttu-id="3637d-146">Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, vá para **BitLocker**  >  **gerenciar BitLocker**  >  **retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3637d-146">If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="3637d-147">Execute **SDT** para confirmar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3637d-147">Run **SDT** to confirm full device functionality.</span></span>  
7.  <span data-ttu-id="3637d-148">Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="3637d-148">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="3637d-149">Se houver mensagens de erro, selecione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="3637d-149">If there are any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="3637d-150">Verifique a conta do Office abrindo o **aplicativo do Office**e, em seguida, navegue até **arquivo**  >  **conta** e verifique se há mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="3637d-150">Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.</span></span>  

### <span data-ttu-id="3637d-151">Gerenciando o SSDs criptografado</span><span class="sxs-lookup"><span data-stu-id="3637d-151">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="3637d-152">Será necessário um segundo dispositivo para ler a chave de recuperação do BitLocker que foi salva na unidade USB.</span><span class="sxs-lookup"><span data-stu-id="3637d-152">You will need a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="3637d-153">Se a SSD permanecia criptografada durante a transferência, conclua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3637d-153">If the SSD remained encrypted during the transfer, complete the following:</span></span>

1.  <span data-ttu-id="3637d-154">Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3637d-154">Insert the USB drive containing the Bitlocker Recovery key into the second device.</span></span> 
2.  <span data-ttu-id="3637d-155">Abra o arquivo. txt que contém a chave de recuperação do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="3637d-155">Open the .txt file containing the Bitlocker Recovery key.</span></span> 
3.  <span data-ttu-id="3637d-156">Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.</span><span class="sxs-lookup"><span data-stu-id="3637d-156">Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="3637d-157">Depois de inserir a chave de recuperação do BitLocker com êxito, acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="3637d-157">After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="3637d-158">Digite a senha e conecte-se à conclusão pendente da autenticação de dois fatores (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="3637d-158">Enter the password and sign in, pending completion of two-factor authentication (if applicable)</span></span> 
6.  <span data-ttu-id="3637d-159">Uma vez conectado completamente, acesse **Iniciar**  >  **conta**  >  **sair**.</span><span class="sxs-lookup"><span data-stu-id="3637d-159">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="3637d-160">Entre novamente com a senha e configure o Windows Hello e adicione um PIN.</span><span class="sxs-lookup"><span data-stu-id="3637d-160">Sign back in with the password and set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="3637d-161">Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, acesse **configurações**  >  **BitLocker**  >  **gerenciar**BitLocker  >  **retomar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3637d-161">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="3637d-162">Execute **SDT** para confirmar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3637d-162">Run **SDT** to confirm full device functionality.</span></span>  
10. <span data-ttu-id="3637d-163">Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="3637d-163">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="3637d-164">Se houver mensagens de erro, selecione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="3637d-164">If there are any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="3637d-165">Para verificar a conta do Office, abra o **aplicativo do Office**e, em seguida, vá para a conta de **arquivo**  >  **Account** e verifique se há mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="3637d-165">To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.</span></span>

## <span data-ttu-id="3637d-166">Mais informações</span><span class="sxs-lookup"><span data-stu-id="3637d-166">More information</span></span> 

<span data-ttu-id="3637d-167">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="3637d-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="3637d-168">Guia de remoção do rSSD para empresas</span><span class="sxs-lookup"><span data-stu-id="3637d-168">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="3637d-169">Guia de recuperação do BitLocker</span><span class="sxs-lookup"><span data-stu-id="3637d-169">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="3637d-170">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="3637d-170">Still need help?</span></span> <span data-ttu-id="3637d-171">Vá para [comunidade da Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3637d-171">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>