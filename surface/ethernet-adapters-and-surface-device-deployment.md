---
title: Adaptadores Ethernet e implantação do Surface (Surface)
description: Este artigo fornece orientação e respostas para ajudá-lo a executar uma implantação de rede para dispositivos Surface.
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: ethernet, implantar, removível, rede, conectividade, inicialização, firmware, dispositivo, adaptador, inicialização PXE, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 4b0cfd9cadab33d82ae3d0acaa83e007229c6fb8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830279"
---
# Adaptadores Ethernet e implantação do Surface


Este artigo fornece orientação e respostas para ajudá-lo a realizar uma implantação de rede para dispositivos de superfície, incluindo Surface Pro 3 e posterior.

A implantação de rede para dispositivos Surface pode gerar alguns desafios únicos para os administradores do sistema. Devido à falta de um adaptador Ethernet com fio nativo, os administradores devem fornecer conectividade por meio de um adaptador Ethernet removível.

##  <a name="select-an-ethernet-adapter-for-surface-devices"></a>Selecionar um adaptador Ethernet para dispositivos Surface


Para você possa abordar as preocupações sobre como executará a inicialização no ambiente de implantação ou como os dispositivos serão reconhecidos por sua solução de implantação, você precisa usar um adaptador de rede com fio.

A principal preocupação ao selecionar um adaptador Ethernet é como o adaptador inicializará o dispositivo Surface por meio da rede. Se você estiver pré-preparando clientes com os serviços de implantação do Windows (WDS) ou se estiver usando o Gerenciador de configuração do Microsoft EndPoint, talvez também queira considerar se os adaptadores Ethernet removíveis serão dedicados a um dispositivo de superfície específico ou compartilhados entre vários dispositivos. Para obter mais informações sobre possíveis conflitos com adaptadores compartilhados, consulte [gerenciar endereços MAC com adaptadores Ethernet removíveis](#manage-mac-addresses) mais adiante neste artigo.

A inicialização por meio da rede (inicialização PXE) tem suporte apenas quando você usa um adaptador Ethernet ou uma base de encaixe da Microsoft. Para inicializar da rede, o chipset no adaptador Ethernet ou encaixe deve ser detectado e configurado como um dispositivo de inicialização no firmware do dispositivo Surface. Os adaptadores Ethernet da Microsoft, como o adaptador Ethernet Surface e o [Encaixe do Surface](https://www.microsoft.com/surface/accessories/surface-dock), usam um chipset que é compatível com o firmware do Surface.

Os seguintes dispositivos Ethernet têm suporte para a inicialização de rede com dispositivos Surface:

-   Adaptador de superfície USB-C para Ethernet e USB 3,0

-   Surface USB 3,0 para adaptador Gigabit Ethernet

-   Encaixe do Surface

-   Base de Encaixe do Surface 3

-   Base de Encaixe do Surface Pro 3

-   Base de Encaixe do Surface Pro e do Surface Pro 2

Também há suporte a adaptadores Ethernet de terceiros para a implantação de rede, embora eles não deem suporte à inicialização PXE. Para usar um adaptador Ethernet de terceiros, você deve carregar os drivers na imagem de inicialização de implantação e iniciar essa imagem de um dispositivo de armazenamento separado, como um pen drive.

##  <a name="boot-surface-devices-from-the-network"></a>Inicializar dispositivos Surface da rede

Para inicializar da rede ou de um pen drive conectado, você deve instruir o dispositivo Surface a ser inicializado de um dispositivo de inicialização alternativo. Você pode alterar a ordem de inicialização no firmware do sistema para priorizar dispositivos de inicialização USB ou pode instrui-lo a inicializar de um dispositivo de inicialização alternativo durante o processo de inicialização.

Para inicializar um dispositivo Surface por meio de um dispositivo de inicialização alternativo, siga estas etapas:

1.  Verifique se o dispositivo Surface está desligado.
2.  Pressione e segure o botão **Diminuir o Volume**.
3.  Pressione e solte o botão de **Energia**.
4.  Depois que o sistema começa a ser inicializado por meio do pen drive ou adaptador Ethernet, solte o botão **Diminuir o Volume**.

>[!NOTE]
>Além de um adaptador Ethernet, um teclado também deve estar conectado ao dispositivo Surface para que você entre no ambiente de pré-instalação e navegue pelo assistente de implantação.

 
Para o Windows 10, versão 1511 e posterior – incluindo o Kit de Avaliação e Implantação do Windows (Windows ADK) para Windows 10, versão 1511 – os drivers para adaptadores de Ethernet do Microsoft Surface estão presentes por padrão. Se você estiver usando uma solução de implantação que usa o Ambiente de Pré-Instalação do Windows (WinPE), como o Microsoft Deployment Toolkit e inicialização de rede com PXE, certifique-se de que sua solução de implantação esteja usando a versão mais recente do Windows ADK.

## <a href="" id="manage-mac-addresses"></a>Gerenciar endereços MAC com adaptadores Ethernet removíveis

Outra consideração para os administradores que executam a implantação do Windows pela rede é como você identificará os computadores ao usar o mesmo adaptador Ethernet para implantação em mais de um computador. Um identificador comum usado pelas tecnologias de implantação é o endereço MAC (Controle de Acesso à Mídia) que é associado a cada adaptador Ethernet. No entanto, ao usar o mesmo adaptador Ethernet para implantação em vários computadores, você não pode usar uma tecnologia de implantação que inspecione endereços MAC, pois não há maneira de diferenciar o endereço MAC do adaptador removível quando usado em computadores diferentes.

A solução mais simples para evitar conflitos de endereço MAC é fornecer um adaptador Ethernet removível dedicado para cada dispositivo Surface. Isso pode fazer sentido em muitos cenários em que o adaptador Ethernet ou a funcionalidade adicional da base de encaixe serão usados regularmente. No entanto, nem todos os cenários exigem a conectividade adicional de uma base de encaixe ou o suporte para redes com fio.

Outra solução potencial para evitar conflitos quando adaptadores são compartilhados é usar o [MDT (Microsoft Deployment Toolkit)](https://technet.microsoft.com/windows/dn475741) para executar uma implantação para dispositivos Surface. O MDT não usa o endereço MAC para identificar computadores individuais e, assim, não está sujeito a essa limitação. No entanto, o MDT usa Serviços de Implantação do Windows para fornecer a funcionalidade de inicialização PXE e está sujeito às limitações com relação a clientes previamente preparados, o que é explicado mais adiante nesta seção.

Quando você usa um adaptador compartilhado para implantação, a solução para tecnologias de implantação afetados é usar outros meios para identificar sistemas exclusivos. Para o Gerenciador de Configurações e o WDS, que podem ser afetados por esse problema, a solução é usar o UUID do Sistema (Identificador Exclusivo Universal do Sistema) que é inserido no firmware do computador pelo respectivo fabricante. Para dispositivos Surface, você pode ver essa entrada no firmware do computador em **Informações do Dispositivo**.

Para acessar o firmware de um dispositivo Surface, siga estas etapas:

1.  Verifique se o dispositivo Surface está desligado.
2.  Pressione e segure o botão **Aumentar o Volume**.
3.  Pressione e solte o botão de **Energia**.
4.  Depois que o dispositivo começar a inicialização, solte o botão **Aumentar o Volume**.

Ao se implantar com o WDS, o endereço MAC é usado apenas para identificar um computador quando o servidor de implantação está configurado para responder apenas a clientes conhecidos e previamente preparados. Ao preparar previamente um cliente, um administrador cria uma conta de computador no Active Directory e define esse computador com o endereço MAC ou o UUID do Sistema. Para evitar conflitos de identidade causados por adaptadores Ethernet compartilhados, você deve usar o [UUID do Sistema para definir clientes previamente preparados](https://technet.microsoft.com/library/cc742034). Como alternativa, você pode configurar o WDS para responder a clientes desconhecidos que não necessitam de definição por meio do endereço MAC ou do UUID do sistema marcando a opção **Responder a todos os computadores cliente (conhecidos e desconhecidos)** na guia [**Resposta PXE**](https://technet.microsoft.com/library/cc732360) em **Propriedades do Servidor de Implantação do Windows**.

O risco de conflitos com adaptadores Ethernet compartilhados é muito maior com o Gerenciador de Configurações. Enquanto o WDS usa endereços MAC apenas para definir sistemas individuais quando configurado para fazer isso, o Gerenciador de Configurações usa o endereço MAC para definir sistemas individuais sempre que executa uma implantação em computadores novos ou desconhecidos. Isso pode resultar em dispositivos configurados incorretamente ou até mesmo na incapacidade de implantar mais de um sistema com um adaptador Ethernet compartilhado. Há várias soluções possíveis para esta situação, descritas em detalhes sobre [como usar o mesmo adaptador Ethernet externo para vários OSD do SCCM](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374), uma postagem no blog na infraestrutura principal e no blog de segurança.

 

 





