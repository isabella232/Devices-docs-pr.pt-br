---
title: Considerações sobre o Surface e o Microsoft Endpoint Configuration Manager
description: O gerenciamento e a implantação de dispositivos Surface com o Configuration Manager são fundamentalmente os mesmos de qualquer outro computador; este artigo descreve cenários que podem exigir considerações adicionais.
keywords: gerenciar, implantação, atualizações, driver, firmware
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 08/12/2021
ms.openlocfilehash: 66fb57afaa3e218a79ac31d36562bae567a3d301
ms.sourcegitcommit: 2776af08eb63c0a23950c476256e5019f83effd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902630"
---
# <a name="considerations-for-surface-and-microsoft-endpoint-configuration-manager"></a>Considerações sobre o Surface e o Microsoft Endpoint Configuration Manager

Fundamentalmente, o gerenciamento e a implantação de dispositivos Surface com Microsoft Endpoint Configuration Manager é o mesmo que o gerenciamento e a implantação de qualquer outro computador. Como qualquer outro computador, uma implantação de dispositivos Surface inclui importar drivers, importar uma imagem Windows, preparar uma sequência de tarefas de implantação e, em seguida, implantar a sequência de tarefas em uma coleção. Após a implantação, os dispositivos Surface são como qualquer outro Windows cliente; para publicar aplicativos, configurações e políticas, você usa o mesmo processo que usaria para qualquer outro dispositivo.

Para saber mais, consulte [Microsoft Endpoint Configuration Manager documentação](/mem/configmgr/).

Embora a implantação e o gerenciamento de dispositivos Surface sejam fundamentalmente semelhantes a outros PCs, alguns cenários podem exigir tarefas de IT adicionais, conforme descrito neste artigo. 

> [!TIP]
> Use o [Branch Atual do Microsoft Endpoint Configuration Manager](/mem/configmgr/core/servers/manage/updates) para gerenciar dispositivos Surface.

## <a name="update-surface-device-drivers-and-firmware"></a>Atualizar drivers e firmware de dispositivo Surface

Para implantar atualizações de drivers de dispositivo e firmware usando o Configuration Manager ou Windows Server Update Services (WSUS), consulte [Manage Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).

## <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Adaptadores Surface Ethernet e implantação do Configuration Manager

O mecanismo padrão que o Configuration Manager usa para identificar dispositivos durante a implantação é o endereço MAC (Controle de Acesso de Mídia). Como o endereço MAC está associado ao controlador Ethernet, um adaptador Ethernet compartilhado entre vários dispositivos fará com que o Configuration Manager identifique cada um dos dispositivos como apenas um único dispositivo, resultando em uma implantação com falha. 

Para garantir que os dispositivos Surface que usam o mesmo adaptador Ethernet sejam identificados como dispositivos exclusivos durante a implantação, você pode instruir o Configuration Manager a identificar dispositivos usando outro método. Você pode especificar que o Configuration Manager use outros métodos de identificação, conforme documentado em [Gerenciar identificadores de hardware duplicados](/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers):

- Adicione uma exclusão para os endereços MAC dos adaptadores Surface Ethernet, o que força o Configuration Manager a ignorar o endereço MAC em preferência do UUID do sistema.

- Use um script para identificar um dispositivo Surface recém-implantado pelo endereço MAC de seu adaptador sem fio.

### <a name="surface-ethernet-driver"></a>Surface Ethernet Driver

Desde 2016, o driver para o adaptador Surface Ethernet foi incluído por padrão no Windows e não requer configuração de IT adicional. Com sua inclusão no Windows 10, o driver não está mais disponível para download no Centro de Download da Microsoft. (Se você precisar implantar versões anteriores do Windows 10 Pro, poderá baixar o driver mais recente do [Catálogo de Atualizações](https://www.catalog.update.microsoft.com/Search.aspx?q=surface%20ethernet%20drivers)da Microsoft ).

## <a name="deploy-surface-app-with-configuration-manager"></a>Implantar o aplicativo Surface com o Configuration Manager

Com o lançamento do Microsoft Store para Empresas, o aplicativo Surface não está mais disponível como um download de driver e firmware. As organizações que implantam o aplicativo Surface em dispositivos surface gerenciados ou durante a implantação por meio do Configuration Manager devem primeiro adquirir o aplicativo Surface por meio Microsoft Store para Empresas. Para saber mais, consulte [Deploy Surface app with Microsoft Store para Empresas](deploy-surface-app-with-windows-store-for-business.md).

## <a name="use-prestaged-media-with-surface-clients"></a>Usar mídia prestada com clientes Surface

Se sua organização usa mídia prestada para carregar recursos de implantação em máquinas antes da implantação com o Configuration Manager, a natureza dos dispositivos Surface como dispositivos UEFI pode exigir que você tome medidas adicionais. Especificamente, um ambiente UEFI nativo exige que você crie várias partições no disco de inicialização do sistema. Se você estiver acompanhando a documentação da [mídia prestada,](/mem/configmgr/osd/deploy-use/create-prestaged-media)as instruções fornecem apenas discos de inicialização de partição única e, portanto, falharão quando aplicadas a dispositivos Surface.

As instruções para aplicar mídia prestada a dispositivos UEFI, como dispositivos Surface, podem ser encontradas na postagem como aplicar a Mídia Prestaged de Sequência de Tarefas em discos multi particionados para BIOS ou [PCs UEFI](https://techcommunity.microsoft.com/t5/configuration-manager-archive/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned/ba-p/392239) no blog do Sistema.

## <a name="licensing-conflicts-with-oem-activation-30"></a>Conflitos de licenciamento com a ativação do OEM 3.0

Os dispositivos Surface vêm pré-instalados com uma cópia licenciada Windows. A chave de licença para essa cópia pré-instalada do Windows está inserida no firmware do dispositivo com [Ativação OEM 3.0](/windows-hardware/manufacture/desktop/oem-activation-3) (OA 3.0). Quando você Windows mídia de instalação em um dispositivo com uma chave OA 3.0, Windows configuração lê automaticamente a chave de licença e a usa para instalar e ativar Windows. Na maioria das situações, isso simplifica a reinstalação de Windows, pois o usuário não precisa encontrar ou inserir uma chave de licença.

Quando você reimage um dispositivo usando Windows Enterprise, essa chave de licença incorporada não causa um conflito. Isso porque a mídia de instalação do Windows Enterprise está configurada para instalar apenas uma edição Enterprise do Windows e, portanto, é incompatível com a chave de licença inserida no firmware do sistema. Se uma chave do produto não for especificada (como quando você pretende ativar com os Serviços de Gerenciamento de Chaves [KMS] ou a Ativação Baseada no Active Directory), uma GVLK (Chave de Licença de Volume Genérico) será usada até que o Windows seja ativado por uma dessas tecnologias.

No entanto, podem surgir problemas quando as organizações pretendem usar versões de Windows compatíveis com a chave incorporada do firmware. Por exemplo, uma organização que deseja instalar o Windows 10 Pro em um dispositivo que originalmente fornecido com o Windows 10 Home pode encontrar dificuldades quando a instalação do Windows lê automaticamente a chave da Edição Inicial durante a instalação e instala como Windows 10 Home em vez de Windows 10 Pro. Para evitar esse conflito, use o arquivo Ei.cfg ou Pid.txt para instruir explicitamente Windows instalação para solicitar uma chave do produto ou inserir uma chave de produto específica na sequência de tarefas de implantação. Para obter mais informações, [consulte Windows Setup Edition Configuration and Product ID Files](/windows-hardware/manufacture/desktop/windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt). Se você não tiver uma chave específica, poderá usar as chaves de produto padrão para Windows. Para obter mais informações, consulte a documentação [para Implantar Windows 10](/windows/deployment/deploy).

## <a name="apply-an-asset-tag-during-deployment"></a>Aplicar uma marca de ativo durante a implantação

Com a [ferramenta de marca do Surface Asset,](assettag.md)você pode identificar dispositivos da UEFI mesmo se o sistema operacional falhar. Para saber mais sobre como gerenciar ativos com o Configuration Manager, consulte [Introdução à inteligência de ativos no Configuration Manager](/mem/configmgr/core/clients/manage/asset-intelligence/introduction-to-asset-intelligence).

## <a name="configure-push-button-reset"></a>Configurar redefinição de botão por push

Quando você implanta Windows em um dispositivo Surface, a funcionalidade de redefinição de botão push do Windows é configurada por padrão para reverter o sistema de volta para um estado em que o ambiente ainda não está configurado. Quando a função de redefinição é usada, o sistema descarta todos os aplicativos e configurações instalados. Embora, em algumas situações, seja útil restaurar o sistema em um estado sem aplicativos e configurações, em um ambiente profissional isso efetivamente torna o sistema inutilizável para o usuário final.

No entanto, a redefinição do botão pode ser configurada para restaurar a configuração do sistema em um estado em que ele está pronto para uso pelo usuário final. Siga o processo descrito em [Deploy push-button reset features](/windows-hardware/manufacture/desktop/deploy-push-button-reset-features) to customize the push-button reset experience for your devices.
