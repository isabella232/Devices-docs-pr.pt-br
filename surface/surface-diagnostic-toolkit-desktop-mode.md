---
title: Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho
description: Como usar o SDT para ajudar os usuários em sua organização a executar a ferramenta para identificar e diagnosticar problemas com o dispositivo Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830169"
---
# Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho

Este tópico explica como usar o SDT (Kit de ferramentas de diagnóstico de superfície) para ajudar os usuários em sua organização a executar a ferramenta para identificar e diagnosticar problemas com o dispositivo Surface. A execução bem-sucedida do SDT pode determinar rapidamente se um problema relatado é causado por um erro de hardware ou usuário com falha. Para obter uma lista de dispositivos de superfície com suporte no SDT, consulte [implantar o kit de ferramentas de diagnóstico de superfície para empresas](surface-diagnostic-toolkit-business.md).


1. Instrua o usuário a instalar [o pacote SDT a](surface-diagnostic-toolkit-business.md#create-custom-sdt) partir de um ponto de distribuição de software ou compartilhamento de rede. Depois de instalado, você está pronto para orientar o usuário em uma série de testes. 

2. Comece na Home Page, que permite que os usuários insiram uma descrição do problema e clique em **continuar**, conforme mostrado na Figura 1.

    ![Inicie o SDT no modo de área de trabalho ](images/sdt-desk-1.png)
 *Figura 1. SDT no modo de área de trabalho*

3. Quando o SDT indicar que o dispositivo tem as atualizações mais recentes, clique em **continuar** para avançar para o catálogo de testes disponíveis, conforme mostrado na Figura 2.

    ![Selecione entre as opções do SDT ](images/sdt-desk-2.png)
 *Figura 2. Selecionar a partir de opções do SDT*

4. Você pode optar por executar todos os testes de diagnóstico. Ou, se você já suspeitar de um problema específico, como uma exibição defeituosa ou um problema de fonte de alimentação, clique em **selecionar** para escolher um dos testes disponíveis e clique em **executar selecionado**, conforme mostrado na Figura 3. Consulte a tabela a seguir para obter detalhes de cada teste. 

    ![Selecione testes de hardware ](images/sdt-desk-3.png)
 *Figura 3. Selecionar testes de hardware*

    Teste de hardware | Descrição
    --- | ---
    Fonte de alimentação e bateria |  Verifica se a fonte de alimentação está funcionando adequadamente
    Vídeo e áudio   | Verifica o brilho, pixels bloqueados ou inativos, alto-falante e o microfone funciona
    Portas e acessórios   | Verifica os acessórios, anexação de tela e funcionamento USB
    Connectivity |  Verifica a conectividade Bluetooth, sem fio e LTE
    Segurança    | Verifica problemas relacionados à segurança
    Touch   | Verifica problemas relacionados ao toque
    Teclado e toque |    Verifica a conexão do teclado integrada e digite a capa
    Sensores | Verifica o funcionamento de sensores diferentes no dispositivo
    Hardware |  Verifica problemas com diferentes componentes de hardware, como placa gráfica e câmera





<span id="multiple" />

## Executando vários testes de hardware para solucionar problemas

O SDT foi projetado como uma ferramenta interativa que executa uma série de testes. Para cada teste, o SDT fornece instruções Resumindo a natureza do teste e o que os usuários devem esperar ou procurar para que o teste seja bem-sucedido. Por exemplo, para diagnosticar se o brilho da exibição estiver funcionando corretamente, o SDT começará em zero e aumentará o brilho para 100%, solicitando que os usuários confirmem: respondendo **Sim** ou **não** --se o brilho está funcionando conforme o esperado, conforme mostrado na Figura 4. 

Para cada teste, se a funcionalidade não funcionar como esperado e o usuário clicar em **não**, o SDT gerará um relatório das possíveis causas e maneiras de solucionar o problema. 

![Executando o diagnóstico de hardware ](images/sdt-desk-4.png)
 *Figura 4. Executando o diagnóstico de hardware*

1. Se o brilho se ajusta com êxito de 0-100% conforme o esperado, direcione o usuário para clicar em **Sim** e, em seguida, clique em **continuar**. 
2. Se o brilho não for ajustado de 0-100% conforme o esperado, instrua o usuário a clicar em **não** e, em seguida, clicar em **continuar**. 
3. Orientar os usuários nos testes remanescentes, conforme apropriado. Quando concluído, o SDT fornece automaticamente um resumo de alto nível do relatório, incluindo as possíveis causas de problemas de hardware, além de orientação para resolução.


### Reparar aplicativos

O SDT permite que você diagnostique e repare aplicativos que possam estar causando problemas, como mostrado na Figura 5.

![Executando reparos ](images/sdt-desk-5.png)
 *Figura 5. Executando reparos*
<span id="logs" />

### Gerando logs para analisar problemas 

O SDT fornece amplo suporte de diagnóstico habilitado para logs entre aplicativos, Drivers, hardware e problemas do sistema operacional, como mostrado na Figura 6.

![Gerando logs ](images/sdt-desk-6.png)
 *Figura 6. Gerando logs*

<span id="detailed-report" />

### Gerando relatórios detalhados comparando o dispositivo versus configuração ideal

Com base nos logs, o SDT gera um relatório para problemas baseados em software e firmware que você pode salvar em um local preferencial.

## Tópicos relacionados

- [Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos](surface-diagnostic-toolkit-command-line.md)

