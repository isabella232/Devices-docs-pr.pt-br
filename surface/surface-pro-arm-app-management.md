---
title: Implantação, gerenciamento e manutenção do Surface Pro X
description: Este artigo fornece uma visão geral das principais considerações para a implantação, o gerenciamento e a manutenção do Surface Pro X.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 83b3db2e9fa3da253c16d208b752bd7b6e6be771
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676415"
---
# <a name="deploying-managing--servicing-surface-pro-x"></a>Implantando, gerenciando e atendendo Surface Pro X

## <a name="introduction"></a>Introdução

Construído para lidar com requisitos comerciais de alto desempenho, o Surface Pro X inova ao incorporar os processadores mais poderosos de sua classe, os chipsets Microsoft SQ1 e Microsoft SQ1 ARM.

Com uma CPU de 3GHz e uma GPU 2.1 teraflop, o Surface Pro X fornece uma experiência completa do Windows. Sua bateria de 15 horas de Gigabit LTE integrada e a versatilidade de toque, caneta, tablet e laptop tornam-no ideal para trabalhadores móveis de primeira linha e profissionais nas áreas financeira, jurídica e médica ou qualquer função que exija bateria estendida capacidades de vida e conectividade contínua.

O Surface Pro X foi projetado quase exclusivamente para um ambiente moderno baseado em nuvem e funciona melhor quando combinado com Microsoft 365, Intune e Windows Autopilot. Este artigo realça a aparência disso e descreve as principais considerações sobre a implantação, o gerenciamento e a manutenção do Surface Pro X.

## <a name="deploying-surface-pro-x"></a>Implantação do Surface Pro X

Para obter a melhor experiência, implante o Surface Pro X usando o Windows Autopilot com a assistência de um Provedor de Soluções na Nuvem da Microsoft ou provisionado automaticamente usando perfis de implantação do Autopilot e recursos relacionados. Para obter mais informações, consulte:

- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md)
- [Visão geral do Windows Autopilot.](/windows/deployment/windows-autopilot/windows-autopilot)

A implantação do Autopilot tem diversas vantagens: permite que você use o sistema operacional provisionado de fábrica, simplificado para implantação de toque zero, para a inclusão da pré-instalação do Office Pro Plus.

As organizações que já usam as soluções modernas de gerenciamento, segurança e produtividade estão bem posicionadas para tirar proveito dos recursos de desempenho exclusivos do Surface Pro X. Os clientes que usam aplicativos modernos de linha de negócios, aplicativos da Microsoft Store (UWP) ou soluções de área de trabalho remota também se beneficiam.

## <a name="image-based-deployment-considerations"></a>Considerações sobre a implantação baseada em imagem

Atualmente, o Microsoft Deployment Toolkit (MDT) e o Microsoft Endpoint Configuration Manager (anteriormente conhecido como System Center Configuration Manager) não dão suporte ao Surface Pro X para a implantação do sistema operacional. Os clientes que dependem da implantação baseada em imagem devem considerar o Surface Pro 7+ enquanto continuam avaliando o momento certo para fazer a transição para soluções de implantação modernas. 

## <a name="managing-surface-pro-x-devices"></a>Gerenciamento de dispositivos Surface Pro X

### <a name="intune"></a>Intune

Um componente do Microsoft Enterprise Mobility + Security, o Intune integra-se ao Azure Active Directory para controle de identidade e acesso, e fornece gerenciamento granular de dispositivos Surface Pro X registrados. As políticas de gerenciamento de dispositivo móvel (MDM) do Intune têm várias vantagens sobre as ferramentas locais anteriores, como a Política de Grupo do Windows. Isso inclui tempos de logon de dispositivos mais rápidos e um catálogo de políticas mais simplificado, permitindo o gerenciamento completo do dispositivo na nuvem. Por exemplo, você pode gerenciar LTE usando perfis eSIM para configurar planos de dados e implantar códigos de ativação em vários dispositivos.<br> 

Para obter mais informações sobre como configurar o Intune, consulte a [documentação do Intune](/intune).

### <a name="co-management"></a>Cogerenciamento

Depois de implantado no Autopilot, você poderá ingressar dispositivos Surface Pro X no Azure AD ou no Active Directory (Ingresso no Azure AD Híbrido), onde você poderá gerenciar os dispositivos com o Intune ou cogerenciá-los com o Endpoint Configuration Manager, que instalará o Cliente do ConfigMgr x86 de 32 bits.

### <a name="third-party-mdm-solutions"></a>Soluções MDM de terceiros

Você poderá usar ferramentas MDM de terceiros para gerenciar dispositivos Surface Pro X. Para obter detalhes, entre em contato com seu provedor de MDM.

### <a name="antivirus-software"></a>Software antivírus

O Windows Defender ajudará a proteger o Windows 10 em computadores baseados em ARM para o tempo de vida com suporte do dispositivo Windows 10. 

Alguns softwares antivírus de terceiros não podem ser instalados em um computador Windows 10 em execução em um processador baseado em ARM. A colaboração com fornecedores de software antivírus de terceiros continua para a preparação do aplicativo AV em computadores baseados em ARM. Entre em contato com seu provedor de software antivírus para entender quando seus aplicativos estarão disponíveis.

## <a name="servicing-surface-pro-x"></a>Manutenção do Surface Pro X

O Surface Pro X vem com o Windows 10 versão 2004 e oferece suporte ao Windows 10, versão 1903 e posterior. Como um dispositivo baseado em ARM, ele tem requisitos específicos para manter os drivers e o firmware mais recentes. 

O Surface Pro X foi projetado para usar o Windows Update para simplificar o processo de manter o firmware e os drivers atualizados para usuários domésticos e usuários de pequenas empresas. Use as configurações padrão para receber Atualizações automáticas.  Para verificar:

1. Vá para **Iniciar** > **Configurações > Atualização e Segurança > Windows Update** > **Opções Avançadas**.
2. Em **Escolher como as atualizações são instaladas**, selecione **Automático (recomendado)**.

### <a name="recommendations-for-commercial-customers"></a>Recomendações para clientes comerciais

- Use o Windows Update ou o Windows Update para Empresas para manter os drivers e o firmware mais recentes. Para saber mais, confira [Implantar atualizações usando o Windows Update para Empresas](/windows/deployment/update/waas-manage-updates-wufb).
- Para obter mais informações sobre a implantação e o gerenciamento de atualizações em dispositivos Surface, consulte [Implantar o firmware e os drivers mais recentes para dispositivos Surface](manage-surface-driver-and-firmware-updates.md).
- Observe que o Windows Server Update Services (WSUS) não oferece suporte à capacidade de fornecer drivers e firmware para o Surface Pro X.

## <a name="running-apps-on-surface-pro-x"></a>Execução de aplicativos no Surface Pro X

A maioria dos aplicativos é executada em computadores Windows 10 baseados em ARM com exclusões limitadas.

### <a name="supported-apps"></a>Aplicativos com suporte

- A maioria dos aplicativos x86 Win32 é executada no Surface Pro X.
- Os aplicativos ARM64 nativos e UWP da Microsoft Store proporcionam uma excelente experiência do usuário usando a velocidade nativa completa do processador baseado em ARM e, ao mesmo tempo, otimizam a duração da bateria.
- Os aplicativos que usam drivers projetados para um computador Windows 10 com um processador baseado em ARM.

> [!NOTE]
> Com a emulação de 64 bits em breve na visualização por meio do Participante do Programa Windows Insider, você poderá executar aplicativos de 64 bits (x64) no Surface Pro X.

### <a name="fasttrack-app-assure"></a>Garantia de Aplicativo do FastTrack 

O programa de Garantia de Aplicativo está disponível para clientes comerciais para seus aplicativos de LOB, ISV e Microsoft voltados para o Windows 10 em ARM. Se clientes comerciais encontrarem um problema de compatibilidade de aplicativo usando o Windows 10 no ARM, a Microsoft fornecerá recursos de desenvolvedor para solucionar o problema e ajudar nas correções do aplicativo, sem custo adicional. Para saber mais, acesse [aka.ms/AppAssure](/fasttrack/products-and-capabilities#app-assure).

Para obter mais informações sobre como executar aplicativos no Surface Pro X, consulte:

- [Perguntas frequentes sobre suporte a computadores Windows 10 baseados em ARM](https://support.microsoft.com/help/4521606)
- [Documentação do Windows 10 em ARM](/windows/arm)

## <a name="virtual-desktops-vdi"></a>Áreas de Trabalho Virtuais (VDI)

A Área de Trabalho Virtual do Windows permite o acesso a áreas de trabalho, aplicativos e dados do Windows em qualquer dispositivo ou plataforma de computação, em qualquer local. Para saber mais, consulte [o site da Área de Trabalho Virtual do Windows](https://aka.ms/wvd). 

## <a name="browsing-with-surface-pro-x"></a>Navegação com o Surface Pro X

Os navegadores populares são executados no Surface Pro X:

- Edge nativo, Firefox, Chrome e Internet Explorer são executados no Surface Pro X.
- O Firefox e o Microsoft Edge baseados no Chromium são executados nativamente e, portanto, têm desempenho avançado em um PC com Windows 10 em um processador baseado em ARM.

## <a name="installing-and-using-microsoft-office"></a>Instalação e uso do Microsoft Office

- Use o Office 365 para obter a melhor experiência em um computador Windows 10 com um processador baseado em ARM.
- O "clique para executar" do Office 365 instala o Outlook, o Word, o Excel e o PowerPoint, otimizado para ser executado em um computador Windows 10 com um processador baseado em ARM.
- O Microsoft Teams tem ótima execução no Surface Pro X.
- Para "versões perpétuas" do Office, como o Office 2019, instale a versão de 32 bits.

## <a name="vpn"></a>VPN

Para confirmar se uma VPN de terceiros específica dá suporte a um computador Windows 10 com um processador baseado em ARM, entre em contato com o provedor de VPN.

## <a name="feature-summary"></a>Resumo dos recursos

As tabelas a seguir mostram a disponibilidade de recursos importantes selecionados no Surface Pro X com Windows 10 no ARM.


**Implantação**

| Recurso                                                           | S/N | Observações                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | Sim |                                                                                                                                   |
| Suporte à Inicialização de Rede (PXE)                                    | Não  |                                                                                                                                   |
| Designer de Configuração do Windows                                    | Não  | Não recomendado para o Surface Pro X.                                                                                                |
| WinPE                                                             | Sim | Não recomendado para o Surface Pro X. A Microsoft não fornece o .ISO e os drivers necessários para dar suporte ao WinPE com Surface Pro X. |
| Endpoint Configuration Manager: Implantação de Sistema Operacional (OSD) | Não  | Sem suporte no Surface Pro X.                                                                                                   |
| MDT                                                               | Não  | Sem suporte no Surface Pro X.                                                                                                   |

 
 
 **Management**
 

| Recurso                                       | S/N     | Observações                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| Intune                                        | Sim     | Gerencie LTE com perfis eSIM.                                                        |
| Windows Autopilot                             | Sim     |                                                                                       |
| Azure AD (cogerenciamento)                      | Sim     | Capacidade de associar o Surface Pro X ao Azure AD ou Active Directory (Ingresso no Azure AD Híbrido). |
| Endpoint Configuration Manager                | Sim     |                                                                                       |
| Ligar Quando a CA for Restaurada                      | Sim     |                                                                                       |
| Kit de Ferramentas de Diagnóstico Surface (SDT) para Empresas | Sim     |                                                                                       |
| Ferramenta de Marca do Ativo Surface                        | Sim     |                                                                                       |
| Surface Enterprise Management Mode (SEMM)     | Parcial | Nenhuma opção para desabilitar o hardware no Surface Pro X no nível do firmware.                 |
| Configurador UEFI do Surface                     | Não      | Nenhuma opção para desabilitar o hardware. no Surface Pro X no nível do firmware.                |
| Gerenciador UEFI do Surface                          | Parcial | Nenhuma opção para desabilitar o hardware no Surface Pro X no nível do firmware.                 |

 

**Segurança**
 

 Recurso                                       | S/N     | Observações                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| BitLocker                                     | Sim     |                                                       |
| Windows Defender                              | Sim     |                                                                                       |
| Suporte para antivírus de terceiros             | Consultar observação| Alguns softwares antivírus de terceiros não podem ser instalados em um computador Windows 10 em execução em um processador baseado em ARM. A colaboração com fornecedores de software antivírus de terceiros continua para a preparação do aplicativo AV em computadores baseados em ARM. Entre em contato com seu provedor de software antivírus para entender quando seus aplicativos estarão disponíveis. |
| Inicialização Segura               | Sim     |                                                                                       |
| Proteção de Informações do Windows                      | Sim     |                                                                                       |
| Surface Data Eraser (SDE)     | Sim     |                                                                                       |




## <a name="faq"></a>Perguntas frequentes

### <a name="can-i-deploy-surface-pro-x-with-mdt-or-endpoint-configuration-manager"></a>Posso implantar o Surface Pro X com o MDT ou Endpoint Configuration Manager?

Atualmente, o Microsoft Deployment Toolkit (MDT) e o Microsoft Endpoint Configuration Manager não oferecem suporte ao Surface Pro X para implantação de sistema operacional. Os clientes que dependem da implantação baseada em imagem devem considerar o Surface Pro 7+ enquanto continuam avaliando o momento certo para fazer a transição para a nuvem.

### <a name="how-can-i-deploy-surface-pro-x"></a>Como faço para implantar o Surface Pro X?

Implante o Surface Pro X usando o Windows Autopilot.

### <a name="is-a-bmr-available"></a>Está disponível um BMR?

Sim, consulte [Baixar uma imagem de recuperação para o Surface](https://support.microsoft.com/surfacerecoveryimage).

### <a name="is-intune-required-to-manage-surface-pro-x"></a>O Intune é necessário para gerenciar o Surface Pro X?

O Intune é recomendado, mas não é necessário. Depois de implantado no Autopilot, você poderá ingressar dispositivos Surface Pro X no Azure AD ou no Active Directory (Ingresso no Azure AD Híbrido), onde você poderá gerenciar os dispositivos com o Intune ou cogerenciá-los com o Endpoint Configuration Manager, que instalará o Cliente do ConfigMgr x86 de 32 bits.
