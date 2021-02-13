---
title: Instale e configure o novo Microsoft Edge no Surface Hub
description: Instale e configure o novo Microsoft Edge no Surface Hub.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 2bc11fb18137ce21cba27368e0c12bbb9e73a4c2
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327305"
---
# Instale e configure o novo Microsoft Edge no Surface Hub

A Atualização do Windows 10 Team 2020 dá suporte ao novo Microsoft Edge baseado no Chromium (versão 85 e superior) como o navegador recomendado para o Surface Hub 2S e o Surface Hub (v1). Este artigo explica como instalar o navegador usando um dos três métodos: um pacote de provisionamento, o Microsoft Intune ou um provedor de gerenciamento de dispositivo móvel (MDM) de terceiros.

> [!IMPORTANT]
> Por padrão, os dispositivos Surface Hub são pré-instalados com a Versão Herdada do Microsoft Edge (versão 44). Depois de instalar a [Atualização de 2020,](surface-hub-2020-update.md)é recomendável alternar para o novo navegador Microsoft Edge; o suporte [para a Herdação do Microsoft Edge](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) terminará em 9 de março de 2021.

## Instalar o Microsoft Edge usando um pacote de provisionamento

1. Em um computador, baixe o pacote de [provisionamento](https://aka.ms/HubEdge) do Microsoft Edge (MicrosoftEdgeInstaller.ppkg) para a pasta raiz de uma unidade USB.
2. Insira a unidade USB no Surface Hub.
3. No Surface Hub, abra **As Configurações** e insira suas credenciais de administrador quando solicitado.
4. Navegue até **Surface Hub** > **Gerenciamento de dispositivo**. Em **Pacotes de provisionamento**, selecione **Adicionar ou remover um pacote de provisionamento**.
5. Selecione **Adicionar um pacote**.
6. Escolha o pacote de provisionamento do Microsoft Edge e selecione **Adicionar**.
7. Você verá um resumo das alterações que o pacote de provisionamento aplica. Selecione **Sim, adicionar**.
8. Aguarde a conclusão da instalação do Microsoft Edge. Depois de instalado, navegue até o menu Iniciar do Surface Hub para acessar o novo Microsoft Edge.              

> [!NOTE]
> Se houver uma versão mais recente do Microsoft Edge disponível, ela será atualizada automaticamente.
 
## Instalar o Microsoft Edge usando o Intune
 
> [!NOTE]
> O dispositivo Surface Hub deve ser inscrito e gerenciado usando o Intune. Para obter mais informações, [consulte Gerenciar o Surface Hub 2S com o Microsoft Intune.](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [Baixe o instalador do Microsoft Edge.](https://www.microsoft.com/edge/business/download)
    - Usar a versão atual do [canal Estável](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versão 85)**
    - Escolher **o Windows de 64 bits**
2. [Adicione o instalador do Microsoft Edge como um aplicativo de linha de negócios ao Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - Se você optar por usar o Microsoft Edge Update para manipular **** atualizações automáticas para o Microsoft Edge, certifique-se de configurar a versão Ignorar aplicativo configurando o painel de informações **do** aplicativo. Quando você alternar essa configuração para **Sim,** o Microsoft Intune não imporá a versão do aplicativo instalada no dispositivo Surface Hub.

## Instalar o Microsoft Edge usando provedor de MDM de terceiros

1. [Baixe o instalador do Microsoft Edge da Microsoft.](https://www.microsoft.com/edge/business/download)
    - Usar a versão atual do [canal Estável](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versão 85)**
    - Escolher **o Windows de 64 bits**
2. Stage the Microsoft Edge installer on a hosted location, such as a local file share (\\server\share\MicrosoftEdgeEnterpriseX64.msi). O dispositivo Surface Hub deve ter permissão para acessar o local hospedado.
3. Use o Provedor de Serviços de [Configuração (CSP) EnterpriseDesktopAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) por meio de seu provedor MDM para instalar o Microsoft Edge.

## Configurar o Microsoft Edge

### Políticas padrão do Microsoft Edge para o Surface Hub

O Microsoft Edge é pré-configurado com as configurações de política a seguir para fornecer uma experiência otimizada para o Surface Hub.
 
> [!TIP]
> É recomendável manter o valor padrão para essas configurações de política.
 

| Configuração de política                                                                                                   | Experiência recomendada                                                                                                                                                                                                                                               | Valor padrão |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Não importe automaticamente tipos de dados e configurações da Herdado do Microsoft Edge. Isso evita alterar os perfis dos usuários com configurações compartilhadas do Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permita que os processos do Microsoft Edge continuem em execução em segundo plano mesmo após o fechamento da última janela do navegador, permitindo acesso mais rápido aos aplicativos Web durante uma sessão.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Não permitir que os usuários criem novos perfis no Microsoft Edge. Isso simplifica a navegação e a experiência de acesso.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que apenas um usuário entre no Microsoft Edge. Isso simplifica a navegação e a experiência de acesso                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permite que os usuários aproveitem o SSO (Sign-On único) no Microsoft Edge. Quando um usuário entra no Surface Hub, suas credenciais podem fluir para sites com suporte sem exigir que eles se autentram.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impede que usuários não administradores instalem novas extensões no Microsoft Edge. Para configurar uma lista de extensões a serem instaladas por padrão, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta a tela inicial e a experiência de primeira vez que normalmente são mostradas quando os usuários executarem o Microsoft Edge pela primeira vez. Como o Surface Hub é um dispositivo compartilhado, isso simplifica a experiência do usuário.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Desabilita o modo InPrivate. Como a Sessão Final já limpa os dados de navegação, isso simplifica a experiência de navegação e de acesso.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Mostra a experiência de feed do Office 365 em novas páginas de guia. Quando um usuário entra no Surface Hub, isso permite acesso rápido a seus arquivos e conteúdo no Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Quando um usuário estiver entrando no Surface Hub, um perfil não removível será criado usando sua conta organizacional. Isso simplifica a experiência de Sign-On único (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Desabilita a impressão no Microsoft Edge. O Surface Hub não dá suporte à impressão.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite que o Microsoft Edge autentifica proativamente os usuários assinados com os serviços Microsoft. Isso simplifica a experiência de Sign-On único (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Salva automaticamente os arquivos na pasta Downloads, em vez de perguntar aos usuários onde salvar o arquivo. Isso simplifica a experiência de navegação.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Aplicativos Web progressivos (PWAs) implantáveis não têm suporte no sistema operacional Windows 10 Team.  Observe também que a configuração de política do Microsoft Edge [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) não é suportada no Surface Hub. 

### Definir configurações de política do Microsoft Edge

Use [as políticas do navegador Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) para definir as configurações do navegador no Microsoft Edge. Essas políticas podem ser aplicadas usando:

- [Microsoft Intune,](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Seu provedor de gerenciamento de dispositivo móvel (MDM) preferencial que oferece suporte à ingestão de ADMX](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)ou
- [Pacotes de provisionamento usando ingestão ADMX no Designer de Configuração do Windows.](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### Configurar atualizações do Microsoft Edge

Por padrão, o Microsoft Edge é atualizado automaticamente. Use [as políticas de atualização do Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) para definir as configurações do Microsoft Edge Update.
Observe que o Surface Hub não dá suporte às seguintes políticas de atualização do Microsoft Edge:

- **Allowsxs** – No Surface Hub, o canal estável do Microsoft Edge sempre substitui a Versão Herdada do Microsoft Edge.
- **CreateDesktopShortcut** – o Surface Hub não usa atalhos da área de trabalho.

> [!TIP]
>  O Microsoft Edge requer conectividade com a Internet para dar suporte aos recursos. Certifique-se [de que as URLs de](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) domínio necessárias sejam adicionadas à lista de Permitir para garantir a comunicação por meio de firewalls e outros mecanismos de segurança.

## Links relacionados

- [Documentação do Microsoft Edge](https://docs.microsoft.com/microsoft-edge/)

