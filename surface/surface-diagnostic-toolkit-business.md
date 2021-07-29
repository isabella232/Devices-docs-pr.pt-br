---
title: Surface Diagnostic Toolkit for Business
description: Este tópico explica como implantar e usar o Surface Diagnostic Toolkit for Business, que permite que os administradores de IT investiguem, resolvam rapidamente problemas de hardware, software e firmware com dispositivos Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 07/27/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 13480c4b642ff64883c0ee69c73161a51f3f1e96
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708802"
---
# <a name="surface-diagnostic-toolkit-for-business"></a>Surface Diagnostic Toolkit for Business

Se o Surface não estiver funcionando corretamente, o Microsoft Surface Diagnostic Toolkit (SDT) para Empresas poderá ajudar você ou seu administrador a encontrar e resolver problemas.  O SDT para empresas permite investigar, solucionar problemas e resolver rapidamente problemas de hardware, software e firmware com dispositivos Surface em toda a sua rede.

> [!NOTE]
> O Surface Diagnostic Toolkit for Business foi criado para dispositivos comerciais. Se o dispositivo for um dispositivo pessoal e não gerenciado pelo trabalho ou escola, execute o Surface [Diagnostic Toolkit.](https://support.microsoft.com/en-us/help/4037239/surface-fix-common-surface-problems-using-surface-diagnostic-toolkit)

Especificamente, o SDT para Empresas permite que você:

- [Personalize o pacote.](#preparing-the-sdt-package-for-distribution)
- [Execute o aplicativo usando comandos.](surface-diagnostic-toolkit-command-line.md)
- [Execute vários testes de hardware para solucionar problemas.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Gere logs para analisar problemas.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtenha relatório detalhado comparando o dispositivo versus a configuração ideal.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)

## <a name="primary-scenarios-and-download-resources"></a>Cenários principais e recursos de download

Para executar o Surface Diagnostic Toolkit para Empresas, baixe os componentes listados na tabela a seguir.

Modo | Cenários principais | Baixar | Saiba mais
--- | --- | --- | ---
Modo desktop | Ajude os usuários a executar o SDT em seus dispositivos Surface para solucionar problemas.<br>Crie um pacote personalizado para implantar em um ou mais dispositivos Surface, permitindo que os usuários selecionem logs específicos para coletar e analisar. | Pacote MSI distribuível SDT:<br>Microsoft Surface Diagnostic Toolkit for Business Installer<br>[Ferramentas Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Usar o Surface Diagnostic Toolkit no modo de área de trabalho](surface-diagnostic-toolkit-desktop-mode.md)
Linha de comando | Solucionar problemas diretos de dispositivos Surface remotamente sem interação do usuário, usando ferramentas padrão, como o Configuration Manager. Ele inclui os seguintes comandos:<br>`-DataCollector` coleta todos os arquivos de log<br>`-bpa` executa diagnósticos de saúde usando o Analisador de Práticas Práticas Melhores.<br>`-windowsupdate` verifica Windows Atualização para atualizações de firmware ou driver ausentes.<br>`-warranty` verifica as informações de garantia. <br><br>| Aplicativo de console SDT:<br>Console do aplicativo de diagnóstico do Microsoft Surface<br>[Ferramentas Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Executar o Surface Diagnostic Toolkit usando comandos](surface-diagnostic-toolkit-command-line.md)

## <a name="supported-devices"></a>Dispositivos com suporte

O SDT para Empresas tem suporte no Surface 3 e em dispositivos posteriores (exceto para dispositivos configurados no modo S):

- Surface Book - todas as gerações
- Surface Go - todas as gerações
- Surface Laptop - todas as gerações
- Surface Pro 3 e posterior
- Surface Pro X - todas as gerações
- Surface Studio - todas as gerações
- Surface 3 LTE
- Surface 3

## <a name="installing-surface-diagnostic-toolkit-for-business"></a>Instalando o Surface Diagnostic Toolkit for Business

Para criar um pacote SDT que você pode distribuir aos usuários em sua organização:

1. Entre no dispositivo Surface usando a conta administrador.
2. Baixe o SDT Windows Pacote do Instalador (.msi) na página de download do [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) e copie-o para um local preferencial em seu dispositivo Surface, como Desktop.
3. O assistente de instalação do SDT é exibido, conforme mostrado na figura 1. Clique em **Avançar**.

    >[!NOTE]
    >Se o assistente de configuração não aparecer, verifique se você está entrando na conta administrador no computador.

    ![bem-vindo ao assistente de Toolkit de configuração do Surface Diagnostic](images/sdt-1.png)

    *Figura 1. Assistente de Toolkit de configuração do Surface Diagnostic*

4. Quando o assistente de instalação do SDT for exibido, clique em **Próximo**, aceite o Contrato de Licença de Usuário Final (EULA)

5. Na tela Opções de Instalação, altere o local de instalação padrão, se desejado.
6. Em Tipo de Instalação, selecione **Avançado**.

    >[!NOTE]
    >A opção padrão permite que os usuários executem a ferramenta de diagnóstico diretamente em seu dispositivo Surface, desde que eles sejam conectados ao dispositivo usando uma conta de Administrador.

     ![Opções de instalação: Avançado](images/sdt-install.png)

7. Clique **em Próximo** e clique em **Instalar**.

## <a name="installing-using-the-command-line"></a>Instalar usando a linha de comando

Se desejado, você pode instalar o SDT em um prompt de comando e definir um sinalizador personalizado para instalar a ferramenta no modo de administração. O SDT contém os seguintes sinalizadores de opção de instalação:

- `SENDTELEMETRY` envia dados de telemetria para a Microsoft. O sinalizador aceita `0` para desabilitado ou `1` para habilitado. O valor padrão é `1` enviar telemetria.
- `ADMINMODE` configura a ferramenta a ser instalada no modo de administração. O sinalizador aceita para `0` o modo cliente ou para o modo administrador de `1` IT. O valor padrão é `0`.

### <a name="to-install-sdt-from-the-command-line"></a>Para instalar o SDT na linha de comando

1. Abra um prompt de comando e digite:

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```

    **Exemplo:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <a name="locating-sdt-on-your-surface-device"></a>Localizando o SDT em seu dispositivo Surface

Tanto o SDT quanto o console do aplicativo SDT estão instalados em `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Além do arquivo .exe, o SDT instala um arquivo JSON e um arquivo admin.dll (modules\admin.dll), conforme mostrado na figura 2.

![lista de arquivos instalados do SDT no Explorador de Arquivos](images/sdt-2.png)

*Figura 2. Arquivos instalados pelo SDT*

## <a name="preparing-the-sdt-package-for-distribution"></a>Preparando o pacote SDT para distribuição

A criação de um pacote personalizado permite direcionar a ferramenta a problemas conhecidos específicos.

1. Clique **em Iniciar > Executar,** insira o **Surface** e clique em Surface Diagnostic Toolkit **for Business**.
2. Quando a ferramenta for aberta, clique em **Criar Pacote Personalizado**, conforme mostrado na figura 3.

    ![Criar opção de pacote personalizado](images/sdt-3.png)

    *Figura 3. Criar pacote personalizado*

### <a name="language-and-telemetry-settings"></a>Configurações de idioma e telemetria

  Ao criar um pacote, você pode selecionar configurações de idioma ou não enviar informações de telemetria para a Microsoft. Por padrão, o SDT envia telemetria para a Microsoft que é usada para melhorar o aplicativo de acordo com a Declaração de [Privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement) Se quiser recusar, desempure a caixa de seleção ao criar um pacote personalizado, conforme mostrado abaixo. Ou des limpar a caixa de seleção Enviar **telemetria para a Microsoft** na página **Opções de** Instalação durante a Instalação do SDT.

>[!NOTE]
>Essa configuração não afeta a telemetria mínima armazenada automaticamente nos servidores Microsoft durante a execução de testes e reparos que exigem uma conexão com a Internet, como o reparo de software e atualização do Windows, ou o fornecimento de comentários usando os botões Smile ou Frown na barra de ferramentas do aplicativo.

![Selecionar configurações de idioma e telemetria](images/sdt-4.png)

*Figura 4. Selecionar configurações de idioma e telemetria*

### <a name="windows-update-page"></a>Windows Página de atualização

Selecione a opção apropriada para sua organização. A maioria das organizações com vários usuários normalmente selecionará receber atualizações por meio Windows Server Update Services (WSUS), conforme mostrado na figura 5. Se estiver usando pacotes Windows update local ou WSUS, insira o caminho conforme apropriado.

![Selecione Windows opção Atualizar](images/sdt-5.png)

*Figura 5. Windows Opção Atualizar*

### <a name="software-repair-page"></a>Página de reparo de software

Isso permite que você selecione ou remova a opção de executar atualizações de reparo de software.

![Selecionar opção de reparo de software](images/sdt-6.png)

*Figura 6. Opção de reparo de software*

### <a name="collecting-logs-and-saving-package-page"></a>Coletando logs e salvando a página do pacote

Você pode selecionar para executar uma ampla variedade de logs entre aplicativos, drivers, hardware e o sistema operacional. Clique na área apropriada e selecione no menu de logs disponíveis. Em seguida, você pode salvar o pacote em um ponto de distribuição de software ou local equivalente que os usuários possam acessar.

![Selecionar opções de log](images/sdt-7.png)

*Figura 7. Opção de log e salvar pacote*

## <a name="next-steps"></a>Próximas etapas

- [Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho](surface-diagnostic-toolkit-desktop-mode.md)
- [Usar o Surface Diagnostic Toolkit business usando comandos](surface-diagnostic-toolkit-command-line.md)

## <a name="changes-and-updates"></a>Alterações e atualizações

### <a name="version-21311390"></a>Versão 2.131.139.0

Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Suporte para Surface Pro 7+
- Experiência de suporte contínuo no Surface Pro X
- Melhorias de segurança
- Melhorias inclusivas da experiência do usuário

### <a name="version-21241390"></a>Versão 2.124.139.0

Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Suporte integrado contínuo
- Salvar todos os resultados do teste
- Verificar se a imagem é criada personalizada
- Incluir avisos do gerenciador de dispositivos
- Versão do firmware do dock
- Sinalizar unidades como possíveis falhas no teste de armazenamento
- Remover link do armazenamento

### <a name="version-2121139"></a>Versão 2.121.139

*Data de lançamento: 31 de julho de 2020*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Experiência de suporte contínuo
- Correções de bugs

### <a name="version-2941390"></a>Versão 2.94.139.0

*Data de lançamento: 11 de maio de 2020*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Capacidade de ignorar Windows Atualização para executar a verificação de hardware.
- Capacidade de receber notificações sobre a atualização mais recente da versão
- Surface Go 2
- Surface Book 3
- Mostrar indicador de progresso

### <a name="version-2431390"></a>Versão 2.43.139.0

*Data de lançamento: 21 de outubro de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Surface Pro 7
- Surface Laptop 3

### <a name="version-2421390"></a>Versão 2.42.139.0

*Data de lançamento: 24 de setembro de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Capacidade de baixar relatórios de hardware.
- Capacidade de entrar em contato com o Suporte da Microsoft diretamente da ferramenta. <br>

### <a name="version-2411390"></a>Versão 2.41.139.0

*Data de lançamento: 24 de junho de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Informações de versão do driver incluídas em logs e relatório.
- Capacidade de fornecer comentários sobre o aplicativo.<br>

### <a name="version-2361390"></a>Versão 2.36.139.0

*Data de lançamento: 26 de abril de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Opção de Instalação Avançada para desbloquear recursos de administrador por meio da interface do usuário do instalador, sem exigir configuração de linha de comando.
- Melhorias de acessibilidade.
- Configurações de controle de brilho de superfície incluídas em logs.
- Link de suporte de compatibilidade de monitor externo no gerador de relatório.
