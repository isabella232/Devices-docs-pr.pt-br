---
title: Redefinir ou recuperar um Surface Hub
description: Descreve os processos de redefinição e recuperação do Surface Hub e fornece instruções.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: redefinir o Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406604"
---
# <a name="reset-or-recover-a-surface-hub"></a>Redefinir ou recuperar um Surface Hub

Este artigo descreve como redefinir ou recuperar um Microsoft Surface Hub.  

[A redefinição do Surface Hub](#reset-a-surface-hub) retorna seu sistema operacional para a última atualização cumulativa do Windows e remove todos os arquivos de usuário locais e informações de configuração. As informações removidas incluem o seguinte:

- A conta do dispositivo
- Informações de conta para os administradores locais do dispositivo
- Informações de junção de domínio ou do Azure AD
- Informações de registro do Gerenciamento de Dispositivo Móvel (MDM)
- Informações de configuração definidas usando o MDM ou o aplicativo Configurações

[A recuperação de um Surface Hub da nuvem](#recover-a-surface-hub-from-the-cloud) também remove essas informações. Além disso, o Surface Hub baixa uma nova imagem do sistema operacional e a instala. Você pode especificar se o processo de recuperação preserva outras informações armazenadas no Surface Hub. A mesma imagem do sistema operacional é usada pela Ferramenta de Recuperação do [Surface Hub](surface-hub-recovery-tool.md) se você precisar recuperar um Surface Hub para o qual nenhuma dessas opções pode ser usada.

## <a name="reset-a-surface-hub"></a>Redefinir um Surface Hub

Talvez seja preciso redefinir o Surface Hub por motivos como:

- Você está repondo o dispositivo para um novo espaço de reunião e deseja reconfigurá-lo.
- Você deseja alterar como gerencia o dispositivo localmente.
- O nome de usuário ou a senha da conta do dispositivo ou da conta de Administrador foi perdido.
- Depois de instalar uma atualização, o desempenho do dispositivo diminui.

Durante o processo de redefinição, se você vir uma tela em branco por longos períodos de tempo, aguarde e não tome nenhuma ação.

> [!WARNING]
> O processo de redefinição do dispositivo pode levar até seis horas. Não desligue ou desconecta o Surface Hub até que o processo seja concluído. Se você interromper o processo, o dispositivo se tornará inoperável. O dispositivo requer serviço de garantia para se tornar funcional novamente.

1. No Surface Hub, abra **Configurações**.

   ![Imagem que mostra o aplicativo Configurações do Surface Hub.](images/sh-settings.png)

2. Selecione **Atualizar & Segurança**.

   ![Imagem que mostra o grupo Atualizar & Segurança no aplicativo Configurações do Surface Hub.](images/sh-settings-update-security.png)

3. Selecione **Recuperação**e, em **Redefinir dispositivo,** selecione **Iniciar**.

   > [!IMPORTANT]
   > Verifique se você tem sua chave BitLocker disponível antes de redefinir o dispositivo, pois você será solicitado mais tarde. Para saber mais, confira [Salvar a tecla BitLocker](save-bitlocker-key-surface-hub.md). Quando o Hub for reiniciado para a partição de recuperação, ele solicitará que você insira a chave BitLocker. Ignorar esse prompt fará com que a redefinição falhe.
   
   ![Imagem que mostra a opção Redefinir dispositivo no aplicativo Configurações do Surface Hub.](images/sh-settings-reset-device.png)

   Depois que o processo de redefinição terminar, o Surface Hub iniciará [o primeiro programa de executar](first-run-program-surface-hub.md) novamente. Se o processo de redefinição encontrar um problema, ele rola o Surface Hub de volta para a imagem do sistema operacional anteriormente existente e exibe a tela de boas-vindas.

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>Recuperar um Surface Hub da nuvem

Se, por algum motivo, o Surface Hub se tornar inutilizável, você ainda poderá recuperá-lo da nuvem sem ajuda do Suporte da Microsoft. O Surface Hub pode baixar uma nova imagem do sistema operacional da nuvem e usar essa imagem para reinstalar seu sistema operacional.

Você pode ter que usar esse tipo de processo de recuperação sob as seguintes circunstâncias:

- [O Surface Hub ou suas contas relacionadas entraram em um estado instável](#recover-a-surface-hub-in-a-bad-state)
- [O Surface Hub está bloqueado](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>O **processo Recuperar da nuvem** requer uma conexão com fio que fornece conectividade de internet aberta (sem proxy ou outros prompts de autenticação).

### <a name="recover-a-surface-hub-in-a-bad-state"></a>Recuperar um Surface Hub de um estado inválido

Se a conta do dispositivo entrar em um estado instável ou se a conta de administrador encontrar problemas, você poderá usar o aplicativo Configurações para iniciar o processo de recuperação na nuvem. Você só deve usar o processo de recuperação de nuvem quando o [processo de redefinição](#reset-a-surface-hub) do dispositivo não corrigir o problema.

1. No Surface Hub, selecione **Configurações** &gt; **Atualizar & recuperação de** &gt; **segurança.**

2. Em **Recuperar da nuvem,** selecione **Reiniciar agora**.

   ![recuperar da nuvem](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>Recuperar um Surface Hub bloqueado

Em raras ocasiões, o Surface Hub pode encontrar um erro durante a limpeza dos dados do usuário e do aplicativo no final de uma sessão. Quando isso acontece, o dispositivo reinicia automaticamente e tenta a operação novamente. Mas se essa operação falhar repetidamente, o dispositivo bloqueia automaticamente para proteger dados do usuário. Para desbloqueá-lo, você deve [redefinir o dispositivo](#reset-a-surface-hub) ou, se isso não funcionar, recuperá-lo da nuvem.

1. Localize a opção de energia na parte inferior do Surface Hub. A opção de energia está ao lado da conexão do cabo de alimentação. Para obter mais informações sobre a opção de energia, consulte o Guia de Preparação do [Site do Surface Hub (PDF)](surface-hub-site-readiness-guide.md).

2. Enquanto o Surface Hub exibe a tela de boas-vindas, use a opção de energia para desativar o Surface Hub.

3. Use a opção de energia para ativar novamente o Surface Hub. O dispositivo é iniciado e exibe a tela logotipo do Surface Hub. Quando você vir pontos giratórios sob o Logotipo do Surface Hub, use a opção de energia para desativar o Surface Hub novamente.  

4. Repita a etapa 3 três vezes ou até que o Surface Hub exibe a mensagem "Preparando Reparo Automático". Depois de exibir essa mensagem, o Surface Hub exibe a tela do Windows RE.

 
5. Selecione **Redefinir para instalar novamente o Windows**. 
![redefinir para reinstalar](images/recover-from-cloud.png)

8. Selecione **Baixar na nuvem.** 

   ![Download em nuvem](images/recover-cloud-download.png)

>[!IMPORTANT]
>Se você receber uma mensagem de erro indicando Não é possível **baixar,** selecione **Cancelar** e tente novamente.

9. Selecione **Limpar totalmente a unidade.**  
![ recuperar e limpar totalmente a unidade](images/recover-fully-clean-drive.png)

10. Você será solicitado **Você está pronto para redefinir este dispositivo?**. Selecione **Redefinir**. 
![recuperar e confirmar redefinição](images/recover-confirm-reset.png)

11. O download começa e o processo de recuperação indica **Redefinindo este dispositivo**. 
![recuperação mostrada em andamento](images/recover-in-progress.png)

## <a name="contact-support"></a>Contate o Suporte

Se você tiver dúvidas ou precisar de ajuda, poderá [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)
