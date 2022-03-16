---
title: Redefinir e recuperar para Surface Hub
description: Descreve os processos de redefinição e recuperação para o Surface Hub e fornece instruções.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: redefinir Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: f0292d4c2ec599ba620ab87930fbecf3bab9e078
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449274"
---
# <a name="reset-and-recovery-for-surface-hub"></a>Redefinir e recuperar para Surface Hub

Este artigo descreve como redefinir um Microsoft Surface Hub.  

[A redefinição do Surface Hub](#reset-a-surface-hub) retorna seu sistema operacional para a última atualização Windows cumulativa e remove todos os arquivos de usuário locais e informações de configuração. As informações removidas incluem o seguinte:

- A conta do dispositivo
- Informações de conta para os administradores locais do dispositivo
- Informações de junção de domínio ou do Azure AD
- Informações de registro do Gerenciamento de Dispositivo Móvel (MDM)
- Informações de configuração que foram definidas usando o MDM ou o Configurações app

Você pode especificar se o processo de recuperação preserva outras informações armazenadas no Surface Hub. Se a opção redefinir não puder ser usada, Surface Hub [Ferramenta](surface-hub-recovery-tool.md) de Recuperação estará disponível para reajustar o Surface Hub SSD diretamente.

## <a name="reset-a-surface-hub"></a>Redefinir um Surface Hub

Talvez seja preciso redefinir seu Surface Hub por motivos como:

- Você está recompondo o dispositivo para um novo espaço de reunião e deseja reconfigurá-lo.
- Você deseja alterar como gerencia o dispositivo localmente.

Durante o processo de redefinição, se você vir uma tela em branco por longos períodos de tempo, aguarde e não tome nenhuma ação.

> [!WARNING]
> O processo de redefinição do dispositivo pode levar até seis horas. Não desligue ou desconecta o Surface Hub até que o processo seja concluído. Se você interromper o processo, o dispositivo se tornará inoperável. O dispositivo requer serviço de garantia para se tornar funcional novamente.

1. No Surface Hub, abra **Configurações**.

   > [!div class="mx-imgBorder"]
   > ![Imagem que mostra Configurações aplicativo para Surface Hub.](images/sh-settings.png)

2. Selecione **Atualizar & Segurança**.

   > [!div class="mx-imgBorder"]
   > ![Imagem que mostra o grupo Update & Security no Configurações app para Surface Hub.](images/sh-settings-update-security.png)

3. Selecione **Recuperação** e, em **Redefinir dispositivo**, selecione **Iniciar**.

   > [!IMPORTANT]
   > Verifique se você tem sua chave BitLocker disponível antes de redefinir o dispositivo, pois você será solicitado mais tarde. Para saber mais, confira [Salvar a tecla BitLocker](save-bitlocker-key-surface-hub.md). Quando o Hub for reiniciado para a partição de recuperação, ele solicitará que você insira a chave BitLocker. Ignorar esse prompt fará com que a redefinição falhe.
   
   > [!div class="mx-imgBorder"]
   > ![Imagem que mostra a opção Redefinir dispositivo no Configurações app para Surface Hub.](images/sh-settings-reset-device.png)

   Depois que o processo de redefinição terminar, o Surface Hub iniciará [o primeiro programa de executar](first-run-program-surface-hub.md) novamente. Se o processo de redefinição encontrar um problema, ele rola o Surface Hub de volta para a imagem do sistema operacional anteriormente existente e exibe a tela de boas-vindas.

## <a name="recover-a-locked-surface-hub"></a>Recuperar um Surface Hub bloqueado

Se, por algum motivo, o Surface Hub se tornar inutilizável e você não conseguir iniciar uma redefinição do aplicativo Configurações, você ainda poderá redefinir o Surface Hub se tiver a chave de recuperação BitLocker.

1. Localize a opção de energia na parte inferior da Surface Hub. A opção de energia está ao lado da conexão do cabo de alimentação. Para obter mais informações sobre a opção de energia, consulte [Surface Hub Guia de Preparação do Site (PDF)](surface-hub-site-readiness-guide.md).

2. Enquanto o Surface Hub exibe a tela de boas-vindas, use o botão de energia para desativar o Surface Hub.

3. Use a opção de energia para Surface Hub ligar novamente. O dispositivo é iniciado e exibe a tela Surface Hub Logo. Quando você vir pontos giratórios sob o logotipo Surface Hub, use o botão de energia para desativar a Surface Hub novamente.  

4. Repita a etapa 3 duas vezes ou até que o Surface Hub exibe a mensagem "Preparando Reparo Automático". Depois de exibir essa mensagem, o Surface Hub exibe a tela Windows RE tela.
 
5. Selecione **Redefinir**.

6. Selecione **Reinstalação local.**

7. Selecione **Limpar totalmente a unidade.**
 
   ![recuperar e limpar completamente a unidade.](images/recover-fully-clean-drive.png)

8. Você será solicitado **Você está pronto para redefinir esse dispositivo?**. Selecione **Redefinir**. 
   
   ![recuperar e confirmar a redefinição.](images/recover-confirm-reset.png)


## <a name="contact-support"></a>Contate o Suporte

Se você tiver dúvidas ou precisar de ajuda, poderá [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)
