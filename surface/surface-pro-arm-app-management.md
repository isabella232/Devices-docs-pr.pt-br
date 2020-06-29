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
ms.date: 4/15/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: d1e7aa41f8219f0ae6ccd81a36fa0fc142dd1c3c
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830497"
---
# Implantação, gerenciamento e manutenção do Surface Pro X

## Introdução

Criado para lidar com requisitos comerciais de alto desempenho, o Surface Pro X trilha um novo caminho ao incorporar o processador mais potente já lançado em um dispositivo ARM, o chipset Microsoft SQ1 ARM.

Com uma CPU de 3GHz e uma GPU 2.1 teraflop, o Surface Pro X fornece uma experiência completa do Windows. Sua vida útil de bateria de 13 horas e 4G LTE interno o tornam ideal para profissionais de móveis de contato direto e profissionais dos campos financeiros, jurídicos e médicos, ou qualquer função que exige duração da bateria estendida e recursos de conectividade contínua.

O Surface Pro X foi desenvolvido quase que exclusivamente para um ambiente moderno, baseado em nuvem, centrado no Microsoft 365, Intune e Windows Autopilot. Este artigo realça a aparência disso e descreve as principais considerações sobre a implantação, o gerenciamento e a manutenção do Surface Pro X.

## Implantação do Surface Pro X

Para obter a melhor experiência, implante o Surface Pro X usando o Windows Autopilot com a assistência de um Provedor de Soluções na Nuvem da Microsoft ou provisionado automaticamente usando perfis de implantação do Autopilot e recursos relacionados. Para obter mais informações, consulte:

- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md)
- [Visão geral do Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

A implantação do Autopilot tem diversas vantagens: permite que você use o sistema operacional provisionado de fábrica, simplificado para implantação de toque zero, para a inclusão da pré-instalação do Office Pro Plus.

As organizações que já usam as soluções modernas de gerenciamento, segurança e produtividade estão bem posicionadas para tirar proveito dos recursos de desempenho exclusivos do Surface Pro X. Os clientes que usam aplicativos modernos de linha de negócios, aplicativos da Microsoft Store (UWP) ou soluções de área de trabalho remota também se beneficiam.

## Considerações sobre a implantação baseada em imagem

Atualmente, o Microsoft Deployment Toolkit (MDT) e o Microsoft Endpoint Configuration Manager (anteriormente conhecido como System Center Configuration Manager) não dão suporte ao Surface Pro X para a implantação do sistema operacional. Os clientes que dependem da implantação baseada em imagem devem considerar o Surface Pro 7 enquanto continuam a avaliar o momento certo para fazer a transição para a nuvem.

## Gerenciamento de dispositivos Surface Pro X

### Intune

Um componente do Microsoft Enterprise Mobility + Security, o Intune integra-se ao Azure Active Directory para controle de identidade e acesso, e fornece gerenciamento granular de dispositivos Surface Pro X registrados. As políticas de gerenciamento de dispositivo móvel (MDM) do Intune têm várias vantagens sobre as ferramentas locais anteriores, como a Política de Grupo do Windows. Isso inclui tempos de logon de dispositivos mais rápidos e um catálogo de políticas mais simplificado, permitindo o gerenciamento completo do dispositivo na nuvem. Por exemplo, você pode gerenciar LTE usando perfis eSIM para configurar planos de dados e implantar códigos de ativação em vários dispositivos.<br> 

Para obter mais informações sobre como configurar o Intune, consulte a [documentação do Intune](https://docs.microsoft.com/intune/).

### Cogerenciamento

Depois de implantado no Autopilot, você poderá ingressar dispositivos Surface Pro X no Azure AD ou no Active Directory (Ingresso no Azure AD Híbrido), onde você poderá gerenciar os dispositivos com o Intune ou cogerenciá-los com o Endpoint Configuration Manager, que instalará o Cliente do ConfigMgr x86 de 32 bits.

### Soluções MDM de terceiros

Você poderá usar ferramentas MDM de terceiros para gerenciar dispositivos Surface Pro X. Para obter detalhes, entre em contato com seu provedor de MDM.

### Software antivírus

O Windows Defender ajudará a proteger o Windows 10 em computadores baseados em ARM para o tempo de vida com suporte do dispositivo Windows 10. 

Alguns softwares antivírus de terceiros não podem ser instalados em um computador Windows 10 em execução em um processador baseado em ARM. A colaboração com fornecedores de software antivírus de terceiros continua para a preparação do aplicativo AV em computadores baseados em ARM. Entre em contato com seu provedor de software antivírus para entender quando seus aplicativos estarão disponíveis.

## Manutenção do Surface Pro X

O Surface Pro X dá suporte ao Windows 10, versão 1903 e posterior. Como um dispositivo baseado em ARM, ele tem requisitos específicos para manter os drivers e o firmware mais recentes. 

O Surface Pro X foi projetado para usar o Windows Update para simplificar o processo de manter o firmware e os drivers atualizados para usuários domésticos e usuários de pequenas empresas. Use as configurações padrão para receber Atualizações automáticas.  Para verificar:

1. Vá para **Iniciar** > **Configurações > Atualização e Segurança > Windows Update** > **Opções Avançadas**.
2. Em **Escolher como as atualizações são instaladas**, selecione **Automático (recomendado)**.

### Recomendações para clientes comerciais

- Use o Windows Update ou o Windows Update para Empresas para manter os drivers e o firmware mais recentes. Para saber mais, confira [Implantar atualizações usando o Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).
- Se os procedimentos exigirem o uso de um arquivo .msi do Windows Installer, entre em contato com o [suporte do Surface para Empresas](https://support.microsoft.com/help/4037645). 
- Para obter mais informações sobre a implantação e o gerenciamento de atualizações em dispositivos Surface, consulte [Implantar o firmware e os drivers mais recentes para dispositivos Surface](manage-surface-driver-and-firmware-updates.md).
- Observe que o Windows Server Update Services (WSUS) não oferece suporte à capacidade de fornecer drivers e firmware para o Surface Pro X.

## Execução de aplicativos no Surface Pro X

A maioria dos aplicativos é executada em computadores Windows 10 baseados em ARM com exclusões limitadas.

### Aplicativos com suporte

- A maioria dos aplicativos x86 Win32 é executada no Surface Pro X.
- Os aplicativos ARM64 nativos e UWP da Microsoft Store proporcionam uma excelente experiência do usuário usando a velocidade nativa completa do processador baseado em ARM e, ao mesmo tempo, otimizam a duração da bateria.
- Os aplicativos que usam drivers projetados para um computador Windows 10 com um processador baseado em ARM.

### Sem suporte

- Os aplicativos x64 não são executados em um computador Windows 10 em um processador baseado em ARM.

Para obter mais informações sobre como executar aplicativos no Surface Pro X, consulte:

- [Perguntas frequentes sobre suporte a computadores Windows 10 baseados em ARM](https://support.microsoft.com/help/4521606)
- [Documentação do Windows 10 em ARM](https://docs.microsoft.com/windows/arm)

## Áreas de Trabalho Virtuais (VDI)

A Área de Trabalho Virtual do Windows permite o acesso a áreas de trabalho, aplicativos e dados do Windows em qualquer dispositivo ou plataforma de computação, em qualquer local. Para saber mais, consulte [o site da Área de Trabalho Virtual do Windows](https://aka.ms/wvd). 

## Navegação com o Surface Pro X

Os navegadores populares são executados no Surface Pro X:

- Edge nativo, Firefox, Chrome e Internet Explorer são executados no Surface Pro X.
- O Edge nativo e o Firefox são executados nativamente e, portanto, têm desempenho aprimorado em um computador Windows 10 com um processador baseado em ARM.

## Instalação e uso do Microsoft Office

- Use o Office 365 para obter a melhor experiência em um computador Windows 10 com um processador baseado em ARM.
- O "clique para executar" do Office 365 instala o Outlook, o Word, o Excel e o PowerPoint, otimizado para ser executado em um computador Windows 10 com um processador baseado em ARM.
- O Microsoft Teams tem ótima execução no Surface Pro X.
- Para "versões perpétuas" do Office, como o Office 2019, instale a versão de 32 bits.

## VPN

Para confirmar se uma VPN de terceiros específica dá suporte a um computador Windows 10 com um processador baseado em ARM, entre em contato com o provedor de VPN.

## Comparação dos principais recursos

As tabelas a seguir mostram a disponibilidade dos principais recursos selecionados no Surface Pro X com o Windows 10 com ARM em comparação ao Surface Pro 7 baseado em Intel.

| Implantação                              | Surface Pro 7 | Surface Pro X | Observações                                                                                                                           |
| --------------------------------------- | ------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                       | Sim           | Sim           |                                                                                                                                 |
| Suporte à Inicialização de Rede (PXE)          | Sim           | Não           |                                                                                                                                 |
| Designer de Configuração do Windows          | Sim           | Não            | Não recomendado para o Surface Pro X.                                                                                              |
| WinPE                                   | Sim           | Sim           | Não recomendado para o Surface Pro X. A Microsoft não fornece o .ISO e os drivers necessários para dar suporte ao WinPE com Surface Pro X. |
| Endpoint Configuration Manager: Implantação de Sistema Operacional (OSD) | Sim           | Não            | Sem suporte no Surface Pro X.                                                                                              |
| MDT                                     | Sim           | Não            | Sem suporte no Surface Pro X.                                                                                              |


| Gerenciamento                                    | Surface Pro 7       | Surface Pro X | Observações                                                                                 |
| --------------------------------------------- | ------------------- | ------------- | ------------------------------------------------------------------------------------- |
| Intune                                        | Sim                 | Sim           | Gerencie LTE com perfis eSIM.                                                        |
| Windows Autopilot                             | Sim                 | Sim           |                                                                                       |
| Azure AD (cogerenciamento)                      | Sim                 | Sim           | Capacidade de associar o Surface Pro X ao Azure AD ou Active Directory (Ingresso no Azure AD Híbrido). |
| Endpoint Configuration Manager                                          | Sim               | Sim           |                                                                                       |
| Ligar Quando a CA for Restaurada                      | Sim                 | Sim           |                                                                                   |
| Kit de Ferramentas de Diagnóstico Surface (SDT) para Empresas | Sim                 | Sim           |                                                                                   |
| Atualização do Firmware do Surface Dock                  | Sim                 | Não           |                                                                                   |
| Utilitário de Marca de Ativo                             | Sim                 | Sim           |                                                                                   |
| Surface Enterprise Management Mode (SEMM)     | Sim | Parcial       | Nenhuma opção para desabilitar o hardware no Surface Pro X no nível do firmware.                 |
| Configurador UEFI do Surface                     | Sim |   Não            | Nenhuma opção para desabilitar o hardware. no Surface Pro X no nível do firmware.                |
| Gerenciador UEFI do Surface                          | Sim | Parcial       | Nenhuma opção para desabilitar o hardware no Surface Pro X no nível do firmware.                 |


| Segurança                          | Surface Pro 7 | Surface Pro X | Observações                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------- | ------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BitLocker                         | Sim           | Sim           |                                                                                                                                                                                                                                                                                                                                                      |
| Windows Defender                  | Sim           | Sim           |                                                                                                                                                                                                                                                                                                                                                      |
| Suporte para antivírus de terceiros | Sim           | Consultar observação      |Alguns softwares antivírus de terceiros não podem ser instalados em um computador Windows 10 em execução em um processador baseado em ARM. A colaboração com fornecedores de software antivírus de terceiros continua para a preparação do aplicativo AV em computadores baseados em ARM. Entre em contato com seu provedor de software antivírus para entender quando seus aplicativos estarão disponíveis. |
| Acesso condicional                | Sim           | Sim           |                                                                                                                                                                                                                                                                                                                                                      |
| Inicialização Segura                       | Sim           | Sim           |                                                                                                                                                                                                                                                                                                                                                      |
| Proteção de Informações do Windows    | Sim           | Sim           |                                                                                                                                                                                                                                                                                                                                                      |
| Surface Data Eraser (SDE)         | Sim           | Sim           |                                                                                                                                                                                                                                                                                                                                                     
## Perguntas frequentes

### Posso implantar o Surface Pro X com MDT ou Endpoint Configuration Manager?

Atualmente, o Microsoft Deployment Toolkit (MDT) e o Microsoft Endpoint Configuration Manager não dão suporte ao Surface Pro X para implantação do sistema operacional. Os clientes que dependem da implantação baseada em imagem devem levar em consideração o Surface Pro 7 enquanto continuam avaliando o momento certo para fazer a transição para a nuvem.

### Como faço para implantar o Surface Pro X?

Implante o Surface Pro X usando o Windows Autopilot.

### O BMR estará disponível?

Sim.

### O Intune é necessário para gerenciar o Surface Pro X?

O Intune é recomendado, mas não é necessário. Depois de implantado no Autopilot, você poderá ingressar dispositivos Surface Pro X no Azure AD ou no Active Directory (Ingresso no Azure AD Híbrido), onde você poderá gerenciar os dispositivos com o Intune ou cogerenciá-los com o Endpoint Configuration Manager, que instalará o Cliente do ConfigMgr x86 de 32 bits.
