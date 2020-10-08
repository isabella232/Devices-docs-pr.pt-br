---
title: Criar pacotes de provisionamento (Surface Hub)
description: No Windows 10, os ajustes que usam o Registro ou um provedor de serviços de configuração (CSP) podem ser definidos por pacotes de provisionamento.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: adicionar certificado, pacote de provisionamento
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: ecbeca9f0910f1fa1ff2721bcf1b745195552ca2
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103795"
---
# Criar pacotes de provisionamento (Surface Hub)

Este tópico explica como criar um pacote de provisionamento usando o Designer de Configuração do Windows e aplicá-lo a dispositivos Surface Hub. Para o Surface Hub, você pode usar pacotes de provisionamento para adicionar certificados, instalar aplicativos da Plataforma Universal do Windows (UWP) e personalizar políticas e configurações.

Você pode aplicar um pacote de provisionamento usando um pendrive na primeira configuração de execução ou por meio do aplicativo **Configurações**. 


## Vantagens
-   Configure rapidamente os dispositivos sem usar um provedor de gerenciamento (MDM) de dispositivo móvel.

-   Nenhuma conectividade de rede é necessária.

-   É simples de aplicar.

[Saiba mais sobre os benefícios e as utilizações dos pacotes de provisionamento.](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## Requisitos 

Para criar e aplicar um pacote de provisionamento a um Surface Hub, você precisará do seguinte:

-   Designer de Configuração do Windows, que pode ser instalado a partir da Microsoft Store ou da avaliação do Windows 10 e Kit de implantação (ADK). [Saiba como instalar o Designer de Configuração do Windows.](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   Um pendrive.
-   Se você aplicar o pacote usando o aplicativo **Configurações**, precisará de credenciais de administrador do dispositivo.

Você deve criar o pacote de provisionamento em um computador com Windows 10, salvar o pacote em uma unidade USB e o implantar no Surface Hub.


## Itens com suporte para pacotes de provisionamento do Surface Hub

Usando o assistente **Dispositivos de provisionamento do Surface Hub**, você pode:

- Inscrever-se no Active Directory, Azure Active Directory, ou MDM 
- Criar uma conta de administrador do dispositivo 
- Adicionar aplicativos e certificados
- Configurar as definições do proxy
- Adicionar um arquivo de configuração do Surface Hub

>[!WARNING]
>Você deve executar o Designer de Configuração do Windows no Windows 10 para configurar o registro do Azure Active Directory usando o assistente.

Usando o editor de provisionamento avançado, você pode adicionar esses itens a pacotes de provisionamento para o Surface Hub:

- **Políticas** – o Surface Hub oferece suporte a um subconjunto das políticas do [Provedor de serviços de configuração de políticas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies). 
- **Configurações** – é possível definir qualquer configuração no [Provedor de serviços de configuração SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx).

>[!TIP]
> Use o assistente para criar um pacote com as configurações comuns e alterne para o editor avançado a fim de adicionar outras configurações.
>
>![abrir editor avançado](images/icd-simple-edit.png)

## Use o assistente de provisionamento do Surface Hub

Depois de [Instalar o Designer de Configuração do Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), você pode criar um pacote de provisionamento.

### Criar o pacote de provisionamento 

1. Abra o Designer de Configuração do Windows:
   - Na tela inicial ou na pesquisa do menu Iniciar, digite "Designer de Configuração do Windows" e clique no atalho do Designer de Configuração do Windows. 
    
     ou
    
   - Se você instalou o Designer de Configuração do Windows do ADK, navegue até `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (em um computador x64) ou `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (em um computador x86) e clique duas vezes em **ICD.exe**.

2. Clique em **Dispositivos de provisionamento do Surface Hub**.

3. Dê um nome ao projeto e clique em **Avançar**.

### Configure settings

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>To provision the device with a certificate, click <strong>Add a certificate</strong>. Enter a name for the certificate, and then browse to and select the certificate to be used.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for proxy settings. A configuração padrão para o Surface Hub é detectar automaticamente as configurações de proxy; portanto, você pode selecionar <strong>Não</strong> se é a configuração que você deseja. No entanto, se anteriormente sua infraestrutura precisava usar um servidor proxy e houve alteração para não exigir um servidor proxy, você pode usar um pacote de provisionamento para reverter seus dispositivos Surface Hub para as configurações padrão, selecionando <strong>Sim</strong> e <strong>Detectar configurações automaticamente</strong>. </br></br>Se você alternar para <strong>Sim</strong>, você pode selecionar para detectar automaticamente as configurações de proxy ou definir manualmente as configurações inserindo um URL para um script de instalação ou um endereço de servidor proxy estático. Você também pode identificar se deve usar o servidor proxy para endereços locais e inserir as exceções (endereços que devem se conectar ao Surface Hub diretamente, sem usar o servidor proxy).  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>Você pode registrar o dispositivo no Active Directory e especificar um grupo de segurança para usar o aplicativo Configurações, se inscrever no Azure Active Directory para permitir que os administradores globais usem o aplicativo Configurações ou criar uma conta de administrador local no dispositivo.</br></br>Para registrar o dispositivo no Active Directory, insira as credenciais de uma conta de usuário de privilégios mínimos para ingressar o dispositivo no domínio e especificar que o grupo de segurança tenha credenciais de administrador no Surface Hub. Se um pacote de provisionamento que registra um dispositivo no Active Directory for aplicado a um Surface Hub que foi redefinido, a mesma conta de domínio só pode ser usada se a conta listada for um administrador de domínio ou for a mesma conta que configurou o Surface Hub inicialmente. Otherwise, a different domain account must be used in the provisioning package.</br></br>Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>. A configuração <strong>número máximo de dispositivos por usuário</strong> em seu locatário do Azure AD determina quantas vezes o token em massa que você obtém do assistente pode ser usado. Para registrar o dispositivo no Azure AD, selecione essa opção e insira um nome amigável para o token em massa que você obterá usando o assistente. Set an expiration date for the token (maximum is 30 days from the date you get the token). Click <strong>Get bulk token</strong>. In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password. Click <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</br></br>To create a local administrator account, select that option and enter a user name and password. </br></br><strong>Important:</strong> If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days. If the password is not changed during that period, the account might be locked out and unable to sign in.  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for enrollment in MDM. </br></br>Se você alternar para <strong>Sim</strong>, você deve fornecer uma conta de serviço e a senha ou impressão digital certificada que está autorizada a registrar o dispositivo, além de especificar o tipo de autenticação. If required by your MDM provider, also enter the URLs for the discovery service, enrollment service, and policy service. <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">Learn more about managing Surface Hub with MDM.</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>You can install multiple Universal Windows Platform (UWP) apps in a provisioning package. For help with the settings, see <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Provision PCs with apps</a>. </br></br><strong>Important:</strong> Although the wizard interface allows you to select a Classic Win32 app, only include UWP apps in a provisioning package that will be applied to Surface Hub. If you include a Classic Win32 app, provisioning will fail. </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>You don&#39;t configure any settings in this step. It provides instructions for including a configuration file that contains a list of device accounts. O arquivo de configuração não deve conter cabeçalhos de coluna. Ao aplicar o pacote de provisionamento ao Surface Hub, se um arquivo de configuração do Surface Hub é incluído na unidade USB, você pode selecionar a conta e o nome amigável para o dispositivo a partir do arquivo. See <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Sample configuration file</a> for an example.</br></br><strong>Important:</strong> The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br>You can set a password to protect your provisioning package. You must enter this password when you apply the provisioning package to a device.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

After you're done, click **Create**. Leva apenas alguns segundos. Quando o pacote é criado, o local onde o pacote está armazenado é exibido como hiperlink na parte inferior da página.

## Arquivo de configuração de exemplo

Um arquivo de configuração do Surface Hub contém uma lista de contas de dispositivo que seu dispositivo pode usar para conectar-se ao Exchange e ao Skype for Business. Ao aplicar um pacote de provisionamento ao Surface Hub, você pode incluir um arquivo de configuração no diretório raiz da unidade USB e, em seguida, selecionar a conta desejada para aplicar a esse dispositivo. O arquivo de configuração só pode ser aplicado durante a experiência de instalação out-of-box (OOBE) e só pode ser usado com pacotes de provisionamento criados usando o Designer de Configuração do Windows lançado com o Windows 10, versão 1703.

Use o Microsoft Excel ou outro editor de CSV para criar um arquivo CSV chamado `SurfaceHubConfiguration.csv`. No arquivo, insira uma lista de contas de dispositivo e nomes amigáveis neste formato:

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>Como o arquivo de configuração armazena as senhas de conta do dispositivo em texto sem formatação, recomendamos que você atualize as senhas depois depois de aplicar o pacote de provisionamento aos seus dispositivos. Você pode usar o [nó DeviceAccount](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) no [provedor de serviço de configuração do Surface Hub (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) para atualizar as senhas por meio do MDM.


Veja este exemplo de `SurfaceHubConfiguration.csv`: 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## Use provisionamento avançado.

Depois de [Instalar o Designer de Configuração do Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), você pode criar um pacote de provisionamento.

### Criar o pacote de provisionamento (avançado)

1. Abra o Designer de Configuração do Windows:
   - Na tela inicial ou na pesquisa do menu Iniciar, digite "Designer de Configuração do Windows" e clique no atalho do Designer de Configuração do Windows. 
    
     ou
    
   - Se você instalou o Designer de Configuração do Windows do ADK, navegue até `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (em um computador x64) ou `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (em um computador x86) e clique duas vezes em **ICD.exe**.

2. Clique em **Provisionamento avançado**.
   
3. Name your project and click **Next**.

4. Select **Common to Windows 10 Team**, click **Next**, and then click **Finish**.

    ![ICD new project](images/icd-new-project.png)

5. In the project, under **Available customizations**, select **Common Team settings**.

    ![ICD common settings](images/icd-common-settings.png)


### Adicionar um certificado ao pacote
É possível usar pacotes de provisionamento para instalar certificados que permitirão a autenticação do dispositivo no Microsoft Exchange.

> [!NOTE]
> Os pacotes de provisionamento só podem instalar certificados no repositório do dispositivo (computador local), não no repositório do usuário. Se a sua organização exige que os certificados sejam instalados no repositório do usuário, use o Gerenciamento de Dispositivos Móveis (MDM) para implantar esses certificados. Consulte a documentação da solução MDM para obter detalhes.

1. No painel **Personalizações disponíveis**, vá até **Configurações de tempo de execução** > **Certificados** > **ClientCertificates**. 

2. Insira um **CertificateName** e clique em **Adicionar**. 

2. Insira a **CertificatePassword**. 

3. Para **CertificatePath**, procure e selecione o certificado. 

4. Defina **ExportCertificate** como **False**.

5. Para **KeyLocation**, selecione **Software only**.


### Adicionar um aplicativo da Plataforma Universal do Windows (UWP) ao pacote
Antes de adicionar um aplicativo UWP a um pacote de provisionamento, você precisa do pacote do aplicativo (.appx ou .appxbundle) e quaisquer arquivos de dependência. Se você adquiriu o aplicativo na Microsoft Store para Empresas, também precisará da licença de aplicativo *não codificada*. Consulte [Distribuir aplicativos offline](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) para saber como baixar esses itens na Microsoft Store para Empresas.

1. No painel **Personalizações disponíveis**, vá até **Configurações de tempo de execução** > **UniversalAppInstall** > **DeviceContextApp**.

2. Insira um **PackageFamilyName** para o aplicativo e clique em **Adicionar**. Para manter a consistência, use o nome da família de pacotes do aplicativo. If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license. Open the license file using a text editor, and use the value between the \<PFM\>...\</PFM\> tags.

3. For **ApplicationFile**, click **Browse** to find and select the target app (either an \*.appx or \*.appxbundle).

4. Para **DependencyAppxFiles**, clique em **Procurar** para encontrar e adicionar quaisquer dependências do aplicativo. Para o Surface Hub, você só precisará das versões x64 dessas dependências.

Se você adquiriu o aplicativo na Microsoft Store para Empresas, também precisará adicionar a licença do aplicativo ao seu pacote de provisionamento.

1. Crie uma cópia da licença do aplicativo e renomeie-a para usar uma extensão **.ms-windows-store-license**. Por exemplo, "example.xml" torna-se "example.ms-windows-store-license".

2. No ICD, no painel **Personalizações disponíveis**, vá até **Configurações de tempo de execução** > **UniversalAppInstall** > **DeviceContextAppLicense**.

3. Insira uma **LicenseProductId** e clique em **Adicionar**. Para manter a consistência, use a ID da licença do aplicativo. Open the license file using a text editor. Then, in the \<License\> tag, use the value in the **LicenseID** attribute.

4. Select the new **LicenseProductId** node. Para **LicenseInstall**, clique em **Procurar** para encontrar e selecionar o arquivo de licença que você renomeou na Etapa 1.


### Adicionar uma política ao pacote
O Surface Hub oferece suporte a um subconjunto das políticas do [Provedor de serviços de configuração de políticas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx). Algumas dessas políticas podem ser configuradas com o ICD.

1. No painel **Personalizações disponíveis**, vá até **Configurações de tempo de execução** > **Políticas**.

2. Selecione uma das áreas de políticas disponíveis.

3. Selecione e defina a política que você deseja adicionar ao seu pacote de provisionamento.


### Adicionar configurações do Surface Hub ao seu pacote 

You can add settings from the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) to your provisioning package. 

1. In the **Available customizations** pane, go to **Runtime settings** > **SurfaceHub**.

2. Select one of the available setting areas.

3. Selecione e defina a configuração que você deseja adicionar ao seu pacote de provisionamento. 


## Compilar o pacote

1. Quando terminar de configurar o pacote de provisionamento, no menu **Arquivo**, clique em **Salvar**.

2. Leia o aviso de que arquivos de projeto podem conter informações confidenciais e clique em **OK**.

    > [!IMPORTANT]
    > Ao compilar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluí-los quando não forem mais necessários.

3. No menu **Exportar**, clique em **Pacote de provisionamento**.

4. Altere **Proprietário** para **Administrador de TI**, o que definirá a precedência desse pacote de provisionamento como acima dos pacotes de provisionamento aplicados a esse dispositivo de outras origens.

5. Defina um valor para **Versão do Pacote** e selecione **Avançar**.

    > [!TIP]
    > Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes previamente aplicados.

6. Opcional: é possível optar por criptografar o pacote e habilitar a assinatura do pacote.

    -   **Habilitar a criptografia de pacote** – se você selecionar essa opção, uma senha gerada automaticamente será mostrada na tela.

    -   **Habilitar a assinatura de pacote** – se você selecionar essa opção, deverá selecionar um certificado válido a ser usado para assinar o pacote. Para especificar o certificado, clique em **Procurar...** e escolha o certificado que deseja usar para assinar o pacote.

        > [!IMPORTANT]
        > Recomendamos incluir um certificado de provisionamento confiável no pacote de provisionamento. Quando o pacote é aplicado a um dispositivo, o certificado é adicionado ao repositório do sistema, e qualquer pacote assinado com esse certificado poderá ser aplicado silenciosamente depois. 

7. Clique em **Avançar** para especificar o local de saída do pacote de provisionamento quando ele estiver compilado. Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.<p>
Como alternativa, clique em **Procurar** para alterar o local de saída padrão.

8. Clique em **Avançar**.

9. Clique em **Compilar** para começar a criar o pacote. As informações do projeto são exibidas na página de compilação, e a barra de progresso indica o status da compilação.<p>
Se precisar cancelar a compilação, clique em **Cancelar**. Isso cancela o atual processo de compilaçãol, fecha o assistente e leva você de volta à **Página de Personalizações**.

10. Se sua compilação falhar, será exibida uma mensagem de erro que inclui um link para a pasta do projeto. Você pode examinar os logs para determinar o que causou o erro. Depois de corrigir o problema, tente compilar o pacote novamente.<p>
Se a compilação for bem-sucedida, o nome do pacote de provisionamento, o diretório de saída e o diretório do projeto serão mostrados.

    -   Se você fizer essa opção, poderá compilar novamente o pacote de provisionamento e escolher um caminho diferente para o pacote de saída. Para fazer isso, clique em **Voltar** para alterar o nome e o caminho do pacote de saída e, em seguida, clique em **Avançar** para iniciar outra compilação.
    
    -   Caso você tenha terminado, clique em **Concluir** para fechar o assistente e voltar para a **Customizations Page**.

11. Selecione o link **local de saída** para ir até o local do pacote. Copie o .ppkg em uma unidade flash USB vazia.


## Aplicar um pacote de provisionamento ao Surface Hub

There are two options for deploying provisioning packages to a Surface Hub. [During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-package-using-settings). 


### Apply a provisioning package during first run

> [!IMPORTANT]
> During the first-run program, you can only use provisioning packages to install certificates. Use the **Settings** app to install apps and apply other settings.

1. Quando você ativar o Surface Hub pela primeira vez, o programa de primeira execução exibirá a [**página Olá**](first-run-program-surface-hub.md#first-page). Verifique se as configurações estão definidas corretamente antes de continuar.

2. Insira a unidade flash USB que contém o arquivo .ppkg no Surface Hub. Se o pacote estiver no diretório raiz da unidade, o programa de primeira execução o reconhecerá e perguntará se você deseja configurar o dispositivo. Selecione **Configurar**.

    ![Configurar dispositivo?](images/provisioningpackageoobe-01.png)

3. A próxima tela solicita que você selecione uma origem de provisionamento. Selecione **Mídia Removível** e toque em **Avançar**.

    ![Provisionar este dispositivo](images/provisioningpackageoobe-02.png)
    
4. Selecione o pacote de provisionamento (\*.ppkg) que deseja aplicar e toque em **Avançar**. Observe que só é possível instalar um pacote durante a primeira execução.

    ![Escolher um pacote](images/provisioningpackageoobe-03.png)

5. O programa de primeira execução mostrará um resumo das alterações que o pacote de provisionamento aplicará. Selecione **Sim, adicionar**.  

    ![Você confia nesse pacote?](images/provisioningpackageoobe-04.png)
    
6. Se um arquivo de configuração estiver incluído no diretório raiz da unidade USB, você verá **Selecionar uma configuração**. A primeira conta de dispositivo no arquivo de configuração será exibida com um resumo das informações da conta que serão aplicadas ao Surface Hub.

    ![selecione uma configuração](images/ppkg-config.png)    

7. Em **Selecionar uma configuração**, selecione o nome do dispositivo a aplicar e, em seguida, clique em **Próximo**.

    ![selecione um nome amigável do dispositivo](images/ppkg-csv.png)
    
As configurações do pacote de provisionamento serão aplicadas ao dispositivo e o OOBE será concluído. Depois que o dispositivo for reiniciado, você pode remover a unidade USB.

### Aplicar um pacote usando Configurações

1. Insira a unidade flash USB que contém o arquivo .ppkg no Surface Hub.

2. No Surface Hub, inicie **Configurações** e insira as credenciais de administrador quando solicitado.

3. Navegue até **Surface Hub** > **Gerenciamento de dispositivo**. Em **Pacotes de provisionamento**, selecione **Adicionar ou remover um pacote de provisionamento**.

4. Selecione **Adicionar um pacote**.

5. Escolha seu pacote de provisionamento e selecione **Adicionar**. Você precisará inserir novamente as credenciais de administrador, se solicitado.

6. Você verá um resumo das alterações que o pacote de provisionamento aplicará. Selecione **Sim, adicionar**.


