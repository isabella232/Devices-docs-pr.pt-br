---
title: Otimizar conectividade Wi-Fi para dispositivos Surface
description: Este tópico descreve as configurações recomendadas Wi-Fi para garantir que os dispositivos Surface permaneçam conectados em ambientes de rede congestionados e cenários móveis.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.date: 11/30/2021
ms.openlocfilehash: e031b485979b20d6206398840466d553772b6f1d
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338244"
---
# <a name="optimize-wi-fi-connectivity-on-surface-devices"></a>Otimizar Wi-Fi conectividade em dispositivos Surface

Para permanecer conectado com a duração da bateria de todos os dias, os dispositivos Surface implementam configurações de conectividade sem fio que equilibram o desempenho e a conservação de energia. Fora das cargas de trabalho de mobilidade mais exigentes, os usuários podem manter conectividade sem fio suficiente sem modificar o adaptador de rede padrão ou configurações relacionadas. Esta página destaca as principais considerações de conectividade sem fio em cenários móveis usando dispositivos Surface.

## <a name="prerequisites"></a>Pré-requisitos

Este documento supõe que você implantou com êxito uma rede sem fio que oferece suporte a 802.11n (Wi-Fi 4) ou posterior após as recomendações de práticas práticas de fornecedores de equipamentos líderes.

## <a name="configuring-access-points-for-optimal-roaming-capabilities"></a>Configurando pontos de acesso para recursos de roaming ideais

Suponha que você esteja gerenciando uma rede sem fio que normalmente é acessada por vários tipos diferentes de dispositivos cliente. Nesse caso, é recomendável habilitar protocolos específicos em pontos de acesso (APs) em seu WLAN, conforme descrito em [Roaming Rápido com 802.11k, 802.11v e 802.11r](/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r). Os dispositivos Surface podem aproveitar os seguintes protocolos sem fio:

- **802.11r.** O "**Fast BSS Transition"** acelera a conexão com novos pontos de acesso sem fio reduzindo o número de quadros necessários para que o dispositivo possa acessar outra AP à medida que você se move com seu dispositivo. Na nova geração de dispositivos Surface lançados desde 2019, os usuários finais podem obter acesso às configurações de agressão móvel em seus dispositivos. Embora a modificação das configurações padrão não seja recomendada, os usuários devem estar cientes desse recurso e entender como configurações específicas podem afetar sua capacidade de permanecer conectada.
- **802,11k.** **"Relatórios de vizinhos"** fornece aos dispositivos informações sobre as condições atuais em pontos de acesso vizinhos. Ele pode ajudar seu dispositivo Surface a escolher a melhor AP usando critérios diferentes da força do sinal, como a utilização de AP.

Dispositivos Surface específicos também podem usar 802.11v "Quadros de Gerenciamento de Transição BSS", que funciona de forma semelhante a 802,11k no fornecimento de informações sobre APs candidatos próximos. Eles incluem Surface Pro 8, Surface Pro 7+, Surface Laptop Studio, Surface Go 3, Surface Go 2, Surface Go, Surface Pro 7, Surface Pro X e Surface Laptop 3.

## <a name="managing-user-settings"></a>Gerenciando configurações do usuário

Você pode obter recursos de roaming ideais por meio de uma rede bem projetada que oferece suporte a 802.11r e 802,11k em todos os pontos de acesso. Garantir que sua rede seja configurada adequadamente para fornecer aos usuários a melhor experiência sem fio é a abordagem recomendada em vez de gerenciar as configurações do usuário em dispositivos individuais.

### <a name="recommended-user-settings-and-best-practices"></a>Configurações recomendadas e práticas recomendadas do usuário

Em determinadas situações, modificar configurações avançadas de adaptador de rede internas em dispositivos Surface pode facilitar uma conexão mais confiável. No entanto, lembre-se de que uma incapacidade de se conectar a recursos sem fio é mais frequente devido a um problema de ponto de acesso, falha de design de rede ou problema de site ambiental.

> [!TIP]
> A forma como você mantém o Surface Pro ou o Surface Go também pode afetar a força do sinal. Se você estiver enfrentando uma perda de largura de banda, verifique se não está segurando a parte superior da tela, onde o receptor de Wi-Fi está localizado. Embora a segurando a parte superior da tela não bloqueie sinais sem fio, ela pode disparar o driver do dispositivo para iniciar alterações que reduzem a conectividade.

### <a name="keep-default-auto-setting-for-dual-bandwidth-capability"></a>Manter a configuração automática padrão para o recurso de largura de banda dupla

Na maioria dos dispositivos Surface, você pode configurar as configurações do adaptador de rede do cliente para se conectar somente a APs sem fio com mais de 5 gigahertz (GHz), se conectar apenas a mais de 2,4 GHz ou permitir que o sistema operacional escolha a melhor opção (configuração automática padrão).

**Para acessar as configurações do adaptador de rede, vá para:**

- **Iniciar** >  **Painel de controle** >  **Central de Rede e Compartilhamento** >  **seu Wi-Fi adaptador** >  **Propriedades** >  **Configurar** >  **Avançado**.

![* configurações de banda wifi*.](images/wifi-band.png) <br>

Tenha em mente que 2,4 GHz tem algumas vantagens sobre 5 GHz: ela se estende mais e mais facilmente penetra entre paredes ou outros objetos sólidos. A menos que você tenha um caso de uso claro que garante a conexão a 5 GHz, é recomendável deixar a configuração band no estado padrão para evitar possíveis consequências adversas. Por exemplo:

- Muitos hotspots encontrados em hotspots, cafeterias e aeroportos ainda usam apenas 2,4 GHz, bloqueando efetivamente o acesso a dispositivos se Band estiver definido como somente 5 GHz.
- Como Miracast conexões de exibição sem fio exigem que o handshake inicial seja concluído em canais de 2,4 GHz, os dispositivos não poderão se conectar somente a 5 GHz.

> [!NOTE]
> Por padrão, os dispositivos Surface preferem se conectar a 5 GHz, se disponíveis. No entanto, o Surface procurará primeiro uma conexão de 2,4 GHz para preservar a energia em um estado de bateria fraca.

Você também pode alternar a configuração da banda conforme necessário para se adequar ao seu ambiente. Por exemplo, os usuários que vivem em edifícios de apartamentos de alta densidade com vários hotspots de Wi-Fi — em meio à presença de dispositivos de consumo todos transmitindo por 2,4 GHz — provavelmente se beneficiarão definindo seu dispositivo Surface para se conectar somente em 5 GHz e, em seguida, reverter para Auto quando necessário.

### <a name="roaming-aggressiveness-settings-on-surface-devices-with-intel-adapters"></a>Configurações de agressividade de roaming em dispositivos Surface com adaptadores Intel

Os usuários podem desejar selecionar um limite de força de sinal que solicita ao dispositivo que procure um novo ponto de acesso quando o sinal cair (a agressividade móvel). Por padrão, os dispositivos Surface com adaptadores Intel tentam percorrer até um novo ponto de acesso se a intensidade do sinal ficar abaixo de **Medium** (72% de força do sinal). As organizações também podem implementar protocolos sem fio de propósito em vários pontos de acesso à rede para facilitar ambientes de rede congestionados em roaming, conforme explicado anteriormente nesta página.

Embora o aumento da agressividade de roaming acima **de Medium** possa gerar conectividade aprimorada em ambientes de escritório altamente congestionados ou residenciais, isso pode resultar em conectividade degradada ao sair desses ambientes.

Deixe a configuração de agressividade móvel no estado padrão, a menos que você tenha problemas de conectividade em cenários móveis específicos, como a realização de inspeções de site ambiental enquanto mantém a conectividade de voz e vídeo durante uma reunião de conferência. Se você não perceber nenhuma melhoria, reverte para o estado médio padrão. Observe que, se você aumentar a agressividade de roaming, também acelerará o consumo de energia da bateria.

**Para habilitar a agressividade de roaming no Surface:**

1. Vá para **StartDevice****** >  Manager.
2. Em **Adaptadores de rede**, selecione **Intel Wi-Fi 6** e clique com o botão direito do **mouse em Propriedades**.
3. Selecione a **guia** Avançado.
4. Selecione **Roaming Aggressiveness** e escolha seu valor preferencial no menu suspenso.

![* Configurações de agressividade de roaming-Intel *.](images/wifi-roaming-int.png) <br>

### <a name="roaming-aggressiveness-settings-on-surface-go-and-surface-pro-x"></a>Configurações de agressividade de roaming no Surface Go e Surface Pro X

Os funcionários de linha de frente que usam o Surface Go podem desejar selecionar um limite de força de sinal que solicita ao dispositivo que procure um novo ponto de acesso quando a força do sinal cair (a agressividade móvel). Por padrão, os dispositivos Surface tentarão percorrer até um novo ponto de acesso se a força do sinal ficar abaixo de **Medium** (50% de força do sinal). Observe que sempre que você aumenta a agressividade de roaming, acelera o consumo de energia da bateria.

Deixe a configuração de agressividade móvel no estado padrão, a menos que você tenha problemas de conectividade em cenários móveis específicos, como a realização de inspeções de site ambiental enquanto mantém a conectividade de voz e vídeo durante uma reunião de conferência. Se você não perceber que qualquer melhoria é revertida, para o estado **médio** padrão.

**Para habilitar a agressividade de roaming no Surface Go:**

1. Vá para **Iniciar > Painel de ControleNetwork** >  **e InternetNetwork** >  **e Centro de Compartilhamento.**
2. Em **Conexões**, selecione **Wi-Fi** e escolha **Propriedades.**
3. Selecione **Cliente para Microsoft Networks** e selecione **Configurar**
4. Selecione **AdvancedRoaming** **** >  Aggressiveness e escolha seu valor preferencial no menu suspenso.

![* Configurações de agressividade de roaming-QualComm *.](images/wifi-roaming.png) <br>

## <a name="conclusion"></a>Conclusão

Os dispositivos Surface são projetados com configurações padrão para uma conectividade sem fio ideal balanceada, juntamente com a necessidade de preservar a vida útil da bateria. A maneira mais eficaz de habilenciar a conectividade confiável para dispositivos Surface é por meio de uma rede bem projetada que oferece suporte a 802.11r e 802.11k. Os usuários podem ajustar as configurações do adaptador de rede ou a agressividade móvel, mas só devem fazer isso em resposta a fatores ambientais específicos e reverter para o estado padrão se não houver melhoria perceptível.
