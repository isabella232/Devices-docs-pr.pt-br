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
ms.openlocfilehash: be6a6c75155b3c45ae9dda9dd2726033411100c4
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497685"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Configurar contas administrativas não globais no Surface Hub

A atualização Windows 10 Team 2020 adiciona suporte para configurar contas de administrador não globais que limitam permissões ao gerenciamento do aplicativo Configurações em dispositivos Surface Hub ingressados em um domínio Azure AD. Isso permite definir o escopo de permissões de administrador somente para Surface Hub e impedir o acesso de administrador potencialmente indesejado em todo o Azure AD domínio. Antes de começar, verifique se o Surface Hub está ingressado no Azure AD e Intune registrado automaticamente. Caso contrário, você precisará redefinir o Surface Hub e concluir o programa de configuração OOBE (primeiro a ser usado), escolhendo a opção de ingressar no Azure AD.

Windows 10 Team Atualização 2 de 2020 adiciona suporte para o provedor de serviços de configuração [LocalUsersAndGroups](/windows/client-management/mdm/policy-csp-localusersandgroups). Isso substitui o [CSP RestrictedGroups](/windows/client-management/mdm/policy-csp-restrictedgroups), que permanece disponível, mas não é mais recomendado, conforme explicado abaixo.

## <a name="summary"></a>Resumo

O processo de criação de contas de administrador não globais envolve as seguintes etapas:

1. Em Microsoft Intune, crie um grupo de segurança que contém os administradores designados para gerenciar Surface Hub.
2. Obtenha Azure AD SID de Grupo usando o PowerShell.
3. Crie um arquivo XML que contenha Azure AD SID do Grupo.
4. Crie um Grupo de Segurança que contenha Surface Hub dispositivos que o grupo de segurança de administradores não globais gerenciará. 
5. Crie um perfil de Configuração personalizado direcionado ao grupo de segurança que contém seus Surface Hub dispositivos.

## <a name="create-azure-ad-security-groups"></a>Criar Azure AD grupos de segurança

Primeiro, crie um grupo de segurança que contenha as contas de administrador. Em seguida, crie outro grupo de segurança para Surface Hub dispositivos.  

### <a name="create-security-group-for-admin-accounts"></a>Criar grupo de segurança para contas de administrador

1. Entre no Intune por meio do centro de administração [do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **GroupsNew** >  **Group** > e, em Tipo de grupo, selecione **Segurança.**
2. Insira um nome de grupo – por exemplo, **Surface Hub Administradores** Locais – e selecione **Criar.**

     ![Crie um grupo de segurança para administradores do Hub.](images/sh-create-sec-group.png)

3. Abra o grupo, selecione **Membros** e escolha Adicionar **** membros para inserir as contas de administrador que você deseja designar como administradores não globais Surface Hub. Para saber mais sobre como criar grupos no Intune, consulte [Adicionar grupos para organizar usuários e dispositivos](/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>Criar um grupo de segurança para Surface Hub dispositivos

1. Repita o procedimento anterior para criar um grupo de segurança separado para dispositivos Hub; por exemplo, **Surface Hub dispositivos**.

     ![Crie um grupo de segurança para dispositivos Hub.](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Obter Azure AD SID de Grupo usando o PowerShell

1. Inicie o PowerShell com privilégios de conta com privilégios **elevados (Executar** como Administrador) e verifique se o sistema está configurado para executar scripts do PowerShell. Para saber mais, consulte [Sobre políticas de execução](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).
2. [Instale Azure PowerShell módulo](/powershell/azure/install-az-ps).
3. Entre em seu locatário Azure AD cliente.

    ```powershell
    Connect-AzureAD
    ```

4. Quando você estiver conectado ao seu locatário, execute o commandlet a seguir. Ele solicitará que você "Digite a ID do objeto do Azure AD Grupo".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. Em Intune, selecione o grupo criado anteriormente e copie a ID do objeto, conforme mostrado na figura a seguir.

     ![Copiar id de objeto do grupo de segurança.](images/sh-objectid.png)

6. Execute o seguinte commandlet para obter o SID do grupo de segurança:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. Cole a ID do objeto no commandlet do PowerShell, pressione **Enter** e copie o **SID Azure AD Grupo** em um editor de texto.

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Criar arquivo XML que contém Azure AD SID do grupo

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
2. Substitua o SID de espaço reservado (começando com S-1-12-1) pelo SID do grupo **Azure AD** e salve o arquivo como XML; por exemplo, **aad-local-admin.xml**.

      > [!NOTE]
      > Embora os grupos deverão ser especificados por meio de seu SID, se você quiser adicionar usuários do Azure diretamente, especifique seus UPNs (Nomes UpNs) neste formato: `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>Criar perfil de configuração personalizada

1. Em Endpoint Manager, selecione **DevicesConfiguration****** >  **profilesCreate** >  profile.
2. Em Plataforma, selecione **Windows 10 e posterior.** Em Perfil, selecione **TemplatesCustomCreate** > **** > **.**
3. Adicione um nome e uma descrição e selecione **Avançar.**
4. Em **Configuração de configuração** >  **de Configurações URI**, selecione **Adicionar**.
5. No painel Adicionar Linha, adicione um nome e, em     **OMA-URI**, adicione a seguinte cadeia de caracteres:

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

   > [!NOTE]
   > A **configuração da política RestrictedGroups/ConfigureGroupMembership** também permite que você configure membros (usuários ou AAD grupos) para um grupo Windows 10 local. No entanto, ele só permite uma substituição completa dos grupos existentes com os novos membros. Você não pode adicionar ou remover membros seletivamente.  Disponível no Windows 10 Team Atualização 2 de 2020, é recomendável usar a configuração de política **LocalUsersandGroups** em vez da configuração de política RestrictedGroups. Não há suporte para a aplicação de ambas as configurações Surface Hub política e pode gerar resultados imprevisíveis.

6. Em Tipo de dados, selecione **CADEIA DE CARACTERES XML** e navegue para abrir o arquivo XML criado na etapa anterior.

     ![carregar arquivo de configuração xml do administrador local.](images/sh-local-admin-config.png)

7. Clique em **Salvar**.
8. Clique **em Selecionar grupos para incluir** e escolha o grupo [de segurança criado anteriormente](#create-security-group-for-surface-hub-devices) (**Surface Hub dispositivos**). Clique em **Avançar**.
9. Em regras de aplicabilidade, adicione uma regra, se desejado. Caso contrário, **selecione Avançar** e, em **seguida, selecione Criar**.

Para saber mais sobre perfis de configuração personalizados usando cadeias de caracteres OMA-URI, consulte Usar configurações [personalizadas para Windows 10 dispositivos Intune](/mem/intune/configuration/custom-settings-windows-10).

## <a name="non-global-admins-managing-surface-hub"></a>Administradores não globais que gerenciam Surface Hub

Os membros do **grupo Surface Hub** segurança de administradores locais agora podem entrar no aplicativo Configurações no Surface Hub e gerenciar configurações.

> [!IMPORTANT]
> O acesso padrão de administradores globais ao aplicativo Configurações é removido (a menos que eles também sejam membros desse novo grupo de segurança).
