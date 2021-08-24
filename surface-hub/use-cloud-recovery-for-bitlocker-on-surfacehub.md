---
title: Como usar a recuperação da nuvem para o BitLocker em um Surface Hub
description: Como usar a recuperação da nuvem para o BitLocker em um Surface Hub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Ajustes de acessibilidade, aplicativo Configurações, Facilidade de Acesso
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: e220be7d4613fcb6a14180e482dc4f2c66a5ddc8
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911026"
---
# <a name="summary"></a>Resumo

Este artigo descreve como usar a função de recuperação de nuvem se você for inesperadamente solicitado pelo BitLocker em um Surface Hub dispositivo.

> [!NOTE]
> Você deve seguir estas etapas somente se uma chave de recuperação do BitLocker não estiver disponível.

> [!WARNING]
> * Esse processo de recuperação exclui o conteúdo da unidade interna. Se o processo falhar, a unidade interna se tornará completamente inutilizável. Se isso ocorrer, você terá que registrar uma solicitação de serviço com a Microsoft para uma resolução.
> * Depois que o processo de recuperação for concluído, o dispositivo será redefinido para as configurações de fábrica e retornado para seu estado de experiência fora da caixa.
> * Após a recuperação, o Surface Hub deve ser completamente reconfigurado.

> [!IMPORTANT]
> Esse processo requer uma conexão de Internet aberta que não usa um proxy ou outro método de autenticação.

## <a name="cloud-recovery-process"></a>Processo de recuperação de nuvem

Para executar uma recuperação de nuvem, siga estas etapas:

1. Selecione **Pressionar Esc para obter mais opções de recuperação.**

   ![Captura de tela de Escape.](images/01-escape.png)

1. Selecione **Ignorar essa unidade**.

   ![Captura de tela de Ignorar essa unidade.](images/02-skip-this-drive.png)

1. Selecione **Recuperar da nuvem**.

   ![Captura de tela de Recuperar da nuvem.](images/03-recover-from-cloud.png)

1. Selecione **Sim**.

   ![Captura de tela de Sim.](images/04-yes.png)

1. Selecione **Reinstalar**.

   ![Captura de tela da Reinstalação.](images/05a-reinstall.png)

   ![Captura de tela de Download.](images/05b-downloading.png)

1. Depois que o processo de recuperação de nuvem for concluído, inicie a reconfiguração usando a **Experiência de**Saída.

   ![Captura de tela de Fora da Caixa.](images/06-out-of-box.png)

## <a name="something-went-wrong-error-message"></a>Mensagem de erro "Algo deu errado"

Esse erro geralmente é causado por problemas de rede que ocorrem durante o download de recuperação. Quando esse problema ocorrer, não desligue o Hub porque você não poderá reiniciá-lo. Se você receber essa mensagem de erro, retorne para a etapa "Recuperar da nuvem" e reinicie o processo de recuperação.

1. Selecione **Cancelar**.

   ![Captura de tela de Cancel.](images/07-cancel.png)

1. Selecione **Solucionar problemas**.

   ![Captura de tela de Solução de Problemas.](images/08-troubleshoot.png)

1. Selecione **Recuperar da nuvem**.

   ![Captura de tela de Recuperar da nuvem.](images/09-recover-from-cloud2.png)

1. Se o **erro da rede** Com fio não for encontrado, selecione **Cancelar**e, em seguida, permitir que a rede Surface Hub redescobrir a rede com fio.

   ![Captura de tela da rede Com fio não foi encontrada.](images/10-cancel.png)