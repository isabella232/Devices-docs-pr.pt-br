---
title: Windows Autopilot e dispositivos Surface
ms.reviewer: ''
manager: laurawi
description: Saiba mais sobre as opções de implantação do piloto automático do Windows para dispositivos Surface.
keywords: piloto automático, Windows 10, Surface, implantação
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830257"
---
# Windows Autopilot e dispositivos Surface

O piloto automático do Windows é uma tecnologia de implantação baseada em nuvem no Windows 10. Você pode usar o Windows AutoPilot para implantar e configurar remotamente dispositivos em um processo Zero Touch imediatamente.

O piloto automático do Windows-dispositivos registrados são identificados pela Internet na primeira inicialização por meio de uma assinatura de dispositivo exclusiva que é chamada de *hash de hardware*. Elas são automaticamente inscritas e configuradas usando soluções de gerenciamento modernas, como Azure Active Directory (Azure AD) e gerenciamento de dispositivos móveis.

Você pode registrar dispositivos Surface no momento da compra a partir de um parceiro Surface habilitado para o piloto automático do Windows. Esses parceiros podem enviar novos dispositivos diretamente para seus usuários. Os dispositivos serão automaticamente inscritos e configurados quando forem ativados pela primeira vez. Esse processo elimina a recriação de imagens durante a implantação, o que permite implementar novos métodos ágeis de gerenciamento e distribuição de dispositivos.

## Gerenciamento moderno

O AutoPilot é a opção de implantação recomendada para dispositivos Surface, incluindo Surface Pro 7, Surface laptop 3 e Surface Pro X, que foi projetado especificamente para implantação por meio do AutoPilot.

 É melhor registrar seus dispositivos Surface com a ajuda de um provedor de soluções na nuvem da Microsoft. Esta etapa permite que você gerencie as configurações de firmware UEFI em superfície diretamente do Intune. Ele elimina a necessidade de tocar fisicamente dispositivos para gerenciamento de certificados. Consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md) para obter detalhes.

## Considerações sobre a versão do Windows

A implantação ampla de dispositivos de superfície por meio do piloto automático do Windows, incluindo a inscrição pelos parceiros Surface no momento da compra, requer o Windows 10 versão 1709 (Outono dos criadores de outono) ou posterior.

Essas versões do Windows dão suporte a um valor de hash de 4.000 bytes que identifica exclusivamente dispositivos para o AutoPilot do Windows, o que é necessário para implantações em escala. Todos os novos dispositivos de superfície, incluindo Surface Pro 7, Surface Pro X e Surface laptop 3, vêm com o Windows 10 versão 1903 ou posterior.

## Experiência do Exchange em dispositivos Surface em necessidade de reparo ou substituição

A Microsoft verifica automaticamente todas as superfícies para a inscrição do piloto automático e cancela o registro do dispositivo do locatário do cliente.  A Microsoft garante que o dispositivo substituto seja registrado no piloto automático do Windows quando um substituto for devolvido ao cliente. Esse serviço está disponível em todos os pedidos de serviço do Exchange para dispositivos diretamente com a Microsoft.

> [!NOTE]
> Quando os clientes usam um parceiro para devolver dispositivos, o parceiro é responsável por gerenciar o processo do Exchange, incluindo o cancelamento do registro e registro de dispositivos no Windows AutoPilot.

## Parceiros Surface habilitados para o piloto automático do Windows

Selecionar os parceiros Surface podem registrar dispositivos de superfície no Windows AutoPilot para você no momento da compra. Eles também podem enviar dispositivos registrados diretamente para seus usuários. Os dispositivos podem ser configurados completamente por meio de um processo de Zero-Touch usando o piloto automático do Windows, o Azure AD e o gerenciamento de dispositivos móveis.

Os parceiros Surface que são habilitados para o piloto automático do Windows incluem:

| Parceiros nos EUA | Parceiros globais | Distribuidores dos EUA |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [TAMBÉM](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Conexões](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Esclarecer](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [SHI](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Confiança protegida](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## Saiba mais

Para obter mais informações sobre o piloto automático do Windows, consulte:
- [Visão geral do Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Requisitos do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)