---
title: Gerenciar atualizações do Windows no Surface Hub
description: Você pode gerenciar atualizações do Windows em seu hub Microsoft Surface ou Surface Hub 2S definindo a janela de manutenção, adiando atualizações ou usando o Windows Server Update Services (WSUS).
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: gerenciar atualizações do Windows, Surface Hub, Windows Server Update Services, WSUS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 72214ec9436e6ea106d9e42c957664631ee88a0a
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103785"
---
# Gerenciar atualizações do Windows no Surface Hub

Novas versões do sistema operacional do Surface Hub são publicadas por meio do Windows Update, assim como as versões do Windows 10. Existem algumas maneiras de gerenciar quais atualizações são instaladas em seus Surface Hubs e quando as atualizações são aplicadas.
- **Windows Update para Empresas** – Novidade no Windows 10, o Windows Update para Empresas é um conjunto de recursos desenvolvidos para proporcionar às empresas controle adicional sobre como e quando o Windows Update instala versões, além de reduzir os custos de gerenciamento de dispositivos. Usando esse método, os Surface Hubs são conectados diretamente ao serviço Windows Update da Microsoft.
- **Windows Server Update Services (WSUS)** – Conjunto de serviços que permitem que os administradores de TI baixem as atualizações que o Windows Update determine que são aplicáveis aos dispositivos de sua empresa, façam uma avaliação e testes adicionais das atualizações e selecionem as atualizações que desejam instalar. Usando esse método, os Surface Hubs receberão atualizações do WSUS, em vez do Windows Update.

Você também pode configurar o Surface Hub para receber atualizações do Windows Update para Empresas e do WSUS. Consulte [Integrar o Windows Update para Empresas com o Windows Server Update Services](https://technet.microsoft.com/itpro/windows/manage/waas-integrate-wufb#integrate-windows-update-for-business-with-windows-server-update-services) para saber os detalhes.

| Funcionalidades | Windows Update para Empresas | Windows Server Update Services (WSUS) |
| ------------ | --------------------------- | ------------------------------------- |
| Receba atualizações diretamente do serviço Windows Update da Microsoft, nenhuma infraestrutura adicional é necessária.  | Sim  | Não  |
| Adie atualizações para fornecer mais tempo para avaliação e testes. | Sim  | Sim  |
| Implante atualizações em alguns grupos de dispositivos. | Sim | Sim |
| Defina janelas de manutenção para a instalação de atualizações. | Sim  | Sim  |

> [!TIP]
> Use o compartilhamento de conteúdo ponto a ponto para reduzir problemas de largura de banda durante atualizações. Consulte [Otimizar a entrega de atualização para atualizações do Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates) para saber os detalhes.

> [!NOTE]
> O Surface Hub não dá suporte atualmente à reversão de atualizações.


## Modelo de manutenção do Surface Hub

O Surface Hub usa o modelo de manutenção do Windows 10, conhecido como [WaaS (Windows como Serviço)](https://docs.microsoft.com/windows/deployment/update/waas-overview). Tradicionalmente, novos recursos são adicionados apenas em novas versões do Windows que são lançadas de tempos em tempos. Cada nova versão exigia processos demorados e caros para implantação em uma organização. Por isso, os usuários finais e as organizações frequentemente não aproveitam os benefícios da inovação. O objetivo do Windows como Serviço é fornecer novas funcionalidades continuamente, mantendo um alto nível de qualidade.

A Microsoft publica dois tipos de versões do Surface Hub de forma ampla e contínua:
- **Atualizações de recursos** – Atualizações que instalam os novos recursos, experiências e funcionalidades mais recentes. A Microsoft espera publicar duas novas atualizações de recursos por ano.
- **Atualizações de qualidade** – Atualizações que se concentram na instalação de correções de segurança, drivers e outras atualizações de manutenção. A Microsoft espera publicar uma atualização cumulativa de qualidade por mês.

Para melhorar a qualidade da versão e simplificar as implantações, todas as novas versões que a Microsoft publicar do Windows 10, inclusive do Surface Hub, serão cumulativas. Isso significa que as novas atualizações de recursos e de qualidade conterão o conteúdo de todas as versões anteriores (de uma forma otimizada para reduzir os requisitos de rede e armazenamento) e que a instalação dessa versão em um dispositivo o atualizará totalmente. Além disso, ao contrário das versões anteriores do Windows, você não pode instalar um subconjunto de conteúdos de uma atualização de qualidade do Windows 10. Por exemplo, se uma atualização de qualidade contiver correções para três problemas de vulnerabilidade de segurança e uma de confiabilidade, a implantação da atualização resultará na instalação de todas as quatro correções.

O sistema operacional do Surface Hub recebe atualizações sobre o [Canal Semestral](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). Assim como outras edições do Windows 10, o tempo de vida de manutenção é finito. Você deve instalar novas atualizações de recursos em computadores que executam essas ramificações para continuar a receber atualizações de qualidade.

Para obter mais informações sobre o Windows como Serviço, consulte [Visão geral do Windows como serviço](https://technet.microsoft.com/itpro/windows/manage/waas-overview).


## Usar Windows Update para Empresas
Os Surface Hubs, como todos os dispositivos Windows 10, possuem o **Windows Update para Empresas (WUfB)** para que você possa controlar como os dispositivos estão sendo atualizados. O Windows Update para Empresas ajuda a reduzir os custos de gerenciamento de dispositivo, fornece controles sobre a implantação de atualizações, oferece acesso mais rápido às atualizações de segurança, além de dar acesso às inovações mais recentes da Microsoft de forma contínua. Para obter mais informações, consulte [Gerenciar atualizações usando o Windows Update para Empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

**Para configurar o Windows Update para Empresas:**
1. [Agrupar o Surface Hub em anéis de implantação](#group-surface-hub-into-deployment-rings)
2. [Configurar quando o Surface Hub receberá atualizações](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> Você pode usar o Microsoft Intune, o Gerenciador de configuração do Microsoft Endpoint ou um provedor de MDM de terceiros compatível para configurar o WUfB. [Passo a passo: use o Microsoft Intune para configurar o Windows Update para Empresas.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### Agrupar o Surface Hub em anéis de implantação
Use anéis de implantação para controlar quando as atualizações são implantadas em seus Surface Hubs, proporcionando tempo para você validá-las. Por exemplo, você pode atualizar um pequeno pool de dispositivos primeiro para verificar a qualidade antes de uma implantação mais ampla em sua organização. Dependendo de quem gerencia o Surface Hub em sua organização, considere a possibilidade de incorporar o Surface Hub em anéis de implantação criados para outros dispositivos Windows 10. Para obter mais informações sobre os anéis de implantação, consulte [Criar anéis de implantação para atualizações do Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates).

Esta tabela contém exemplos de anéis de implantação.

| Anel de implantação | Tamanho do anel | Branch de manutenção | Adiamento de atualizações de recursos | Adiamento de atualizações de qualidade (correções de segurança, drivers e outras atualizações) | Etapa de validação |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Avaliação (por exemplo, dispositivos não críticos ou de teste) | Pequeno | Visualização do Windows Insider | Nenhum.  | Nenhum.  | Testar e avaliar manualmente a nova funcionalidade. Pausar as atualizações se houver problemas. |
| Liberação (por exemplo, dispositivos usados por algumas equipes) | Médio | Canal semestral  | Nenhum. | Nenhum.  | Monitorar o uso dos dispositivos e os comentários dos usuários. Pausar as atualizações se houver problemas. |
| Ampla implantação (por exemplo, a maioria dos dispositivos em sua organização) | Grande | Canal semestral |  120 dias depois do lançamento. | 7-14 dias depois do lançamento. | Monitorar o uso dos dispositivos e os comentários dos usuários. Pausar as atualizações se houver problemas. |
| Crítico (por exemplo, dispositivos em salas de diretoria executiva) | Pequeno | Canal semestral |  180 dias depois do lançamento (adiamento máximo para atualizações de recursos). | 30 dias depois do lançamento (adiamento máximo para atualizações de qualidade). | Monitorar o uso dos dispositivos e os comentários dos usuários. |





### Configurar quando o Surface Hub receberá atualizações
Depois de determinar os anéis de implantação para seus Surface Hubs, configure as políticas de adiamento de atualização para cada anel:
- Para adiar atualizações de recursos, defina uma política [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) apropriada para cada anel.
- Para adiar atualizações de qualidade, defina uma política [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) apropriada para cada anel.

> [!NOTE]
> Se você encontrar problemas durante a distribuição de atualizações, você pode pausar as atualizações usando [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) e [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates).


## Usar o Windows Server Update Services

Você pode conectar o Surface Hub ao servidor do Windows Server Update Services (WSUS) para gerenciar as atualizações. As atualizações serão controladas por meio de aprovações ou regras de implantação automática configuradas em seu servidor WSUS. Portanto, as novas atualizações não serão implantadas até que você escolha implantá-las.

**Para conectar manualmente um Surface Hub a um servidor WSUS:**
1. Abra **Configurações** em seu Surface Hub.
2. Insira as credenciais de administrador de dispositivo quando solicitado.
3. Navegue até **Atualização e segurança** > **Windows Update** > **Opções avançadas** > **Configurar servidor do Windows Server Update Services (WSUS)**.
4. Clique em **Usar o Servidor WSUS para baixar atualizações** e digite a URL do servidor WSUS.

Para conectar o Surface Hub a um servidor WSUS usando o MDM, defina uma política [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl) apropriada.

**Se você usa um servidor proxy ou outro método para bloquear URLs**

Se você usar um método diferente do WSUS para bloquear URLs específicas e impedir atualizações, precisará adicionar as seguintes URLs de sites confiáveis de atualização do Windows à "lista de permissão":
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Quando a Atualização de Aniversário do Windows 10 Team estiver instalada, você poderá remover esses endereços para retornar o Surface Hub ao estado anterior.

## Janela de manutenção

Para garantir que o dispositivo esteja sempre disponível para uso durante o horário comercial, o Surface Hub executa suas funções administrativas durante uma janela de manutenção especificada. Durante a janela de manutenção, o Surface Hub instala atualizações automaticamente por meio do Windows Update ou do WSUS e reinicializa o dispositivo 20 minutos antes do fim da janela.

O Surface Hub segue estas diretrizes para aplicar atualizações:
- Instale a atualização durante a próxima janela de manutenção. Se uma reunião for agendada para iniciar durante uma janela de manutenção ou se os sensores do Surface Hub detectarem que o dispositivo está sendo usado, a atualização pendente será adiada para a janela de manutenção seguinte.
- Se a próxima janela de manutenção for após o período de carência prescrito da atualização, o dispositivo calculará a próxima brecha disponível durante o horário comercial usando o tempo estimado de instalação a partir dos metadados da atualização. Ele continuará a adiar a atualização se uma reunião estiver agendada ou se os sensores do Surface Hub detectarem que o dispositivo está sendo usado.
- Se a próxima janela de manutenção **não** ultrapassar o período de cortesia da atualização, o Surface Hub continuará adiando a atualização.
- Se uma reinicialização for necessária, o Surface Hub será reinicializado automaticamente durante a próxima janela de manutenção.

> [!NOTE]
> Reserve um tempo para as atualizações ao configurar seu Surface Hub pela primeira vez. Por exemplo, uma lista de pendências de definições de vírus pode estar disponível, o que deve ser instalado imediatamente.

Uma janela de manutenção padrão é definida para todos os novos Surface Hubs:
-   **Hora de início:** 2:00 am
-   **Duração:** 2 horas

**Para alterar manualmente a janela de manutenção:**
1.  Abra **Configurações** em seu Surface Hub.
2.  Navegue até **Atualização e segurança** > **Windows Update** > **Opções avançadas**.
3.  Em **Horário de manutenção**, selecione **Alterar**.

Para alterar a janela de manutenção usando o MDM, defina o nó **MOMAgent** no [Provedor de serviços de configuração SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). Consulte [Gerenciar configurações usando um provedor de MDM](manage-settings-with-mdm-for-surface-hub.md) para saber mais detalhes.


## Mais informações

- [Postagem de blog: manutenção, processamento e gerenciamento de atualizações para o Surface Hub (com o Intune, é claro!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)

