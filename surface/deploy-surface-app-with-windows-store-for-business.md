---
title: Implantar o aplicativo Surface com a Microsoft Store para empresas ou a Microsoft Store para educação (Surface)
description: Saiba como adicionar e baixar o aplicativo Surface na Microsoft Store para empresas ou Microsoft Store para educação, bem como instalar o aplicativo Surface com o PowerShell e o MDT.
keywords: aplicativo Surface, aplicativo, implantação, personalizar
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
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830383"
---
# Implantar o aplicativo Surface com a Microsoft Store para empresas e educação

**Aplicável a**

- Surface Pro 7
- Laptop Surface 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Surface Go com LTE
- Surface Book 2
- Surface Pro com LTE Avançado (Model 1807)
- Surface Pro (Model 1796)
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3


O aplicativo Surface é um aplicativo da Microsoft Store leve que fornece controle de muitas configurações e opções específicas da superfície, incluindo: 

* Habilitar ou desabilitar o botão Windows no dispositivo Surface 
 

* Ajustar a sensibilidade de uma Caneta Surface 
 

* Personalizar ações de botão da Caneta Surface 
 

* Habilitar ou desabilitar os aperfeiçoamentos de áudio do Surface 
 

* Acesso rápido à documentação de suporte e informações para o seu dispositivo

Os clientes que usam o Windows Update normalmente recebem o aplicativo Surface como parte das atualizações automáticas. Mas se a sua organização estiver preparando imagens para implantação em seus dispositivos Surface, talvez você queira incluir o aplicativo Surface (antes chamado de Surface Hub) no seu processo de criação de imagens e implantação em vez de exigir que os usuários de cada dispositivo específico baixem e instalem o aplicativo da Microsoft Store ou da Microsoft Store para empresas. 

> [!NOTE]
> Este artigo não se aplica ao Surface Pro X. Para obter mais informações, consulte [implantação, gerenciamento e manutenção do Surface Pro X](surface-pro-arm-app-management.md)

## Visão geral do aplicativo Surface

O aplicativo Surface está disponível como um download gratuito na [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P). Os usuários podem baixar e instalá-lo na Microsoft Store, mas se a sua organização usa a Microsoft Store para empresas, você precisará adicioná-lo ao estoque da sua loja e, possivelmente, incluir o aplicativo como parte do processo de implantação do Windows. Esses processos são discutidos em todo este artigo. Para obter mais informações sobre a Microsoft Store para empresas, consulte [Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/) no TechCenter do Windows. 

## Adicionar aplicativo Surface a uma conta da Microsoft Store para empresas 

Antes que os usuários possam instalar ou implantar um aplicativo da conta da Microsoft Store para empresas de uma empresa, os aplicativos desejados devem primeiro ser disponibilizados e licenciados para os usuários de uma empresa. 

1. Se você ainda não tiver feito isso, crie uma [conta da Microsoft Store para empresas](https://www.microsoft.com/business-store). 

2. Faça logon no Portal. 

3. Habilitar o licenciamento offline: clique em **configurações da loja de gerenciar->** e marque a caixa de seleção **Mostrar aplicativos licenciados offline para as pessoas comprando na loja** , conforme mostrado na Figura 1. Para obter mais informações sobre os modelos de licenciamento do aplicativo Microsoft Store para empresas, consulte [aplicativos na Microsoft Store para empresas e instituições de ensino](https://docs.microsoft.com/microsoft-store/).<br/> <br/>
   ![Caixa de seleção Mostrar aplicativos de licenças offline](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figura 1. Habilitar aplicativos para uso offline*

4. Adicione o aplicativo Surface à sua conta da Microsoft Store para empresas seguindo este procedimento:
    * Clique no menu **comprar** .
    * Na caixa de pesquisa, digite **aplicativo Surface**e, em seguida, clique no ícone Pesquisar.
    * Após o aplicativo Surface ser apresentado nos resultados da pesquisa, clique no ícone do aplicativo.
    * Você verá uma opção (selecione **online** ou **offline**), conforme mostrado na Figura 2.<br/><br/>
    
    ![Selecionar o modo de licenciamento offline e adicionar o aplicativo ao seu inventário](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *Figura 2. Selecionar o modo de licenciamento offline e adicionar o aplicativo ao seu inventário*
    
    * Clique em **offline** para selecionar o modo de licenciamento offline.
    * Clique em **obter o aplicativo** para adicionar o aplicativo ao seu inventário da Microsoft Store para empresas. Conforme mostrado na Figura 3, você verá uma caixa de diálogo que solicita que você confirme que os aplicativos offline podem ser implantados usando uma ferramenta de gerenciamento ou baixados da página de inventário da empresa em seu repositório particular.
    
    ![Janela de confirmação do aplicativo licenciado offline](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *Figura 3. Confirmação de aplicativo licenciada offline*
    * Clique em **OK**.

## Baixar o aplicativo Surface de uma conta da Microsoft Store para empresas
Depois de adicionar um aplicativo à conta da Microsoft Store para empresas no modo offline, você pode baixar e adicionar o aplicativo como uma AppxBundle para um compartilhamento de implantação.
1. Faça logon na conta da Microsoft Store para empresas em https://businessstore.microsoft.com .
2. Clique em **Manage->Apps & software**. Uma lista de todos os aplicativos da sua empresa é exibida, incluindo o aplicativo Surface que você adicionou na seção [Adicionar aplicativo Surface a uma conta da Microsoft Store para empresas](#add-surface-app-to-a-microsoft-store-for-business-account) deste artigo.
3. Em **ações**, clique nas reticências (**...**) e, em seguida, clique em **baixar para uso offline** do aplicativo Surface.
4. Selecione as opções de **plataforma** e **arquitetura** desejadas nas seleções disponíveis para o aplicativo selecionado, como mostrado na Figura 4.

    ![Exemplo do pacote AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *Figura 4. Baixar o pacote AppxBundle para um aplicativo*
5. Clique em **baixar**. O pacote AppxBundle será baixado. Certifique-se de anotar o caminho do arquivo baixado porque você precisará mais tarde neste artigo.
6. Clique na opção **licença codificada** ou **licença não codificada** . Use a opção de licença codificada com ferramentas de gerenciamento como o Microsoft Endpoint Configuration Manager ou use o designer de configuração do Windows para criar um pacote de provisionamento. Selecione a opção licença não codificada quando você usar o DISM (gerenciamento e manutenção de imagens de implantação) ou soluções de implantação com base em imagens, incluindo o kit de ferramentas de implantação da Microsoft (MDT).
7. Clique em **gerar** para gerar e baixar a licença do aplicativo. Certifique-se de anotar o caminho do arquivo de licença porque você precisará mais tarde neste artigo.

>[!NOTE]
>Ao baixar um aplicativo para uso offline, como o aplicativo Surface, você pode observar uma seção na parte inferior da página rotulada **estruturas obrigatórias**. Seus computadores de destino devem ter estruturas instaladas para que o aplicativo seja executado, portanto, talvez seja necessário repetir o processo de download para cada um dos frameworks obrigatórios para a sua arquitetura (x86 ou x64) e também incluí-los como parte da sua implantação do Windows abordada posteriormente neste artigo.

A Figura 5 mostra as estruturas necessárias para o aplicativo Surface.

![Estruturas obrigatórias para o aplicativo Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*Figura 5. Estruturas obrigatórias para o aplicativo Surface*

>[!NOTE]
>Os números de versão do aplicativo Surface e das estruturas obrigatórias serão alterados à medida que os aplicativos forem atualizados. Verifique a última versão do aplicativo Surface e cada estrutura na Microsoft Store para empresas. Sempre use o aplicativo Surface e versões de estrutura recomendadas conforme fornecido pela Microsoft Store para empresas. Usar estruturas desatualizadas ou as versões incorretas pode resultar em erros ou falhas do aplicativo.

Para baixar as estruturas necessárias para o aplicativo Surface, siga estas etapas:
1. Clique no botão **baixar** em **Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe**. Isso baixa o Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe. Arquivo Appx para a pasta especificada.
2. Clique no botão **baixar** em **Microsoft. net. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe**. Isso faz o download do arquivo Microsoft. NET. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe. Appx para a pasta especificada.

>[!NOTE]
>Somente a versão de 64 bits (x64) de cada estrutura é necessária para os dispositivos Surface. Os dispositivos de superfície são dispositivos UEFI nativos de 64 bits e não são compatíveis com versões de 32 bits (x86) do Windows que exigem estruturas de 32 bits. 

## Instalar o aplicativo Surface em seu computador com o PowerShell
O procedimento a seguir provisiona o aplicativo Surface para o seu computador e o disponibiliza para qualquer conta de usuário criada no computador posteriormente.
1. Usando o procedimento descrito na seção [como baixar o aplicativo Surface a partir de uma conta da Microsoft Store para empresas](#download-surface-app-from-a-microsoft-store-for-business-account) deste artigo, baixe o aplicativo Surface AppxBundle e o arquivo de licença. 
2. Inicie uma sessão do PowerShell com privilégios elevados.

    >[!NOTE]
    >Se você não executar o PowerShell como administrador, a sessão não terá as permissões necessárias para instalar o aplicativo.
    
3. Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: 
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Onde `<DownloadPath>` é a pasta onde você baixou o AppxBundle e o arquivo de licença da conta da Microsoft Store para empresas.

    Por exemplo, se você tiver baixado os arquivos para c:\Temp, o comando que executar será:
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
