---
title: Redefinir ou recuperar um Surface Hub
description: Descreve os processos de redefinição e recuperação para o Surface Hub e fornece instruções.
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
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304814"
---
# Redefinir ou recuperar um Surface Hub

Este artigo descreve como redefinir ou recuperar um Microsoft Surface Hub.  

[A redefinição do Surface Hub](#reset-a-surface-hub) retorna seu sistema operacional para a última atualização cumulativa do Windows e remove todos os arquivos do usuário local e informações de configuração. As informações removidas incluem o seguinte:

- A conta do dispositivo
- Informações da conta dos administradores locais do dispositivo
- Informações de ingressar no domínio ou ingressar no Azure AD
- Informações de registro do Gerenciamento de Dispositivo Móvel (MDM)
- Informações de configuração que foram definidas usando o MDM ou o aplicativo Configurações

[A recuperação de um Surface Hub da nuvem](#recover-a-surface-hub-from-the-cloud) também remove essas informações. Além disso, o Surface Hub baixa uma nova imagem do sistema operacional e a instala. Você pode especificar se o processo de recuperação preserva outras informações armazenadas no Surface Hub. A mesma imagem do sistema operacional é usada pela Ferramenta de Recuperação do [Surface Hub](surface-hub-recovery-tool.md) se você precisar recuperar um Surface Hub para o qual nenhuma dessas opções pode ser usada.

## Redefinir um Surface Hub

Talvez seja preciso redefinir o Surface Hub por motivos como os seguintes:

- Você está reconfigurando o dispositivo para um novo espaço de reunião e deseja reconfigurá-lo.
- Você deseja alterar como gerencia o dispositivo localmente.
- O nome de usuário ou senha da conta de dispositivo ou da conta de Administrador foi perdido.
- Depois de instalar uma atualização, o desempenho do dispositivo diminui.

Durante o processo de redefinição, se você vir uma tela em branco por longos períodos de tempo, aguarde e não tome nenhuma ação.

> [!WARNING]
> O processo de redefinição do dispositivo pode levar até seis horas. Não desligue ou desconecta o Surface Hub até que o processo seja concluído. Se você interromper o processo, o dispositivo se tornará inoperante. O dispositivo requer o serviço de garantia para se tornar funcional novamente.

1. No Surface Hub, abra **Configurações**.

   ![Imagem que mostra o aplicativo Configurações do Surface Hub.](images/sh-settings.png)

2. Selecione **Atualizar & Segurança.**

   ![Imagem que mostra o grupo & Segurança no aplicativo Configurações do Surface Hub.](images/sh-settings-update-security.png)

3. Selecione **Recuperação**e, em **Redefinir dispositivo,** selecione **Começar.**

   > [!IMPORTANT]
   > Verifique se sua chave do BitLocker está disponível antes de redefinir o dispositivo, pois ela será solicitado posteriormente. Para saber mais, consulte [Salvar sua chave do BitLocker.](save-bitlocker-key-surface-hub.md) Quando o Hub for reiniciado para a partição de recuperação, ele solicitará que você insira a chave do BitLocker. Ignorar esse prompt causará falha na redefinição.
   
   ![Imagem que mostra a opção Redefinir dispositivo no aplicativo Configurações do Surface Hub.](images/sh-settings-reset-device.png)

   Depois que o processo de redefinição terminar, o Surface Hub iniciará [o programa de primeira duração](first-run-program-surface-hub.md) novamente. Se o processo de redefinição encontrar um problema, ele rola o Surface Hub de volta para a imagem do sistema operacional existente anteriormente e exibe a tela de boas-vindas.

<span id="cloud-recovery" />

## Recuperar um Surface Hub da nuvem

Se, por algum motivo, o Surface Hub se tornar inutilizável, você ainda poderá recuperá-lo da nuvem sem assistência do Suporte da Microsoft. O Surface Hub pode baixar uma imagem nova do sistema operacional da nuvem e usar essa imagem para reinstalar seu sistema operacional.

Talvez seja preciso usar esse tipo de processo de recuperação nas seguintes circunstâncias:

- [O Surface Hub ou suas contas relacionadas entraram em um estado instável](#recover-a-surface-hub-in-a-bad-state)
- [O Surface Hub está bloqueado](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>A **recuperação do processo de nuvem** requer uma conexão com fio que fornece conectividade aberta à Internet (sem proxy ou outros prompts de autenticação).

### Recuperar um Surface Hub de um estado inválido

Se a conta do dispositivo entrar em um estado instável ou se a conta de administrador encontrar problemas, você poderá usar o aplicativo Configurações para iniciar o processo de recuperação na nuvem. Você só deve usar o processo de recuperação na nuvem quando o [processo de redefinição](#reset-a-surface-hub) do dispositivo não corrigir o problema.

1. No Surface Hub, selecione **Atualização de Configurações** &gt; **& recuperação de** &gt; **segurança.**

2. Em **Recuperar da nuvem,** selecione **Reiniciar agora.**

   ![recuperar da nuvem](images/recover-from-the-cloud.png)

### Recuperar um Surface Hub bloqueado

Em raras ocasiões, o Surface Hub pode encontrar um erro durante a limpeza dos dados do usuário e do aplicativo no final de uma sessão. Quando isso acontece, o dispositivo reinicia automaticamente e tenta a operação novamente. Mas se essa operação falhar repetidamente, o dispositivo será automaticamente protegido para proteger os dados do usuário. Para desbloqueá-lo, [você deve redefinir o](#reset-a-surface-hub) dispositivo ou, se isso não funcionar, recuperá-lo da nuvem.

1. Localize o switch de energia na parte inferior do Surface Hub. O botão de energia fica ao lado da conexão do cabo de alimentação. Para obter mais informações sobre a opção de energia, consulte o Guia de Preparação do Site do [Surface Hub (PDF).](surface-hub-site-readiness-guide.md)

2. Enquanto o Surface Hub exibe a tela de boas-vindas, use o botão de energia para desligar o Surface Hub.

3. Use o botão ligar/desligar para rea ligar o Surface Hub. O dispositivo é iniciado e exibe a tela de logotipo do Surface Hub. Quando você vir pontos giratórios sob o Logotipo do Surface Hub, use o botão de energia para desligar o Surface Hub novamente.  

4. Repita a etapa 3 três vezes ou até que o Surface Hub exibe a mensagem "Preparando o reparo automático". Depois de exibir essa mensagem, o Surface Hub exibe a tela do Windows RE.

5. Selecione **Opções Avançadas.**

6. Selecione **Recuperar da nuvem.** (Opcionalmente, você pode selecionar **Redefinir**. No entanto, **recuperar da nuvem** é a abordagem recomendada.)

   ![Recuperar da nuvem](images/recover-from-cloud.png)
7. Se você for solicitado a inserir a chave do Bitlocker, faça o seguinte:

   - Para preservar as informações que o Bitlocker protege no Surface Hub, insira a chave do Bitlocker.
   - Para descartar as informações protegidas, selecione **Ignorar esta unidade**  

8. Quando você for solicitado, selecione **Reinstalar.**

    ![Reinstalar](images/reinstall.png)

9. Para reparticionar o disco, selecione **Sim**.

   ![Reparticionar](images/repartition.png)

   Primeiro, o processo de recuperação baixa a imagem do sistema operacional da nuvem.  

   ![baixando 97&](images/recover-progress.png)

   Quando o download terminar, o processo de recuperação restaura o Surface Hub de acordo com as opções selecionadas.
   

## Contate o Suporte

Se você tiver dúvidas ou precisar de ajuda, poderá [criar uma solicitação de suporte.](https://support.microsoft.com/supportforbusiness/productselection)


## Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)
