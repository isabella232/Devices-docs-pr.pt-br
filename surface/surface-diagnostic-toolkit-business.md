---
title: Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas
description: Este tópico explica como usar o Surface Diagnostic Toolkit for Business.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271575"
---
# Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas

O Microsoft Surface Diagnostic Toolkit for Business (SDT) permite que os administradores de IT investiguem, solucionem rapidamente problemas de hardware, software e firmware com dispositivos Surface. Você pode executar vários testes de diagnóstico e reparos de software, além de obter informações e diretrizes de saúde do dispositivo para resolver problemas. 

Especificamente, o SDT para Empresas permite que você:

- [Personalize o pacote.](#preparing-the-sdt-package-for-distribution)
- [Execute o aplicativo usando comandos.](surface-diagnostic-toolkit-command-line.md)
- [Execute vários testes de hardware para solucionar problemas.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Gere logs para analisar problemas.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtenha um relatório detalhado comparando o dispositivo com a configuração ideal.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## Cenários principais e recursos de download 

Para executar o SDT para Empresas, baixe os componentes listados na tabela a seguir.


Modo |  Cenários principais | Baixar | Saiba mais
--- | --- | --- | ---
Modo desktop |  Ajude os usuários a executar o SDT em seus dispositivos Surface para solucionar problemas.<br>Crie um pacote personalizado para implantar em um ou mais dispositivos Surface, permitindo que os usuários selecionem logs específicos para coletar e analisar. | Pacote MSI distribuível do SDT:<br>Instalador do Microsoft Surface Diagnostic Toolkit for Business<br>[Ferramentas Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Usar o Surface Diagnostic Toolkit no modo desktop](surface-diagnostic-toolkit-desktop-mode.md)
Linha de comando |  Solucionar problemas diretamente de dispositivos Surface remotamente sem a interação do usuário, usando ferramentas padrão, como o Configuration Manager. Ele inclui os seguintes comandos:<br>`-DataCollector` coleta todos os arquivos de log<br>`-bpa` executa diagnósticos de saúde usando o Analisador de Práticas Práticas Melhores.<br>`-windowsupdate` verifica se há atualizações de firmware ou driver ausentes no Windows Update.<br>`-warranty` verifica as informações de garantia. <br><br>| Aplicativo de console SDT:<br>Console do Aplicativo de Diagnóstico do Microsoft Surface<br>[Ferramentas Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Executar o Surface Diagnostic Toolkit usando comandos](surface-diagnostic-toolkit-command-line.md)

##  <a name="supported-devices"></a>Dispositivos com suporte 

O SDT para Empresas tem suporte no Surface 3 e em dispositivos posteriores, incluindo:

- Surface Book – todas as gerações
- Surface Go – todas as gerações
- Surface Laptop – todas as gerações
- Surface Pro 3 e posterior
- Surface Pro X - todas as gerações
- Surface Studio – todas as gerações
- Surface 3 LTE
- Surface 3


## Instalando o Surface Diagnostic Toolkit for Business

Para criar um pacote SDT que você pode distribuir aos usuários em sua organização:

1. Entre no dispositivo Surface usando a conta de Administrador.
2. Baixe o pacote do Windows Installer (.msi) do SDT na página de download do [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) e copie-o para um local preferencial no dispositivo Surface, como a área de trabalho.
3. O assistente de instalação do SDT é exibido, conforme mostrado na figura 1. Clique em **Avançar**. 

    >[!NOTE]
    >Se o assistente de configuração não aparecer, verifique se você está entrando na conta de Administrador no computador. 

    ![bem-vindo ao assistente de configuração do Surface Diagnostic Toolkit](images/sdt-1.png)

    *Figura 1. Assistente de configuração do Surface Diagnostic Toolkit*

4. Quando o assistente de instalação do SDT for exibido, clique em **Próximo**, aceite o EULA (Contrato de Licença de Usuário Final)

5. Na tela Opções de Instalação, altere o local de instalação padrão, se desejado. 
6. Em Tipo de Instalação, selecione **Avançado**. 

    >[!NOTE]
    >A opção padrão permite que os usuários executem a ferramenta de diagnóstico diretamente no dispositivo Surface, desde que eles sejam conectados ao dispositivo usando uma conta de Administrador. 
    
     ![Opções de instalação: Avançado](images/sdt-install.png)

7. Clique **em Próximo** e, em seguida, clique em **Instalar.** 

## Instalando usando a linha de comando
Se desejado, você pode instalar o SDT em um prompt de comando e definir um sinalizador personalizado para instalar a ferramenta no modo de administrador. O SDT contém os seguintes sinalizadores de opção de instalação:

- `SENDTELEMETRY` envia dados de telemetria para a Microsoft. O sinalizador aceita `0` para desabilitado `1` ou habilitado. O valor padrão é `1` enviar telemetria.
- `ADMINMODE` configura a ferramenta a ser instalada no modo de administrador. O sinalizador aceita para o `0` modo cliente ou para o modo administrador de `1` IT. O valor padrão é `0`.

### Para instalar o SDT a partir da linha de comando:

1. Abra um prompt de comando e insira:

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **Exemplo:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Localizar o SDT em seu dispositivo Surface

O SDT e o console do aplicativo SDT estão instalados em `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Além do arquivo .exe, o SDT instala um arquivo JSON e um arquivo admin.dll (modules\admin.dll), conforme mostrado na figura 2.

![lista de arquivos instalados do SDT no Explorador de Arquivos](images/sdt-2.png)

*Figura 2. Arquivos instalados pelo SDT*

## Preparando o pacote SDT para distribuição

Criar um pacote personalizado permite direcionar a ferramenta a problemas conhecidos específicos.

1. Clique **em Iniciar > Executar,** insira o **Surface** e clique em Surface **Diagnostic Toolkit for Business.** 
2. Quando a ferramenta for aberta, **clique em Criar Pacote Personalizado,** conforme mostrado na figura 3.

    ![Criar uma opção de pacote personalizado](images/sdt-3.png)

    *Figura 3. Criar um pacote personalizado*

### Configurações de idioma e telemetria

  Ao criar um pacote, você pode selecionar configurações de idioma ou optar por não enviar informações de telemetria para a Microsoft. Por padrão, o SDT envia telemetria para a Microsoft que é usada para melhorar o aplicativo de acordo com a Política [de Privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement) Se você quiser recusar, des marque a caixa de seleção ao criar um pacote personalizado, conforme mostrado abaixo. Ou des clear the **Send telemetry to Microsoft** check box on the Install **Options** page during SDT Setup. 

>[!NOTE]
>Essa configuração não afeta a telemetria mínima armazenada automaticamente nos servidores da Microsoft durante a execução de testes e reparos que exigem uma conexão com a Internet, como o Windows Update e o reparo de software, ou o fornecimento de comentários usando os botões Feliz ou Rosto Feliz na barra de ferramentas do aplicativo. 


![Selecionar configurações de idioma e telemetria](images/sdt-4.png)

*Figura 4. Selecionar configurações de idioma e telemetria*


### Página do Windows Update

Selecione a opção apropriada para sua organização. A maioria das organizações com vários usuários normalmente selecionará receber atualizações por meio do Windows Server Update Services (WSUS), conforme mostrado na figura 5. Se estiver usando pacotes locais do Windows Update ou WSUS, insira o caminho conforme apropriado. 

![Selecionar a opção Windows Update](images/sdt-5.png)

*Figura 5. Opção Windows Update*

### Página de reparo de software

Isso permite que você selecione ou remova a opção de executar atualizações de reparo de software. 

![Selecionar a opção de reparo de software](images/sdt-6.png)

*Figura 6. Opção de reparo de software*

### Coletando logs e salvando a página do pacote

Você pode optar por executar uma ampla variedade de logs entre aplicativos, drivers, hardware e o sistema operacional. Clique na área apropriada e selecione no menu de logs disponíveis. Em seguida, você pode salvar o pacote em um ponto de distribuição de software ou um local equivalente que os usuários possam acessar. 

![Selecionar opções de log](images/sdt-7.png)

*Figura 7. Opção de log e salvar pacote*

##  <a name="next-steps"></a>Próximas etapas

- [Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho](surface-diagnostic-toolkit-desktop-mode.md)
- [Usar o Surface Diagnostic Toolkit for Business usando comandos](surface-diagnostic-toolkit-command-line.md)

##  <a name="changes-and-updates"></a>Alterações e atualizações

### Versão 2.131.139.0

Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Suporte para Surface Pro 7+
- Experiência de suporte perfeita no Surface Pro X
- Melhorias de segurança
- Melhorias na experiência do usuário inclusiva

### Versão 2.124.139.0

Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Suporte integrado contínuo
- Salvar todos os resultados do teste
- Verificar se a imagem é personalizada criada
- Incluir avisos do gerenciador de dispositivos
- Versão do firmware do Dock
- Sinalizar unidades como possíveis falhas no teste de armazenamento
- Remover link do armazenamento 

### Versão 2.121.139
*Data do lançamento: 31 de julho de 2020*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Experiência de suporte contínuo
- Correções de bugs

### Versão 2.94.139.0
*Data do lançamento: 11 de maio de 2020*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Capacidade de ignorar o Windows Update para executar a verificação de hardware.
- Capacidade de receber notificações sobre a atualização de versão mais recente
- Surface Go 2
- Surface Book 3
- Mostrar indicador de progresso


### Versão 2.43.139.0
*Data do lançamento: 21 de outubro de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte:

- Surface Pro 7
- Surface Laptop 3

### Versão 2.42.139.0
*Data do lançamento: 24 de setembro de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte: 
- Capacidade de baixar relatórios de hardware.
- Capacidade de entrar em contato com o Suporte da Microsoft diretamente da ferramenta. <br>

### Versão 2.41.139.0
*Data do lançamento: 24 de junho de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte: 
- Informações de versão do driver incluídas em logs e relatórios.
- Capacidade de fornecer comentários sobre o aplicativo.<br>


### Versão 2.36.139.0
*Data do lançamento: 26 de abril de 2019*<br>
Esta versão do Surface Diagnostic Toolkit for Business adiciona suporte para o seguinte: 
- Opção de instalação avançada para desbloquear recursos de administrador por meio da interface do usuário do instalador, sem a necessidade de configuração de linha de comando.
- Melhorias de acessibilidade.
- Configurações de controle de brilho da superfície incluídas nos logs.
- Link de suporte de compatibilidade do monitor externo no gerador de relatório.
