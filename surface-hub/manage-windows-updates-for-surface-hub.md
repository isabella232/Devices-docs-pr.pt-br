---
title: Gerenciar atualizações do Windows no Surface Hub
description: Descreve as práticas recomendadas para gerenciar atualizações no Microsoft Surface Hub ou Surface Hub 2S.
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: gerenciar Windows atualizações, Surface Hub, Windows Server Update Services
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: ecff961e1aaa14ed2af5e6d91ffc2254e4dcfa46
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497774"
---
# <a name="manage-windows-updates-on-surface-hub"></a>Gerenciar atualizações do Windows no Surface Hub

Novas versões do Surface Hub sistema operacional são publicadas por meio Windows Update, assim como as versões do Windows 10 ou Windows 11. Esta página explica as práticas recomendadas para gerenciar atualizações para Surface Hub dispositivos. 

## <a name="windows-update-for-business"></a>Windows Update para Empresas

Windows Update for Business é um conjunto de recursos projetados para fornecer às empresas controle adicional sobre como e quando o Windows Update instala versões, reduzindo os custos de gerenciamento de dispositivos. Usando esse método, os Surface Hubs são conectados diretamente ao serviço Windows Update da Microsoft.

- Receba atualizações diretamente do serviço Windows Update da Microsoft, nenhuma infraestrutura adicional é necessária. 
- Adie atualizações para fornecer mais tempo para avaliação e testes. 
- Implante atualizações em alguns grupos de dispositivos. 
- Defina janelas de manutenção para a instalação de atualizações. 

> [!TIP]
> Use o compartilhamento de conteúdo ponto a ponto para reduzir problemas de largura de banda durante atualizações. Consulte [Otimizar Windows entrega de atualização para](/windows/deployment/do/waas-optimize-windows-10-updates) obter detalhes.

> [!NOTE]
> O Surface Hub não dá suporte atualmente à reversão de atualizações.


## <a name="surface-hub-servicing-model"></a>Modelo de manutenção do Surface Hub

Surface Hub usa o Windows de manutenção, conhecido como [Windows como serviço (WaaS)](/windows/deployment/update/waas-overview). Tradicionalmente, novos recursos são adicionados apenas em novas versões do Windows que são lançadas de tempos em tempos. Cada nova versão exigia processos demorados e caros para implantação em uma organização. Por isso, os usuários finais e as organizações frequentemente não aproveitam os benefícios da inovação. O objetivo do Windows como Serviço é fornecer novas funcionalidades continuamente, mantendo um alto nível de qualidade.

A Microsoft publica dois tipos de versões do Surface Hub de forma ampla e contínua:
- **Atualizações de recursos** – Atualizações que instalam os novos recursos, experiências e funcionalidades mais recentes. A Microsoft espera publicar duas novas atualizações de recursos por ano.
- **Atualizações de qualidade** – Atualizações que se concentram na instalação de correções de segurança, drivers e outras atualizações de manutenção. A Microsoft espera publicar uma atualização cumulativa de qualidade por mês.

Para melhorar a qualidade da versão e simplificar as implantações, todas as novas versões que a Microsoft publica para Windows 10 ou Windows 11, incluindo Surface Hub, serão cumulativas. Isso significa que as novas atualizações de recursos e de qualidade conterão o conteúdo de todas as versões anteriores (de uma forma otimizada para reduzir os requisitos de rede e armazenamento) e que a instalação dessa versão em um dispositivo o atualizará totalmente. Além disso, ao contrário das versões anteriores do Windows, você não pode instalar um subconjunto de conteúdos de uma atualização de qualidade do Windows 10. Por exemplo, se uma atualização de qualidade contiver correções para três problemas de vulnerabilidade de segurança e uma de confiabilidade, a implantação da atualização resultará na instalação de todas as quatro correções.

O sistema operacional do Surface Hub recebe atualizações sobre o [Canal Semestral](/windows/deployment/update/waas-overview#naming-changes). Como outras edições do Windows 10 ou Windows 11, o tempo de vida de manutenção é finito. Você deve instalar novas atualizações de recursos em computadores que executam essas ramificações para continuar a receber atualizações de qualidade.

Para obter mais informações sobre o Windows como Serviço, consulte [Visão geral do Windows como serviço](/windows/deployment/update/waas-overview).


## <a name="use-windows-update-for-business"></a>Usar Windows Update para Empresas

Os Surface Hubs, como todos os dispositivos Windows 10, possuem o **Windows Update para Empresas (WUfB)** para que você possa controlar como os dispositivos estão sendo atualizados. O Windows Update para Empresas ajuda a reduzir os custos de gerenciamento de dispositivo, fornece controles sobre a implantação de atualizações, oferece acesso mais rápido às atualizações de segurança, além de dar acesso às inovações mais recentes da Microsoft de forma contínua. Para obter mais informações, consulte [Gerenciar atualizações usando o Windows Update para Empresas](/windows/deployment/update/waas-manage-updates-wufb).

> [!IMPORTANT]
> A Microsoft geralmente lança uma atualização de segurança Windows obrigatória por mês (lançada na segunda terça-feira e geralmente chamada de versão "B"). Juntamente com atualizações de segurança fora de banda, essas são as únicas atualizações disponibilizadas para dispositivos que usam o WUfB. No entanto, Surface Hub melhorias geralmente são entregues por meio de atualizações opcionais não de segurança na 3ª terça-feira de cada mês ("versão C"). Como resultado, os clientes que usam o Windows Update for Business com seus Surface Hubs terão que aguardar até a versão "B" do mês seguinte para ver as melhorias mais recentes nesses dispositivos.

**Para configurar o Windows Update para Empresas:**
1. [Agrupar o Surface Hub em anéis de implantação](#group-surface-hub-into-deployment-rings)
2. [Configurar quando o Surface Hub receberá atualizações](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> Você pode usar Microsoft Intune, Microsoft Endpoint Configuration Manager ou um provedor de MDM de terceiros com suporte para configurar o WUfB. [Passo a passo: use o Microsoft Intune para configurar o Windows Update para Empresas.](/windows/deployment/update/waas-wufb-intune)


### <a name="group-surface-hub-into-deployment-rings"></a>Agrupar o Surface Hub em anéis de implantação

Use anéis de implantação para controlar quando as atualizações são implantadas em seus Surface Hubs, proporcionando tempo para você validá-las. Por exemplo, você pode atualizar um pequeno pool de dispositivos primeiro para verificar a qualidade antes de uma implantação mais ampla em sua organização. Dependendo de quem gerencia o Surface Hub em sua organização, considere incorporar o Surface Hub aos anéis de implantação que você criou para seus outros dispositivos Windows 10 ou Windows 11. Para obter mais informações sobre anéis de implantação, consulte [Preparar estratégia de manutenção para Windows de cliente](/windows/deployment/update/waas-servicing-strategy-windows-10-updates).

Consulte a tabela a seguir para obter exemplos de anéis de implantação.

| Anel de implantação | Tamanho do anel | Branch de manutenção | Adiamento de atualizações de recursos | Adiamento de atualizações de qualidade (correções de segurança, drivers e outras atualizações) | Etapa de validação |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Avaliação (por exemplo, dispositivos não críticos ou de teste) | Pequeno | Windows Insider Preview | Nenhum.  | Nenhum.  | Testar e avaliar manualmente a nova funcionalidade. Pausar as atualizações se houver problemas. |
| Liberação (por exemplo, dispositivos usados por algumas equipes) | Médio | Canal semestral  | Nenhum. | Nenhum.  | Monitorar o uso dos dispositivos e os comentários dos usuários. Pausar as atualizações se houver problemas. |
| Ampla implantação (por exemplo, a maioria dos dispositivos em sua organização) | Grande | Canal semestral |  120 dias depois do lançamento. | 7-14 dias depois do lançamento. | Monitorar o uso dos dispositivos e os comentários dos usuários. Pausar as atualizações se houver problemas. |
| Crítico (por exemplo, dispositivos em salas de diretoria executiva) | Pequeno | Canal semestral |  180 dias depois do lançamento (adiamento máximo para atualizações de recursos). | 30 dias depois do lançamento (adiamento máximo para atualizações de qualidade). | Monitorar o uso dos dispositivos e os comentários dos usuários. |


### <a name="configure-when-surface-hub-receives-updates"></a>Configurar quando o Surface Hub receberá atualizações

Depois de determinar os anéis de implantação para seus Surface Hubs, configure as políticas de adiamento de atualização para cada anel:
- Para adiar atualizações de recursos, defina uma política [Update/DeferFeatureUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) apropriada para cada anel.
- Para adiar atualizações de qualidade, defina uma política [Update/DeferQualityUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) apropriada para cada anel.

> [!NOTE]
> Se você encontrar problemas durante a distribuição de atualizações, você pode pausar as atualizações usando [Update/PauseFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) e [Update/PauseQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates).

**Se você usa um servidor proxy ou outro método para bloquear URLs**

Adicione o seguinte Windows urLs de site confiável à "lista de permissões":
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Quando a Atualização de Aniversário do Windows 10 Team estiver instalada, você poderá remover esses endereços para retornar o Surface Hub ao estado anterior.

## <a name="maintenance-window"></a>Janela de manutenção

Para garantir que o dispositivo esteja sempre disponível para uso durante o horário comercial, o Surface Hub executa suas funções administrativas durante uma janela de manutenção especificada. Durante a janela de manutenção, o Surface Hub instala automaticamente as atualizações por meio do Windows Update e reinicializa o dispositivo 20 minutos antes do final da janela.

O Surface Hub segue estas diretrizes para aplicar atualizações:
- Instale a atualização durante a próxima janela de manutenção. Se uma reunião for agendada para iniciar durante uma janela de manutenção ou se os sensores do Surface Hub detectarem que o dispositivo está sendo usado, a atualização pendente será adiada para a janela de manutenção seguinte.
- Se a próxima janela de manutenção for após o período de carência prescrito da atualização, o dispositivo calculará a próxima brecha disponível durante o horário comercial usando o tempo estimado de instalação a partir dos metadados da atualização. Ele continuará a adiar a atualização se uma reunião estiver agendada ou se os sensores do Surface Hub detectarem que o dispositivo está sendo usado.
- Se a próxima janela de manutenção **não passar** do período de carência da atualização, o Surface Hub continuará a adiar a atualização.
- Se uma reinicialização for necessária, o Surface Hub será reinicializado automaticamente durante a próxima janela de manutenção.

> [!NOTE]
> Reserve um tempo para as atualizações ao configurar seu Surface Hub pela primeira vez. Por exemplo, uma lista de pendências de definições de vírus pode estar disponível, o que deve ser instalado imediatamente.

Uma janela de manutenção padrão é definida para todos os novos Surface Hubs:
-   **Hora de início:** 2h
-   **Duração:** 2 horas

**Para alterar manualmente a janela de manutenção:**
1.  Abra **Configurações** em seu Surface Hub.
2.  Navegue até **Atualização e segurança** > **Windows Update** > **Opções avançadas**.
3.  Em **Horário de manutenção**, selecione **Alterar**.

Para alterar a janela de manutenção usando o MDM, defina o nó **MaintenanceHoursSimple** no provedor de serviços de [configuração do SurfaceHub](/windows/client-management/mdm/surfacehub-csp). Consulte [Gerenciar configurações usando um provedor de MDM](manage-settings-with-mdm-for-surface-hub.md) para saber mais detalhes.


## <a name="more-information"></a>Mais informações

- [Postagem no blog: Manutenção, liberação de voo e gerenciamento de atualizações para Surface Hub (com Intune, é claro!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)

