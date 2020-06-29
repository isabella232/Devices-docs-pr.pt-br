---
title: Compatibilidade de dispositivos Surface com canal de manutenção de longo prazo do Windows 10 (Surface)
description: Saiba mais sobre compatibilidade e limitações de dispositivos Surface executando o Windows 10 Enterprise corporativo Edition.
keywords: corporativo, atualização, opções de serviço de superfície
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: db3dfd57c3b79fcec507ffd146483915490801b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830175"
---
# Compatibilidade de dispositivos Surface com canal de serviço de longo prazo do Windows 10 (LTSC)

Os dispositivos Surface são projetados para fornecer experiências de melhor classe em produtividade e cenários de uso geral. As atualizações regulares permitem que os dispositivos de superfície tragam novas inovações e evolumos com os novos recursos oferecidos pelas atualizações de recursos do Windows 10. As atualizações de recursos estão disponíveis apenas em edições do Windows 10 pro ou Windows 10 Enterprise que recebem atualizações contínuas por meio do canal semestral (SAC).

Em contraste com a opção de serviço do SAC, anteriormente conhecida como a ramificação atual (CB) ou as opções de serviço do Branch da empresa atual (CBB), você não pode selecionar a opção canal de manutenção de longo prazo (LTSC) nas configurações do Windows 10. Para usar a opção de manutenção do LTSC, você deve instalar uma edição separada do Windows 10 Enterprise, conhecida como Windows 10 Enterprise LTSC, anteriormente conhecida como Windows 10 Enterprise corporativo (ramificação de serviço de longo prazo. Além de fornecer um modelo de serviço estendido, o Windows 10 Enterprise LTSC Edition também fornece um ambiente com vários componentes do Windows removidos. As principais experiências de superfície afetadas pela LTSC incluem:

* Atualizações de recursos do Windows, incluindo aprimoramentos como:

  *  Melhorias na rejeição de tinta direta e de Palm fornecido no Windows 10, versão 1607 (também conhecida como atualização de aniversário)
  *  Suporte aprimorado para aplicativos de DPI alto fornecidos no Windows 10, versão 1703 (também conhecido como a atualização de criadores)

* Configurações de sensibilidade à pressão fornecidas pelo aplicativo Surface

* O espaço de trabalho do Windows Ink

* Principais aplicativos com toque otimizados, incluindo Microsoft Edge, OneNote, calendário e câmera

O uso do ambiente Windows 10 Enterprise LTSC em dispositivos de superfície resulta em experiências do usuário final subótimas e você deve evitar usá-lo em ambientes em que os usuários querem e esperam uma experiência de usuário Premium e atualizada.

A opção de serviço LTSC é projetada para tipos de dispositivo e cenários em que o atributo Key é para recursos ou funcionalidades que nunca mudam. Os exemplos incluem sistemas que a fabricação de energia ou equipamento médico ou sistemas incorporados em quiosques, como caixas eletrônicos ou sistemas de tíquetes de aeroportos.

>[!NOTE]
>Para obter informações gerais sobre as ramificações de manutenção do Windows, incluindo LTSC, consulte [visão geral do Windows como um serviço](https://technet.microsoft.com/itpro/windows/update/waas-overview#long-term-servicing-branch).

Como uma diretriz geral, os dispositivos que atendem aos critérios a seguir são considerados dispositivos de finalidade geral e devem ser combinados com o Windows 10 pro ou o Windows 10 Enterprise usando a opção de manutenção do canal semestral:

* Dispositivos que executam software de produtividade, como o Microsoft Office

* Dispositivos que usam aplicativos da Microsoft Store

* Dispositivos que são usados para navegação geral na Internet (por exemplo, pesquisa ou acesso a mídia social)

Antes de optar por usar o Windows 10 Enterprise LTSC Edition em dispositivos de superfície, considere as seguintes limitações:

* As atualizações de driver e firmware não são explicitamente testadas em relação às versões do Windows 10 Enterprise LTSC.

* Se você tiver problemas, o suporte da Microsoft fornecerá assistência para solução de problemas. No entanto, devido à natureza de manutenção do Windows LTSC, a resolução de problemas pode exigir que os dispositivos sejam atualizados para uma versão mais recente do Windows 10 Enterprise LTSC ou para o Windows 10 pro ou Enterprise com a opção de serviço do SAC.

* Substituições de dispositivos Surface (por exemplo, dispositivos substituídos na garantia) podem conter variações sutis em componentes de hardware que exigem firmware e drivers de dispositivo atualizados. A compatibilidade com essas atualizações pode exigir a instalação de uma versão mais recente do Windows 10 Enterprise LTSC ou Windows 10 pro ou Enterprise com a opção de serviço do SAC.

>[!NOTE]
>As organizações que padronizam uma versão específica do Windows 10 Enterprise LTSC podem não conseguir adotar novas gerações de hardware de superfície, como Surface Pro 7, Surface Pro X ou Surface laptop 3, sem também atualizar para uma versão mais recente do Windows 10 Enterprise LTSC ou do Windows 10 pro ou Enterprise. Para obter mais informações, consulte o tópico **como o Windows 10 LTSBs será compatível?** no tópico **suporte à seção mais recente do Windows para Windows** de [perguntas frequentes sobre política de ciclo de vida – produtos do Windows](https://support.microsoft.com/help/18581/lifecycle-policy-faq-windows-products#b4).

Os dispositivos Surface que executam o Windows 10 Enterprise LTSC Edition não receberão novos recursos. Em muitos casos, esses recursos são solicitados pelos clientes para melhorar a usabilidade e os recursos de hardware Surface. Por exemplo, novos aprimoramentos para aplicativos DPI alto no Windows 10, versão 1703. Os clientes que usam dispositivos Surface na configuração do LTSC não verão as melhorias até que sejam atualizados para uma nova versão do Windows 10 Enterprise LTSC ou atualização para uma versão do Windows 10 com suporte para a opção de serviço do SAC.

Os dispositivos podem ser alterados do Windows 10 Enterprise LTSC para uma versão mais recente do Windows 10 Enterprise, com suporte para a opção de serviço do SAC sem a perda dos dados do usuário executando uma instalação de atualização. Você também pode executar uma instalação de atualização em vários dispositivos aproveitando os modelos de sequência de tarefas de atualização disponíveis no Microsoft Deployment Toolkit (MDT) e Microsoft Endpoint Configuration Manager. Para obter mais informações, consulte [Atualizar dispositivos de superfície para o Windows 10 com o kit de ferramentas de implantação da Microsoft](https://technet.microsoft.com/itpro/surface/upgrade-surface-devices-to-windows-10-with-mdt).
