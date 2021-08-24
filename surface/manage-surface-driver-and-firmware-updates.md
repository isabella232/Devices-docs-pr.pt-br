---
title: Gerenciar e implantar atualizações de driver e firmware do Surface
description: Este artigo explica as opções disponíveis para gerenciar e implantar atualizações de firmware e driver para dispositivos Surface.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, atualização, dispositivo, gerenciar, implantar, driver, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 10/12/2020
ms.openlocfilehash: afc7b2e82519fb42ca07b107bff73ddea894cfdf
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911636"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>Gerenciar e implantar atualizações de driver e firmware do Surface

A forma como você gerencia as atualizações de driver e firmware do Surface varia dependendo do ambiente e dos requisitos organizacionais. Em dispositivos Surface, o firmware é exposto ao sistema operacional como um driver e fica visível no Gerenciador de Dispositivos. Isso permite que o firmware do dispositivo e os drivers sejam atualizados automaticamente usando o Windows Update ou Windows Update for Business. Embora essa abordagem simplificada possa ser viável para startups e pequenas ou médias empresas, as organizações maiores geralmente precisam de administradores de TI para distribuir atualizações internamente. Isso pode envolver planejamento abrangente, testes de compatibilidade de aplicativos e pilotagem e validação de atualizações antes da aprovação final e distribuição na rede.

> [!NOTE]
> Este artigo destina-se a agentes de suporte técnico e profissionais de TI e se aplica somente a dispositivos Surface. Se você estiver procurando ajuda para instalar atualizações do Surface ou firmware em um dispositivo home, consulte [Update Surface firmware and Windows 10](https://support.microsoft.com/help/4023505).

Embora as soluções de distribuição de software de nível empresarial continuem a evoluir, a lógica de negócios para gerenciar as atualizações centralmente permanece a mesma: manter a segurança dos dispositivos Surface e mantê-los atualizados com as melhorias mais recentes do sistema operacional e dos recursos. Isso é essencial para manter um ambiente de produção estável e garantir que os usuários não sejam impedidos de serem produtivos. Este artigo fornece uma visão geral das ferramentas e processos recomendados para que organizações maiores realizem essas metas.

## <a name="central-update-management-in-commercial-environments"></a>Gerenciamento de atualizações centrais em ambientes comerciais

A Microsoft tem ferramentas simplificadas para gerenciar dispositivos , incluindo atualizações [](https://devicemanagement.microsoft.com/) de driver e firmware, em uma única experiência unificada chamada Microsoft Endpoint Manager centro de administração e acessada a partir [do devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home).

### <a name="manage-updates-with-configuration-manager-and-intune"></a>Gerenciar atualizações com o Configuration Manager e o Intune

Microsoft Endpoint Configuration Manager permite sincronizar e implantar atualizações de firmware e driver do Surface com o cliente do Configuration Manager. A integração Microsoft Intune permite que você veja todos os dispositivos gerenciados, co-gerenciados e gerenciados por parceiros em um só lugar. Essa é a solução recomendada para grandes organizações gerenciarem atualizações do Surface.

Para etapas detalhadas, consulte os seguintes recursos:

- [Atualizações do driver do Surface no Gerenciador de Configurações](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Implantar aplicativos com o Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentação do Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Gerenciar atualizações com o Microsoft Deployment Toolkit

O Microsoft Deployment Toolkit (MDT) está incluído no Endpoint Configuration Manager. Ele contém ferramentas de implantação opcionais que você pode querer usar, dependendo do seu ambiente. Eles incluem Windows Kit de Avaliação e Implantação (Windows ADK), Windows System Image Manager (Windows SIM), Serviço e Gerenciamento de Imagens de Implantação (DISM) e USMT (User State Migration Tool). Você pode baixar a versão mais recente do MDT na página de download do [Microsoft Deployment Toolkit download](https://www.microsoft.com/download/details.aspx?id=54259).

Para etapas detalhadas, consulte os seguintes recursos:

- [Documentação Toolkit microsoft deployment](https://docs.microsoft.com/configmgr/mdt/)
- [Implantar o Windows 10 com o Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implantar Windows 10 em dispositivos Surface com o Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

As atualizações do driver e do firmware do Surface são empacotados Windows arquivos do Instalador (*.msi). Para implantar esses pacotes Windows Instalador, você pode usar o Gerenciador de Configuração do Ponto de Extremidade ou o MDT. Para obter informações sobre como selecionar o arquivo .msi correto para um dispositivo e sistema operacional, consulte as orientações nas seções a seguir sobre como baixar arquivos .msi.

Para obter instruções sobre como implantar atualizações usando o Endpoint Configuration Manager, consulte [Deploy applications with Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications). Para obter instruções sobre como implantar atualizações usando o MDT, consulte [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**Firmware e drivers do WindowsPE e Surface**

O Endpoint Configuration Manager e o MDT usam o Ambiente Windows de Pré-instalação (WindowsPE) durante o processo de implantação. O WindowsPE oferece suporte apenas a um conjunto limitado de drivers básicos, como aqueles para adaptadores de rede e controladores de armazenamento. Drivers para Windows componentes que não fazem parte do WindowsPE podem gerar erros. Como prática prática, você pode evitar esses erros configurando o processo de implantação para usar apenas os drivers necessários durante a fase do WindowsPE.

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

A partir do Gerenciador de Configuração do Ponto de Extremidade, você pode sincronizar e implantar atualizações de firmware e driver do Microsoft Surface usando o cliente do Configuration Manager. Para obter informações adicionais, consulte KB 4098906, [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## <a name="supported-devices"></a>Dispositivos com suporte

Os arquivos .msi de download estão disponíveis para dispositivos Surface Pro 2 e posteriores (exceto Surface Pro X que executa Windows 10 em ARM).

## <a name="managing-firmware-with-dfci"></a>Gerenciando firmware com DFCI

Ao ter perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados ao Intune (agora disponível na visualização [pública),](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)o gerenciamento uefi do Surface estende a pilha de gerenciamento moderna até o nível de hardware UEFI. O DFCI dá suporte ao provisionamento de toque zero, elimina senhas de BIOS, fornece controle de configurações de segurança (incluindo opções de inicialização e periféricos integrados) e estabelece as bases para cenários avançados de segurança no futuro. Para obter mais informações, consulte os seguintes artigos:

- [Gerenciamento pelo Intune das configurações de UEFI do Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Anunciando o gerenciamento remoto das configurações uefi do Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## <a name="best-practices-for-update-deployment-processes"></a>Práticas recomendadas para atualizar processos de implantação

Para manter um ambiente estável, é recomendável manter a paridade com a versão mais recente do Windows 10.  Para recomendações de práticas, consulte [Build deployment rings for Windows 10 updates](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).

## <a name="downloadable-surface-update-packages"></a>Pacotes de atualização do Surface baixáveis

Versões específicas Windows 10 arquivos .msi, cada uma contendo todas as atualizações de driver e firmware cumulativas necessárias para dispositivos Surface. Os pacotes de atualização podem incluir alguns ou todos os seguintes componentes:

- Wi-Fi e LTE
- Vídeo
- Unidade de estado sólido
- Módulo de agregação do sistema (SAM)
- Bateria
- Controlador de teclado
- Controlador incorporado (EC)
- Mecanismo de gerenciamento (ME)
- Interface de firmware extensível unificada (UEFI)

### <a name="downloading-msi-files"></a>Baixando .msi arquivos

1. Navegue [até Baixar drivers e firmware do Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) no Centro de Download da Microsoft.
2. Selecione o .msi de arquivo que corresponde ao modelo surface e à versão Windows. O .msi de arquivo inclui o número de com build mínimo Windows necessário para instalar os drivers e o firmware. Por exemplo, consulte a figura a seguir. Para atualizar um Surface Book 2 com build 18362 de Windows 10, **escolhaSurfaceBook2_Win10_18362_19.101.13994.msi.** Para um Surface Book 2 com build 16299 de Windows 10, **escolhaSurfaceBook2_Win10_16299_1803509_3.msi**.

    ![Figura 1. Baixando atualizações do Surface.](images/fig1-downloads-msi.png)

    *Figura 1. Baixando atualizações do Surface*

### <a name="surface-msi-naming-convention"></a>Convenção .msi de nomenis do Surface

Desde agosto de 2019, .msi arquivos estão usando a seguinte convenção de nomeniso:

- *Product*_*Windows release Windows*_ build*number*_*Version number*_ Revisão do número da versão *(normalmente zero)*.

**Exemplo**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Este nome de arquivo fornece as seguintes informações:

- **Produto:** SurfacePro6
- **Windows versão:** Win10
- **Build:** 18362
- **Versão:** 19.073.44195 – Isso mostra a data e a hora em que o arquivo foi criado, da seguinte forma:
  - **Ano:** 19 (2019)
  - **Mês e semana:** 073 (terceira semana de julho)
  - **Minuto do mês:** 44195
- **Revisão da versão:** 0 (primeira versão desta versão)

### <a name="legacy-surface-msi-naming-convention"></a>Convenção de nomenis do Surface .msi herdada

Arquivos .msi herdados (arquivos que foram construídos antes de agosto de 2019) seguiram a mesma fórmula de nomenrção geral, mas usaram um método diferente para derivar o número da versão.

**Exemplo**

- SurfacePro6_Win10_16299_1900307_0.msi

Este nome de arquivo fornece as seguintes informações:

- **Produto:** SurfacePro6
- **Windows versão:** Win10
- **Build:** 16299
- **Versão:** 1900307 – Mostra a data em que o arquivo foi criado e sua posição na sequência de lançamento, da seguinte forma:
  - **Ano:** 19 (2019)
  - **Número de lançamento:** 003 (terceira versão do ano)
  - **Número da versão do produto:** 07 (Surface Pro 6 é oficialmente a sétima versão do Surface Pro)
- **Revisão da versão:** 0 (primeira versão desta versão)

## <a name="learn-more"></a>Saiba mais

- [Baixar drivers e firmware para Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Como gerenciar atualizações de driver do Surface no Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Implantar aplicativos com o Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentação do Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/)
- [Documentação Toolkit microsoft deployment](https://docs.microsoft.com/configmgr/mdt/)
- [Implantar o Windows 10 com o Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implantar Windows 10 em dispositivos Surface com o Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Gerenciamento pelo Intune das configurações de UEFI do Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Anunciando o gerenciamento remoto das configurações uefi do Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).
- [Criar anéis de implantação para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
