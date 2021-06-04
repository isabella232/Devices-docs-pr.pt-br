---
title: Redefinir e recuperar para o Surface Hub 2S
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
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342971"
---
# Redefinir e recuperar para o Surface Hub 2S

Se você tiver problemas com o Surface Hub 2S, poderá redefinir o dispositivo para as configurações de fábrica ou restaurá-lo usando uma unidade USB.

Para começar, entre no Surface Hub 2S com **** credenciais de administrador, abra o aplicativo Configurações, selecione **Atualizar**& segurança e, em seguida, selecione **Recuperação**.

##  <a name="reset-the-device"></a>Redefina o dispositivo

   > [!IMPORTANT]
   > Verifique se sua chave do BitLocker está disponível antes de redefinir o dispositivo, pois ela será solicitado posteriormente. Para saber mais, consulte [Salvar sua chave do BitLocker.](save-bitlocker-key-surface-hub.md)

1. Para redefinir o dispositivo, selecione **Começar.**

2. Quando a **janela Pronto para redefinir este dispositivo** for exibida, selecione **Redefinir**. 
  
   > [!IMPORTANT]
   > Quando o Hub for reiniciado para a partição de recuperação, ele solicitará que você insira a chave do BitLocker. Ignorar esse prompt causará falha na redefinição. Depois de inserir a chave do BitLocker, o Hub reinstala o sistema operacional a partir da partição de recuperação. Isso pode levar até uma hora para ser concluído.
  
3. Para reconfigurar o dispositivo, execute o programa de Instalação pela primeira vez.

4. Se você gerenciar o dispositivo usando o Microsoft Intune ou outra solução de gerenciamento de dispositivo móvel, retire e exclua o registro anterior e, em seguida, inscreva o novo dispositivo. Para obter mais informações, consulte Remover dispositivos usando apagar, retirar ou [desemrollar manualmente o dispositivo.](https://docs.microsoft.com/intune/devices-wipe)

   > [!div class="mx-imgBorder"]
   > ![*Redefinir e recuperar para o Surface Hub 2S*](images/sh2-reset.png)
   <br/>*Figura 1. Redefinir e recuperar para o Surface Hub 2S* 

##  <a name="recover-surface-hub-2s-by-using-a-usb-recovery-drive"></a>Recuperar o Surface Hub 2S usando uma unidade de recuperação USB

Novidade no Surface Hub 2S, agora você pode reinstalar o dispositivo usando uma imagem de recuperação.

###  <a name="recovery-from-a-usb-drive"></a>Recuperação de uma unidade USB

Usando o Surface Hub 2S, você pode reinstalar o dispositivo usando uma imagem de recuperação. Ao fazer isso, você pode reinstalar o dispositivo nas configurações de fábrica se tiver perdido a chave do BitLocker ou se não tiver mais credenciais de administrador para o aplicativo Configurações.

>[!NOTE]
>Use uma unidade USB 3.0 com 8 GB ou 16 GB de armazenamento, formatada como FAT32.

1. Em um computador separado, baixe a imagem de recuperação de arquivo .zip do [site do Surface Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) e retorne a essas instruções. 

1. Na caixa de pesquisa na **** barra de tarefas, insira a unidade de recuperação e selecione Criar uma unidade de **recuperação** ou Uma Unidade de **Recuperação** a partir dos resultados. Talvez seja necessário inserir uma senha de administrador ou confirmar sua escolha.

1. Na caixa **Controle de Conta de** Usuário, selecione **Sim**.

1. Certifique-se de limpar os **arquivos do sistema de back up para a caixa de** seleção de unidade de recuperação e, em seguida, selecione **Próximo**.

1. Selecione sua unidade USB e selecione **Próxima > Criar.**  Alguns utilitários precisam ser copiados para a unidade de recuperação, portanto, isso pode levar alguns minutos.

1. Quando a unidade de recuperação estiver pronta, selecione **Concluir**.

1. Clique duas vezes no arquivo .zip da imagem de recuperação que você baixou anteriormente para abri-lo.

1. Selecione todos os arquivos da pasta de imagem de **recuperação,** copie-os para a raiz da unidade USB e, em seguida, selecione Escolher para substituir os arquivos no destino.

1. Depois que os arquivos terminarem de copiar, selecione o ícone Remover **Hardware** e Ejetar Mídia com Segurança na barra de tarefas e remova sua unidade USB.

1. Conecte a unidade USB a qualquer porta USB-C ou USB-A no Surface Hub 2S.

1. Desligue o Hub e, em seguida, tome estas etapas para inicializar a partir da unidade USB:

   1. Enquanto pressiona o botão Aumentar o volume para baixo, pressione o botão Ligar/Desligar.
   1. Continue pressionando os dois botões até ver o logotipo do Windows.
   1. Solte o botão Ligar/Desligar, mas continue a manter o botão De volume para baixo até que a interface do usuário de instalação comece.

      ![*Use botões de baixo volume e ligar/desligar para iniciar a recuperação*](images/sh2-keypad.png)
      <br>*Figura 2. Botões Volume e Ligar/Desligar*

1. Na tela de seleção de idioma, selecione o idioma de exibição do Surface Hub 2S.

1. Selecione **Recuperar de uma unidade,** limpe totalmente a **unidade**e, em seguida, **selecione Recuperar.** Se você for solicitado a solicitar uma chave do BitLocker, selecione **Ignorar esta unidade.** O Surface Hub 2S reinicia várias vezes e leva aproximadamente 30 minutos para concluir o processo de recuperação.

Quando a tela de instalação pela primeira vez for exibida, remova a unidade USB.

##  <a name="contact-support"></a>Contate o Suporte

Se você tiver dúvidas ou precisar de ajuda, poderá [criar uma solicitação de suporte.](https://support.microsoft.com/supportforbusiness/productselection)
