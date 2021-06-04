---
title: Windows Autopilot e dispositivos Surface
ms.reviewer: ''
manager: laurawi
description: Saiba mais sobre as opções de implantação do Windows Autopilot para dispositivos Surface.
keywords: autopilot, windows 10, surface, implantação
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
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271097"
---
# Windows Autopilot e dispositivos Surface

O Windows Autopilot é uma tecnologia de implantação baseada em nuvem no Windows 10. Você pode usar o Windows Autopilot para implantar e configurar dispositivos remotamente em um processo de zero toque imediatamente.

Tradicionalmente, os profissionais de IT gastam muito tempo criando e personalização de imagens que serão implantadas posteriormente em dispositivos que já vêm com um sistema operacional perfeitamente bom já instalado neles. O Windows Autopilot introduz uma nova abordagem de implantação de toque zero usando uma coleção de tecnologias para configurar e configurar dispositivos Windows. Isso permite que um departamento de TI configure/personalize imagens com pouca ou nenhuma infraestrutura para gerenciar e um processo fácil e simples. Da perspectiva do usuário, são necessárias apenas algumas etapas simples para levar o Surface a um estado produtivo. Na verdade, a única interação necessária do usuário final é se conectar a uma rede e verificar suas credenciais. Tudo depois disso é totalmente automatizado.

O Windows Autopilot permite que você:

- Ingressar dispositivos automaticamente no Azure Active Directory (Azure AD).
- Registrar dispositivos automaticamente em serviços MDM, como o Microsoft Intune (requer uma assinatura do Azure AD Premium).
- Restringir a criação de uma conta de Administrador. O Autopilot é a única maneira de fazer com que a primeira pessoa que entrar no Windows entre como um usuário padrão.
- Criar e atribuir dispositivos automaticamente a grupos de configuração com base em perfis de dispositivo.
- Personalize o conteúdo da OOBE (Configuração Original) e a identidade visual para atender aos requisitos organizacionais.
- Habilitar a configuração completa do dispositivo com o Intune.
- Redefina ou reinicie dispositivos remotamente.

##  <a name="how-it-works"></a>Como funciona

Os dispositivos registrados no Windows Autopilot são identificados pela Internet na primeira inicialização por meio de uma assinatura de dispositivo exclusiva chamada *de hash de hardware.* Eles são automaticamente inscritos e configurados usando soluções de gerenciamento modernas, como o Azure Active Directory (Azure AD) e o gerenciamento de dispositivos móveis.

Você pode registrar dispositivos Surface no momento da compra de um parceiro Surface que está habilitado para o Windows Autopilot. Esses parceiros podem enviar novos dispositivos diretamente para seus usuários. Os dispositivos serão automaticamente inscritos e configurados quando são ativados pela primeira vez. Esse processo elimina a geração de imagens durante a implantação, o que permite implementar novos métodos ágeis de gerenciamento e distribuição de dispositivos.

##  <a name="modern-management"></a>Gerenciamento moderno

O Autopilot é a opção de implantação recomendada para dispositivos Surface, incluindo Surface Pro 7+, Surface Laptop 3, Surface Pro 7 e Surface Pro X, projetado especificamente para implantação por meio do Autopilot.

 É melhor registrar seus dispositivos Surface com a ajuda de um Provedor de Soluções na Nuvem da Microsoft. Esta etapa permite que você gerencie as configurações de firmware UEFI no Surface diretamente do Intune. Isso elimina a necessidade de tocar dispositivos fisicamente para o gerenciamento de certificados. Confira [o gerenciamento do Intune das configurações de UEFI do Surface](surface-manage-dfci-guide.md) para obter detalhes.

##  <a name="windows-version-considerations"></a>Considerações sobre a versão do Windows

A ampla implantação de dispositivos Surface por meio do Windows Autopilot, incluindo o registro por parceiros do Surface no momento da compra, requer o Windows 10 versão 1709 (Fall Creators Update) ou posterior.

Essas versões do Windows suportam um valor de hash de 4.000 byte (4k) que identifica exclusivamente dispositivos para o Windows Autopilot, o que é necessário para implantações em escala. Todos os novos dispositivos Surface, incluindo o Surface Pro 7+, o Surface Pro X e o Surface Laptop 3 são compatíveis com o Windows 10 versão 1903 ou posterior.

##  <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Experiência do Exchange em dispositivos Surface que precisam de reparo ou substituição

A Microsoft verifica automaticamente cada registro do Surface para piloto automático e desregula o dispositivo do locatário do cliente.  A Microsoft garante que o dispositivo de substituição seja inscrito no Windows Autopilot assim que uma substituição for enviada de volta para o cliente. Esse serviço está disponível em todos os pedidos de serviço de troca de dispositivos diretamente com a Microsoft.

> [!NOTE]
> Quando os clientes usam um Parceiro para retornar dispositivos, o parceiro é responsável por gerenciar o processo de troca, incluindo o desregistente e o registro de dispositivos no Windows Autopilot.

##  <a name="microsoft-support-registration"></a>Registro do Suporte da Microsoft

Os clientes e os CSPs (Provedores de Soluções na Nuvem da Microsoft) têm a opção de registrar dispositivos Surface enviando solicitações ao Suporte da Microsoft. Para saber mais, consulte Suporte [ao registro do Surface para o Windows Autopilot.](surface-autopilot-registration-support.md)

##  <a name="surface-partners-enabled-for-windows-autopilot"></a>Parceiros Surface habilitados para o Windows Autopilot

Os parceiros selecionados do Surface podem registrar dispositivos Surface no Windows Autopilot para você no momento da compra. Eles também podem enviar dispositivos inscritos diretamente para seus usuários. Os dispositivos podem ser configurados inteiramente por meio de um processo de toque zero usando o Windows Autopilot, o Azure AD e o gerenciamento de dispositivos móveis.

Os parceiros Surface habilitados para o Windows Autopilot incluem:

| Parceiros dos EUA | Parceiros globais | Distribuidores dos EUA |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [ALÉM DISSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Conexão](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [ASE](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Confiança Protegida](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

##  <a name="learn-more"></a>Saiba mais

Para obter mais informações sobre o Windows Autopilot, consulte:
- [Visão geral do Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Requisitos do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Suporte a Registro Surface para o Windows Autopilot](surface-autopilot-registration-support.md)