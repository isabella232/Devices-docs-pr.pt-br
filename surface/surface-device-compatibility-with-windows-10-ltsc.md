---
title: Compatibilidade do dispositivo Surface com o Windows 10 Long-Term de Manutenção (Surface)
description: Saiba mais sobre compatibilidade e limitações de dispositivos Surface executando Windows 10 Enterprise edição LTSB.
keywords: Opções de manutenção de superfície, atualização, ltsb
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 07/21/2021
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: 6127685edb0c098235734439ffbffac8c2c508ca
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338435"
---
# <a name="surface-device-compatibility-with-windows-10-long-term-servicing-channel-ltsc"></a>Compatibilidade do dispositivo Surface com Windows 10 Long-Term de Manutenção (LTSC)

Os dispositivos Surface são projetados para oferecer as melhores experiências em cenários de produtividade e de finalidade geral. As atualizações regulares permitem que os dispositivos Surface tragam novas inovações à vida e evoluam com os novos recursos fornecidos pelas Windows 10 de recursos. As Atualizações de Recursos estão disponíveis somente em Windows 10 Pro ou Windows 10 Enterprise edições que recebem atualizações contínuas por meio do Canal Semi-Annual (SAC).

Em contraste com a opção de manutenção SAC, anteriormente conhecida como as opções de manutenção do Branch Atual (CB) ou Do Branch Atual para Empresas (CBB), não é possível selecionar Long-Term opção do Canal de Manutenção do Long-Term (LTSC) nas configurações Windows 10. Para usar a opção de manutenção LTSC, você deve instalar uma edição separada do Windows 10 Enterprise, conhecido como Windows 10 Enterprise LTSC, anteriormente conhecido como Windows 10 Enterprise LTSB (Branch de Manutenção de Longo Prazo).

>[!TIP]
>Para obter as informações mais recentes sobre LTSC, consulte as seguintes perguntas frequentes: o próximo lançamento Windows 10 Canal de Manutenção de Longo Prazo [(LTSC](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/the-next-windows-10-long-term-servicing-channel-ltsc-release/ba-p/2147232)).

 Além de fornecer um modelo de manutenção estendida, a Windows 10 Enterprise LTSC também fornece um ambiente com vários componentes Windows removidos. As principais experiências do Surface que são impactadas pelo LTSC incluem:

* Windows atualizações de recursos, incluindo aprimoramentos como:

  *  Melhorias para Tinta Direta e rejeição de palma Windows 10, versão 1607 (também conhecida como Atualização de Aniversário)
  *  Suporte aprimorado para aplicativos DPI elevados fornecidos Windows 10 versão 1703 (também conhecida como Atualização de Criadores)

* Configurações de sensibilidade de pressão fornecidas pelo aplicativo Surface

* O Espaço de Trabalho do Windows Ink

* Principais aplicativos in-box otimizados para toque, incluindo Microsoft Edge, OneNote, Calendário e Câmera

O uso do ambiente Windows 10 Enterprise LTSC em dispositivos Surface resulta em experiências de usuário final sub-ideais e você deve evitar usá-lo em ambientes onde os usuários querem e esperam uma experiência de usuário premium e atualizada.

A opção de manutenção LTSC foi projetada para tipos de dispositivos e cenários em que o atributo-chave é para que recursos ou funcionalidades nunca mudem. Exemplos incluem sistemas que fabricam energia ou equipamentos médicos ou sistemas incorporados em quiosques, como caixas eletrônicos ou sistemas de tíquete de aeroporto.

>[!NOTE]
>Para obter informações gerais sobre Windows de manutenção, incluindo LTSC, consulte [Overview of Windows como serviço](/windows/deployment/update/waas-overview).

Como diretriz geral, os dispositivos que cumprem os seguintes critérios são considerados dispositivos de finalidade geral e devem ser emparelhados com Windows 10 Pro ou Windows 10 Enterprise usando Semi-Annual opção de manutenção do Canal Semi-Annual:

* Dispositivos que executem software de produtividade, como Microsoft Office

* Dispositivos que usam Microsoft Store aplicativos

* Dispositivos usados para navegação geral na Internet (por exemplo, pesquisa ou acesso a mídias sociais)

Antes de optar por usar a Windows 10 Enterprise LTSC em dispositivos Surface, considere as seguintes limitações:

* As atualizações de driver e firmware não são explicitamente testadas em relação às versões Windows 10 Enterprise LTSC.

* Se você encontrar problemas, o Suporte da Microsoft fornecerá assistência para solução de problemas. No entanto, devido à natureza de manutenção do Windows LTSC, a resolução de problemas pode exigir que os dispositivos sejam atualizados para uma versão mais recente do Windows 10 Enterprise LTSC ou para Windows 10 Pro ou Enterprise com a opção de manutenção SAC.

* As substituições de dispositivo Surface (por exemplo, dispositivos substituídos em garantia) podem conter variações sutis em componentes de hardware que exigem drivers de dispositivo atualizados e firmware. A compatibilidade com essas atualizações pode exigir a instalação de uma versão mais recente do Windows 10 Enterprise LTSC ou Windows 10 Pro ou Enterprise com a opção de manutenção SAC.

>[!NOTE]
>As organizações que padronizarem uma versão específica do Windows 10 Enterprise LTSC podem não poder adotar novas gerações de hardware surface, como Surface Pro 8, Surface Pro X ou Surface Laptop 4, sem também atualizar para uma versão posterior do Windows 10 Enterprise LTSC ou Windows 10 Pro ou Enterprise. Para obter mais informações, consulte a perguntas [frequentes sobre ciclo de vida - Windows](/lifecycle/faq/windows#what-are-the-requirements-for-servicing-and-updating-the-windows-10-long-term-servicing-channel--ltsc--).

Os dispositivos Surface que executam Windows 10 Enterprise edição LTSC não receberão novos recursos. Em muitos casos, esses recursos são solicitados pelos clientes para melhorar a usabilidade e os recursos do hardware surface. Por exemplo, novas melhorias para aplicativos high DPI Windows 10 versão 1703. Os clientes que usam dispositivos Surface na configuração LTSC não verão as melhorias até que eles atualizem para uma nova versão do Windows 10 Enterprise LTSC ou atualizem para uma versão do Windows 10 com suporte para a opção de manutenção SAC.

Os dispositivos podem ser alterados do Windows 10 Enterprise LTSC para uma versão mais recente do Windows 10 Enterprise, com suporte para a opção de manutenção SAC, sem a perda de dados do usuário executando uma instalação de atualização. Você também pode executar uma instalação de atualização em vários dispositivos aproveitando os Modelos de Sequência de Tarefas de Atualização disponíveis no Microsoft Deployment Toolkit (MDT) e Microsoft Endpoint Configuration Manager. Para obter mais informações, consulte [Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit](upgrade-surface-devices-to-windows-10-with-mdt.md).
