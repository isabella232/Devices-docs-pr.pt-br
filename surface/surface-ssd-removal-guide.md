---
title: Remoção de SSD em dispositivos Surface compatíveis
description: Este artigo, destinado a técnicos de IT qualificados, descreve as práticas recomendadas para a remoção e substituição de SSDs no Surface Laptop 3, Surface Pro X e Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270626"
---
# <span data-ttu-id="0b0f0-103">Práticas recomendadas para remoção de SSD de dispositivos Surface compatíveis</span><span class="sxs-lookup"><span data-stu-id="0b0f0-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b0f0-104">Este artigo destina-se somente ao uso de técnicos de IT qualificados em uma organização corporativa.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="0b0f0-105">Ele descreve as práticas recomendadas para uso por técnicos de IT qualificados na remoção e substituição de SSDs nos seguintes dispositivos Surface compatíveis:</span><span class="sxs-lookup"><span data-stu-id="0b0f0-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="0b0f0-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="0b0f0-106">Surface Pro 7+</span></span>
- <span data-ttu-id="0b0f0-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="0b0f0-107">Surface Pro X</span></span>
- <span data-ttu-id="0b0f0-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="0b0f0-108">Surface Laptop Go</span></span>
- <span data-ttu-id="0b0f0-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="0b0f0-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="0b0f0-110">Abrir dispositivos e substituir componentes do dispositivo pode causar danos elétricos, danos ao dispositivo, incêndio e riscos de danos pessoais e outros riscos.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="0b0f0-111">Sempre seja cuidadoso ao realizar essas atividades.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="0b0f0-112">Siga as precauções e os procedimentos de segurança identificados no Guia de Remoção [do rSSD para Empresas.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="0b0f0-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="0b0f0-113">Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "Guia de Remoção de RSSD para Empresas".</span><span class="sxs-lookup"><span data-stu-id="0b0f0-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="0b0f0-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0b0f0-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b0f0-115">Este artigo supõe que você compreende as políticas e procedimentos gerais de segurança e precauções de segurança descritas no "Guia de Remoção de RSSD para Empresas".</span><span class="sxs-lookup"><span data-stu-id="0b0f0-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="0b0f0-116">Preparar para remoção do SSD</span><span class="sxs-lookup"><span data-stu-id="0b0f0-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="0b0f0-117">Instalar as atualizações mais recentes</span><span class="sxs-lookup"><span data-stu-id="0b0f0-117">Install the latest updates</span></span> 

<span data-ttu-id="0b0f0-118">Antes de começar, certifique-se de que sua versão do Windows tenha as atualizações mais recentes instaladas:</span><span class="sxs-lookup"><span data-stu-id="0b0f0-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="0b0f0-119">Vá para **Iniciar**  >  **Configurações Atualização**&  >  **Segurança**e selecione Verificar se há **atualizações.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="0b0f0-120">Instale todas as atualizações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-120">Install all available updates.</span></span>
3. <span data-ttu-id="0b0f0-121">Verifique as senhas necessárias para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="0b0f0-122">Gerenciar o BitLocker</span><span class="sxs-lookup"><span data-stu-id="0b0f0-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="0b0f0-123">Esta seção inclui recomendações para organizações que habilitaram a criptografia BitLocker para discos rígidos.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="0b0f0-124">Para obter mais informações, consulte [o Guia de Recuperação do BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="0b0f0-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="0b0f0-125">Se a criptografia BitLocker estiver desabilitada durante a remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="0b0f0-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="0b0f0-126">Se o dispositivo puder ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:</span><span class="sxs-lookup"><span data-stu-id="0b0f0-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="0b0f0-127">Em **Configurações,** digite **BitLocker** e selecione **Gerenciar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="0b0f0-128">Selecione **Desativar BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="0b0f0-129">Alimente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-129">Power down the device.</span></span> 

### <span data-ttu-id="0b0f0-130">Se a criptografia BitLocker estiver habilitada durante a remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="0b0f0-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="0b0f0-131">Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:</span><span class="sxs-lookup"><span data-stu-id="0b0f0-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="0b0f0-132">Em **Configurações,** digite **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="0b0f0-133">Selecione **Gerenciar BitLocker**  > **Gerar Chave de Recuperação do BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="0b0f0-134">Insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="0b0f0-135">Salve a chave de recuperação no armazenamento USB.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="0b0f0-136">Remova a unidade USB.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="0b0f0-137">Alimente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-137">Power down the device.</span></span> 

## <span data-ttu-id="0b0f0-138">Remover e substituir o SSD</span><span class="sxs-lookup"><span data-stu-id="0b0f0-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="0b0f0-139">Remova o SSD usando as instruções apropriadas para seu dispositivo incluído no Guia de Remoção [rSSD para Empresas.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="0b0f0-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="0b0f0-140">Coloque o SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão com a Internet com fio.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="0b0f0-141">A energia do novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-141">Power on the new device.</span></span> <span data-ttu-id="0b0f0-142">O dispositivo pode passar por uma atualização de firmware durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="0b0f0-143">Após a remoção e substituição do SSD</span><span class="sxs-lookup"><span data-stu-id="0b0f0-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="0b0f0-144">Gerenciar SSDs não criptografados</span><span class="sxs-lookup"><span data-stu-id="0b0f0-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="0b0f0-145">Se o SSD não for criptografado durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0b0f0-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="0b0f0-146">Vá para **Senha de Opções de**  >  **Login** (representado pelo ícone de tecla no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="0b0f0-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="0b0f0-147">Insira a senha e entre com a conclusão pendente da autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="0b0f0-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="0b0f0-148">Depois de entrar totalmente, vá para **Iniciar**Saída  >  \*\*\*\*  >  **da Conta.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="0b0f0-149">Entre novamente usando a senha e configurar o Windows Hello e um PIN quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="0b0f0-150">Se o dispositivo foi desabilitado pelo BitLocker para facilitar a remoção e substituição do SSD e você deseja habilitar o BitLocker após a substituição, vá para **o BitLocker**Gerenciar o  >  **BitLocker**Retomar  >  **o BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="0b0f0-151">Execute o [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="0b0f0-152">Verifique se há ativação do Windows navegando até **a ativação de**  >  **configurações.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="0b0f0-153">Se você vir alguma mensagem de erro, selecione **Solucionar problemas.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="0b0f0-154">Verifique a conta do Office abrindo \*\*\*\* o **Aplicativo do Office,** navegue até Conta de Arquivo e verifique se há mensagens  >  \*\*\*\* de erro.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="0b0f0-155">Gerenciando SSDs criptografados</span><span class="sxs-lookup"><span data-stu-id="0b0f0-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="0b0f0-156">Você terá que ter um segundo dispositivo para ler a chave de Recuperação do BitLocker que foi salva na unidade USB.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="0b0f0-157">Se o SSD for criptografado durante a transferência, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0b0f0-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="0b0f0-158">Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="0b0f0-159">Abra o arquivo .txt que contém a chave de recuperação do Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="0b0f0-160">Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="0b0f0-161">Depois de ter inserido com êxito a chave \*\*\*\* de recuperação do BitLocker, vá para Senha de Opções de Entrada (representada pelo ícone de chave  >  \*\*\*\* no lado esquerdo).</span><span class="sxs-lookup"><span data-stu-id="0b0f0-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="0b0f0-162">Insira a senha e entre, conclusão pendente da autenticação de dois fatores (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="0b0f0-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="0b0f0-163">Depois de entrar totalmente, vá para **Iniciar**Saída  >  \*\*\*\*  >  **da Conta.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="0b0f0-164">Entre novamente usando a senha e, em seguida, configurar o Windows Hello e adicionar um PIN.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="0b0f0-165">Se o dispositivo foi desabilitado pelo BitLocker para facilitar a remoção e substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para Configurações **do**  >  **BitLocker**Gerenciar o  >  **BitLocker**Retomar  >  **o BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="0b0f0-166">Execute **[o SDT](surface-diagnostic-toolkit-for-business-intro.md)** para verificar a funcionalidade completa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="0b0f0-167">Para verificar a ativação do Windows, selecione **Ativação de**  >  **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="0b0f0-168">Se você vir alguma mensagem de erro, selecione **Solucionar problemas.**</span><span class="sxs-lookup"><span data-stu-id="0b0f0-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="0b0f0-169">Para verificar o status da conta do Office, \*\*\*\* abra o Aplicativo do **Office**e vá para a Conta de Arquivo  >  \*\*\*\* para verificar se há mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="0b0f0-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="0b0f0-170">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="0b0f0-170">Learn more</span></span>

- [<span data-ttu-id="0b0f0-171">Guia de remoção do rSSD para empresas</span><span class="sxs-lookup"><span data-stu-id="0b0f0-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="0b0f0-172">Guia de recuperação do BitLocker</span><span class="sxs-lookup"><span data-stu-id="0b0f0-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="0b0f0-173">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="0b0f0-173">Still need help?</span></span> <span data-ttu-id="0b0f0-174">Vá para [a Comunidade da Microsoft.](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="0b0f0-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>