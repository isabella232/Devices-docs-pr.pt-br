---
title: Gerenciar atualizações de driver e firmware do Surface
description: Este artigo descreve as opções disponíveis para gerenciar e implantar firmware e atualizações de driver para dispositivos Surface.
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
ms.openlocfilehash: 91cde5fdf4a7745d491bd2eb928baca75955b90d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830373"
---
# Gerenciar atualizações de driver e firmware do Surface

A maneira como você gerencia as atualizações de driver de superfície e firmware varia dependendo do ambiente e dos requisitos organizacionais. Em dispositivos de superfície, o firmware é exposto ao sistema operacional como um driver e fica visível no Gerenciador de dispositivos, permitindo que o firmware e os drivers do dispositivo sejam atualizados automaticamente usando o Windows Update ou o Windows Update for Business. Embora essa abordagem simplificada possa ser viável para as inicializações e empresas de pequeno e médio porte, as organizações maiores geralmente precisam dos administradores de ti para distribuir as atualizações internamente. Isso pode envolver planejamento abrangente, teste de compatibilidade de aplicativos, piloto e validação de atualizações, antes da aprovação e distribuição finais em toda a rede.

> [!NOTE]
> Este artigo destina-se a agentes de suporte técnico e profissionais de ti e aplica-se somente a dispositivos Surface. Se você estiver procurando ajuda para instalar as atualizações da superfície ou o firmware em um dispositivo doméstico, consulte [atualizar o firmware da superfície e o Windows 10](https://support.microsoft.com/help/4023505).

Embora as soluções de distribuição de software de nível empresarial continuem a evoluir, a lógica dos negócios para o gerenciamento centralizado das atualizações continua sendo a mesma: Mantenha a segurança dos dispositivos de superfície e mantenha-os atualizados com os mais recentes aprimoramentos de recursos e sistema operacional. Isso é essencial para sustentar um ambiente de produção estável e garantir que os usuários não sejam tão produtivos. Este artigo fornece uma visão geral de ferramentas e processos recomendados para organizações maiores para alcançar essas metas.

## Gerenciamento de atualizações centrais em ambientes comerciais

A Microsoft tem ferramentas simplificadas para o gerenciamento de dispositivos, incluindo atualizações de driver e firmware, em uma única experiência unificada chamada [centro de administração do Microsoft Endpoint Manager](https://devicemanagement.microsoft.com/) acessada a partir do devicemanagement.Microsoft.com.

### Gerenciar atualizações com o Configuration Manager e o Intune

O Gerenciador de configuração do Microsoft Endpoint permite sincronizar e implantar o firmware de superfície e atualizações de driver com o cliente do Configuration Manager. A integração com o Microsoft Intune permite que você veja todos os dispositivos gerenciados, cogerenciados e gerenciados por parceiros em um só lugar. Esta é a solução recomendada para grandes organizações gerenciar atualizações de superfície.

Para obter etapas detalhadas, confira os seguintes recursos:

- [Como gerenciar atualizações de driver de superfície no Configuration Manager](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Implantar aplicativos com o Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentação do Gerenciador de configuração de ponto de extremidade](https://docs.microsoft.com/configmgr/)

### Gerenciar atualizações com o Microsoft Deployment Toolkit

Incluído no Endpoint Configuration Manager, o Microsoft Deployment Toolkit (MDT) contém ferramentas de implantação opcionais que você pode querer usar dependendo do seu ambiente. Isso inclui o kit de avaliação e implantação do Windows (Windows ADK), o Gerenciador de imagem de sistema do Windows (Windows SIM), o gerenciamento e manutenção de imagens de implantação (DISM) e a ferramenta de migração de estado do usuário (USMT). Você pode baixar a versão mais recente do MDT na [página de download do kit de ferramentas de implantação da Microsoft](https://www.microsoft.com/download/details.aspx?id=54259).

Para obter etapas detalhadas, confira os seguintes recursos:

- [Documentação do kit de ferramentas de implantação da Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Implantar o Windows 10 com o Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implantar o Windows 10 em dispositivos de superfície com o kit de ferramentas de implantação da Microsoft](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

As atualizações de driver Surface e firmware são empacotadas como arquivos do Windows Installer (*. msi). Para implantar esses pacotes do Windows Installer, você pode usar o Gerenciador de configuração de ponto de extremidade ou o MDT. Para obter informações sobre como selecionar o arquivo. msi correto para um dispositivo e sistema operacional, Confira as diretrizes abaixo sobre o download de arquivos. msi.

Para obter instruções sobre como implantar atualizações usando o Gerenciador de configuração de ponto de extremidade, consulte [implantar aplicativos com o Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications). Para obter instruções sobre como implantar atualizações usando o MDT, consulte [implantar uma imagem do Windows 10 usando o MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**Firmware e drivers do WindowsPE e do Surface**

O Gerenciador de configuração de ponto de extremidade e o MDT usam o ambiente de pré-instalação do Windows (WindowsPE) durante o processo de implantação. O WindowsPE só oferece suporte a um conjunto limitado de drivers básicos, como os de adaptadores de rede e controladores de armazenamento. Os drivers para componentes do Windows que não fazem parte do WindowsPE podem produzir erros. Como prática recomendada, você pode evitar esses erros Configurando o processo de implantação para usar somente os drivers obrigatórios durante a fase WindowsPE.

### Endpoint Configuration Manager

Iniciando no Gerenciador de configuração de ponto de extremidade, você pode sincronizar e implantar o firmware de superfície da Microsoft e atualizações de driver usando o cliente do Configuration Manager. Para obter informações adicionais, consulte KB 4098906, [como gerenciar atualizações de driver de superfície no Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## Dispositivos com suporte

Os arquivos. msi disponíveis para download estão disponíveis para dispositivos de superfície do Surface Pro 2 e posteriores. As informações sobre os arquivos. msi dos dispositivos de superfície mais recentes, como Surface Pro 7, Surface Pro X e Surface laptop 3, estarão disponíveis nesta página ao soltar.

## Gerenciando o firmware com o DFCI

Com os perfis da interface de configuração de firmware do dispositivo (DFCI) incorporados ao Intune (agora disponível em [Visualização pública](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), o gerenciamento de UEFI da superfície estende a pilha de gerenciamento moderno para o nível de hardware UEFI. O DFCI é compatível com o provisionamento de Zero Touch, elimina as senhas do BIOS, fornece o controle das configurações de segurança, incluindo opções de inicialização e periféricos incorporados, e prepara a base para cenários de segurança avançada no futuro. Para obter mais informações, consulte:

- [Gerenciamento pelo Intune das configurações de UEFI do Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: anunciando o gerenciamento remoto de configurações de controle de Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## Práticas recomendadas para processos de atualização de implantação

Para manter um ambiente estável, é altamente recomendável manter a paridade com a versão mais recente do Windows 10.  Para obter recomendações de práticas recomendadas, consulte [criar toques de implantação para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).

## Pacotes de atualização de superfície para download

Versões específicas do Windows 10 têm arquivos. msi separados, cada um contendo todas as atualizações de driver cumulativo e firmware necessárias para dispositivos Surface. Os pacotes de atualização podem incluir alguns ou todos os seguintes componentes:

- Wi-Fi e LTE
- Vídeo
- Unidade de estado sólido
- Módulo agregador de sistema (SAM)
- Bateria
- Controlador de teclado
- Controlador incorporado (EC)
- Mecanismo de gerenciamento (eu)
- Unified Extensible Firmware Interface (UEFI)

### Baixando arquivos. msi

1. Navegue até [baixar drivers e firmware para o Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) no centro de download da Microsoft.
2. Selecione o nome do arquivo. msi que corresponda ao modelo de superfície e à versão do Windows. O nome do arquivo. msi inclui o número mínimo de compilação do Windows com suporte necessário para instalar os drivers e o firmware. Por exemplo, conforme mostrado na figura a seguir, para atualizar um livro Surface 2 com Build 18362 do Windows 10, escolha **SurfaceBook2_Win10_18362_19.101.13994.msi.** Para um livro Surface 2 com Build 16299 do Windows 10, escolha **SurfaceBook2_Win10_16299_1803509_3.msi**.

    ![Figura 1. Baixando atualizações de superfície](images/fig1-downloads-msi.png)

    *Figura 1. Baixando atualizações de superfície*

### Convenção de nomenclatura Surface. msi

Desde que os arquivos. msi de agosto de 2019, tenham usado a seguinte convenção de nomenclatura:

- *Product*_*Lançamento do Windows versão*_*número*da_*versão*_*do número da versão revisão do número da versão (geralmente zero)*.

**Exemplo**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Este nome de arquivo fornece as seguintes informações:

- **Produto:** SurfacePro6
- **Versão do Windows:** Win10
- **Build:** 18362
- **Versão:** 19.073.44195 – mostra a data e a hora em que o arquivo foi criado, da seguinte maneira:
  - **Ano:** 19 (2019)
  - **Mês e semana:** 073 (terceira semana de julho)
  - **Minuto do mês:** 44195
- **Revisão da versão:** 0 (primeiro lançamento desta versão)

### Convenção de nomenclatura do Surface. msi herdada

Os arquivos. msi herdados (arquivos criados antes de agosto de 2019) seguimos a mesma fórmula de nomenclatura geral, mas usaram um método diferente para gerar o número da versão.

**Exemplo**

- SurfacePro6_Win10_16299_1900307_0.msi

Este nome de arquivo fornece as seguintes informações:

- **Produto:** SurfacePro6
- **Versão do Windows:** Win10
- **Build:** 16299
- **Versão:** 1900307 – mostra a data em que o arquivo foi criado e sua posição na sequência de versões, da seguinte maneira:
  - **Ano:** 19 (2019)
  - **Número da versão:** 003 (terceiro lançamento do ano)
  - **Número da versão do produto:** 07 (Surface pro 6 é oficialmente a sétima versão do Surface pro)
- **Revisão da versão:** 0 (primeiro lançamento desta versão)

## Saiba mais

- [Baixar drivers e firmware para Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Como gerenciar atualizações de driver de superfície no Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Implantar aplicativos com o Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentação do Gerenciador de configuração de ponto de extremidade](https://docs.microsoft.com/configmgr/)
- [Documentação do kit de ferramentas de implantação da Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Implantar o Windows 10 com o Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implantar o Windows 10 em dispositivos de superfície com o kit de ferramentas de implantação da Microsoft](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Gerenciamento pelo Intune das configurações de UEFI do Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: anunciando o gerenciamento remoto de configurações de controle de Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).
- [Criar anéis de implantação para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
