---
title: Visão geral técnica do livro de superfície 3 GPU
description: Este artigo fornece uma avaliação técnica dos recursos de GPU nos modelos do Surface Book 3.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 5/06/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: a3bfe6eec313c9cd9a38f966a1bed46fbc1ca92b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830173"
---
# Visão geral técnica do livro de superfície 3 GPU

## Introdução

O catálogo de superfície 3, o melhor laptop de superfície mais potente ainda lançado, integra recursos de computação e elementos gráficos totalmente modernizados em seu formato de forma de formato famoso.  Administrada pela Intel® Quad-Core 10 Gen Intel® Core™ i7 e NVIDIA®™ Quadro de processamento gráfico (GPU) 3000 no modelo de 15 polegadas, o catálogo de superfície 3 vem em uma ampla gama de configurações para consumidores, profissionais de criação, arquitetos, engenheiros e cientistas de dados. Este artigo explica as principais diferenças entre as configurações de GPU entre os modelos de 13 e 15 polegadas do Surface Book 3.

Um diferenciador significativo nos modelos do catálogo de superfície 3 é a configuração da GPU. Além da GPU integrada Intel integrada a todos os modelos, tudo, exceto o dispositivo básico de i5 de 13,5 polegadas, também apresenta uma GPU NVIDIA discreta com design Max-Q, que incorpora recursos que otimizam o uso eficiente de energia para fatores forma de dispositivo móvel.

Embutida na base do teclado, a GPU NVIDIA adicional oferece recursos avançados de renderização de elementos gráficos e vem em duas configurações principais: GeForce® GTX® 1650/1660 it para consumidores ou profissionais de criação e quadro RTX 3000 para profissionais de criação, engenheiros e outros profissionais de negócios que precisam de gráficos avançados ou recursos de aprendizagem profundas. Este artigo também descreve como otimizar a utilização de aplicativos GPUs especificando quais aplicativos devem usar o iGPU integrado versus a GPU NVIDIA discreta.

## GPUs do livro de superfície 3

Esta seção descreve as GPUs integradas e discretas entre os modelos do Surface Book 3. Para obter detalhes de configuração de todos os modelos, consulte [o apêndice a: catálogo de superfície 3 SKUs](#).

### Elementos gráficos da Intel íris™ Plus

A GPU integrada (iGPU) incluída em todos os modelos do Surface Book 3 incorpora um mecanismo de elementos gráficos mais amplo e um controlador de memória reprojetado com suporte para LPDDR4X. Instalado como a GPU secundária na maioria dos modelos do catálogo de Surface, as funções de elementos gráficos Intel íris Plus, como a GPU singular no modelo de núcleo i5, de 13,5 polegadas. Embora o dispositivo de nível de entrada seja nominal na linha 3 do livro Surface, ele oferece recursos gráficos avançados que permitem que consumidores, entusiastas e criadores online executem o software de produtividade mais recente, como a nuvem do Adobe Creative, ou aproveitem os títulos de jogos na 1080p.  

### NVIDIA GeForce GTX 1650

A NVIDIA GeForce GTX 1650 com o design Max-Q oferece uma importante atualização do multiprocessador de fluxo contínuo principal para manipular mais eficientemente os gráficos complexos de jogos modernos. Sua execução simultânea de operações de ponto flutuante e inteiro aumenta o desempenho das cargas de trabalho de jogos pesados de computação. Uma nova arquitetura de memória unificada com duas vezes o cache de sua predecessora permite um melhor desempenho em jogos modernos complexos. Novos aprimoramentos de sombreamento melhoram o desempenho, melhoram a qualidade da imagem e fornecem novos níveis de complexidade geométrica.

### Ti NVIDIA GeForce GTX 1660

Em comparação com a GeForce GTX 1650, o ti mais veloz da GeForce GTX 1660 fornece o catálogo de superfície 3 com melhorias de desempenho adicionais e inclui o codificador NVIDIA novo e atualizado, tornando-o melhor para consumidores, jogadores, transportadores dinâmicos e profissionais criativos.

Graças a 6 GB de memória de gráficos do GDDR6, os modelos do Surface Book 3 equipados com NVIDIA GeForce GTX 1660 it fornecem velocidades superiores ao software avançado de produtividade empresarial e jogos populares, especialmente ao executar os títulos ou livestreaming mais modernos. Com um SSD de 2 TB opcional (disponível somente nos EUA), o modelo de 15 polegadas com GeForce GTX 1660 it oferece o maior armazenamento de qualquer dispositivo de catálogo de superfície 3.

### NVIDIA Quadro RTX 3000

O NVIDIA Quadro RTX 3000 desbloqueia vários recursos principais para usuários profissionais: representação de controle de raio e aceleração AI, além de gráficos avançados e desempenho de computação. Uma combinação de núcleos de 30 RT, 240 tensor núcleos e 6 GB de memória de gráficos GDDR6 permite várias cargas de trabalho avançadas, incluindo fluxos de trabalho Al-powered, criação de conteúdo 3D, edição de vídeo avançada, transmissão profissional e fluxos de trabalho de vários aplicativos. Suporte a hardware e software em nível empresarial integre ferramentas de implantação para maximizar o tempo de atividade e minimizar os requisitos de suporte de ti. Certificado para os softwares mais avançados do mundo, os drivers quadro a quadro são otimizados para aplicativos profissionais e são ajustados, testados e validados para fornecer certificação de aplicativos, estabilidade em nível empresarial, confiabilidade, disponibilidade e suporte com disponibilidade de produtos ampliada.
 

## Comparar GPUs entre o catálogo de superfície 3

As GPUs NVIDIA fornecem aos usuários excelente desempenho para jogos, streaming dinâmico e criação de conteúdo. Os produtos GeForce GTX são ótimos para jogadores e criadores de conteúdo. Os produtos quadro RTX são direcionados a usuários profissionais, fornecem excelente desempenho em jogos e criação de conteúdo, além de adicionar os seguintes recursos:

- Aceleração de RTX para Ray tracing e AI. Isso torna possível renderizar os objetos e os ambientes de qualidade do filme com sombras, reflexos e refrações fisicamente precisos.  E seus recursos de hardware do AI acelerados significam que os recursos avançados baseados em AI em aplicativos populares podem ser executados mais rapidamente do que nunca.
- Hardware, drivers e suporte de nível empresarial, bem como certificações de aplicativos para ISVs.
- Recursos de gerenciamento de ti, incluindo uma camada adicional de ferramentas corporativas dedicadas para gerenciamento remoto que ajudam a maximizar o tempo de atividade e minimizar os requisitos de suporte de ti

 A menos que você se conte entre os postos de engenharia avançada, design, arquitetura ou profissionais de dados da ciência, o catálogo de superfície 3 equipado com recursos gráficos NVIDIA GeForce provavelmente atenderá às suas necessidades. Por outro lado, se você já estiver em-ou Aspiring para participar, uma profissão que exige recursos de elementos gráficos altamente avançados em um formato portátil que permite que você trabalhe em praticamente qualquer lugar, o Surface Book 3 com quadro RTX 3000 merece consideração sério. Para saber mais, consulte o livro Surface 3 quadro RTX 3000 Technical Overview.
 
**Tabela 1. GPUs discretas no catálogo de superfície 3**

|                      | **GeForce GTX 1650**                   | **GeForce GTX 1660 ti**                            | **Quadro RTX 3000**                                                                                       |
| -------------------- | -------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Usuários de destino**     | Jogadores, entusiastas e criadores online  | Jogadores, profissionais de criação e criadores online | Profissionais de criação, arquitetos, engenheiros, desenvolvedores, cientistas de dados                                |
| **Fluxos**        | Design gráfico<br>Estúdio<br>Vídeo | Design gráfico<br>Estúdio<br>Vídeo             | Fluxos de trabalho do Al-powered  <br>Certificações de aplicativos<br>Vídeo de alta resolução<br>Transmissão de pro<br>Fluxos de trabalho de vários aplicativos |
| **Principais aplicativos**         | Adobe Creative Suite                   | Adobe Creative Suite                               | Adobe Creative Suite<br>Autodesk AutoCAD<br>Dassault System SolidWorks                                  |
| **Aceleração da GPU** | Processamento de vídeo e imagem             | Processamento de vídeo e imagem                         | Vídeo de Ray tracing + AI + 6K<br>Recursos de transmissão pro<br>Suporte para empresas                            |


**Tabela 2. Especificações técnicas da GPU no livro Surface 3**

|                                                          | **GeForce GTX 1650** | **GeForce GTX 1660 ti** | **Quadro RTX 3000** |
| -------------------------------------------------------- | -------------------- | ----------------------- | ------------------- |
| **Núcleos de processamento do NVIDIA CUDA**                         | 1024                 | 1536                    | 1920                |
| **Núcleos NVIDIA tensor**                                  | Não                   | Não                      | 240                 |
| **Núcleos NVIDIA RT**                                      | Não                   | Não                      | 30                  |
| **Memória da GPU**                                           | 4 GB                 | 6 GB                    | 6 GB                |
| **Largura de banda de memória (GB/s)**                            | Até 112            | Até 288               | Até 288           |
| **Tipo de memória**                                          | GDDR5                | GDDR6                   | GDDR6               |
| **Interface de memória**                                     | 128 bits              | 192 bits                 | 192 bits             |
| **Aumento do relógio MHz**                                      | 1245                 | 1425                    | 1305                |
| **Relógio base (MHz)**                                     | 1020                 | 1245                    | 765                 |
| **Rastreamento de raio em tempo real**                                | Não                   | Não                      | Sim                 |
| **Aceleração de hardware AI**                             | Não                   | Não                      | Sim                 |
| **Codificador de hardware**                                     | Sim                  | Sim                     | Sim                 |
| **Driver pronto para jogos (GRD)**                              | Sim <sup> 1</sup>                                   | Sim <sup> 1</sup>          |Sim <sup> 2</sup> 
| **Driver de estúdio (SD)**                                   | Sim <sup> 1</sup>            | Sim <sup> 1</sup>                 | Sim <sup> 1</sup>           |
| **Driver ideal para Enterprise (ODE)**                  | Não                   | Não                      | Sim            |
| **Driver de recurso quadro novo (QNF)**                      | Não                   | Não                      | Sim            |
| **API do Microsoft DirectX 12, API Vulkan, Open GL 4,6**    | Sim                  | Sim                     | Sim                 |
| **Proteção de conteúdo digital de alta largura de banda (HDCP) 2,2** | Sim                  | Sim                     | Sim                 |
| **Aumento da GPU NVIDIA**                                     | Sim                  | Sim                     | Sim                 |


 1. *Recomendações*
 2.  *Com suporte*

## Otimizando o consumo de energia e desempenho no catálogo de superfície 3

O Windows 10 inclui um modo de economia de bateria com um controle deslizante de desempenho que permite maximizar o desempenho do aplicativo (deslizando para a direita) ou preservar a duração da bateria (deslizando-a para a esquerda). O livro Surface 3 implementa esta funcionalidade algorithmically para otimizar o desempenho e o desempenho dos seguintes componentes:

- Registros de eficiência de energia da CPU (tecnologia Intel Speed Shift) e outros parâmetros de ajuste da SoC para maximizar a eficiência.
- Máximo de RPM de ventilador com quatro modos: silencioso, nominal, desempenho e máx.
- Power Cap do processador (PL1/PL2).
- Limitações do processador IA Turbo.

Por padrão, quando a bateria cai abaixo de 20%, a economia de bateria ajusta as configurações para estender a duração da bateria. Quando conectado à potência, o livro Surface 3 tem como padrão as configurações de "melhor desempenho" para garantir que os aplicativos sejam executados no modo de alto desempenho na GPU NVIDIA secundária presente em todos os sistemas do i7 Surface Book 3.

Usar as configurações padrão é recomendado para obter um desempenho ideal quando usado como um laptop ou desconectado no modo tablet ou estúdio. Você pode acessar economia de bateria selecionando o ícone de bateria na extrema direita da barra de tarefas.

### Modo de jogo

O catálogo de superfície 3 inclui um novo modo de jogo que seleciona automaticamente as configurações de desempenho máximo quando iniciada.

### Desanexação segura

Novo no catálogo de superfície 3, os aplicativos habilitados para desanexação segura permitem que você se desconecte enquanto o aplicativo estiver usando a GPU. Para aplicativos compatíveis como o *mundo da Warcraft*, seu trabalho é movido para o iGPU.

### Modificando as configurações do aplicativo para sempre usar uma GPU específica

Você pode alternar entre os elementos gráficos Intel integrados com economia de energia e ainda com e sem suporte e a GPU NVIDIA discreta mais poderosa e associar uma GPU a um aplicativo específico. Por padrão, o Windows 10 escolhe automaticamente a GPU apropriada, atribuindo aplicativos graficamente exigentes à GPU NVIDIA discreta. Na maioria dos casos, não é necessário ajustar manualmente essas configurações. No entanto, se você desconectar e reanexar a exibição da base do teclado usando um aplicativo com dados em elementos gráficos, geralmente precisará fechar o aplicativo antes de desanexar. Para habilitar o uso contínuo do aplicativo sem precisar fechá-lo toda vez que você desanexar ou anexar novamente a exibição, você pode atribuí-lo à GPU integrada, embora com alguma perda de desempenho de elementos gráficos.  

Em alguns casos, o Windows 10 pode atribuir um aplicativo com um design gráfico que exige iGPU; por exemplo, se o aplicativo não for totalmente otimizado para elementos gráficos híbridos. Para corrigir isso, você pode atribuir manualmente o aplicativo à GPU NVIDIA discreta.

**Para configurar aplicativos usando opções personalizadas por GPU:**  

1. Vá para **configurações**  >  **System**  >  **exibição** do sistema e selecione **configurações de elementos gráficos**.

    1. Para um programa da área de trabalho do Windows, escolha procurar no **aplicativo clássico**  >  **Browse** e, em seguida, localize o programa.
    2. Para um aplicativo UWP, escolha **aplicativo universal** e, em seguida, selecione o aplicativo na lista suspensa.

2. Selecione **Adicionar** para criar uma nova entrada na lista para o seu programa selecionado, selecione opções para abrir as especificações de gráficos e selecione a opção desejada.

   ![Selecionar opções da GPU de alto desempenho ou economia de energia](./images/graphics-settings2.png)

3. Para verificar qual GPU são usadas para cada aplicativo, abra o **Gerenciador de tarefas,** selecione **desempenho** e exiba a coluna do **mecanismo da GPU** .


## Apêndice A: SKUs do livro de superfície 3

| **Vídeo**   | **Processador**                     | **GPU**                                                                                              | **RAM**    | **Armazenamento** |
| ------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ----------- |
| **13,5 polegadas** | Quad-Core 10 Gen Core i5-1035G7 | Elementos gráficos da Intel íris™ Plus                                                                            | 16 LPDDR4x | 256 GB      |
| **13,5 polegadas** | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>NVIDIA GeForce GTX 1650. Design Max-Q com memória de gráficos de 4 GB GDDR5    | 16 LPDDR4x | 256 GB      |
| **13,5 polegadas** | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>NVIDIA GeForce GTX 1650. Design Max-Q com memória de gráficos de 4 GB GDDR5    | 32 LPDDR4x | 512 GB      |
| **13,5 polegadas** | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>NVIDIA GeForce GTX 1650. Design Max-Q com memória de gráficos de 4 GB GDDR5    | 32 LPDDR4x | 1 TB        |
| **15 polegadas**   | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>Ti NVIDIA GeForce GTX 1660. Design Max-Q com 6GB GDDR6 de memória gráfica | 16 LPDDR4x | 256 GB      |
| **15 polegadas**   | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>Ti NVIDIA GeForce GTX 1660. Design Max-Q com 6GB GDDR6 de memória gráfica | 32 LPDDR4x | 512 GB      |
| **15 polegadas**   | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>Ti NVIDIA GeForce GTX 1660. Design Max-Q com 6GB GDDR6 de memória gráfica | 32 LPDDR4x | 1 TB        |
| **15 polegadas**   | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>Ti NVIDIA GeForce GTX 1660. Design Max-Q com 6GB GDDR6 de memória gráfica | 32 LPDDR4x | 2 TB        |
| **15 polegadas**   | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>NVIDIA Quadro RTX 3000. Design Max-Q com 6GB GDDR6 de memória gráfica     | 32 LPDDR4x | 512 GB      |
| **15 polegadas**   | Quad-Core 10 Gen Core i7-1065G7 | Elementos gráficos Intel íris Plus<br>NVIDIA Quadro RTX 3000. Design Max-Q com 6GB GDDR6 de memória gráfica     | 32 LPDDR4x | 1 TB        |

> [!NOTE]
> SSD de 2 TB disponível somente nos EUA: catálogo de superfície 3 15 "com NVIDIA GTX 1660Ti

## Resumo

Projetado para desempenho, o catálogo de superfície 3 inclui configurações de GPU diferentes otimizadas para atender a requisitos específicos de carga de trabalho e uso. Uma GPU de elementos gráficos Intel íris integrados funciona como a GPU exclusiva no dispositivo de nível básico i5 e como uma GPU secundária em todos os outros modelos. GeForce GTX 1650 apresenta uma importante atualização do multiprocessador de fluxo contínuo principal para executar gráficos complexos com mais eficiência. O ti mais veloz da GeForce GTX 1660 fornece o catálogo de superfície 3 com melhorias de desempenho adicionais que o tornam mais fácil para consumidores, jogadores, transportadores dinâmicos e profissionais criativos. Quadro RTX 3000 desbloqueia vários recursos principais para usuários profissionais: renderização de controle e aceleração AI e gráficos avançados e desempenho de computação.


## Saiba mais

- [Livro Surface 3 quadro RTX 3000 Technical Overview](surface-book-quadro.md)
- [Surface para Empresas](https://www.microsoft.com/surface/business)
