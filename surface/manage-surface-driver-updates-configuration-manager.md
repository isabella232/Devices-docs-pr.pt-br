---
title: Atualizações do driver do Surface no Gerenciador de Configurações
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
ms.openlocfilehash: be32309b26ff6a873c36927cc39595022c4dbb90
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897069"
---
# Atualizações do driver do Surface no Gerenciador de Configurações

## Resumo

A partir do [Microsoft System Center Configuration Manager versão 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), você pode sincronizar e implantar o firmware da superfície da Microsoft e atualizações de driver diretamente por meio do cliente do Configuration Manager. O processo é semelhante à implantação de atualizações regulares. No entanto, algumas configurações adicionais são necessárias para obter as atualizações do driver da superfície em seu catálogo.

## Pré-requisitos

Para gerenciar atualizações de driver de superfície, os seguintes pré-requisitos devem ser atendidos:

- Você deve usar o Configuration Manager versão 1710 ou uma versão posterior.
- Todos os pontos de atualização de software (SUPs) devem executar o Windows Server 2016 ou uma versão posterior. Caso contrário, o Configuration Manager ignorará essa configuração e os drivers de superfície não serão sincronizados.

> [!NOTE]
> Se o seu ambiente não atender aos pré-requisitos, consulte os [métodos alternativos](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) de implantação de driver de superfície e atualizações de firmware na seção [perguntas frequentes](#frequently-asked-questions-faq) .

## Arquivos de log úteis

Os logs a seguir são especialmente úteis quando você gerencia atualizações de driver de superfície.

|Nome do log|Descrição|
|---|---|
|WCM. log|Registra detalhes sobre a configuração do ponto de atualização de software e as conexões com o servidor WSUS para as categorias de atualização, as classificações e os idiomas assinados.|
|WsyncMgr. log|Registra detalhes sobre o processo de sincronização de atualizações de software.|

Esses logs estão localizados no servidor do site que gerencia o SUP ou no SUP, se ele estiver instalado diretamente em um servidor de site.
Para obter uma lista completa de logs do Configuration Manager, consulte [log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).

## Habilitando o gerenciamento de atualizações de driver de superfície

Para habilitar o gerenciamento de atualizações do driver de superfície no Configuration Manager, siga estas etapas:

1. No console do Configuration Manager, vá para **Administration**  >  sites de configuração de site de**visão geral**de administração  >  **Site Configuration**  >  **Sites**.
1. Selecione o site que contém o servidor SUP de nível superior do seu ambiente.
1. Na faixa de opções, selecione **configurar componentes do site**e, em seguida, selecione **ponto de atualização do software**. Ou clique com o botão direito do mouse no site e selecione Configurar o ponto de atualização do software dos **componentes do site**  >  **Software Update Point**.
1. Na guia **classificações** , marque a caixa de seleção **incluir drivers de superfície da Microsoft e atualizações de firmware** .

   ![Propriedades do componente ponto de atualização de software](images/manage-surface-driver-updates-1.png)

1. Quando for solicitado pela seguinte mensagem de aviso, selecione **OK**.

   ![Gerenciador de Configurações](images/manage-surface-driver-updates-2.png)

1. Na guia produtos, selecione os produtos que você deseja atualizar e, em seguida, selecione **OK**.

   A maioria dos drivers pertence aos seguintes grupos de produtos:

   - Windows 10 e drivers de versões posteriores
   - Atualização do Windows 10 e posterior & drivers de serviço
   - Atualização de aniversário do Windows 10 e drivers de serviços posteriores
   - Atualização de aniversário do Windows 10 e atualização posterior & drivers de serviço
   - Drivers de manutenção do Windows 10 Creators Update e posteriores
   - Atualização do Windows 10 Creators Update e atualização posterior & drivers de serviço
   - Drivers de serviços de atualização do Windows 10 para criadores de outono e versões posteriores
   - Atualização dos criadores de outono do Windows 10 e atualização posterior & drivers de serviço
   - Drivers de serviços do Windows 10 S e posteriores
   - Drivers de serviços do Windows 10 S versão 1709 e posterior para teste
   - Atualização do Windows 10 S 1709 e posteriores & drivers de manutenção para teste

   > [!NOTE]
   > A maioria dos drivers de superfície pertence a vários grupos de produtos do Windows 10. Pode ser que você não precise selecionar todos os produtos listados aqui. Para ajudar a reduzir o número de produtos que preenchem o catálogo de atualizações, recomendamos que você selecione apenas os produtos necessários para a sincronização do seu ambiente.

## Verificando a configuração

Para verificar se o SUP está configurado corretamente, siga estas etapas:

1. Abra WsyncMgr. log e procure a seguinte entrada:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   Se qualquer uma das seguintes entradas estiver registrada no WsyncMgr. log, verifique novamente a etapa 4 na seção anterior:

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. Abra WCM. log e procure uma entrada semelhante à seguinte:

   ![Configurações de WCM. log](images/manage-surface-driver-updates-3.png)

   Esta entrada é um elemento XML que lista cada grupo de produtos e classificação atualmente sincronizada pelo seu servidor SUP. Por exemplo, você pode ver uma entrada semelhante à seguinte:

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   Se você não conseguir encontrar os produtos que selecionou na etapa 6 na seção anterior, verifique se as configurações do SUP foram salvas.

   Você também pode esperar até que a próxima sincronização seja concluída e verificar se o driver de superfície e atualizações de firmware estão listados em atualizações de software no console do Configuration Manager. Por exemplo, o console pode exibir as informações a seguir.

   ![Todas as atualizações de software resultados da pesquisa](images/manage-surface-driver-updates-4.png)

## Sincronização manual

Se você não quiser esperar até a próxima sincronização, siga estas etapas para iniciar uma sincronização:

1. No console do Configuration Manager, acesse Software visão geral da **biblioteca de software**  >  **Overview**  >  **atualiza**  >  **todas as atualizações de software**.
1. Na faixa de opções, selecione **sincronizar atualizações de software**. Ou clique com o botão direito do mouse em **toda a atualização de software**e selecione **sincronizar atualização de software**.
1. Monitore o progresso da sincronização procurando as seguintes entradas no WsyncMgr. log:

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

## Implantação de firmware de superfície e atualizações de driver

Você pode implantar o firmware da superfície e as atualizações de driver da mesma maneira que implanta outras atualizações.

Para obter mais informações sobre a implantação, consulte [Gerenciador de configuração do System Center 2012 – Part7: atualizações de software (implantar)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).

## Perguntas frequentes (FAQ)

**Depois de seguir as etapas deste artigo, meus drivers de superfície ainda não estão sincronizados. Por quê?**

Se você sincronizar de um servidor WSUS (Windows Server Update Services) upstream, em vez do Microsoft Update, certifique-se de que o servidor upstream do WSUS esteja configurado para dar suporte e sincronizar atualizações de driver de superfície. Todos os servidores downstream são limitados a atualizações que estão presentes no banco de dados do servidor do WSUS upstream.

Há mais de 68.000 atualizações classificadas como drivers no WSUS. Para impedir a sincronização de drivers não relacionados à superfície no Configuration Manager, a Microsoft filtra a sincronização do driver em relação a uma lista de permissões. Depois que a nova lista de permissões é publicada e incorporada no Configuration Manager, os novos drivers são adicionados ao console após a próxima sincronização. A Microsoft tem o objetivo de obter os drivers de superfície adicionados à lista de permissões a cada mês em alinhamento com as versões de atualização mensais para disponibilizá-los para sincronização com o Configuration Manager.

Se o ambiente do Configuration Manager estiver offline, uma nova lista de permissões será importada toda vez que você importar [atualizações de serviço](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) para o Configuration Manager. Você também terá que importar um [novo catálogo WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) que contém os drivers antes de as atualizações serem exibidas no console do Configuration Manager. Como um ambiente autônomo do WSUS contém mais drivers do que um SUP do Configuration Manager, recomendamos que você estabeleça um ambiente do Configuration Manager com recursos online, e que você o configure para sincronizar drivers Surface. Isso proporciona uma exportação menor do WSUS que é semelhante ao ambiente offline.

Se o ambiente do Configuration Manager estiver online e puder detectar novas atualizações, você receberá atualizações automaticamente na lista. Se você não vir os drivers esperados, examine os arquivos WCM. log e WsyncMgr. log em busca de falhas de sincronização.

**Meu ambiente do Configuration Manager está offline. Eu posso importar manualmente os drivers de superfície para o WSUS?**

Não. Mesmo que a atualização seja importada para o WSUS, a atualização não será importada para o console do Configuration Manager para implantação se ela não estiver listada na lista de permissões. Você deve usar a [ferramenta de conexão de serviço](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) para importar atualizações de serviço para o Configuration Manager para atualizar a lista de permissões.

**Quais são os métodos alternativos que preciso para implantar drivers de superfície e atualizações de firmware?**

Para obter informações sobre como implantar atualizações de driver de superfície e firmware por meio de canais alternativos, consulte [gerenciar atualizações de driver de superfície e firmware](manage-surface-driver-and-firmware-updates.md). Se você quiser baixar o arquivo. msi ou. exe e implantá-lo por meio dos canais tradicionais de implantação de software, consulte [mantendo o firmware de superfície atualizado com o Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).

## Informações adicionais

Para obter mais informações sobre driver de superfície e atualizações de firmware, consulte os seguintes artigos:

- [Gerenciar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md)
- [Considerações sobre o Surface e o System Center Configuration Manager](considerations-for-surface-and-system-center-configuration-manager.md)
