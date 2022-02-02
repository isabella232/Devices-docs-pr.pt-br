---
title: Redefinir e recuperar para Surface Hub 2S
description: Saiba como recuperar e redefinir Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 6ba5677fabd3d309875cf339ec1432e99529b23b
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338084"
---
# <a name="reset-and-recovery-for-surface-hub-2s"></a>Redefinir e recuperar para Surface Hub 2S

Se você encontrar problemas com o Surface Hub 2S, poderá redefinir o dispositivo para as configurações de fábrica ou restaurar usando uma unidade USB.

Para começar, entre no Surface Hub 2S com credenciais de administrador, abra o aplicativo **Configurações**, selecione **Atualizar & segurança** e selecione **Recuperação**.

## <a name="reset-the-device"></a>Redefina o dispositivo

   > [!IMPORTANT]
   > Verifique se você tem sua chave BitLocker disponível antes de redefinir o dispositivo, pois você será solicitado mais tarde. Para saber mais, confira [Salvar a tecla BitLocker](save-bitlocker-key-surface-hub.md).

1. Para redefinir o dispositivo, **selecione Introdução**.

2. Quando a **janela Pronto para redefinir esse dispositivo** for exibida, selecione **Redefinir**.
  
   > [!TIP]
   > Quando o Hub for reiniciado para a partição de recuperação, ele solicitará que você insira a chave BitLocker. Ignorar esse prompt fará com que a redefinição falhe. Depois de inserir a chave BitLocker, o Hub reinstala o sistema operacional da partição de recuperação. Isso pode levar até uma hora para ser concluído.
  
3. Para reconfigurar o dispositivo, execute o programa de Instalação pela primeira vez.

4. Se você gerenciar o dispositivo usando Microsoft Intune ou outra solução de gerenciamento de dispositivo móvel, retire e exclua o registro anterior e, em seguida, re-inscreva o novo dispositivo. Para obter mais informações, [consulte Remove devices by using wipe, retire, or manually unenrolling the device](/intune/devices-wipe).

   > [!div class="mx-imgBorder"]
   > ![*Redefinir e recuperar para Surface Hub 2S*.](images/sh2-reset.png)
   <br/>*Figura 1. Redefinir e recuperar para Surface Hub 2S*

## <a name="recover-surface-hub-2s-by-using-a-usb-recovery-drive"></a>Recuperar Surface Hub 2S usando uma unidade de recuperação USB

Novo no Surface Hub 2S, agora você pode reinstalar o dispositivo usando uma imagem de recuperação.

### <a name="recovery-from-a-usb-drive"></a>Recuperação de uma unidade USB

Usando Surface Hub 2S, você pode reinstalar o dispositivo usando uma imagem de recuperação. Ao fazer isso, você pode reinstalar o dispositivo nas configurações de fábrica se perder a chave BitLocker ou se não tiver mais credenciais de administrador para o aplicativo Configurações.

>[!TIP]
>Use uma unidade USB 3.0 com 8 GB ou 16 GB de armazenamento, formatada como FAT32.

1. Em um computador separado, baixe .zip imagem de recuperação de arquivo do [site de Recuperação do Surface](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) e retorne para essas instruções.

2. Na caixa de pesquisa na barra de tarefas, insira a unidade **de** recuperação e selecione **Criar uma unidade** de recuperação ou **Unidade de Recuperação** a partir dos resultados. Talvez seja necessário inserir uma senha de administrador ou confirmar sua escolha.

3. Na caixa **Controle de Conta de Usuário** , selecione **Sim**.

4. Certifique-se de limpar a **caixa de seleção Fazer o back up de arquivos** do sistema na unidade de recuperação e selecione **Próximo**.

5. Selecione sua unidade USB e selecione Próximo > **Criar**.  Alguns utilitários precisam ser copiados para a unidade de recuperação, portanto, isso pode levar alguns minutos.

6. Quando a unidade de recuperação estiver pronta, selecione **Concluir**.

7. Clique duas vezes na imagem de recuperação .zip arquivo que você baixou anteriormente para abri-la.

8. Selecione todos os arquivos da pasta de imagem de recuperação, copie-os para a raiz da unidade USB e selecione Escolher para substituir **os arquivos no destino**.

9. Depois que os arquivos terminarem de copiar, selecione o ícone Remover Hardware e Ejetar **Mídia** com Segurança na barra de tarefas e remova sua unidade USB.

10. Conexão unidade USB para qualquer porta USB-C ou USB-A no Surface Hub 2S. Desativar o Hub e, em seguida, inicializar da unidade USB.

#### <a name="boot-surface-hub-from-usb-drive"></a>Inicialização Surface Hub da unidade USB

>[!NOTE]
>Se o dispositivo foi desconectado ou teve uma interrupção abrupta de energia ou cabo de alimentação puxada, aguarde pelo menos 15 segundos antes de tentar inicializar do USB.

1. Ao pressionar o botão Volume para baixo, pressione o botão Ligar.

2. Continue pressionando os dois botões até ver o logotipo Windows.

3. Solte o botão Ligar, mas continue a segurar o botão Volume para baixo até que a interface do usuário de instalação comece.

   ![*Use botões De volume para baixo e de energia para iniciar a recuperação*.](images/sh2-keypad.png)
   <br>*Figura 2. Botões Volume e Power*

4. Na tela de seleção de idioma, selecione o idioma de exibição do seu Surface Hub 2S.

5. Selecione **Recuperar de uma unidade e** **Limpe totalmente a unidade** e selecione **Recuperar**. Se você for solicitado a solicitar uma chave BitLocker, selecione **Ignorar essa unidade**. Surface Hub reinicializações do 2S várias vezes e pode levar uma hora ou mais para concluir o processo de recuperação.

6. Quando a tela de instalação pela primeira vez for exibida, remova a unidade USB.

## <a name="contact-support"></a>Contate o Suporte

Se você tiver dúvidas ou precisar de ajuda, poderá [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).
