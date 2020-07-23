---
title: Instalar e configurar o novo Microsoft Edge no Surface Hub
description: Instalar e configurar o novo Microsoft Edge no Surface Hub.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: cf4d909a8c06bddf2bb0b3e42259f0b69cd97109
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894097"
---
# Instalar e configurar o novo Microsoft Edge no Surface Hub

A atualização do Windows 10 Team 2020 oferece suporte ao novo Microsoft Edge baseado no Chromium (versão 85 e posterior) que o navegador recomendado para Surface Hub. Você pode instalar o Microsoft Edge manualmente usando um pacote de provisionamento, remotamente usando o Microsoft Intune ou seu provedor de gerenciamento de dispositivos móveis (MDM) preferido.

 Por padrão, os dispositivos Surface Hub são pré-instalados com o Microsoft Edge Legacy (versão 44).

> [!IMPORTANT]
> O Surface Hub requer a versão 85 ou posterior do novo Microsoft Edge, com disponibilidade limitada ao "[canal de desenvolvimento](https://docs.microsoft.com/deployedge/microsoft-edge-channels)", projetado para dar aos administradores de ti uma olhada antecipada na próxima funcionalidade de borda e se preparar para a próxima versão beta.  O suporte para o canal de desenvolvimento está temporariamente habilitado para os participantes do Windows a visualizarem o Microsoft Edge. (Normalmente, o Surface Hub suporta apenas versões lançadas para o "canal estável".) Para obter mais informações, consulte [visão geral do canal Microsoft Edge.](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
 
### Instalando os builds de canais de desenvolvimento do Microsoft Edge 

- Por design, o canal de desenvolvimento do Microsoft Edge é instalado lado a lado com o Microsoft Edge Legacy, e os usuários verão ambos "desenvolvimento do Microsoft Edge" (versão 85) e "Microsoft Edge" (versão 44) no menu Iniciar do Surface Hub. Em contraste, o canal estável do Microsoft Edge substituirá o Microsoft Edge Legacy como navegador padrão.
- Depois de instalado, o canal de desenvolvimento do Microsoft Edge não será exibido automaticamente como um aplicativo fixado. Para abrir, selecione **Iniciar**  >  **todos os aplicativos**. Em contraste, o canal estável do Microsoft Edge substitui automaticamente o Microsoft Edge Legacy como um aplicativo fixado na lista todos os aplicativos.
- Uma vez que a versão 85 seja promovida para canal estável, o canal de desenvolvimento do Microsoft Edge desaparecerá automaticamente do menu Iniciar, e você precisará instalar o canal estável do Microsoft Edge no Surface Hub.

> [!NOTE]
>  Uma redefinição de dispositivo é necessária para remover o novo Microsoft Edge. Consulte [redefinir ou recuperar um Surface Hub](https://docs.microsoft.com/surface-hub/device-reset-surface-hub) para obter mais informações.

## Instalar o Microsoft Edge

### Instalar o Microsoft Edge usando um pacote de provisionamento

1. Em um computador, baixe o [pacote de provisionamento do Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeDevInstaller. ppkg) para a pasta raiz de uma unidade USB.
2. Insira a unidade USB no Surface Hub.
3. Em Surface Hub, abra **configurações** e insira suas credenciais de administrador quando solicitado.
4. Navegue até **Surface Hub** > **Gerenciamento de dispositivo**. Em **Pacotes de provisionamento**, selecione **Adicionar ou remover um pacote de provisionamento**.
5. Selecione **Adicionar um pacote**.
6. Escolha o pacote de provisionamento do Microsoft Edge e selecione **Adicionar**.
7. Você verá um resumo das alterações que o pacote de aprovisionamento aplica. Selecione **Sim, adicionar**.
8. Aguarde até que a instalação do Microsoft Edge seja concluída. Depois de instalado, navegue até o menu Iniciar do Surface Hub para acessar o novo Microsoft Edge.              
Okey
> [!IMPORTANT]
>  Depois de instalado, o canal de desenvolvimento do Microsoft Edge não será exibido automaticamente como um aplicativo fixado no menu Iniciar do Surface Hub. Em vez disso, os usuários vão encontrá-lo em **Iniciar**  >  **todos os aplicativos**. Se você estiver usando o layout padrão do menu Iniciar, poderá instalar o menu iniciar com o [pacote de provisionamento do Microsoft Edge](https://aka.ms/HubEdge) para adicionar o Microsoft Edge como um aplicativo fixo. Para obter mais informações, consulte a seção a seguir: [Exibir o Microsoft Edge no menu Iniciar do Microsoft Edge](#display-start).

> [!NOTE]
> Se houver uma versão mais recente do Microsoft Edge disponível, ela será atualizada automaticamente.
 
### Instalar o Microsoft Edge usando o Intune
 
> [!NOTE]
> O dispositivo do Surface hub deve ser registrado e gerenciado usando o Intune. Para obter mais informações, consulte [gerenciar Surface Hub 2s com o Microsoft Intune](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune).
 

1. [Baixe o Microsoft Edge Installer da Microsoft](https://www.microsoft.com/edge/business/download).
    - Usar a versão atual do [canal de desenvolvimento](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versão 85)**
    - Escolher o **Windows 64-bit**
2. [Adicione o instalador do Microsoft Edge como um aplicativo de linha de negócios ao Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - Se você optar por usar o Microsoft Edge Update para manipular as atualizações automáticas para o Microsoft Edge, certifique-se de definir a configuração **ignorar a versão do aplicativo** no painel informações do **aplicativo** . Quando você alterna essa configuração para **Sim**, o Microsoft Intune não impedirá a versão do aplicativo que está instalada no dispositivo do Surface Hub.

 
### Instalar o Microsoft Edge usando o gerenciamento de dispositivos móveis

1. [Baixe o Microsoft Edge Installer da Microsoft](https://www.microsoft.com/edge/business/download).
    - Usar a versão atual do [canal de desenvolvimento](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versão 85)**
    - Escolher o **Windows 64-bit**
2. Testar o instalador do Microsoft Edge em um local hospedado, como um compartilhamento de arquivos local (\\server\share\MicrosoftEdgeEnterpriseX64.msi). O dispositivo de Surface hub deve ter permissão para acessar o local hospedado.
3. Use o [provedor de serviços de configuração EnterpriseDesktopAppManagement (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) por meio do seu provedor de MDM para instalar o Microsoft Edge.

 

## Configurar o Microsoft Edge

### Políticas padrão do Microsoft Edge para Surface Hub
O Microsoft Edge é pré-configurado com as políticas a seguir para oferecer uma experiência otimizada para o Surface Hub.
 
> [!NOTE]
>  Recomendamos manter o valor padrão para essas políticas.
 

| Políticas do Microsoft Edge                                                                                                    | Experiência recomendada                                                                                                                                                                                                                                               | Valor padrão |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Não importar automaticamente tipos de texto e configurações do Microsoft Edge herdado. Isso evita a alteração dos perfis dos usuários conectados com configurações compartilhadas do Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permitir que os processos do Microsoft Edge continuem sendo executados em segundo plano, mesmo depois que a última janela do navegador estiver fechada, permitindo acesso mais rápido a aplicativos Web durante uma sessão.                                                                                                      | um                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Não permitir que os usuários criem novos perfis no Microsoft Edge. Isso simplifica a navegação e a experiência que você está conectado.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que apenas um usuário entre no Microsoft Edge. Isso simplifica a navegação e a experiência que você está conectado                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permite que os usuários aproveitem o SSO (logon único) no Microsoft Edge. Quando um usuário é conectado ao Surface Hub, suas credenciais podem fluir para os websites com suporte sem exigir uma nova autenticação.  | um                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impede que usuários não administradores instalem novas extensões no Microsoft Edge. Para configurar uma lista de extensões a serem instaladas por padrão, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta a experiência de primeira execução e a tela inicial que normalmente são mostradas quando os usuários executam o Microsoft Edge pela primeira vez. Como o Surface Hub é um dispositivo compartilhado, isso simplifica a experiência do usuário.                                                                      | um                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Desabilita o modo InPrivate. Como a sessão final já limpa os dados de navegação, isso simplifica a navegação e a experiência que você está conectado.                                                                                                                                          | um                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Mostra a experiência de feed do Office 365 em novas páginas da guia. Quando um usuário é conectado ao Surface Hub, isso permite acesso rápido aos arquivos e conteúdo do Office 365.                                                                                                        | um                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Quando um usuário estiver conectado ao Surface Hub, um perfil não removível será criado usando sua conta organizacional. Isso simplifica a experiência de logon único (SSO).                                                                                                 | um                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Desabilita a impressão no Microsoft Edge. O Surface Hub não oferece suporte à impressão.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Habilita o Microsoft Edge a autenticar proativamente usuários conectados com serviços da Microsoft. Isso simplifica a experiência de logon único (SSO).                                                                                                                         | um                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Salva arquivos automaticamente na pasta downloads, em vez de perguntar aos usuários onde salvar o arquivo. Isso simplifica a experiência de navegação.                                                                                                                             | 0                 |

 
### Configurar as políticas do Microsoft Edge

Use [as políticas do navegador Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) para definir as configurações do navegador no Microsoft Edge. Essas políticas podem ser aplicadas usando:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Seu provedor de gerenciamento de dispositivos móveis (MDM) preferido que ofereça suporte ao ingestão de ADMX](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)ou
- [Provisionando pacotes usando a inclusão de ADMX no designer de configuração do Windows](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### Configurar atualizações do Microsoft Edge

Por padrão, o Microsoft Edge é atualizado automaticamente. Use [as políticas de atualização do Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) para definir configurações para o Microsoft Edge Update.
Observe que o Surface Hub não é compatível com as seguintes políticas de atualização do Microsoft Edge:

- **Allowsxs** – em Surface Hub, o canal estável do Microsoft Edge sempre substitui o Microsoft Edge Legacy.
- **CreateDesktopShortcut** – o Surface Hub não usa atalhos da área de trabalho.

> [!NOTE]
>  O Microsoft Edge requer conectividade com a Internet para dar suporte aos recursos. Certifique-se de que as [URLs de domínio necessárias](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) sejam adicionadas à lista de permissões para garantir a comunicação por meio de firewalls e outros mecanismos de segurança.
 
### <a name="display-start"></a> Exibir o Microsoft Edge no menu Iniciar do Surface Hub

Depois de instalado, o canal de desenvolvimento do Microsoft Edge não será exibido automaticamente como um aplicativo fixado no menu Iniciar do Surface Hub. Em vez disso, os usuários vão encontrá-lo em **Iniciar**  >  **todos os aplicativos**.
Se você estiver usando o layout padrão do menu Iniciar, poderá instalar o menu iniciar com o pacote de provisionamento do Microsoft Edge para adicionar o Microsoft Edge como um aplicativo fixo.
Se você quiser aplicar um layout personalizado do menu Iniciar, use o seguinte XML para adicionar um bloco fixado para o Microsoft Edge.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge Dev\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Para obter mais informações, consulte o [menu Iniciar do Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-start-menu).
 
> [!NOTE]
> O novo Microsoft Edge não oferece suporte a links e sites fixos usando o SecondaryTiles.

## Links relacionados

- [Documentação do Microsoft Edge](https://docs.microsoft.com/microsoft-edge/).

