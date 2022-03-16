---
title: Implantar o aplicativo Surface com Microsoft Store para Empresas ou Microsoft Store para Educação (Surface)
description: Saiba como adicionar e baixar o aplicativo Surface com Microsoft Store para Empresas ou Microsoft Store para Educação, bem como instalar o aplicativo Surface com o PowerShell e o MDT.
keywords: surface app, app, deployment, customize
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 4/16/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: cb101ece861b19bab43b0e3356a1109389eebb2f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448354"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a>Implantar aplicativo surface com Microsoft Store para Empresas e Education

**Aplicável ao**

- Surface Laptop (todas as gerações)
- Surface Pro 3 e posterior
- Surface Laptop Go
- Surface Go (todas as gerações)
- Surface Book (todas as gerações)
- Surface Studio (todas as gerações)
- Surface Laptop Studio
- Surface Pro com LTE Avançado (Model 1807)
- Surface Pro (Model 1796)
- Surface 3 LTE
- Surface 3

O aplicativo Surface é um aplicativo Microsoft Store leve que fornece controle de muitas configurações e opções específicas do Surface com acesso rápido às informações do dispositivo, incluindo número de série, nome do modelo surface, versão UEFI e drivers relacionados.  

Os clientes que Windows Update normalmente receberão o aplicativo Surface como parte das atualizações automáticas. Mas se sua organização estiver preparando imagens para implantação em seus dispositivos Surface, talvez você queira incluir o aplicativo Surface (anteriormente chamado de Surface Hub) em seu processo de imagens e implantação, em vez de exigir que os usuários de cada dispositivo individual baixem e instalem o aplicativo no Microsoft Store ou no seu Microsoft Store para Empresas. 

> [!NOTE]
> Este artigo não se aplica ao Surface Pro X. Para obter mais informações, consulte [Deploying, managing, and sering Surface Pro X](surface-pro-arm-app-management.md)

## <a name="surface-app-overview"></a>Visão geral do aplicativo Surface

O aplicativo Surface está disponível como download gratuito do [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P). Os usuários podem baixá-lo e instalá-lo do Microsoft Store, mas se sua organização usar o Microsoft Store para Empresas, você precisará adicioná-lo ao inventário da sua loja e possivelmente incluir o aplicativo como parte do seu processo de implantação Windows. Esses processos são discutidos ao longo deste artigo. Para obter mais informações sobre Microsoft Store para Empresas, [consulte Microsoft Store para Empresas](/microsoft-store/). 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a>Adicionar aplicativo Surface a uma Microsoft Store para Empresas de usuário 

Antes que os usuários possam instalar ou implantar um aplicativo a partir da conta de Microsoft Store para Empresas de uma empresa, os aplicativos desejados primeiro devem ser disponibilizados e licenciados para os usuários de uma empresa. 

1. Se você ainda não tiver feito isso, crie uma Microsoft Store para Empresas [de usuário](https://www.microsoft.com/business-store). 

2. Entre no portal. 

3. Habilitar o licenciamento offline: clique em **Gerenciar** >  **Configurações** e selecione a caixa de seleção Mostrar aplicativos licenciados **offline** para pessoas que estão comprando na loja, conforme mostrado na Figura 1. Para obter mais informações sobre Microsoft Store para Empresas de licenciamento de aplicativos, consulte [Apps in Microsoft Store para Empresas e Education](/microsoft-store/).

   > [!div class="mx-imgBorder"]
   > ![Mostrar caixa de seleção de aplicativos de licenças offline.](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figura 1. Habilitar aplicativos para uso offline*

4. Adicione o aplicativo Surface à sua Microsoft Store para Empresas de usuário:

    * Pesquisar na loja para **o aplicativo Surface** 
    
    * Depois que o aplicativo Surface for apresentado nos resultados da pesquisa, clique no ícone do aplicativo.
    
    * Você é apresentado com uma opção (selecione **Online** ou **Offline**), conforme mostrado na Figura 2.
    
      > [!div class="mx-imgBorder"]
      > ![Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Figura 2. Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário*
    
    * Clique **em Offline** para selecionar o modo de licenciamento offline.
    
    * Clique **em Obter o aplicativo** para adicionar o aplicativo ao inventário Microsoft Store para Empresas usuário. Conforme mostrado na Figura 3, você verá uma caixa de diálogo que solicita que você reconheça que os aplicativos offline podem ser implantados usando uma ferramenta de gerenciamento ou baixados da página de inventário da empresa em seu armazenamento particular.
    
      > [!div class="mx-imgBorder"]
      > ![Janela de confirmação de aplicativo licenciado offline.](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figura 3. Reconhecimento de aplicativo licenciado offline*
      
    * Clique em **OK**.

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a>Baixar o aplicativo Surface de uma Microsoft Store para Empresas de usuário
Depois de adicionar um aplicativo à conta Microsoft Store para Empresas no modo Offline, você pode baixar e adicionar o aplicativo como um AppxBundle a um compartilhamento de implantação.

1. Faça logoff na conta Microsoft Store para Empresas em https://businessstore.microsoft.com.

2. Clique **em Gerenciar aplicativos >aplicativos & software**. Uma lista de todos os aplicativos da sua empresa é exibida, incluindo o aplicativo Surface que você adicionou no aplicativo [Adicionar Surface a](#add-surface-app-to-a-microsoft-store-for-business-account) uma Microsoft Store para Empresas de conta deste artigo.

3. Em **Ações**, clique na reellipse (**...**) e clique em **Baixar** para uso offline para o aplicativo Surface.

4. Selecione as opções **de Plataforma** e **** Arquitetura desejadas nas seleções disponíveis para o aplicativo selecionado, conforme mostrado na Figura 4.

    > [!div class="mx-imgBorder"]
    > ![Exemplo do pacote AppxBundle.](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Figura 4. Baixar o pacote AppxBundle para um aplicativo*
    
5. Clique **em Baixar**. O pacote AppxBundle será baixado. Observe o caminho do arquivo baixado, pois você precisará disso mais adiante neste artigo.

6. Clique na opção **Licença codificada** ou **Licença não codificada** . Use a opção de licença codificada com ferramentas de gerenciamento como Microsoft Endpoint Configuration Manager ou quando você usa Windows Designer de Configuração para criar um pacote de provisionamento. Selecione a opção licença não codificada ao usar o DISM (Deployment Image Servicing and Management) ou soluções de implantação com base em imagens, incluindo o Microsoft Deployment Toolkit (MDT).

7. Clique **em Gerar** para gerar e baixar a licença do aplicativo. Certifique-se de observar o caminho do arquivo de licença, pois você precisará disso mais adiante neste artigo.

>[!NOTE]
>Quando você baixa um aplicativo para uso offline, como o aplicativo Surface, pode notar uma seção na parte inferior da página rotulada **estruturas necessárias**. Seus computadores de destino devem ter as estruturas instaladas para que o aplicativo seja executado, portanto, talvez seja necessário repetir o processo de download para cada uma das estruturas necessárias para sua arquitetura (x86 ou x64) e também incluí-las como parte da implantação do Windows discutida posteriormente neste artigo.

A Figura 5 mostra as estruturas necessárias para o aplicativo Surface.

> [!div class="mx-imgBorder"]
> ![Estruturas necessárias para o aplicativo Surface.](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Figura 5. Estruturas necessárias para o aplicativo Surface*

>[!NOTE]
>Os números de versão do aplicativo Surface e as estruturas necessárias mudarão à medida que os aplicativos são atualizados. Verifique a versão mais recente do aplicativo Surface e cada estrutura no Microsoft Store para Empresas. Sempre use o aplicativo Surface e as versões recomendadas da estrutura, conforme fornecido pelo Microsoft Store para Empresas. Usar estruturas desatualizadas ou versões incorretas pode resultar em erros ou falhas de aplicativo.

Para baixar as estruturas necessárias para o aplicativo Surface, siga estas etapas:

1. Clique no **botão Baixar** **em Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**. Isso baixa o Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Arquivo Appx para a pasta especificada.

2. Clique no **botão Baixar** **em Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**. Isso baixa o Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe. Arquivo Appx para a pasta especificada.

>[!NOTE]
>Somente a versão de 64 bits (x64) de cada estrutura é necessária para dispositivos Surface. Os dispositivos Surface são dispositivos UEFI nativos de 64 bits e não são compatíveis com versões de 32 bits (x86) de Windows que exigiriam estruturas de 32 bits. 

## <a name="install-surface-app-on-your-computer-with-powershell"></a>Instalar o aplicativo Surface no computador com o PowerShell
O procedimento a seguir provisiona o aplicativo Surface para seu computador e o disponibiliza para quaisquer contas de usuário criadas no computador posteriormente.

1. Usando o procedimento descrito na seção Como [baixar o aplicativo Surface](#download-surface-app-from-a-microsoft-store-for-business-account) de uma Microsoft Store para Empresas deste artigo, baixe o aplicativo Surface AppxBundle e o arquivo de licença. 

2. Inicie uma sessão do PowerShell com privilégios elevados.

    >[!NOTE]
    >Se você não executar o PowerShell como administrador, a sessão não terá as permissões necessárias para instalar o aplicativo.
    
3. Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Onde `<DownloadPath>` está a pasta onde você baixou o appxBundle e o arquivo de licença da conta Microsoft Store para Empresas.

    Por exemplo, se você baixou os arquivos para c:\Temp, o comando executado será:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. Agora o aplicativo do Surface estará disponível no computador atual com o Windows. 

   Antes que o aplicativo Surface seja funcional no computador em que ele foi provisionado, você também deve provisioná-los descritos anteriormente neste artigo. Para provisionar essas estruturas, use o procedimento a seguir na sessão elevada do PowerShell que você usou para provisionar o aplicativo Surface.

5. Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a>Instalar o aplicativo Surface com o MDT
O procedimento a seguir usa o MDT para automatizar a instalação do aplicativo Surface no momento da implantação. O aplicativo é provisionado automaticamente pelo MDT durante a implantação e, assim, você pode usar esse processo com imagens existentes. Este é o processo recomendado para implantar o aplicativo Surface como parte de uma implantação Windows para dispositivos Surface porque ele não reduz a compatibilidade entre plataformas da imagem Windows.

1. Usando o procedimento descrito [anteriormente neste artigo](#download-surface-app-from-a-microsoft-store-for-business-account), baixe o aplicativo Surface AppxBundle e o arquivo de licença. 

2. Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem**.

3. Na página **Detalhes do** Comando do Assistente para Novo Aplicativo, especifique **** o Diretório de Trabalho padrão **** e para o Comando especifique o nome de arquivo do AppxBundle, da seguinte forma:

   * Comando:
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Diretório de Trabalho: %DEPLOYROOT%\Applications\SurfaceApp

Para que o aplicativo Surface funcione no computador de destino, ele também exigirá as estruturas descritas anteriormente neste artigo. Use o procedimento a seguir para importar as estruturas necessárias para o aplicativo Surface para o MDT e configurá-las como dependências.

1. Usando o procedimento descrito anteriormente neste artigo, baixe os arquivos de estrutura. Armazene cada estrutura em uma pasta separada.

2. Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem**.

3. Na página **Detalhes do Comando** , digite o nome de arquivo de cada aplicativo que você baixou no campo **Comando** e no Diretório de Trabalho padrão.

Para configurar as estruturas como dependências do aplicativo Surface, use este processo:

1. Abra as propriedades do aplicativo Surface no MDT Deployment Workbench.

2. Clique na **guia Dependências** e clique em **Adicionar**.

3. Marque a caixa de seleção de cada estrutura usando o nome fornecido no Assistente para Novo Aplicativo.

Após a importação, o aplicativo Surface estará disponível para seleção na etapa **Aplicativos** do Assistente Windows Implantação. Você também pode instalar o aplicativo automaticamente, especificando-o na sequência de tarefas de implantação com este processo:

1. Abra a sequência de tarefas de implantação no MDT Deployment Workbench.

2. Adicione uma nova tarefa **instalar Aplicativo** na seção **Restaurar Estado** da implantação.

3. Selecione **Instalar um único aplicativo** e especifique o **Surface App** como **o Aplicativo a ser instalado**.

Para obter mais informações sobre como incluir aplicativos em suas implantações Windows, consulte [Prepare for deployment with MDT](/windows/deployment/deploy-windows-mdt/prepare-for-windows-deployment-with-mdt).
