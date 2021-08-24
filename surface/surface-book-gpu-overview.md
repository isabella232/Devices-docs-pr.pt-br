---
title: Visão geral técnica da GPU do Surface Book 3
description: Este artigo fornece uma avaliação técnica dos recursos de GPU entre Surface Book 3 modelos.
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
ms.openlocfilehash: 31ce5192670b8c9051ba499273909fdf31c1062d
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911956"
---
# <a name="surface-book-3-gpu-tech-overview"></a>Surface Book de tecnologia de GPU 3

## <a name="introduction"></a>Introdução

Surface Book 3, o laptop Surface mais poderoso ainda lançado, integra recursos de computação e elementos gráficos totalmente modernizados ao seu fator de forma destacável.  Liderada pela GPU (10ª Geração) intel quad-core® Core™ i7 e NVIDIA® Quadro RTX™ 3000 unidade de processamento gráfico (GPU) no modelo de 15 polegadas, o Surface Book 3 vem em uma ampla variedade de configurações para consumidores, profissionais criativos, arquitetos, engenheiros e especialistas em dados. Este artigo explica as principais diferenças entre as configurações de GPU entre modelos de 13 e 15 polegadas de Surface Book 3.

Um diferencial significativo entre Surface Book 3 é a configuração da GPU. Além da GPU intel integrada em todos os modelos, todos, menos o dispositivo Core i5 de nível de entrada de 13,5 polegadas também apresentam uma GPU NVIDIA discreta com Design Max-Q, que incorpora recursos que otimizam a eficiência de energia para fatores de forma móvel.

Integrado à base de teclado, a GPU NVIDIA adicional fornece recursos avançados de renderização de elementos gráficos e vem em duas configurações principais: GeForce® GTX® 1650/1660 Ti para consumidores ou profissionais criativos e Quadro RTX 3000 para profissionais criativos, engenheiros e outros profissionais de negócios que precisam de gráficos avançados ou recursos de aprendizagem profunda. Este artigo também descreve como otimizar a utilização de APLICATIVOs de GPUs especificando quais aplicativos devem usar o iGPU integrado versus a GPU NVIDIA discreta.

## <a name="surface-book-3-gpus"></a>Surface Book 3 GPUs

Esta seção descreve as GPUs integradas e discretas entre Surface Book 3 modelos. Para obter detalhes de configuração de todos os modelos, consulte [Apêndice A: Surface Book 3 SKUs](#).

### <a name="intel-iris-plus-graphics"></a>Intel Iris™ Mais Gráficos

A GPU integrada (iGPU) incluída em todos os modelos Surface Book 3 incorpora um mecanismo gráfico mais amplo e um controlador de memória redesenhado com suporte para LPDDR4X. Instalado como a GPU secundária na maioria dos Surface Book 3, o Intel Iris Plus Graphics funciona como a GPU singular no modelo principal i5, de 13,5 polegadas. Embora nominalmente o dispositivo de nível de entrada na linha Surface Book 3, ele oferece recursos gráficos avançados que permitem que os consumidores, entusiastas e criadores online executem o software de produtividade mais recente, como o Adobe Creative Cloud ou desfrutem de títulos de jogos no 1080p.  

### <a name="nvidia-geforce-gtx-1650"></a>NVIDIA GeForce GTX 1650

O NVIDIA GeForce GTX 1650 com design Max-Q oferece uma atualização importante do principal multiprocessador de streaming para manipular com mais eficiência os gráficos complexos de jogos modernos. Sua execução simultânea de operações de ponto flutuante e inteiro aumenta o desempenho nas cargas de trabalho pesadas de computação de jogos modernos. Uma nova arquitetura de memória unificada com o dobro do cache de seu predecessor permite melhor desempenho em jogos modernos complexos. Novos avanços de sombreamento melhoram o desempenho, a qualidade da imagem e oferecem novos níveis de complexidade geométrica.

### <a name="nvidia-geforce-gtx-1660-ti"></a>NVIDIA GeForce GTX 1660 Ti

Em comparação com o GeForce GTX 1650, o GeForce GTX 1660 Ti mais rápido fornece Surface Book 3 com melhorias de desempenho adicionais e inclui o codificador NVIDIA novo e atualizado, tornando-o melhor para consumidores, jogadores, streamers ao vivo e profissionais criativos.

Graças a 6 GB de memória gráfica GDDR6, os modelos Surface Book 3 equipados com a TI NVIDIA GeForce GTX 1660 oferecem velocidades superiores em softwares avançados de produtividade comercial e jogos populares, especialmente ao executar os títulos mais modernos ou livestreaming. Com um SSD opcional de 2 TB (disponível somente nos EUA), o modelo de 15 polegadas com GeForce GTX 1660 Ti oferece a maior parte do armazenamento de qualquer dispositivo Surface Book 3.

### <a name="nvidia-quadro-rtx-3000"></a>NVIDIA Quadro RTX 3000

O NVIDIA Quadro RTX 3000 desbloqueia vários recursos principais para usuários profissionais: renderização de rastreamento de raios e aceleração de IA e gráficos avançados e desempenho de computação. Uma combinação de 30 núcleos RT, 240 núcleos tensores e 6 GB de memória gráfica GDDR6 permite várias cargas de trabalho avançadas, incluindo fluxos de trabalho com Al, criação de conteúdo 3D, edição de vídeo avançada, transmissão profissional e fluxos de trabalho de vários aplicativos. Enterprise suporte a hardware e software de nível integram ferramentas de implantação para maximizar o tempo de atividade e minimizar os requisitos de suporte a IT. Certificados para o software mais avançado do mundo, os drivers quadro são otimizados para aplicativos profissionais e são ajustados, testados e validados para fornecer certificação de aplicativos, estabilidade de nível empresarial, confiabilidade, disponibilidade e suporte com disponibilidade estendida do produto.
 

## <a name="comparing-gpus-across-surface-book-3"></a>Comparando GPUs entre Surface Book 3

As GPUs NVIDIA oferecem aos usuários um ótimo desempenho para jogos, livestreaming e criação de conteúdo. Os produtos GeForce GTX são ótimos para jogadores e criadores de conteúdo. Os produtos Quadro RTX são voltados para usuários profissionais, oferecem excelente desempenho na criação de conteúdo e jogos e também adicionam os seguintes recursos:

- Aceleração RTX para rastreamento de raios e AI. Isso possibilita renderizar a qualidade do filme, objetos fotorealistas e ambientes com sombras, reflexos e refração fisicamente precisos.  E seus recursos de IA acelerados por hardware significa que os recursos avançados baseados em IA em aplicativos populares podem ser executados mais rápido do que nunca.
- Enterprise hardware, drivers e suporte em nível de nível, bem como certificações de aplicativos ISV.
- Recursos de gerenciamento de IT, incluindo uma camada adicional de ferramentas corporativas dedicadas para gerenciamento remoto, que ajudam a maximizar o tempo de atividade e minimizar os requisitos de suporte de IT.

 A menos que você se conte entre as classificações de profissionais avançados de engenharia, design, arquitetura ou ciência de dados, Surface Book 3 equipados com recursos gráficos do NVIDIA GeForce provavelmente atenderão às suas necessidades. Por outro lado, se você já estiver em uma profissão que exige recursos gráficos altamente avançados em um fator de formulário portátil que permite que você trabalhe de qualquer lugar, o Surface Book 3 com Quadro RTX 3000 merece uma consideração séria. Para saber mais, consulte a visão geral técnica Surface Book 3 Quadro RTX 3000.
 
**Tabela 1. GPUs discretos Surface Book 3**

|                      | **GeForce GTX 1650**                   | **GeForce GTX 1660 Ti**                            | **Quadro RTX 3000**                                                                                       |
| -------------------- | -------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Usuários de destino**     | Jogadores, amadores e criadores online  | Jogadores, profissionais criativos e criadores online | Profissionais criativos, arquitetos, engenheiros, desenvolvedores, especialistas em dados                                |
| **Fluxos de trabalho**        | Design gráfico<br>Fotografia<br>Vídeo | Design gráfico<br>Fotografia<br>Vídeo             | Fluxos de trabalho com al-powered  <br>Certificações de aplicativos<br>Vídeo high-res<br>Pro transmissão<br>Fluxos de trabalho de vários aplicativos |
| **Principais aplicativos**         | Adobe Creative Suite                   | Adobe Creative Suite                               | Adobe Creative Suite<br>Autodesk AutoCAD<br>Dassault Systemes SolidWorks                                  |
| **Aceleração gpu** | Processamento de vídeo e imagem             | Processamento de vídeo e imagem                         | Rastreamento de raios + vídeo AI + 6K<br>Pro de transmissão<br>Enterprise suporte                            |


**Tabela 2. Especificações técnicas da GPU no Surface Book 3**

|                                                          | **GeForce GTX 1650** | **GeForce GTX 1660 Ti** | **Quadro RTX 3000** |
| -------------------------------------------------------- | -------------------- | ----------------------- | ------------------- |
| **Núcleos de processamento do NVIDIA CUDA**                         | 1024                 | 1536                    | 1920                |
| **Núcleos NVIDIA Tensor**                                  | Não                   | Não                      | 240                 |
| **Núcleos RT NVIDIA**                                      | Não                   | Não                      | 30                  |
| **Memória GPU**                                           | 4 GB                 | 6 GB                    | 6 GB                |
| **Largura de banda da memória (GB/s)**                            | Até 112            | Até 288               | Até 288           |
| **Tipo de memória**                                          | GDDR5                | GDDR6                   | GDDR6               |
| **Interface de memória**                                     | 128 bits              | 192 bits                 | 192 bits             |
| **Aumentar mHz do relógio**                                      | 1245                 | 1425                    | 1305                |
| **Relógio base (MHz)**                                     | 1020                 | 1245                    | 765                 |
| **Rastreamento de raios em tempo real**                                | Não                   | Não                      | Sim                 |
| **Aceleração de hardware de IA**                             | Não                   | Não                      | Sim                 |
| **Codificador de hardware**                                     | Sim                  | Sim                     | Sim                 |
| **Driver pronto para jogo (GRD)**                              | Sim <sup> 1</sup>                                   | Sim  <sup> 1</sup>          |Sim <sup> 2</sup> 
| **Driver do Studio (SD)**                                   | Sim  <sup> 1</sup>            | Sim <sup> 1</sup>                 | Sim  <sup> 1</sup>           |
| **Driver ideal para Enterprise (ODE)**                  | Não                   | Não                      | Sim            |
| **Quadro New Feature Driver (QNF)**                      | Não                   | Não                      | Sim            |
| **API do Microsoft DirectX 12, API de Vulkan, Open GL 4.6**    | Sim                  | Sim                     | Sim                 |
| **HdCP (Proteção de Conteúdo Digital) de alta largura de banda 2.2** | Sim                  | Sim                     | Sim                 |
| **Aumento da GPU NVIDIA**                                     | Sim                  | Sim                     | Sim                 |


 1. *Recomendações*
 2.  *Com suporte*

## <a name="optimizing-power-and-performance-on-surface-book-3"></a>Otimizando a energia e o desempenho no Surface Book 3

Windows 10 inclui um modo de Economia de Bateria com um controle deslizante de desempenho que permite maximizar o desempenho do aplicativo (deslizando-o para a direita) ou preservando a vida útil da bateria (deslizando-a para a esquerda). Surface Book 3 implementa essa funcionalidade em algoritmos para otimizar a energia e o desempenho nos seguintes componentes:

- Registros de Eficiência de Energia da CPU (tecnologia Intel Speed Shift) e outros parâmetros de ajuste soC para maximizar a eficiência.
- Rpm máxima do fan com quatro modos: silencioso, nominal, desempenho e máx.
- Power Caps do processador (PL1/PL2).
- Limitações do PROCESSADOR IA Turbo.

Por padrão, quando a bateria cai abaixo de 20%, o Economia de Bateria ajusta as configurações para estender a duração da bateria. Quando conectado à energia, o Surface Book 3 é padrão para as configurações de "Melhor Desempenho" para garantir que os aplicativos são executados no modo de alto desempenho na GPU NVIDIA secundária presente em todos os sistemas i7 Surface Book 3.

O uso de configurações padrão é recomendado para o desempenho ideal quando usado como um laptop ou desvinculado no modo tablet ou studio. Você pode acessar o Economia de Bateria selecionando o ícone da bateria à extrema direita da barra de tarefas.

### <a name="game-mode"></a>Modo de jogo

Surface Book 3 inclui um novo modo de jogo que seleciona automaticamente as configurações máximas de desempenho quando é lançado.

### <a name="safe-detach"></a>Cofre Desconectar

Novo no Surface Book 3, os aplicativos habilitados para Cofre Desconectar permitem desconectar enquanto o aplicativo está usando a GPU. Para aplicativos com suporte como *World of Warcraft*, seu trabalho é movido para o iGPU.

### <a name="modifying-app-settings-to-always-use-a-specific-gpu"></a>Modificando configurações de aplicativo para sempre usar uma GPU específica

Você pode alternar entre os elementos gráficos Intel de economia de energia, mas ainda capazes, e a GPU NVIDIA discreta mais poderosa e associar uma GPU a um aplicativo específico. Por padrão, Windows 10 escolhe automaticamente a GPU apropriada, atribuindo aplicativos graficamente exigentes à GPU NVIDIA discreta. Na maioria das instâncias, não é necessário ajustar manualmente essas configurações. No entanto, se você desconectar e reattar com frequência a exibição da base de teclado ao usar um aplicativo graficamente exigente, você geralmente precisará fechar o aplicativo antes de desconectar. Para habilitar o uso contínuo do aplicativo sem precisar fechar sempre que você desconectar ou reaconectar a exibição, você pode atribuí-lo à GPU integrada, embora com alguma perda de desempenho gráfico.  

Em algumas instâncias, Windows 10 pode atribuir um aplicativo graficamente exigente para ser iGPU; por exemplo, se o aplicativo não estiver totalmente otimizado para gráficos híbridos. Para corrigir isso, você pode atribuir manualmente o aplicativo à GPU NVIDIA discreta.

**Para configurar aplicativos usando opções personalizadas por GPU:**  

1. Vá para **Configurações**  >  **System**  >  **Display e** selecione **Gráficos Configurações**.

    1. Para um Windows de área de trabalho, escolha **Procurar aplicativo**  >  **clássico** e localize o programa.
    2. Para um aplicativo UWP, escolha **Aplicativo Universal** e selecione o aplicativo na listada.

2. Selecione **Adicionar** para criar uma nova entrada na lista do programa selecionado, selecione Opções para abrir Especificações gráficas e selecione a opção desejada.

   ![Selecione opções de GPU de economia de energia ou de alto desempenho.](./images/graphics-settings2.png)

3. Para verificar qual GPU é usada para cada aplicativo, abra o Gerenciador de **Tarefas,** selecione **Desempenho** e ex view the **GPU Engine** column.


## <a name="appendix-a-surface-book-3-skus"></a>Apêndice A: Surface Book 3 SKUs

| **Display**   | **Processor**                     | **GPU**                                                                                              | **RAM**    | **Storage** |
| ------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ----------- |
| **13,5 polegadas** | Quad-core 10th Gen Core i5-1035G7 | Intel Iris™ Mais Gráficos                                                                            | 16 LPDDR4x | 256 GB      |
| **13,5 polegadas** | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA GeForce GTX 1650. Design Max-Q com memória gráfica GDDR5 de 4 GB    | 16 LPDDR4x | 256 GB      |
| **13,5 polegadas** | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA GeForce GTX 1650. Design Max-Q com memória gráfica GDDR5 de 4 GB    | 32 LPDDR4x | 512 GB      |
| **13,5 polegadas** | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA GeForce GTX 1650. Design Max-Q com memória gráfica GDDR5 de 4 GB    | 32 LPDDR4x | 1 TB        |
| **15 polegadas**   | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA GeForce GTX 1660 Ti. Design Max-Q com memória gráfica GDDR6 de 6 GB | 16 LPDDR4x | 256 GB      |
| **15 polegadas**   | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA GeForce GTX 1660 Ti. Design Max-Q com memória gráfica GDDR6 de 6 GB | 32 LPDDR4x | 512 GB      |
| **15 polegadas**   | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA GeForce GTX 1660 Ti. Design Max-Q com memória gráfica GDDR6 de 6 GB | 32 LPDDR4x | 1 TB        |
| **15 polegadas**   | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA GeForce GTX 1660 Ti. Design Max-Q com memória gráfica GDDR6 de 6 GB | 32 LPDDR4x | 2 TB        |
| **15 polegadas**   | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA Quadro RTX 3000. Design Max-Q com memória gráfica GDDR6 de 6 GB     | 32 LPDDR4x | 512 GB      |
| **15 polegadas**   | Quad-core 10th Gen Core i7-1065G7 | Gráficos Intel Iris Plus<br>NVIDIA Quadro RTX 3000. Design Max-Q com memória gráfica GDDR6 de 6 GB     | 32 LPDDR4x | 1 TB        |

> [!NOTE]
> SSD de 2 TB disponível somente nos EUA: Surface Book 3 15" com NVIDIA GTX 1660Ti

## <a name="summary"></a>Resumo

Criado para desempenho, Surface Book 3 inclui configurações de GPU diferentes otimizadas para atender a carga de trabalho específica e usar requisitos. Uma GPU gráfica Intel Iris integrada funciona como a GPU exclusiva no dispositivo Core i5 de nível de entrada e como uma GPU secundária em todos os outros modelos. O GeForce GTX 1650 apresenta uma atualização importante do principal multiprocessador de streaming para executar gráficos complexos de forma mais eficiente. Quanto mais rápido o GeForce GTX 1660 Ti oferece Surface Book 3 com melhorias de desempenho adicionais, melhorando-o para consumidores, jogadores, streamers ao vivo e profissionais criativos. Quadro RTX 3000 desbloqueia vários recursos principais para usuários profissionais: renderização de rastreamento de raios e aceleração de IA e gráficos avançados e desempenho de computação.


## <a name="learn-more"></a>Saiba mais

- [Visão geral técnica do Surface Book 3 Quadro RTX 3000](surface-book-quadro.md)
- [Surface para Empresas](https://www.microsoft.com/surface/business)
