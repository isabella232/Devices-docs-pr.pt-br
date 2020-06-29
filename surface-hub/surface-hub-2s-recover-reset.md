---
title: Redefinição e recuperação para Surface Hub 2S
description: Saiba como recuperar e redefinir o Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830431"
---
# Redefinição e recuperação para Surface Hub 2S

Se você encontrar problemas com o Surface Hub 2S, pode redefinir o dispositivo para configurações de fábrica ou restaurar usando uma unidade USB.

Para começar, entre no Surface Hub 2S com as credenciais de administrador, abra o aplicativo **configurações** , selecione **Atualizar & segurança**e, em seguida, selecione **recuperação**.

## Redefinir o dispositivo

1. Para redefinir o dispositivo **, selecione começar**.
2. Quando a janela **pronto para redefinir este dispositivo** for exibida, selecione **Redefinir**. 
  
  >[!NOTE]
  >Surface Hub 2S reinstala o sistema operacional da partição de recuperação. Isso pode levar até uma hora para ser concluído.
  
3. Para reconfigurar o dispositivo, execute o programa de instalação pela primeira vez.
4. Se você gerenciar o dispositivo usando o Microsoft Intune ou outra solução de gerenciamento de dispositivo móvel, desative e exclua o registro anterior e, em seguida, registre novamente o novo dispositivo. Para obter mais informações, consulte [remover dispositivos usando apagar, desativar ou cancelar o registro manual do dispositivo](https://docs.microsoft.com/intune/devices-wipe).

![* Redefinição e recuperação para Surface Hub 2S *](images/sh2-reset.png)<br>
*Figura 1. Redefinição e recuperação para Surface Hub 2S* 

## Recuperar o Surface Hub 2S usando uma unidade de recuperação USB

Novo no Surface Hub 2S, agora você pode reinstalar o dispositivo usando uma imagem de recuperação.

### Recuperação de uma unidade USB

Usando o Surface Hub 2S, você pode reinstalar o dispositivo usando uma imagem de recuperação. Ao fazer isso, você pode reinstalar o dispositivo nas configurações de fábrica se perdeu a chave do BitLocker ou se não tiver mais as credenciais de administrador para o aplicativo configurações.

>[!NOTE]
>Use uma unidade USB 3,0 com 8 GB ou 16 GB de armazenamento, formatada como FAT32.

1. Em um computador separado, baixe a imagem de recuperação de arquivo. zip do [site de recuperação de superfície](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) e, em seguida, retorne a estas instruções. 
1. Descompacte o arquivo baixado na raiz da unidade USB.  
1. Conecte a unidade USB a qualquer porta USB-C ou USB-A no Surface Hub 2S.
1. Desative o dispositivo:
   1. Mantenha pressionado o botão baixo volume, pressione o botão de energia.
   1. Mantenha os dois botões pressionados até ver o logotipo do Windows.
   1. Solte o botão de energia, mas continue a manter o volume até que a interface do usuário de instalação comece.

    ![* Use os botões baixo de volume e energia para iniciar a recuperação *](images/sh2-keypad.png) <br>
   **Figura 2. Botões de volume e energia**

1. Na tela seleção de idioma, selecione o idioma de exibição do Surface Hub 2S.
1. Selecione **recuperar de uma unidade** e **limpe completamente a unidade**e, em seguida, selecione **recuperar**. Se você for solicitado a fornecer uma chave BitLocker, selecione **ignorar esta unidade**. O Surface Hub 2S é reinicializado várias vezes e leva aproximadamente 30 minutos para concluir o processo de recuperação.

Quando a tela instalação inicial for exibida, remova a unidade USB.

## Contatar o Suporte

Se tiver dúvidas ou precisar de ajuda, você pode [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).
