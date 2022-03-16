---
title: Windows Autopilot e dispositivos Surface
ms.reviewer: ''
manager: laurawi
description: Saiba mais sobre as Windows de implantação do Autopilot para dispositivos Surface.
keywords: autopilot, Windows 10, Windows 11, superfície, implantação
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ca2dab5483ecb7ae11a102c56308742e348156bb
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448524"
---
# <a name="windows-autopilot-and-surface-devices"></a>Windows Autopilot e dispositivos Surface

Windows Autopilot é uma tecnologia de implantação baseada em nuvem no Windows 10 e Windows 11. Você pode usar Windows Autopilot remotamente para implantar e configurar dispositivos em um processo de toque zero imediatamente.

Tradicionalmente, os profissionais de IT gastam muito tempo criando e personalização de imagens que serão implantadas posteriormente em dispositivos que já vêm com um sistema operacional perfeitamente bom já instalado neles. Windows Autopilot introduz uma nova abordagem de implantação de toque zero usando uma coleção de tecnologias para configurar e configurar Windows dispositivos. Isso permite que um departamento de TI configure/personalize imagens com pouca ou nenhuma infraestrutura para gerenciar e um processo fácil e simples. Da perspectiva do usuário, ele só precisa de algumas etapas simples para levar o Surface a um estado produtivo. Na verdade, a única interação necessária do usuário final é se conectar a uma rede e verificar suas credenciais. Tudo depois disso é totalmente automatizado.

Windows Autopilot permite:

- Associar automaticamente dispositivos ao Azure Active Directory (Azure AD).
- Registrar automaticamente dispositivos em serviços MDM, como Microsoft Intune (requer uma assinatura Azure AD Premium de segurança).
- Restringir a criação de uma conta de Administrador. O piloto automático é a única maneira de ter a primeira pessoa que faz logo Windows entrar como um usuário padrão.
- Crie e atribua automaticamente dispositivos a grupos de configuração com base nos perfis de dispositivo.
- Personalizar conteúdo e identidade visual OOBE (Experiência In-loco) para atender aos requisitos organizacionais.
- Habilitar a configuração completa do dispositivo com o Intune.
- Redefinir ou reiniciar dispositivos remotamente.

## <a name="how-it-works"></a>Como funciona

Windows os dispositivos registrados no Autopilot são identificados pela Internet na primeira inicialização por meio de uma assinatura de dispositivo exclusiva chamada *hash de hardware*. Eles são automaticamente inscritos e configurados usando soluções de gerenciamento modernas, como o Azure Active Directory (Azure AD) e o gerenciamento de dispositivos móveis.

Você pode registrar dispositivos Surface no momento da compra de um parceiro surface habilitado para Windows Autopilot. Esses parceiros podem enviar novos dispositivos diretamente para seus usuários. Os dispositivos serão automaticamente inscritos e configurados quando eles são ativados pela primeira vez. Esse processo elimina a geração de imagens durante a implantação, o que permite implementar novos métodos ágeis de gerenciamento e distribuição de dispositivos.

## <a name="modern-management"></a>Gerenciamento moderno

O Piloto Automático é a opção de implantação recomendada para dispositivos Surface, incluindo Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Pro 7+, Surface Laptop 4 e Surface Pro X, que foi projetado especificamente para implantação por meio do Autopilot.

 É melhor registrar seus dispositivos Surface com a ajuda de um Provedor de Soluções na Nuvem da Microsoft. Esta etapa permite que você gerencie as configurações de firmware UEFI no Surface diretamente do Intune. Elimina a necessidade de tocar fisicamente em dispositivos para gerenciamento de certificados. Consulte [Gerenciamento do Intune de configurações uefi do Surface](surface-manage-dfci-guide.md) para obter detalhes.

## <a name="windows-version-considerations"></a>Windows considerações de versão

A ampla implantação de dispositivos Surface por meio do Windows Autopilot, incluindo o registro por parceiros do Surface no momento da compra, requer Windows 10 versão 1709 (Fall Creators Update) ou posterior.

Essas Windows versões suportam um valor de hash de 4.000 byte (4k) que identifica exclusivamente dispositivos para o Windows Autopilot, o que é necessário para implantações em escala.

## <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Exchange experiência em dispositivos Surface que precisam de reparo ou substituição

A Microsoft verifica automaticamente cada registro do Surface for Autopilot e desregulamenta o dispositivo do locatário do cliente.  A Microsoft garante que o dispositivo de substituição seja inscrito no Windows Autopilot quando uma substituição for enviada de volta para o cliente. Esse serviço está disponível em todos os pedidos de serviço de troca de dispositivo diretamente com a Microsoft.

> [!NOTE]
> Quando os clientes usam um Parceiro para retornar dispositivos, o Parceiro é responsável por gerenciar o processo do exchange, incluindo a desregulamentação e registro de dispositivos no Windows Autopilot.

## <a name="microsoft-support-registration"></a>Registro do Suporte da Microsoft

Os clientes e os CSPs (Provedores de Soluções de Nuvem da Microsoft) têm a opção de registrar dispositivos Surface enviando solicitações ao Suporte da Microsoft. Para saber mais, consulte [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).

## <a name="surface-partners-enabled-for-windows-autopilot"></a>Parceiros surface habilitados para Windows Autopilot

Selecione Parceiros do Surface podem registrar dispositivos Surface no Windows Autopilot para você no momento da compra. Eles também podem enviar dispositivos inscritos diretamente para seus usuários. Os dispositivos podem ser configurados inteiramente por meio de um processo de toque zero usando o Windows Autopilot, o Azure AD e o gerenciamento de dispositivos móveis.

Os parceiros surface habilitados para Windows Autopilot incluem:

| Parceiros dos EUA | Parceiros globais | Distribuidores dos EUA |
|--------------|---------------|-------------------|
|  [CDW](https://www.cdw.com/) |  [ALSO](https://www.also.com/ec/cms5/da_2800/2800-msportal/products-and-solutions/surface/surface-is-more/surface-and-wa/index.jsp) |  [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
|  [Conexão](https://www.connection.com/brand/microsoft/microsoft-surface)   |  [ATEA](https://www.atea.com/) |  [Techdata](https://www.techdata.com/)  |
|  [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  |  [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) |  [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
|  [SHI](https://www.shi.com/Surface) |  [Cancom](https://www.cancom.de/) |    |
|  [LDI Conexão](https://www.myldi.com/managed-it/)  |  [Computacenter](https://www.computacenter.com/uk) |    |
|  [F1](https://www.functiononeit.com/#empower)  |   |  |
|  [Confiança Protegida](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | |

## <a name="learn-more"></a>Saiba mais

Para obter mais informações sobre Windows Autopilot, consulte:

- [Visão geral do Windows Autopilot.](/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Requisitos do Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Suporte a Registro Surface para o Windows Autopilot](surface-autopilot-registration-support.md)
