---
title: Como usar a recuperação da nuvem para o BitLocker em um Surface Hub
description: Como usar a recuperação da nuvem para o BitLocker em um Surface Hub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Ajustes de acessibilidade, aplicativo Configurações, Facilidade de Acesso
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830320"
---
# <span data-ttu-id="d1e66-104">Resumo</span><span class="sxs-lookup"><span data-stu-id="d1e66-104">Summary</span></span>

<span data-ttu-id="d1e66-105">Este artigo descreve como usar a função de recuperação de nuvem se você for avisado de forma inesperada pelo BitLocker em um dispositivo Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="d1e66-105">This article describes how to use the cloud recovery function if you are unexpectedly prompted by BitLocker on a Surface Hub device.</span></span>

> [!NOTE]
> <span data-ttu-id="d1e66-106">Você deve seguir estas etapas apenas se uma chave de recuperação do BitLocker não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="d1e66-106">You should follow these steps only if a BitLocker recovery key isn't available.</span></span>

> [!WARNING]
> * <span data-ttu-id="d1e66-107">Este processo de recuperação exclui o conteúdo da unidade interna.</span><span class="sxs-lookup"><span data-stu-id="d1e66-107">This recovery process deletes the contents of the internal drive.</span></span> <span data-ttu-id="d1e66-108">Se o processo falhar, a unidade interna ficará completamente inutilizável.</span><span class="sxs-lookup"><span data-stu-id="d1e66-108">If the process fails, the internal drive will become completely unusable.</span></span> <span data-ttu-id="d1e66-109">Se isso ocorrer, será preciso registrar uma solicitação de serviço na Microsoft para obter uma solução.</span><span class="sxs-lookup"><span data-stu-id="d1e66-109">If this occurs, you will have to log a service request with Microsoft for a resolution.</span></span>
> * <span data-ttu-id="d1e66-110">Após a conclusão do processo de recuperação, o dispositivo será redefinido para as configurações de fábrica e retornado ao estado de experiência inicial do da caixa.</span><span class="sxs-lookup"><span data-stu-id="d1e66-110">After the recovery process is complete, the device will be reset to the factory settings and returned to its Out of Box Experience state.</span></span>
> * <span data-ttu-id="d1e66-111">Após a recuperação, o Surface hub deve ser completamente reconfigurado.</span><span class="sxs-lookup"><span data-stu-id="d1e66-111">After the recovery, the Surface Hub must be completely reconfigured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1e66-112">Esse processo requer uma conexão com a Internet aberta que não usa um método proxy ou outro método de autenticação.</span><span class="sxs-lookup"><span data-stu-id="d1e66-112">This process requires an open Internet connection that does not use a proxy or other authentication method.</span></span>

## <span data-ttu-id="d1e66-113">Processo de recuperação na nuvem</span><span class="sxs-lookup"><span data-stu-id="d1e66-113">Cloud recovery process</span></span>

<span data-ttu-id="d1e66-114">Para executar uma recuperação na nuvem, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d1e66-114">To perform a cloud recovery, follow these steps:</span></span>

1. <span data-ttu-id="d1e66-115">Selecione **pressione ESC para obter mais opções de recuperação**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-115">Select **Press Esc for more recovery options**.</span></span>

   ![Captura de tela do escape](images/01-escape.png)

1. <span data-ttu-id="d1e66-117">Selecione **ignorar esta unidade**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-117">Select **Skip this drive**.</span></span>

   ![Captura de tela de ignorar esta unidade](images/02-skip-this-drive.png)

1. <span data-ttu-id="d1e66-119">Selecione **recuperar na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-119">Select **Recover from the cloud**.</span></span>

   ![Captura de tela da recuperação da nuvem](images/03-recover-from-cloud.png)

1. <span data-ttu-id="d1e66-121">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-121">Select **Yes**.</span></span>

   ![Captura de tela de Sim](images/04-yes.png)

1. <span data-ttu-id="d1e66-123">Selecione **reinstalar**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-123">Select **Reinstall**.</span></span>

   ![Captura de tela da reinstalação](images/05a-reinstall.png)

   ![Captura de tela do download](images/05b-downloading.png)

1. <span data-ttu-id="d1e66-126">Após a conclusão do processo de recuperação na nuvem, inicie a reconfiguração usando a **experiência**inicial.</span><span class="sxs-lookup"><span data-stu-id="d1e66-126">After the cloud recovery process is complete, start the reconfiguration by using the **Out of Box Experience**.</span></span>

   ![Captura de tela da caixa de saída](images/06-out-of-box.png)

## <span data-ttu-id="d1e66-128">Mensagem de erro "algo deu errado"</span><span class="sxs-lookup"><span data-stu-id="d1e66-128">"Something went Wrong" error message</span></span>

<span data-ttu-id="d1e66-129">Geralmente, esse erro é causado por problemas de rede que ocorrem durante o download de recuperação.</span><span class="sxs-lookup"><span data-stu-id="d1e66-129">This error is usually caused by network issues that occur during the recovery download.</span></span> <span data-ttu-id="d1e66-130">Quando esse problema ocorre, não desligue o Hub porque você não poderá reiniciá-lo.</span><span class="sxs-lookup"><span data-stu-id="d1e66-130">When this issue occurs, don't turn off the Hub because you won't be able to restart it.</span></span> <span data-ttu-id="d1e66-131">Se você receber essa mensagem de erro, retorne à etapa "recuperar da nuvem" e reinicie o processo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="d1e66-131">If you receive this error message, return to the "Recover from the cloud" step, and then restart the recovery process.</span></span>

1. <span data-ttu-id="d1e66-132">Selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-132">Select **Cancel**.</span></span>

   ![Captura de tela do cancelamento](images/07-cancel.png)

1. <span data-ttu-id="d1e66-134">Selecione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-134">Select **Troubleshoot**.</span></span>

   ![Captura de tela da solução de problemas](images/08-troubleshoot.png)

1. <span data-ttu-id="d1e66-136">Selecione **recuperar na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="d1e66-136">Select **Recover from the cloud**.</span></span>

   ![Captura de tela da recuperação da nuvem](images/09-recover-from-cloud2.png)

1. <span data-ttu-id="d1e66-138">Se o erro **rede com fio não for encontrado** , selecione **Cancelar**e deixe o Surface Hub Redescubra a rede com fio.</span><span class="sxs-lookup"><span data-stu-id="d1e66-138">If the **Wired network isn't found** error occurs, select **Cancel**, and then let the Surface Hub rediscover the wired network.</span></span>

   ![A captura de tela da rede com fio não é encontrada](images/10-cancel.png)