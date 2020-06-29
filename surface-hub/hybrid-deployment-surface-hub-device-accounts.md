---
title: Implantação híbrida (Surface Hub)
description: Uma implantação híbrida exige processamento especial para configurar uma conta de dispositivo para seu Microsoft Surface Hub.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: implantação híbrida, conta de dispositivo para o Surface Hub, Exchange hospedado no local, Exchange hospedado online
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830653"
---
# Implantação híbrida (Surface Hub)

Uma implantação híbrida exige processamento especial para configurar uma conta de dispositivo para seu Microsoft Surface Hub. Se você estiver usando uma implantação híbrida, em que sua organização possui uma combinação de serviços, com alguns hospedados no local e alguns hospedados online, sua configuração dependerá de onde cada serviço está hospedado. Este tópico aborda implantações híbridas para [Exchange hospedado no local](#exchange-on-premises), [Exchange hospedado online](#exchange-online), Skype for Business local, Skype for Business online e Skype for Business híbrido. Como existem muitas variações diferentes nesse tipo de implantação, não é possível fornecer instruções detalhadas para todos eles. O seguinte processo funciona para muitas configurações. Se o processo não estiver correto para sua instalação, recomendamos que você use o PowerShell (veja [Apêndice: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) para obter o mesmo resultado final documentado aqui e para outras opções de implantação. Em seguida, você deve usar o script de PowerShell fornecido para verificar a configuração do Surface Hub. (Veja [Script de verificação da conta](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)

> [!NOTE]
> Em um ambiente híbrido do Exchange, siga as etapas para [Exchange local](#exchange-on-premises). Para mover objetos do Exchange para o Office 365, use o cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .

## Exchange no local

Use este procedimento se você usar o Exchange no local.

1. Para este procedimento, você usará as ferramentas de administração do AD para adicionar um endereço de email à sua conta de domínio local. Essa conta será sincronizada com o Office 365.

- Na ferramenta do AD **Usuários e computadores do Active Directory** , clique com o botão direito do mouse na pasta ou unidade organizacional que suas contas do Surface Hub serão criadas e clique em **Nova**e **Usuário**.
- Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário** . Clique em **Avançar**.<p>

![Caixa Novo objeto para criar um novo usuário no Active Directory.](images/hybriddeployment-01a.png)

- Digite a senha dessa conta. Você precisará digitá-la novamente para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

> **Importante** Selecionar **A senha nunca expira** é um requisito para o Skype for Business no Surface Hub. As regras de domínio podem proibir senhas que não expiram. Nesse caso, você precisará criar uma exceção para cada conta de dispositivo do Surface Hub.

![Imagem mostrando caixa de diálogo de senha.](images/hybriddeployment-02a.png)

-   Clique em **Concluir** para criar a conta.

![Imagem com nome da conta, nome de logon e opções de senha para o novo usuário.](images/hybriddeployment-03a.png)

2. Habilite a caixa de correio remota.

Abra o Shell de gerenciamento do Exchange local com permissões de administrador e execute este cmdlet.

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> Se você não tiver um ambiente do Exchange no local para executar este cmdlet, você pode fazer as mesmas alterações diretamente para o objeto do Active Directory para a conta.
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType = -2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. Depois que você criar a conta, execute uma sincronização de diretório. Quando ele estiver concluído, vá para a página usuários no centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi mesclada para online.

4. Conecte-se ao Microsoft Exchange Online e defina algumas propriedades para a conta no Office 365.

Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Microsoft Exchange. Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.

As próximas etapas serão executadas em seu locatário do Office 365.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. Crie uma nova política do Exchange ActiveSync ou use uma política existente compatível.

Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.

Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como False. Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.

Se você não criou uma política compatível ainda, use o seguinte cmdlet — este cria uma política chamada "Surface Hubs". Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Depois que você tiver uma política compatível, será necessário aplicar a política à conta do dispositivo. 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. Defina as propriedades do Exchange.

Definindo propriedades do Exchange na conta de dispositivo para melhorar a experiência de reunião. Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. Conecte-se ao Azure AD.

Primeiro você precisa instalar o módulo do Azure AD para PowerShell versão 2. Em um prompt elevado do PowerShell, execute o seguinte comando:

```PowerShell
Install-Module -Name AzureAD
```

Você precisa conectar-se ao Azure AD para aplicar algumas configurações de conta. Você pode executar este cmdlet para se conectar.

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Atribua uma licença do Office 365.

A conta de dispositivo precisa ter uma licença válida do Office 365 (O365), ou o Exchange e o Skype for Business não funcionarão. Se você tiver a licença, deverá atribuir um local de uso à sua conta de dispositivo. Isso determina quais SKUs de licença estão disponíveis para sua conta.

Você pode usar `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para seu locatário do O365.

Depois de listar as SKUs, você precisará atribuir a SkuId que deseja para a variável `$License.SkuId`.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

Em seguida, você pode habilitar a conta de dispositivo com [Skype for Business Online](#skype-for-business-online), [Skype for Business local](#skype-for-business-on-premises) ou [Skype for Business híbrido](#skype-for-business-hybrid).

### Skype for Business Online

Para habilitar o Skype for Business online, os usuários de locatário devem ter caixas de entrada do Exchange (pelo menos uma caixa de entrada do Exchange no locatário é necessária). A tabela a seguir explica quais planos ou serviços adicionais você precisa.

| Cenário de sistema da sala Skype | Se você tiver o Office 365 Premium, os aplicativos da Microsoft 365 para empresas ou o plano autônomo 2 do Skype for Business, você precisará: | Se você tiver um plano baseado em empresa, você precisa: | Se você tiver o Skype for Business Server 2015 (local ou híbrido), precisará: |
| --- | --- | --- | --- |
| Ingressar em uma reunião agendada | Plano 1 autônomo do Skype for Business | E1, 3, 4 ou 5 | CAL do Skype for Business Server padrão |
| Iniciar uma reunião ad-hoc | Plano 2 autônomo do Skype for Business | E 1, 3, 4 ou 5 | CAL do Skype for Business Server Padrão ou CAL empresarial |
| Iniciar uma reunião ad hoc e discar de uma reunião para números de telefone | Plano autônomo 2 do Skype for Business para conferência de áudio</br></br>**Observação** a cobrança de consumo PSTN é opcional | E1 ou E3 com conferência de áudio ou e5| CAL do Skype for Business Server Padrão ou CAL empresarial |
| Dê ao grupo um número de telefone e faça ou receba chamadas do grupo ou ingresse em uma conferência de discagem rápida usando um número de telefone | Plano autônomo 2 do Skype for Business para o sistema telefônico e um plano de chamada de voz PSTN | E1 ou E3 com o sistema telefônico e um plano de chamada de voz PSTN ou e5 | CAL do Skype for Business Server Padrão ou Plus CAL |

A tabela a seguir lista as opções dos planos do Office 365 e do Skype for Business.

| Plano O365 | Skype for Business | Sistema telefônico | Conferência de áudio | Planos de chamada |
| --- | --- | --- | --- | --- |
| O365 Business Essentials | Incluído |  |  |  |
| O365 Business Premium | Incluído |  |  |  |
| E1 | Incluído | Complemento | Complemento | Complemento (requer complemento do sistema de telefonia) |
| E3 | Incluído | Complemento | Complemento | Complemento (requer complemento do sistema de telefonia) |
| E5 | Incluído | Incluído | Incluído | Complemento  |

1. Comece criando uma sessão remota do PowerShell de um computador para o ambiente do Skype for Business Online.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. Atribua a licença do Skype for Business à sua conta do Surface Hub.

 Depois de concluir as etapas anteriores para ativar sua conta do Surface Hub no Skype for Business Online, você deverá atribuir uma licença ao Surface Hub. Usando o portal administrativo do O365, atribua uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) ao dispositivo.

- Entre como um administrador de locatário, abra o Portal Administrativo do O365 e clique no aplicativo de administração.

- Clique em **Usuários e grupos** e em **Adicionar usuários, redefinir senhas e mais**.

- Clique na conta do Surface Hub e, em seguida, clique no ícone de caneta para editar as informações da conta.

- Clique em **Licenças**.

- Em **atribuir licenças**, selecione Skype for Business (plano 1) ou Skype for Business (plano 2), dependendo dos requisitos de licenciamento e Enterprise Voice. Você terá que usar uma licença do plano 2 se quiser usar o Enterprise Voice em seu Surface Hub.

- Clique em **Salvar**.

> [!NOTE]
> Você também pode usar o módulo Active Directory do Microsoft Azure para Windows Powershell para executar os cmdlets necessários para atribuir uma dessas licenças, mas isso não é abordado aqui.

Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business (PC, Android, etc.) para entrar nessa conta.

### Skype for Business local

Para executar este cmdlet, você precisará se conectar a um dos front-ends do Skype. Abra o Skype PowerShell e execute:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype for Business híbrido

Se sua organização tiver configurado [conectividade híbrida entre Skype for Business Server e Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), as diretrizes para a criação de contas serão diferentes de uma implantação padrão do Surface Hub.

O Surface Hub requer uma conta do Skype do tipo `meetingroom`, enquanto um usuário normal usaria uma conta de tipo de usuário no Skype. Se o servidor do Skype estiver configurado para híbrido onde você pode ter usuários no servidor do Skype local, bem como usuários hospedados no Office 365, você pode ter alguns problemas ao tentar criar uma conta do Surface Hub.

No ambiente híbrido do Skype for Business Server 2015, todos os usuários que você quiser no Skype for Business online devem ser criados primeiro na implantação local, para que a conta do usuário seja criada nos serviços de domínio do Active Directory. Em seguida, você pode mover o usuário para o Skype for Business online. A mudança de uma conta de usuário no local para online é feita por meio do cmdlet [move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Para mover um objeto Csmeetingroom, use o cmdlet [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Para usar o cmdlet Move-CsMeetingRoom, você deve ter instalado [o 6.0.9319.281 de atualização cumulativa de maio de 2017 para o Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [a atualização cumulativa de julho de 2017 5.0.8308.992 para o Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).


## Exchange Online

Use este procedimento se você usar o Exchange online.

1. Crie uma conta de email no Office 365.

Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange. Verifique se você tem as permissões corretas configuradas para execução dos cmdlets associados.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. Configurar uma caixa de correio.

Depois de estabelecer uma sessão, você criará uma nova caixa de correio e irá habilitá-la como um RoomMailboxAccount, ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta seja autenticada no Surface Hub.

Se você estiver alterando uma caixa de correio de recurso existente:

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Se você estiver criando uma nova caixa de correio de recurso:

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. Crie a política do Exchange ActiveSync.

Depois de configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.

Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como False. Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingressar em reuniões) não serão habilitados.

Se você não criou uma política compatível ainda, use o seguinte cmdlet — este cria uma política chamada "Surface Hubs". Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Depois que você tiver uma política compatível, será necessário aplicar a política à conta do dispositivo. No entanto, políticas só podem ser aplicadas a contas de usuário e não a caixas de correio de recurso. Você precisa converter a caixa de correio em um tipo de usuário, aplicar a política e, em seguida, convertê-la novamente em uma caixa de correio. Talvez você precise reativá-la e definir a senha novamente também.

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. Defina as propriedades do Exchange.

Várias propriedades do Exchange devem ser definidas na conta de dispositivo para melhorar a experiência de reunião. Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. Adicione um endereço de email para a sua conta de domínio local.

Para este procedimento, você usará as ferramentas de administração do AD para adicionar um endereço de email à sua conta de domínio local.

- Na ferramenta do AD **Usuários e computadores do Active Directory** , clique com o botão direito do mouse na pasta ou unidade organizacional que suas contas do Surface Hub serão criadas e clique em **Nova**e **Usuário**.
- Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário** . Clique em **Avançar**.

![Caixa Novo objeto para criar um novo usuário no Active Directory.](images/hybriddeployment-01a.png)

- Digite a senha dessa conta. Você precisará digitá-la novamente para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

> [!IMPORTANT]
> A seleção da **senha nunca expira** é um requisito para o Skype for Business no Surface Hub. As regras de domínio podem proibir senhas que não expiram. Nesse caso, você precisará criar uma exceção para cada conta de dispositivo do Surface Hub.

![Imagem mostrando caixa de diálogo de senha.](images/hybriddeployment-02a.png)

- Clique em **Concluir** para criar a conta.

![Imagem com nome da conta, nome de logon e opções de senha para o novo usuário.](images/hybriddeployment-03a.png)

6. Executar sincronização de diretório.

Depois que você criar a conta, execute uma sincronização de diretório. Quando terminar, vá para a página de usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.

7. Conecte-se ao Azure AD.

Primeiro você precisa instalar o módulo do Azure AD para PowerShell versão 2. Em um prompt elevado do PowerShell, execute o seguinte comando:

```PowerShell
Install-Module -Name AzureAD
```

Você precisa conectar-se ao Azure AD para aplicar algumas configurações de conta. Você pode executar esse cmdlet para se conectar:

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Atribua uma licença do Office 365.

A conta de dispositivo precisa ter uma licença válida do Office 365 (O365), ou o Exchange e o Skype for Business não funcionarão. Se você tiver a licença, deverá atribuir um local de uso à sua conta de dispositivo. Isso determina quais SKUs de licença estão disponíveis para sua conta.

Em seguida, você pode usar `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para seu locatário do O365.

Depois de listar as SKUs, você precisará atribuir a SkuId que deseja para a variável `$License.SkuId`.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

Em seguida, você pode habilitar a conta de dispositivo com [Skype for Business Online](#skype-for-business-online), [Skype for Business local](#skype-for-business-on-premises) ou [Skype for Business híbrido](#skype-for-business-hybrid).

### Skype for Business Online

Para habilitar o Skype for Business, seu ambiente deverá atender aos seguintes [pré-requisitos do Skype for Business Online](#skype-for-business-online).

1. Comece criando uma sessão remota do PowerShell para o ambiente do Skype for Business online de um computador.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. Atribuir a licença do Skype for Business à sua conta do Surface Hub

Depois de concluir as etapas anteriores para ativar sua conta do Surface Hub no Skype for Business Online, você deverá atribuir uma licença ao Surface Hub. Usando o portal administrativo do O365, atribua uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) ao dispositivo.

- Conecte-se como um administrador de locatário, abra o Portal Administrativo do O365 e clique no aplicativo de administração.

- Clique em **Usuários e grupos** e em **Adicionar usuários, redefinir senhas e mais**.

- Clique na conta do Surface Hub e, em seguida, clique no ícone de caneta para editar as informações da conta.

- Clique em **Licenças**.

- Em **Atribuir licenças**, selecione Skype for Business (Plano 2) ou o Skype for Business (Plano 3), dependendo de seus requisitos de licenciamento e de Enterprise Voice. Você terá que usar uma licença de Plano 3 se quiser usar Enterprise Voice no Surface Hub.

- Clique em **Salvar**.

> [!NOTE]
> Você também pode usar o módulo Active Directory do Microsoft Azure para Windows PowerShell para executar os cmdlets necessários para atribuir uma dessas licenças, mas isso não é abordado aqui.

Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business (PC, Android, etc) para entrar nessa conta.

### Skype for Business local

Para executar este cmdlet, você precisará se conectar a um dos front-ends do Skype. Abra o Skype PowerShell e execute:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype for Business híbrido

Se sua organização tiver configurado [conectividade híbrida entre Skype for Business Server e Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), as diretrizes para a criação de contas serão diferentes de uma implantação padrão do Surface Hub.

O Surface Hub requer uma conta do Skype do tipo *meetingroom*, enquanto um usuário normal usaria uma conta de tipo de *usuário* no Skype. Se o servidor do Skype estiver configurado para híbrido onde você pode ter usuários no servidor do Skype local, bem como usuários hospedados no Office 365, você pode ter alguns problemas ao tentar criar uma conta do Surface Hub.

No ambiente híbrido do Skype for Business Server 2015, todos os usuários que você quiser no Skype for Business online devem ser criados primeiro na implantação local, para que a conta do usuário seja criada nos serviços de domínio do Active Directory. Em seguida, você pode mover o usuário para o Skype for Business online. A mudança de uma conta de usuário no local para online é feita por meio do cmdlet [move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Para mover um objeto Csmeetingroom, use o cmdlet [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Para usar o cmdlet Move-CsMeetingRoom, você deve ter instalado [o 6.0.9319.281 de atualização cumulativa de maio de 2017 para o Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [a atualização cumulativa de julho de 2017 5.0.8308.992 para o Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).
