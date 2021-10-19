---
title: Gerenciar Microsoft Edge no Surface Hub
description: Este artigo descreve as configurações Microsoft Edge de política padrão e ferramentas para configurar as configurações do navegador.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 80e861fd575324db21be458f7b82cd5fdb538b50
ms.sourcegitcommit: 68b6e86919d6e29155bf9386d05279866e1157e5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2021
ms.locfileid: "12100709"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>Gerenciar Microsoft Edge no Surface Hub

Use [Microsoft Edge de navegador](/deployedge/microsoft-edge-policies) para configurar as configurações do navegador Microsoft Edge por meio de qualquer um dos seguintes métodos:

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Seu provedor MDM (Gerenciamento de Dispositivo Móvel) preferencial que oferece suporte à Ingestão ADMX](/deployedge/configure-edge-with-mdm)
- [Provisionamento de pacotes usando a Ingestão ADMX no Windows Configuration Designer](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> O passar o dedo para baixo da parte superior do gesto de tela para sair do modo de tela inteira requer dois dedos com o novo Microsoft Edge. A ação de saída de tela inteira também está disponível no menu de contexto exibido após um toque de pressão longa.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Políticas Microsoft Edge padrão para Surface Hub

Microsoft Edge é pré-configurado com os seguintes setttings de política para fornecer uma experiência otimizada para Surface Hub.


> [!TIP]
> É recomendável manter o valor padrão para essas configurações de política.

| Configuração de política                                                                                                   | Experiência recomendada                                                                                                                                                                                                                                               | Valor padrão |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Não importe automaticamente tipos de dados e configurações de Versão Prévia do Microsoft Edge. Isso evita a alteração dos perfis de usuários assinados com as configurações compartilhadas do Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permitir Microsoft Edge processos continuem sendo executados em segundo plano mesmo após o fechamento da última janela do navegador, permitindo acesso mais rápido a aplicativos Web durante uma sessão.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Não permita que os usuários criem novos perfis Microsoft Edge. Isso simplifica a experiência de navegação e de acesso.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que apenas um usuário entre Microsoft Edge. Isso simplifica a experiência de navegação e de acesso                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Permite que os usuários aproveitem o SSO (single Sign-On) no Microsoft Edge. Quando um usuário está Surface Hub, suas credenciais podem fluir para sites com suporte sem exigir que eles se reautentem.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impede que usuários não administradores instalem novas extensões no Microsoft Edge. Para configurar uma lista de extensões a serem instaladas por padrão, use [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta a primeira experiência de executar e a tela inicial que normalmente é mostrada quando os usuários são executados Microsoft Edge pela primeira vez. Como Surface Hub é um dispositivo compartilhado, isso simplifica a experiência do usuário.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Desabilita o modo InPrivate. Como a Sessão Final já limpa os dados de navegação, isso simplifica a experiência de navegação e de acesso.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Mostra a Office 365 de feed em novas páginas de tabulação. Quando um usuário está Surface Hub, isso permite acesso rápido a seus arquivos e conteúdo em Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Quando um usuário estiver Surface Hub, um perfil não removível será criado usando sua conta organizacional. Isso simplifica a experiência de Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Desabilita a impressão em Microsoft Edge. Surface Hub não dá suporte à impressão.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite Microsoft Edge autenticar proativamente os usuários que estão serviços Microsoft. Isso simplifica a experiência de Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Salva automaticamente arquivos na pasta Downloads, em vez de perguntar aos usuários onde salvar o arquivo. Isso simplifica a experiência de navegação.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Os aplicativos Web progressivos implantáveis (PWAs) não têm suporte no Windows 10 Team operacional.  Observe também que a configuração Microsoft Edge política [webAppInstallForceList](/deployedge/microsoft-edge-policies#webappinstallforcelist) não é suportada em Surface Hub.

### <a name="configure-microsoft-edge-updates"></a>Configurar Microsoft Edge atualizações

Por padrão, Microsoft Edge é atualizado automaticamente. Use [Microsoft Edge políticas de atualização](/deployedge/microsoft-edge-update-policies) para configurar configurações para Microsoft Edge Update. Observe que Surface Hub não dá suporte à configuração de política **CreateDesktopShortcut** como Surface Hub não usa atalhos de área de trabalho.

> [!TIP]
> O Microsoft Edge requer conectividade com a Internet para dar suporte aos recursos. Adicione as [URLs de domínio necessárias](/deployedge/microsoft-edge-security-endpoints) à lista Permitir para garantir comunicações por meio de firewalls e outros mecanismos de segurança.

## <a name="related-links"></a>Links relacionados

- [Documentação do Microsoft Edge](/microsoft-edge/)