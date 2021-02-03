---
title: Criar conta de dispositivo do Surface Hub 2S
description: Esta página descreve o procedimento para criar a conta de dispositivo do Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 76ac960be2ab30a30b4e29618f350a13a284f52a
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312017"
---
# <span data-ttu-id="288cb-104">Criar conta de dispositivo do Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="288cb-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="288cb-105">Criar uma conta de dispositivo do Surface Hub (também conhecida como caixa de correio de sala) permite que o Surface Hub 2S receba, aprove ou reenva solicitações de reunião e participe de reuniões.</span><span class="sxs-lookup"><span data-stu-id="288cb-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings.</span></span> <span data-ttu-id="288cb-106">Configure a conta de dispositivo durante a configuração inicial pelo usuário (OOBE).</span><span class="sxs-lookup"><span data-stu-id="288cb-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="288cb-107">Se necessário, você pode alterá-la mais tarde (sem passar pela configuração OOBE).</span><span class="sxs-lookup"><span data-stu-id="288cb-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="288cb-108">Você pode criar a conta no Centro de administração do Microsoft 365 em combinação com o Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="288cb-108">You can create the account from  Microsoft 365 Admin center in combination with Windows PowerShell:</span></span> 

- <span data-ttu-id="288cb-109">**Criar conta por meio do Centro de administração.**</span><span class="sxs-lookup"><span data-stu-id="288cb-109">**Create account via Admin center**.</span></span> <span data-ttu-id="288cb-110">Para atender aos requisitos mínimos, você pode configurar tudo o que precisa para a conta diretamente do centro de administração do [Microsoft 365.](https://admin.microsoft.com/AdminPortal)</span><span class="sxs-lookup"><span data-stu-id="288cb-110">To meet minimum requirements, you can configure everything you need for the account directly from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal).</span></span> <span data-ttu-id="288cb-111">Alguns recursos, como o compartilhamento de whiteboards diretamente do aplicativo whiteboard, exigem o uso do PowerShell para configurar o ActiveSync; confira [Habilitar ActiveSync se o uso do aplicativo de email for necessário](#enable-activesync-if-use-of-email-app-is-required) nesta página.</span><span class="sxs-lookup"><span data-stu-id="288cb-111">Some features like sharing whiteboards directly from the whiteboard app require using PowerShell to configure ActiveSync; see [Enable ActiveSync if use of email app is required](#enable-activesync-if-use-of-email-app-is-required) on this page.</span></span>

- <span data-ttu-id="288cb-112">**Criar conta por meio do PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="288cb-112">**Create account via PowerShell**.</span></span> <span data-ttu-id="288cb-113">Você pode usar scripts do PowerShell para facilitar a criação de várias contas de dispositivo e configurar rapidamente recursos específicos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="288cb-113">You can use PowerShell scripts to facilitate creation of multiple device accounts and quickly configure specific features including:</span></span>
    - <span data-ttu-id="288cb-114">Processamento de calendário para cada conta de dispositivo do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="288cb-114">Calendar processing for every Surface Hub device account.</span></span>
    - <span data-ttu-id="288cb-115">Respostas automáticas personalizadas a solicitações de agendamento.</span><span class="sxs-lookup"><span data-stu-id="288cb-115">Custom auto replies to scheduling requests.</span></span>
    - <span data-ttu-id="288cb-116">Se a política de caixa de correio padrão do ActiveSync já tiver sido modificada por outra pessoa ou por outro processo, você provavelmente terá que criar e atribuir uma nova política de caixa de correio do ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="288cb-116">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!TIP]
> <span data-ttu-id="288cb-117">Você pode verificar a configuração da conta executando o [script de verificação da conta](#account-verification-script) abaixo.</span><span class="sxs-lookup"><span data-stu-id="288cb-117">You can check account setup by running the [Account verification script](#account-verification-script) below.</span></span>

> [!NOTE]  
> <span data-ttu-id="288cb-118">A conta de dispositivo do Surface Hub não dá suporte a FIPs (Provedores de Identidade Federada) de terceiros e deve ser uma conta padrão do Active Directory ou do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="288cb-118">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="288cb-119">Criar conta por meio do centro de administração</span><span class="sxs-lookup"><span data-stu-id="288cb-119">Create account via admin center</span></span>

1. <span data-ttu-id="288cb-120">No centro de administração do Microsoft \*\*\*\* 365, vá para Recursos e escolha Salas **& Equipamento** e selecione + **Adicionar recurso.**</span><span class="sxs-lookup"><span data-stu-id="288cb-120">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Add resource**.</span></span>

2. <span data-ttu-id="288cb-121">Forneça um nome e endereço de email para a conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="288cb-121">Provide a name and email address for the device account.</span></span> <span data-ttu-id="288cb-122">Deixe as configurações restantes inalteradas no estado padrão.</span><span class="sxs-lookup"><span data-stu-id="288cb-122">Leave remaining settings unchanged in the default state.</span></span>

   ![Forneça um nome e um endereço de email](images/sh2-account2.png)

   ![Deixar as configurações restantes inalteradas no estado padrão](images/sh2-account3.png)

3. <span data-ttu-id="288cb-125">De definida a senha da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="288cb-125">Set the password for the device account.</span></span> <span data-ttu-id="288cb-126">Para definir a senha, escolha **Usuários e** selecione **Usuários Ativos.**</span><span class="sxs-lookup"><span data-stu-id="288cb-126">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="288cb-127">Agora procure o usuário recém-criado para definir a senha.</span><span class="sxs-lookup"><span data-stu-id="288cb-127">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="288cb-128">Certifique-se **de não selecionar** a opção Fazer com que esse usuário **altere a senha ao entrar pela primeira vez.**</span><span class="sxs-lookup"><span data-stu-id="288cb-128">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Definir a senha da conta de dispositivo](images/sh2-account4.png)

4. <span data-ttu-id="288cb-130">Atribua a sala com uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="288cb-130">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="288cb-131">É recomendável atribuir a licença da \*\*\*\* Sala de Reunião do Office 365, que habilita automaticamente a conta do Microsoft Teams e do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="288cb-131">It’s recommended to assign the Office 365 **Meeting Room** license, which automatically enables the account for Microsoft Teams and Skype for Business.</span></span>

   ![Atribuir licença do Office 365](images/sh2-account5.png)


> [!NOTE]  
> <span data-ttu-id="288cb-133">Se estiver usando o Skype for Business, você precisará finalizar a instalação por meio do PowerShell – Calendário do Skype for Business: Definir o [Autoprocessamento](#set-calendar-auto-processing-skype-for-business-only) de Calendário para essa conta.</span><span class="sxs-lookup"><span data-stu-id="288cb-133">If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account.</span></span> 

## <span data-ttu-id="288cb-134">Criar conta por meio do PowerShell</span><span class="sxs-lookup"><span data-stu-id="288cb-134">Create account via PowerShell</span></span>

 <span data-ttu-id="288cb-135">Usar o PowerShell para automatizar rapidamente tarefas no Surface Hub não requer necessariamente experiência no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="288cb-135">Using PowerShell to rapidly automate tasks on Surface Hub does not necessarily require PowerShell expertise.</span></span> <span data-ttu-id="288cb-136">Verifique se você concluiu os pré-requisitos de instalação antes de usar os scripts apropriados nesta página.</span><span class="sxs-lookup"><span data-stu-id="288cb-136">Ensure you have completed the setup prerequisites before using the appropriate scripts on this page.</span></span>

### <span data-ttu-id="288cb-137">Pré-requisitos para usar o PowerShell para gerenciar o Surface Hub</span><span class="sxs-lookup"><span data-stu-id="288cb-137">Prerequisites for using PowerShell to manage Surface Hub</span></span> 

1. <span data-ttu-id="288cb-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span><span class="sxs-lookup"><span data-stu-id="288cb-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="288cb-139">Para saber mais, consulte Sobre [políticas de execução.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)</span><span class="sxs-lookup"><span data-stu-id="288cb-139">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="288cb-140">[Instale o módulo do Azure PowerShell.](https://docs.microsoft.com/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="288cb-140">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>


### <span data-ttu-id="288cb-141">Conectar-se ao PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="288cb-141">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="288cb-142">Criar caixa de correio</span><span class="sxs-lookup"><span data-stu-id="288cb-142">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="288cb-143">Definir o processamento automático de calendário (somente Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="288cb-143">Set Calendar auto-processing (Skype for Business only)</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="288cb-144">Habilitar ActiveSync se o uso do aplicativo de email for necessário</span><span class="sxs-lookup"><span data-stu-id="288cb-144">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="288cb-145">A Política activeSync padrão funcionará se não for alterada.</span><span class="sxs-lookup"><span data-stu-id="288cb-145">The default ActiveSync Policy will work if unchanged.</span></span> <span data-ttu-id="288cb-146">Caso contrário, crie uma nova Política e atribua.</span><span class="sxs-lookup"><span data-stu-id="288cb-146">Otherwise createStupid a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <span data-ttu-id="288cb-147">Conecte-se ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="288cb-147">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="288cb-148">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="288cb-148">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="288cb-149">Verificar se há licenças disponíveis</span><span class="sxs-lookup"><span data-stu-id="288cb-149">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <span data-ttu-id="288cb-150">Script de verificação da conta</span><span class="sxs-lookup"><span data-stu-id="288cb-150">Account verification script</span></span>

<span data-ttu-id="288cb-151">Depois de criar a conta de dispositivo, você pode executar o seguinte script de verificação.</span><span class="sxs-lookup"><span data-stu-id="288cb-151">After creating the device account, you can run the following verification script.</span></span> <span data-ttu-id="288cb-152">Esse script valida uma conta de dispositivo criada anteriormente e produz um relatório resumido.</span><span class="sxs-lookup"><span data-stu-id="288cb-152">This script validates a previously-created device account and produces a summary report.</span></span> <span data-ttu-id="288cb-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="288cb-153">For example:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="288cb-154">Detalhes de configurações específicas não serão mostrados.</span><span class="sxs-lookup"><span data-stu-id="288cb-154">Details of specific settings will not be shown.</span></span>

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}
```

## <span data-ttu-id="288cb-155">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="288cb-155">Learn more</span></span>

- [<span data-ttu-id="288cb-156">Criar contas locais do Surface Hub 2S com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="288cb-156">Create Surface Hub 2S on-premises accounts with PowerShell</span></span>](surface-hub-2s-onprem-powershell.md)