---
title: Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho
description: Como usar o SDT para ajudar os usuários em sua organização a executar a ferramenta para identificar e diagnosticar problemas com o dispositivo Surface, bem como enviar solicitações de Suporte diretamente da ferramenta.
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
ms.date: 7/31/2020
ms.openlocfilehash: 7ebdff37cb96589c765e9c9315b098a760976c80
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911236"
---
# <a name="use-surface-diagnostic-toolkit-for-business-in-desktop-mode"></a>Usar o Kit de Ferramentas de Diagnóstico Surface para Empresas no modo de área de trabalho

Este tópico explica como usar o Surface Diagnostic Toolkit (SDT) para ajudar os usuários em sua organização a executar a ferramenta para identificar e diagnosticar problemas com seu dispositivo Surface, bem como enviar solicitações de Suporte diretamente da ferramenta. 

A execução com êxito do SDT pode determinar rapidamente se um problema relatado é causado por falha de hardware ou erro do usuário. Para uma lista de dispositivos Surface com suporte no SDT, consulte [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).


1. Direcionar o usuário para instalar [o pacote SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)) de um ponto de distribuição de software ou compartilhamento de rede. Depois que ele for instalado, você estará pronto para orientar o usuário por meio de uma série de testes. 

2. Comece na home page, que permite que os usuários insiram uma descrição do problema e clique em **Continuar**, conforme mostrado na figura 1.

    ![Inicie o SDT no modo de área de trabalho. ](images/sdt-desk-1.png)
 *Figura 1. SDT no modo desktop*

3. Quando o SDT indicar que o dispositivo tem as atualizações mais recentes, clique em **Continuar** para avançar para o catálogo de testes disponíveis, conforme mostrado na figura 2.

    ![Selecione entre as opções do SDT. ](images/sdt1.png)
 *Figura 2. Selecione entre opções do SDT*

4. Você pode optar por executar todos os testes de diagnóstico. Ou, se você já suspeitar de um problema específico, como **** uma exibição com falha ou um problema de fonte de alimentação, clique em Selecionar para escolher entre os testes disponíveis e clique em Executar Selecionado **,** conforme mostrado na figura 3. Consulte a tabela a seguir para obter detalhes de cada teste. 

    ![Selecione testes de hardware. ](images/sdt2.png)
 *Figura 3. Selecionar testes de hardware*

    Teste de hardware | Descrição
    --- | ---
    Fonte de energia e bateria |  Verifica se a fonte de alimentação está funcionando de forma ideal
    Exibição e som   | Verifica o brilho, pixels travados ou mortos, alto-falante e funcionamento do microfone
    Portas e Acessórios   | Verifica acessórios, anexação de tela e funcionamento USB
    Connectivity |  Verifica Bluetooth conectividade sem fio e LTE
    Segurança    | Verifica problemas relacionados à segurança
    Touch   | Verifica problemas relacionados ao toque
    Teclado e toque |    Verifica a conexão integrada do teclado e a capa de tipo
    Sensores | Verifica o funcionamento de sensores diferentes no dispositivo
    Hardware |  Verifica problemas com diferentes componentes de hardware, como placa gráfica e câmera

5. Quando todos os testes terminarem, a ferramenta solicita que você confirme se o problema foi corrigido. 

 ![Seu problema foi resolvido? ](images/sdt3.png)
 *Figura 3a. Seu problema foi resolvido?*

6. Se o problema não for resolvido ou você não sabe, você pode enviar um tíquete de Suporte selecionando **Entrar** em contato conosco para **Obter ajuda agora.**
 
 ![Envie um tíquete de Suporte. ](images/sdt4.png)
 *Figura 3b. Enviar um tíquete de Suporte*

<span id="multiple" />

## <a name="running-multiple-hardware-tests-to-troubleshoot-issues"></a>Executando vários testes de hardware para solucionar problemas

O SDT foi projetado como uma ferramenta interativa que executa uma série de testes. Para cada teste, o SDT fornece instruções resumindo a natureza do teste e o que os usuários devem esperar ou procurar para que o teste seja bem-sucedido. Por exemplo, para diagnosticar se o brilho da exibição está funcionando corretamente, o SDT começa em zero e aumenta o brilho para 100%, solicitando que os usuários confirmem – respondendo **Sim** ou **Não** – que o brilho está funcionando conforme o esperado, conforme mostrado na figura 4. 

Para cada teste, se a funcionalidade não funcionar conforme o esperado e o usuário clicar em **Não**, o SDT gerará um relatório das possíveis causas e maneiras de solucione-lo. 

![Executando diagnósticos de hardware. ](images/sdt-desk-4.png)
 *Figura 4. Executando diagnósticos de hardware*

1. Se o brilho for ajustado com êxito de 0 a 100 por cento conforme esperado, direcionará o usuário para clicar em **Sim** e clique em **Continuar**. 
2. Se o brilho falhar ao ajustar de 0 a 100 por cento conforme o esperado, direcionará o usuário para clicar em **Não** e clique em **Continuar**. 
3. Orientar os usuários por meio de testes restantes conforme apropriado. Quando concluído, o SDT fornece automaticamente um resumo de alto nível do relatório, incluindo as possíveis causas de quaisquer problemas de hardware, juntamente com orientações para resolução.


### <a name="repairing-applications"></a>Reparar aplicativos

O SDT permite diagnosticar e reparar aplicativos que podem estar causando problemas, conforme mostrado na figura 5.

![Executando reparos. ](images/sdt-desk-5.png)
 *Figura 5. Executando reparos*
<span id="logs" />

### <a name="generating-logs-for-analyzing-issues"></a>Gerar logs para analisar problemas 

O SDT oferece suporte extensivo ao diagnóstico habilitado para log em aplicativos, drivers, hardware e problemas do sistema operacional, conforme mostrado na figura 6.

![Gerando logs. ](images/sdt-desk-6.png)
 *Figura 6. Gerar logs*

<span id="detailed-report" />

### <a name="generating-detailed-report-comparing-device-vs-optimal-configuration"></a>Gerando relatório detalhado comparando dispositivo versus configuração ideal

Com base nos logs, o SDT gera um relatório para problemas baseados em software e firmware que você pode salvar em um local preferencial.

## <a name="related-topics"></a>Tópicos relacionados

- [Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos](surface-diagnostic-toolkit-command-line.md)

