---
title: Implantação online ou híbrida usando o ambiente Skype Hybrid Voice (Surface Hub)
description: Este tópico explica como habilitar o Cloud PBX do Skype for Business com a conectividade PSTN local por meio do pool do Cloud Connector Edition ou do Skype for Business 2015.
keywords: Implantação híbrida, Skype Hybrid Voice
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831042"
---
# Implantação online ou híbrida usando o ambiente Skype Hybrid Voice (Surface Hub)

Este tópico explica como habilitar o Cloud PBX do Skype for Business com a conectividade PSTN (Rede Telefônica Pública Comutada) local por meio do pool do Cloud Connector Edition ou do Skype for Business 2015. Nesta opção. O pools domésticos do Skype for Business e os servidores Exchange estão na nuvem e são conectados por PSTN por meio de um pool local que executa o Skype for Business 2015 ou o Cloud Connector edition. [Saiba mais sobre as diferentes opções de Cloud PBX](https://technet.microsoft.com/library/mt612869.aspx).  

Se você tiver implantado o Cloud PBX do Skype for Business com uma das opções de voz híbrida, siga as etapas abaixo para habilitar a conta com mais espaço para o Surface Hub. É importante criar uma conta de usuário normal primeiro, atribuir todas as opções de voz híbrida e números de telefone e, em seguida, converter a conta em uma conta com mais espaço. Se você não seguir essa ordem, não poderá atribuir um número de telefone híbrido.  

>[!WARNING]
>Se você criar uma conta antes da configuração de voz híbrida (executar o comando Enable-CSMeetingRoom), não conseguirá configurar os parâmetros de voz híbrida necessários. Para configurar os parâmetros de voz híbrida para uma conta configurada anteriormente ou para reconfigurar um número de telefone, exclua a licença de complemento do E5 ou E3 + Cloud PBX e siga as etapas abaixo, a partir da etapa 3.

1. Crie uma nova conta de usuário para o Surface Hub. Este exemplo usa <strong> surfacehub2@adatum.com </strong> . A conta pode ser criada no Active Directory local e sincronizada com a nuvem, ou criada diretamente na nuvem. 

    ![novo usuário do objeto](images/new-user-hybrid-voice.png)

2. Selecione **A Senha Nunca Expira**. Isso é importante para um dispositivo Surface Hub.

   ![A senha nunca expira](images/new-user-password-hybrid-voice.png)

3. No Office 365, adicione a licença **E5** ou o complemento **E3 e Cloud PBX** à conta de usuário criada para o espaço. Isso é necessário para que o Hybrid Voice funcione.

   ![Adicionar licença de produto](images/product-license-hybrid-voice.png)

4. Aguarde aproximadamente 15 minutos até que a conta de usuário do espaço apareça no Skype for Business Online.

5. Depois que a conta de usuário do espaço for criada no Skype for Business Online, habilite-o para Hybrid Voice no PowerShell Remoto do Skype for Business executando o seguinte cmdlet:

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. Valide o fluxo de chamadas do Hybrid Voice inserindo chamadas de teste do Surface Hub.

7. Inicie uma sessão remota do PowerShell em um computador e conecte-se ao Exchange executando os cmdlets a seguir.

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. Após estabelecer uma sessão, modifique a conta de usuário do espaço para habilitá-lo como **RoomMailboxAccount** executando os cmdlets a seguir. Isso permite que a conta seja autenticada com o Surface Hub.

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. Após configurar a caixa de correio, você precisará criar uma nova política do Exchange ActiveSync ou usar uma política existente compatível.

   Os Surface Hubs só são compatíveis com contas de dispositivo que têm uma política de ActiveSync onde a propriedade **PasswordEnabled** é definida como **False**. Se isso não estiver definido corretamente, os serviços do Exchange no Surface Hub (email, calendário e ingresso em reuniões) não serão habilitados.
    
   Se você não criou uma política compatível ainda, use o cmdlet a seguir (este cria uma política chamada "Surface Hubs"). Depois que ela é criada, você pode aplicar a mesma política a outras contas de dispositivo.

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   Quando você tiver uma política compatível, precisará aplicar a política à conta de dispositivo. No entanto, as políticas só podem ser aplicadas a contas de usuário, e não a caixas de correio de recurso. Execute os cmdlets a seguir para converter a caixa de correio em um tipo de usuário, aplicar a política e, em seguida, convertê-la novamente em uma caixa de correio (talvez você precise reabilitar a conta e definir a senha novamente).
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. Várias propriedades do Exchange devem ser definidas na conta de dispositivo para melhorar a experiência de reunião. Você pode ver quais propriedades podem ser definidas em [Propriedades do Exchange](exchange-properties-for-surface-hub-device-accounts.md). Os cmdlets a seguir fornecem um exemplo de como definir propriedades do Exchange.

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. Habilite a caixa de correio como dispositivo de reunião no Skype for Business Online. Execute o seguinte cmdlet que habilita a conta como um dispositivo de reunião. 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    Como resultado da execução desse cmdlet, os usuários serão perguntados se eles estão em uma sala de reunião, conforme mostrado na imagem a seguir. **Sim** ativará o mudo do microfone e do alto-falante.

    ![](images/adjust-room-audio.png)


    
Nesse momento, a conta com mais espaço será totalmente configurada, incluindo o Hybrid Voice. Se você usar o Skype no local, poderá configurar atributos adicionais, como descrição, localização etc., no local. Se você criar um espaço no Skype Online, esses parâmetros poderão ser definidos online. 

Na imagem a seguir, veja como o dispositivo é exibido para os usuários.


![](images/select-room-hybrid-voice.png)
