---
title: Práticas recomendadas de configurações de energia para dispositivos Surface
description: Este tópico fornece recomendações de práticas recomendações para manter as configurações de energia ideais e explica como o Surface simplifica a experiência de gerenciamento de energia. Este artigo se aplica a todos os dispositivos Surface com suporte no momento, incluindo Surface Pro 7+, Surface Pro 7, Surface Pro X e Surface Laptop 3.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 54aff228e8a72d413fc53bd14fe15d8ad7b15ab0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271395"
---
# Práticas recomendadas de configurações de energia para dispositivos Surface

Os dispositivos Surface foram projetados para aproveitar os avanços mais recentes no consumo de energia do dispositivo móvel para oferecer uma experiência otimizada otimizada entre cargas de trabalho. Dependendo do que você estiver fazendo, o Surface ajusta dinamicamente como a energia flui para componentes de hardware individuais, ativas momentaneamente os componentes do sistema para lidar com tarefas em segundo plano , como um email de entrada ou tráfego de rede, antes de retornar a um estado de baixo consumo de energia ocioso (S0ix).

##  <a name="summary"></a>Resumo das recomendações para administradores de IT

Para garantir que os dispositivos Surface em toda a organização se beneficiem totalmente dos recursos de otimização de energia do Surface:

-  Instale os drivers e o firmware mais recentes do Windows Update ou o Driver e Firmware do Surface MSI. Isso cria o plano de energia balanceado (também conhecido como perfil de energia) por padrão e define as configurações de energia ideais.  Para obter mais informações, consulte [Gerenciar e implantar atualizações de driver](manage-surface-driver-and-firmware-updates.md)e firmware do Surface.
- Evite criar perfis de energia personalizados ou ajustar configurações de energia avançadas não visíveis na interface do usuário padrão **(sistema**de  >  **energia & sleep**).
- Se você precisa gerenciar o perfil de energia de dispositivos em sua rede (como em organizações altamente gerenciadas), use a ferramenta de comando powercfg para exportar o plano de energia da imagem de fábrica do dispositivo Surface e importá-lo para o pacote de provisionamento para seus dispositivos Surface. 

    >[!NOTE]
    >Você só pode exportar um plano de energia no mesmo tipo de dispositivo Surface.  Por exemplo, você não pode exportar um plano de energia do Surface Laptop e importá-lo no Surface Pro.  Para obter mais informações, consulte [Definir configurações de energia.](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)

- Exclua dispositivos Surface de quaisquer configurações de política de gerenciamento de energia existentes. 

## Tela de fundo

A maneira como o Surface implementa o gerenciamento de energia difere significativamente do padrão anterior do sistema operacional, que reduz gradualmente e desliga a energia por meio de uma série de estados de diminuição; por exemplo, passando por S1, S2, S3 e assim por diante.

Em vez disso, o Surface é imagens com um perfil de energia personalizado que substitui a funcionalidade herdada de suspensão e consumo de energia por recursos de espera modernos e ajuste dinâmico. Esse perfil de energia personalizado é implementado por meio do Surface Serial Hub Driver e do módulo de agregação de sistema (SAM). O chip SAM funciona como o proprietário da política de energia do dispositivo Surface, usando algoritmos para calcular os requisitos de energia ideais. Ele funciona em conjunto com o Gerenciador de energia do Windows para alocar ou acelerar apenas a quantidade exata de energia necessária para que os componentes de hardware funcionem. Este artigo se aplica a todos os dispositivos Surface com suporte no momento, incluindo Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X e Surface Laptop 3.

## Utilizando o perfil de energia personalizado no Surface

Se você entrar nas opções de energia em um dispositivo Surface, verá que há um único plano de energia disponível. Este é o perfil de energia personalizado. E se você for para as configurações de energia avançadas, verá um subconjunto muito menor de opções de energia em comparação com um computador genérico executando o Windows 10. Ao contrário de dispositivos genéricos, o Surface tem firmware e componentes personalizados para gerenciar essas opções de energia.


## Modo de Espera Moderno

O perfil de energia personalizado inserido por algoritmos permite a conectividade de espera moderna para o Surface, mantendo um estado de baixo consumo de energia para a funcionalidade de entrada/reação instantânea típica de smartphones. O S0ix, também conhecido como Estado de Plataforma Ociosa do Tempo de Execução mais Profundo (TAMBÉM CONHECIDO), é o modo de energia padrão para dispositivos Surface. O modo de espera moderno tem dois modos:

- **Modo de espera conectado.** O modo padrão para entrega completa de emails, mensagens e dados sincronizados na nuvem, o modo de espera conectado mantém Wi-Fi e mantém a conectividade de rede.

- **Modo de espera desconectado.** Um modo opcional para a duração da bateria estendida, o modo de espera desconectado oferece a mesma experiência de conexão instantânea e economiza energia, desligando o Wi-Fi, o Bluetooth e a conectividade de rede relacionada.

Para saber mais sobre o modo de espera moderno, consulte o Centro [de Desenvolvimento de Hardware da Microsoft.](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## Como o Surface simplifica a experiência de gerenciamento de energia 

O Surface integra os seguintes recursos projetados para ajudar os usuários a otimizar a experiência de gerenciamento de energia:

- [Plano de energia singular](#singular-power-plan)

- [Interface do usuário de configurações de energia simplificadas](#simplified-power-settings-user-interface)

- [Controle deslizante de energia de desempenho do Windows](#windows-performance-power-slider)

### Plano de energia singular

O Surface foi projetado para uma experiência de gerenciamento de energia simplificada que elimina a necessidade de criar planos de energia personalizados ou definir manualmente as configurações de energia. A Microsoft simplifica a experiência do usuário fornecendo um único plano de energia (balanceado) que substitui os vários planos de energia de builds padrão do Windows.

###  <a name="user-interface"></a>Interface do usuário de configurações de energia simplificadas

O Surface fornece uma interface do usuário simplificada de acordo com as recomendações de configuração de energia de práticas práticas. Em geral, é recomendável apenas ajustar as configurações visíveis na interface do usuário padrão e evitar definir configurações avançadas de energia ou configurações de Política de Grupo. Usar o tempo limite de tela e atividade padrão, evitando níveis máximos de brilho são as maneiras mais eficazes para os usuários manterem a duração da bateria estendida.

![Figura 1. Configurações de sleep & de energia simplificada](images/powerintrofig1.png)

Figura 1. Configurações de energia e sleep simplificadas

### Controle deslizante de energia de desempenho do Windows

Dispositivos Surface que executam o Windows 10 build 1709 e versões posteriores incluem um controle deslizante de energia que permite priorizar a duração da bateria quando necessário ou favorecer o desempenho, se desejado. Você pode acessar o controle deslizante de energia na barra de tarefas clicando no ícone da bateria. Deslize para a esquerda por uma duração de bateria mais longa (modo de economia de bateria) ou deslize para a direita para um desempenho mais rápido.

![Figura 2. Controle deslizante de energia](images/powerintrofig2a.png)

Figura 2. Controle deslizante de energia

O controle deslizante de energia habilita quatro estados conforme descrito na tabela a seguir:

| Modo de controle deslizante| Descrição |
|---|---|
| Economia de bateria| Ajuda a economizar energia e prolongar a duração da bateria quando o sistema é desconectado de uma fonte de energia. Quando a economia de bateria está activada, alguns recursos do Windows são desabilitados, aceleradores ou se comportam de maneira diferente. O brilho da tela também é reduzido. A economia de bateria só está disponível ao usar a energia da bateria (DC). Para saber mais, consulte [Economia de Bateria.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)|
| Recomendações | Oferece duração de bateria mais longa do que as configurações padrão em versões anteriores do Windows. |
| Melhor desempenho | Favorece um pouco o desempenho em relação à duração da bateria, funcionando como o modo de controle deslizante padrão. |
| Melhor desempenho | Favoreça o desempenho sobre a energia para cargas de trabalho que exigem desempenho máximo e capacidade de resposta, independentemente do consumo de energia da bateria.|

Os modos de controle deslizante de energia controlam diretamente componentes de hardware específicos mostrados na tabela a seguir.

| Componente | Funcionalidade de controle deslizante |
|---|---|
| Intel Speed Shift (registros de energia da CPU) e dica de Preferência de Desempenho de Energia. | Seleciona a melhor frequência operacional e melhor desempenho e energia. A Preferência de Desempenho de Energia (PERFEPP) é uma dica de eficiência de energia global para a CPU. |
| Velocidade do leque (RPM)| Quando aplicável, ajusta para alterar condições, como manter a ventoinha silenciosa no modo de controle deslizante de economia de bateria.|
| Limites de energia do pacote do processador (PL1/PL2).| Requer que a CPU gerencie suas opções de frequência para acomodar um limite médio de energia em execução para cargas de trabalho de estado estável (PL1) e cpu (PL2).|
| Limites de frequência de processador (limitações ia-core). | Ajusta o desempenho do processador e gráfico, permitindo que os núcleos do processador executem mais rápido ou mais lento do que a frequência operacional classificada.                                                |

>[!NOTE]
>O controle deslizante de energia é totalmente independente das configurações de energia do sistema operacional, sejam configuradas do Painel de Controle/ Opções de Energia, política de grupo ou métodos relacionados.

Para saber mais, confira:

-   [Personalizar o controle deslizante de energia de desempenho do Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Economia de bateria.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## Práticas recomendadas para duração da bateria estendida


| Prática recomendada | Vá para | Próximas etapas |
|---|---|---|                                                                                                                                    
| Certifique-se de que seu dispositivo Surface está atualizado| Windows Update | Na caixa de pesquisa da barra de tarefas, digite **Windows Update** e selecione Verificar se **há atualizações.** |
| Escolha a melhor configuração de energia para o que você está fazendo | Controle deslizante de energia | Na barra de tarefas, selecione o ícone de bateria e escolha Melhor **desempenho**, **Melhor**duração da bateria ou algum lugar entre eles.|
| Economizar bateria quando estiver baixa | Economia de bateria | Na barra de tarefas, selecione o ícone de bateria e clique **em Configurações de bateria.** Selecione **Turn battery saver on automatically if my battery falls below** and then move the slider further to the right for longer battery life. |
| Configurar o brilho ideal da tela | Economia de bateria | Na barra de tarefas, selecione o ícone de bateria e clique em Configurações de **bateria,** selecione Baixo brilho da tela enquanto **estiver na economia de bateria.** |
| Economizar energia sempre que você não estiver conectado | Economia de bateria| Selecione **Ativar status de economia de bateria até a próxima carga.**|
| Investigue problemas com as configurações de energia. | Solução de problemas de energia | Na pesquisa da barra de tarefas para solucionar problemas, selecione **Solucionar**problemas e, em seguida, selecione **Energia** e siga as instruções.|
| Verificar o uso do aplicativo | Seus aplicativos | Feche os aplicativos.|
| Verifique se há danos no cabo de alimentação.| Seu cabo de alimentação | Substitua o cabo de alimentação se estiver danificado ou danificado.|

##  <a name="learn-more"></a>Saiba mais 

- [Modo de espera moderno](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personalizar o controle deslizante de energia de desempenho do Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Economia de bateria](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Gerenciar e implantar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md)
