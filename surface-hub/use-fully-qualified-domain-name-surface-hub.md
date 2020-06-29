---
title: Usar o nome de domínio totalmente qualificado com o Surface Hub
description: Solucione problemas comuns, incluindo problemas de instalação e erros do Exchange ActiveSync.
keywords:
- Solucionar problemas comuns
- problemas de instalação
- Erros do Exchange ActiveSync
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830315"
---
# <span data-ttu-id="b71db-106">Configurar o nome de domínio para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b71db-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="b71db-107">Existem alguns cenários em que você precisa especificar o nome de domínio do seu Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="b71db-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="b71db-108">**Vários sufixos DNS** – quando a infraestrutura do Skype for Business tem namespaces separados de tal forma que um ou mais servidores tenham um sufixo DNS que não corresponda ao sufixo do SIP (endereço de entrada) do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b71db-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="b71db-109">**Os sufixos do Skype for Business e do Exchange são diferentes** – quando o sufixo do endereço de entrada para o Skype for Business difere do sufixo do endereço do Exchange usado para a conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b71db-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="b71db-110">**Trabalhando com certificados** – grandes organizações com servidores do Skype for Business local geralmente usam certificados com sua própria CA (autoridade de certificação raiz).</span><span class="sxs-lookup"><span data-stu-id="b71db-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="b71db-111">É comum que o domínio da CA seja diferente do domínio do Skype for Business Server, que faz com que o certificado não seja confiável e que haja falha na entrada.</span><span class="sxs-lookup"><span data-stu-id="b71db-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="b71db-112">O Skype precisa saber o nome de domínio do certificado para configurar uma relação de confiança.</span><span class="sxs-lookup"><span data-stu-id="b71db-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="b71db-113">As empresas geralmente usam a Política de Grupo para enviar isso à área de trabalho do Skype, mas não há suporte para a Política de grupo no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b71db-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="b71db-114">Para configurar o nome de domínio do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b71db-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="b71db-115">No Surface Hub, abra **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="b71db-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="b71db-116">Clique em **Surface Hub**e, em seguida, clique em **Chamadas e áudio**.</span><span class="sxs-lookup"><span data-stu-id="b71db-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="b71db-117">Em **Configuração do Skype for Business**, clique em **Configurar nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="b71db-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="b71db-118">Digite o nome de domínio do Skype for Business Server e clique em **Ok**.</span><span class="sxs-lookup"><span data-stu-id="b71db-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="b71db-119">Você pode digitar vários nomes de domínio, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="b71db-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="b71db-120">Por exemplo: lync.com, outlook.com, lync.glbdns.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b71db-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![Adicionar FQDN para configurações do Skype for Business](images/system-settings-add-fqdn.png)
