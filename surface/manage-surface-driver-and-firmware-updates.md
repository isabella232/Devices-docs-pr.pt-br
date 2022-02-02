---
title: Gerenciar e implantar atualizações de driver e firmware do Surface
description: Este artigo fornece links para pacotes baixáveis que contêm atualizações de driver e firmware para dispositivos Surface e explica as soluções de gerenciamento e implantação disponíveis.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 8, Surface Go, Surface Laptop, Surface Studio, Surface Pro 3, firmware, atualização, dispositivo, gerenciar, implantar, driver, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 12/14/2021
ms.openlocfilehash: 6cfe5f44c156c8042172741739fffbfed3ceba07
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338574"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>Gerenciar e implantar atualizações de driver e firmware do Surface

A forma como você gerencia as atualizações de driver e firmware do Surface pode variar dependendo do ambiente e dos requisitos organizacionais. Em organizações maiores, os administradores de TI normalmente organizam implantações internamente e alocam tempo para testar atualizações antes de locá-las para dispositivos de usuário.

> [!NOTE]
> Este artigo destina-se a profissionais de TI e agentes de suporte técnico e se aplica somente a dispositivos Surface. Se você estiver procurando ajuda para instalar atualizações do Surface ou firmware em um dispositivo home, consulte [Baixar drivers e firmware para Surface](https://support.microsoft.com/help/4023505).

Embora as soluções de distribuição de software de nível empresarial continuem a evoluir, a lógica de negócios para gerenciar as atualizações centralmente permanece a mesma: manter a segurança dos dispositivos Surface e mantê-los atualizados com as melhorias mais recentes do sistema operacional e dos recursos. Isso é essencial para manter um ambiente de produção estável e garantir que os usuários não sejam impedidos de serem produtivos.

## <a name="whats-in-surface-driver-and-firmware-updates"></a>O que há em atualizações de firmware e driver do Surface

Windows arquivos .msi do Instalador contêm todas as atualizações cumulativas necessárias de driver e firmware para dispositivos Surface. Os pacotes de atualização podem incluir alguns ou todos os seguintes componentes:

- Wi-Fi e LTE
- Vídeo
- Unidade de estado sólido
- Módulo de agregação do sistema (SAM)
- Bateria
- Controlador de teclado
- Controlador incorporado (EC)
- Mecanismo de gerenciamento (ME)
- Interface de firmware extensível unificada (UEFI)

## <a name="download-msi-files"></a>Baixar .msi arquivos

Esta seção fornece links diretos para pacotes baixáveis que contêm atualizações de driver e firmware para dispositivos Surface. 

1. Selecione Windows 10 ou Windows 11 conforme apropriado. 
2. Para dispositivos com vários arquivos .msi, selecione o nome do arquivo .msi que corresponde ao modelo surface e à versão do Windows implantado em sua organização.  


| Dispositivo Surface                                                                                                                                        | Download de .msi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Pro**                                                                                                                                       | - [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)<br>- [Surface Pro 7+ e Surface Pro 7+ (LTE)](https://www.microsoft.com/en-us/download/details.aspx?id=102633)<br>- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)<br>- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)<br>- [Surface Pro 5 (LTE)](https://www.microsoft.com/download/details.aspx?id=56278)<br>- [Surface Pro 5 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=55484)<br>- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)<br>- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)<br>- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)<br>- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038) |
| **Surface Laptop**                                                                                                                                    | - [Surface Laptop Go](https://www.microsoft.com/download/details.aspx?id=102261)<br>- [Surface Laptop 4 com processador Intel](https://www.microsoft.com/download/details.aspx?id=102924)<br>- [Surface Laptop 4 com processador AMD](https://www.microsoft.com/download/details.aspx?id=102923)<br>- [Surface Laptop 3 com processador Intel](https://www.microsoft.com/download/details.aspx?id=100429)<br>- [Surface Laptop 3 com processador AMD](https://www.microsoft.com/download/details.aspx?id=100428)<br>- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)<br>- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)                                                                                                                                                                                    |
| **Surface Laptop Studio**                                                                                                                             | - [Surface Laptop Studio](https://www.microsoft.com/en-us/download/details.aspx?id=103505)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Surface Book**                                                                                                                                      | - [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)<br>- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)<br>- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Surface Go**                                                                                                                                        | - [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)<br>- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)<br>- [Surface Go (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=57439)<br>- [Surface Go (LTE)](https://www.microsoft.com/download/details.aspx?id=57601)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Surface Studio**                                                                                                                                    | - [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)<br>- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Surface 3**                                                                                                                                         | - [Surface 3 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=49040)<br>- [Surface 3 (LTE) - ATT](https://www.microsoft.com/download/details.aspx?id=49039)<br>- [Surface 3 (LTE) - Verizon](https://www.microsoft.com/download/details.aspx?id=49920)<br>- [Surface 3 (LTE) - Operadora da América do Norte Desbloqueada](https://www.microsoft.com/download/details.aspx?id=49037)<br>- [Surface 3 (LTE) - Fora da América do Norte e Y!mobile no Japão](https://www.microsoft.com/download/details.aspx?id=49041)                                                                                                                                                                                                                                                                                                                                                   |
| **Surface Hub em** [**execução Windows 10 Pro ou Windows 10 Enterprise**](/surface-hub/surface-hub-2s-migrate-os)   | - [Windows 10 Pro e Enterprise sistema operacional no Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Surface Hub executando Windows 10 Teams Atualização 2020**                                                                                                  | - Consulte [Gerenciar Windows atualizações no Surface Hub](/surface-hub/manage-windows-updates-for-surface-hub)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Surface Dock 2**                                                                                                                                    | - [Surface Dock 2](https://www.microsoft.com/download/details.aspx?id=101317)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

 

> [!TIP]
> Para dispositivos anteriores que incluem arquivos separados para versões Windows diferentes, selecione o nome de arquivo .msi que corresponde ao modelo surface e à versão do Windows. O .msi de arquivo inclui o número de com build mínimo Windows necessário para instalar os drivers e o firmware. Por exemplo, para atualizar um Surface Book 2 que tenha build 18362 de Windows 10, ** escolhaSurfaceBook2_Win10_18362_19.101.13994.msi.** Para um Surface Book 2 com build 16299 de Windows 10, escolha **SurfaceBook2_Win10_16299_1803509_3.msi**.

## <a name="central-update-management-in-commercial-environments"></a>Gerenciamento de atualizações centrais em ambientes comerciais

Ferramentas para gerenciar dispositivos , incluindo atualizações de driver e firmware, incluídas [Microsoft Endpoint Manager](https://devicemanagement.microsoft.com/). 

### <a name="manage-updates-with-configuration-manager-and-intune"></a>Gerenciar atualizações com o Configuration Manager e o Intune

Microsoft Endpoint Configuration Manager permite sincronizar e implantar atualizações de firmware e driver do Surface com o cliente do Configuration Manager. A integração Microsoft Intune permite que você veja todos os dispositivos gerenciados, co-gerenciados e gerenciados por parceiros em um só lugar. Essa é a solução recomendada para grandes organizações gerenciarem atualizações do Surface.

Para etapas detalhadas, consulte os seguintes recursos:

- [Atualizações do driver do Surface no Gerenciador de Configurações](manage-surface-driver-updates-configuration-manager.md)
- [Implantar aplicativos com o Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
- [Documentação do Endpoint Configuration Manager](/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Gerenciar atualizações com o Microsoft Deployment Toolkit

O Microsoft Deployment Toolkit (MDT) está incluído no Endpoint Configuration Manager. Dependendo do seu ambiente, ele contém ferramentas de implantação opcionais que você pode querer usar.  Eles incluem Windows Kit de Avaliação e Implantação (Windows ADK), Windows System Image Manager (Windows SIM), Serviço e Gerenciamento de Imagens de Implantação (DISM) e USMT (User State Migration Tool). Você pode baixar a versão mais recente do MDT na [página de download do Microsoft Deployment Toolkit download](https://www.microsoft.com/download/details.aspx?id=54259).

Para etapas detalhadas, consulte os seguintes recursos:

- [Documentação Toolkit microsoft deployment](/configmgr/mdt/)
- [Preparar para a implantação com o MDT](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)

Para obter instruções sobre como implantar atualizações usando o Endpoint Configuration Manager, consulte [Deploy applications with Configuration Manager](/configmgr/apps/deploy-use/deploy-applications). Para obter instruções sobre como implantar atualizações usando o MDT, consulte [Deploy a Windows 10 image using MDT](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**Firmware e drivers do WindowsPE e Surface**

O Endpoint Configuration Manager e o MDT usam o Ambiente Windows de Pré-instalação (WindowsPE) durante o processo de implantação. O WindowsPE oferece suporte apenas a um conjunto limitado de drivers básicos, como adaptadores de rede e controladores de armazenamento. Drivers para Windows componentes que não fazem parte do WindowsPE podem gerar erros. Como prática prática, você pode evitar esses erros configurando o processo de implantação para usar apenas os drivers necessários durante a fase do WindowsPE.

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

A partir do Gerenciador de Configuração do Ponto de Extremidade, você pode sincronizar e implantar atualizações de firmware e driver do Microsoft Surface usando o cliente do Configuration Manager. Para obter informações adicionais, consulte KB 4098906, [Manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## <a name="supported-devices"></a>Dispositivos com suporte

Os arquivos .msi de download estão disponíveis para dispositivos Surface Pro 2 e posteriores (exceto Surface Pro X que executa Windows 10 em ARM).

## <a name="managing-firmware-with-dfci"></a>Gerenciando firmware com DFCI

Ao ter perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados ao [Intune](/intune/configuration/device-firmware-configuration-interface-windows), o gerenciamento uefi do Surface estende a pilha de gerenciamento moderna até o nível de hardware UEFI. O DFCI dá suporte ao provisionamento de toque zero, elimina senhas de BIOS, fornece controle de configurações de segurança (incluindo opções de inicialização e periféricos integrados) e estabelece as bases para cenários avançados de segurança no futuro. Para obter mais informações, consulte:

- [Gerenciar DFCI em dispositivos Surface](surface-manage-dfci-guide.md)
- [Ignite 2019: Anunciando o gerenciamento remoto das configurações uefi do Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## <a name="best-practices-for-update-deployment-processes"></a>Práticas recomendadas para atualizar processos de implantação

Para manter um ambiente estável, é recomendável manter a paridade com a versão mais recente do Windows 10.  Para saber mais sobre as recomendações de práticas práticas, consulte [Prepare servicing strategy for Windows client updates](/windows/deployment/update/waas-deployment-rings-windows-10-updates).

### <a name="surface-msi-naming-convention"></a>Convenção .msi de nomenis do Surface

Desde agosto de 2019, .msi arquivos estão usando a seguinte convenção de nomeniso:

- *Product* _*Windows release*_ *Windows build* _*numberVersionRevision*_ *of version number (normalmente zero)*.

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
- **Versão:** 1900307 – mostra a data em que o arquivo foi criado e sua posição na sequência de lançamento, da seguinte forma:
  - **Ano:** 19 (2019)
  - **Número de lançamento:** 003 (terceira versão do ano)
  - **Número da versão do produto:** 07 (Surface Pro 6 é oficialmente a sétima versão do Surface Pro)
- **Revisão da versão:** 0 (primeira versão desta versão)

## <a name="learn-more"></a>Saiba mais

- [Prepare a estratégia de manutenção para as atualizações de cliente do Windows](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
- [Atualizações do driver do Surface no Gerenciador de Configurações](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Implantar aplicativos com o Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
- [Documentação do Endpoint Configuration Manager](/configmgr/)
- [Documentação Toolkit microsoft deployment](/configmgr/mdt/)
- [Preparar para a implantação com o MDT](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Gerenciar DFCI em dispositivos Surface](surface-manage-dfci-guide.md)
- [Ignite 2019: Anunciando o gerenciamento remoto das configurações uefi do Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

