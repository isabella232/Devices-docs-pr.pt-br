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
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830320"
---
# Resumo

Este artigo descreve como usar a função de recuperação de nuvem se você for avisado de forma inesperada pelo BitLocker em um dispositivo Surface Hub.

> [!NOTE]
> Você deve seguir estas etapas apenas se uma chave de recuperação do BitLocker não estiver disponível.

> [!WARNING]
> * Este processo de recuperação exclui o conteúdo da unidade interna. Se o processo falhar, a unidade interna ficará completamente inutilizável. Se isso ocorrer, será preciso registrar uma solicitação de serviço na Microsoft para obter uma solução.
> * Após a conclusão do processo de recuperação, o dispositivo será redefinido para as configurações de fábrica e retornado ao estado de experiência inicial do da caixa.
> * Após a recuperação, o Surface hub deve ser completamente reconfigurado.

> [!IMPORTANT]
> Esse processo requer uma conexão com a Internet aberta que não usa um método proxy ou outro método de autenticação.

##  <a name="cloud-recovery-process"></a>Processo de recuperação na nuvem

Para executar uma recuperação na nuvem, siga estas etapas:

1. Selecione **pressione ESC para obter mais opções de recuperação**.

   ![Captura de tela do escape](images/01-escape.png)

1. Selecione **ignorar esta unidade**.

   ![Captura de tela de ignorar esta unidade](images/02-skip-this-drive.png)

1. Selecione **recuperar na nuvem**.

   ![Captura de tela da recuperação da nuvem](images/03-recover-from-cloud.png)

1. Selecione **Sim**.

   ![Captura de tela de Sim](images/04-yes.png)

1. Selecione **reinstalar**.

   ![Captura de tela da reinstalação](images/05a-reinstall.png)

   ![Captura de tela do download](images/05b-downloading.png)

1. Após a conclusão do processo de recuperação na nuvem, inicie a reconfiguração usando a **experiência**inicial.

   ![Captura de tela da caixa de saída](images/06-out-of-box.png)

##  <a name="something-went-wrong-error-message"></a>Mensagem de erro "algo deu errado"

Geralmente, esse erro é causado por problemas de rede que ocorrem durante o download de recuperação. Quando esse problema ocorre, não desligue o Hub porque você não poderá reiniciá-lo. Se você receber essa mensagem de erro, retorne à etapa "recuperar da nuvem" e reinicie o processo de recuperação.

1. Selecione **Cancelar**.

   ![Captura de tela do cancelamento](images/07-cancel.png)

1. Selecione **solucionar problemas**.

   ![Captura de tela da solução de problemas](images/08-troubleshoot.png)

1. Selecione **recuperar na nuvem**.

   ![Captura de tela da recuperação da nuvem](images/09-recover-from-cloud2.png)

1. Se o erro **rede com fio não for encontrado** , selecione **Cancelar**e deixe o Surface Hub Redescubra a rede com fio.

   ![A captura de tela da rede com fio não é encontrada](images/10-cancel.png)