---
title: Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas
description: Este tópico explica como usar o kit de ferramentas de diagnóstico de superfície para empresas.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 97d0a3d76cf9286ca946e08be9f605084084b2ba
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145956"
---
# Implantar o Kit de Ferramentas de Diagnóstico Surface para Empresas

O Microsoft Surface Diagnostic Toolkit for Business (SDT) permite que os administradores de ti investiguem rapidamente, solucionem problemas e resolvam problemas de hardware, software e firmware com dispositivos Surface. Você pode executar diversos testes de diagnóstico e recorreções de software, além de obter orientação sobre a integridade do dispositivo e orientação para a solução de problemas. 

Especificamente, o SDT para empresas permite que você:

- [Personalize o pacote.](#preparing-the-sdt-package-for-distribution)
- [Executar o aplicativo usando comandos.](surface-diagnostic-toolkit-command-line.md)
- [Execute vários testes de hardware para solucionar problemas.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Gere logs para analisar problemas.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obter um relatório detalhado para comparar o dispositivo versus a configuração ideal.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## Principais cenários e recursos de download 

Para executar o SDT para empresas, baixe os componentes listados na tabela a seguir.


Modo |  Cenários principais | Baixar | Saiba mais
--- | --- | --- | ---
Modo desktop |  Ajude os usuários a executar o SDT em seus dispositivos de superfície para solucionar problemas.<br>Crie um pacote personalizado para implantar em um ou mais dispositivos Surface, permitindo que os usuários selecionem logs específicos para coletar e analisar. | Pacote MSI distribuído do SDT:<br>Instalador do kit de ferramentas de diagnóstico de superfície Microsoft para empresas<br>[Ferramentas Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Usar o kit de ferramentas de diagnóstico Surface no modo de área de trabalho](surface-diagnostic-toolkit-desktop-mode.md)
Linha de comando |  Solucionar problemas diretamente de dispositivos Surface remotamente sem interação do usuário, usando ferramentas padrão, como o Configuration Manager. Ele inclui os seguintes comandos:<br>`-DataCollector` coleta todos os arquivos de log<br>`-bpa` executa o diagnóstico de integridade usando o analisador de práticas recomendadas.<br>`-windowsupdate` verifica se há atualizações de firmware ou drivers ausentes no Windows Update.<br>`-warranty` verifica as informações de garantia. <br><br>| Aplicativo de console do SDT:<br>Console do aplicativo Microsoft Surface Diagnostics<br>[Ferramentas Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Executar o kit de ferramentas de diagnóstico de Surface usando comandos](surface-diagnostic-toolkit-command-line.md)

## Dispositivos com suporte 

O SDT para empresas tem suporte em dispositivos Surface 3 e posteriores, incluindo:

- Usar o laptop Surface
- Catálogo de superfície 3
- Ir para a superfície 2
- Surface Pro X
- Surface Pro 7
- Laptop Surface 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Surface Go com LTE
- Surface Book 2
- Surface Pro com LTE Avançado (Model 1807)
- Surface Pro (Model 1796)
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3

## Instalando o kit de ferramentas de diagnóstico de superfície para empresas

Para criar um pacote do SDT que você pode distribuir para os usuários em sua organização:

1. Conecte-se ao seu dispositivo Surface usando a conta de administrador.
2. Baixe o pacote do SDT do Windows Installer (. msi) da [página de ferramentas do Surface para download](https://www.microsoft.com/download/details.aspx?id=46703) e copie-o para um local preferido no seu dispositivo Surface, como área de trabalho.
3. O assistente de configuração do SDT é exibido, como mostra a Figura 1. Clique em **Avançar**. 

    >[!NOTE]
    >Se o assistente de configuração não for exibido, verifique se você está conectado à conta de administrador em seu computador. 

    ![Bem-vindo ao assistente de configuração do kit de ferramentas de diagnóstico de superfície](images/sdt-1.png)

    *Figura 1. Assistente de configuração do kit de ferramentas de diagnóstico de superfície*

4. Quando o assistente de configuração do SDT for exibido, clique em **Avançar**e aceite o contrato de licença de usuário final (EULA)

5. Na tela opções de instalação, altere o local de instalação padrão, se desejar. 
6. Em tipo de instalação, selecione **avançado**. 

    >[!NOTE]
    >A opção padrão permite que os usuários executem a ferramenta de diagnóstico diretamente em seu dispositivo Surface desde que estejam conectadas ao dispositivo usando uma conta de administrador. 
    
     ![Opções de instalação: avançado](images/sdt-install.png)

7. Clique em **Avançar** e, em seguida, clique em **instalar**. 

## Instalando usando a linha de comando
Se desejar, você pode instalar o SDT em um prompt de comando e definir um sinalizador personalizado para instalar a ferramenta no modo de administração. O SDT contém os seguintes sinalizadores de opções de instalação:

- `SENDTELEMETRY` envia dados de telemetria para a Microsoft. O sinalizador aceita `0` para Disabled ou `1` for Enabled. O valor padrão é `1` Enviar telemetria.
- `ADMINMODE` configura a ferramenta para ser instalada no modo de administração. O sinalizador aceita o `0` modo de cliente ou `1` para o modo de administrador de ti. O valor padrão é `0`.

### Para instalar o SDT na linha de comando:

1. Abra um prompt de comando e digite:

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **Exemplo:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Localizando o SDT em seu dispositivo Surface

O SDT e o console do aplicativo SDT são instalados em `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Além do arquivo. exe, o SDT instala um arquivo JSON e um arquivo admin.dll (modules\admin.dll), como mostrado na Figura 2.

![lista de arquivos instalados do SDT no explorador de arquivos](images/sdt-2.png)

*Figura 2. Arquivos instalados pelo SDT*

## Preparando o pacote SDT para distribuição

A criação de um pacote personalizado permite direcionar a ferramenta para problemas específicos conhecidos.

1. Clique em **iniciar > executar**, digite **Surface** e clique em **Kit de ferramentas de diagnóstico de Surface for Business**. 
2. Quando a ferramenta abrir, clique em **criar pacote personalizado**, conforme mostrado na Figura 3.

    ![Criar opção de pacote personalizado](images/sdt-3.png)

    *Figura 3. Criar pacote personalizado*

### Configurações de idioma e telemetria

  Ao criar um pacote, você pode selecionar as configurações de idioma ou optar por não enviar informações de telemetria à Microsoft. Por padrão, o SDT envia telemetria à Microsoft que é usada para melhorar o aplicativo de acordo com a [política de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement). Se quiser recusar, desmarque a caixa de seleção ao criar um pacote personalizado, como mostrado abaixo. Ou desmarque a caixa de seleção **Enviar telemetria para a Microsoft** na página **Opções de instalação** durante a configuração do SDT. 

>[!NOTE]
>Essa configuração não afeta a telemetria mínima armazenada automaticamente em servidores Microsoft durante a execução de testes e reparos que exigem uma conexão à Internet, como o Windows Update e o reparo de software, ou o fornecimento de comentários usando os botões sorrir ou rosto triste na barra de ferramentas do aplicativo. 


![Selecionar configurações de idioma e telemetria](images/sdt-4.png)

*Figura 4. Selecionar configurações de idioma e telemetria*


### Página do Windows Update

Selecione a opção apropriada para a sua organização. A maioria das organizações com vários usuários geralmente selecionam receber atualizações por meio do WSUS (Windows Server Update Services), conforme mostrado na Figura 5. Se estiver usando pacotes locais do Windows Update ou WSUS, digite o caminho conforme apropriado. 

![Selecione a opção de atualização do Windows](images/sdt-5.png)

*Figura 5. Opção de atualização do Windows*

### Página de reparo de software

Isso permite que você selecione ou remova a opção para executar atualizações de reparo de software. 

![Selecione a opção de reparo de software](images/sdt-6.png)

*Figura 6. Opção de reparo de software*

### Página coletando logs e salvando pacote

Você pode optar por executar uma ampla variedade de logs entre aplicativos, Drivers, hardware e sistema operacional. Clique na área apropriada e selecione no menu de logs disponíveis. Em seguida, você pode salvar o pacote em um ponto de distribuição de software ou em um local equivalente que os usuários possam acessar. 

![Selecionar opções de log](images/sdt-7.png)

*Figura 7. Opção de log e salvar pacote*

## Próximas etapas

- [Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho](surface-diagnostic-toolkit-desktop-mode.md)
- [Usar o kit de ferramentas de diagnóstico de superfície para empresas usando comandos](surface-diagnostic-toolkit-command-line.md)

## Alterações e atualizações

### Versão 2.124.139.0

Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:

- Suporte integrado ininterrupto
- Salvar todos os resultados do teste
- Verificar se a imagem é personalizada criada
- Incluir avisos do Gerenciador de dispositivos
- Encaixar versão do firmware
- Sinalizar unidades como possíveis falhas no teste de armazenamento
- Remover link da loja 

### Versão 2.121.139
*Data do lançamento: 31 2020 de julho*<br>
Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:

- Experiência de suporte contínua
- Correções de bugs

### Versão 2.94.139.0
*Data do lançamento: 11 de maio de 2020*<br>
Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:

- Capacidade de ignorar o Windows Update para executar a verificação de hardware.
- Capacidade de receber notificações sobre a atualização da versão mais recente
- Ir para a superfície 2
- Catálogo de superfície 3
- Mostrar indicador de progresso


### Versão 2.43.139.0
*Data do lançamento: 21 de outubro de 2019*<br>
Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte:

- Surface Pro 7
- Laptop Surface 3

### Versão 2.42.139.0
*Data do lançamento: 24 de setembro de 2019*<br>
Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte: 
- Capacidade de baixar relatórios de hardware.
- Capacidade de entrar em contato com o suporte da Microsoft diretamente da ferramenta. <br>

### Versão 2.41.139.0
*Data do lançamento: 24 de junho de 2019*<br>
Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte: 
- Informações sobre a versão do driver incluídas em logs e relatórios.
- Capacidade de fornecer comentários sobre o aplicativo.<br>


### Versão 2.36.139.0
*Data do lançamento: 26 de abril de 2019*<br>
Esta versão do Surface Diagnostic Toolkit para empresas adiciona suporte para o seguinte: 
- Opção configuração avançada para desbloquear os recursos de administração por meio da interface do usuário do instalador, sem exigir configuração de linha de comando.
- Melhorias de acessibilidade.
- Configurações de controle de brilho da superfície incluídas nos logs.
- Link de suporte de compatibilidade do monitor externo no gerador de relatórios.
