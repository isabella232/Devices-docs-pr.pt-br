---
title: Configurar contas administrativas não globais no Surface Hub
description: Este artigo descreve como configurar contas de administrador não globais para gerenciar Surface Hub e Surface Hub 2S.
keywords: Surface Hub, Surface Hub v1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/22/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 03359a7d8ea028a8094c064c1fcb82cc9a53fe6a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576761"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Configurar contas administrativas não globais no Surface Hub

O Windows 10 Team 2020 Update adiciona suporte para configurar contas de administrador não globais que limitam permissões ao gerenciamento do aplicativo Configurações em dispositivos Surface Hub ingressados em um domínio do Azure AD. Isso permite que você escopo permissões de administrador somente Surface Hub e impedir o acesso de administrador potencialmente indesejado em todo um domínio do Azure AD. Antes de começar, certifique-se de que seu Surface Hub está ingressado no Azure AD e ingresse automaticamente no Intune. Caso não seja, você precisará redefinir Surface Hub e concluir o programa de instalação OOBE (OOBE) de primeira vez, escolhendo a opção de ingressar no Azure AD.

## <a name="summary"></a>Resumo 

O processo de criação de contas de administrador não globais envolve as seguintes etapas: 

1. Em Microsoft Intune, crie um grupo de Segurança contendo os administradores designados para gerenciar Surface Hub.
2. Obtenha o SID do grupo do Azure AD usando o PowerShell.
3. Criar arquivo XML contendo SID do grupo do Azure AD.
4. Crie um Grupo de Segurança contendo os Surface Hub que serão gerenciados pelo grupo de Segurança de administradores não globais.
5. Crie um perfil de Configuração personalizado destinado ao grupo de segurança que contém seus Surface Hub dispositivos. 


## <a name="create-azure-ad-security-groups"></a>Criar grupos de segurança do Azure AD

Primeiro crie um grupo de segurança que contenha as contas de administrador. Em seguida, crie outro grupo de segurança para Surface Hub dispositivos.  

### <a name="create-security-group-for-admin-accounts"></a>Criar grupo de segurança para contas de administrador

1. Entre no Intune por meio do Microsoft Endpoint Manager [de](https://go.microsoft.com/fwlink/?linkid=2109431)administração, selecione **Grupos**Novo Grupo > e em Tipo  >  **** de grupo, selecione **Segurança.** 
2. Insira um nome de grupo , por exemplo, **Surface Hub Administradores Locais** e selecione **Criar.** 

     ![Criar grupo de segurança para administradores do Hub](images/sh-create-sec-group.png)

3. Abra o grupo, selecione **Membros**e escolha **Adicionar** membros para inserir as contas de administrador que você deseja designar como administradores não globais no Surface Hub. Para saber mais sobre a criação de grupos no Intune, consulte  [Adicionar grupos para organizar usuários e dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>Criar grupo de segurança para Surface Hub dispositivos

1. Repita o procedimento anterior para criar um grupo de segurança separado para dispositivos Hub; por exemplo, **Surface Hub dispositivos**. 

     ![Criar grupo de segurança para dispositivos Hub](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Obter SID do grupo do Azure AD usando o PowerShell

1. Iniciar o PowerShell com privilégios de conta elevados ( Executar como**Administrador**) e garantir que seu sistema está configurado para executar scripts do PowerShell. Para saber mais, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Instalar Azure PowerShell módulo](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Entre no locatário do Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. Quando você estiver entrando em seu locatário, execute o seguinte comando. Ele solicitará que você "Digite a ID do objeto do grupo do Azure AD".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. No Intune, selecione o grupo criado anteriormente e copie a ID do objeto, conforme mostrado na figura a seguir. 

     ![Copiar id do objeto do grupo de segurança](images/sh-objectid.png)

6. Execute o seguinte commandlet para obter o SID do grupo de segurança:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Colar a id object no commandlet do PowerShell, pressione **Enter**e copie o SID do Grupo **do Azure AD** em um editor de texto. 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Criar arquivo XML contendo SID do grupo do Azure AD

1. Copie o seguinte em um editor de texto: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```
      > [!IMPORTANT]
      > Não remova o membro do Administrador padrão do arquivo XML.

2. Substitua o SID de espaço reservado (começando pelo S-1-12-1) pelo SID do **grupo do Azure AD** e salve o arquivo como XML; por exemplo, **aad-local-admin.xml**. 

## <a name="create-custom-configuration-profile"></a>Criar perfil de configuração personalizado

1. Em Endpoint Manager, selecione **Perfis**de  >  **Configuração de**  >  **Dispositivos Criar perfil**. 
2. Em Plataforma, **selecione Windows 10 e posterior.** Em Perfil, selecione **Personalizado**e, em seguida, selecione **Criar.**
3. Adicione um nome e uma descrição e selecione **Next.**
4. Em **Configuração configurações**  >  **OMA-URI Configurações**, selecione **Adicionar**.
5. No painel Adicionar Linha, adicione um nome e em     **OMA-URI**, adicione a seguinte cadeia de caracteres: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. Em Tipo de dados, selecione XML de **cadeia** de caracteres e navegue até abrir o arquivo XML criado na etapa anterior. 

     ![carregar arquivo de configuração xml do administrador local](images/sh-local-admin-config.png)

7. Clique em **Salvar**.
8. Clique **em Selecionar grupos para incluir** e escolher o grupo de segurança [criado](#create-security-group-for-surface-hub-devices) anteriormente (**Surface Hub dispositivos**). Clique em **Avançar**.
9. Em Regras de Aplicabilidade, adicione uma Regra, se desejado. Caso contrário, selecione **Próximo** e selecione **Criar**.

Para saber mais sobre perfis de configuração personalizados usando cadeias de caracteres OMA-URI, consulte [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).


## <a name="non-global-admins-managing-surface-hub"></a>Administradores não globais gerenciando Surface Hub

Membros do grupo **Surface Hub** Segurança de Administradores Locais agora podem entrar no aplicativo Configurações no Surface Hub e gerenciar configurações.

> [!IMPORTANT]
> O acesso padrão de administradores globais ao aplicativo Configurações é removido (a menos que eles também sejam membros desse novo grupo de segurança).
