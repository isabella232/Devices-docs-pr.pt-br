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
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a><span data-ttu-id="e375c-104">Configurar contas administrativas não globais no Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e375c-104">Configure non Global admin accounts on Surface Hub</span></span>

<span data-ttu-id="e375c-105">O Windows 10 Team 2020 Update adiciona suporte para configurar contas de administrador não globais que limitam permissões ao gerenciamento do aplicativo Configurações em dispositivos Surface Hub ingressados em um domínio do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e375c-105">The Windows 10 Team 2020 Update adds support for configuring non Global admin accounts that limit permissions to management of the Settings app on Surface Hub devices joined to an Azure AD domain.</span></span> <span data-ttu-id="e375c-106">Isso permite que você escopo permissões de administrador somente Surface Hub e impedir o acesso de administrador potencialmente indesejado em todo um domínio do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e375c-106">This enables you to scope admin permissions for Surface Hub only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="e375c-107">Antes de começar, certifique-se de que seu Surface Hub está ingressado no Azure AD e ingresse automaticamente no Intune.</span><span class="sxs-lookup"><span data-stu-id="e375c-107">Before you begin, make sure your Surface Hub is joined to Azure AD and Intune auto-enrolled.</span></span> <span data-ttu-id="e375c-108">Caso não seja, você precisará redefinir Surface Hub e concluir o programa de instalação OOBE (OOBE) de primeira vez, escolhendo a opção de ingressar no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e375c-108">If not, you will need to reset Surface Hub and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="e375c-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="e375c-109">Summary</span></span> 

<span data-ttu-id="e375c-110">O processo de criação de contas de administrador não globais envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e375c-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="e375c-111">Em Microsoft Intune, crie um grupo de Segurança contendo os administradores designados para gerenciar Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e375c-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub.</span></span>
2. <span data-ttu-id="e375c-112">Obtenha o SID do grupo do Azure AD usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e375c-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="e375c-113">Criar arquivo XML contendo SID do grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e375c-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="e375c-114">Crie um Grupo de Segurança contendo os Surface Hub que serão gerenciados pelo grupo de Segurança de administradores não globais.</span><span class="sxs-lookup"><span data-stu-id="e375c-114">Create a Security Group containing the Surface Hub devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="e375c-115">Crie um perfil de Configuração personalizado destinado ao grupo de segurança que contém seus Surface Hub dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e375c-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="e375c-116">Criar grupos de segurança do Azure AD</span><span class="sxs-lookup"><span data-stu-id="e375c-116">Create Azure AD security groups</span></span>

<span data-ttu-id="e375c-117">Primeiro crie um grupo de segurança que contenha as contas de administrador.</span><span class="sxs-lookup"><span data-stu-id="e375c-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="e375c-118">Em seguida, crie outro grupo de segurança para Surface Hub dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e375c-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="e375c-119">Criar grupo de segurança para contas de administrador</span><span class="sxs-lookup"><span data-stu-id="e375c-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="e375c-120">Entre no Intune por meio do Microsoft Endpoint Manager [de](https://go.microsoft.com/fwlink/?linkid=2109431)administração, selecione **Grupos**Novo Grupo > e em Tipo  >  \*\*\*\* de grupo, selecione **Segurança.**</span><span class="sxs-lookup"><span data-stu-id="e375c-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="e375c-121">Insira um nome de grupo , por exemplo, **Surface Hub Administradores Locais** e selecione **Criar.**</span><span class="sxs-lookup"><span data-stu-id="e375c-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Criar grupo de segurança para administradores do Hub](images/sh-create-sec-group.png)

3. <span data-ttu-id="e375c-123">Abra o grupo, selecione **Membros**e escolha **Adicionar** membros para inserir as contas de administrador que você deseja designar como administradores não globais no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e375c-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub.</span></span> <span data-ttu-id="e375c-124">Para saber mais sobre a criação de grupos no Intune, consulte  [Adicionar grupos para organizar usuários e dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="e375c-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-devices"></a><span data-ttu-id="e375c-125">Criar grupo de segurança para Surface Hub dispositivos</span><span class="sxs-lookup"><span data-stu-id="e375c-125">Create security group for Surface Hub devices</span></span>

1. <span data-ttu-id="e375c-126">Repita o procedimento anterior para criar um grupo de segurança separado para dispositivos Hub; por exemplo, **Surface Hub dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e375c-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Criar grupo de segurança para dispositivos Hub](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="e375c-128">Obter SID do grupo do Azure AD usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e375c-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="e375c-129">Iniciar o PowerShell com privilégios de conta elevados ( Executar como**Administrador**) e garantir que seu sistema está configurado para executar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e375c-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="e375c-130">Para saber mais, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="e375c-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="e375c-131">[Instalar Azure PowerShell módulo](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="e375c-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="e375c-132">Entre no locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e375c-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="e375c-133">Quando você estiver entrando em seu locatário, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="e375c-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="e375c-134">Ele solicitará que você "Digite a ID do objeto do grupo do Azure AD".</span><span class="sxs-lookup"><span data-stu-id="e375c-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="e375c-135">No Intune, selecione o grupo criado anteriormente e copie a ID do objeto, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="e375c-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Copiar id do objeto do grupo de segurança](images/sh-objectid.png)

6. <span data-ttu-id="e375c-137">Execute o seguinte commandlet para obter o SID do grupo de segurança:</span><span class="sxs-lookup"><span data-stu-id="e375c-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="e375c-138">Colar a id object no commandlet do PowerShell, pressione **Enter**e copie o SID do Grupo **do Azure AD** em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="e375c-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="e375c-139">Criar arquivo XML contendo SID do grupo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="e375c-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="e375c-140">Copie o seguinte em um editor de texto:</span><span class="sxs-lookup"><span data-stu-id="e375c-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```
      > [!IMPORTANT]
      > <span data-ttu-id="e375c-141">Não remova o membro do Administrador padrão do arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="e375c-141">Do not remove the default Administrator member from the XML file.</span></span>

2. <span data-ttu-id="e375c-142">Substitua o SID de espaço reservado (começando pelo S-1-12-1) pelo SID do **grupo do Azure AD** e salve o arquivo como XML; por exemplo, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="e375c-142">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="e375c-143">Criar perfil de configuração personalizado</span><span class="sxs-lookup"><span data-stu-id="e375c-143">Create Custom configuration profile</span></span>

1. <span data-ttu-id="e375c-144">Em Endpoint Manager, selecione **Perfis**de  >  **Configuração de**  >  **Dispositivos Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="e375c-144">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="e375c-145">Em Plataforma, **selecione Windows 10 e posterior.**</span><span class="sxs-lookup"><span data-stu-id="e375c-145">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="e375c-146">Em Perfil, selecione **Personalizado**e, em seguida, selecione **Criar.**</span><span class="sxs-lookup"><span data-stu-id="e375c-146">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="e375c-147">Adicione um nome e uma descrição e selecione **Next.**</span><span class="sxs-lookup"><span data-stu-id="e375c-147">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="e375c-148">Em **Configuração configurações**  >  **OMA-URI Configurações**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e375c-148">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="e375c-149">No painel Adicionar Linha, adicione um nome e em     **OMA-URI**, adicione a seguinte cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="e375c-149">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="e375c-150">Em Tipo de dados, selecione XML de **cadeia** de caracteres e navegue até abrir o arquivo XML criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e375c-150">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![carregar arquivo de configuração xml do administrador local](images/sh-local-admin-config.png)

7. <span data-ttu-id="e375c-152">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e375c-152">Click **Save**.</span></span>
8. <span data-ttu-id="e375c-153">Clique **em Selecionar grupos para incluir** e escolher o grupo de segurança [criado](#create-security-group-for-surface-hub-devices) anteriormente (**Surface Hub dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="e375c-153">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="e375c-154">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e375c-154">Click **Next.**</span></span>
9. <span data-ttu-id="e375c-155">Em Regras de Aplicabilidade, adicione uma Regra, se desejado.</span><span class="sxs-lookup"><span data-stu-id="e375c-155">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="e375c-156">Caso contrário, selecione **Próximo** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="e375c-156">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="e375c-157">Para saber mais sobre perfis de configuração personalizados usando cadeias de caracteres OMA-URI, consulte [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="e375c-157">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub"></a><span data-ttu-id="e375c-158">Administradores não globais gerenciando Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e375c-158">Non Global admins managing Surface Hub</span></span>

<span data-ttu-id="e375c-159">Membros do grupo **Surface Hub** Segurança de Administradores Locais agora podem entrar no aplicativo Configurações no Surface Hub e gerenciar configurações.</span><span class="sxs-lookup"><span data-stu-id="e375c-159">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub and manage settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e375c-160">O acesso padrão de administradores globais ao aplicativo Configurações é removido (a menos que eles também sejam membros desse novo grupo de segurança).</span><span class="sxs-lookup"><span data-stu-id="e375c-160">The default access of global admins to the Settings app is removed (unless they are also members of this new security group).</span></span>
