---
title: Criar uma conta de dispositivo usando a interface do usuário (Surface Hub v1)
description: Se você preferir usar uma interface do usuário gráfica, poderá criar uma conta do dispositivo para seu Microsoft Surface Hub na interface do usuário do Office 365 ou no Centro de Administração do Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: criar conta de dispositivo, interface do usuário do Office 365, Centro de administração do Exchange, centro de administração do Microsoft 365, Skype for Business, política de caixa de correio de dispositivo móvel
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: 9e6d72dc2b36bb149ee09c2edab885c80e60ac14
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314464"
---
# <span data-ttu-id="c15eb-104">Criar uma conta de dispositivo usando a interface do usuário (Surface Hub v1)</span><span class="sxs-lookup"><span data-stu-id="c15eb-104">Create a device account using UI (Surface Hub v1)</span></span>

 > [!NOTE]
 ><span data-ttu-id="c15eb-105">Esta página inclui informações sobre o Surface Hub original (v1).</span><span class="sxs-lookup"><span data-stu-id="c15eb-105">This page includes information about the original Surface Hub (v1).</span></span> <span data-ttu-id="c15eb-106">Para o Surface Hub 2S, confira Criar conta de dispositivo do [Surface Hub 2S.](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="c15eb-106">For Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

<span data-ttu-id="c15eb-107">Se você preferir usar uma interface do usuário gráfica, poderá criar uma conta do dispositivo para seu Microsoft Surface Hub na [interface do usuário do Office 365](#create-device-acct-o365) ou no [Centro de Administração do Exchange](#create-device-acct-eac).</span><span class="sxs-lookup"><span data-stu-id="c15eb-107">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="c15eb-108">Criar uma conta de dispositivo usando o Office 365</span><span class="sxs-lookup"><span data-stu-id="c15eb-108">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="c15eb-109">[Crie a conta no Centro de administração do Microsoft 365.](#create-device-acct-o365-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="c15eb-109">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="c15eb-110">[Criar uma política de caixa de correio de dispositivo móvel (ActiveSync) do Centro de administração do Microsoft Exchange](#create-device-acct-o365-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="c15eb-110">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="c15eb-111">[Usar o PowerShell para concluir a criação de conta do dispositivo](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="c15eb-111">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="c15eb-112">[Usar o PowerShell para configurar as propriedades da conta do Exchange](#create-device-acct-o365-configure-exch-prop).</span><span class="sxs-lookup"><span data-stu-id="c15eb-112">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="c15eb-113">[Habilitar a conta com o Skype for Business](#create-device-acct-o365-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="c15eb-113">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="c15eb-114">Criar a conta no centro de administração</span><span class="sxs-lookup"><span data-stu-id="c15eb-114">Create the account in the admin center</span></span>

1.  <span data-ttu-id="c15eb-115">Entrar no Office 365 visitando https://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="c15eb-115">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="c15eb-116">Forneça as credenciais de administrador para o seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c15eb-116">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="c15eb-117">Isso levará você para o Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c15eb-117">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Centro de administração do Microsoft 365.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="c15eb-119">No centro de administração, navegue até **Recursos** no painel esquerdo e clique em Salas & **equipamento.**</span><span class="sxs-lookup"><span data-stu-id="c15eb-119">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![Salas & de equipamento no Centro de administração](images/room-equipment.png)

4. <span data-ttu-id="c15eb-121">Clique em **Adicionar** para criar uma nova conta de Sala.</span><span class="sxs-lookup"><span data-stu-id="c15eb-121">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="c15eb-122">Insira um nome de exibição e endereço de e-mail para a conta, e depois clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-122">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![Criar nova janela de conta de sala](images/room-add.png)

5. <span data-ttu-id="c15eb-124">Selecione a conta de Sala você acabou de criar na lista de Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="c15eb-124">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="c15eb-125">No painel direito, você pode ver as propriedades da conta e diversas ações opcionais.</span><span class="sxs-lookup"><span data-stu-id="c15eb-125">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="c15eb-126">Clique em **Redefinir senha** para alterar a senha e desmarque **Fazer com que esse usuário altere sua senha quando fizer logon pela primeira vez**, pois não é possível alterar a senha do fluxo de entrada do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c15eb-126">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="c15eb-127">Na seção **Licença atribuída**, clique em **Editar** e, em seguida, clique na seta suspensa ao lado da licença apropriada para expandir os detalhes.</span><span class="sxs-lookup"><span data-stu-id="c15eb-127">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="c15eb-128">Selecione um local de usuário e na lista de licenças, ative **Skype for Business Online (Plano 2)** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-128">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="c15eb-129">A licença pode variar de acordo com a organização (por exemplo, você pode ter o Plano 2 ou o Plano 3).</span><span class="sxs-lookup"><span data-stu-id="c15eb-129">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="c15eb-130">Criar uma política de caixa de entrada (ActiveSync) de dispositivo móvel a partir do Centro de Administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="c15eb-130">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="c15eb-131">No painel esquerdo do centro de administração, clique em **ADMIN**e, em seguida, clique em **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-131">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![centro de administração, mostrando usuários ativos do Exchange.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="c15eb-133">Isso abrirá outra guia do navegador para levá-lo para o Centro de Administração do Exchange, onde você poderá criar e definir a Configuração de caixa de correio do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c15eb-133">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Centro de administração do Exchange.](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="c15eb-135">Para criar uma Política de Caixa de Entrada de Dispositivo Móvel, clique em **Dispositivo móvel** , no painel esquerdo e, em seguida, clique em **Políticas de caixa de entrada de dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-135">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="c15eb-136">Surface Hubs requerem uma conta com uma política de caixa de entrada de dispositivo móvel que não exija uma senha, portanto se você já tem uma política existente que corresponde a esse requisito, você pode aplicar essa política para a conta.</span><span class="sxs-lookup"><span data-stu-id="c15eb-136">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="c15eb-137">Caso contrário, use as etapas a seguir para criar uma nova para ser usada somente para contas do dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c15eb-137">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Centro de administração Exchange - criação de uma política de caixa de entrada de dispositivo móvel.](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="c15eb-139">Para criar uma nova política de caixa de entrada de dispositivo móvel do Surface Hub, clique no botão **+** nos controles acima da lista de políticas para adicionar uma nova política.</span><span class="sxs-lookup"><span data-stu-id="c15eb-139">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="c15eb-140">Para o nome, forneça um nome que lhe ajudará a diferenciar essa política de outras contas do dispositivo (por exemplo, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="c15eb-140">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="c15eb-141">Verifique se a política não exige uma senha para os dispositivos atribuídos, portanto, verifique se a opção **Exigir uma senha** permanece desmarcada, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-141">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Imagem mostrando a nova política de dispositivo móvel.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="c15eb-143">Depois que você criou a nova política de caixa de correio de dispositivo móvel, volte para o **Centro de Administração do Exchange** e você verá a nova política listada.</span><span class="sxs-lookup"><span data-stu-id="c15eb-143">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Imagem com a nova política de caixa de correio de dispositivo móvel no Centro de administração do Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="c15eb-145">Use o PowerShell para concluir a criação de conta do dispositivo</span><span class="sxs-lookup"><span data-stu-id="c15eb-145">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="c15eb-146">A partir daqui, você precisará concluir o processo de criação de conta usando o PowerShell para definir algumas configurações.</span><span class="sxs-lookup"><span data-stu-id="c15eb-146">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="c15eb-147">Para executar cmdlets usados por esses scripts do PowerShell, o seguinte deve estar instalado no console de administração do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c15eb-147">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="c15eb-148">Assistente de Sign-In microsoft online para profissionais de TI RTW</span><span class="sxs-lookup"><span data-stu-id="c15eb-148">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="c15eb-149">Windows Azure Active Directory Module for Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c15eb-149">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="c15eb-150">Skype for Business Online, Windows PowerShell Module</span><span class="sxs-lookup"><span data-stu-id="c15eb-150">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="c15eb-151">Instalar o seguinte módulo no Powershell</span><span class="sxs-lookup"><span data-stu-id="c15eb-151">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="c15eb-152">Conectando-se a serviços online</span><span class="sxs-lookup"><span data-stu-id="c15eb-152">Connecting to online services</span></span>

1.  <span data-ttu-id="c15eb-153">Execute o Windows PowerShell como Administrador.</span><span class="sxs-lookup"><span data-stu-id="c15eb-153">Run Windows PowerShell as Administrator.</span></span>

    ![Imagem mostrando como iniciar o Windows PowerShell e executar como administrador.](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="c15eb-155">Crie um Objeto Credenciais e, em seguida, crie uma nova sessão que se conecte ao Skype for Business Online. Forneça a conta de administrador locatário global e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-155">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Imagem de solicitação de credenciais do Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="c15eb-157">Para conectar-se ao Microsoft Online Services, execute:</span><span class="sxs-lookup"><span data-stu-id="c15eb-157">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="c15eb-159">Agora para conectar-se ao Skype for Business Online Services, execute:</span><span class="sxs-lookup"><span data-stu-id="c15eb-159">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="c15eb-161">Por fim, para conectar-se ao Exchange Online Services, execute:</span><span class="sxs-lookup"><span data-stu-id="c15eb-161">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="c15eb-163">Agora você tem que importar o Skype for Business Online Session e a sessão do Exchange Online que você acabou de criar, o que irá importar os comandos do Skype e Exchange para que possa usá-los localmente.</span><span class="sxs-lookup"><span data-stu-id="c15eb-163">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="c15eb-164">Observe que isso pode levar algum tempo para concluir.</span><span class="sxs-lookup"><span data-stu-id="c15eb-164">Note that this could take a while to complete.</span></span>

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="c15eb-166">Depois que estiver conectado aos serviços online, você precisará executar mais alguns cmdlets para configurar essa conta como uma conta do dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c15eb-166">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="c15eb-167">Use o PowerShell para configurar as propriedades do Exchange da conta</span><span class="sxs-lookup"><span data-stu-id="c15eb-167">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="c15eb-168">Agora que você está conectado aos serviços online, você pode concluir a configuração da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c15eb-168">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="c15eb-169">Você usará o endereço de email da conta do dispositivo para:</span><span class="sxs-lookup"><span data-stu-id="c15eb-169">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="c15eb-170">Alterar o tipo da caixa de entrada de regular para uma com mais espaço.</span><span class="sxs-lookup"><span data-stu-id="c15eb-170">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="c15eb-171">Definir a senha e habilitar a conta de caixa de entrada com mais espaço</span><span class="sxs-lookup"><span data-stu-id="c15eb-171">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="c15eb-172">Alterar várias propriedades do Exchange</span><span class="sxs-lookup"><span data-stu-id="c15eb-172">Change various Exchange properties</span></span>
-   <span data-ttu-id="c15eb-173">Definir a senha da conta de usuário para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="c15eb-173">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="c15eb-174">Você precisará inserir o endereço de email da conta e criar uma variável com esse valor:</span><span class="sxs-lookup"><span data-stu-id="c15eb-174">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="c15eb-175">Para armazenar o valor obtido na caixa de entrada:</span><span class="sxs-lookup"><span data-stu-id="c15eb-175">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="c15eb-176">Imprima o valor:</span><span class="sxs-lookup"><span data-stu-id="c15eb-176">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="c15eb-177">Você verá o endereço de email correto.</span><span class="sxs-lookup"><span data-stu-id="c15eb-177">You will see the correct email address.</span></span>

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="c15eb-179">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c15eb-179">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="c15eb-180">Várias propriedades do Exchange podem ser definidas na conta do dispositivo para melhorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="c15eb-180">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="c15eb-181">Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="c15eb-181">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="c15eb-183">Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também.</span><span class="sxs-lookup"><span data-stu-id="c15eb-183">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="c15eb-184">Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c15eb-184">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="c15eb-185">Habilitar a conta com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c15eb-185">Enable the account with Skype for Business</span></span>

<span data-ttu-id="c15eb-186">Habilite a conta de dispositivo com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c15eb-186">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="c15eb-187">Para habilitar o Skype for Business, seu ambiente precisará atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="c15eb-187">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="c15eb-188">Você precisará ter o Skype for Business Online Plano Autônomo 2 ou superior em seu plano do O365.</span><span class="sxs-lookup"><span data-stu-id="c15eb-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="c15eb-189">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="c15eb-189">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="c15eb-190">Se você precisar do Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para o Surface Hub, precisará do Skype for Business Online Plano Autônomo 3.</span><span class="sxs-lookup"><span data-stu-id="c15eb-190">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="c15eb-191">Os usuários de locatário devem ter caixas de entrada do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c15eb-191">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="c15eb-192">Sua conta do Surface Hub exige uma licença do Plano Autônomo 2 do Skype for Business Online ou do Plano Autônomo 3 do Skype for Business Online, mas não exige uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c15eb-192">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="c15eb-193">Comece criando uma sessão remota do PowerShell de um computador.</span><span class="sxs-lookup"><span data-stu-id="c15eb-193">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="c15eb-194">Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c15eb-194">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="c15eb-195">Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c15eb-195">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="c15eb-196">Criar uma conta do dispositivo usando o Centro de Administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="c15eb-196">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="c15eb-197">Esse método só funcionará se você estiver sincronizando de um Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="c15eb-197">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="c15eb-198">Você pode usar o Centro de Administração do Exchange para criar uma conta do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c15eb-198">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="c15eb-199">[Criar uma conta e uma caixa de correio com o Centro de Administração do Exchange](#create-device-acct-exch-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="c15eb-199">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="c15eb-200">[Criar uma política de caixa de correio de dispositivo móvel no Centro de Administração do Exchange](#create-device-acct-exch-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="c15eb-200">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="c15eb-201">[Usar o PowerShell para configurar a conta](#create-device-acct-exch-powershell-conf).</span><span class="sxs-lookup"><span data-stu-id="c15eb-201">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="c15eb-202">[Habilitar a conta com o Skype for Business](#create-device-acct-exch-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="c15eb-202">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="c15eb-203">Criar uma conta e uma caixa de entrada com o Centro de Administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="c15eb-203">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="c15eb-204">Entrar no seu Centro de Administração do Exchange usando as credenciais de administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c15eb-204">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="c15eb-205">Depois que você está no Centro de Administração do Exchange (EAT), navegue até **Destinatários** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="c15eb-205">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Imagem mostrando caixas de entrada no Centro de administração do Exchange.](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="c15eb-207">Nos controles acima da lista de caixas de correio, escolha **+** para criar uma nova caixa e forneça um **Nome de exibição**, **Nome**, e **Nome de logon do usuário** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-207">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Imagem mostrando a criação de uma nova caixa de correio.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="c15eb-209">Criar uma política de caixa de correio de dispositivo móvel a partir do Centro de Administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c15eb-209">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="c15eb-210">Se você deseja criar e atribuir uma política à conta que você criou e está usando o Exchange 2010, procure as informações correspondentes sobre criação de política e atribuição de política ao usar o EMC (console de gerenciamento do Exchange).</span><span class="sxs-lookup"><span data-stu-id="c15eb-210">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="c15eb-211">Vá até o Centro de Administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c15eb-211">Go to the Exchange Admin Center.</span></span>

    ![Imagem mostrando o Centro de administração do Exchange.](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="c15eb-213">Para criar uma política de caixa de entrada de dispositivo móvel, clique em **Dispositivo móvel** , no painel esquerdo e clique em **Políticas de caixa de entrada de dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-213">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="c15eb-214">Surface Hubs requerem uma conta com uma política de caixa de entrada de dispositivo móvel que não exija uma senha, portanto se você já tem uma política existente que corresponde a esse requisito, você pode aplicar essa política para a conta.</span><span class="sxs-lookup"><span data-stu-id="c15eb-214">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="c15eb-215">Caso contrário, use as etapas a seguir para criar uma nova para ser usada somente para contas do dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c15eb-215">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Imagem mostrando como usar o Centro de administração do Exchange para criar uma política de caixa de entrada de dispositivo móvel.](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="c15eb-217">Para criar uma nova política de caixa de entrada de conta do dispositivo móvel, clique no botão **+** nos controles acima da lista de políticas para adicionar uma nova política.</span><span class="sxs-lookup"><span data-stu-id="c15eb-217">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="c15eb-218">Para o nome, forneça um nome que lhe ajudará a diferenciar essa política de outras contas do dispositivo (por exemplo, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="c15eb-218">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="c15eb-219">A política de não deve ser protegida por senha, portanto, verifique se a opção **Exigir uma senha** permanece desmarcada, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-219">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Imagem mostrando a nova política de caixa de correio de dispositivo móvel.](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="c15eb-221">Depois que você criou a nova política de caixa de correio de dispositivo móvel, volte para o Centro de Administração do Exchange e você verá a nova política listada.</span><span class="sxs-lookup"><span data-stu-id="c15eb-221">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Imagem mostrando nova política de caixa de correio de dispositivo móvel no Centro de administração do Exchange.](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="c15eb-223">Para aplicar a política do ActiveSync sem o uso do PowerShell, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c15eb-223">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="c15eb-224">No EAC, clique em **Destinatários** &gt; **Caixas de correio** e selecione uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c15eb-224">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Imagem mostrando o Centro de Administração do Exchange.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="c15eb-226">No painel **Detalhes**, role a tela até **Telefone e Recursos de Voz** e clique em **Exibir detalhes** para exibir a tela **Detalhes do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-226">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![Imagem mostrando detalhes da caixa de correio.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="c15eb-228">A política de caixa de correio de dispositivo móvel que atualmente é atribuída é exibida.</span><span class="sxs-lookup"><span data-stu-id="c15eb-228">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="c15eb-229">Para alterar a política de caixa de correio de dispositivo móvel, clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-229">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![Imagem mostrando a política de caixa de correio de dispositivo móvel atribuída no momento.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="c15eb-231">Escolha a política de caixa de correio de dispositivo móvel apropriada da lista, clique em **OK** e, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c15eb-231">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![Imagem mostrando uma lista de políticas de caixa de correio de dispositivos móveis.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="c15eb-233">Use o PowerShell para configurar a conta</span><span class="sxs-lookup"><span data-stu-id="c15eb-233">Use PowerShell to configure the account</span></span>

<span data-ttu-id="c15eb-234">Agora que você está conectado aos serviços online, você pode concluir a configuração da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c15eb-234">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="c15eb-235">Você usará o endereço de email da conta do dispositivo para:</span><span class="sxs-lookup"><span data-stu-id="c15eb-235">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="c15eb-236">Alterar o tipo da caixa de entrada de regular para uma com mais espaço.</span><span class="sxs-lookup"><span data-stu-id="c15eb-236">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="c15eb-237">Alterar várias propriedades do Exchange</span><span class="sxs-lookup"><span data-stu-id="c15eb-237">Change various Exchange properties</span></span>
-   <span data-ttu-id="c15eb-238">Definir a senha da conta de usuário para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="c15eb-238">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="c15eb-239">Você precisará inserir o endereço de email da conta e criar uma variável com esse valor:</span><span class="sxs-lookup"><span data-stu-id="c15eb-239">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="c15eb-240">Para armazenar o valor obtido na caixa de correio:</span><span class="sxs-lookup"><span data-stu-id="c15eb-240">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="c15eb-241">Imprima o valor executando:</span><span class="sxs-lookup"><span data-stu-id="c15eb-241">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="c15eb-242">Você verá o endereço de email correto.</span><span class="sxs-lookup"><span data-stu-id="c15eb-242">You will see the correct email address.</span></span>

2.  <span data-ttu-id="c15eb-243">Você precisa converter a conta em uma caixa de correio de sala, portanto, execute:</span><span class="sxs-lookup"><span data-stu-id="c15eb-243">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="c15eb-244">Afim de autenticar a conta do dispositivo em um Surface Hub, você precisa habilitar a conta da caixa de entrada com mais espaço e definir uma senha, para que a conta possa ser usada pelo dispositivo para obter informações da reunião usando o ActiveSync e fazer logon no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c15eb-244">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="c15eb-245">Várias propriedades do Exchange podem ser definidas na conta do dispositivo para melhorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="c15eb-245">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="c15eb-246">Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="c15eb-246">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="c15eb-247">Agora, precisamos definir algumas propriedades no AD.</span><span class="sxs-lookup"><span data-stu-id="c15eb-247">Now we have to set some properties in AD.</span></span> <span data-ttu-id="c15eb-248">Para fazer isso, você precisa do alias da conta (esta é a parte do nome UPN que precede o "@").</span><span class="sxs-lookup"><span data-stu-id="c15eb-248">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="c15eb-249">O usuário precisa estar habilitado no AD antes que ele possa autenticar com um Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c15eb-249">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="c15eb-250">Executar:</span><span class="sxs-lookup"><span data-stu-id="c15eb-250">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="c15eb-251">Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também.</span><span class="sxs-lookup"><span data-stu-id="c15eb-251">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="c15eb-252">Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c15eb-252">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="c15eb-253">Habilitar a conta com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c15eb-253">Enable the account with Skype for Business</span></span>

<span data-ttu-id="c15eb-254">Habilite a conta de dispositivo com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c15eb-254">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="c15eb-255">Para habilitar o Skype for Business, seu ambiente precisará atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="c15eb-255">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

- <span data-ttu-id="c15eb-256">Você precisará ter o Skype for Business Online Plano Autônomo 2 ou superior em seu plano do O365.</span><span class="sxs-lookup"><span data-stu-id="c15eb-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="c15eb-257">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="c15eb-257">The plan needs to support conferencing capability.</span></span>
- <span data-ttu-id="c15eb-258">Se você precisar do Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para o Surface Hub, precisará do Skype for Business Online Plano Autônomo 3.</span><span class="sxs-lookup"><span data-stu-id="c15eb-258">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
- <span data-ttu-id="c15eb-259">Os usuários de locatário devem ter caixas de entrada do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c15eb-259">Your tenant users must have Exchange mailboxes.</span></span>
- <span data-ttu-id="c15eb-260">Sua conta do Surface Hub exige uma licença do Plano Autônomo 2 do Skype for Business Online ou do Plano Autônomo 3 do Skype for Business Online, mas não exige uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c15eb-260">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1. <span data-ttu-id="c15eb-261">Comece criando uma sessão remota do PowerShell de um computador.</span><span class="sxs-lookup"><span data-stu-id="c15eb-261">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="c15eb-262">Recuperar o pool de registradores da conta do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="c15eb-262">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="c15eb-263">Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c15eb-263">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

 ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
 ```

3. <span data-ttu-id="c15eb-264">Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c15eb-264">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```