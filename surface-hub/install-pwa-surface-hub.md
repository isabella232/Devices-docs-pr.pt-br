---
title: Instalar o Aplicativos Web Progressivo no Surface Hub
description: Explica como os administradores podem instalar PWAs (Aplicativos Web progressivos) no Surface Hub por meio Intune ou um pacote de provisionamento.
keywords: Surface Hub, PWAs, Aplicativo
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/22/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: ea30f25451b0be54bd2b6eaa2552036e0d78ff27
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472669"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>Instalar o Aplicativos Web Progressivo no Surface Hub

Os administradores podem instalar remotamente [PWAs (Aplicativos Web Progressivos)](/microsoft-edge/progressive-web-apps-chromium/) em Surface Hubs usando um MDM (provedor de gerenciamento de dispositivo móvel), como Microsoft Intune ou um pacote de provisionamento. Os PWAs funcionam como aplicativos nativos instalados em plataformas com suporte e funcionam como sites regulares em outros navegadores. Quando os administradores instalam PWAs no Surface Hub, os usuários podem executar diretamente no menu Aplicativo. 

> [!IMPORTANT]
> Antes de instalar PWAs, verifique se o Surface Hub tem [KB5011543](https://support.microsoft.com/help/5011543) (ou uma atualização Windows posterior) instalado. Para saber mais sobre as atualizações Windows 10 Team mais recentes, consulte [Surface Hub histórico de atualizações](surface-hub-update-history.md). 

- [Instalar PWAs no Surface Hub via Intune](#install-pwas-via-intune)
- [Instalar PWAs no Surface Hub por meio do pacote de provisionamento](#install-pwas-via-provisioning-package)

Os usuários também podem instalar PWAs para uso durante a sessão do Hub. Quando a sessão termina, os PWAs são removidos. Para saber mais, confira [Instalar, gerenciar ou desinstalar aplicativos no Microsoft Edge](https://support.microsoft.com/topic/install-manage-or-uninstall-apps-in-microsoft-edge-0c156575-a94a-45e4-a54f-3a84846f6113)

## <a name="install-pwas-via-intune"></a>Instalar PWAs por meio Intune

Use Intune ou outro provedor de MDM para instalar PWAs em Surface Hubs. Para saber mais, consulte [Gerenciar configurações com um provedor de MDM](manage-settings-with-mdm-for-surface-hub.md).

### <a name="get-started"></a>Introdução

1. Entre no portal do Intune no [**Microsoft Endpoint Manager de administração**](https://endpoint.microsoft.com/).
2. Acesse o **perfil** **DevicesConfiguration** >  **PoliciesCreate****** > . 
3. Em Plataforma, selecione **Windows 10 e posterior**. Em Tipo de perfil, selecione **Modelos**. Em Nome do modelo, selecione **Modelos Administrativos.**
4. Selecione **Criar.**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Criar um Intune de configuração" :::

5. Nomeie o perfil, insira uma descrição opcional e selecione **Avançar**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Perfil de nome" :::

### <a name="configure-force-installed-web-apps-policy-intune"></a>Configurar a política de Aplicativos Web (Intune)

1. Selecione **Microsoft Edge Configuração** e, na caixa Pesquisa, insira instalado à **força, selecione** Aplicativos Web **e, em** seguida, **selecione Habilitado**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Configurar a instalação forçada Aplicativos Web" :::

2. Em **URLs Aplicativos Web** ser instaladas silenciosamente, crie um snippet XML da sintaxe a seguir ou copie do [exemplo](#example-pwas) abaixo. 

    ```
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  }, ]
    ```
    
#### <a name="example-pwas"></a>PWAs de exemplo

Este exemplo instala PWAs para YoutTube, Webex, Zoom e Uber.

```
    [
{ "url": "https://www.youtube.com/",       "default_launch_container": "window" },
{ "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
{ "url": "https://zoom.us/join",           "default_launch_container": "window" },
{ "url": "https://www.uber.com/",          "default_launch_container": "tab"}
]
```

3. Insira o snippet de código que contém URLs para os aplicativos que você deseja instalar.
4. Insira marcas de escopo opcionais conforme apropriado e selecione **Avançar.**
5. Atribua aos usuários conforme apropriado.
6. Atribua a um grupo que contém os Surface Hubs que você deseja direcionar. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](/mem/intune/fundamentals/groups-add)
7. Examine e selecione **Criar**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Criar perfil" :::
    

8. Sincronize os dispositivos de destino conforme apropriado.
9. No Surface Hub, inicie o Edge. Os PWAs são instalados e aparecem na lista menu Iniciar todos os aplicativos.

## <a name="install-pwas-via-provisioning-package"></a>Instalar PWAs por meio do pacote de provisionamento

Você pode instalar PWAs aplicando um pacote de provisionamento aos Surface Hubs usando uma unidade USB. Para saber mais, confira [Criar pacotes de provisionamento](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### <a name="get-started-with-provisioning"></a>Introdução com provisionamento

1. Em um computador separado executando Windows 10 ou Windows 11, instale [Windows WCD (Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) de Configuração) do Microsoft Store.
2. No WCD, crie um novo Project. Selecione **Provisionar Dispositivos de Área de Trabalho,** forneça um nome para o projeto e escolha **Concluir.**
3. Selecione **Alternar para o editor avançado** e selecione **Sim** para confirmar.

### <a name="configure-msedgepolicy"></a>Configurar MSEdgePolicy

1. No painel Personalizações disponíveis no WCD, vá para **\Runtime Configurações\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**
2. No painel de edição de personalizações, insira o nome do aplicativo como **MSEdgePolicy** e selecione **Adicionar**.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="Insira o nome do aplicativo como MSEdgePolicy" :::

3. No painel Personalizações Disponíveis, selecione **AppName: MSEdgePolicy** e, no painel de edição, altere **SettingType** para **Política** e escolha **Adicionar**.
4. No painel Personalizações Disponíveis, selecione **SettingType: Policy** e, no painel de edição, defina **AdmxFileUid** como **MSEdgePolicy** e escolha **Adicionar**.
5. No painel Personalizações disponíveis, selecione **AdmxFileUid: MSEdgePolicy** e, no painel de edição, defina **MSEdgePolicy** inserindo o seguinte código como uma única linha de texto:

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="Inserir código para MSEdgePolicy" :::   
   
    ```
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```
 
### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>Configurar a política de Aplicativos Web forçada (pacote de provisionamento)

1. No painel Personalizações disponíveis no WCD, vá para: **\Runtime Configurações\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**
2. No painel de edição de personalizações, insira o Nome da área como **MSEdgePolicy~Policy~microsoft_edge,** selecione **Adicionar**.
3. No painel Personalizações Disponíveis, selecione **AreaName: MSEdgePolicy~Policy~microsoft_edge** e, no painel de edição, defina o Nome da Política como **WebAppInstallForceList** e selecione **Adicionar.******
4. No painel Personalizações Disponíveis, selecione **PolicyName: WebAppInstallForceList** e, no painel de edição para **WebAppInstallForceList** , insira o código a seguir como uma única linha de texto.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="Insira o código para a política de Aplicativos Web forçada" :::   

 > [!TIP]
 > Este exemplo instala o You Tube como um PWA. Substitua a URL conforme apropriado. 

```
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
```    

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>Exportar pacote de provisionamento e aplicar aos Surface Hubs

1. Na barra de menus, selecione **Exportar**, selecione **Pacote de Provisionamento** e siga os prompts para gerar o arquivo .ppkg.
2. Insira uma unidade flash USB vazia. Selecione o local de saída para ir para o local do pacote. Copie o arquivo .ppkg para a unidade USB.
3. Aplique o pacote de provisionamento por meio Configurações aplicativo ou durante a configuração da primeira execução. Para saber mais, confira [Criar pacotes de provisionamento](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

## <a name="learn-more"></a>Saiba mais

- [Referência de WCD: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [Visão geral dos Aplicativos Web Progressivos (PWAs)](/microsoft-edge/progressive-web-apps-chromium/)
