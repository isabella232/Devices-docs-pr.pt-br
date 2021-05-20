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
ms.openlocfilehash: 93f76cadafe2570197fbe70db88540b6be90c3f1
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576721"
---
# <a name="install-and-configure-the-new-microsoft-edge-on-surface-hub"></a>Instale e configure o novo Microsoft Edge no Surface Hub

Windows 10 Team Atualização 2020 dá suporte ao novo Microsoft Edge com base no Chromium (versão 85 e acima) como o navegador recomendado para Surface Hub 2S e Surface Hub (v1). Este artigo explica como instalar o navegador usando um dos três métodos: um pacote de provisionamento, um Microsoft Intune ou um provedor de gerenciamento de dispositivo móvel (MDM) de terceiros.

> [!IMPORTANT]
> Por padrão, Surface Hub dispositivos são pré-instalados com Versão Prévia do Microsoft Edge (versão 44). Depois de instalar a [Atualização 2020,](surface-hub-2020-update.md)é recomendável alternar para o novo Microsoft Edge navegador; o suporte [para Versão Prévia do Microsoft Edge](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) terminará em 9 de março de 2021.

> [!NOTE]
> O passar o dedo para baixo da parte superior do gesto de tela para sair do modo de tela inteira requer dois dedos com o novo Microsoft Edge. A ação de saída de tela inteira também está disponível no menu de contexto exibido após um toque de pressão longa.


## <a name="install-microsoft-edge-using-a-provisioning-package"></a>Instalar Microsoft Edge usando um pacote de provisionamento

1. Em um computador, baixe o pacote Microsoft Edge de [provisionamento](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) para a pasta raiz de uma unidade USB.
2. Insira a unidade USB no Surface Hub.
3. A partir Surface Hub, **abra Configurações** e insira suas credenciais de administrador quando solicitado.
4. Navegue até **Surface Hub** > **Gerenciamento de dispositivo**. Em **Pacotes de provisionamento**, selecione **Adicionar ou remover um pacote de provisionamento**.
5. Selecione **Adicionar um pacote**.
6. Escolha o Microsoft Edge de provisionamento e selecione **Adicionar**.
7. Você verá um resumo das alterações que o pacote de provisionamento aplica. Selecione **Sim, adicionar**.
8. Aguarde a conclusão Microsoft Edge instalação do Microsoft Edge. Depois de instalado, navegue até o menu iniciar Surface Hub para acessar o novo Microsoft Edge.              

> [!NOTE]
> Se houver uma versão mais recente do Microsoft Edge disponível, ela será atualizada automaticamente.
 
## <a name="install-microsoft-edge-using-intune"></a>Instalar Microsoft Edge usando o Intune
 
> [!NOTE]
> Para usar esse método de instalação, o dispositivo Surface Hub deve ser inscrito e gerenciado usando o Intune. Para obter mais informações, consulte [Manage Surface Hub 2S with MDM](manage-settings-with-mdm-for-surface-hub.md).
 

1. [Baixe o Microsoft Edge instalador](https://www.microsoft.com/edge/business/download).
    - Usar a versão atual do [canal Estável](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versão 85)**
    - Escolha **Windows 64 bits**
2. [Adicione o Microsoft Edge como um aplicativo de](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)linha de negócios para Microsoft Intune .
    - Se você optar por usar Microsoft Edge Update para lidar com atualizações automáticas para **** Microsoft Edge, configure a versão Ignorar aplicativo configurando o painel de informações **do** aplicativo. Quando você alterna essa configuração para **Sim**, Microsoft Intune não imporá a versão do aplicativo instalada no Surface Hub dispositivo.

## <a name="install-microsoft-edge-using-third-party-mdm-provider"></a>Instalar Microsoft Edge usando provedor MDM de terceiros

1. [Baixe o Microsoft Edge instalador da Microsoft](https://www.microsoft.com/edge/business/download).
    - Usar a versão atual do [canal Estável](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versão 85)**
    - Escolha **Windows 64 bits**
2. Stage the Microsoft Edge installer on a hosted location, such as a local file share (\\server\share\MicrosoftEdgeEnterpriseX64.msi). O Surface Hub dispositivo deve ter permissão para acessar o local hospedado.
3. Use [o EnterpriseDesktopAppManagement Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) por meio do provedor MDM para instalar Microsoft Edge.

## <a name="configure-microsoft-edge"></a>Configurar o Microsoft Edge

### <a name="default-microsoft-edge-policies-for-surface-hub"></a>Políticas Microsoft Edge padrão para Surface Hub

Microsoft Edge é pré-configurado com os seguintes setttings de política para fornecer uma experiência otimizada para Surface Hub.
 
> [!TIP]
> É recomendável manter o valor padrão para essas configurações de política.
 

| Configuração de política                                                                                                   | Experiência recomendada                                                                                                                                                                                                                                               | Valor padrão |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Não importe automaticamente tipos de dados e configurações de Versão Prévia do Microsoft Edge. Isso evita a alteração dos perfis de usuários assinados com as configurações compartilhadas do Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permitir Microsoft Edge processos continuem sendo executados em segundo plano mesmo após o fechamento da última janela do navegador, permitindo acesso mais rápido a aplicativos Web durante uma sessão.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Não permita que os usuários criem novos perfis Microsoft Edge. Isso simplifica a experiência de navegação e de acesso.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que apenas um usuário entre Microsoft Edge. Isso simplifica a experiência de navegação e de acesso                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permite que os usuários aproveitem o SSO (single Sign-On) no Microsoft Edge. Quando um usuário está Surface Hub, suas credenciais podem fluir para sites com suporte sem exigir que eles se reautentem.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impede que usuários não administradores instalem novas extensões no Microsoft Edge. Para configurar uma lista de extensões a serem instaladas por padrão, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta a primeira experiência de executar e a tela inicial que normalmente é mostrada quando os usuários são executados Microsoft Edge pela primeira vez. Como Surface Hub é um dispositivo compartilhado, isso simplifica a experiência do usuário.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Desabilita o modo InPrivate. Como a Sessão Final já limpa os dados de navegação, isso simplifica a experiência de navegação e de acesso.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Mostra a Office 365 de feed em novas páginas de tabulação. Quando um usuário está Surface Hub, isso permite acesso rápido a seus arquivos e conteúdo em Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Quando um usuário estiver Surface Hub, um perfil não removível será criado usando sua conta organizacional. Isso simplifica a experiência de Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Desabilita a impressão em Microsoft Edge. Surface Hub não dá suporte à impressão.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite Microsoft Edge autenticar proativamente os usuários que estão serviços Microsoft. Isso simplifica a experiência de Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Salva automaticamente arquivos na pasta Downloads, em vez de perguntar aos usuários onde salvar o arquivo. Isso simplifica a experiência de navegação.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Os aplicativos Web progressivos implantáveis (PWAs) não têm suporte no Windows 10 Team operacional.  Observe também que a configuração Microsoft Edge política [webAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) não é suportada em Surface Hub. 

### <a name="configure-microsoft-edge-policy-settings"></a>Configurar Microsoft Edge de política

Use [Microsoft Edge de navegador para](https://docs.microsoft.com/deployedge/microsoft-edge-policies) definir as configurações do navegador em Microsoft Edge. Essas políticas podem ser aplicadas usando:

- [Microsoft Intune,](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Seu provedor de gerenciamento de dispositivo móvel (MDM) preferencial que oferece suporte à Ingestão ADMX](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)ou
- [Provisionamento de pacotes usando a Ingestão ADMX no Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### <a name="configure-microsoft-edge-updates"></a>Configurar Microsoft Edge atualizações

Por padrão, Microsoft Edge é atualizado automaticamente. Use [Microsoft Edge políticas de atualização](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) para configurar configurações para Microsoft Edge Update.
Observe que Surface Hub não dá suporte às seguintes políticas Microsoft Edge de atualização:

- **Allowsxs** – No Surface Hub, Microsoft Edge canal estável sempre substitui Versão Prévia do Microsoft Edge.
- **CreateDesktopShortcut** – Surface Hub não usa atalhos da área de trabalho.

> [!TIP]
>  O Microsoft Edge requer conectividade com a Internet para dar suporte aos recursos. Certifique-se [de que as URLs de](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) domínio necessárias sejam adicionadas à lista Permitir para garantir comunicações por meio de firewalls e outros mecanismos de segurança.

## <a name="related-links"></a>Links relacionados

- [Documentação do Microsoft Edge](https://docs.microsoft.com/microsoft-edge/)

