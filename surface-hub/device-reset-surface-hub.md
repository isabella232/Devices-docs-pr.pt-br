---
title: Redefinir ou recuperar um Surface Hub
description: Descreve os processos de restauração e recuperação do Surface Hub e fornece instruções.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: redefinir o Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: c5cf643d0f4a68344bb098916a909dd66e1dac9b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830673"
---
# Redefinir ou recuperar um Surface Hub

Este artigo descreve como redefinir ou recuperar um hub Surface Hub da Microsoft.  

[Redefinir o Surface Hub](#reset-a-surface-hub) retorna o sistema operacional para a última atualização cumulativa do Windows e remove todos os arquivos de usuários locais e informações de configuração. As informações que são removidas incluem o seguinte:

- A conta do dispositivo
- Informações da conta para administradores locais do dispositivo
- Informações de ingresso em domínio ou ingressar no Azure AD
- Informações de inscrição no gerenciamento de dispositivo móvel (MDM)
- Informações de configuração que foram definidas usando o MDM ou o aplicativo configurações

[Recuperar um Surface Hub da nuvem](#recover-a-surface-hub-from-the-cloud) também remove essas informações. Além disso, o Surface Hub baixa uma nova imagem do sistema operacional e a instala. Você pode especificar se o processo de recuperação preserva outras informações armazenadas no Surface Hub.

## Redefinir um Surface Hub

Pode ser necessário redefinir o Surface Hub por motivos como os seguintes:

- Você está redirecionando o dispositivo para um novo espaço de reunião e deseja reconfigurá-lo.
- Você deseja alterar como gerencia o dispositivo localmente.
- O nome de usuário ou a senha da conta do dispositivo ou da conta de administrador foi perdida.
- Após a instalação de uma atualização, o desempenho do dispositivo diminui.

Durante o processo de redefinição, se você vir uma tela em branco por longos períodos de tempo, aguarde e não execute nenhuma ação.

> [!WARNING]
> O processo de redefinição do dispositivo pode levar até seis horas. Não desligue ou desconecte o Surface Hub até que o processo seja concluído. Se você interromper o processo, o dispositivo se torna inoperante. O dispositivo requer serviço de garantia para se tornar funcional novamente.

1. No Surface Hub, abra **Configurações**.

   ![Imagem que mostra o aplicativo configurações para Surface Hub.](images/sh-settings.png)

1. Selecione **atualizar & segurança**.

   ![Imagem que mostra a atualização & grupo de segurança no aplicativo configurações para Surface Hub.](images/sh-settings-update-security.png)

1. Selecione **recuperação**e, em seguida, em **Redefinir dispositivo**, selecione **introdução**.

   ![Imagem que mostra a opção redefinir dispositivo no aplicativo configurações para Surface Hub.](images/sh-settings-reset-device.png)

   Após a conclusão do processo de redefinição, o Surface Hub iniciará o [programa de primeira execução](first-run-program-surface-hub.md) novamente. Se o processo de redefinição encontrar um problema, ele volta ao Surface Hub para a imagem do sistema operacional existente e, em seguida, exibe a tela de boas-vindas.

<span id="cloud-recovery" />

## Recuperar um Surface Hub da nuvem

Se, por algum motivo, o Surface Hub se tornar inutilizável, você ainda poderá recuperá-lo da nuvem sem assistência do suporte da Microsoft. O Surface Hub pode baixar uma imagem do sistema operacional nova da nuvem e usar essa imagem para reinstalar o sistema operacional.

Talvez seja necessário usar esse tipo de processo de recuperação nas seguintes circunstâncias:

- [O Surface Hub ou suas contas relacionadas digitaram um estado instável](#recover-a-surface-hub-in-a-bad-state)
- [O Surface Hub está bloqueado](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>A **recuperação do** processo na nuvem requer uma conexão com a Internet aberta (sem proxy ou outras autenticação). É recomendável uma conexão Ethernet.

### Recuperar um Surface Hub de um estado inválido

Se a conta do dispositivo ficar em um estado instável ou se a conta de administrador encontrar problemas, você poderá usar o aplicativo configurações para iniciar o processo de recuperação na nuvem. Você só deve usar o processo de recuperação na nuvem quando o processo de [redefinição do dispositivo](#reset-a-surface-hub) não corrigir o problema.

1. Em seu Surface Hub, selecione **Settings** &gt; **Atualizar configurações &** &gt; **recuperação**de segurança.

1. Em **recuperar da nuvem**, selecione **reiniciar agora**.

   ![recuperar da nuvem](images/recover-from-the-cloud.png)

### Recuperar um Surface Hub bloqueado

Em raras ocasiões, o Surface Hub pode encontrar um erro durante a limpeza dos dados do usuário e do aplicativo no final de uma sessão. Quando isso acontece, o dispositivo é reiniciado automaticamente e tenta a operação novamente. Mas se essa operação falhar repetidamente, o dispositivo será bloqueado automaticamente para proteger os dados do usuário. Para desbloqueá-lo, você deve [redefinir o dispositivo](#reset-a-surface-hub) ou, se isso não funcionar, recuperá-lo da nuvem.

1. Localize a chave de energia na parte inferior do Surface Hub. O botão liga/desliga está ao lado da conexão do cabo de alimentação. Para obter mais informações sobre o botão de ligar, consulte o [Guia de preparação de site do Surface Hub (PDF)](surface-hub-site-readiness-guide.md).

1. Enquanto o Surface Hub exibe a tela de boas-vindas, use o botão de energia para desativar o Surface Hub.

1. Use o botão de ligar para ligar o Surface Hub novamente. O dispositivo é iniciado e exibe a tela do logotipo do Surface Hub. Quando você vir os pontos de rotação sob o logotipo do Surface Hub, use o botão de ligar para desligar o Surface Hub novamente.  

1. Repita a etapa 3 3 vezes, ou até que o Surface Hub exiba a mensagem "preparando reparo automático". Depois de exibir essa mensagem, o Surface Hub exibe a tela do Windows RE.

1. Selecione **Opções avançadas**.

1. Selecione **recuperar na nuvem**. (Opcionalmente, você pode selecionar **Redefinir**. No entanto, a **recuperação da nuvem** é a abordagem recomendada.)

   ![Recuperar da nuvem](images/recover-from-cloud.png)
1. Se for solicitado a inserir a chave do BitLocker, siga um destes procedimentos:

   - Para preservar as informações que o BitLocker protege no Surface Hub, insira a chave do BitLocker.
   - Para descartar as informações protegidas, selecione **ignorar esta unidade**  

1. Quando solicitado, selecione **reinstalar**.

    ![Reinstalar](images/reinstall.png)

1. Para reparticionar o disco, selecione **Sim**.

   ![Reparticionar](images/repartition.png)

   Primeiro, o processo de recuperação baixa a imagem do sistema operacional da nuvem.  

   ![baixando 97&](images/recover-progress.png)

   Quando o download terminar, o processo de recuperação restaura o Surface Hub de acordo com as opções que você selecionou.
   

## Contatar o Suporte

Se tiver dúvidas ou precisar de ajuda, você pode [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).


## Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)
