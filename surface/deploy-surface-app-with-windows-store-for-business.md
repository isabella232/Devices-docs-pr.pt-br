---
title: Implantar o aplicativo Surface com a Microsoft Store para Empresas ou a Microsoft Store para Educação (Surface)
description: Saiba como adicionar e baixar o aplicativo Surface com a Microsoft Store para Empresas ou a Microsoft Store para Educação, bem como instalar o aplicativo Surface com o PowerShell e o MDT.
keywords: surface app, app, implantação, personalizar
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
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271068"
---
# Implantar o aplicativo Surface com a Microsoft Store para Empresas e Educação

**Aplicável a**

- Surface Pro 7+
- Surface Laptop Go
- Surface Pro 7
- Surface Laptop 3
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


O aplicativo do Surface é um aplicativo leve da Microsoft Store que fornece controle de muitas configurações e opções específicas do Surface, incluindo: 

* Habilitar ou desabilitar o botão Windows no dispositivo Surface 
 

* Ajustar a sensibilidade de uma Caneta Surface 
 

* Personalizar ações de botão da Caneta Surface 
 

* Habilitar ou desabilitar os aperfeiçoamentos de áudio do Surface 
 

* Acesso rápido à documentação de suporte e informações do seu dispositivo

Os clientes que usam o Windows Update normalmente receberão o aplicativo Surface como parte das atualizações automáticas. Mas se sua organização estiver preparando imagens para implantação em seus dispositivos Surface, talvez você queira incluir o aplicativo do Surface (anteriormente chamado de Surface Hub) em seu processo de implantação e imagens em vez de exigir que os usuários de cada dispositivo individual baixem e instalem o aplicativo da Microsoft Store ou da Microsoft Store para Empresas. 

> [!NOTE]
> Este artigo não se aplica ao Surface Pro X. Para obter mais informações, consulte [Implantação, gerenciamento](surface-pro-arm-app-management.md) e manutenção do Surface Pro X

## Visão geral do aplicativo do Surface

O aplicativo do Surface está disponível como um download gratuito da [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P) Os usuários podem baixá-lo e instalá-lo da Microsoft Store, mas se sua organização usa a Microsoft Store para Empresas, você precisará adicioná-lo ao inventário da loja e possivelmente incluir o aplicativo como parte do processo de implantação do Windows. Esses processos são discutidos ao longo deste artigo. Para obter mais informações sobre a Microsoft Store para Empresas, [consulte a Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/) no Windows TechCenter. 

## Adicionar o aplicativo Surface a uma conta da Microsoft Store para Empresas 

Antes que os usuários possam instalar ou implantar um aplicativo da conta da Microsoft Store para Empresas de uma empresa, os aplicativos desejados devem primeiro ser disponibilizados e licenciados para os usuários de uma empresa. 

1. Se você ainda não tiver feito isso, crie uma [conta da Microsoft Store para Empresas.](https://www.microsoft.com/business-store) 

2. Faça logoff no portal. 

3. Habilita o licenciamento offline: clique em Gerenciar >configurações da Loja e selecione Mostrar **aplicativos licenciados** **offline** para pessoas que estão comprando na loja, conforme mostrado na Figura 1. Para obter mais informações sobre modelos de licenciamento de aplicativos da Microsoft Store para Empresas, consulte Aplicativos na [Microsoft Store para Empresas e Educação.](https://docs.microsoft.com/microsoft-store/)

   > [!div class="mx-imgBorder"]
   > ![Mostrar a caixa de seleção de aplicativos de licenças offline](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figura 1. Habilitar aplicativos para uso offline*

4. Adicione o aplicativo Surface à sua conta da Microsoft Store para Empresas seguindo este procedimento:

    * Clique no menu **Comprar.**
    
    * Na caixa de pesquisa, digite **o aplicativo Surface**e clique no ícone de pesquisa.
    
    * Depois que o aplicativo Surface for apresentado nos resultados da pesquisa, clique no ícone do aplicativo.
    
    * Você pode escolher (selecionar **Online** ou **Offline),** conforme mostrado na Figura 2.
    
      > [!div class="mx-imgBorder"]
      > ![Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Figura 2. Selecione o modo de licenciamento offline e adicione o aplicativo ao inventário*
    
    * Clique **em Offline** para selecionar o modo de licenciamento offline.
    
    * Clique **em Obter o aplicativo** para adicionar o aplicativo ao inventário da Microsoft Store para Empresas. Conforme mostrado na Figura 3, você verá uma caixa de diálogo solicitando que você confirme que os aplicativos offline podem ser implantados usando uma ferramenta de gerenciamento ou baixados da página de inventário da empresa em seu armazenamento particular.
    
      > [!div class="mx-imgBorder"]
      > ![Janela de confirmação de aplicativo licenciado offline ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figura 3. Confirmação de aplicativo licenciado offline*
      
    * Clique em **OK**.

## Baixar o aplicativo Surface de uma conta da Microsoft Store para Empresas
Depois de adicionar um aplicativo à conta da Microsoft Store para Empresas no modo Offline, você pode baixar e adicionar o aplicativo como um AppxBundle a um compartilhamento de implantação.

1. Faça logoff na conta da Microsoft Store para Empresas em https://businessstore.microsoft.com .

2. Clique **em Gerenciar >aplicativos & software.** Uma lista de todos os aplicativos da empresa é exibida, incluindo o aplicativo do Surface que você adicionou no aplicativo Adicionar Surface a uma seção de conta da [Microsoft Store](#add-surface-app-to-a-microsoft-store-for-business-account) para Empresas deste artigo.

3. Em **Ações,** clique nas reellipses (**...**) e clique em **Baixar para uso offline** para o aplicativo Surface.

4. Selecione as opções **** de **Plataforma** e Arquitetura desejadas nas seleções disponíveis para o aplicativo selecionado, conforme mostrado na Figura 4.

    > [!div class="mx-imgBorder"]
    > ![Exemplo do pacote AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Figura 4. Baixar o pacote AppxBundle para um aplicativo*
    
5. Clique **em Baixar.** O pacote AppxBundle será baixado. Certifique-se de anotar o caminho do arquivo baixado, pois você precisará disso posteriormente neste artigo.

6. Clique na opção **licença codificada** ou **não codificada.** Use a opção de licença codificada com ferramentas de gerenciamento como o Microsoft Endpoint Configuration Manager ou quando você usa o Designer de Configuração do Windows para criar um pacote de provisionamento. Selecione a opção de licença não codificada ao usar o Gerenciamento e Manutenção de Imagens de Implantação (DISM) ou soluções de implantação baseadas em imagens, incluindo o Microsoft Deployment Toolkit (MDT).

7. Clique **em Gerar** para gerar e baixar a licença do aplicativo. Certifique-se de anotar o caminho do arquivo de licença, pois você precisará disso mais adiante neste artigo.

>[!NOTE]
>Ao baixar um aplicativo para uso offline, como o aplicativo Surface, você pode notar uma seção na parte inferior da página rotulada como **estruturas necessárias.** Os computadores de destino devem ter as estruturas instaladas para que o aplicativo seja executado, portanto, talvez seja necessário repetir o processo de download para cada uma das estruturas necessárias para sua arquitetura (x86 ou x64) e também incluí-las como parte da implantação do Windows discutida mais adiante neste artigo.

A Figura 5 mostra as estruturas necessárias para o aplicativo do Surface.

> [!div class="mx-imgBorder"]
> ![Estruturas necessárias para o aplicativo do Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Figura 5. Estruturas necessárias para o aplicativo do Surface*

>[!NOTE]
>Os números de versão do aplicativo Surface e as estruturas necessárias mudarão à medida que os aplicativos são atualizados. Verifique a versão mais recente do aplicativo Surface e cada estrutura na Microsoft Store para Empresas. Sempre use o aplicativo do Surface e as versões de estrutura recomendadas, conforme fornecido pela Microsoft Store para Empresas. O uso de estruturas desatualizadas ou versões incorretas pode resultar em erros ou falhas no aplicativo.

Para baixar as estruturas necessárias para o aplicativo Surface, siga estas etapas:

1. Clique no **botão Baixar** em **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**. Isso baixa o Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Arquivo Appx para a pasta especificada.

2. Clique no **botão Baixar** em **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**. Isso baixa o arquivo Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx para a pasta especificada.

>[!NOTE]
>Somente a versão de 64 bits (x64) de cada estrutura é necessária para dispositivos Surface. Dispositivos Surface são dispositivos UEFI nativos de 64 bits e não são compatíveis com versões de 32 bits (x86) do Windows que exigiriam estruturas de 32 bits. 

## Instalar o aplicativo Surface em seu computador com o PowerShell
O procedimento a seguir provisiona o aplicativo Surface em seu computador e o disponibiliza para qualquer conta de usuário criada posteriormente no computador.

1. Usando o procedimento descrito na seção Como baixar o aplicativo Surface de uma seção de conta da [Microsoft Store para](#download-surface-app-from-a-microsoft-store-for-business-account) Empresas deste artigo, baixe o app Surface AppxBundle e o arquivo de licença. 

2. Inicie uma sessão do PowerShell com privilégios elevados.

    >[!NOTE]
    >Se você não executar o PowerShell como Administrador, a sessão não terá as permissões necessárias para instalar o aplicativo.
    
3. Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Onde `<DownloadPath>` está a pasta onde você baixou o AppxBundle e o arquivo de licença da conta da Microsoft Store para Empresas.

    Por exemplo, se você baixou os arquivos para c:\Temp, o comando executado será:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. Agora o aplicativo do Surface estará disponível no computador atual com o Windows. 

   Antes que o aplicativo do Surface seja funcional no computador em que ele foi provisionado, você também deve provisioná-lo conforme descrito anteriormente neste artigo. Para provisionar essas estruturas, use o procedimento a seguir na sessão elevada do PowerShell que você usou para provisionar o aplicativo Surface.

5. Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. Na sessão do PowerShell com privilégios elevados, copie e cole o seguinte comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Instalar o aplicativo Surface com o MDT
O procedimento a seguir usa o MDT para automatizar a instalação do aplicativo Surface no momento da implantação. O aplicativo é provisionado automaticamente pelo MDT durante a implantação e, assim, você pode usar esse processo com imagens existentes. Esse é o processo recomendado para implantar o aplicativo surface como parte de uma implantação do Windows em dispositivos Surface porque ele não reduz a compatibilidade entre plataformas da imagem do Windows.

1. Usando o procedimento descrito [anteriormente neste artigo,](#download-surface-app-from-a-microsoft-store-for-business-account)baixe o app AppxBundle do Surface e o arquivo de licença. 

2. Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem.**

3. Na página **Detalhes do** Comando do Assistente **** para Novo Aplicativo, especifique o Diretório de Trabalho padrão e, para o comando, especifique o nome de arquivo do AppxBundle, da seguinte forma: ****

   * Comando:
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Diretório de Trabalho: %DEPLOYROOT%\Applications\SurfaceApp

Para que o aplicativo do Surface funcione no computador de destino, ele também exigirá as estruturas descritas anteriormente neste artigo. Use o procedimento a seguir para importar as estruturas necessárias para o aplicativo Surface para o MDT e configurá-las como dependências.

1. Usando o procedimento descrito anteriormente neste artigo, baixe os arquivos de estrutura. Armazene cada estrutura em uma pasta separada.

2. Usando o Assistente para Novo Aplicativo no MDT Deployment Workbench, importe os arquivos baixados como um novo **Aplicativo com arquivos de origem.**

3. Na página **Detalhes do** Comando, digite o nome de arquivo de cada aplicativo que você baixou no campo **Comando** e no Diretório de Trabalho padrão.

Para configurar as estruturas como dependências do aplicativo Surface, use este processo:

1. Abra as propriedades do aplicativo Surface no MDT Deployment Workbench.

2. Clique na **guia Dependências** e em **Adicionar.**

3. Marque a caixa de seleção de cada estrutura usando o nome fornecido no Assistente para Novo Aplicativo.

Após a importação, o aplicativo Do Surface estará disponível para seleção na etapa **Aplicativos** do Assistente de Implantação do Windows. Você também pode instalar o aplicativo automaticamente, especificando-o na sequência de tarefas de implantação com este processo:

1. Abra a sequência de tarefas de implantação no MDT Deployment Workbench.

2. Adicione uma nova tarefa **instalar Aplicativo** na seção **Restaurar Estado** da implantação.

3. Selecione **Instalar um único aplicativo** e especifique o Aplicativo do **Surface** como o Aplicativo a **ser instalado.**

Para obter mais informações sobre como incluir aplicativos em suas implantações do Windows, consulte [Implantar o Windows 10 com o Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
