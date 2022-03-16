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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ec73d437d2784ffbceb350f38507524e761df8dd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448474"
---
# <a name="ethernet-adapters-and-surface-deployment"></a>Adaptadores Ethernet e implantação do Surface

Este artigo descreve como executar uma implantação de rede dos dispositivos Surface mais recentes, incluindo Surface Pro 3 e posteriores.

A implantação de rede para dispositivos Surface pode gerar alguns desafios únicos para os administradores do sistema. Devido à falta de um adaptador Ethernet com fio nativo, os administradores devem fornecer conectividade por meio de um adaptador Ethernet removível.

## <a name="select-an-ethernet-adapter-for-surface-devices"></a>Selecionar um adaptador Ethernet para dispositivos Surface

Para você possa abordar as preocupações sobre como executará a inicialização no ambiente de implantação ou como os dispositivos serão reconhecidos por sua solução de implantação, você precisa usar um adaptador de rede com fio.

Ao selecionar adaptadores Ethernet, a principal preocupação é como os adaptadores inicializam seus dispositivos Surface da rede. Suponha que você está pré-preparação de clientes com Windows de Implantação (WDS) ou usando Microsoft Endpoint Configuration Manager. Nesse caso, você também pode considerar se os adaptadores Ethernet removíveis serão dedicados a um dispositivo Surface específico ou compartilhados entre vários dispositivos. Para obter mais informações sobre possíveis conflitos com adaptadores compartilhados, consulte Gerenciar endereços MAC com adaptadores [Ethernet](#manage-mac-addresses) removíveis posteriormente neste artigo.

A inicialização da rede (inicialização PXE) só é suportada ao usar um adaptador Ethernet ou uma estação de encaixe da Microsoft. O chipset no adaptador Ethernet ou dock deve ser detectado e configurado como um dispositivo de inicialização no firmware do dispositivo Surface. Os adaptadores Ethernet da Microsoft, como o Adaptador Surface Ethernet e o [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock), usam um chipset compatível com o firmware do Surface.

Os seguintes dispositivos Ethernet têm suporte para a inicialização de rede com dispositivos Surface:

- Surface USB-C para Ethernet e Adaptador USB 3.0
- Surface USB 3.0 para Adaptador Ethernet Gigabit
- Microsoft USB-C Travel Hub
- Encaixe do Surface
- Surface Dock 2
- Estação de encaixe do Surface 3
- Docking Station for Surface Pro 3 
- Base de Encaixe do Surface Pro e do Surface Pro 2

Também há suporte a adaptadores Ethernet de terceiros para a implantação de rede, embora eles não deem suporte à inicialização PXE. Para usar um adaptador Ethernet de terceiros, você deve carregar os drivers na imagem de inicialização de implantação e iniciar essa imagem de inicialização de um dispositivo de armazenamento separado, como um pen drive.

## <a name="boot-surface-devices-from-the-network"></a>Inicializar dispositivos Surface da rede

Para inicializar da rede ou de um pen drive conectado, você deve instruir o dispositivo Surface a ser inicializado de um dispositivo de inicialização alternativo. Você pode alterar a ordem de inicialização no firmware do sistema para priorizar dispositivos de inicialização USB ou inicialização de um dispositivo de inicialização alternativo durante o processo de inicialização.

**Para inicializar de um dispositivo de inicialização alternativo:**

1. Verifique se o dispositivo Surface está desligado.
2. Pressione e segure o botão **Diminuir o Volume**.
3. Pressione e solte o botão de **Energia**.
4. Depois que o sistema começa a ser inicializado por meio do pen drive ou adaptador Ethernet, solte o botão **Diminuir o Volume**.

>[!NOTE]
>Além de um adaptador Ethernet, um teclado também deve estar conectado ao dispositivo Surface para que você entre no ambiente de pré-instalação e navegue pelo assistente de implantação.

Para o Windows 10, versão 1511 e posterior – incluindo o Kit de Avaliação e Implantação do Windows (Windows ADK) para Windows 10, versão 1511 – os drivers para adaptadores de Ethernet do Microsoft Surface estão presentes por padrão. Se você estiver usando uma solução de implantação que usa o WinPE (Ambiente de Pré-instalação do Windows), como o Microsoft Deployment Toolkit, e a inicialização da rede com PXE, verifique se sua solução de implantação usa a versão mais recente do ADK do Windows.

## <a name="manage-mac-addresses-with-removable-ethernet-adapters"></a><a href="" id="manage-mac-addresses"></a>Gerenciar endereços MAC com adaptadores Ethernet removíveis

Outra consideração para os administradores que executam Windows implantação na rede é identificar computadores ao usar o mesmo adaptador Ethernet para implantar em mais de um computador. Um identificador comum usado pelas tecnologias de implantação é o endereço MAC (Controle de Acesso de Mídia) associado a cada adaptador Ethernet. No entanto, quando você usa o mesmo adaptador Ethernet para implantar em vários computadores, não é possível usar uma tecnologia de implantação que inspeciona endereços MAC porque não há como diferenciar o endereço MAC do adaptador removível quando usado em computadores diferentes.

A solução mais simples para evitar conflitos de endereço MAC é fornecer um adaptador Ethernet removível dedicado para cada dispositivo Surface. Isso pode fazer sentido em muitos cenários em que o adaptador Ethernet ou a funcionalidade adicional da base de encaixe serão usados regularmente. No entanto, nem todos os cenários exigem a conectividade adicional de uma base de encaixe ou o suporte para redes com fio.

Outra solução potencial para evitar conflitos quando adaptadores são compartilhados é usar o [MDT (Microsoft Deployment Toolkit)](/mem/configmgr/mdt) para executar uma implantação para dispositivos Surface. O MDT não usa o endereço MAC para identificar computadores individuais e, assim, não está sujeito a essa limitação. No entanto, o MDT usa os serviços de implantação Windows para fornecer a funcionalidade de inicialização PXE e está sujeito às limitações em relação a clientes pré-em estágios, conforme descrito posteriormente nesta seção.

Quando você usa um adaptador compartilhado para implantação, a solução para tecnologias de implantação afetados é usar outros meios para identificar sistemas exclusivos. Para o Configuration Manager e o WDS, ambos podem ser afetados por esse problema, a solução é usar o Identificador Universal exclusivo do sistema (UUID) incorporado no firmware do computador pelo fabricante do computador. Para dispositivos Surface, você pode ver essa entrada no firmware do computador em **Informações do Dispositivo**.

**Para acessar o firmware de um dispositivo Surface:**

1. Verifique se o dispositivo Surface está desligado.
2. Pressione e segure o botão **Aumentar o Volume**.
3. Pressione e solte o botão de **Energia**.
4. Depois que o computador começar a inicializar, solte o **botão Volume Up** .

Ao se implantar com o WDS, o endereço MAC é usado apenas para identificar um computador quando o servidor de implantação está configurado para responder apenas a clientes conhecidos e previamente preparados. Ao preparar previamente um cliente, um administrador cria uma conta de computador no Active Directory e define esse computador com o endereço MAC ou o UUID do Sistema. Para evitar conflitos de identidade causados por adaptadores Ethernet compartilhados, você deve usar o [UUID do Sistema para definir clientes previamente preparados](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc742034(v=ws.11)). 

Como alternativa, você pode configurar o WDS para responder a clientes desconhecidos que não exigem definição por endereço MAC ou UUID do sistema. Selecione a **opção Responder a todos os computadores cliente (conhecidos e desconhecidos)** na guia [**Resposta PXE**](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732360(v=ws.11)) **em Windows Propriedades do Servidor de Implantação**.

O risco de conflitos com adaptadores Ethernet compartilhados é muito maior com o Gerenciador de Configurações. Onde o WDS usa apenas endereços MAC para definir sistemas individuais, o Configuration Manager usa o endereço MAC para definir sistemas separados sempre que estiver implantando em computadores novos ou desconhecidos. Isso pode resultar em dispositivos configurados incorretamente ou até mesmo na incapacidade de implantar mais de um sistema com um adaptador Ethernet compartilhado. Várias soluções possíveis para essa situação são descritas em detalhes em [How to Use The Same External Ethernet Adapter for Multiple SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374).
