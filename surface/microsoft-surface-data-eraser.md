---
title: Microsoft Surface Data Eraser (Surface)
description: Saiba como a ferramenta Microsoft Surface Data Eraser pode ajudá-lo a apagar dados com segurança de dispositivos Surface.
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: ferramenta, USB, dados, apagar
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 05/17/2021
ms.openlocfilehash: d96581cd67e9cd4171fbb745aed4e9b34e2f0627
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576621"
---
# <a name="microsoft-surface-data-eraser"></a>Microsoft Surface Data Eraser

Saiba como a ferramenta Microsoft Surface Data Eraser pode ajudá-lo a apagar dados com segurança de dispositivos Surface.

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) é uma ferramenta que é inicializada a partir de um pen drive e permite que você execute a limpeza segura de todos os dados de um dispositivo Surface. Um pen drive com o Microsoft Surface Data Eraser requer apenas a capacidade de inicialização via USB. O pen drive é fácil de criar usando o assistente fornecido, o wrapper do Microsoft Surface Data Eraser, e é fácil de usar, com uma interface gráfica simples; a linha de comando não é necessária. Para saber mais sobre recursos para apagar dados e as práticas que a Microsoft usa durante o processo de manutenção do Surface, consulte [Proteção de seus dados se você enviar o Surface para manutenção](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Microsoft Surface Data Eraser usa o comando de formato NVM Express (NVMe) para apagar os dados conforme autorizado em [NIST Special Publication 800-88 Revisão 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf).

Dispositivos Surface compatíveis incluem:

- Surface Book (todas as edições)
- Surface Go (todas as edições)
- Surface Pro X (todas as edições)
- Surface Laptop (todas as edições)
- Surface Laptop Go
- Surface Studio (todas as edições)
- Surface Pro 2 e posterior
- Surface 3
- Windows 10 Pro e Enterprise no Surface Hub 2

Alguns cenários em que o Microsoft Surface Data Eraser pode ser útil são:

- Preparar um dispositivo Surface a ser enviado para reparo.
- Desative um dispositivo Surface a ser removido. de uso corporativo ou organizacional.
- Reutilizar um dispositivo Surface para uso em um novo departamento ou para uso por um novo usuário.
- Prática padrão ao executar a re-imagem para dispositivos usados com dados confidenciais.

>[!NOTE]
>Dispositivos de terceiros, dispositivos Surface que executam o Windows RT (inclusive Surface e Surface 2) e o Surface Pro não são compatíveis com o Microsoft Surface Data Eraser.

>[!NOTE]
>Como a capacidade de inicializar via USB é necessária para executar o Microsoft Surface Data Eraser, se o dispositivo não for configurado para inicialização via USB ou se não puder ser inicializado ou executar POST com êxito, a ferramenta Microsoft Surface Data Eraser não funcionará.

>[!NOTE]
>O Surface Data Eraser no Surface Studio e Surface Studio 2 pode levar até 6 minutos para ser inicializado no WinPE antes que o apagamento do disco possa ocorrer.

## <a name="how-to-create-a-microsoft-surface-data-eraser-usb-stick"></a>Como criar um pen drive do Microsoft Surface Data Eraser

Para criar um pen drive do Microsoft Surface Data Eraser, primeiro instale a ferramenta de instalação do Microsoft Surface Data Eraser por meio do Centro de Download da Microsoft usando o link fornecido no início deste artigo. Você não precisa de um dispositivo Surface para *criar* o pen drive. Após baixar o arquivo de instalação para o computador, siga estas etapas para instalar a ferramenta de criação do Microsoft Surface Data Eraser:

1. Execute o DataEraserSetup.msi de instalação que você baixou do [Centro de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=46703)

2. Marque a caixa de seleção para aceitar os termos do contrato de licença e clique em **Instalar**.

3. Clique em **Concluir** para fechar a janela de instalação do Microsoft Surface Data Eraser.

Depois que a ferramenta de criação for instalada, siga estas etapas para criar um pen drive do Microsoft Surface Data Eraser. Antes de iniciar as etapas, verifique se há um pen drive USB 3.0 com tamanho de 4 GB ou maior conectado ao computador.

1. Inicie o Microsoft Surface Data Eraser por meio do menu Iniciar ou da tela Inicial.

2. Clique em **Compilar** para iniciar o processo de criação do pen drive do Microsoft Surface Data Eraser.

3. Clique em **Iniciar** para confirmar que há um pen drive de pelo menos 4 GB conectado, conforme mostrado na Figura 1.

   ![Inicie a ferramenta Microsoft Surface Data Eraser](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *Figura 1. Inicie a ferramenta Microsoft Surface Data Eraser*
4. Escolha **x64 para a** maioria dos dispositivos Surface ou **** **ARM64** para Surface Pro X na página Seleção de Arquitetura, conforme mostrado na Figura 2. Selecione **Continuar**.

    ![Seleção de arquitetura](images/dataeraser-arch.png "Architecture Selection")<br>
       *Figura 2. Selecionar arquitetura de dispositivo*

5. Selecione a unidade USB de sua escolha na página Seleção de Unidade **** de Polegar **USB,** conforme mostrado na Figura 3, e clique em Iniciar para iniciar o processo de criação usb. A unidade que você selecionar será formatada, e todos os dados existentes nela serão perdidos.

   >[!TIP]
   >Se o botão Iniciar estiver desabilitado, verifique se a unidade removível tem capacidade total de pelo menos 4 GB.
  
   ![Seleção de pen drive](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *Figura 3. Seleção de pen drive*

6. Após a conclusão do processo de criação, a unidade USB está formatada, e todos os binários são copiados para a unidade USB. Clique em **Êxito**.

7. Quando a tela **Parabéns** for exibida, você poderá ejetar e remover o pen drive. Esse pen drive agora está pronto para ser inserido em um dispositivo Surface, para executar a inicialização e apagar todos os dados no dispositivo. Clique **em Concluir** para concluir o processo de criação usb, conforme mostrado na Figura 4.

   ![Processo de criação do Surface Data Eraser USB](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *Figura 4. Concluir o processo de criação do pen drive do Microsoft Surface Data Eraser*

8. Clique em **X** para fechar o Microsoft Surface Data Eraser.

## <a name="how-to-use-a-microsoft-surface-data-eraser-usb-stick"></a>Como usar um pen drive do Microsoft Surface Data Eraser

Após criar um pen drive do Microsoft Surface Data Eraser, você pode inicializar um dispositivo Surface com suporte por meio do pen drive seguindo este procedimento:

1. Insira o pen drive inicializável do Microsoft Surface Data Eraser no dispositivo Surface com suporte.

2. Inicialize o dispositivo Surface por meio do drive pen drive do Microsoft Surface Data Eraser. Para inicializar o dispositivo por meio do pen drive, siga estas etapas:

   a. Desligue o dispositivo Surface.
   b. Pressione e segure o botão **Diminuir o Volume**.
   c. Pressione e solte o botão de **Energia**.
   d. Solte o botão **Diminuir o Volume**.

   >[!TIP]
   >Se o dispositivo não for inicializado via USB usando estas etapas, talvez você precise ativar a opção **Habilitar a sequência de inicialização alternativa** de UEFI do Surface. Você pode ler mais sobre a configuração de inicialização UEFI do Surface em [Gerenciar configurações de UEFI do Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. Quando o dispositivo Surface é inicializado, um **arquivo de texto SoftwareLicenseTerms** é exibido, conforme mostrado na Figura 5.

   ![Inicialização do pen drive do Microsoft Surface Data Eraser](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *Figura 5. Inicialização do pen drive do Microsoft Surface Data Eraser*

4. Leia os termos de licença de software e feche o arquivo do Bloco de Notas.

5. Aceite ou recuse os termos de licença de software digitando **Aceitar** ou **Recusar**. Você deve aceitar os termos de licença para continuar.

6. O script do Microsoft Surface Data Eraser detecta os dispositivos de armazenamento que estão presentes no dispositivo Surface e exibe os detalhes do dispositivo de armazenamento nativo. Para continuar, pressione **S** (essa ação é executada Microsoft Surface Data Eraser e remove todos os dados do dispositivo de armazenamento) ou pressione **N** (essa ação desliga o dispositivo sem remover dados).

   >[!CAUTION]
   >A ferramenta Microsoft Surface Data Eraser excluirá todos os dados, incluindo arquivos do sistema operacional Windows necessários para inicializar o dispositivo, de forma segura e irrecuperável. Para inicializar um dispositivo Surface que foi apagado com o Microsoft Surface Data Eraser, primeiro você precisará reinstalar o sistema operacional Windows. Para remover dados de um dispositivo Surface sem remover o sistema operacional Windows, você pode usar a função **Restaurar o PC**. No entanto, isso não impede que os dados sejam recuperados com recursos forenses ou de recuperação de dados. Confira [Opções de recuperação no Windows 10](https://support.microsoft.com/help/12415/windows-10-recovery-options) para obter mais informações.

   ![A partição a ser apagada é exibida](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *Figura 6. A partição a ser apagada é exibida no Microsoft Surface Data Eraser*

7. Se você pressionou **S** na etapa 6, devido à natureza destrutiva do processo de apagamento de dados, uma caixa de diálogo adicional é exibida para confirmar sua escolha.

8. Clique no botão **Sim** continuar a apagar dados no dispositivo Surface.

   >[!TIP]
   >Quando você executa o Surface Data Eraser na unidade USB do Surface Data Eraser, um arquivo de log é gerado na pasta **SurfaceDataEraserLogs**.

## <a name="changes-and-updates"></a>Alterações e atualizações

Microsoft Surface Data Eraser é atualizado periodicamente pela Microsoft. Para obter mais informações sobre as alterações fornecidas em cada nova versão, consulte o seguinte:

### <a name="3391390"></a>3.39.139.0

*Data de lançamento: 13 de abril de 2021*

Esta versão do Surface Data Eraser inclui:

- Suporte para Surface Laptop 4

### <a name="2341390"></a>2.34.139.0

*Data de lançamento: 15 de janeiro de 2021*

Esta versão do Surface Data Eraser:

- Inclui correções de bugs

### <a name="333139"></a>3.33.139

*Data de lançamento: 9 de setembro de 2020*

Esta versão do Surface Data Eraser inclui correções de bugs e adiciona suporte para: 

- Re-design de arquitetura para reduzir a necessidade de atualização com novas versões de produto
- Notificação disponível para novas atualizações de ferramentas
- Adições de telemetria
- Windows 10 Pro e Enterprise no Surface Hub 2

### <a name="330139"></a>3.30.139

*Data de lançamento: 11 de maio de 2020*

Esta versão do Surface Data Eraser adiciona suporte para:

- Surface Book 3
- Surface Go 2
- Novo SSD no Surface Go

### <a name="328137"></a>3.28.137

*Data do lançamento: 11 de novembro de 2019*

Esta versão do Surface Data Eraser:

- Inclui correções de bugs

### <a name="version-321137"></a>Versão 3.21.137

*Data do lançamento: 21 de outubro de 2019*

Esta versão do Surface Data Eraser é compilada para x86 e adiciona suporte para os seguintes dispositivos:

- Surface Pro 7, Surface Pro X e Surface Laptop 3

### <a name="version-32780"></a>Versão 3.2.78.0

*Data do lançamento: 4 de dezembro de 2018*

Esta versão do Surface Data Eraser:

- Inclui correções de bugs

### <a name="version-32750"></a>Versão 3.2.75.0

*Data de lançamento: 12 de novembro de 2018*

Esta versão do Surface Data Eraser:

- Adiciona suporte ao Surface Studio 2
- Corrige problemas com cartão SD

### <a name="version-32690"></a>Versão 3.2.69.0

*Data de lançamento: 12 de outubro de 2018*

Esta versão do Surface Data Eraser adiciona suporte para o seguinte:

- Surface Pro 6
- Surface Laptop 2

### <a name="version-32680"></a>Versão 3.2.68.0

Esta versão do Microsoft Surface Data Eraser adiciona suporte para o seguinte:

- Surface Go

### <a name="version-32580"></a>Versão 3.2.58.0

Esta versão do Microsoft Surface Data Eraser adiciona suporte para o seguinte:

- Dispositivos de armazenamento adicionais (unidades) para Surface Pro e Surface Laptop dispositivos

### <a name="version-32460"></a>Versão3.2.46.0

Esta versão do Microsoft Surface Data Eraser adiciona suporte para o seguinte:

- Surface Pro com LTE Avançado

### <a name="version-32450"></a>Versão3.2.45.0

Esta versão do Microsoft Surface Data Eraser adiciona suporte para o seguinte:

- Surface Book 2
- Surface Pro 1 TB

   >[!NOTE]
   >O Surface Data Eraser v3.2.45.0 e superiores pode ser usado para restaurar dispositivos Surface Pro ou Surface Laptop com a opção de armazenamento de 1 TB quando o dispositivo mostrar dois volumes separados de 512 GB ou encontrar erros durante a tentativa de implantar ou instalar o Windows 10. Consulte [Surface Pro Model 1796 e Surface Laptop 1 TB exibem duas unidades](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives) para obter mais informações.

### <a name="version-32360"></a>Versão3.2.36.0

Esta versão do Microsoft Surface Data Eraser adiciona suporte para o seguinte:

- Surface Pro
- Surface Laptop

>[!NOTE]
>A ferramenta de criação de unidade da unidade USB do Microsoft Surface Data Eraser não pode ser executada no Windows 10 S. Para limpar um Surface Laptop executando o Windows 10 S, primeiro você deve criar a unidade USB do Microsoft Surface Data Eraser em outro computador com Windows 10 Pro ou Windows 10 Enterprise.
