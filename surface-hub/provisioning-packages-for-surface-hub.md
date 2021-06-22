---
title: Criar pacotes de provisionamento
description: No Windows 10, os ajustes que usam o Registro ou um provedor de serviços de configuração (CSP) podem ser definidos por pacotes de provisionamento.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: adicionar certificado, pacote de provisionamento
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/28/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 087826a7a0cba7a47accc0d3d66714289f2ae9d2
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613930"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>Criar pacotes de provisionamento para Surface Hub

Os pacotes de provisionamento permitem automatizar a implantação de recursos principais, ajudando a oferecer uma experiência consistente em todos os Surface Hubs em sua organização.  Usando Windows Designer de Configuração (WCD) em um computador separado, você pode concluir as seguintes tarefas:

- Inscreva-se no Active Directory ou Azure Active Directory
- Criar uma conta de administrador de dispositivo
- Adicionar aplicativos e certificados
- Configurar as definições do proxy
- Adicionar um arquivo de configuração do Surface Hub
- Configurar [configurações do Provedor de Serviços de Configuração (CSP)](/windows/client-management/mdm/surfacehub-csp)

## <a name="overview"></a>Visão geral

1. Em um computador separado executando Windows 10, [instale Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) do Microsoft Store.
1. Selecione [**Provisionar Surface Hub dispositivos**](#use-surface-hub-provisioning-wizard) para configurar configurações comuns usando um assistente. Ou selecione [Provisionamento avançado](#use-advanced-provisioning) para exibir e configurar todas as configurações possíveis.
1. Crie o pacote de provisionamento e salve-o em uma unidade USB.
1. Implante o pacote no seu Surface Hub durante a instalação da primeira ou por meio do Configurações aplicativo. Para saber mais, confira [Criar um pacote de provisionamento para Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package).

## <a name="use-surface-hub-provisioning-wizard"></a>Usar Surface Hub de provisionamento

1. Abra Windows Designer de Configuração e selecione **Provision Surface Hub dispositivos**.<br>
    ![Use o assistente de provisionamento do Surface Hub](images/sh-prov-start.png)
    
2. Nomeia seu projeto e selecione **Próximo**.

### <a name="add-certificates"></a>Adicionar certificados

> [!div class="mx-imgBorder"]
> ![adicionar um certificado](images/sh-prov-cert.png)

Para provisionar o dispositivo com um certificado, selecione **Adicionar um certificado**. Insira um nome para o certificado e procure para selecionar o certificado a ser usado.  Para opções de provisionamento avançadas, consulte a seção abaixo [Adicionar um certificado ao pacote](#add-a-certificate-to-your-package).

### <a name="configure-proxy-settings"></a>Configurar as definições do proxy

> [!div class="mx-imgBorder"]
> ![configurar as definições do proxy](images/sh-prov-proxy.png)

1. Alterne entre **Sim** ou **Não** para as configurações de proxy. Por padrão, Surface Hub detecta automaticamente as configurações de proxy. No entanto, se anteriormente sua infraestrutura precisava usar um servidor proxy e houve alteração para não exigir um servidor proxy, você pode usar um pacote de provisionamento para reverter seus dispositivos Surface Hub para as configurações padrão, selecionando **Sim** e **Detectar configurações automaticamente**.
2. Se você alternar **sim**, poderá selecionar para detectar automaticamente as configurações de proxy ou configurar manualmente as configurações inserindo uma das seguintes:

    - Uma URL para um script de instalação.
    - Um endereço de servidor proxy estático e informações de porta.

3. Se você pretende usar um script de instalação ou um servidor proxy, desativar detectar automaticamente **as configurações**. Você pode usar um script de instalação *ou um* servidor proxy, não ambos.
4. Insira exceções (endereços aos Surface Hub devem se conectar diretamente sem usar o servidor proxy). **Exemplo:** *.office365.com
5. Identifique se o servidor proxy deve ser usado para endereços locais.

### <a name="set-up-device-admins"></a>Configurar administradores de dispositivos

 > [!div class="mx-imgBorder"]
 > ![Ingressar no Active Directory, no Azure AD ou criar uma conta de administrador local](images/sh2-wcd.png)

Você pode registrar o dispositivo no Active Directory e especificar um grupo de segurança para usar o aplicativo Configurações, se inscrever no Azure Active Directory para permitir que os administradores globais usem o aplicativo Configurações ou criar uma conta de administrador local no dispositivo.

1. Para registrar o dispositivo no Active Directory, insira as credenciais de uma conta de usuário de privilégios mínimos para ingressar o dispositivo no domínio e especificar que o grupo de segurança tenha credenciais de administrador no Surface Hub. Se aplicar o pacote a um Surface Hub que foi redefinido, você poderá usar a mesma conta de domínio desde que seja a mesma conta que definiu o Surface Hub inicialmente. Caso contrário, uma conta de domínio diferente deve ser usada no pacote de provisionamento.
2. Antes de usar Windows Designer de Configuração para configurar o registro em massa do Azure AD, planeje sua implementação de participação [do Azure AD.](/azure/active-directory/devices/azureadjoin-plan) A configuração **número máximo de dispositivos por usuário** em seu locatário do Azure AD determina quantas vezes o token em massa que você obtém do assistente pode ser usado.
3. Para registrar o dispositivo no Azure AD, selecione essa opção e insira um nome amigável para o token em massa que você obterá usando o assistente. Defina uma data de expiração do token (máximo de 30 dias a partir da data de obtenção do token). Selecione **Obter token em massa**. Na janela **Vamos conectá-lo**, insira uma conta que tenha permissões para ingressar um dispositivo ao Azure AD e, em seguida, a senha. Selecione **Aceitar** para dar Windows Desenhista de Configuração as permissões necessárias.
4. Para criar uma conta de administrador local, selecione essa opção e insira um nome de usuário e senha.

> [!IMPORTANT]
> Se criar uma conta local no pacote de provisionamento, você deverá alterar a senha usando o aplicativo **Configurações** a cada 42 dias. Se a senha não for alterada durante esse período, a conta poderá estar bloqueada e não será possível entrar.

### <a name="enroll-in-third-party-mdm-provider"></a>Registrar-se no provedor de MDM de terceiros

> [!div class="mx-imgBorder"]
> ![Registrar-se no gerenciamento de dispositivo móvel de terceiros](images/sh-prov-mdm.png)

Se você usar um provedor de gerenciamento de dispositivo móvel (MDM) de terceiros, poderá usar esta seção para registrar Surface Hub. Para se inscrever no Intune, primeiro configure o Azure AD join, conforme descrito na seção anterior, e siga as instruções na seguinte documentação do Intune: Configurar o registro automático para dispositivos [Windows 10](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

1. Alternar **Sim** ou **Não** para registro no MDM de terceiros.
2. Se você alternar **sim**, forneça uma conta de serviço e senha ou impressão digital de certificado que está autorizada a registrar o dispositivo e especificar o tipo de autenticação.
3. Se necessário pelo provedor MDM, insira as URLs para o serviço de descoberta, o serviço de registro e o serviço de política.

 Para saber mais, confira [Gerenciar Surface Hub com um provedor MDM.](manage-settings-with-mdm-for-surface-hub.md)

### <a name="add-applications"></a>Adicionar aplicativos

> [!div class="mx-imgBorder"]
> ![adicionar um aplicativo](images/sh-prov-apps.png)

Você pode instalar vários aplicativos da Plataforma Universal do Windows (UWP) em um pacote de provisionamento. Para saber mais, confira [Provisionar PCs com aplicativos](/windows/configuration/provisioning-packages/provision-pcs-with-apps).

> [!NOTE]
> Embora Windows Designer de Configuração permite adicionar um aplicativo Win32 clássico a um pacote de provisionamento, Surface Hub aceita somente aplicativos UWP. Se você incluir um aplicativo Win32 clássico, o provisionamento falhará.

### <a name="add-a-configuration-file"></a>Adicionar um arquivo de configuração

Além desse pacote de provisionamento, você pode usar um arquivo de configuração Surface Hub para facilitar ainda mais a configuração de seus dispositivos. Um arquivo Surface Hub de configuração contém uma lista de contas de dispositivos para se conectar a Exchange, Microsoft Teams ou Skype for Business, bem como "nomes amigáveis" para projeção sem fio.

**Para criar um arquivo Surface Hub configuração:**

1. Abra Microsoft Excel (ou outro editor de .csv), crie um arquivo .csv chamado SurfaceHubConfiguration.csv
2. Insira uma lista de contas de dispositivo e nomes amigáveis neste formato:

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > O arquivo de configuração não deve conter cabeçalhos de coluna. Quando incluído em um pacote de provisionamento aplicado Surface Hub, você pode selecionar a conta e o nome amigável para o dispositivo no arquivo. Para criar o arquivo .csv, use um formato de endereço UPN (rainier@contoso.com) ou o formato de nome de logon de nível inferior (contoso\rainier).

- rainier@contoso.com,password,Rainier Surface Hub

3. Salve o arquivo na pasta do projeto e copie-o para a chave USB com o pacote de provisionamento.

> [!NOTE]
> O arquivo de configuração só pode ser aplicado durante a configuração da primeira execução.

### <a name="password-protect-provisioning-package"></a>Pacote de provisionamento de proteção de senha

Se você optar por usar uma senha, precisará inserá-la sempre que aplicar o pacote de provisionamento a um dispositivo.

### <a name="complete-provisioning-wizard"></a>Assistente de provisionamento completo

Se você precisar apenas definir configurações comuns, selecione **Concluir**Criar e ignorar para a seção  >  **** Criar [seu pacote](#build-your-package). Ou continue configurando configurações alternando para Provisionamento Avançado.

## <a name="use-advanced-provisioning"></a>Usar provisionamento avançado

> [!TIP]
> Use o assistente para criar um pacote com as configurações comuns e alterne para o editor avançado a fim de adicionar outras configurações.<br><br> ![Alternar para o editor avançado](images/icd-simple-edit.png)

1. Se continuar na seção anterior, selecione **Alternar** para editor avançado caso contrário, abra **Windows Designer** de Configuração e selecione **Provisionamento avançado**.<br>
  ![Use provisionamento avançado.](images/sh-prov-adv.png)

2. Nomeia seu projeto e selecione **Próximo**.
3. Selecione **Comum para Windows 10 Team,** selecione **Próximo**e, em seguida, selecione **Concluir**.<br>
     ![Novo projeto do WCD](images/icd-new-project.png)

4. No projeto, em **Personalizações disponíveis,** selecione **Configurações comuns da equipe.**<br>
     ![Configurações comuns do WCD](images/icd-common-settings.png)

### <a name="add-a-certificate-to-your-package"></a>Adicionar um certificado ao pacote

É possível usar pacotes de provisionamento para instalar certificados que permitirão a autenticação do dispositivo no Microsoft Exchange.

> [!NOTE]
> Os pacotes de provisionamento só podem instalar certificados no repositório do dispositivo (computador local), não no repositório do usuário. Se sua organização exigir que os certificados sejam instalados no armazenamento **** do usuário, use o aplicativo hub **Configurações:** Atualizar & Certificado de Importação de  >  **Certificados de**  >  **Segurança**.
Como alternativa, você pode usar políticas  [**MDM**](manage-settings-with-mdm-for-surface-hub.md) para implantar certificados no armazenamento de dispositivos ou no armazenamento do usuário.

> [!TIP]
> A **seção ClientCertificates** é para arquivos .pfx com uma chave privada; os arquivos .cer para CAs raiz devem ser colocados na seção **RootCertificates** e para CAs intermediários na seção **CACertificates.**

1. Em **Windows personalizações**disponíveis do Designer de Configuração, vá para Configurações do Tempo de Execução  >  **** ****  >  **Certificados**  >  **ClientCertificates**.
2. Insira um rótulo para **CertificateName** e selecione **Adicionar**.
3. Insira a **CertificatePassword**.
4. Para **CertificatePath**, procure e selecione o certificado.
5. Defina **ExportCertificate** como **False**.
6. Para **KeyLocation**, selecione **Software only**.

### <a name="add-a-uwp-app-to-your-package"></a>Adicionar um aplicativo UWP ao pacote

Para adicionar um aplicativo UWP a um pacote de provisionamento, você precisará do pacote do aplicativo (arquivos .appx ou .appxbundle) e quaisquer arquivos de dependência. Se você adquiriu o aplicativo na Microsoft Store para Empresas, também precisará da licença de aplicativo *não codificada*. Consulte [Distribuir aplicativos offline](/microsoft-store/distribute-offline-apps) para saber como baixar esses itens na Microsoft Store para Empresas.

**Para adicionar um aplicativo UWP:**

1. No painel **Personalizações disponíveis**, vá até **Configurações de tempo de execução** > **UniversalAppInstall** > **DeviceContextApp**.
2. Insira um **PackageFamilyName** para o aplicativo e selecione **Adicionar**. Para manter a consistência, use o nome da família de pacotes do aplicativo. Se você adquiriu o aplicativo na Microsoft Store para Empresas, poderá encontrar o nome da família de pacotes na licença do aplicativo. Abra o arquivo de licença usando um editor de texto e use o valor entre as marcas PFM.
3. Para **ApplicationFile,** selecione **Procurar** para encontrar e selecionar o aplicativo de destino ( .appx ou .appxbundle).
4. Para **DependencyAppxFiles,** selecione **Procurar** para encontrar e adicionar quaisquer dependências para o aplicativo. Para o Surface Hub, você só precisará das versões x64 dessas dependências.

Se você adquiriu o aplicativo do Microsoft Store para Empresas, precisará adicionar a licença do aplicativo ao pacote de provisionamento.

**Para adicionar licença de aplicativo:**

1. Crie uma cópia da licença do aplicativo e renomeie-a para usar uma extensão **.ms-windows-store-license**. Por exemplo, renomeie "example.xml" para "example.ms-windows-store-license".
2. Em Windows Configuration Designer, vá **para Personalizações**disponíveis Configurações do Tempo de Execução  >  ****  >  **UniversalAppInstall**  >  **DeviceContextAppLicense**.
3. Insira um **LicenseProductId** e selecione **Adicionar**. Para manter a consistência, use a ID da licença do aplicativo. Abra o arquivo de licença usando um editor de texto. Em seguida, na marca **Licença,** use o valor no **atributo LicenseID.**
4. Selecione o novo nó **LicenseProductId**. Para **LicenseInstall,** selecione **Procurar** para encontrar e selecione seu arquivo de licença renomeado (example.ms-windows-store-license).

### <a name="add-a-policy-to-your-package"></a>Adicionar uma política ao pacote

O Surface Hub oferece suporte a um subconjunto das políticas do [Provedor de serviços de configuração de políticas](/windows/client-management/mdm/policy-configuration-service-provider). Algumas dessas políticas podem ser configuradas com o Windows Configuration Designer.

 **Para adicionar [políticas de CSP:](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)**

1. Vá para **Personalizações disponíveis**  >  **Configurações de tempo de execução**  >  **Políticas**.
2. Selecione o componente que você deseja gerenciar e configure a configuração de política conforme apropriado. Por exemplo, para impedir que os funcionários usem a navegação no site inPrivate no Surface Hub, selecione **PermitirInPrivate** e selecione **Desabilitar**.  

    > [!div class="mx-imgBorder"]
    > ![Configurar configuração de política](images/sh-prov-policies.png)

### <a name="add-surface-hub-settings-to-your-package"></a>Adicionar configurações do Surface Hub ao seu pacote

Você pode adicionar configurações do [Provedor de serviços de configuração SurfaceHub](/windows/client-management/mdm/surfacehub-csp) ao seu pacote de provisionamento.

1. Vá para **Personalizações disponíveis Common**  >  **Team Edition Configurações**.
1. Selecione o componente que você deseja gerenciar e configure a configuração de política conforme apropriado.
1. Quando terminar de configurar o pacote de provisionamento, selecione **Salvar**  >  **arquivo**.
1. Leia o aviso de que os arquivos de projeto podem conter informações confidenciais e selecione **OK**

### <a name="build-your-package"></a>Compilar o pacote

Ao compilar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados.  Armazene os arquivos do projeto em um local seguro ou exclua se não for mais necessário.

1. Abra **Windows pacote de Provisionamento**de Exportação do Designer de  >  ****  >  **Configuração.**
2. Alterar **Proprietário** para **Administrador de IT.**  
3. Defina um valor para **Versão do Pacote** e selecione **Avançar**.

> [!TIP]
> A definição do proprietário como Administrador de IT garante que as configurações do pacote mantenham as "propriedades de precedência" apropriadas e permaneçam em vigor no Surface Hub se outros pacotes de provisionamento são subsequentemente aplicados de outras fontes.

> [!TIP]
> Você pode modificar pacotes existentes e alterar o número da versão para atualizar pacotes aplicados anteriormente.

4. Opcional: você pode optar por criptografar o pacote e habilitar a assinatura de pacote:

    1. Selecione **Criptografar pacote** e insira uma senha.
    1. Selecione **Assinar pacote**  >  **Procurar** e escolha o certificado conforme apropriado.

    > [!IMPORTANT]
    > É recomendável incluir um certificado de provisionamento confiável no pacote de provisionamento. Quando o pacote é aplicado a um dispositivo, o certificado é adicionado ao armazenamento do sistema, permitindo que os pacotes subsequentes sejam aplicados silenciosamente.

5. Selecione **Próximo** para especificar o local de saída. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída. Ou selecione **Procurar** para alterar o local de saída padrão. Selecione **Avançar**.
6. Selecione **Criar** para começar a criar o pacote. As informações do projeto são exibidas na página de com build.
7. Se sua com build falhar, uma mensagem de erro será exibida com um link para a pasta do projeto. Revise os logs para diagnosticar o erro e tente criar o pacote novamente.
8. Se sua com build for bem-sucedida, o nome do pacote de provisionamento, diretório de saída e diretório do projeto será exibido. Selecione **Concluir** para fechar o assistente e volte para a página Personalizações.
9. Selecione  **o local de**  saída para ir para o local do pacote. Copie o .ppkg em uma unidade flash USB vazia.

## <a name="apply-a-provisioning-package-to-surface-hub"></a>Aplicar um pacote de provisionamento ao Surface Hub

Há duas opções para implantar pacotes de provisionamento em um Surface Hub. Durante o primeiro assistente de executar [,](#apply-a-provisioning-package-during-first-run)você pode aplicar um pacote de provisionamento que instala certificados ou depois que o programa de primeira executado é concluído, você pode aplicar um pacote de provisionamento que configura configurações, aplicativos e certificados usando o [Configurações](#apply-a-provisioning-package-using-settings-app).

### <a name="apply-a-provisioning-package-during-first-run"></a>Aplicar um pacote de provisionamento durante a primeira execução

> [!IMPORTANT]
> Durante o programa executado pela primeira vez, você só pode usar pacotes de provisionamento para instalar certificados. Use o aplicativo **Configurações** para instalar aplicativos e aplicar outras configurações.

1. Quando você ativar o Surface Hub pela primeira vez, o programa de primeira executar exibirá a página [**Olá lá.**](first-run-program-surface-hub.md) Verifique se as configurações estão definidas corretamente antes de continuar.
2. Insira a unidade flash USB que contém o arquivo .ppkg no Surface Hub. Se o pacote estiver no diretório raiz da unidade, o programa de primeira execução o reconhecerá e perguntará se você deseja configurar o dispositivo. Selecione **Configurar**.
3. A próxima tela solicita que você selecione uma origem de provisionamento. Selecione **Mídia Removível** e toque em **Avançar**.
4. Selecione o pacote de provisionamento (*.ppkg) que você deseja aplicar e toque em **Próximo**. Observe que só é possível instalar um pacote durante a primeira execução.
5. O programa de primeira execução mostrará um resumo das alterações que o pacote de provisionamento aplicará. Selecione **Sim, adicionar**.
6. Se um arquivo de configuração estiver incluído no diretório raiz da unidade USB, você verá **Selecionar uma configuração**. A primeira conta de dispositivo no arquivo de configuração será exibida com um resumo das informações da conta que serão aplicadas ao Surface Hub.
7. Em **Selecionar uma configuração,** selecione o nome do dispositivo a ser aplicado e selecione **Next**.

As configurações do pacote de provisionamento serão aplicadas ao dispositivo e o OOBE será concluído. Depois que o dispositivo for reiniciado, você pode remover a unidade USB.

### <a name="apply-a-provisioning-package-using-settings-app"></a>Aplicar um pacote de provisionamento usando Configurações aplicativo

1. Insira a unidade flash USB que contém o arquivo .ppkg no Surface Hub.
2. A partir Surface Hub, **inicie Configurações** e insira as credenciais de administrador quando solicitado.
3. Navegue até **Surface Hub** > **Gerenciamento de dispositivo**. Em **Pacotes de provisionamento,** selecione **Adicionar ou remover um pacote de provisionamento**  >  **Adicionar um pacote**.
4. Escolha seu pacote de provisionamento e selecione **Adicionar**.  Se solicitado, insira suas credenciais de administrador novamente.
5. Você verá um resumo das alterações a serem aplicadas. Selecione **Sim, adicionar**.

## <a name="learn-more"></a>Saiba mais

- [Baixar Windows Designer de Configuração](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [Criar um pacote de provisionamento para o Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Gerenciar o Surface Hub com um provedor MDM](manage-settings-with-mdm-for-surface-hub.md)
