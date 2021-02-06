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
# Criar uma conta de dispositivo usando a interface do usuário (Surface Hub v1)

 > [!NOTE]
 >Esta página inclui informações sobre o Surface Hub original (v1). Para o Surface Hub 2S, confira Criar conta de dispositivo do [Surface Hub 2S.](surface-hub-2s-account.md)

Se você preferir usar uma interface do usuário gráfica, poderá criar uma conta do dispositivo para seu Microsoft Surface Hub na [interface do usuário do Office 365](#create-device-acct-o365) ou no [Centro de Administração do Exchange](#create-device-acct-eac).

## <a href="" id="create-device-acct-o365"></a>Criar uma conta de dispositivo usando o Office 365


1.  [Crie a conta no Centro de administração do Microsoft 365.](#create-device-acct-o365-admin-ctr)
2.  [Criar uma política de caixa de correio de dispositivo móvel (ActiveSync) do Centro de administração do Microsoft Exchange](#create-device-acct-o365-mbx-policy).
3.  [Usar o PowerShell para concluir a criação de conta do dispositivo](#create-device-acct-o365-complete-acct).
4.  [Usar o PowerShell para configurar as propriedades da conta do Exchange](#create-device-acct-o365-configure-exch-prop).
5.  [Habilitar a conta com o Skype for Business](#create-device-acct-o365-skype-for-business).

### <a href="" id="create-device-acct-o365-admin-ctr"></a>Criar a conta no centro de administração

1.  Entrar no Office 365 visitando https://portal.office.com
2.  Forneça as credenciais de administrador para o seu locatário do Office 365. Isso levará você para o Centro de administração do Microsoft 365.

    ![Centro de administração do Microsoft 365.](images/setupdeviceaccto365-02.png)

3. No centro de administração, navegue até **Recursos** no painel esquerdo e clique em Salas & **equipamento.**

    ![Salas & de equipamento no Centro de administração](images/room-equipment.png)

4. Clique em **Adicionar** para criar uma nova conta de Sala. Insira um nome de exibição e endereço de e-mail para a conta, e depois clique em **Adicionar**.

    ![Criar nova janela de conta de sala](images/room-add.png)

5. Selecione a conta de Sala você acabou de criar na lista de Usuários ativos. No painel direito, você pode ver as propriedades da conta e diversas ações opcionais. Clique em **Redefinir senha** para alterar a senha e desmarque **Fazer com que esse usuário altere sua senha quando fizer logon pela primeira vez**, pois não é possível alterar a senha do fluxo de entrada do Surface Hub.

6. Na seção **Licença atribuída**, clique em **Editar** e, em seguida, clique na seta suspensa ao lado da licença apropriada para expandir os detalhes. Selecione um local de usuário e na lista de licenças, ative **Skype for Business Online (Plano 2)** e clique em **Salvar**. A licença pode variar de acordo com a organização (por exemplo, você pode ter o Plano 2 ou o Plano 3).

### <a href="" id="create-device-acct-o365-mbx-policy"></a>Criar uma política de caixa de entrada (ActiveSync) de dispositivo móvel a partir do Centro de Administração do Exchange

1.  No painel esquerdo do centro de administração, clique em **ADMIN**e, em seguida, clique em **Exchange**.

    ![centro de administração, mostrando usuários ativos do Exchange.](images/setupdeviceaccto365-08.png)

2.  Isso abrirá outra guia do navegador para levá-lo para o Centro de Administração do Exchange, onde você poderá criar e definir a Configuração de caixa de correio do Surface Hub.

    ![Centro de administração do Exchange.](images/setupdeviceaccto365-09.png)

3.  Para criar uma Política de Caixa de Entrada de Dispositivo Móvel, clique em **Dispositivo móvel** , no painel esquerdo e, em seguida, clique em **Políticas de caixa de entrada de dispositivo móvel**. Surface Hubs requerem uma conta com uma política de caixa de entrada de dispositivo móvel que não exija uma senha, portanto se você já tem uma política existente que corresponde a esse requisito, você pode aplicar essa política para a conta. Caso contrário, use as etapas a seguir para criar uma nova para ser usada somente para contas do dispositivo do Surface Hub.

    ![Centro de administração Exchange - criação de uma política de caixa de entrada de dispositivo móvel.](images/setupdeviceaccto365-10.png)

4.  Para criar uma nova política de caixa de entrada de dispositivo móvel do Surface Hub, clique no botão **+** nos controles acima da lista de políticas para adicionar uma nova política. Para o nome, forneça um nome que lhe ajudará a diferenciar essa política de outras contas do dispositivo (por exemplo, *SurfaceHubDeviceMobilePolicy*). Verifique se a política não exige uma senha para os dispositivos atribuídos, portanto, verifique se a opção **Exigir uma senha** permanece desmarcada, em seguida, clique em **Salvar**.

    ![Imagem mostrando a nova política de dispositivo móvel.](images/setupdeviceaccto365-11.png)

5.  Depois que você criou a nova política de caixa de correio de dispositivo móvel, volte para o **Centro de Administração do Exchange** e você verá a nova política listada.

    ![Imagem com a nova política de caixa de correio de dispositivo móvel no Centro de administração do Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>Use o PowerShell para concluir a criação de conta do dispositivo

A partir daqui, você precisará concluir o processo de criação de conta usando o PowerShell para definir algumas configurações.

Para executar cmdlets usados por esses scripts do PowerShell, o seguinte deve estar instalado no console de administração do PowerShell:

-   [Assistente de Sign-In microsoft online para profissionais de TI RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [Windows Azure Active Directory Module for Windows PowerShell](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366)

Instalar o seguinte módulo no Powershell
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### Conectando-se a serviços online

1.  Execute o Windows PowerShell como Administrador.

    ![Imagem mostrando como iniciar o Windows PowerShell e executar como administrador.](images/setupdeviceaccto365-17.png)

2.  Crie um Objeto Credenciais e, em seguida, crie uma nova sessão que se conecte ao Skype for Business Online. Forneça a conta de administrador locatário global e clique em **OK**.

    ![Imagem de solicitação de credenciais do Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  Para conectar-se ao Microsoft Online Services, execute:

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-19.png)

4.  Agora para conectar-se ao Skype for Business Online Services, execute:

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-20.png)

5.  Por fim, para conectar-se ao Exchange Online Services, execute:

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-21.png)

6.  Agora você tem que importar o Skype for Business Online Session e a sessão do Exchange Online que você acabou de criar, o que irá importar os comandos do Skype e Exchange para que possa usá-los localmente.

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    Observe que isso pode levar algum tempo para concluir.

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-22.png)

7.  Depois que estiver conectado aos serviços online, você precisará executar mais alguns cmdlets para configurar essa conta como uma conta do dispositivo do Surface Hub.

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>Use o PowerShell para configurar as propriedades do Exchange da conta

Agora que você está conectado aos serviços online, você pode concluir a configuração da conta do dispositivo. Você usará o endereço de email da conta do dispositivo para:

-   Alterar o tipo da caixa de entrada de regular para uma com mais espaço.
-   Definir a senha e habilitar a conta de caixa de entrada com mais espaço
-   Alterar várias propriedades do Exchange
-   Definir a senha da conta de usuário para que nunca expire.

1.  Você precisará inserir o endereço de email da conta e criar uma variável com esse valor:

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Para armazenar o valor obtido na caixa de entrada:

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Imprima o valor:

    ```powershell
    $strEmail
    ```

    Você verá o endereço de email correto.

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-23.png)

2. Execute o seguinte cmdlet:

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  Várias propriedades do Exchange podem ser definidas na conta do dispositivo para melhorar a experiência de reunião. Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Imagem mostrando o cmdlet do PowerShell.](images/setupdeviceaccto365-26.png)

5.  Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também. Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>Habilitar a conta com o Skype for Business

Habilite a conta de dispositivo com o Skype for Business.

Para habilitar o Skype for Business, seu ambiente precisará atender aos seguintes pré-requisitos:

-   Você precisará ter o Skype for Business Online Plano Autônomo 2 ou superior em seu plano do O365. O plano precisa dar suporte à funcionalidade de conferência.
-   Se você precisar do Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para o Surface Hub, precisará do Skype for Business Online Plano Autônomo 3.
-   Os usuários de locatário devem ter caixas de entrada do Exchange.
-   Sua conta do Surface Hub exige uma licença do Plano Autônomo 2 do Skype for Business Online ou do Plano Autônomo 3 do Skype for Business Online, mas não exige uma licença do Exchange Online.

1.  Comece criando uma sessão remota do PowerShell de um computador.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>Criar uma conta do dispositivo usando o Centro de Administração do Exchange

>[!NOTE]
>Esse método só funcionará se você estiver sincronizando de um Active Directory local.

Você pode usar o Centro de Administração do Exchange para criar uma conta do dispositivo:

1.  [Criar uma conta e uma caixa de correio com o Centro de Administração do Exchange](#create-device-acct-exch-admin-ctr).
2.  [Criar uma política de caixa de correio de dispositivo móvel no Centro de Administração do Exchange](#create-device-acct-exch-mbx-policy).
3.  [Usar o PowerShell para configurar a conta](#create-device-acct-exch-powershell-conf).
4.  [Habilitar a conta com o Skype for Business](#create-device-acct-exch-skype-for-business).

### <a href="" id="create-device-acct-exch-admin-ctr"></a>Criar uma conta e uma caixa de entrada com o Centro de Administração do Exchange

1.  Entrar no seu Centro de Administração do Exchange usando as credenciais de administrador do Exchange.
2.  Depois que você está no Centro de Administração do Exchange (EAT), navegue até **Destinatários** no painel esquerdo.

    ![Imagem mostrando caixas de entrada no Centro de administração do Exchange.](images/setupdeviceacctexch-01.png)

3.  Nos controles acima da lista de caixas de correio, escolha **+** para criar uma nova caixa e forneça um **Nome de exibição**, **Nome**, e **Nome de logon do usuário** e clique em **Salvar**.

    ![Imagem mostrando a criação de uma nova caixa de correio.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>Criar uma política de caixa de correio de dispositivo móvel a partir do Centro de Administração do Exchange.

>[!NOTE]
>Se você deseja criar e atribuir uma política à conta que você criou e está usando o Exchange 2010, procure as informações correspondentes sobre criação de política e atribuição de política ao usar o EMC (console de gerenciamento do Exchange).

 

1.  Vá até o Centro de Administração do Exchange.

    ![Imagem mostrando o Centro de administração do Exchange.](images/setupdeviceacctexch-03.png)

2.  Para criar uma política de caixa de entrada de dispositivo móvel, clique em **Dispositivo móvel** , no painel esquerdo e clique em **Políticas de caixa de entrada de dispositivo móvel**. Surface Hubs requerem uma conta com uma política de caixa de entrada de dispositivo móvel que não exija uma senha, portanto se você já tem uma política existente que corresponde a esse requisito, você pode aplicar essa política para a conta. Caso contrário, use as etapas a seguir para criar uma nova para ser usada somente para contas do dispositivo do Surface Hub.

    ![Imagem mostrando como usar o Centro de administração do Exchange para criar uma política de caixa de entrada de dispositivo móvel.](images/setupdeviceacctexch-05.png)

3.  Para criar uma nova política de caixa de entrada de conta do dispositivo móvel, clique no botão **+** nos controles acima da lista de políticas para adicionar uma nova política. Para o nome, forneça um nome que lhe ajudará a diferenciar essa política de outras contas do dispositivo (por exemplo, *SurfaceHubDeviceMobilePolicy*). A política de não deve ser protegida por senha, portanto, verifique se a opção **Exigir uma senha** permanece desmarcada, em seguida, clique em **Salvar**.

    ![Imagem mostrando a nova política de caixa de correio de dispositivo móvel.](images/setupdeviceacctexch-06.png)

4.  Depois que você criou a nova política de caixa de correio de dispositivo móvel, volte para o Centro de Administração do Exchange e você verá a nova política listada.

    ![Imagem mostrando nova política de caixa de correio de dispositivo móvel no Centro de administração do Exchange.](images/setupdeviceacctexch-07.png)

5.  Para aplicar a política do ActiveSync sem o uso do PowerShell, você pode fazer o seguinte:

    -   No EAC, clique em **Destinatários** &gt; **Caixas de correio** e selecione uma caixa de correio.

        ![Imagem mostrando o Centro de Administração do Exchange.](images/setupdeviceacctexch-08.png)

    -   No painel **Detalhes**, role a tela até **Telefone e Recursos de Voz** e clique em **Exibir detalhes** para exibir a tela **Detalhes do dispositivo móvel**.

        ![Imagem mostrando detalhes da caixa de correio.](images/setupdeviceacctexch-09.png)

    -   A política de caixa de correio de dispositivo móvel que atualmente é atribuída é exibida. Para alterar a política de caixa de correio de dispositivo móvel, clique em **Procurar**.

        ![Imagem mostrando a política de caixa de correio de dispositivo móvel atribuída no momento.](images/setupdeviceacctexch-10.png)

    -   Escolha a política de caixa de correio de dispositivo móvel apropriada da lista, clique em **OK** e, em seguida, clique em **Salvar**.

        ![Imagem mostrando uma lista de políticas de caixa de correio de dispositivos móveis.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>Use o PowerShell para configurar a conta

Agora que você está conectado aos serviços online, você pode concluir a configuração da conta do dispositivo. Você usará o endereço de email da conta do dispositivo para:

-   Alterar o tipo da caixa de entrada de regular para uma com mais espaço.
-   Alterar várias propriedades do Exchange
-   Definir a senha da conta de usuário para que nunca expire.

1.  Você precisará inserir o endereço de email da conta e criar uma variável com esse valor:

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Para armazenar o valor obtido na caixa de correio:

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Imprima o valor executando:

    ``` syntax
    $strEmail
    ```

    Você verá o endereço de email correto.

2.  Você precisa converter a conta em uma caixa de correio de sala, portanto, execute:

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  Afim de autenticar a conta do dispositivo em um Surface Hub, você precisa habilitar a conta da caixa de entrada com mais espaço e definir uma senha, para que a conta possa ser usada pelo dispositivo para obter informações da reunião usando o ActiveSync e fazer logon no Skype for Business.

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  Várias propriedades do Exchange podem ser definidas na conta do dispositivo para melhorar a experiência de reunião. Você pode ver quais propriedades precisam ser definidas na seção [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Agora, precisamos definir algumas propriedades no AD. Para fazer isso, você precisa do alias da conta (esta é a parte do nome UPN que precede o "@").

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  O usuário precisa estar habilitado no AD antes que ele possa autenticar com um Surface Hub. Executar:

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  Se você decidir que a senha não irá expirar, poderá defini-la com os cmdlets do PowerShell também. Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter mais informações.

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>Habilitar a conta com o Skype for Business

Habilite a conta de dispositivo com o Skype for Business.

Para habilitar o Skype for Business, seu ambiente precisará atender aos seguintes pré-requisitos:

- Você precisará ter o Skype for Business Online Plano Autônomo 2 ou superior em seu plano do O365. O plano precisa dar suporte à funcionalidade de conferência.
- Se você precisar do Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para o Surface Hub, precisará do Skype for Business Online Plano Autônomo 3.
- Os usuários de locatário devem ter caixas de entrada do Exchange.
- Sua conta do Surface Hub exige uma licença do Plano Autônomo 2 do Skype for Business Online ou do Plano Autônomo 3 do Skype for Business Online, mas não exige uma licença do Exchange Online.

1. Comece criando uma sessão remota do PowerShell de um computador.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. Recuperar o pool de registradores da conta do Surface Hub

Se você não souber qual valor usar para o parâmetro `RegistrarPool` em seu ambiente, poderá obter o valor de um usuário Skype for Business existente usando este cmdlet:

 ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
 ```

3. Para ativar sua conta do Surface Hub para o Skype for Business Server, execute este cmdlet:

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```