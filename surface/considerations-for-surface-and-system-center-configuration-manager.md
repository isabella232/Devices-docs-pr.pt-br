---
title: Considerações sobre Surface e Microsoft Endpoint Configuration Manager
description: O gerenciamento e a implantação de dispositivos Surface com o Configuration Manager são fundamentalmente iguais aos outros PCs; Este artigo descreve cenários que podem exigir considerações adicionais.
keywords: gerenciar, implantação, atualizações, Driver, firmware
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
ms.openlocfilehash: 4fa62d227deb0b0b07fa0fbc6552ea5b04c1b87b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830285"
---
# Considerações sobre Surface e Microsoft Endpoint Configuration Manager

Fundamentalmente, o gerenciamento e a implantação de dispositivos Surface com o Microsoft Endpoint Configuration Manager é o mesmo que o gerenciamento e a implantação de qualquer outro computador. Como qualquer outro computador, uma implantação em dispositivos Surface inclui a importação de drivers, a importação de uma imagem do Windows, a preparação de uma sequência de tarefas de implantação e a implantação da sequência de tarefas em uma coleção. Após a implantação, os dispositivos Surface são como qualquer outro cliente Windows; para publicar aplicativos, configurações e políticas, use o mesmo processo que você usaria para qualquer outro dispositivo.

Você pode encontrar mais informações sobre como usar o Configuration Manager para implantar e gerenciar dispositivos na [documentação do Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/index).

Embora a implantação e o gerenciamento de dispositivos Surface sejam fundamentalmente iguais aos outros PCs, há alguns cenários que podem exigir considerações adicionais ou etapas. Este artigo fornece descrições e diretrizes para esses cenários. As soluções documentadas neste artigo também podem ser aplicadas a outros dispositivos e fabricantes.

> [!NOTE]
> Para o gerenciamento de dispositivos Surface, é recomendável que você use a ramificação atual do Microsoft Endpoint Configuration Manager.

##  <a name="updating-surface-device-drivers-and-firmware"></a>Atualização de drivers de dispositivo Surface e firmware

Para os dispositivos que recebem atualizações por meio do Windows Update, drivers para componentes Surface (e até mesmo atualizações de firmware) são aplicados automaticamente como parte do processo do Windows Update. Para dispositivos com atualizações gerenciadas, como aquelas atualizadas por meio do Windows Server Update Services (WSUS) ou do Configuration Manager, consulte [gerenciar atualizações de driver de superfície e firmware](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates/).

> [!NOTE]
> O firmware e os drivers de dispositivo Surface são assinados com SHA-256, que não tem suporte nativo do Windows Server 2008 R2. Uma solução alternativa está disponível para ambientes do Configuration Manager em execução no Windows Server 2008 R2. Para obter mais informações, consulte [não é possível importar drivers para o Gerenciador de configuração do Microsoft EndPoint (KB3025419)](https://support.microsoft.com/kb/3025419).

##  <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Adaptadores Ethernet Surface e implantação do Configuration Manager

O mecanismo padrão usado pelo Configuration Manager para identificar dispositivos durante a implantação é o endereço de controle de acesso à mídia (MAC). Como o endereço MAC está associado ao controlador Ethernet, um adaptador Ethernet compartilhado entre vários dispositivos fará com que o Configuration Manager identifique cada um dos dispositivos como um único dispositivo. Isso pode fazer com que uma implantação do Configuration Manager do Windows não seja aplicada a dispositivos pretendidos.

Para garantir que os dispositivos Surface que usam o mesmo adaptador Ethernet sejam identificados como dispositivos exclusivos durante a implantação, você pode instruir o Configuration Manager a identificar dispositivos usando outro método. Esse outro método pode ser o endereço MAC do adaptador de rede sem fio ou o identificador exclusivo universal do sistema (UUID do sistema). Você pode especificar que o Configuration Manager use outros métodos de identificação com as seguintes opções:

* Adicione uma exclusão para os endereços MAC de adaptadores Ethernet Surface, que força o Configuration Manager a ignorar o endereço MAC em preferência ao UUID do sistema, conforme documentado na [reutilização da mesma NIC para várias implantações iniciadas em PXE na postagem de blog OSD do SMicrosoft Endpoint Configuration Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) .

* Pré-teste de dispositivos pelo UUID do sistema conforme documentado na [reutilização da mesma NIC para várias implantações iniciadas PXE na postagem de blog OSD do Gerenciador de configuração do Microsoft Endpoint Configuration Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) .

* Use um script para identificar um dispositivo de superfície recém implantado pelo endereço MAC do seu adaptador sem fio, conforme documentado em [como usar o mesmo adaptador Ethernet externo para várias Postagens de blog do SCCM OSD](https://blogs.technet.microsoft.com/askpfeplat/2014/07/27/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm-osd/) .

Outra consideração para o adaptador Ethernet Surface durante implantações com o Configuration Manager é o driver para o controlador Ethernet. A partir do Windows 10, versão 1511, o driver para o adaptador de Ethernet Surface está incluído por padrão no Windows. Para as organizações que desejam implantar a versão mais recente do Windows 10 e usar a versão mais recente do WinPE, o uso do adaptador Ethernet Surface não requer nenhuma ação adicional.

Para as versões do Windows anteriores ao Windows 10, versão 1511 (incluindo Windows 10 RTM e Windows 8,1), talvez você ainda precise instalar o driver do adaptador Ethernet da superfície e incluir o driver na mídia de inicialização do WinPE. Com sua inclusão no Windows 10, o driver não está mais disponível para download no centro de download da Microsoft. Para baixar o driver do adaptador de Ethernet Surface, baixe-o a partir do catálogo do Microsoft Update, conforme documentado na postagem de blog de [drivers Ethernet Surface](https://blogs.technet.microsoft.com/askcore/2016/08/18/surface-ethernet-drivers/) do blog da equipe principal.

##  <a name="deploy-surface-app-with-configuration-manager"></a>Implantar o aplicativo Surface com o Configuration Manager

Com o lançamento da Microsoft Store para empresas, o aplicativo Surface não está mais disponível como um download de driver e firmware. As organizações que desejam implantar o aplicativo Surface em dispositivos de superfície gerenciada ou durante a implantação com o uso do Configuration Manager devem adquirir o aplicativo Surface por meio da Microsoft Store para empresas e, em seguida, implantar o aplicativo Surface com o PowerShell. Você pode encontrar os comandos do PowerShell para implantação do aplicativo Surface, instruções para baixar o aplicativo Surface e estruturas de pré-requisito da Microsoft Store para empresas no [aplicativo implantar superfície com o artigo da Microsoft Store para empresas](https://technet.microsoft.com/itpro/surface/deploy-surface-app-with-windows-store-for-business) na biblioteca do TechNet.

##  <a name="use-prestaged-media-with-surface-clients"></a>Usar mídia em pré-teste com clientes Surface

Se a sua organização usa mídia em pré-teste para carregar recursos de implantação em máquinas antes da implantação com o Configuration Manager, a natureza dos dispositivos de superfície como dispositivos UEFI pode exigir que você execute etapas adicionais. Especificamente, um ambiente UEFI nativo exige que você crie várias partições no disco de inicialização do sistema. Se você estiver acompanhando com a [documentação da mídia em pré-teste](https://technet.microsoft.com/library/79465d90-4831-4872-96c2-2062d80f5583?f=255&MSPPError=-2147217396#BKMK_CreatePrestagedMedia), as instruções fornecidas serão apenas para discos de inicialização de partição única e, portanto, falharão quando aplicadas aos dispositivos de superfície.

Instruções para aplicar a mídia em pré-teste a dispositivos UEFI, como dispositivos de superfície, podem ser encontradas na postagem em [como aplicar a mídia de pré-teste de sequência de tarefas em discos de várias partições para computadores BIOS ou UEFI na postagem de blog do Microsoft Endpoint Configuration Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2014/04/02/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned-disks-for-bios-or-uefi-pcs-in-system-center-configuration-manager/) .

##  <a name="licensing-conflicts-with-oem-activation-3.0"></a>Conflitos de licenciamento com a ativação do OEM 3,0

Os dispositivos Surface vêm pré-instalados com uma cópia licenciada do Windows. Por exemplo, Surface Pro 4 vem pré-instalado com o Windows 10 Professional. A chave de licença para esta cópia pré instalada do Windows está incorporada no firmware do dispositivo com a ativação do OEM 3,0 (OA 3,0). Quando você executa a mídia de instalação do Windows em um dispositivo com uma chave OA 3,0, a instalação do Windows lê automaticamente a chave de licença e a usa para instalar e ativar o Windows. Na maioria dos casos, isso simplifica a reinstalação do Windows, porque o usuário não precisa localizar ou inserir uma chave de licença.

Ao refazer a nova imagem de um dispositivo usando o Windows Enterprise, essa chave de licença inserida não causa um conflito. Isso ocorre porque a mídia de instalação do Windows Enterprise está configurada para instalar apenas uma edição empresarial do Windows e, portanto, é incompatível com a chave de licença incorporada no firmware do sistema. Se uma chave do produto (Product Key) não for especificada (por exemplo, quando você pretende ativar com o serviço de gerenciamento de chaves [KMS] ou a ativação do Active Directory), uma chave de licença de volume genérica (CSVLK) será usada até que o Windows seja ativado por uma dessas tecnologias.

No entanto, os problemas podem surgir quando as organizações pretendem usar versões do Windows compatíveis com a chave incorporada do firmware. Por exemplo, uma organização que quer instalar o Windows 10 Professional em um dispositivo Surface 3 que originalmente veio com o Windows 10 Home Edition pode ter dificuldade quando a instalação do Windows lê automaticamente a chave Home Edition durante a instalação e é instalada como Home Edition, em vez de profissional. Para evitar esse conflito, você pode usar o arquivo Ei. cfg ou Pid.txt para instruir explicitamente o programa de instalação do Windows a solicitar uma chave do produto ou pode inserir uma chave do produto específica na sequência de tarefas de implantação. Para obter mais informações, consulte [configuração da Windows Setup Edition e arquivos de ID do produto](https://technet.microsoft.com/library/hh824952.aspx). Se você não tiver uma chave específica, poderá usar as chaves de produto padrão do Windows, que você pode encontrar em [Personalizar e implantar um sistema operacional Windows 10](https://dpcenter.microsoft.com/en/Windows/Build/cp-Windows-10-build) no Device Partner Center.

##  <a name="apply-an-asset-tag-during-deployment"></a>Aplicar uma marca de ativo durante a implantação

Os dispositivos Surface Studio, Surface Book, Surface Pro 4, Surface Pro 3 e Surface 3 dão suporte à aplicação de uma marca de ativos em UEFI. Essa marca de ativos pode ser usada para identificar o dispositivo da UEFI, mesmo que o sistema operacional falhe e também pode ser consultado no sistema operacional. Para ler mais sobre a função de marca de ativos de superfície, consulte a ferramenta de marca de ativos para a postagem [do blog do Surface Pro 3](https://blogs.technet.microsoft.com/askcore/2014/10/20/asset-tag-tool-for-surface-pro-3/) .

Para aplicar uma marca de ativos usando o [utilitário CLI de marca de ativos de superfície](https://www.microsoft.com/download/details.aspx?id=44076) durante uma sequência de tarefas de implantação do Configuration Manager, use o script e as instruções encontradas na marca de ativos de superfície de conjunto, durante uma postagem de blog de [sequência de tarefas do Configuration Manager](https://blogs.technet.microsoft.com/jchalfant/set-surface-pro-3-asset-tag-during-a-configuration-manager-task-sequence/) .

##  <a name="configure-push-button-reset"></a>Configurar a redefinição do botão de ação

Quando você implanta o Windows em um dispositivo de superfície, a funcionalidade de redefinição de botão pressionado do Windows é configurada por padrão para reverter o sistema para um estado em que o ambiente ainda não está configurado. Quando a função reset for usada, o sistema descartará todos os aplicativos e configurações instalados. Embora, em algumas situações, seja benéfico restaurar o sistema a um estado sem aplicativos e configurações, em um ambiente profissional, isso efetivamente torna o sistema inutilizável para o usuário final.

A redefinição do botão pode ser configurada, entretanto, para restaurar a configuração do sistema a um estado em que ele está pronto para ser usado pelo usuário final. Siga o processo descrito em [implantar recursos de redefinição de botão de ação](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/deploy-push-button-reset-features) para personalizar a experiência de redefinição de botão de ação para seus dispositivos.
