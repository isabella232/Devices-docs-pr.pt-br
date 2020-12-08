---
title: Configurar contas de administrador não globais no Surface Hub 2S
description: Este artigo descreve como configurar contas de administração não globais para gerenciar o Surface Hub 2S.
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196780"
---
# Configurar contas de administrador não globais no Surface Hub 2S

Ao participar do Surface Hub 2S em um domínio do Azure AD, você pode configurar contas de administrador não globais que limitam as permissões ao gerenciamento do aplicativo configurações no Surface Hub 2S. Isso permite que você deescopo as permissões de administrador para Surface Hub 2S apenas e impedir o acesso de administradores potencialmente indesejados a todo o domínio do Azure AD. Antes de começar, verifique se o Surface Hub 2S está associado ao Azure AD. Caso contrário, você precisará redefinir o Surface Hub 2S e concluir o programa de instalação da primeira vez, de fora da caixa (OOBE), escolhendo a opção para participar do Azure AD.

## Resumo 

O processo de criação de contas de administrador não globais envolve as seguintes etapas: 

1. No Microsoft Intune, crie um grupo de segurança contendo os administradores designados para gerenciar o Surface Hub 2S.
2. Obtenha o SID do grupo do Azure AD usando o PowerShell.
3. Criar arquivo XML contendo o SID do grupo do Azure AD.
4. Crie um grupo de segurança contendo os dispositivos Surface Hub 2S que serão gerenciados pelo grupo de segurança não global administradores.
5. Crie um perfil de configuração personalizado que direcionará o grupo de segurança que contém os dispositivos Surface Hub 2S. 


## Criar grupos de segurança do Azure AD

Primeiro, crie um grupo de segurança contendo as contas de administrador. Em seguida, crie outro grupo de segurança para dispositivos Surface Hub.  

### Criar grupo de segurança para contas de administração

1. Entre no Intune por meio do [centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **grupos**  >  **novo grupo** > e em tipo de grupo, selecione **segurança.** 
2. Insira um nome de grupo--por exemplo, **Administradores locais do Surface Hub** --e, em seguida, selecione **criar.** 

     ![Criar grupo de segurança para administradores de Hub](images/sh-create-sec-group.png)

3. Abra o grupo, selecione **Membros**e, em seguida, escolha **adicionar membros** para inserir as contas de administrador que você deseja designar como administradores não globais no Surface Hub 2s. Para saber mais sobre como criar grupos no Intune, consulte  [Adicionar grupos para organizar usuários e dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

### Criar grupo de segurança para dispositivos Surface Hub 2S

1. Repita o procedimento anterior para criar um grupo de segurança separado para dispositivos Hub; por exemplo, **dispositivos Surface Hub**. 

     ![Criar grupo de segurança para dispositivos Hub](images/sh-create-sec-group-devices.png) 

## Obter SID do grupo do Azure AD usando o PowerShell

1. Inicie o PowerShell com privilégios de conta elevada (**Executar como administrador**) e verifique se o sistema está configurado para executar scripts do PowerShell. Para saber mais, consulte [sobre as políticas de execução](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Instale o módulo do PowerShell do PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Entre em seu locatário do Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. Quando estiver conectado ao seu locatário, execute o commandlet a seguir. Ele solicitará que você "digite a ID do objeto do seu grupo do Azure AD".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. No Intune, selecione o grupo que você criou anteriormente e copie a identificação do objeto, conforme mostrado na figura a seguir. 

     ![Copiar ID de objeto do grupo de segurança](images/sh-objectid.png)

6. Execute o commandlet a seguir para obter o SID do grupo de segurança:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Cole a ID do objeto no próprio cmdlet do PowerShell, pressione **Enter**e copie o **SID do grupo do Azure ad** em um editor de texto. 

## Criar arquivo XML contendo o SID do grupo do Azure AD

1. Copie o seguinte em um editor de texto: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. Substitua o SID do espaço reservado (começando com S-1-12-1) pelo **SID do grupo do Azure ad** e salve o arquivo como XML; por exemplo, **aad-local-admin.xml**. 

## Criar perfil de configuração personalizado

1. No Endpoint Manager, selecione os perfis de configuração de **dispositivos**  >  **Configuration profiles**  >  **Criar perfil**. 
2. Em plataforma, selecione **Windows 10 e posterior.** Em perfil, selecione **personalizado**e, em seguida, selecione **criar.**
3. Adicione um nome e uma descrição e selecione **Avançar.**
4. Em **configurações**  >  **OMA-URI**configurações, selecione **Adicionar**.
5. No painel Adicionar linha, adicione um nome e, em     **OMA-URI**, adicione a seguinte cadeia de caracteres: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. Em tipo de dados, selecione **cadeia de caracteres XML** e navegue para abrir o arquivo XML que você criou na etapa anterior. 

     ![carregar o arquivo de configuração XML do administrador local](images/sh-local-admin-config.png)

7. Clique em **Salvar**.
8. Clique em **Selecionar grupos para incluir** e escolher o [grupo de segurança que você criou anteriormente](#create-security-group-for-surface-hub-2s-devices) (**dispositivos Surface Hub**). Clique em **Avançar**.
9. Em regras de aplicabilidade, adicione uma regra, se desejar. Caso contrário, selecione **Avançar** e, em seguida, selecione **criar**.

Para saber mais sobre perfis de configuração personalizados usando cadeias de caracteres do OMA-URI, consulte [usar configurações personalizadas para dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).


## Administradores não globais que gerenciam o Surface Hub 2S

Os membros do grupo de segurança **Administradores locais do Surface Hub** podem agora entrar no aplicativo configurações no Surface Hub 2S e gerenciar as configurações.
