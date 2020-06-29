---
title: Não registrar dispositivos de superfície da SEMM (Surface)
description: Saiba como cancelar o registro de um dispositivo do SEMM usando um pacote de redefinição de UEFI ou a opção de solicitação de recuperação.
keywords: gerenciamento de superfície empresarial
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
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830254"
---
# Cancelar o registro de dispositivos Surface no SEMM

Quando um dispositivo de superfície é registrado no modo de gerenciamento do Surface Enterprise (SEMM), um certificado é armazenado no firmware do dispositivo. A presença desse certificado e a inscrição no SEMM impedir alterações não autorizadas nas configurações ou opções de configuração de superfície enquanto o dispositivo estiver registrado no SEMM. Para restaurar o controle das configurações de Surface UEFI para o usuário, o dispositivo de superfície deve ser cancelado no SEMM, um processo, às vezes, descrito como redefinir ou recuperar. Há dois métodos que você pode usar para cancelar o registro de um dispositivo a partir do SEMM, um pacote de redefinição de de superfície e uma solicitação de recuperação.

>[!WARNING]
>Para cancelar o registro de um dispositivo do SEMM e restaurar o controle do usuário das configurações de controle de falha de superfície, você deve ter o certificado SEMM que foi usado para registrar o dispositivo no SEMM. Se esse certificado for perdido ou corrompido, não será possível cancelar a inscrição no SEMM. Faça backup e proteja o certificado do SEMM de acordo.

Para obter mais informações sobre o SEMM, consulte [modo de gerenciamento do Microsoft Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

## Cancelar o registro de um dispositivo de superfície do SEMM com um pacote de redefinição de UEFI de superfície

O pacote de redefinição de UEFI de superfície é o método principal que você usa para cancelar o registro de um dispositivo de superfície de SEMM. Assim como um pacote de configuração do Surface UEFI, o pacote de redefinição é um arquivo do Windows Installer (. msi) que configura o SEMM no dispositivo. Ao contrário do pacote de configuração, o pacote de redefinição redefinirá a configuração do Surface UEFI em um dispositivo Surface para suas configurações padrão, removerá o certificado SEMM e cancelará o registro do dispositivo do SEMM.

Os pacotes de restauração são criados especificamente para um dispositivo de superfície individual. Para iniciar o processo de criação de um pacote de redefinição, você precisará do número de série do dispositivo que você deseja cancelar a inscrição, bem como o certificado SEMM usado para registrar o dispositivo. Você pode encontrar o número de série do seu dispositivo Surface na página **informações do PC** do Surface UEFI, conforme mostrado na Figura 1. Esta página será exibida mesmo se a UEFI da superfície estiver protegida por senha e a senha incorreta for inserida.

![Número de série do dispositivo de superfície é exibido](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*Figura 1. O número de série do dispositivo de superfície é exibido na página informações de PC da Surface UEFI*

>[!NOTE]
>Para inicializar o Surface UEFI, pressione **aumentar volume** e **energia** simultaneamente enquanto o dispositivo estiver desligado. Segure o **volume** até que o logotipo da superfície seja exibido e o dispositivo comece a inicializar.

Para criar um pacote de redefinição de UEFI de Surface, siga estas etapas:

1. Abra o Microsoft Surface UEFI configurate a partir do menu iniciar.
2. Clique em **Iniciar**.
3. Clique em **Redefinir pacote**, conforme mostrado na Figura 2.

   ![Selecione redefinir pacote para criar um pacote para cancelar o registro do dispositivo de superfície de SEMM](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *Figura 2. Clique em redefinir pacote para criar um pacote para cancelar o registro de um dispositivo de superfície de SEMM*

4. Clique em **proteção de certificado** para adicionar seu arquivo de certificado Semm com chave privada (. pfx), conforme mostrado na Figura 3. Navegue até o local do seu arquivo de certificado, selecione o arquivo e clique em **OK**.

   ![Adicionar o certificado SEMM ao pacote de redefinição de UEFI de superfície](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *Figura 3. Adicionar o certificado SEMM a um pacote de redefinição de UEFI de superfície*

5. Clique em **Avançar**.
6. Digite o número de série do dispositivo que você deseja cancelar o registro de SEMM (conforme mostrado na Figura 4) e clique em **Compilar** para gerar o pacote de redefinição de UEFI de superfície.

   ![Criar um pacote de redefinição de UEFI de superfície com número de série de dispositivo Surface](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *Figura 4. Usar o número de série do seu dispositivo Surface para criar um pacote de redefinição de UEFI de superfície*

7. Na caixa de diálogo **salvar como** , especifique um nome para o pacote de redefinição de UEFI de Surface, navegue até o local onde deseja salvar o arquivo e clique em **salvar**.
8. Quando a geração do pacote for concluída, a página **bem-sucedida** será exibida. Clique em **concluir** para concluir a criação do pacote e feche o Microsoft Surface UEFI Configuration.

Execute o arquivo de instalação do Windows Installer (. msi) do pacote de redefinição de UEFI de Surface no dispositivo Surface para cancelar o registro do dispositivo a partir do SEMM. O pacote de restauração exigirá uma reinicialização para executar a operação de cancelamento de registro. Depois que o dispositivo tiver sido cancelado, você poderá verificar a remoção bem-sucedida, assegurando que o item do **pacote de configuração do Surface da Microsoft** em **programas e recursos** (mostrado na Figura 5) não está mais presente.

![Tela que mostra que o dispositivo está registrado no SEMM](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*Figura 5. A presença do item do pacote de configuração do Surface da Microsoft em programas e recursos indica que o dispositivo está registrado no SEMM*

## Cancelar o registro de um dispositivo de superfície do SEMM com uma solicitação de recuperação

Em alguns cenários, um pacote do Surface UEFI Reset pode não ser uma opção viável para cancelar o registro de um dispositivo de superfície de SEMM (por exemplo, onde o Windows tornou-se inutilizável). Nesses cenários, você pode cancelar o registro do dispositivo usando uma solicitação de recuperação gerada no Surface UEFI. O processo de solicitação de recuperação pode ser iniciado mesmo em dispositivos nos quais você não tem a senha UEFI de superfície.

O processo de solicitação de recuperação é iniciado a partir da UEFI do Surface no dispositivo Surface, aprovado com o Microsoft Surface UEFI Configuration em outro computador e, em seguida, preenchido na UEFI da superfície. Assim como o pacote de restauração, a aprovação de uma solicitação de recuperação com o Microsoft Surface UEFI Configuration requer o acesso ao certificado SEMM usado para registrar o dispositivo de superfície.

Para iniciar uma solicitação de recuperação, siga estas etapas:

1. Inicializar o dispositivo Surface que deve ser cancelado em SEMM para a UEFI da superfície.
2. Digite a senha UEFI da superfície, se for solicitado.
3. Clique na página de **gerenciamento corporativo** , conforme mostrado na Figura 6.

   ![Página de gerenciamento da empresa](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *Figura 6. A página de gerenciamento da empresa é exibida em uma UEFI de superfície em dispositivos registrados no SEMM*

4. Clique **ou pressione introdução**.
5. Clique ou pressione **Avançar** para iniciar o processo de solicitação de recuperação.
   >[!NOTE]
   >Uma solicitação de recuperação expira duas horas após sua criação. Se uma solicitação de recuperação não for concluída nesse período, será preciso reiniciar o processo de solicitação de recuperação.
6. Selecione **Semm certificado** na lista de certificados exibida na página **escolher uma chave de redefinição de Semm** (mostrada na Figura 7) e clique ou pressione **Avançar**.

   ![Selecione SEMM certificado para sua solicitação de recuperação](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *Figura 7. Escolha SEMM certificado para sua solicitação de recuperação (solicitação de redefinição)*

7. Na página de **código de verificação de redefinição de Semm** , você pode clicar nos botões código ou **texto** **QR** para exibir sua solicitação de recuperação (solicitação de redefinição), conforme mostrado na Figura 8, ou o botão **USB** para salvar sua solicitação de recuperação (solicitação de redefinição) como um arquivo para uma unidade USB, como mostrado na Figura 9.

   ![Solicitação de recuperação exibida como um código QR](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *Figura 8. Uma solicitação de recuperação (solicitação de redefinição) exibida como um código QR*

   ![Salvar uma solicitação de recuperação em uma unidade USB](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *Figura 9. Salvar uma solicitação de recuperação (solicitação de redefinição) para uma unidade USB*

   * Para usar uma solicitação de recuperação de código QR (solicitação de redefinição), use um aplicativo leitor QR em um dispositivo móvel para ler o código. O aplicativo leitor QR converterá o código QR em uma cadeia de caracteres alfanumérica. Você pode enviar um email ou uma mensagem para o administrador que produzirá o código de verificação de redefinição com o Microsoft Surface UEFI Configuration.
   * Para usar uma solicitação de recuperação (solicitação de redefinição) salva em uma unidade USB como um arquivo, use a unidade USB para transferir o arquivo para o computador em que o Microsoft Surface UEFI configurador será usado para produzir o código de verificação de redefinição. O arquivo também pode ser copiado da unidade USB em outro dispositivo para ser enviado por email ou transferido pela rede.
   * Para usar a solicitação de recuperação (solicitação de redefinição) como texto, basta digitar o texto diretamente no Microsoft Surface UEFI Configuration.

8. Abra o Microsoft Surface UEFI configurate a partir do menu iniciar em outro computador.
    >[!NOTE]
    >O configurador UEFI da Microsoft Surface deve ser executado em um ambiente que possa autenticar a cadeia de certificados para o certificado SEMM.
9. Clique em **Iniciar**.
10. Clique em **solicitação de recuperação**, conforme mostrado na Figura 10.

    ![Iniciar processo para aprovar uma solicitação de recuperação](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *Figura 10. Clique em solicitação de recuperação para iniciar o processo de aprovação de uma solicitação de recuperação*

11. Clique em **proteção de certificado** para autenticar a solicitação de recuperação com o certificado Semm.
12. Procure e selecione o arquivo de certificado do SEMM e, em seguida, clique em **OK**.
13. Quando for solicitado a digitar a senha do certificado, conforme mostrado na Figura 11, digite e confirme a senha do arquivo de certificado e clique em **OK**.

    ![Digite a senha do certificado SEMM](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *Figura 11. Digite a senha do certificado SEMM*

14. Clique em **Avançar**.
15. Digite a solicitação de recuperação (solicitação de redefinição) e clique em **gerar** para criar um código de verificação de redefinição (conforme mostrado na Figura 12).

    ![Digite a solicitação de recuperação](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *Figura 12. Inserir a solicitação de recuperação (solicitação de redefinição)*

    * Se você tiver exibido a solicitação de recuperação (solicitação de redefinição) como texto no dispositivo de superfície que está sendo redefinido, use o teclado para digitar a solicitação de recuperação (solicitação de redefinição) no campo fornecido.
    * Se você tiver exibido a solicitação de recuperação (solicitação de redefinição) como um código QR e, em seguida, usou um aplicativo de mensagens ou de email para enviar o código ao computador com o Microsoft Surface UEFI Configuration, copie e cole o código no campo fornecido.
    * Se você salvou a solicitação de recuperação (solicitação de redefinição) como um arquivo para uma unidade USB, clique no botão **importar** , procure e selecione o arquivo de solicitação de recuperação (solicitação de redefinição) e clique em **OK**.

16. O código de verificação de redefinição é exibido no Microsoft Surface UEFI Configuration, conforme mostrado na Figura 13.

    ![Exibição do código de verificação de redefinição](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *Figura 13. O código de verificação de redefinição exibido no Microsoft Surface UEFI Configuration*

    * Clique no botão **compartilhar** para enviar o código de verificação de redefinição por e-mail.

17. Digite o código de verificação de redefinição no campo fornecido no dispositivo Surface (mostrado na Figura 8) e, em seguida, clique ou pressione **Verify** para redefinir o dispositivo e cancelar o registro do dispositivo a partir do Semm.
18. Clique ou pressione **reiniciar agora** na página **Semm redefinir êxito** para concluir o cancelamento de registro do Semm, conforme mostrado na Figura 14.

    ![Exemplo de exibição de cancelamento de registro bem-sucedido de SEMM](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *Figura 14. Cancelamento de registro bem-sucedido de SEMM*

19. Clique em **encerrar** no Microsoft Surface UEFI Configurator para concluir o processo de solicitação de recuperação (solicitação de redefinição) e feche o Microsoft Surface UEFI Configuration.


