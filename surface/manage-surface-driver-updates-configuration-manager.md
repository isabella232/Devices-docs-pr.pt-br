---
title: Gerenciar atualizações de driver de superfície no Configuration Manager
description: Este artigo descreve as opções disponíveis para gerenciar e implantar firmware e atualizações de driver para dispositivos Surface.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, atualização, dispositivo, gerenciar, implantar, driver, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: 1a9c8c64bd524de58696c73a28795b69cc70a7b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830569"
---
# <span data-ttu-id="25ca3-104">Gerenciar atualizações de driver de superfície no Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="25ca3-104">Manage Surface driver updates in Configuration Manager</span></span>

## <span data-ttu-id="25ca3-105">Resumo</span><span class="sxs-lookup"><span data-stu-id="25ca3-105">Summary</span></span>

<span data-ttu-id="25ca3-106">A partir do [Microsoft System Center Configuration Manager versão 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), você pode sincronizar e implantar o firmware da superfície da Microsoft e atualizações de driver diretamente por meio do cliente do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="25ca3-106">Starting in [Microsoft System Center Configuration Manager version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), you can synchronize and deploy Microsoft Surface firmware and driver updates directly through the Configuration Manager client.</span></span> <span data-ttu-id="25ca3-107">O processo é semelhante à implantação de atualizações regulares.</span><span class="sxs-lookup"><span data-stu-id="25ca3-107">The process resembles deploying regular updates.</span></span> <span data-ttu-id="25ca3-108">No entanto, algumas configurações adicionais são necessárias para obter as atualizações do driver da superfície em seu catálogo.</span><span class="sxs-lookup"><span data-stu-id="25ca3-108">However, some additional configurations are required to get the Surface driver updates into your catalog.</span></span>

## <span data-ttu-id="25ca3-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="25ca3-109">Prerequisites</span></span>

<span data-ttu-id="25ca3-110">Para gerenciar atualizações de driver de superfície, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="25ca3-110">To manage Surface driver updates, the following prerequisites must be met:</span></span>

- <span data-ttu-id="25ca3-111">Você deve usar o Configuration Manager versão 1710 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="25ca3-111">You must use Configuration Manager version 1710 or a later version.</span></span>
- <span data-ttu-id="25ca3-112">Todos os pontos de atualização de software (SUPs) devem executar o Windows Server 2016 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="25ca3-112">All Software Update Points (SUPs) must run Windows Server 2016 or a later version.</span></span> <span data-ttu-id="25ca3-113">Caso contrário, o Configuration Manager ignorará essa configuração e os drivers de superfície não serão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="25ca3-113">Otherwise, Configuration Manager ignores this setting and Surface drivers won't be synchronized.</span></span>

> [!NOTE]
> <span data-ttu-id="25ca3-114">Se o seu ambiente não atender aos pré-requisitos, consulte os [métodos alternativos](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) de implantação de driver de superfície e atualizações de firmware na seção [perguntas frequentes](#frequently-asked-questions-faq) .</span><span class="sxs-lookup"><span data-stu-id="25ca3-114">If your environment doesn’t meet the prerequisites, refer to the [alternative methods](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) to deploy Surface driver and firmware updates in the [FAQ](#frequently-asked-questions-faq) section.</span></span>

## <span data-ttu-id="25ca3-115">Arquivos de log úteis</span><span class="sxs-lookup"><span data-stu-id="25ca3-115">Useful log files</span></span>

<span data-ttu-id="25ca3-116">Os logs a seguir são especialmente úteis quando você gerencia atualizações de driver de superfície.</span><span class="sxs-lookup"><span data-stu-id="25ca3-116">The following logs are especially useful when you manage Surface driver updates.</span></span>

|<span data-ttu-id="25ca3-117">Nome do log</span><span class="sxs-lookup"><span data-stu-id="25ca3-117">Log name</span></span>|<span data-ttu-id="25ca3-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="25ca3-118">Description</span></span>|
|---|---|
|<span data-ttu-id="25ca3-119">WCM. log</span><span class="sxs-lookup"><span data-stu-id="25ca3-119">WCM.log</span></span>|<span data-ttu-id="25ca3-120">Registra detalhes sobre a configuração do ponto de atualização de software e as conexões com o servidor WSUS para as categorias de atualização, as classificações e os idiomas assinados.</span><span class="sxs-lookup"><span data-stu-id="25ca3-120">Records details about the software update point configuration and connections to the WSUS server for subscribed update categories, classifications, and languages.</span></span>|
|<span data-ttu-id="25ca3-121">WsyncMgr. log</span><span class="sxs-lookup"><span data-stu-id="25ca3-121">WsyncMgr.log</span></span>|<span data-ttu-id="25ca3-122">Registra detalhes sobre o processo de sincronização de atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="25ca3-122">Records details about the software updates sync process.</span></span>|

<span data-ttu-id="25ca3-123">Esses logs estão localizados no servidor do site que gerencia o SUP ou no SUP, se ele estiver instalado diretamente em um servidor de site.</span><span class="sxs-lookup"><span data-stu-id="25ca3-123">These logs are located on the site server that manages the SUP, or on the SUP itself if it's installed directly on a site server.</span></span>
<span data-ttu-id="25ca3-124">Para obter uma lista completa de logs do Configuration Manager, consulte [log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="25ca3-124">For a complete list of Configuration Manager logs, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

## <span data-ttu-id="25ca3-125">Habilitando o gerenciamento de atualizações de driver de superfície</span><span class="sxs-lookup"><span data-stu-id="25ca3-125">Enabling Surface driver updates management</span></span>

<span data-ttu-id="25ca3-126">Para habilitar o gerenciamento de atualizações do driver de superfície no Configuration Manager, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="25ca3-126">To enable Surface driver updates management in Configuration Manager, follow these steps:</span></span>

1. <span data-ttu-id="25ca3-127">No console do Configuration Manager, vá para **Administration**  >  sites de configuração de site de**visão geral**de administração  >  **Site Configuration**  >  **Sites**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-127">In the Configuration Manager console, go to **Administration** > **Overview** > **Site Configuration** > **Sites**.</span></span>
1. <span data-ttu-id="25ca3-128">Selecione o site que contém o servidor SUP de nível superior do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="25ca3-128">Select the site that contains the top-level SUP server for your environment.</span></span>
1. <span data-ttu-id="25ca3-129">Na faixa de opções, selecione **configurar componentes do site**e, em seguida, selecione **ponto de atualização do software**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-129">On the ribbon, select **Configure Site Components**, and then select **Software Update Point**.</span></span> <span data-ttu-id="25ca3-130">Ou clique com o botão direito do mouse no site e selecione Configurar o ponto de atualização do software dos **componentes do site**  >  **Software Update Point**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-130">Or, right-click the site, and then select **Configure Site Components** > **Software Update Point**.</span></span>
1. <span data-ttu-id="25ca3-131">Na guia **classificações** , marque a caixa de seleção **incluir drivers de superfície da Microsoft e atualizações de firmware** .</span><span class="sxs-lookup"><span data-stu-id="25ca3-131">On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.</span></span>

   ![Propriedades do componente ponto de atualização de software](images/manage-surface-driver-updates-1.png)

1. <span data-ttu-id="25ca3-133">Quando for solicitado pela seguinte mensagem de aviso, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-133">When you're prompted by the following warning message, select **OK**.</span></span>

   ![Gerenciador de Configurações](images/manage-surface-driver-updates-2.png)

1. <span data-ttu-id="25ca3-135">Na guia produtos, selecione os produtos que você deseja atualizar e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-135">On the Products tab, select the products that you want to update, and then select **OK**.</span></span>

   <span data-ttu-id="25ca3-136">A maioria dos drivers pertence aos seguintes grupos de produtos:</span><span class="sxs-lookup"><span data-stu-id="25ca3-136">Most drivers belong to the following product groups:</span></span>

   - <span data-ttu-id="25ca3-137">Windows 10 e drivers de versões posteriores</span><span class="sxs-lookup"><span data-stu-id="25ca3-137">Windows 10 and later version drivers</span></span>
   - <span data-ttu-id="25ca3-138">Atualização do Windows 10 e posterior & drivers de serviço</span><span class="sxs-lookup"><span data-stu-id="25ca3-138">Windows 10 and later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-139">Atualização de aniversário do Windows 10 e drivers de serviços posteriores</span><span class="sxs-lookup"><span data-stu-id="25ca3-139">Windows 10 Anniversary Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-140">Atualização de aniversário do Windows 10 e atualização posterior & drivers de serviço</span><span class="sxs-lookup"><span data-stu-id="25ca3-140">Windows 10 Anniversary Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-141">Drivers de manutenção do Windows 10 Creators Update e posteriores</span><span class="sxs-lookup"><span data-stu-id="25ca3-141">Windows 10 Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-142">Atualização do Windows 10 Creators Update e atualização posterior & drivers de serviço</span><span class="sxs-lookup"><span data-stu-id="25ca3-142">Windows 10 Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-143">Drivers de serviços de atualização do Windows 10 para criadores de outono e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="25ca3-143">Windows 10 Fall Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-144">Atualização dos criadores de outono do Windows 10 e atualização posterior & drivers de serviço</span><span class="sxs-lookup"><span data-stu-id="25ca3-144">Windows 10 Fall Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-145">Drivers de serviços do Windows 10 S e posteriores</span><span class="sxs-lookup"><span data-stu-id="25ca3-145">Windows 10 S and Later Servicing Drivers</span></span>
   - <span data-ttu-id="25ca3-146">Drivers de serviços do Windows 10 S versão 1709 e posterior para teste</span><span class="sxs-lookup"><span data-stu-id="25ca3-146">Windows 10 S Version 1709 and Later Servicing Drivers for testing</span></span>
   - <span data-ttu-id="25ca3-147">Atualização do Windows 10 S 1709 e posteriores & drivers de manutenção para teste</span><span class="sxs-lookup"><span data-stu-id="25ca3-147">Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing</span></span>

   > [!NOTE]
   > <span data-ttu-id="25ca3-148">A maioria dos drivers de superfície pertence a vários grupos de produtos do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="25ca3-148">Most Surface drivers belong to multiple Windows 10 product groups.</span></span> <span data-ttu-id="25ca3-149">Pode ser que você não precise selecionar todos os produtos listados aqui.</span><span class="sxs-lookup"><span data-stu-id="25ca3-149">You may not have to select all the products that are listed here.</span></span> <span data-ttu-id="25ca3-150">Para ajudar a reduzir o número de produtos que preenchem o catálogo de atualizações, recomendamos que você selecione apenas os produtos necessários para a sincronização do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="25ca3-150">To help reduce the number of products that populate your Update Catalog, we recommend that you select only the products that are required by your environment for synchronization.</span></span>

## <span data-ttu-id="25ca3-151">Verificando a configuração</span><span class="sxs-lookup"><span data-stu-id="25ca3-151">Verifying the configuration</span></span>

<span data-ttu-id="25ca3-152">Para verificar se o SUP está configurado corretamente, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="25ca3-152">To verify that the SUP is configured correctly, follow these steps:</span></span>

1. <span data-ttu-id="25ca3-153">Abra WsyncMgr. log e procure a seguinte entrada:</span><span class="sxs-lookup"><span data-stu-id="25ca3-153">Open WsyncMgr.log, and then look for the following entry:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   <span data-ttu-id="25ca3-154">Se qualquer uma das seguintes entradas estiver registrada no WsyncMgr. log, verifique novamente a etapa 4 na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="25ca3-154">If either of the following entries is logged in WsyncMgr.log, recheck step 4 in the previous section:</span></span>

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. <span data-ttu-id="25ca3-155">Abra WCM. log e procure uma entrada semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="25ca3-155">Open WCM.log, and then look for an entry that resembles the following:</span></span>

   ![Configurações de WCM. log](images/manage-surface-driver-updates-3.png)

   <span data-ttu-id="25ca3-157">Esta entrada é um elemento XML que lista cada grupo de produtos e classificação atualmente sincronizada pelo seu servidor SUP.</span><span class="sxs-lookup"><span data-stu-id="25ca3-157">This entry is an XML element that lists every product group and classification that's currently synchronized by your SUP server.</span></span> <span data-ttu-id="25ca3-158">Por exemplo, você pode ver uma entrada semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="25ca3-158">For example, you might see an entry that resembles the following:</span></span>

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   <span data-ttu-id="25ca3-159">Se você não conseguir encontrar os produtos que selecionou na etapa 6 na seção anterior, verifique se as configurações do SUP foram salvas.</span><span class="sxs-lookup"><span data-stu-id="25ca3-159">If you can't find the products that you selected in step 6 in the previous section, double-check whether the SUP settings are saved.</span></span>

   <span data-ttu-id="25ca3-160">Você também pode esperar até que a próxima sincronização seja concluída e verificar se o driver de superfície e atualizações de firmware estão listados em atualizações de software no console do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="25ca3-160">You can also wait until the next synchronization finishes, and then check whether the Surface driver and firmware updates are listed in Software Updates in the Configuration Manager console.</span></span> <span data-ttu-id="25ca3-161">Por exemplo, o console pode exibir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="25ca3-161">For example, the console might display the following information:</span></span>

   ![Todas as atualizações de software resultados da pesquisa](images/manage-surface-driver-updates-4.png)

## <span data-ttu-id="25ca3-163">Sincronização manual</span><span class="sxs-lookup"><span data-stu-id="25ca3-163">Manual synchronization</span></span>

<span data-ttu-id="25ca3-164">Se você não quiser esperar até a próxima sincronização, siga estas etapas para iniciar uma sincronização:</span><span class="sxs-lookup"><span data-stu-id="25ca3-164">If you don't want to wait until the next synchronization, follow these steps to start a synchronization:</span></span>

1. <span data-ttu-id="25ca3-165">No console do Configuration Manager, acesse Software visão geral da **biblioteca de software**  >  **Overview**  >  **atualiza**  >  **todas as atualizações de software**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-165">In the Configuration Manager console, go to **Software Library** > **Overview** > **Software Updates** > **All Software Updates**.</span></span>
1. <span data-ttu-id="25ca3-166">Na faixa de opções, selecione **sincronizar atualizações de software**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-166">On the ribbon, select **Synchronize Software Updates**.</span></span> <span data-ttu-id="25ca3-167">Ou clique com o botão direito do mouse em **toda a atualização de software**e selecione **sincronizar atualização de software**.</span><span class="sxs-lookup"><span data-stu-id="25ca3-167">Or, right-click **All Software Update**, and then select **Synchronize Software Update**.</span></span>
1. <span data-ttu-id="25ca3-168">Monitore o progresso da sincronização procurando as seguintes entradas no WsyncMgr. log:</span><span class="sxs-lookup"><span data-stu-id="25ca3-168">Monitor the synchronization progress by looking for the following entries in WsyncMgr.log:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <span data-ttu-id="25ca3-169">Implantação de firmware de superfície e atualizações de driver</span><span class="sxs-lookup"><span data-stu-id="25ca3-169">Deploying Surface firmware and driver updates</span></span>

<span data-ttu-id="25ca3-170">Você pode implantar o firmware da superfície e as atualizações de driver da mesma maneira que implanta outras atualizações.</span><span class="sxs-lookup"><span data-stu-id="25ca3-170">You can deploy Surface firmware and driver updates in the same manner as you deploy other updates.</span></span>

<span data-ttu-id="25ca3-171">Para obter mais informações sobre a implantação, consulte [Gerenciador de configuração do System Center 2012 – Part7: atualizações de software (implantar)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span><span class="sxs-lookup"><span data-stu-id="25ca3-171">For more information about deployment, see [System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span></span>

## <span data-ttu-id="25ca3-172">Perguntas frequentes (FAQ)</span><span class="sxs-lookup"><span data-stu-id="25ca3-172">Frequently asked questions (FAQ)</span></span>

**<span data-ttu-id="25ca3-173">Depois de seguir as etapas deste artigo, meus drivers de superfície ainda não estão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="25ca3-173">After I follow the steps in this article, my Surface drivers are still not synchronized.</span></span> <span data-ttu-id="25ca3-174">Por quê?</span><span class="sxs-lookup"><span data-stu-id="25ca3-174">Why?</span></span>**

<span data-ttu-id="25ca3-175">Se você sincronizar de um servidor WSUS (Windows Server Update Services) upstream, em vez do Microsoft Update, certifique-se de que o servidor upstream do WSUS esteja configurado para dar suporte e sincronizar atualizações de driver de superfície.</span><span class="sxs-lookup"><span data-stu-id="25ca3-175">If you synchronize from an upstream Windows Server Update Services (WSUS) server, instead of Microsoft Update, make sure that the upstream WSUS server is configured to support and synchronize Surface driver updates.</span></span> <span data-ttu-id="25ca3-176">Todos os servidores downstream são limitados a atualizações que estão presentes no banco de dados do servidor do WSUS upstream.</span><span class="sxs-lookup"><span data-stu-id="25ca3-176">All downstream servers are limited to updates that are present in the upstream WSUS server database.</span></span>

<span data-ttu-id="25ca3-177">Há mais de 68.000 atualizações classificadas como drivers no WSUS.</span><span class="sxs-lookup"><span data-stu-id="25ca3-177">There are more than 68,000 updates that are classified as drivers in WSUS.</span></span> <span data-ttu-id="25ca3-178">Para impedir a sincronização de drivers não relacionados à superfície no Configuration Manager, a Microsoft filtra a sincronização do driver em relação a uma lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="25ca3-178">To prevent non-Surface related drivers from synchronizing to Configuration Manager, Microsoft filters driver synchronization against an allow list.</span></span> <span data-ttu-id="25ca3-179">Depois que a nova lista de permissões é publicada e incorporada no Configuration Manager, os novos drivers são adicionados ao console após a próxima sincronização.</span><span class="sxs-lookup"><span data-stu-id="25ca3-179">After the new allow list is published and incorporated into Configuration Manager, the new drivers are added to the console following the next synchronization.</span></span> <span data-ttu-id="25ca3-180">A Microsoft tem o objetivo de obter os drivers de superfície adicionados à lista de permissões a cada mês na linha com a Patch Tuesday para disponibilizá-los para sincronização com o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="25ca3-180">Microsoft aims to get the Surface drivers added to the allow list each month in line with Patch Tuesday to make them available for synchronization to Configuration Manager.</span></span>

<span data-ttu-id="25ca3-181">Se o ambiente do Configuration Manager estiver offline, uma nova lista de permissões será importada toda vez que você importar [atualizações de serviço](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) para o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="25ca3-181">If your Configuration Manager environment is offline, a new allow list is imported every time you import [servicing updates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to Configuration Manager.</span></span> <span data-ttu-id="25ca3-182">Você também terá que importar um [novo catálogo WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) que contém os drivers antes de as atualizações serem exibidas no console do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="25ca3-182">You will also have to import a [new WSUS catalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) that contains the drivers before the updates are displayed in the Configuration Manager console.</span></span> <span data-ttu-id="25ca3-183">Como um ambiente autônomo do WSUS contém mais drivers do que um SUP do Configuration Manager, recomendamos que você estabeleça um ambiente do Configuration Manager com recursos online, e que você o configure para sincronizar drivers Surface.</span><span class="sxs-lookup"><span data-stu-id="25ca3-183">Because a stand-alone WSUS environment contains more drivers than a Configuration Manager SUP, we recommend that you establish a Configuration Manager environment that has online capabilities, and that you configure it to synchronize Surface drivers.</span></span> <span data-ttu-id="25ca3-184">Isso proporciona uma exportação menor do WSUS que é semelhante ao ambiente offline.</span><span class="sxs-lookup"><span data-stu-id="25ca3-184">This provides a smaller WSUS export that closely resembles the offline environment.</span></span>

<span data-ttu-id="25ca3-185">Se o ambiente do Configuration Manager estiver online e puder detectar novas atualizações, você receberá atualizações automaticamente na lista.</span><span class="sxs-lookup"><span data-stu-id="25ca3-185">If your Configuration Manager environment is online and able to detect new updates, you will receive updates to the list automatically.</span></span> <span data-ttu-id="25ca3-186">Se você não vir os drivers esperados, examine o WCM. log e o WsyncMgr. log para qualquer falha de sincronização.</span><span class="sxs-lookup"><span data-stu-id="25ca3-186">If you don’t see the expected drivers, please review the WCM.log and WsyncMgr.log for any synchronization failures.</span></span>

**<span data-ttu-id="25ca3-187">Meu ambiente do Configuration Manager está offline, eu posso importar manualmente os drivers de superfície para o WSUS?</span><span class="sxs-lookup"><span data-stu-id="25ca3-187">My Configuration Manager environment is offline, can I manually import Surface drivers into WSUS?</span></span>**

<span data-ttu-id="25ca3-188">Não.</span><span class="sxs-lookup"><span data-stu-id="25ca3-188">No.</span></span> <span data-ttu-id="25ca3-189">Mesmo que a atualização seja importada para o WSUS, a atualização não será importada para o console do Configuration Manager para implantação se ela não estiver listada na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="25ca3-189">Even if the update is imported into WSUS, the update won't be imported into the Configuration Manager console for deployment if it isn't listed in the allow list.</span></span> <span data-ttu-id="25ca3-190">Você deve usar a [ferramenta de conexão de serviço](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) para importar atualizações de serviço para o Configuration Manager para atualizar a lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="25ca3-190">You must use the [Service Connection Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to import servicing updates to Configuration Manager to update the allow list.</span></span>

**<span data-ttu-id="25ca3-191">Quais são os métodos alternativos que preciso para implantar drivers de superfície e atualizações de firmware?</span><span class="sxs-lookup"><span data-stu-id="25ca3-191">What alternative methods do I have to deploy Surface driver and firmware updates?</span></span>**

<span data-ttu-id="25ca3-192">Para obter informações sobre como implantar atualizações de driver de superfície e firmware por meio de canais alternativos, consulte [gerenciar atualizações de driver de superfície e firmware](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="25ca3-192">For information about how to deploy Surface driver and firmware updates through alternative channels, see [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates).</span></span> <span data-ttu-id="25ca3-193">Se você quiser baixar o arquivo. msi ou. exe e implantá-lo por meio dos canais tradicionais de implantação de software, consulte [mantendo o firmware de superfície atualizado com o Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="25ca3-193">If you want to download the .msi or .exe file, and then deploy through traditional software deployment channels, see [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span></span>

## <span data-ttu-id="25ca3-194">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="25ca3-194">Additional Information</span></span>

<span data-ttu-id="25ca3-195">Para obter mais informações sobre driver de superfície e atualizações de firmware, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="25ca3-195">For more information about Surface driver and firmware updates, see the following articles:</span></span>

- [<span data-ttu-id="25ca3-196">Baixar o firmware e os drivers mais recentes para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="25ca3-196">Download the latest firmware and drivers for Surface devices</span></span>](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)
- [<span data-ttu-id="25ca3-197">Gerenciar atualizações de driver e firmware do Surface</span><span class="sxs-lookup"><span data-stu-id="25ca3-197">Manage Surface driver and firmware updates</span></span>](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)
- [<span data-ttu-id="25ca3-198">Considerações sobre o Surface e o System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="25ca3-198">Considerations for Surface and System Center Configuration Manager</span></span>](https://docs.microsoft.com/surface/considerations-for-surface-and-system-center-configuration-manager)
