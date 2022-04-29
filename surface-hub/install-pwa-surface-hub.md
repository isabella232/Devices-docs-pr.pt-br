---
title: Instalar Apps Web Progressivos no Surface Hub
description: Explica como os administradores podem instalar PWAs (Aplicativos Web progressivos) no Surface Hub por meio Intune ou um pacote de provisionamento.
keywords: Surface Hub, PWAs, Aplicativo
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/27/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 687dd85d3490d420133edc5b7de3b2af0c0433ef
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497524"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>Instalar Apps Web Progressivos no Surface Hub

O suporte a aplicativo Web progressivo (PWA) abre uma nova fonte avançada de aplicativos que estende significativamente a biblioteca de aplicativos disponíveis que podem ser executados no Suface Hub.  Os usuários podem acessar uma grande quantidade de aplicativos fora do Microsoft Store e execute-os diretamente no menu Aplicativo.  Em comparação com páginas da Web, os PWAs se comportam mais como aplicativos nativos com funcionalidade offline, a capacidade de atualizar em segundo plano e outros recursos exclusivos. A maioria dos sites pode ser instalada como PWAs e aproveitar qualquer função adicional habilitada por desenvolvedores da Web.

Os administradores podem instalar remotamente PWAs em Surface Hubs por meio de provedores de MDM (gerenciamento de dispositivo móvel), como Microsoft Intune. Ou você pode usar um pacote de provisionamento. Este artigo descreve os dois métodos com código de exemplo para instalar o YouTube, WebEx, Zoom e Uber e instruções para instalar seus próprios PWAs. Para saber mais, confira [Visão geral dos Aplicativos Web](/microsoft-edge/progressive-web-apps-chromium/).

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

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Criar um Intune de configuração" lightbox="images/pwa-hubpwainstall.png":::

5. Nomeie o perfil, insira uma descrição opcional e selecione **Avançar**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Perfil de nome" lightbox="images/pwa-hubwebappscreateprofile.png":::

### <a name="configure-force-installed-web-apps-policy-intune"></a>Configurar a política de Aplicativos Web (Intune)

1. Em Todas **Configurações** >  **Consulta** de Compilação, selecione **Microsoft Edge** e, na caixa De pesquisa, insira **force-installed**, selecione **force-installed Aplicativos Web** e, em seguida, selecione **Habilitado.**

    :::image type="content" source="images/pwa-enable-force-install.png" alt-text="Habilitar aplicativos Web instalados à força" lightbox="images/pwa-enable-force-install.png":::

2. Em **URLs** Aplicativos Web ser instaladas silenciosamente, copie e insira o snippet de código a seguir para instalar PWAs para YouTube, Webex, Zoom e Uber. Ou pule para a próxima etapa para instalar outros PWAs.

    :::image type="content" source="images/hub-pwa-install-enable.png" alt-text="Insira a lista de aplicativos Web instalados à força" lightbox="images/hub-pwa-install-enable.png":::

    ```json
    [
    { "url": "https://www.youtube.com/",       "default_launch_container": "window" },
    { "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
    { "url": "https://zoom.us/join",           "default_launch_container": "window" },
    { "url": "https://www.uber.com/",          "default_launch_container": "tab"}
    ]
    ```

3. Como alternativa, você pode criar um snippet JSON com base na sintaxe a seguir para instalar outros PWAs.

    ```json
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  } ]
    ```

4. Na página Marcas de escopo, selecione **Avançar** para ignorar.

5. Na página Atribuições, em Grupos **incluídos**, selecione **Adicionar grupos**.

    :::image type="content" source="images/pwa-add-groups.png" alt-text="Adicionar grupos" lightbox="images/pwa-add-groups.png" :::

6. Em **Selecionar grupos a serem incluídos**, insira o nome de um grupo que contém os Surface Hubs que você deseja direcionar, escolha Selecionar **e clique em** **Avançar**. Para saber mais sobre como atribuir um perfil de configuração a um grupo, consulte [Adicionar grupos para organizar usuários e dispositivos](/mem/intune/fundamentals/groups-add).

    :::image type="content" source="images/pwa-select-groups.png" alt-text="Selecionar grupos" lightbox="images/pwa-select-groups.png":::

7. Examine e selecione **Criar**.

    :::image type="content" source="images/pwa-create-profile.png" alt-text="Criar perfil" lightbox="images/pwa-create-profile.png" :::

8. Para aplicar o perfil de configuração de forma immediate, selecione **Dispositivos** >  **Todos** os dispositivos e localize o dispositivo direcionado. Abra o painel Visão geral e selecione **Sincronizar**.

    :::image type="content" source="images/pwa-sync-tenant.png" alt-text="Locatário de sincronização" lightbox="images/pwa-select-groups.png":::

 > [!IMPORTANT]
 > Para concluir a instalação de PWAs, vá para o Surface Hub e inicie o Edge. Os PWAs são instalados e aparecem na lista menu Iniciar todos os aplicativos.

 ### <a name="troubleshooting-intune-managed-pwas"></a>Solução de Intune PWAs gerenciados
 
Se você não vir PWAs listados em **Todos os aplicativos:**

- Verifique se o Surface Hub tem as atualizações mais recentes, especificamente [KB5011543](https://support.microsoft.com/help/5011543) (ou uma atualização Windows atualização posterior). Para saber mais sobre as atualizações Windows 10 Team mais recentes, consulte [Surface Hub histórico de atualizações](surface-hub-update-history.md).
- Verifique se o perfil de configuração foi aplicado com êxito e não tem conflitos com outras configurações. 
- Verifique se o perfil de configuração é direcionado a um grupo de segurança que contém sua Surface Hub. 
- Lembre-se de iniciar o Edge uma única vez no Surface Hub, o que é necessário para que Intune PWAs gerenciados com êxito.

## <a name="install-pwas-via-provisioning-package"></a>Instalar PWAs por meio do pacote de provisionamento

Você pode instalar PWAs aplicando um pacote de provisionamento aos Surface Hubs usando uma unidade USB. Para saber mais, confira [Criar pacotes de provisionamento](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### <a name="get-started-with-provisioning"></a>Introdução com provisionamento

1. Em um computador separado executando Windows 10 ou Windows 11, instale [Windows WCD (Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) de Configuração) do Microsoft Store.

2. No WCD, crie um novo Project. Selecione **Provisionar Dispositivos de Área de Trabalho,** forneça um nome para o projeto e escolha **Concluir.**

3. Selecione **Alternar para o editor avançado** e selecione **Sim** para confirmar.

### <a name="configure-msedgepolicy"></a>Configurar MSEdgePolicy

1. No painel Personalizações disponíveis no WCD, vá para **\Runtime Configurações\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**

2. No painel de edição de personalizações, insira o nome do aplicativo como **MSEdgePolicy** e selecione **Adicionar**.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="Insira o nome do aplicativo como MSEdgePolicy" lightbox="images/pwa-add-edge-policy.png" :::

3. No painel Personalizações Disponíveis, selecione **AppName: MSEdgePolicy** e, no painel de edição, altere **SettingType** para **Política** e escolha **Adicionar**.

4. No painel Personalizações Disponíveis, selecione **SettingType: Policy** e, no painel de edição, defina **AdmxFileUid** como **MSEdgePolicy** e escolha **Adicionar**.

5. No painel Personalizações disponíveis, selecione **AdmxFileUid: MSEdgePolicy** e, no painel de edição, defina **MSEdgePolicy** inserindo o seguinte código como uma única linha de texto:

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="Inserir código para MSEdgePolicy" lightbox="images/pwa-enter-edge-policy.png" :::

    ```xml
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```

### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>Configurar a política de Aplicativos Web forçada (pacote de provisionamento)

1. No painel Personalizações disponíveis no WCD, vá para: **\Runtime Configurações\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**

2. No painel de edição de personalizações, insira o Nome da área como **MSEdgePolicy~Policy~microsoft_edge,** selecione **Adicionar**.

3. No painel Personalizações Disponíveis, selecione **AreaName: MSEdgePolicy~Policy~microsoft_edge** e, no painel de edição, defina o Nome da Política como **WebAppInstallForceList** e selecione **Adicionar.******

4. No painel [Personalizações](#ppkg-code-samples) disponíveis, selecione **PolicyName: WebAppInstallForceList** e, no painel de edição para **WebAppInstallForceList**, insira PWA código como uma única linha de texto.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="Insira o código para a política de Aplicativos Web forçada" lightbox="images/pwa-force-web-app-install.png":::

### <a name="ppkg-code-samples"></a>Exemplos de código PPKG

- YouTube PWA:

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- Vários PWAs, incluindo YouTube, Webex, Zoom e Uber:

    ```xml
     <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.signin.webex.com/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://zoom.us/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.uber.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- Como alternativa, você pode criar um snippet JSON com base na sintaxe a seguir para instalar outros PWAs:

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.contoso.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>Exportar pacote de provisionamento e aplicar aos Surface Hubs

1. Na barra de menus, selecione **Exportar**, selecione **Pacote de Provisionamento** e siga os prompts para gerar o arquivo .ppkg.

2. Insira uma unidade flash USB vazia. Selecione o local de saída para ir para o local do pacote. Copie o arquivo .ppkg para a unidade USB.

3. Aplique o pacote de provisionamento por meio Configurações aplicativo ou durante a configuração da primeira execução. Para saber mais, confira [Criar pacotes de provisionamento](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

 ### <a name="troubleshooting-provisioning-package-pwas"></a>Solução de problemas de PWAs de pacote de provisionamento
 
Se você não vir PWAs listados em **Todos os aplicativos**:

- Verifique se o Surface Hub tem as atualizações mais recentes, especificamente [KB5011543](https://support.microsoft.com/help/5011543) (ou uma atualização Windows atualização posterior). Para saber mais sobre as atualizações Windows 10 Team mais recentes, consulte [Surface Hub histórico de atualizações](surface-hub-update-history.md).

## <a name="learn-more"></a>Saiba mais

- [Referência de WCD: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [Visão geral dos Aplicativos Web Progressivos (PWAs)](/microsoft-edge/progressive-web-apps-chromium/)
