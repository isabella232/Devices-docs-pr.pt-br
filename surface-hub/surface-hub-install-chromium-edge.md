---
title: Gerenciar Microsoft Edge no Surface Hub
description: Este artigo descreve as configurações Microsoft Edge política padrão e as ferramentas para definir as configurações do navegador.
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
ms.openlocfilehash: b652b990ce798d807ff2a27e87d212d01f3c23a2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497724"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>Gerenciar Microsoft Edge no Surface Hub

Use [Microsoft Edge de navegador](/deployedge/microsoft-edge-policies) para definir as configurações do navegador Microsoft Edge por meio de qualquer um dos seguintes métodos:

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Seu provedor MDM (mobile Gerenciamento de Dispositivos) preferencial que dá suporte à ingestão ADMX](/deployedge/configure-edge-with-mdm)
- [Provisionamento de pacotes usando a ingestão ADMX no designer Windows configuração](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> O gesto de deslizar para baixo da parte superior da tela para sair do modo de tela inteira requer dois dedos com o novo Microsoft Edge. A ação de saída em tela inteira também está disponível no menu de contexto exibido após um toque de pressionamento longo.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Políticas Microsoft Edge padrão para Surface Hub

Microsoft Edge é pré-configurado com as configurações de política a seguir para fornecer uma experiência otimizada para Surface Hub.


> [!TIP]
> É recomendável manter o valor padrão para essas configurações de política.

| Configuração de política                                                                                                   | Experiência recomendada                                                                                                                                                                                                                                               | Valor padrão |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Não importe automaticamente tipos de dados e configurações de Versão Prévia do Microsoft Edge. Isso evita alterar perfis de usuários conectados com configurações compartilhadas do Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permita Microsoft Edge processos continuem em execução em segundo plano mesmo após o fechamento da última janela do navegador, permitindo acesso mais rápido a aplicativos Web durante uma sessão.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Não permita que os usuários criem novos perfis no Microsoft Edge. Isso simplifica a navegação e a experiência de conexão.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que apenas um usuário entre no Microsoft Edge. Isso simplifica a navegação e a experiência de conexão                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Permite que os usuários aproveitem o SSO (Sign-On único) no Microsoft Edge. Quando um usuário está conectado ao Surface Hub, suas credenciais podem fluir para sites com suporte sem exigir que ele se autentique novamente.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impede que usuários não administradores instalem novas extensões no Microsoft Edge. Para configurar uma lista de extensões a serem instaladas por padrão, use [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta a primeira experiência de execução e a tela inicial que normalmente são mostradas quando os usuários executam Microsoft Edge pela primeira vez. Como Surface Hub é um dispositivo compartilhado, isso simplifica a experiência do usuário.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Desabilita o modo InPrivate. Como a Sessão Final já limpa os dados de navegação, isso simplifica a experiência de navegação e de entrada.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Mostra a experiência Office 365 feed em novas páginas de guia. Quando um usuário está conectado ao Surface Hub, isso permite acesso rápido aos arquivos e conteúdo no Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Quando um usuário estiver conectado Surface Hub, um perfil não removível será criado usando sua conta organizacional. Isso simplifica a experiência de SSO (Sign-On single Sign-On).                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Desabilita a impressão Microsoft Edge. Surface Hub não dá suporte à impressão.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite Microsoft Edge autenticar proativamente usuários conectados com serviços Microsoft. Isso simplifica a experiência de SSO (Sign-On single Sign-On).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Salva automaticamente os arquivos na pasta Downloads, em vez de perguntar aos usuários onde salvar o arquivo. Isso simplifica a experiência de navegação.                                                                                                                             | 0                 |

> [!TIP]
> Os PWAs (aplicativos Web progressivos) implantáveis agora têm suporte Windows 10 Team sistema operacional. Para saber mais, confira [Instalar o Aplicativos Web Progressivo no Surface Hub](install-pwa-surface-hub.md). 

### <a name="configure-microsoft-edge-updates"></a>Configurar Microsoft Edge atualizações

Por padrão, o Microsoft Edge é atualizado automaticamente. Use [Microsoft Edge políticas de atualização](/deployedge/microsoft-edge-update-policies) para definir configurações para Microsoft Edge Update. Observe que Surface Hub não dá suporte à **configuração de política CreateDesktopShortcut**, pois Surface Hub não usa atalhos da área de trabalho.

> [!TIP]
> O Microsoft Edge requer conectividade com a Internet para dar suporte aos recursos. Adicione as [URLs de domínio necessárias à](/deployedge/microsoft-edge-security-endpoints) lista Permitir para garantir a comunicação por meio de firewalls e outros mecanismos de segurança.

## <a name="related-links"></a>Links relacionados

- [Documentação do Microsoft Edge](/microsoft-edge/)