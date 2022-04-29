---
title: Criar pacotes de provisionamento
description: Para Windows 10 ou Windows 11, as configurações que usam o registro ou um provedor de serviços de configuração (CSP) podem ser configuradas usando pacotes de provisionamento.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: adicionar certificado, pacote de provisionamento
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/20/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 1f1e084b8be0ab44c853fe003236ba7f25b4ff4c
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497634"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>Criar os pacotes de provisionamento para Surface Hub

Os pacotes de provisionamento permitem automatizar a implantação de recursos principais, ajudando a fornecer uma experiência consistente em todos os Surface Hubs em sua organização.  Usando Windows WCD (Designer de Configuração) em um computador separado, você pode concluir as seguintes tarefas:

- Registrar-se no Active Directory ou Azure Active Directory
- Criar uma conta de administrador de dispositivo
- Adicionar aplicativos e certificados
- Configurar as definições do proxy
- Adicionar um arquivo de configuração do Surface Hub
- Definir [configurações do CSP (Provedor de Serviços de Configuração)](/windows/client-management/mdm/surfacehub-csp)

## <a name="overview"></a>Visão Geral

1. Em um computador separado executando Windows 10 ou Windows 11, instale [Windows Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) de Configuração do Microsoft Store.
1. Selecione [**Provisionar Surface Hub para**](#use-surface-hub-provisioning-wizard) definir configurações comuns usando um assistente. Ou selecione [Provisionamento avançado para](#use-advanced-provisioning) exibir e definir todas as configurações possíveis.
1. Crie o pacote de provisionamento e salve-o em uma unidade USB.
1. Implante o pacote em seu Surface Hub durante a instalação da primeira execução ou por meio do Configurações aplicativo. Para saber mais, confira [Criar um pacote de provisionamento](/windows/configuration/provisioning-packages/provisioning-create-package).

## <a name="use-surface-hub-provisioning-wizard"></a>Usar Surface Hub de provisionamento

1. Abra Windows Designer de Configuração e selecione **Provisionar Surface Hub dispositivos**.<br>
    ![Use o assistente Surface Hub de provisionamento.](images/sh-prov-start.png)
    
2. Nomeie seu projeto e selecione **Avançar**.

### <a name="add-certificates"></a>Adicionar certificados

> [!div class="mx-imgBorder"]
> ![adicionar um certificado.](images/sh-prov-cert.png)

Para provisionar o dispositivo com um certificado, selecione **Adicionar um certificado**. Insira um nome para o certificado e, em seguida, navegue para selecionar o certificado a ser usado.  Para obter opções avançadas de provisionamento, consulte a seção abaixo [Adicionar um certificado ao pacote](#add-a-certificate-to-your-package).

### <a name="configure-proxy-settings"></a>Configurar as definições do proxy

> [!div class="mx-imgBorder"]
> ![defina as configurações de proxy.](images/sh-prov-proxy.png)

1. Alterne entre **Sim** ou **Não** para as configurações de proxy. Por padrão, Surface Hub detecta automaticamente as configurações de proxy. No entanto, se anteriormente sua infraestrutura precisava usar um servidor proxy e houve alteração para não exigir um servidor proxy, você pode usar um pacote de provisionamento para reverter seus dispositivos Surface Hub para as configurações padrão, selecionando **Sim** e **Detectar configurações automaticamente**.
2. Se você alternar **Sim**, poderá selecionar para detectar automaticamente as configurações de proxy ou definir manualmente as configurações inserindo uma das seguintes opções:

    - Uma URL para um script de instalação.
    - Um endereço do servidor proxy estático e informações de porta.

3. Se você pretende usar um script de instalação ou um servidor proxy, desative automaticamente **as configurações de detecção**. Você pode usar um script de instalação *ou um* servidor proxy, não ambos.
4. Insira exceções (endereços aos Surface Hub devem se conectar diretamente sem usar o servidor proxy). **Exemplo:** *.office365.com
5. Identifique se o servidor proxy deve ser usado para endereços locais.

### <a name="set-up-device-admins"></a>Configurar administradores de dispositivos

 > [!div class="mx-imgBorder"]
 > ![Ingresse no Active Directory, Azure AD ou crie uma conta de administrador local.](images/sh2-wcd.png)

Você pode registrar o dispositivo no Active Directory e especificar um grupo de segurança para usar o aplicativo Configurações, se inscrever no Azure Active Directory para permitir que os administradores globais usem o aplicativo Configurações ou criar uma conta de administrador local no dispositivo.

1. Para registrar o dispositivo no Active Directory, insira as credenciais de uma conta de usuário de privilégios mínimos para ingressar o dispositivo no domínio e especificar que o grupo de segurança tenha credenciais de administrador no Surface Hub. Se aplicar o pacote a um Surface Hub que foi redefinido, você poderá usar a mesma conta de domínio, desde que seja a mesma conta que configurou o Surface Hub inicialmente. Caso contrário, uma conta de domínio diferente deve ser usada no pacote de provisionamento.
2. Antes de usar Windows Designer de Configuração para configurar o registro em Azure AD em massa, [planeje sua implementação Azure AD junção.](/azure/active-directory/devices/azureadjoin-plan) A configuração **número máximo de dispositivos por usuário** em seu locatário do Azure AD determina quantas vezes o token em massa que você obtém do assistente pode ser usado.
3. Para registrar o dispositivo no Azure AD, selecione essa opção e insira um nome amigável para o token em massa que você obterá usando o assistente. Defina uma data de expiração do token (máximo de 30 dias a partir da data de obtenção do token). Selecione **Obter token em massa**. Na janela **Vamos conectá-lo**, insira uma conta que tenha permissões para ingressar um dispositivo ao Azure AD e, em seguida, a senha. Selecione **Aceitar** para dar a Windows Designer de Configuração as permissões necessárias.
4. Para criar uma conta de administrador local, selecione essa opção e insira um nome de usuário e senha.

> [!IMPORTANT]
> Se criar uma conta local no pacote de provisionamento, você deverá alterar a senha usando o aplicativo **Configurações** a cada 42 dias. Se a senha não for alterada durante esse período, a conta poderá estar bloqueada e não será possível entrar.

### <a name="enroll-in-third-party-mdm-provider"></a>Registrar-se no provedor de MDM de terceiros

> [!div class="mx-imgBorder"]
> ![Registre-se no gerenciamento de dispositivo móvel de terceiros.](images/sh-prov-mdm.png)

Se você usar um provedor de MDM (gerenciamento de dispositivo móvel) de terceiros, poderá usar esta seção para registrar Surface Hub. Para se registrar no Intune, primeiro configure o ingresso no Azure AD, conforme descrito na seção anterior, e siga as instruções na seguinte documentação do Intune: Início Rápido: Configurar o registro automático para dispositivos [Windows 10/11](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

1. Alterne **Sim** ou **Não** para registro no MDM de terceiros.
2. Se você alternar **Sim**, forneça uma conta de serviço e senha ou impressão digital de certificado que esteja autorizada a registrar o dispositivo e especificar o tipo de autenticação.
3. Se exigido pelo provedor de MDM, insira as URLs para o serviço de descoberta, o serviço de registro e o serviço de política.

 Para saber mais, confira [Gerenciar Surface Hub com um provedor de MDM.](manage-settings-with-mdm-for-surface-hub.md)

### <a name="add-applications"></a>Adicionar aplicativos

> [!div class="mx-imgBorder"]
> ![adicionar um aplicativo.](images/sh-prov-apps.png)

Você pode instalar vários aplicativos da Plataforma Universal do Windows (UWP) em um pacote de provisionamento. Para saber mais, confira [Provisionar computadores com aplicativos](/windows/configuration/provisioning-packages/provision-pcs-with-apps).

> [!NOTE]
> Embora Windows Designer de Configuração permita adicionar um aplicativo Win32 clássico a um pacote de provisionamento, o Surface Hub aceita apenas aplicativos UWP. Se você incluir um aplicativo Win32 clássico, o provisionamento falhará.

### <a name="add-a-configuration-file"></a>Adicionar um arquivo de configuração

Além desse pacote de provisionamento, você pode usar um arquivo Surface Hub configuração para facilitar ainda mais a configuração de seus dispositivos. Um Surface Hub de configuração do Surface Hub contém uma lista de contas de dispositivo para conexão com Exchange, Microsoft Teams ou Skype for Business, bem como "nomes amigáveis" para projeção sem fio.

**Para criar um arquivo Surface Hub configuração:**

1. Abra Microsoft Excel (ou outro editor de .csv), crie um arquivo .csv chamado _SurfaceHubConfiguration.csv_.

2. Insira uma lista de contas de dispositivo e nomes amigáveis neste formato:

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > O arquivo de configuração não deve conter cabeçalhos de coluna. Quando incluído em um pacote de provisionamento aplicado ao Surface Hub, você pode selecionar a conta e o nome amigável do dispositivo no arquivo. Para criar o arquivo .csv, use um formato de endereço UPN (rainier@contoso.com) ou um formato de nome de logon de nível inferior (contoso\rainier).

    rainier@contoso.com,password,Rainier Surface Hub

3. Salve o arquivo na pasta do projeto e copie-o para a chave USB com o pacote de provisionamento.

> [!NOTE]
> O arquivo de configuração só pode ser aplicado durante a configuração da primeira execução.

### <a name="password-protect-provisioning-package"></a>Pacote de provisionamento de proteção de senha

Se você optar por usar uma senha, precisará inseri-la sempre que aplicar o pacote de provisionamento a um dispositivo.

### <a name="complete-provisioning-wizard"></a>Assistente de provisionamento completo

Se você só precisar definir configurações comuns, selecione **FinishCreate** **** >  e pule para a seção [Compilar seu pacote](#build-your-package). Ou continue definindo as configurações alternando para provisionamento avançado.

## <a name="use-advanced-provisioning"></a>Usar provisionamento avançado

> [!TIP]
> Use o assistente para criar um pacote com as configurações comuns e alterne para o editor avançado a fim de adicionar outras configurações.<br><br> ![Alterne para o editor avançado.](images/icd-simple-edit.png)

1. Se continuar na seção anterior, selecione **Alternar para o editor avançado**; caso contrário, abra **Windows Designer** de Configuração e selecione **Provisionamento avançado**.

   ![Use o provisionamento avançado.](images/sh-prov-adv.png)

2. Nomeie seu projeto e selecione **Avançar**.

3. Selecione **Comum para Windows 10 Team**, selecione **Avançar** e, em seguida, selecione **Concluir**.

   ![Novo projeto WCD.](images/icd-new-project.png)

4. No projeto, em **Personalizações disponíveis**, selecione **Configurações da Equipe Comum**.

   :::image type="content" alt-text="Configurações comuns do WCD." source="images/icd-common-settings.png":::

### <a name="add-a-certificate-to-your-package"></a>Adicionar um certificado ao pacote

É possível usar pacotes de provisionamento para instalar certificados que permitirão a autenticação do dispositivo no Microsoft Exchange.

> [!NOTE]
> Os pacotes de provisionamento só podem instalar certificados no repositório do dispositivo (computador local), não no repositório do usuário. Se sua organização exigir que os certificados sejam instalados no repositório de usuários, use o aplicativo Hub **Configurações**: Atualizar & **SecurityCertificatesImport** > **** > .****
Como alternativa, você pode usar políticas  [**de MDM**](manage-settings-with-mdm-for-surface-hub.md) para implantar certificados no repositório de dispositivos ou no repositório de usuários.

> [!TIP]
> A **seção ClientCertificates** é para arquivos .pfx com uma chave privada; os arquivos .cer para ACs raiz devem ser colocados na seção **RootCertificates** e para CAs intermediárias na seção **CACertificates** .

1. Em **Windows personalizações disponíveis do Designer** >  **de** Configuração, vá para **Configurações de RuntimeCertificatesClientCertificates** > **** > .****
2. Insira um rótulo para **CertificateName** e selecione **Adicionar**.
3. Insira a **CertificatePassword**.
4. Para **CertificatePath**, procure e selecione o certificado.
5. Defina **ExportCertificate** como **False**.
6. Para **KeyLocation**, selecione **Software only**.

### <a name="add-a-uwp-app-to-your-package"></a>Adicionar um aplicativo UWP ao pacote

Para adicionar um aplicativo UWP a um pacote de provisionamento, você precisará do pacote do aplicativo (arquivos .appx ou .appxbundle) e de quaisquer arquivos de dependência. Se você adquiriu o aplicativo na Microsoft Store para Empresas, também precisará da licença de aplicativo *não codificada*. Consulte [Distribuir aplicativos offline](/microsoft-store/distribute-offline-apps) para saber como baixar esses itens na Microsoft Store para Empresas.

**Para adicionar um aplicativo UWP:**

1. No painel **Personalizações disponíveis**, vá até **Configurações de tempo de execução** > **UniversalAppInstall** > **DeviceContextApp**.

2. Insira um **PackageFamilyName para** o aplicativo e selecione **Adicionar**. Para manter a consistência, use o nome da família de pacotes do aplicativo. Se você adquiriu o aplicativo na Microsoft Store para Empresas, poderá encontrar o nome da família de pacotes na licença do aplicativo. Abra o arquivo de licença usando um editor de texto e use o valor entre as marcas PFM.

3. Para **ApplicationFile**, selecione **Procurar** para localizar e selecionar o aplicativo de destino ( .appx ou .appxbundle).

4. Para **DependencyAppxFiles**, selecione **Procurar** para localizar e adicionar quaisquer dependências para o aplicativo. Para o Surface Hub, você só precisará das versões x64 dessas dependências.

Se você adquiriu o aplicativo do Microsoft Store para Empresas, precisará adicionar a licença do aplicativo ao pacote de provisionamento.

**Para adicionar a licença do aplicativo:**

1. Crie uma cópia da licença do aplicativo e renomeie-a para usar uma extensão **.ms-windows-store-license**. Por exemplo, renomeie "example.xml" para "example.ms-windows-store-license".

2. No Windows Designer de Configuração, acesse **As configurações personalizações** >  disponíveisRuntimeUniversalAppInstallDeviceContextAppLicense**** > **** > .****

3. Insira um **LicenseProductId** e selecione **Adicionar**. Para manter a consistência, use a ID da licença do aplicativo. Abra o arquivo de licença usando um editor de texto. Em seguida, na **marca Licença** , use o valor no atributo **LicenseID** .

4. Selecione o novo nó **LicenseProductId**. Para **LicenseInstall**, selecione **Procurar** para localizar e selecionar o arquivo de licença renomeado (example.ms-windows-store-license).

### <a name="add-a-policy-to-your-package"></a>Adicionar uma política ao pacote

O Surface Hub oferece suporte a um subconjunto das políticas do [Provedor de serviços de configuração de políticas](/windows/client-management/mdm/policy-configuration-service-provider). Algumas dessas políticas podem ser configuradas com o designer Windows configuração.

 **Para adicionar [políticas do CSP](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub):**

1. Acesse **Available customizationsRuntime** >  **settingsPolicies****** > .
2. Selecione o componente que você deseja gerenciar e defina a configuração de política conforme apropriado. Por exemplo, para impedir que os funcionários usem a navegação inPrivate no site Surface Hub, selecione **AllowInPrivate** e, em seguida, **selecione Desabilitar**.  

   :::image type="content" alt-text="Defina a configuração de política." source="images/sh-prov-policies.png" lightbox="images/sh-prov-policies.png":::

### <a name="add-surface-hub-settings-to-your-package"></a>Adicionar configurações do Surface Hub ao seu pacote

Você pode adicionar configurações do [Provedor de serviços de configuração SurfaceHub](/windows/client-management/mdm/surfacehub-csp) ao seu pacote de provisionamento.

1. Vá para **Personalizações DisponíveisCommon** >  **Team Edition Configurações**.
1. Selecione o componente que você deseja gerenciar e defina a configuração de política conforme apropriado.
1. Quando terminar de configurar o pacote de provisionamento, selecione **FileSave****** > .
1. Leia o aviso de que os arquivos de projeto podem conter informações confidenciais e selecione **OK**

### <a name="build-your-package"></a>Compilar o pacote

Ao compilar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados.  Armazene os arquivos de projeto em um local seguro ou exclua se não for mais necessário.

1. Abra **Windows designer** **de configuraçãoExportProvisioning** >  > .****

2. **Altere Proprietário** para **Administrador de TI**.  

3. Defina um valor para **Versão do Pacote** e selecione **Avançar**.

   > [!TIP]
   > Definir o proprietário como Administrador de TI garante que as configurações do pacote mantenham as "propriedades de precedência" apropriadas e permaneçam em vigor no Surface Hub se outros pacotes de provisionamento forem aplicados subsequentemente de outras fontes.

   > [!TIP]
   > Você pode modificar os pacotes existentes e alterar o número de versão para atualizar os pacotes aplicados anteriormente.

4. Opcional: você pode optar por criptografar o pacote e habilitar a assinatura de pacote:

    1. Selecione **Criptografar** pacote e insira uma senha.
    1. Selecione **Assinar** **packageBrowse** >  e escolha o certificado conforme apropriado.

    > [!IMPORTANT]
    > É recomendável incluir um certificado de provisionamento confiável em seu pacote de provisionamento. Quando o pacote é aplicado a um dispositivo, o certificado é adicionado ao repositório do sistema, permitindo que os pacotes subsequentes sejam aplicados silenciosamente.

5. Selecione **Avançar** para especificar o local de saída. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída. Ou selecione **Procurar** para alterar o local de saída padrão. Selecione **Avançar**.

6. Selecione **Compilar** para começar a compilar o pacote. As informações do projeto são exibidas na página de build.

7. Se o build falhar, uma mensagem de erro será exibida com um link para a pasta do projeto. Examine os logs para diagnosticar o erro e tente compilar o pacote novamente.

8. Se o build for bem-sucedido, o nome do pacote de provisionamento, o diretório de saída e o diretório do projeto serão exibidos. Selecione **Concluir** para fechar o assistente e voltar para a página Personalizações.

9. Selecione  **o local**  de saída para ir para o local do pacote. Copie o .ppkg em uma unidade flash USB vazia.

## <a name="apply-a-provisioning-package-to-surface-hub"></a>Aplicar um pacote de provisionamento ao Surface Hub

Há duas maneiras de implantar pacotes de provisionamento em um Surface Hub:

- [Configuração da primeira execução.](#apply-a-provisioning-package-during-first-run) Você pode aplicar um pacote de provisionamento para personalizar várias opções, incluindo configurações de Wi-Fi, configurações de proxy, detalhes da conta do dispositivo, Azure AD junção e configurações relacionadas.  
- [Configurações aplicativo.](#apply-a-provisioning-package-using-settings-app) Após a primeira instalação da execução, você pode aplicar um pacote de provisionamento por meio do Configurações aplicativo. 

### <a name="apply-a-provisioning-package-during-first-run"></a>Aplicar um pacote de provisionamento durante a primeira execução

1. Quando você ativa o Surface Hub pela primeira vez, o programa de primeira execução exibe a página [**Olá, lá**](first-run-program-surface-hub.md). Verifique se as configurações estão definidas corretamente antes de continuar.

2. Insira a unidade flash USB que contém o arquivo .ppkg no Surface Hub. Se o pacote estiver no diretório raiz da unidade, o programa de primeira execução o reconhecerá e perguntará se você deseja configurar o dispositivo. Selecione **Configurar**.

3. A próxima tela solicita que você selecione uma origem de provisionamento. Selecione **Mídia Removível** e toque em **Avançar**.

4. Selecione o pacote de provisionamento (*.ppkg) que você deseja aplicar e toque em **Avançar**. Observe que só é possível instalar um pacote durante a primeira execução.

5. O programa de primeira execução mostrará um resumo das alterações que o pacote de provisionamento aplicará. Selecione **Sim, adicionar**.

6. Se um arquivo de configuração estiver incluído no diretório raiz da unidade USB, você verá **Selecionar uma configuração**. A primeira conta de dispositivo no arquivo de configuração será exibida com um resumo das informações da conta que serão aplicadas ao Surface Hub.

7. Em **Selecionar uma configuração**, selecione o nome do dispositivo a ser aplicado e, em seguida, **selecione Avançar**.

As configurações do pacote de provisionamento serão aplicadas ao dispositivo e o OOBE será concluído. Depois que o dispositivo for reiniciado, você pode remover a unidade USB.

### <a name="apply-a-provisioning-package-using-settings-app"></a>Aplicar um pacote de provisionamento usando Configurações aplicativo

1. Insira a unidade flash USB que contém o arquivo .ppkg no Surface Hub.
2. Na Surface Hub, comece **Configurações** e insira as credenciais de administrador quando solicitado.
3. Navegue até **Surface Hub** > **Gerenciamento de dispositivo**. Em **Pacotes de provisionamento**, **selecione Adicionar ou remover um pacote de** >  **provisionamentoAdd um pacote**.
4. Escolha seu pacote de provisionamento e selecione **Adicionar**.  Se solicitado, insira suas credenciais de administrador novamente.
5. Você verá um resumo das alterações a serem aplicadas. Selecione **Sim, adicionar**.

## <a name="learn-more"></a>Saiba mais

- [Baixar Windows Designer de Configuração](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [Criar um pacote de provisionamento](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Gerenciar o Surface Hub com um provedor MDM](manage-settings-with-mdm-for-surface-hub.md)
