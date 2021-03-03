---
title: Criar conta de dispositivo do Surface Hub 2S
description: Esta página descreve o procedimento para criar a conta do dispositivo Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/18/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3afd4115ff4bd22a84f9a5fb86ceb6805c347f8a
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385219"
---
# <a name="create-surface-hub-2s-device-account"></a>Criar conta de dispositivo do Surface Hub 2S

A criação de uma conta de dispositivo surface hub (também conhecida como caixa de correio de sala) permite que o Surface Hub 2S receba, aprove ou decline solicitações de reunião e participe de reuniões. Configure a conta do dispositivo durante a configuração do OOBE (Experiência Inicial). Se necessário, você pode alterá-lo mais tarde (sem passar pela configuração OOBE).

Você pode criar a conta do Centro de administração do Microsoft 365 em combinação com Windows PowerShell: 

- **Criar conta por meio do Centro de administração**. Para atender aos requisitos mínimos, você pode configurar tudo o que precisa para a conta diretamente do centro de administração [do Microsoft 365.](https://admin.microsoft.com/AdminPortal) Alguns recursos, como o compartilhamento de whiteboards diretamente do aplicativo de quadro de trabalho, exigem o uso do PowerShell para configurar o ActiveSync; consulte [Habilitar ActiveSync se o uso do aplicativo de email for necessário](#enable-activesync-if-use-of-email-app-is-required) nesta página.

- **Criar conta por meio do PowerShell**. Você pode usar scripts do PowerShell para facilitar a criação de várias contas de dispositivo e configurar rapidamente recursos específicos, incluindo:
    - Processamento de calendário para cada conta de dispositivo Surface Hub.
    - Respostas automáticas personalizadas a solicitações de agendamento.
    - Se a política de caixa de correio do ActiveSync padrão já tiver sido modificada por outra pessoa ou por outro processo, você provavelmente terá que criar e atribuir uma nova política de caixa de correio activeSync.

> [!TIP]
> Você pode verificar a configuração da conta executando o script de verificação [de conta abaixo.](#account-verification-script)

> [!NOTE]  
> A conta de dispositivo Surface Hub não dá suporte a FIPs (Provedores de Identidade Federadas) de terceiros e deve ser uma conta padrão do Active Directory ou do Azure Active Directory.

## <a name="create-account-via-admin-center"></a>Criar conta por meio do centro de administração

1. No Centro de administração do Microsoft 365, vá para **Recursos** e escolha **Salas & Equipamento** e selecione + Adicionar **recurso**.

2. Forneça um nome e um endereço de email para a conta do dispositivo. Deixe as configurações restantes inalteradas no estado padrão.

   ![Fornecer um nome e um endereço de email](images/sh2-account2.png)

   ![Deixar as configurações restantes inalteradas no estado padrão](images/sh2-account3.png)

3. De definir a senha da conta do dispositivo. Para definir a senha, escolha **Usuários** e selecione **Usuários ativos**. Agora procure o usuário recém-criado para definir a senha. Certifique-se **de não selecionar** a opção Fazer com que esse usuário **altere a senha ao entrar pela primeira vez.**

   ![Definir a senha da conta de dispositivo](images/sh2-account4.png)

4. Atribua a sala com uma licença do Office 365. É recomendável atribuir a licença da **** Sala de Reunião do Office 365, que habilita automaticamente a conta para o Microsoft Teams e o Skype for Business.

   ![Atribuir licença do Office 365](images/sh2-account5.png)


> [!NOTE]  
> Se estiver usando o Skype for Business, você precisará finalizar a instalação por meio do PowerShell -- Calendário do Skype for Business: Definir o [Autoprocessamento](#set-calendar-auto-processing-skype-for-business-only) de Calendário para essa conta. 

## <a name="create-account-via-powershell"></a>Criar conta por meio do PowerShell

 Usar o PowerShell para automatizar rapidamente tarefas no Surface Hub não exige necessariamente a experiência do PowerShell. Verifique se você concluiu os pré-requisitos de instalação antes de usar os scripts apropriados nesta página.

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a>Pré-requisitos para usar o PowerShell para gerenciar o Surface Hub 

1. Iniciar o PowerShell com privilégios de conta elevados ( Executar como**Administrador**) e garantir que seu sistema está configurado para executar scripts do PowerShell. Para saber mais, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Instalar o módulo do Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).


### <a name="connect-to-exchange-online-powershell"></a>Conectar-se ao PowerShell do Exchange Online

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a>Criar caixa de correio

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a>Definir o processamento automático do calendário (somente Skype for Business)

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a>Habilitar ActiveSync se o uso do aplicativo de email for necessário

 A Política ActiveSync padrão funcionará se não for alterada. Caso contrário, crie uma nova Política e atribua.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a>Conecte-se ao Azure AD

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a>Atribuir uma licença

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a>Verifique se há licenças disponíveis

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a>Script de verificação da conta

Depois de criar a conta de dispositivo, você pode executar o seguinte script de verificação. Esse script valida uma conta de dispositivo criada anteriormente e produz um relatório de resumo. Por exemplo:

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

Detalhes de configurações específicas não serão mostrados.

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

## <a name="learn-more"></a>Saiba mais

- [Criar contas locais do Surface Hub 2S com o PowerShell](surface-hub-2s-onprem-powershell.md)