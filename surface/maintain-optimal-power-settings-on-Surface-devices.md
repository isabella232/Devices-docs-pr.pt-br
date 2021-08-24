---
title: Práticas recomendadas de configurações de energia para dispositivos Surface
description: Este tópico fornece recomendações de práticas para manter as configurações de energia ideais e explica como o Surface simplifica a experiência de gerenciamento de energia. Este artigo se aplica a todos os dispositivos Surface atualmente suportados, incluindo Surface Pro 7+, Surface Pro 7, Surface Pro X e Surface Laptop 3.
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
ms.openlocfilehash: 23b94c865c43ad92b7ae6f047e980084760e4aed
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911746"
---
# <a name="best-practice-power-settings-for-surface-devices"></a>Práticas recomendadas de configurações de energia para dispositivos Surface

Os dispositivos Surface foram projetados para aproveitar os últimos avanços no consumo de energia de dispositivo móvel para oferecer uma experiência simplificada otimizada em cargas de trabalho. Dependendo do que você está fazendo, o Surface ajusta dinamicamente como a energia flui para componentes de hardware individuais, a acordar momentaneamente os componentes do sistema para lidar com tarefas em segundo plano , como um email de entrada ou tráfego de rede, antes de retornar para um estado de ociosidade de baixa potência (S0ix).

## <a name="summary-of-recommendations-for-it-administrators"></a>Resumo das recomendações para administradores de IT

Para garantir que os dispositivos Surface em toda a sua organização se beneficiem totalmente dos recursos de otimização de energia do Surface:

-  Instale os drivers e firmware mais recentes do Windows Update ou do Surface Driver e firmware MSI. Isso cria o plano de energia balanceado (também conhecido como perfil de energia) por padrão e configura as configurações de energia ideais.  Para obter mais informações, consulte [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).
- Evite criar perfis de energia personalizados ou ajustar configurações de energia avançadas não visíveis na interface do usuário padrão (**System**  >  **Power & sleep**).
- Se você deve gerenciar o perfil de energia de dispositivos em sua rede (como em organizações altamente gerenciadas), use a ferramenta de comando powercfg para exportar o plano de energia da imagem de fábrica do dispositivo Surface e importá-lo para o pacote de provisionamento para seus dispositivos Surface. 

    >[!NOTE]
    >Você só pode exportar um plano de energia no mesmo tipo de dispositivo Surface.  Por exemplo, você não pode exportar um plano de energia do Surface Laptop e importá-lo em Surface Pro.  Para obter mais informações, consulte [Configure power settings](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).

- Exclua dispositivos Surface de qualquer configuração de política de gerenciamento de energia existente. 

## <a name="background"></a>Tela de fundo

A maneira como o Surface implementa o gerenciamento de energia difere significativamente do padrão anterior do sistema operacional que reduz gradualmente e desliga a energia por meio de uma série de estados de sono; por exemplo, passar por S1, S2, S3 e assim por diante.

Em vez disso, o Surface é imagens com um perfil de energia personalizado que substitui a funcionalidade herdada de consumo de energia e suspensão por recursos de espera modernos e ajuste dinâmico de ajuste. Esse perfil de energia personalizado é implementado por meio do Surface Serial Hub Driver e do módulo de agregação do sistema (SAM). O chip SAM funciona como o proprietário da política de energia do dispositivo Surface, usando algoritmos para calcular os requisitos de energia ideais. Ele funciona em conjunto com o Windows de energia para alocar ou acelerar apenas a quantidade exata de energia necessária para que os componentes de hardware funcionem. Este artigo se aplica a todos os dispositivos Surface atualmente suportados, incluindo Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X e Surface Laptop 3.

## <a name="utilizing-the-custom-power-profile-in-surface"></a>Utilizando o perfil de energia personalizado no Surface

Se você entrar nas opções de energia em um dispositivo surface, verá que há um único plano de energia disponível. Este é o perfil de energia personalizado. E se você for para as configurações de energia avançadas, verá um subconjunto muito menor de opções de energia em comparação com um computador genérico que executa Windows 10. Diferentemente de dispositivos genéricos, o Surface tem firmware e componentes personalizados para gerenciar essas opções de energia.


## <a name="modern-standby"></a>Espera moderna

O perfil de energia personalizado incorporado por algoritmos habilita a conectividade de espera moderna para o Surface mantendo um estado de energia baixo para a funcionalidade instantânea on/instant off típica dos smartphones. O S0ix, também conhecido como Estado da Plataforma Ociosa do Tempo de Execução Mais Profundo (PINGOS), é o modo de energia padrão para dispositivos Surface. O modo de espera moderno tem dois modos:

- **Espera conectada.** O modo padrão para entrega completa de emails, mensagens e dados sincronizados na nuvem, o modo de espera conectado mantém a Wi-Fi e mantém a conectividade de rede.

- **Espera desconectada.** Um modo opcional para a duração estendida da bateria, o modo de espera desconectado oferece a mesma experiência instantânea e economiza energia ao desligar o Wi-Fi, o Bluetooth e a conectividade de rede relacionada.

Para saber mais sobre o modo de espera moderno, consulte o [microsoft Centro de Desenvolvimento de Hardware](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).

## <a name="how-surface-streamlines-the-power-management-experience"></a>Como o Surface simplifica a experiência de gerenciamento de energia 

O Surface integra os seguintes recursos projetados para ajudar os usuários a otimizar a experiência de gerenciamento de energia:

- [Plano de energia singular](#singular-power-plan)

- [Interface do usuário configurações de energia simplificadas](#simplified-power-settings-user-interface)

- [Windows controle deslizante de energia de desempenho](#windows-performance-power-slider)

### <a name="singular-power-plan"></a>Plano de energia singular

O Surface foi projetado para uma experiência de gerenciamento de energia simplificada que elimina a necessidade de criar planos de energia personalizados ou configurar manualmente as configurações de energia. A Microsoft simplifica a experiência do usuário entregando um único plano de energia (balanceado) que substitui os vários planos de energia de Windows builds padrão.

### <a name="simplified-power-settings-user-interface"></a>Interface do usuário configurações de energia simplificadas

O Surface fornece uma interface do usuário simplificada de acordo com as recomendações de configuração de energia de práticas. Em geral, é recomendável ajustar apenas as configurações visíveis na interface do usuário padrão e evitar configurar configurações avançadas de energia ou configurações de Política de Grupo. Usar a tela padrão e os tempos limite de luminosidade padrão, evitando níveis máximos de brilho, são as maneiras mais eficazes para os usuários manterem a vida útil estendida da bateria.

![Figura 1. Configurações de & de sono simplificadas.](images/powerintrofig1.png)

Figura 1. Configurações simplificadas de energia e sono

### <a name="windows-performance-power-slider"></a>Windows controle deslizante de energia de desempenho

Os dispositivos Surface que executam Windows 10 build 1709 e posterior incluem um controle deslizante de energia que permite priorizar a vida útil da bateria quando necessário ou favorecer o desempenho, se desejado. Você pode acessar o controle deslizante de energia da barra de tarefas clicando no ícone da bateria. Deslize para a esquerda para maior duração da bateria (modo de economia de bateria) ou deslize para a direita para um desempenho mais rápido.

![Figura 2. Controle deslizante de energia.](images/powerintrofig2a.png)

Figura 2. Controle deslizante de energia

O controle deslizante de energia habilita quatro estados conforme descrito na tabela a seguir:

| Modo de controle deslizante| Descrição |
|---|---|
| Economia de bateria| Ajuda a economizar energia e prolongar a vida útil da bateria quando o sistema é desconectado de uma fonte de energia. Quando a economia de bateria está a ser aplicada, alguns Windows recursos são desabilitados, recarrados ou se comportam de maneira diferente. O brilho da tela também é reduzido. A economia de bateria só está disponível ao usar a energia da bateria (DC). Para saber mais, confira [Economia de Bateria](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).|
| Recomendações | Oferece maior duração da bateria do que as configurações padrão em versões anteriores do Windows. |
| Melhor desempenho | Favorece ligeiramente o desempenho sobre a duração da bateria, funcionando como o modo de controle deslizante padrão. |
| Melhor desempenho | Favorece o desempenho sobre a energia para cargas de trabalho que exigem desempenho máximo e capacidade de resposta, independentemente do consumo de energia da bateria.|

Os modos de controle deslizante de energia controlam diretamente componentes de hardware específicos mostrados na tabela a seguir.

| Componente | Funcionalidade do controle deslizante |
|---|---|
| Intel Speed Shift (registros de energia da CPU) e Dica de Preferência de Desempenho de Energia. | Seleciona a melhor frequência operacional e tensão para o desempenho e a potência ideais. A Preferência de Desempenho de Energia (PERFEPP) é uma dica de eficiência de energia global para a CPU. |
| Velocidade do fan (RPM)| Quando aplicável, ajusta as condições de alteração, como manter o fan silencioso no modo de controle deslizante de economia de bateria.|
| Limites de energia do pacote do processador (PL1/PL2).| Exige que a CPU gerencie suas opções de frequência para acomodar um limite médio de energia em execução para cargas de trabalho de estado estável (PL1) e de turbo (PL2).|
| Limites de frequência de turbo do processador (limitações do IA turbo). | Ajusta o desempenho do processador e gráfico permitindo que os núcleos do processador executem mais rápido ou mais lento do que a frequência operacional classificada.                                                |

>[!NOTE]
>O controle deslizante de energia é totalmente independente das configurações de energia do sistema operacional, sejam configuradas do Painel de Controle/ Opções de Energia, Política de Grupo ou métodos relacionados.

Para saber mais, confira:

-   [Personalizar o controle deslizante Windows desempenho](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Economia de bateria.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## <a name="best-practices-for-extended-battery-life"></a>Práticas recomendadas para a duração estendida da bateria


| Prática recomendada | Vá para | Próximas etapas |
|---|---|---|                                                                                                                                    
| Verifique se o dispositivo Surface está atualizado| Windows Update | Na caixa de pesquisa da barra de tarefas, digite **Windows Atualizar** e selecione Verificar se **há atualizações**. |
| Escolha a melhor configuração de energia para o que você está fazendo | Controle deslizante de energia | Na barra de tarefas, selecione o ícone da bateria e escolha **Melhor desempenho**, **Melhor**duração da bateria ou em algum lugar entre eles.|
| Economizar bateria quando estiver baixa | Economia de bateria | Na barra de tarefas, selecione o ícone de bateria e clique **em Configurações de bateria**. Selecione **Ativar automaticamente a economia de** bateria se minha bateria ficar abaixo e, em seguida, mover o controle deslizante para a direita para maior duração da bateria. |
| Configurar o brilho ideal da tela | Economia de bateria | Na barra de tarefas, selecione o ícone de bateria e clique em **Configurações**de bateria, selecione Brilho inferior da tela enquanto estiver na **economia de bateria**. |
| Economizar energia sempre que você não estiver conectado | Economia de bateria| Selecione **Ativar o status do economia de bateria até a próxima carga.**|
| Investigue problemas com suas configurações de energia. | Solução de problemas de energia | Na pesquisa da Barra de Tarefas para solução de problemas, selecione **Solucionar**problemas e, em seguida, selecione **Power** e siga as instruções.|
| Verificar o uso do aplicativo | Seus aplicativos | Feche aplicativos.|
| Verifique se o cabo de alimentação está danificado.| Seu cabo de alimentação | Substitua o cabo de alimentação se estiver gasto ou danificado.|

## <a name="learn-more"></a>Saiba mais 

- [Espera moderna](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personalizar o controle deslizante Windows desempenho](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Economia de bateria](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Gerenciar e implantar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md)
