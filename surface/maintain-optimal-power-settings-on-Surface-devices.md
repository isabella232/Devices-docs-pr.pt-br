---
title: Práticas recomendadas de configurações de energia para dispositivos Surface
description: Este tópico fornece recomendações de práticas recomendadas para manter as configurações de energia ideais e explica como a superfície simplifica a experiência de gerenciamento de energia. Este artigo se aplica a todos os dispositivos de superfície com suporte no momento, incluindo Surface Pro 7, Surface Pro X e Surface laptop 3.
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
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830267"
---
# Práticas recomendadas de configurações de energia para dispositivos Surface

Os dispositivos Surface destinam-se ao aproveitamento dos avanços mais recentes no consumo de energia do dispositivo móvel para oferecer uma experiência simplificada otimizada entre cargas de trabalho. Dependendo do que você estiver fazendo, a superfície ajusta dinamicamente ajusta o fluxo de energia para componentes de hardware individuais, o que, momentaneamente, apresenta os componentes do sistema para lidar com tarefas em segundo plano, como um email de entrada ou um tráfego de rede, antes de retornar a um estado ocioso de baixo consumo de energia (S0ix).

## Resumo das recomendações para administradores de ti

Para garantir que os dispositivos Surface em toda a sua organização beneficiem-se totalmente dos recursos de otimização de energia do Surface

-  Instale os drivers e firmware mais recentes do Windows Update ou do driver de superfície e do MSI do firmware. Isso cria o plano de energia balanceada (também conhecido como perfil de energia) e configura as configurações de energia ideais.  Para obter mais informações, consulte [gerenciar e implantar driver de superfície e atualizações de firmware](manage-surface-driver-and-firmware-updates.md).
- Evite criar perfis de energia personalizados ou ajustar as configurações de energia avançadas não visíveis na interface do usuário padrão (energia do**sistema**  >  **& repouso**).
- Se você deve gerenciar o perfil de energia de dispositivos em toda a rede (por exemplo, em organizações altamente gerenciadas), use a ferramenta de comando Powercfg para exportar o plano de energia da imagem de fábrica do dispositivo Surface e, em seguida, importá-lo para o pacote de provisionamento para seus dispositivos Surface. 

    >[!NOTE]
    >Você só pode exportar um plano de energia no mesmo tipo de dispositivo de superfície.  Por exemplo, não é possível exportar um plano de energia do Surface laptop e importá-lo no Surface pro.  Para obter mais informações, consulte [definir configurações de energia](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).

- Exclua os dispositivos de superfície de todas as configurações de política de gerenciamento de energia existentes. 

## Tela de fundo

A superfície que implementa o gerenciamento de energia difere significativamente do padrão anterior do sistema operacional que reduz gradualmente e desliga a energia por meio de uma série de Estados de repouso; por exemplo, percorrendo o S1, S2, S3 e assim por diante.

Em vez disso, a superfície é transportada com um perfil de energia personalizado que substitui a funcionalidade de suspensão e consumo de energia herdada pelos recursos de espera moderna e ajuste dinâmico de multas. Este perfil de energia personalizado é implementado por meio do driver do Surface Hub e do módulo do agregador do sistema (SAM). O chip SAM funciona como o proprietário da política de energia do dispositivo Surface, usando algoritmos para calcular os requisitos de energia ideais. Ele funciona em conjunto com o Windows Power Manager para atribuir ou acelerar apenas a quantidade exata de energia necessária para que os componentes de hardware funcionem. Este artigo se aplica a todos os dispositivos de superfície com suporte no momento, incluindo Surface Pro 7, Surface Pro X e Surface laptop 3.

## Usando o perfil de energia personalizado na superfície

Se você entrar nas opções de energia em um dispositivo Surface, verá que há um único plano de energia disponível. Este é o perfil de energia personalizado. E se você acessar as configurações avançadas de energia, verá um subconjunto muito menor de opções de energia em comparação a um PC genérico executando o Windows 10. Ao contrário dos dispositivos genéricos, a superfície tem firmware e componentes personalizados para gerenciar essas opções de energia.


## Modo de espera moderno

O perfil de energia personalizado algorithmically incorporado permite a conectividade em espera moderna para a superfície, mantendo um estado de baixa energia para a funcionalidade instantânea/instantâneo típica dos smartphones. S0ix, também conhecido como estado de plataforma ociosa de tempo de execução mais profundo (DRIPS), é o modo de energia padrão para dispositivos Surface. O modo de espera moderno tem dois modos:

- **Conectado em espera.** O modo padrão para a entrega de emails, mensagens e dados sincronizados em nuvem até o momento em que o modo de espera conectado mantém o Wi-Fi ligado e mantém a conectividade de rede.

- **Espera desconectada.** Um modo opcional para a duração da bateria estendida, o standby desconectado oferece a mesma experiência instantânea e poupa energia, desativando o Wi-Fi, Bluetooth e conectividade de rede relacionada.

Para saber mais sobre o modo de espera moderno, consulte o [centro de desenvolvimento de hardware da Microsoft](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).

## Como a superfície simplifica a experiência de gerenciamento de energia 

Surface integra os seguintes recursos projetados para ajudar os usuários a otimizar a experiência de gerenciamento de energia:

- [Plano de energia singular](#singular-power-plan)

- [Interface do usuário de configurações de energia simplificada](#simplified-power-settings-user-interface)

- [Controle deslizante de desempenho do Windows](#windows-performance-power-slider)

### Plano de energia singular

A Surface foi projetada para uma experiência de gerenciamento de energia simplificada que elimina a necessidade de criar planos de energia personalizados ou definir manualmente as configurações de energia. A Microsoft otimiza a experiência do usuário fornecendo um plano de energia único (balanceado) que substitui os vários planos de energia das compilações padrão do Windows.

### Interface do usuário de configurações de energia simplificada

Surface fornece uma interface do usuário simplificada do acordo com as recomendações de configuração de energia recomendada. Em geral, é recomendável ajustar apenas as configurações visíveis na interface do usuário padrão e evitar definir configurações avançadas de energia ou configurações de política de grupo. Usando os tempos limite de tela e de suspensão padrão ao evitar níveis máximos de brilho são as maneiras mais eficientes para os usuários manterem a duração da bateria estendida.

![Figura 1. Configurações de suspensão & de energia simplificadas](images/powerintrofig1.png)

Figura 1. Configurações de energia e suspensão simplificadas

### Controle deslizante de desempenho do Windows

Os dispositivos de superfície que executam o Windows 10 Build 1709 e posterior incluem um controle deslizante de energia que permite priorizar a duração da bateria quando necessário ou favorecer o desempenho, se desejado. Você pode acessar o controle deslizante de energia na barra de tarefas clicando no ícone de bateria. Deslize para a esquerda para maior duração da bateria (modo de economia de bateria) ou deslize para a direita para obter um desempenho mais rápido.

![Figura 2. Controle deslizante de energia](images/powerintrofig2a.png)

Figura 2. Controle deslizante de energia

O controle deslizante de energia permite quatro Estados conforme descrito na tabela a seguir:

| Modo deslizante| Descrição |
|---|---|
| Economia de bateria| Ajuda a economizar energia e prolongar a bateria quando o sistema está desconectado de uma fonte de energia. Quando a economia de bateria está ativada, alguns recursos do Windows são desativados, regulados ou comportam-se de forma diferente. O brilho da tela também é reduzido. O recurso economia de bateria só está disponível ao usar o recurso de energia da bateria (CC). Para saber mais, consulte [economia de bateria](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).|
| Recomendações | Oferece duração da bateria mais longa do que as configurações padrão nas versões anteriores do Windows. |
| Melhor desempenho | Favorece levemente o desempenho na duração da bateria, funcionando como modo de controle deslizante padrão. |
| Melhor desempenho | Favorece o desempenho em vez de poder para cargas de trabalho que exigem máximo desempenho e capacidade de resposta, independentemente do consumo de energia da bateria.|

Os modos de controle deslizante de energia controlam diretamente componentes de hardware específicos mostrados na tabela a seguir.

| Componente | Funcionalidade de controle deslizante |
|---|---|
| Intel Speed Shift (CPU CPU) e dica de preferência de desempenho de energia. | Seleciona a melhor frequência de operação e voltagem para melhor desempenho e energia. A preferência de desempenho de energia (PERFEPP) é uma dica de eficiência de energia global para a CPU. |
| Velocidade do ventilador (RPM)| Quando aplicável, o ajusta-se às condições variáveis como manter o ventilador silencioso no modo de controle deslizante de economia de bateria.|
| Limites de energia do pacote do processador (PL1/PL2).| Requer que a CPU gerencie suas opções de frequência para acomodar um limite de energia médio em execução para cargas de trabalho de estado estacionário (PL1) e Turbo (PL2).|
| Limites de frequência do processador de Turbo (limitações IA Turbo). | Ajusta o desempenho do processador e do gráfico, permitindo que os núcleos do processador sejam executados mais rapidamente ou mais lentos do que a frequência de operação nominal.                                                |

>[!NOTE]
>O controle deslizante de energia é totalmente independente das configurações de energia do sistema operacional, seja configurado no painel de controle/opções de energia, política de grupo ou métodos relacionados.

Para saber mais, consulte:

-   [Personalizar o controle deslizante do Power performance do Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Economia de bateria.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## Práticas recomendadas para a duração da bateria estendida


| Prática recomendada | Vá para | Próximas etapas |
|---|---|---|                                                                                                                                    
| Certifique-se de que seu dispositivo Surface esteja atualizado| Windows Update | Na caixa de pesquisa da barra de tarefas, digite **Windows Update** e selecione **verificar se há atualizações**. |
| Escolha a melhor configuração de energia para o que você está fazendo | Controle deslizante de energia | Na barra de tarefas, selecione o ícone bateria e escolha **melhor desempenho**, **melhor duração da bateria**ou em algum lugar entre elas.|
| Conservar bateria quando baixa | Economia de bateria | Na barra de tarefas, selecione o ícone bateria e clique em **configurações da bateria**. Selecione **ativar a economia de bateria automaticamente se minha bateria ficar abaixo** e, em seguida, mova o controle deslizante para a direita para a duração da bateria mais longa. |
| Configurar o melhor brilho da tela | Economia de bateria | Na barra de tarefas, selecione o ícone de bateria e clique em **configurações de bateria**, selecione **diminuir brilho da tela enquanto estiver em economia de bateria**. |
| Conservar energia sempre que não estiver conectado | Economia de bateria| Selecione **ativar o status da economia de bateria até a próxima cobrança**.|
| Investigue problemas em suas configurações de energia. | Solução de problemas de energia | Na barra de tarefas Pesquisar para solucionar problemas, selecione **solucionar problemas**e, em seguida, escolha **energia** e siga as instruções.|
| Verificar o uso do aplicativo | Seus aplicativos | Feche os aplicativos.|
| Verifique se há danos no cabo de alimentação.| O cabo de alimentação | Substitua o cabo de alimentação se gasto ou danificado.|

## Saiba mais 

- [Modo de espera moderno](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personalizar o controle deslizante do Power performance do Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Economia de bateria](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Gerenciar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md)
