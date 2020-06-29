---
title: Otimizar conectividade Wi-Fi para dispositivos Surface
description: Este tópico descreve as configurações de Wi-Fi recomendadas para garantir que os dispositivos Surface permaneçam conectados a ambientes de rede congestionados e a cenários móveis.
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
ms.openlocfilehash: 2fb64f86e3c1da0e4ba3834877548898e98fd893
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830489"
---
# Otimizar conectividade Wi-Fi para dispositivos Surface


Para ficar conectado com a vida útil da bateria de todo o dia, os dispositivos de superfície implementam configurações de conectividade sem fio que equilibram desempenho e conservação de energia. Fora dos cenários de mobilidade mais exigentes, os usuários podem manter conectividade sem fio suficiente sem modificar o adaptador de rede padrão ou configurações relacionadas. 

Em ambientes de rede congestionados, as organizações podem implementar protocolos sem fio de uso específico em vários pontos de acesso à rede para facilitar o roaming. Esta página destaca as principais considerações de conectividade sem fio em cenários de celular usando Surface Pro 3 e posterior, livro Surface, laptop Surface e Surface go.

## Pré-requisitos

Este documento pressupõe que você implantou com êxito uma rede sem fio compatível com 802.11 n (Wi-Fi 4) ou posterior, de acordo com as recomendações de práticas recomendadas dos principais fornecedores de equipamentos.

## Configurando pontos de acesso para recursos de roaming ideais

Se você estiver gerenciando uma rede sem fio geralmente acessada por muitos tipos diferentes de dispositivos cliente, é recomendável habilitar protocolos específicos nos pontos de acesso (APs) na sua WLAN, conforme descrito em [roaming rápido com 802.11 k, 802.11 v e 802.11 r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r). Os dispositivos de superfície podem tirar proveito dos seguintes protocolos sem fio:

- **802.11 r.** A "**transição de BSS rápido"** acelera a conexão com novos pontos de acesso sem fio reduzindo o número de quadros necessários para que o dispositivo possa acessar outro AP enquanto você se move com o seu dispositivo.
- **802.11 k.** **"Relatórios de vizinho"** fornece os dispositivos com informações sobre as condições atuais em pontos de acesso vizinhos. Ele pode ajudar o dispositivo de superfície a escolher o melhor ponto de acesso usando critérios diferentes da força do sinal, como utilização do AP.

Dispositivos de superfície específicos também podem usar os "quadros de gerenciamento de transição de BSS" do 802.11 v, que funciona de forma muito semelhante ao 802.11 k para fornecer informações sobre APs de candidatos na proximidade. Eles incluem Surface Go, Surface Pro 7, Surface Pro X e Surface laptop 3. 

## Gerenciando configurações de usuário

Você pode obter recursos de roaming ideais por meio de uma rede bem projetada compatível com 802.11 r e 802.11 k em todos os pontos de acesso. Garantir que sua rede esteja configurada corretamente para fornecer aos usuários a melhor experiência sem fio é a abordagem recomendada em relação à tentativa de gerenciar as configurações de usuário em dispositivos individuais. Além disso, em muitos ambientes corporativos, os usuários de dispositivos da superfície não poderão acessar as configurações avançadas do adaptador de rede sem permissões explícitas ou direitos de administrador local. Em outras redes levemente gerenciadas, os usuários podem se beneficiar sabendo como configurações específicas podem impactar a sua capacidade de permanecer conectada.

### Configurações de usuário e práticas recomendadas recomendadas

Em determinadas situações, modificar as configurações avançadas do adaptador de rede embutida em dispositivos Surface pode facilitar uma conexão mais confiável. Não se esqueça de que uma incapacidade de se conectar a recursos sem fio é mais frequente devido a um problema de ponto de acesso, falha de design de rede ou problema no site ambiental.

> [!NOTE]
> A forma como você mantém o Surface pro ou Surface go também pode afetar a intensidade do sinal. Se você estiver sofrendo perda de largura de banda, verifique se você não está segurando a parte superior da tela, onde o receptor de rádio Wi-Fi está localizado. Embora manter o topo da tela não bloqueie sinais sem fio, ele pode disparar o driver de dispositivo para iniciar as alterações que reduzem a conectividade.

### Manter a configuração automática padrão para a funcionalidade de largura de banda dupla
Na maioria dos dispositivos de superfície, você pode definir as configurações do adaptador de rede do cliente para se conectar somente a APs sem fio mais de 5 gigahertz (GHz), conectar-se apenas em 2,4 GHz ou permitir que o sistema operacional escolha a melhor opção (configuração automática padrão).

**Para acessar as configurações do adaptador de rede, acesse:**

- **Iniciar**  >  **Painel**  >  de controle Central de rede **e compartilhamento**  >  **seu adaptador**  >  Wi-Fi **Propriedades**  >  de **Configurar**  >  o **Avançado**.

![* configurações de banda WiFi *](images/wifi-band.png) <br>

Lembre-se de que 2,4 GHz tem algumas vantagens com mais de 5 GHz: ele se estende melhor e mais fácil penetrar em paredes ou outros objetos sólidos. A menos que você tenha um caso de uso claro que garante a conexão a 5 GHz, é recomendável deixar a configuração de banda no estado padrão para evitar possíveis conseqüências adversas. Por exemplo:


- Muitos pontos de acesso encontrados em hotéis, lanchonetes e aeroportos ainda usam o 2,4 GHz, bloqueando o acesso a dispositivos se a banda estiver definida como 5 GHz somente.
- Como as conexões de exibição sem fio Miracast exigem que o handshake inicial seja concluído em canais de 2,4 GHz, os dispositivos não poderão se conectar apenas a 5 GHz.

> [!NOTE]
> Por padrão, os dispositivos de superfície preferem se conectar a 5 GHz, se disponíveis. No entanto, para preservar a energia em um estado de bateria fraca, a superfície irá primeiro procurar uma conexão de 2,4 GHz.

Você também pode mudar a configuração de banda conforme necessário para se adequar ao seu ambiente. Por exemplo, os usuários que moram em prédios Apartment de alta densidade com vários pontos de acesso Wi-Fi, ao meio da presença de dispositivos de consumo, todas as transmissões via 2,4 GHz, provavelmente serão beneficiados definindo-se o dispositivo Surface para conectar-se apenas em 5 GHz e, em seguida, reverter para auto quando necessário.

### Configurações de agressividade de roaming no Surface go

Os funcionários de linha dianteira que usam a superfície podem querer selecionar um limiar de intensidade de sinal que solicite que o dispositivo procure um novo ponto de acesso quando a força do sinal cai (agressividade de roaming). Por padrão, os dispositivos Surface tentam fazer roaming para um novo ponto de acesso se a força do sinal cair abaixo da **média** (50% de força do sinal). Observe que, sempre que você aumenta a agressividade de roaming, é possível acelerar o consumo de energia da bateria.

Deixe a configuração de agressividade de roaming no estado padrão, a menos que você esteja encontrando problemas de conectividade em cenários móveis específicos, como a condução de inspeções de site ambiental enquanto também mantém a conectividade de voz e vídeo durante uma reunião de conferência. Caso não perceba nenhuma reversão revertida para o estado **médio** padrão.

**Para habilitar a agressividade de roaming no Surface Go:**

1. Vá para **Iniciar > painel de controle**rede  >  **e**  >  **central de redes e compartilhamento** da Internet.
2. Em **conexões** , selecione **Wi-Fi** e, em seguida, selecione **Propriedades.**
3. Selecione **cliente para redes Microsoft** e, em seguida, selecione **Configurar**
4. Selecione **Advanced**  >  **agressividade de roaming** avançado e escolha seu valor preferido no menu suspenso.

![* Configurações de agressividade de roaming *](images/wifi-roaming.png) <br>

## Conclusão

Os dispositivos Surface são projetados com configurações padrão para a conectividade sem fio ideal balanceada juntamente com a necessidade de preservar a duração da bateria. A maneira mais eficiente de habilitar a conectividade confiável para dispositivos Surface é por meio de uma rede bem projetada compatível com 802.11 r e 802.11 k. Os usuários podem ajustar as configurações do adaptador de rede ou a agressividade de roaming, mas só devem fazer isso em resposta a fatores ambientais específicos e reverter para o estado padrão, se não houver melhoria perceptível.
