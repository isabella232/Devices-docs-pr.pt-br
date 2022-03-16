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
ms.date: 02/15/2022
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 429a7c84605167aa5129999f516c18d17ee30e65
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449293"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Configurar contas administrativas não globais no Surface Hub

O Windows 10 Team 2020 Update adiciona suporte para configurar contas de administrador não globais que limitam permissões ao gerenciamento do aplicativo Configurações em dispositivos Surface Hub ingressados em um domínio do Azure AD. Isso permite que você escopo permissões de administrador somente Surface Hub e impedir o acesso de administrador potencialmente indesejado em todo um domínio do Azure AD inteiro. Antes de começar, certifique-se de que seu Surface Hub está ingressado no Azure AD e no Intune. Caso não seja, você precisará redefinir Surface Hub e concluir o programa de instalação OOBE (OOBE) de primeira vez, escolhendo a opção de ingressar no Azure AD.

Windows 10 Team atualização 2020 2 adiciona suporte para o [provedor de serviços de configuração LocalUsersAndGroups](/windows/client-management/mdm/policy-csp-localusersandgroups). Isso substitui o [CSP RestrictedGroups](/windows/client-management/mdm/policy-csp-restrictedgroups), que permanece disponível, mas não é mais recomendado, conforme explicado a seguir.

## <a name="summary"></a>Resumo

O processo de criação de contas de administrador não globais envolve as seguintes etapas:

1. Em Microsoft Intune, crie um grupo de Segurança contendo os administradores designados para gerenciar Surface Hub.
2. Obtenha o SID do grupo do Azure AD usando o PowerShell.
3. Crie um arquivo XML que contenha SID do grupo do Azure AD.
4. Crie um Grupo de Segurança que contenha os Surface Hub que o grupo de Segurança de administradores não globais gerenciará. 
5. Crie um perfil de Configuração personalizado destinado ao grupo de segurança que contém seus Surface Hub dispositivos.

## <a name="create-azure-ad-security-groups"></a>Criar grupos de segurança do Azure AD

Primeiro, crie um grupo de segurança que contenha as contas de administrador. Em seguida, crie outro grupo de segurança para Surface Hub dispositivos.  

### <a name="create-security-group-for-admin-accounts"></a>Criar grupo de segurança para contas de administrador

1. Entre no Intune por meio do Microsoft Endpoint Manager [de](https://go.microsoft.com/fwlink/?linkid=2109431) administração, selecione **GruposNovo** >  Grupo > e em Tipo de grupo, selecione **Segurança.******
2. Insira um nome de grupo , por exemplo, **Surface Hub Administradores Locais** e selecione **Criar.**

     ![Criar grupo de segurança para administradores do Hub.](images/sh-create-sec-group.png)

3. Abra o grupo, selecione **Membros** e escolha **Adicionar** membros para inserir as contas de administrador que você deseja designar como administradores não globais no Surface Hub. Para saber mais sobre como criar grupos no Intune, consulte  [Adicionar grupos para organizar usuários e dispositivos](/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>Criar grupo de segurança para Surface Hub dispositivos

1. Repita o procedimento anterior para criar um grupo de segurança separado para dispositivos Hub; por exemplo, **Surface Hub dispositivos**.

     ![Crie um grupo de segurança para dispositivos Hub.](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Obter SID do grupo do Azure AD usando o PowerShell

1. Iniciar o PowerShell com privilégios de conta elevados (**Executar como Administrador**) e garantir que seu sistema está configurado para executar scripts do PowerShell. Para saber mais, consulte [Sobre políticas de execução](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).
2. [Instalar Azure PowerShell módulo](/powershell/azure/install-az-ps).
3. Entre no locatário do Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. Ao entrar no locatário, execute o seguinte comando. Ele solicitará que você "Digite a ID do objeto do grupo do Azure AD".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. No Intune, selecione o grupo criado anteriormente e copie a ID do objeto, conforme mostrado na figura a seguir.

     ![Copy Object id of security group.](images/sh-objectid.png)

6. Execute o seguinte commandlet para obter o SID do grupo de segurança:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. Colar a id object no comando do PowerShell, pressione **Enter** e copie o SID do Grupo **do Azure AD** em um editor de texto.

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Criar arquivo XML contendo SID do grupo do Azure AD

1. Copie o seguinte em um editor de texto:

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. Substitua o SID de espaço reservado (começando pelo S-1-12-1) pelo **SID do grupo do Azure AD** e salve o arquivo como XML; por exemplo, **aad-local-admin.xml**.

      > [!NOTE]
      > Embora os grupos sejam especificados por meio do SID, se você quiser adicionar usuários do Azure diretamente, especifique seus UPNs (Nomes principais de usuário) nesse formato: `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>Criar perfil de configuração personalizado

1. Em Endpoint Manager, selecione **DevicesConfiguration****** >  **profilesCriar** >  perfil.
2. Em Plataforma, **selecione Windows 10 e posterior.** Em Perfil, selecione **Personalizado** e selecione **Criar.**
3. Adicione um nome e uma descrição e selecione **Next.**
4. Em **Configuração** **configuraçõesOMA-URI** >  Configurações, selecione **Adicionar**.
5. No painel Adicionar Linha, adicione um nome e, em     **OMA-URI**, adicione a seguinte cadeia de caracteres:

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

> [!NOTE]
> A **configuração da política RestrictedGroups/ConfigureGroupMembership** também permite configurar membros (usuários ou AAD grupos) para um grupo Windows 10 local. No entanto, ele só permite uma substituição completa dos grupos existentes com os novos membros. Não é possível adicionar ou remover membros seletivamente.  Disponível na Windows 10 Team 2020 Update 2, é recomendável usar a configuração de política **LocalUsersandGroups** em vez da configuração de política RestrictedGroups. A aplicação das duas configurações de política Surface Hub não é compatível e pode gerar resultados imprevisíveis.

6. Em Tipo de dados, selecione **XML de cadeia** de caracteres e navegue até abrir o arquivo XML criado na etapa anterior.

     ![carregar arquivo de configuração xml de administrador local.](images/sh-local-admin-config.png)

7. Clique em **Salvar**.
8. Clique **em Selecionar grupos para incluir** e escolher o grupo [de segurança criado anteriormente](#create-security-group-for-surface-hub-devices) (**Surface Hub dispositivos**). Clique em **Avançar**.
9. Em Regras de Aplicabilidade, adicione uma Regra, se desejado. Caso contrário, selecione **Próximo** e, em seguida, selecione **Criar**.

Para saber mais sobre perfis de configuração personalizados usando cadeias de caracteres OMA-URI, consulte [Use custom settings for Windows 10 devices in Intune](/mem/intune/configuration/custom-settings-windows-10).

## <a name="non-global-admins-managing-surface-hub"></a>Administradores não globais gerenciando Surface Hub

Membros do grupo **Surface Hub** Segurança de Administradores Locais agora podem entrar no aplicativo Configurações no Surface Hub e gerenciar configurações.

> [!IMPORTANT]
> O acesso padrão de administradores globais ao aplicativo Configurações é removido (a menos que eles também sejam membros desse novo grupo de segurança).
