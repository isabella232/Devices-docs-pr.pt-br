---
title: Desemrollar dispositivos Surface do SEMM (Surface)
description: Saiba como desempacodar um dispositivo do SEMM usando um pacote de redefinição uefi do Surface ou a opção Solicitação de Recuperação.
keywords: gerenciamento do surface enterprise
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 8584ae4ade7d7a043438206230cb24d146b586cb
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911666"
---
# <a name="unenroll-surface-devices-from-semm"></a>Cancelar o registro de dispositivos Surface no SEMM

Quando um dispositivo Surface é inscrito no Surface Enterprise Modo de Gerenciamento (SEMM), um certificado é armazenado no firmware desse dispositivo. A presença desse certificado e o registro no SEMM impedem alterações não autorizadas nas configurações ou opções do Surface UEFI enquanto o dispositivo está inscrito no SEMM. Para restaurar o controle das configurações uefi do Surface para o usuário, o dispositivo Surface deve ser desempacodado do SEMM, um processo às vezes descrito como redefinição ou recuperação. Há dois métodos que você pode usar para desempacorar um dispositivo do SEMM — um pacote de redefinição uefi do Surface e uma solicitação de recuperação.

>[!WARNING]
>Para desempacodar um dispositivo do SEMM e restaurar o controle do usuário das configurações uefi do Surface, você deve ter o certificado SEMM que foi usado para registrar o dispositivo no SEMM. Se esse certificado for perdido ou corrompido, não será possível desempacar do SEMM. Fazer o back-up e proteger seu certificado SEMM de acordo.

Para obter mais informações sobre o SEMM, consulte [Microsoft Surface Enterprise Modo de Gerenciamento.](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)

## <a name="unenroll-a-surface-device-from-semm-with-a-surface-uefi-reset-package"></a>Desempacodar um dispositivo Surface do SEMM com um pacote de redefinição uefi do Surface

O pacote de redefinição uefi do Surface é o método principal que você usa para desempacorar um dispositivo Surface do SEMM. Como um pacote de configuração UEFI do Surface, o pacote de redefinição é um arquivo Windows (.msi) que configura o SEMM no dispositivo. Ao contrário do pacote de configuração, o pacote de redefinição irá redefinir a configuração uefi do Surface em um dispositivo Surface para suas configurações padrão, remover o certificado SEMM e desempacodá-lo do SEMM.

Os pacotes de redefinição são criados especificamente para um dispositivo Surface individual. Para começar o processo de criação de um pacote de redefinição, você precisará do número de série do dispositivo que deseja desemrollar, bem como o certificado SEMM usado para registrar o dispositivo. Você pode encontrar o número de série do dispositivo Surface na página de informações do **computador** do Surface UEFI, conforme mostrado na Figura 1. Esta página será exibida mesmo se o Surface UEFI estiver protegido por senha e a senha incorreta for inserida.

![O número de série do dispositivo Surface é exibido.](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*Figura 1. O número de série do dispositivo Surface é exibido na página de informações do computador UEFI surface*

>[!NOTE]
>Para inicializar no Surface UEFI, pressione **Volume Up** e **Power** simultaneamente enquanto o dispositivo está desligado. Mantenha **o volume para cima** até que o logotipo do Surface seja exibido e o dispositivo comece a ser inicializado.

Para criar um pacote de redefinição uefi do Surface, siga estas etapas:

1. Abra o Configurador UEFI do Microsoft Surface a partir do menu Iniciar.
2. Clique em **Iniciar**.
3. Clique **em Redefinir Pacote**, conforme mostrado na Figura 2.

   ![Selecione Redefinir Pacote para criar um pacote para desemrollar o dispositivo Surface a partir do SEMM.](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *Figura 2. Clique em Redefinir Pacote para criar um pacote para desemrollar um dispositivo Surface do SEMM*

4. Clique **em Proteção de Certificado** para adicionar seu arquivo de certificado SEMM com chave privada (.pfx), conforme mostrado na Figura 3. Navegue até o local do arquivo de certificado, selecione o arquivo e clique em **OK**.

   ![Adicione o certificado SEMM ao pacote de redefinição uefi do Surface.](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *Figura 3. Adicionar o certificado SEMM a um pacote de redefinição uefi do Surface*

5. Clique em **Avançar**.
6. Digite o número de série do dispositivo que você deseja desempacorar do SEMM (conforme mostrado na Figura 4) e clique em **Criar** para gerar o pacote de redefinição uefi do Surface.

   ![Crie um pacote de redefinição uefi do Surface com o número de série do dispositivo Surface.](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *Figura 4. Use o número de série do dispositivo Surface para criar um pacote de redefinição uefi do Surface*

7. Na caixa **de diálogo Salvar como,** especifique um nome para o pacote de redefinição uefi do Surface, navegue até o local onde você gostaria de salvar o arquivo e clique em **Salvar**.
8. Quando a geração do pacote é concluída, a página **Bem-sucedida** é exibida. Clique **em Fim** para concluir a criação do pacote e feche o Configurador UEFI do Microsoft Surface.

Execute o pacote de redefinição do Surface UEFI Windows o arquivo instalador (.msi) no dispositivo Surface para desempacodar o dispositivo do SEMM. O pacote de redefinição exigirá uma reinicialização para executar a operação de desempaco. Depois que o dispositivo for desemrollado, você poderá verificar a remoção bem-sucedida garantindo que o item pacote de configuração do **Microsoft Surface** em Programas e Recursos **(mostrado** na Figura 5) não está mais presente.

![A tela que mostra que o dispositivo está inscrito no SEMM.](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*Figura 5. A presença do item Pacote de Configuração do Microsoft Surface em Programas e Recursos indica que o dispositivo está inscrito no SEMM*

## <a name="unenroll-a-surface-device-from-semm-with-a-recovery-request"></a>Desemarme um dispositivo Surface do SEMM com uma Solicitação de Recuperação

Em alguns cenários, um pacote de redefinição do Surface UEFI pode não ser uma opção viável para desempacorar um dispositivo Surface do SEMM (por exemplo, onde o Windows se tornou inutilizável). Nesses cenários, você pode desempacodar o dispositivo usando uma Solicitação de Recuperação gerada de dentro do Surface UEFI. O processo de Solicitação de Recuperação pode ser iniciado mesmo em dispositivos em que você não tem a senha UEFI do Surface.

O processo de Solicitação de Recuperação é iniciado a partir da UEFI do Surface no dispositivo Surface, aprovado com o Configurador UEFI do Microsoft Surface em outro computador e, em seguida, concluído no Surface UEFI. Como o pacote de redefinição, aprovar uma Solicitação de Recuperação com o Configurador UEFI do Microsoft Surface requer acesso ao certificado SEMM que foi usado para registrar o dispositivo Surface.

Para iniciar uma Solicitação de Recuperação, siga estas etapas:

1. Inicializar o dispositivo Surface que deve ser desempacodado do SEMM para o Surface UEFI.
2. Digite a senha UEFI do Surface se for solicitado a fazer isso.
3. Clique na **página Enterprise de gerenciamento,** conforme mostrado na Figura 6.

   ![Enterprise Página de gerenciamento.](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *Figura 6. A Enterprise de gerenciamento do Enterprise é exibida no Surface UEFI em dispositivos inscritos no SEMM*

4. Clique ou pressione **Introdução**.
5. Clique ou pressione **Next para** iniciar o processo de Solicitação de Recuperação.
   >[!NOTE]
   >Uma Solicitação de Recuperação expira duas horas após a criação. Se uma Solicitação de Recuperação não for concluída neste momento, você terá que reiniciar o processo de Solicitação de Recuperação.
6. Selecione **Certificado SEMM** na lista de certificados exibidos na página Escolher uma chave de redefinição **do SEMM** (mostrada na Figura 7) e clique ou pressione **Next**.

   ![Selecione Certificado SEMM para sua Solicitação de Recuperação.](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *Figura 7. Escolha Certificado SEMM para sua Solicitação de Recuperação (Solicitação de Redefinição)*

7. Na página Inserir código de verificação de redefinição **** do **SEMM,** você pode clicar nos botões **Código QR** ou Texto para exibir sua Solicitação de Recuperação (Solicitação de Redefinição), conforme mostrado na Figura 8, ou o botão **USB** para salvar sua Solicitação de Recuperação (Solicitação de Redefinição) como um arquivo em uma unidade USB, conforme mostrado na Figura 9.

   ![Solicitação de Recuperação exibida como um código QR.](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *Figura 8. Uma Solicitação de Recuperação (Solicitação de Redefinição) exibida como um código QR*

   ![Salve uma solicitação de recuperação em uma unidade USB.](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *Figura 9. Salvar uma Solicitação de Recuperação (Solicitação de Redefinição) em uma unidade USB*

   * Para usar uma Solicitação de Recuperação de Código QR (Solicitação de Redefinição), use um aplicativo de leitor de QR em um dispositivo móvel para ler o código. O aplicativo de leitor de QR converterá o código QR em uma cadeia de caracteres alfanumérico. Em seguida, você pode enviar emails ou mensagens para o administrador que produzirá o código de verificação de redefinição com o Configurador UEFI do Microsoft Surface.
   * Para usar uma Solicitação de Recuperação (Solicitação de Redefinição) salva em uma unidade USB como um arquivo, use a unidade USB para transferir o arquivo para o computador onde o Configurador UEFI do Microsoft Surface será usado para produzir o Código de Verificação de Redefinição. O arquivo também pode ser copiado da unidade USB em outro dispositivo para ser enviado por email ou transferido pela rede.
   * Para usar a Solicitação de Recuperação (Solicitação de Redefinição) como texto, basta digitar o texto diretamente no Configurador UEFI do Microsoft Surface.

8. Abra o Configurador UEFI do Microsoft Surface menu Iniciar em outro computador.
    >[!NOTE]
    >O Microsoft Surface UEFI Configurator deve ser executado em um ambiente capaz de autenticar a cadeia de certificados do certificado SEMM.
9. Clique em **Iniciar**.
10. Clique **em Solicitação de**Recuperação , conforme mostrado na Figura 10.

    ![Inicie o processo para aprovar uma Solicitação de Recuperação.](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *Figura 10. Clique em Solicitação de Recuperação para iniciar o processo para aprovar uma Solicitação de Recuperação*

11. Clique **em Proteção de Certificados** para autenticar a Solicitação de Recuperação com o certificado SEMM.
12. Navegue até e selecione seu arquivo de certificado SEMM e clique em **OK**.
13. Quando você for solicitado a inserir a senha do certificado, conforme mostrado na Figura 11, digite e confirme a senha do arquivo de certificado e clique em **OK**.

    ![Digite senha para certificado SEMM.](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *Figura 11. Digite a senha do certificado SEMM*

14. Clique em **Avançar**.
15. Insira a Solicitação de Recuperação (Solicitação de Redefinição) e clique em **Gerar** para criar um código de verificação de redefinição (conforme mostrado na Figura 12).

    ![Insira a solicitação de recuperação.](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *Figura 12. Insira a Solicitação de Recuperação (Solicitação de Redefinição)*

    * Se você exibiu a Solicitação de Recuperação (Solicitação de Redefinição) como texto no dispositivo Surface que está sendo redefinido, use o teclado para digitar a Solicitação de Recuperação (Solicitação de Redefinição) no campo fornecido.
    * Se você exibiu a Solicitação de Recuperação (Solicitação de Redefinição) como um Código QR e usou um aplicativo de mensagens ou email para enviar o código para o computador com o Configurador UEFI do Microsoft Surface, copie e colar o código no campo fornecido.
    * Se você salvou a Solicitação de Recuperação (Solicitação **** de Redefinição) como um arquivo em uma unidade USB, clique no botão Importar, navegue até e selecione o arquivo Solicitação de Recuperação (Solicitação de Redefinição) e clique em **OK**.

16. O código de verificação de redefinição é exibido no Configurador UEFI do Microsoft Surface, conforme mostrado na Figura 13.

    ![Exibição do código de verificação de redefinição.](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *Figura 13. O código de verificação de redefinição exibido no Configurador UEFI do Microsoft Surface*

    * Clique no **botão Compartilhar** para enviar o código de verificação de redefinição por email.

17. Insira o código de verificação de redefinição no campo fornecido no dispositivo Surface (mostrado na Figura 8) e clique ou pressione **Verificar** para redefinir o dispositivo e desempurar o dispositivo do SEMM.
18. Clique ou pressione **Reiniciar agora** na página bem-sucedida redefinir **SEMM** para concluir o desemrollamento do SEMM, conforme mostrado na Figura 14.

    ![Exemplo de exibição de desemplamento bem-sucedido do SEMM.](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *Figura 14. Unenrollment bem-sucedido do SEMM*

19. Clique **em Finalizar** no Configurador UEFI do Microsoft Surface para concluir o processo de Solicitação de Recuperação (Solicitação de Redefinição) e fechar o Configurador UEFI do Microsoft Surface.


