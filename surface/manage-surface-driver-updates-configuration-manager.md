---
title: Atualizações do driver do Surface no Gerenciador de Configurações
description: Este artigo descreve as opções disponíveis para gerenciar e implantar atualizações de firmware e driver para dispositivos Surface.
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e27f2ade66602c53c1bd0e7ef3d326834f1d95ed
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449174"
---
# <a name="manage-surface-driver-updates-in-configuration-manager"></a>Atualizações do driver do Surface no Gerenciador de Configurações

## <a name="summary"></a>Resumo

A partir [do Microsoft System Center Configuration Manager versão 1710](/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), você pode sincronizar e implantar atualizações de firmware e driver do Microsoft Surface diretamente por meio do cliente do Configuration Manager. O processo se parece com a implantação de atualizações regulares. No entanto, algumas configurações adicionais são necessárias para obter as atualizações do driver do Surface em seu catálogo.

## <a name="prerequisites"></a>Pré-requisitos

Para gerenciar atualizações de driver do Surface, os seguintes pré-requisitos devem ser atendidos:

- Você deve usar o Configuration Manager versão 1710 ou uma versão posterior.
- Todos os Pontos de Atualização de Software (SUPs) devem ser executados Windows Server 2016 ou uma versão posterior. Caso contrário, o Configuration Manager ignora essa configuração e os drivers do Surface não serão sincronizados.

> [!NOTE]
> Se seu ambiente não atender aos pré-requisitos, consulte os métodos [alternativos](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) para implantar atualizações de driver e firmware do Surface na seção [Perguntas frequentes](#frequently-asked-questions-faq) .

## <a name="useful-log-files"></a>Arquivos de log úteis

Os logs a seguir são especialmente úteis quando você gerencia atualizações de driver do Surface.

|Nome do log|Descrição|
|---|---|
|WCM.log|Registra detalhes sobre a configuração do ponto de atualização de software e as conexões com o servidor WSUS para categorias, classificações e idiomas de atualização inscritos.|
|WsyncMgr.log|Registra detalhes sobre o processo de sincronização de atualizações de software.|

Esses logs estão localizados no servidor de site que gerencia o SUP ou no próprio SUP se ele estiver instalado diretamente em um servidor de site.
Para uma lista completa de logs do Configuration Manager, consulte [Log files in System Center Configuration Manager](/sccm/core/plan-design/hierarchy/log-files).

## <a name="enabling-surface-driver-updates-management"></a>Habilitando o gerenciamento de atualizações de driver do Surface

Para habilitar o gerenciamento de atualizações de driver do Surface no Configuration Manager, siga estas etapas:

1. No console do Configuration Manager, vá para **AdministrationOverviewSite** > **** >  **ConfigurationSites****** > .
1. Selecione o site que contém o servidor SUP de nível superior para seu ambiente.
1. Na faixa de opções, selecione **Configurar Componentes do Site** e selecione **Ponto de Atualização de Software**. Ou clique com o botão direito do mouse no site e selecione **Configurar Componentes do SiteO** >  **Ponto de Atualização do Microsoft Microsoft.**
1. Na guia **Classificações** , marque a caixa de seleção **Incluir drivers do Microsoft Surface e atualizações de firmware** .

   ![Propriedades do componente do Ponto de Atualização de Software.](images/manage-surface-driver-updates-1.png)

1. Quando você for solicitado pela seguinte mensagem de aviso, selecione **OK**.

   ![Configuration Manager.](images/manage-surface-driver-updates-2.png)

1. Na guia Produtos, selecione os produtos que você deseja atualizar e selecione **OK**.

   A maioria dos drivers pertence aos seguintes grupos de produtos:

   - Windows 10 e drivers de versão posterior
   - Windows 10 e posterior Upgrade & drivers de manutenção
   - Windows 10 atualização de aniversário e drivers de manutenção posteriores
   - Windows 10 atualização de aniversário e atualização posterior & drivers de manutenção
   - Atualização do Windows 10 para Criadores e drivers de manutenção posteriores
   - Atualização do Windows 10 para Criadores e atualização posterior & drivers de manutenção
   - Windows 10 Fall Creators Update e drivers de manutenção posteriores
   - Windows 10 Fall Creators Update e posterior atualização & drivers de manutenção
   - Windows 10 drivers de manutenção S e Posteriores
   - Windows 10 S Versão 1709 e Drivers de Manutenção Posteriores para teste
   - Windows 10 versão S 1709 e Atualização Posterior & drivers de manutenção para teste

   > [!NOTE]
   > A maioria dos drivers surface pertence a vários grupos Windows 10 ou Windows 11 produtos. Talvez não seja preciso selecionar todos os produtos listados aqui. Para ajudar a reduzir o número de produtos que preenchem seu Catálogo de Atualizações, recomendamos que você selecione apenas os produtos exigidos pelo seu ambiente para sincronização.

## <a name="verifying-the-configuration"></a>Verificando a configuração

Para verificar se o SUP está configurado corretamente, siga estas etapas:

1. Abra WsyncMgr.log e procure a seguinte entrada:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   Se uma das seguintes entradas estiver registrada em WsyncMgr.log, verifique novamente a etapa 4 na seção anterior:

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. Abra WCM.log e procure uma entrada que se pareça com o seguinte:

   ![Configurações WCM.log.](images/manage-surface-driver-updates-3.png)

   Essa entrada é um elemento XML que lista cada grupo de produtos e classificação que está sincronizado no momento pelo servidor SUP. Por exemplo, você pode ver uma entrada que se parece com o seguinte:

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   Se você não conseguir encontrar os produtos selecionados na etapa 6 da seção anterior, verifique duas vezes se as configurações sup foram salvas.

   Você também pode aguardar até que a próxima sincronização seja final e verifique se as atualizações de driver e firmware do Surface estão listadas em Atualizações de Software no console do Configuration Manager. Por exemplo, o console pode exibir as informações a seguir.

   ![Todos os Resultados da Pesquisa de Atualizações de Software.](images/manage-surface-driver-updates-4.png)

## <a name="manual-synchronization"></a>Sincronização manual

Se você não quiser esperar até a próxima sincronização, siga estas etapas para iniciar uma sincronização:

1. No console do Configuration Manager, acesse Software **LibraryOverviewSoftware** > **** >  **UpdatesAll** >  **Software Updates**.
1. Na faixa de opções, selecione **Sincronizar Atualizações de Software**. Ou clique com o botão direito do **mouse em Todas as Atualizações de Software** e selecione **Sincronizar Atualização de Software**.
1. Monitore o progresso da sincronização procurando as seguintes entradas em WsyncMgr.log:

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

## <a name="deploying-surface-firmware-and-driver-updates"></a>Implantando atualizações de firmware e driver do Surface

Você pode implantar atualizações de firmware e driver do Surface da mesma maneira que implanta outras atualizações.

Para obter mais informações sobre a implantação, [consulte System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes (FAQ)

**Depois de seguir as etapas deste artigo, meus drivers do Surface ainda não estão sincronizados. Por quê?**

Se você sincronizar de um servidor de Windows Server Update Services (WSUS) upstream, em vez do Microsoft Update, certifique-se de que o servidor WSUS upstream está configurado para dar suporte e sincronizar atualizações de driver do Surface. Todos os servidores downstream estão limitados às atualizações presentes no banco de dados de servidor WSUS upstream.

Há mais de 68.000 atualizações classificadas como drivers no WSUS. Para impedir que drivers não relacionados ao Surface sincronem com o Configuration Manager, a Microsoft filtra a sincronização de driver em uma lista de autorizações. Depois que a nova lista de permitir é publicada e incorporada ao Configuration Manager, os novos drivers são adicionados ao console após a próxima sincronização. A Microsoft pretende adicionar os drivers do Surface à lista de autorizações a cada mês em alinhamento com as versões de atualização mensais para torná-los disponíveis para sincronização com o Configuration Manager.

Se seu ambiente do Configuration Manager estiver offline, uma nova lista de permissão será importada sempre que você importar atualizações de manutenção [para o](/mem/configmgr/core/servers/manage/use-the-service-connection-tool) Configuration Manager. Você também terá que importar um novo [catálogo WSUS](/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) que contenha os drivers antes que as atualizações sejam exibidas no console do Configuration Manager. Como um ambiente WSUS autônomo contém mais drivers do que um SUP do Configuration Manager, recomendamos estabelecer um ambiente do Configuration Manager com recursos online e configurá-lo para sincronizar drivers do Surface. Isso fornece uma exportação WSUS menor que se parece muito com o ambiente offline.

Se seu ambiente do Configuration Manager estiver online e conseguir detectar novas atualizações, você receberá atualizações para a lista automaticamente. Se você não vir os drivers esperados, revise os arquivos WCM.log e WsyncMgr.log para ver se há falhas de sincronização.

**Meu ambiente do Configuration Manager está offline. Posso importar manualmente drivers do Surface para o WSUS?**

Não. Mesmo que a atualização seja importada para o WSUS, a atualização não será importada para o console do Configuration Manager para implantação se ela não estiver listada na lista de autorizações. Você deve usar a [Ferramenta de Conexão de Serviço](/mem/configmgr/core/servers/manage/use-the-service-connection-tool) para importar atualizações de manutenção para o Configuration Manager para atualizar a lista de permissão.

**Quais métodos alternativos preciso implantar atualizações de firmware e driver do Surface?**

Para obter informações sobre como implantar atualizações de driver e firmware do Surface por meio de canais alternativos, consulte [Manage Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md). Se você quiser baixar o arquivo .msi ou .exe e implantar por meio de canais de implantação de software tradicionais, consulte Mantendo o [Firmware do Surface Atualizado com o Configuration Manager](/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).

## <a name="additional-information"></a>Informações adicionais

Para obter mais informações sobre atualizações de firmware e driver do Surface, consulte os seguintes artigos:

- [Gerenciar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md)
- [Considerações sobre o Surface e o System Center Configuration Manager](considerations-for-surface-and-system-center-configuration-manager.md)
