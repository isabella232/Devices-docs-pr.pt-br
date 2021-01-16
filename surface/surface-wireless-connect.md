---
title: Otimizar conectividade Wi-Fi para dispositivos Surface
description: Este tópico descreve as configurações Wi-Fi para garantir que os dispositivos Surface permaneçam conectados em ambientes de rede congestionados e cenários móveis.
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
ms.date: 01/15/2021
ms.openlocfilehash: 69ca7bc7383a122dfd4f069135319b92ff7edfb0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271375"
---
# Otimizar conectividade Wi-Fi para dispositivos Surface


Para permanecer conectado com a duração da bateria o dia todo, os dispositivos Surface implementam configurações de conectividade sem fio que equilibram o desempenho e a carga de energia. Fora dos cenários de mobilidade mais exigentes, os usuários podem manter conectividade sem fio suficiente sem modificar o adaptador de rede padrão ou as configurações relacionadas. Esta página destaca as principais considerações de conectividade sem fio em cenários móveis usando os dispositivos Surface mais recentes, incluindo Surface Pro 7+, Surface Laptop Go, Surface Go 2, Surface Pro X, Surface Laptop 3, Surface Book 3 e Surface Pro 7.

## Pré-requisitos

Este documento assume que você implantou com êxito uma rede sem fio que oferece suporte a 802.11n (Wi-Fi 4) ou posterior, de acordo com as recomendações de práticas recomendações de fornecedores de equipamentos líderes.

## Configurando pontos de acesso para os recursos de roaming ideais

Se você estiver gerenciando uma rede sem fio normalmente acessada por vários tipos diferentes de dispositivos cliente, é recomendável habilitar protocolos específicos em pontos de acesso (APs) em sua WLAN, conforme descrito em Fast Roaming com [802.11k, 802.11v e 802.11r.](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r) Os dispositivos Surface podem tirar proveito dos seguintes protocolos sem fio:

- **802.11r.** "Transição**rápida do BSS"** acelera a conexão a novos pontos de acesso sem fio, reduzindo o número de quadros necessários para que seu dispositivo possa acessar outro AP à medida que você se move com seu dispositivo. Na nova geração de dispositivos Surface lançada desde 2019, os usuários finais podem obter acesso às configurações de agressiva de roaming em seus dispositivos. Embora não seja recomendável modificar as configurações padrão, os usuários devem estar cientes desse recurso e entender como configurações específicas podem afetar sua capacidade de permanecer conectada.
- **802,11k.** **"Relatórios de Vizinhos"** fornece aos dispositivos informações sobre as condições atuais nos pontos de acesso vizinhos. Ele pode ajudar o dispositivo Surface a escolher o melhor AP usando critérios diferentes da intensidade do sinal, como a utilização de AP.

Dispositivos Surface específicos também podem usar "Quadros de Gerenciamento de Transição BSS" 802.11v, que funciona muito como 802,11k no fornecimento de informações sobre PAs candidatos próximos. Isso inclui o Surface Pro 7+, o Surface Go, o Surface Go 2, o Surface Pro 7, o Surface Pro X e o Surface Laptop 3. 

## Gerenciando configurações do usuário

Você pode obter os recursos de roaming ideais por meio de uma rede bem projetada que dá suporte a 802.11r e 802.11k em todos os pontos de acesso. Garantir que sua rede seja configurada corretamente para fornecer aos usuários a melhor experiência sem fio é a abordagem recomendada em vez de tentar gerenciar as configurações do usuário em dispositivos individuais. 

### Configurações de usuário recomendadas e práticas recomendadas

Em determinadas situações, modificar as configurações avançadas do adaptador de rede integrados aos dispositivos Surface pode facilitar uma conexão mais confiável. Tenha em mente, no entanto, que a incapacidade de se conectar a recursos sem fio ocorre com mais frequência devido a um problema de ponto de acesso, falha no design de rede ou problema de site ambiental.

> [!NOTE]
> A forma como você mantém o Surface Pro ou o Surface Go também pode afetar a intensidade do sinal. Se você estiver enfrentando uma perda de largura de banda, verifique se não está segurando a parte superior da tela, onde o receptor de rádio Wi-Fi está localizado. Embora manter a parte superior da tela não bloqueie sinais sem fio, ele pode disparar o driver de dispositivo para iniciar alterações que reduzem a conectividade.

### Manter a configuração automática padrão para o recurso de largura de banda dupla

Na maioria dos dispositivos Surface, você pode definir as configurações do adaptador de rede do cliente para se conectar somente a PAs sem fio com mais de 5 gigahertz (GHz), conectar-se apenas a 2,4 GHz ou permitir que o sistema operacional escolha a melhor opção (configuração automática padrão).

**Para acessar as configurações do adaptador de rede, vá para:**

- **Iniciar**  >  **Painel de controle**  >  **Central de Rede e Compartilhamento**  >  **seu adaptador Wi-Fi usuário**  >  **Propriedades**  >  **Configurar**  >  **Avançado**.

![* wifi-band settings*](images/wifi-band.png) <br>

Tenha em mente que 2,4 GHz tem algumas vantagens em relação a 5 GHz: ele se estende mais e mais facilmente atravessa paredes ou outros objetos sólidos. A menos que você tenha um caso de uso claro que garante a conexão a 5 GHz, é recomendável deixar a configuração de Banda no estado padrão para evitar possíveis consequências adversas. Por exemplo:


- Muitos hotspots encontrados em restaurantes, cafeterias e aeroportos ainda usam apenas 2,4 GHz, bloqueando efetivamente o acesso a dispositivos se a Faixa estiver definida como Somente 5 GHz.
- Como as conexões de exibição sem fio miracast exigem que o handshake inicial seja concluído em canais de 2,4 GHz, os dispositivos não poderão se conectar somente a 5 GHz.

> [!NOTE]
> Por padrão, os dispositivos Surface preferem se conectar a 5 GHz, se disponíveis. No entanto, para preservar a energia em um estado de bateria baixa, o Surface procurará primeiro uma conexão de 2,4 GHz.

Você também pode alternar a configuração de banda conforme necessário para se adequar ao seu ambiente. Por exemplo, os usuários que moram em edifícios de apartment de alta densidade com vários hotspots do Wi-Fi — que interagem com a presença de dispositivos de consumidor, todos transmitidos por 2,4 GHz — provavelmente se beneficiarão configurando seu dispositivo Surface para se conectar somente em 5 GHz e, em seguida, reverter para Automático quando necessário.

### Configurações de postura de roaming em dispositivos Surface com adaptadores Intel 

Os usuários podem querer selecionar um limite de força do sinal que solicita ao dispositivo que procure um novo ponto de acesso quando o sinal cai (intensidade de roaming). Por padrão, dispositivos Surface com adaptadores Intel tentam transitar para um novo ponto de acesso se a intensidade do sinal cair abaixo de **Médio** (intensidade do sinal de 72%). Observe também que as organizações podem implementar protocolos sem fio de propósito em vários pontos de acesso à rede para facilitar o roaming em ambientes de rede congestionados, conforme explicado anteriormente nesta página. 

Embora o aumento da agressiva de roaming acima de **Médio** possa gerar conectividade aprimorada em ambientes de escritório ou ambientes altamente congestionados, isso pode resultar em conectividade degradada ao sair desses ambientes. 

É recomendável deixar a configuração de agressiva de roaming no estado padrão, a menos que você esteja encontrando problemas de conectividade em cenários móveis específicos, como a realização de inspeções ambientais do site, além de manter a conectividade de voz e vídeo durante uma reunião de conferência. Se você não observar nenhuma melhoria, reverta para o estado médio padrão. Observe que, se você aumentar a agressivaidade de roaming, também acelera o consumo de energia da bateria. 

**Para habilitar a agressivaidade de roaming no Surface:**

1. Vá para **Iniciar o**Gerenciador  >  **de Dispositivos.**
2. Em **Adaptadores de rede,** selecione **Intel Wi-Fi 6** e clique com o botão direito do mouse em **Propriedades.**
3. Selecione a **guia** Avançado.
4. Selecione **a postura de roaming** e escolha seu valor preferido no menu suspenso.

![* Roaming aggressiveness settings -Intel *](images/wifi-roaming-int.png) <br>

### Configurações de postura de roaming no Surface Go e no Surface Pro X

Os funcionários de linha de frente que usam o Surface Go podem querer selecionar um limite de força do sinal que solicita ao dispositivo que procure um novo ponto de acesso quando o sinal de força cai (intensidade móvel). Por padrão, os dispositivos Surface tentam transitar para um novo ponto de acesso se a intensidade do sinal cair abaixo de **Médio** (intensidade do sinal de 50%). Observe que sempre que você aumenta a agressivaidade de roaming, acelera o consumo de energia da bateria.

Deixe a configuração de agressivação de roaming no estado padrão, a menos que você esteja encontrando problemas de conectividade em cenários móveis específicos, como a realização de inspeções do site ambiental, além de manter a conectividade de voz e vídeo durante uma reunião de conferência. Se você não perceber nenhuma melhoria, reverta para o estado **médio** padrão.

**Para habilitar a agressivaidade de roaming no Surface Go:**

1. Vá para **Iniciar > Rede do Painel de**Controle e Rede e Centro de  >  ****  >  **Compartilhamento da Internet.**
2. Em **Conexões,** **selecione Wi-Fi** e, em seguida, **Selecione Propriedades.**
3. Selecione **Client for Microsoft Networks** e, em seguida, **configure**
4. Selecione **a Agressiva**de  >  **Roaming Avançado** e escolha seu valor preferencial no menu suspenso.

![* Roaming aggressiveness settings-QualComm *](images/wifi-roaming.png) <br>


## Conclusão

Os dispositivos Surface são projetados com configurações padrão para uma conectividade sem fio ideal balanceada junto com a necessidade de preservar a duração da bateria. A maneira mais eficaz de permitir conectividade confiável para dispositivos Surface é por meio de uma rede bem projetada que dá suporte a 802.11r e 802.11k. Os usuários podem ajustar as configurações do adaptador de rede ou a agressiva roaming, mas só devem fazer isso em resposta a fatores ambientais específicos e reverter para o estado padrão se não houver melhoria perceptível.
