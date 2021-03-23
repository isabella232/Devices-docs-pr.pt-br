---
title: Configurar contas de administrador não globais no Surface Hub
description: Este artigo descreve como configurar contas de administrador não globais para gerenciar o Surface Hub e o Surface Hub 2S.
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
ms.openlocfilehash: ceac8fc1b0e168b206d937197ef404990b8e40ae
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442895"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a><span data-ttu-id="1e8cc-104">Configurar contas de administrador não globais no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1e8cc-104">Configure non Global admin accounts on Surface Hub</span></span>

<span data-ttu-id="1e8cc-105">Ao ingressar o Surface Hub v1 ou o Surface Hub 2S em um domínio do Azure AD, você pode configurar contas de administrador não globais que limitem permissões ao gerenciamento do aplicativo Configurações no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-105">When you join Surface Hub v1 or Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub.</span></span> <span data-ttu-id="1e8cc-106">Isso permite que você escopo permissões de administrador somente para o Surface Hub e impedir o acesso de administrador potencialmente indesejado em todo um domínio do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-106">This enables you to scope admin permissions for Surface Hub only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="1e8cc-107">Antes de começar, certifique-se de que o Surface Hub está ingressado no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-107">Before you begin, make sure your Surface Hub is joined to Azure AD.</span></span> <span data-ttu-id="1e8cc-108">Caso não seja, você precisará redefinir o Surface Hub e concluir o programa de instalação inicial e in-loco (OOBE), escolhendo a opção de ingressar no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-108">If not, you will need to reset Surface Hub and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="1e8cc-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="1e8cc-109">Summary</span></span> 

<span data-ttu-id="1e8cc-110">O processo de criação de contas de administrador não globais envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="1e8cc-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="1e8cc-111">No Microsoft Intune, crie um grupo de Segurança contendo os administradores designados para gerenciar o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub.</span></span>
2. <span data-ttu-id="1e8cc-112">Obtenha o SID do grupo do Azure AD usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="1e8cc-113">Criar arquivo XML contendo SID do grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="1e8cc-114">Crie um Grupo de Segurança contendo os dispositivos Surface Hub que serão gerenciados pelo grupo de Segurança de administradores não globais.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-114">Create a Security Group containing the Surface Hub devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="1e8cc-115">Crie um perfil de Configuração personalizado destinado ao grupo de segurança que contém seus dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="1e8cc-116">Criar grupos de segurança do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1e8cc-116">Create Azure AD security groups</span></span>

<span data-ttu-id="1e8cc-117">Primeiro crie um grupo de segurança que contenha as contas de administrador.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="1e8cc-118">Em seguida, crie outro grupo de segurança para dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="1e8cc-119">Criar grupo de segurança para contas de administrador</span><span class="sxs-lookup"><span data-stu-id="1e8cc-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="1e8cc-120">Entre no Intune por meio do Centro de administração do [Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)selecione **Grupos**Novo Grupo > e em Tipo  >  \*\*\*\* de grupo, selecione **Segurança.**</span><span class="sxs-lookup"><span data-stu-id="1e8cc-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="1e8cc-121">Insira um nome de grupo , por exemplo, Administradores Locais **do Surface Hub,** e selecione **Criar.**</span><span class="sxs-lookup"><span data-stu-id="1e8cc-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Criar grupo de segurança para administradores do Hub](images/sh-create-sec-group.png)

3. <span data-ttu-id="1e8cc-123">Abra o grupo, selecione **Membros**e escolha **Adicionar** membros para inserir as contas de administrador que você deseja designar como administradores não globais no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub.</span></span> <span data-ttu-id="1e8cc-124">Para saber mais sobre a criação de grupos no Intune, consulte  [Adicionar grupos para organizar usuários e dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="1e8cc-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-devices"></a><span data-ttu-id="1e8cc-125">Criar grupo de segurança para dispositivos Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1e8cc-125">Create security group for Surface Hub devices</span></span>

1. <span data-ttu-id="1e8cc-126">Repita o procedimento anterior para criar um grupo de segurança separado para dispositivos Hub; por exemplo, **dispositivos Surface Hub**.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Criar grupo de segurança para dispositivos Hub](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="1e8cc-128">Obter SID do grupo do Azure AD usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8cc-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="1e8cc-129">Iniciar o PowerShell com privilégios de conta elevados ( Executar como**Administrador**) e garantir que seu sistema está configurado para executar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="1e8cc-130">Para saber mais, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="1e8cc-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="1e8cc-131">[Instalar o módulo do Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="1e8cc-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="1e8cc-132">Entre no locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="1e8cc-133">Quando você estiver entrando em seu locatário, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="1e8cc-134">Ele solicitará que você "Digite a ID do objeto do grupo do Azure AD".</span><span class="sxs-lookup"><span data-stu-id="1e8cc-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="1e8cc-135">No Intune, selecione o grupo criado anteriormente e copie a ID do objeto, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Copiar id do objeto do grupo de segurança](images/sh-objectid.png)

6. <span data-ttu-id="1e8cc-137">Execute o seguinte commandlet para obter o SID do grupo de segurança:</span><span class="sxs-lookup"><span data-stu-id="1e8cc-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="1e8cc-138">Colar a id object no commandlet do PowerShell, pressione **Enter**e copie o SID do Grupo **do Azure AD** em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="1e8cc-139">Criar arquivo XML contendo SID do grupo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1e8cc-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="1e8cc-140">Copie o seguinte em um editor de texto:</span><span class="sxs-lookup"><span data-stu-id="1e8cc-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="1e8cc-141">Substitua o SID de espaço reservado (começando pelo S-1-12-1) pelo SID do **grupo do Azure AD** e salve o arquivo como XML; por exemplo, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="1e8cc-142">Criar perfil de configuração personalizado</span><span class="sxs-lookup"><span data-stu-id="1e8cc-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="1e8cc-143">No Endpoint Manager, selecione **Perfis**de  >  **Configuração de**  >  **Dispositivos Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="1e8cc-144">Em Plataforma, **selecione Windows 10 e posterior.**</span><span class="sxs-lookup"><span data-stu-id="1e8cc-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="1e8cc-145">Em Perfil, selecione **Personalizado**e, em seguida, selecione **Criar.**</span><span class="sxs-lookup"><span data-stu-id="1e8cc-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="1e8cc-146">Adicione um nome e uma descrição e selecione **Next.**</span><span class="sxs-lookup"><span data-stu-id="1e8cc-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="1e8cc-147">Em **Configurações configurações**  >  **OMA-URI Configurações,** selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="1e8cc-148">No painel Adicionar Linha, adicione um nome e em     **OMA-URI**, adicione a seguinte cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="1e8cc-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="1e8cc-149">Em Tipo de dados, selecione XML de **cadeia** de caracteres e navegue até abrir o arquivo XML criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![carregar arquivo de configuração xml do administrador local](images/sh-local-admin-config.png)

7. <span data-ttu-id="1e8cc-151">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-151">Click **Save**.</span></span>
8. <span data-ttu-id="1e8cc-152">Clique **em Selecionar grupos para incluir** e escolher o grupo de segurança criado [anteriormente](#create-security-group-for-surface-hub-devices) (**dispositivos Surface Hub**).</span><span class="sxs-lookup"><span data-stu-id="1e8cc-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="1e8cc-153">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-153">Click **Next.**</span></span>
9. <span data-ttu-id="1e8cc-154">Em Regras de Aplicabilidade, adicione uma Regra, se desejado.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="1e8cc-155">Caso contrário, selecione **Próximo** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="1e8cc-156">Para saber mais sobre perfis de configuração personalizados usando cadeias de caracteres OMA-URI, consulte Usar configurações personalizadas para [dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="1e8cc-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub"></a><span data-ttu-id="1e8cc-157">Administradores não globais que gerenciam o Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1e8cc-157">Non Global admins managing Surface Hub</span></span>

<span data-ttu-id="1e8cc-158">Membros do grupo de Segurança de **Administradores** Locais do Surface Hub agora podem entrar no aplicativo Configurações no Surface Hub e gerenciar configurações.</span><span class="sxs-lookup"><span data-stu-id="1e8cc-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub and manage settings.</span></span>
