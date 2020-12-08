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
# <span data-ttu-id="bc09d-104">Configurar contas de administrador não globais no Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="bc09d-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="bc09d-105">Ao participar do Surface Hub 2S em um domínio do Azure AD, você pode configurar contas de administrador não globais que limitam as permissões ao gerenciamento do aplicativo configurações no Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="bc09d-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="bc09d-106">Isso permite que você deescopo as permissões de administrador para Surface Hub 2S apenas e impedir o acesso de administradores potencialmente indesejados a todo o domínio do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bc09d-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="bc09d-107">Antes de começar, verifique se o Surface Hub 2S está associado ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bc09d-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="bc09d-108">Caso contrário, você precisará redefinir o Surface Hub 2S e concluir o programa de instalação da primeira vez, de fora da caixa (OOBE), escolhendo a opção para participar do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bc09d-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <span data-ttu-id="bc09d-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="bc09d-109">Summary</span></span> 

<span data-ttu-id="bc09d-110">O processo de criação de contas de administrador não globais envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bc09d-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="bc09d-111">No Microsoft Intune, crie um grupo de segurança contendo os administradores designados para gerenciar o Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="bc09d-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="bc09d-112">Obtenha o SID do grupo do Azure AD usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc09d-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="bc09d-113">Criar arquivo XML contendo o SID do grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bc09d-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="bc09d-114">Crie um grupo de segurança contendo os dispositivos Surface Hub 2S que serão gerenciados pelo grupo de segurança não global administradores.</span><span class="sxs-lookup"><span data-stu-id="bc09d-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="bc09d-115">Crie um perfil de configuração personalizado que direcionará o grupo de segurança que contém os dispositivos Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="bc09d-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <span data-ttu-id="bc09d-116">Criar grupos de segurança do Azure AD</span><span class="sxs-lookup"><span data-stu-id="bc09d-116">Create Azure AD security groups</span></span>

<span data-ttu-id="bc09d-117">Primeiro, crie um grupo de segurança contendo as contas de administrador.</span><span class="sxs-lookup"><span data-stu-id="bc09d-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="bc09d-118">Em seguida, crie outro grupo de segurança para dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="bc09d-118">Then create another security group for Surface Hub devices.</span></span>  

### <span data-ttu-id="bc09d-119">Criar grupo de segurança para contas de administração</span><span class="sxs-lookup"><span data-stu-id="bc09d-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="bc09d-120">Entre no Intune por meio do [centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **grupos**  >  **novo grupo** > e em tipo de grupo, selecione **segurança.**</span><span class="sxs-lookup"><span data-stu-id="bc09d-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="bc09d-121">Insira um nome de grupo--por exemplo, **Administradores locais do Surface Hub** --e, em seguida, selecione **criar.**</span><span class="sxs-lookup"><span data-stu-id="bc09d-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Criar grupo de segurança para administradores de Hub](images/sh-create-sec-group.png)

3. <span data-ttu-id="bc09d-123">Abra o grupo, selecione **Membros**e, em seguida, escolha **adicionar membros** para inserir as contas de administrador que você deseja designar como administradores não globais no Surface Hub 2s.</span><span class="sxs-lookup"><span data-stu-id="bc09d-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="bc09d-124">Para saber mais sobre como criar grupos no Intune, consulte  [Adicionar grupos para organizar usuários e dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="bc09d-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <span data-ttu-id="bc09d-125">Criar grupo de segurança para dispositivos Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="bc09d-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="bc09d-126">Repita o procedimento anterior para criar um grupo de segurança separado para dispositivos Hub; por exemplo, **dispositivos Surface Hub**.</span><span class="sxs-lookup"><span data-stu-id="bc09d-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Criar grupo de segurança para dispositivos Hub](images/sh-create-sec-group-devices.png) 

## <span data-ttu-id="bc09d-128">Obter SID do grupo do Azure AD usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc09d-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="bc09d-129">Inicie o PowerShell com privilégios de conta elevada (**Executar como administrador**) e verifique se o sistema está configurado para executar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc09d-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="bc09d-130">Para saber mais, consulte [sobre as políticas de execução](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="bc09d-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="bc09d-131">[Instale o módulo do PowerShell do PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="bc09d-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="bc09d-132">Entre em seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bc09d-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="bc09d-133">Quando estiver conectado ao seu locatário, execute o commandlet a seguir.</span><span class="sxs-lookup"><span data-stu-id="bc09d-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="bc09d-134">Ele solicitará que você "digite a ID do objeto do seu grupo do Azure AD".</span><span class="sxs-lookup"><span data-stu-id="bc09d-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="bc09d-135">No Intune, selecione o grupo que você criou anteriormente e copie a identificação do objeto, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="bc09d-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Copiar ID de objeto do grupo de segurança](images/sh-objectid.png)

6. <span data-ttu-id="bc09d-137">Execute o commandlet a seguir para obter o SID do grupo de segurança:</span><span class="sxs-lookup"><span data-stu-id="bc09d-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="bc09d-138">Cole a ID do objeto no próprio cmdlet do PowerShell, pressione **Enter**e copie o **SID do grupo do Azure ad** em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="bc09d-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <span data-ttu-id="bc09d-139">Criar arquivo XML contendo o SID do grupo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="bc09d-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="bc09d-140">Copie o seguinte em um editor de texto:</span><span class="sxs-lookup"><span data-stu-id="bc09d-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="bc09d-141">Substitua o SID do espaço reservado (começando com S-1-12-1) pelo **SID do grupo do Azure ad** e salve o arquivo como XML; por exemplo, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="bc09d-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <span data-ttu-id="bc09d-142">Criar perfil de configuração personalizado</span><span class="sxs-lookup"><span data-stu-id="bc09d-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="bc09d-143">No Endpoint Manager, selecione os perfis de configuração de **dispositivos**  >  **Configuration profiles**  >  **Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="bc09d-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="bc09d-144">Em plataforma, selecione **Windows 10 e posterior.**</span><span class="sxs-lookup"><span data-stu-id="bc09d-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="bc09d-145">Em perfil, selecione **personalizado**e, em seguida, selecione **criar.**</span><span class="sxs-lookup"><span data-stu-id="bc09d-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="bc09d-146">Adicione um nome e uma descrição e selecione **Avançar.**</span><span class="sxs-lookup"><span data-stu-id="bc09d-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="bc09d-147">Em **configurações**  >  **OMA-URI**configurações, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bc09d-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="bc09d-148">No painel Adicionar linha, adicione um nome e, em     **OMA-URI**, adicione a seguinte cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="bc09d-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="bc09d-149">Em tipo de dados, selecione **cadeia de caracteres XML** e navegue para abrir o arquivo XML que você criou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="bc09d-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![carregar o arquivo de configuração XML do administrador local](images/sh-local-admin-config.png)

7. <span data-ttu-id="bc09d-151">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bc09d-151">Click **Save**.</span></span>
8. <span data-ttu-id="bc09d-152">Clique em **Selecionar grupos para incluir** e escolher o [grupo de segurança que você criou anteriormente](#create-security-group-for-surface-hub-2s-devices) (**dispositivos Surface Hub**).</span><span class="sxs-lookup"><span data-stu-id="bc09d-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="bc09d-153">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc09d-153">Click **Next.**</span></span>
9. <span data-ttu-id="bc09d-154">Em regras de aplicabilidade, adicione uma regra, se desejar.</span><span class="sxs-lookup"><span data-stu-id="bc09d-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="bc09d-155">Caso contrário, selecione **Avançar** e, em seguida, selecione **criar**.</span><span class="sxs-lookup"><span data-stu-id="bc09d-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="bc09d-156">Para saber mais sobre perfis de configuração personalizados usando cadeias de caracteres do OMA-URI, consulte [usar configurações personalizadas para dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="bc09d-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <span data-ttu-id="bc09d-157">Administradores não globais que gerenciam o Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="bc09d-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="bc09d-158">Os membros do grupo de segurança **Administradores locais do Surface Hub** podem agora entrar no aplicativo configurações no Surface Hub 2S e gerenciar as configurações.</span><span class="sxs-lookup"><span data-stu-id="bc09d-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
