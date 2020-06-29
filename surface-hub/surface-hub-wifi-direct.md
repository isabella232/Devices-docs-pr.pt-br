---
title: Como o Surface Hub resolve problemas de segurança do Wi-Fi Direct
description: Orientação sobre riscos de segurança Wi-Fi Direct.
keywords: histórico de alterações
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/27/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d877d9b6a4e330a74a9d79cf1150487d89c0da23
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830352"
---
# Como o Surface Hub resolve problemas de segurança do Wi-Fi Direct

O Microsoft Surface Hub é um dispositivo de produtividade "all-in-one" que permite que as equipes troquem, colaborem e compartilhem ideias de uma maneira melhor. O Surface Hub depende do Miracast para projeção sem fio através de Wi-Fi Direct.

Este artigo descreve as vulnerabilidades de segurança do Wi-Fi Direct, como o Surface Hub aborda esses riscos e como os administradores podem configurar o Surface Hub para o nível mais alto de segurança. Essas informações ajudarão os clientes que têm requisitos de alta segurança a proteger suas redes e dados conectados ao Hub de superfície em trânsito.

As audiências pretendidas para este artigo são e administradores de rede que desejam implantar o Surface Hub em seu ambiente corporativo com configurações de segurança ideais.

## Visão geral

A segurança do Surface Hub depende amplamente do Wi-Fi Direct/Miracast e dos padrões associados do 802,11, do Wi-Fi Protected Access (WPA2) e da configuração da rede sem fio do WPS (configuração protegida sem fio). Como o dispositivo só oferece suporte a WPS (em oposição à chave pré-compartilhada WPA2 [PSK] ou à Corporação WPA2), os problemas geralmente associados à criptografia 802,11 são simplificados.

O Surface Hub funciona em par com o campo de receptores Miracast. Portanto, ele está vulnerável a um conjunto de exploits semelhante, como todos os dispositivos de rede sem fio baseados em WPS. Mas a implementação do Surface Hub do WPS tem precauções adicionais incorporadas. Além disso, sua arquitetura interna ajuda a impedir que um invasor comprometisse a camada Wi-Fi Direct/Miracast de passar após a interface de rede para outras superfícies de ataque e redes corporativas conectadas.

## Informações básicas do Wi-Fi Direct

O Miracast faz parte do padrão de exibição de Wi-Fi, que é compatível com o protocolo Wi-Fi Direct. Esses padrões têm suporte em dispositivos móveis modernos para compartilhamento de tela e colaboração.

Wi-Fi Direct ou Wi-Fi "ponto a ponto" (P2P) é um padrão da Wi-Fi Alliance para redes "ad-hoc". Os dispositivos com suporte podem se comunicar diretamente e criar grupos de redes sem um ponto de acesso Wi-Fi convencional ou conexão à Internet.

A segurança para Wi-Fi Direct é fornecida pelo WPA2 sob o padrão WPS. O mecanismo de autenticação para dispositivos pode ser um PIN numérico (WPS-PIN), um botão de push físico ou virtual (WPS-PBC) ou uma mensagem fora de banda, como comunicação ao redor do campo (WPS-ausência temporária). O Surface Hub suporta o método PIN e o método Push-Button, que é o padrão.

No Wi-Fi Direct, os grupos são criados como um dos seguintes tipos:
- *Persistente*, em que a reconexão automática pode ocorrer usando material de chave armazenado
- *Temporário*, em quais dispositivos não é possível autenticar novamente sem a ação do usuário

Os grupos Wi-Fi Direct determinam um *proprietário do grupo* (GO) por meio de um protocolo de negociação, que imita a funcionalidade "estação" ou "ponto de acesso" do grupo Wi-Fi Direct estabelecido. O Wi-Fi Direct GO oferece autenticação (por meio de um "registrador interno") e facilita conexões de rede de upstream. Para Surface Hub, a negociação não ocorre. A rede só funciona no modo "autônomo" e o Surface Hub é sempre o proprietário do grupo. Por fim, o Surface Hub em si não se une a outras redes Wi-Fi Direct como cliente.

## Como o Surface Hub aborda as vulnerabilidades do Wi-Fi Direct

**Vulnerabilidades e ataques no processo de convite, transmissão e descoberta de Wi-Fi Direct:** Ataques Wi-Fi Direct/Miracast podem direcionar fracos no estabelecimento de grupo, descoberta de par, transmissão de dispositivo ou processos de convite.

|Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| O processo de descoberta pode permanecer ativo por um período de tempo prolongado, o que pode permitir que convites e conexões sejam estabelecidos sem a aprovação do proprietário do dispositivo. | O Surface hub só funciona como o proprietário do grupo, que não executa os processos de descoberta do cliente ou de negociação GO. Você pode desativar completamente a projeção sem fio para desativar a transmissão. |
| O convite e descoberta por meio do PBC permite que um invasor não autenticado execute tentativas de conexão repetidas, ou que as conexões não autenticadas sejam automaticamente aceitas. | Ao exigir a segurança do pino WPS, os administradores podem reduzir o potencial para tais conexões não autorizadas ou "convite bombas", em que os convites são repetidos repetidamente até que um usuário aceite incorretamente um. |

**Conexão do botão de ação do WPS (Wi-Fi Protected Setup) conecta-se (PBC) vs, entrada de PIN:** As deficiências públicas foram demonstradas no design e na implementação do método do WPS-PIN. O WPS-PBC tem outras vulnerabilidades que podem permitir ataques ativos contra um protocolo projetado para uso único.

| Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| O WPS-PBC é vulnerável a ataques ativos. A especificação WPS declara: "o método PBC tem bits zero de entropia e só protege contra ataques de espionagem passivos. O PBC protege contra ataques de interceptação e adota medidas para evitar que um dispositivo ingresse em uma rede que não tenha sido selecionada pelo proprietário do dispositivo. No entanto, a ausência da autenticação significa que o PBC não protege contra ataques ativos. " Os invasores podem usar a obstrução sem fio seletiva ou outras técnicas de negação de serviço para disparar uma conexão ou conexão direta Wi-Fi. Além disso, um invasor ativo que simplesmente tem proximidade física pode subdividir repetidamente qualquer grupo Wi-Fi Direct e tentar o ataque até que seja bem-sucedido. | Habilitar a segurança do WPS-PIN na configuração do Surface Hub. A especificação do WPS Wi-Fi diz: "o método PBC só deve ser usado se nenhum registrador compatível com PIN estiver disponível e o usuário da WLAN estiver disposto a aceitar os riscos associados ao PBC." |
| As implementações do WPS-PIN podem estar sujeitas a ataques de força bruta que destinam-se a uma vulnerabilidade no padrão WPS. O design da verificação do pino dividido leva a várias vulnerabilidades de implementação nos últimos anos em uma série de fabricantes de hardware Wi-Fi. No 2011, os pesquisadores Stefan Viehböck e Craig Heffner lançam informações sobre essa vulnerabilidade e ferramentas como "reaver" como uma prova de conceito. |   A implementação da Microsoft do WPS no Surface Hub muda o pino a cada 30 segundos. Para decifrar o PIN, um invasor deve concluir toda a exploração em menos de 30 segundos. Devido ao estado atual de ferramentas e pesquisa nesta área, um ataque de quebra de PIN de força bruta por meio do WPS provavelmente será bem-sucedido. |
| O WPS-PIN pode ser rachado por um ataque offline, devido à entropia de chave inicial fraca (E-S1, E S2). No 2014, Dominique Bongard descreveu um ataque de "poeira Pixie", em que a Random insatisfatória inicial do gerador de número aleatório (PRNG) no dispositivo sem fio permitiu um ataque de força bruta offline. | A implementação da Microsoft do WPS no Surface Hub não é suscetível a esse ataque de força bruta do pino offline. O WPS-PIN é randomizado para cada conexão. |

**Exposição não intencional dos serviços de rede:** Os daemons de rede destinados a serviços de Ethernet ou WLAN podem ser acidentalmente expostos devido a configurações incorretas (como associação a interfaces "All"/0.0.0.0). Outras causas possíveis incluem um firewall de dispositivo mal configurado ou regras de firewall ausentes.

| Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| A configuração incorreta associa um serviço de rede vulnerável ou não autenticado a "todas" as interfaces, que inclui a interface do Wi-Fi Direct. Isso pode expor serviços que não devem ser acessíveis a clientes Wi-Fi Direct, que podem ser autenticados de baixa segurança ou automática. | No Surface Hub, as regras de firewall padrão só permitem as portas de rede TCP e UDP necessárias e, por padrão, negam todas as conexões de entrada. Configurar a autenticação forte habilitando o modo WPS-PIN.|

**Ponte Wi-Fi Direct e outras redes com fio ou sem fio:** A ponte de rede entre redes WLAN ou Ethernet é uma violação da especificação do Wi-Fi Direct. Uma ponte ou uma configuração incorreta pode reduzir ou remover os controles de acesso sem fio da rede corporativa interna de forma eficaz.

| Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| Os dispositivos Wi-Fi Direct podem permitir acesso não autenticado ou autenticado incorretamente a conexões de ponte de rede. Isso pode permitir que as redes Wi-Fi Direct direcionem o tráfego para LAN interna Ethernet ou outra infraestrutura ou para redes WLAN corporativas violando os protocolos de segurança de ti existentes. | O Surface Hub não pode ser configurado para pontes para interfaces sem fio nem permitir roteamento entre redes distintas. As regras de firewall padrão adicionam segurança abrangente a qualquer uma dessas conexões de roteamento ou ponte. |

**O uso do modo "herdado" de Wi-Fi Direct:** A exposição a redes ou dispositivos não pretendidos poderá ocorrer quando você operar no modo "herdado". Conexões de falsificação ou não intencionais de dispositivos podem ocorrer quando o WPS-PIN não está habilitado.

| Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| Com o suporte para clientes de infraestrutura Wi-Fi Direct e 802.11, o sistema está operando em um modo de suporte "herdado". Isso pode expor a fase de configuração de conexão indefinidamente, permitindo que os grupos sejam associados ou que os dispositivos convidados se conectem bem após a fase de configuração desejada ser encerrada. |    O Surface Hub não oferece suporte a clientes herdados Wi-Fi Direct. Somente conexões Wi-Fi Direct podem ser feitas com o Surface Hub mesmo quando o modo WPS-PIN está habilitado. |

**Negociação do Wi-Fi Direct Go durante a configuração da conexão:** O proprietário do grupo em Wi-Fi Direct é análogo ao "ponto de acesso" em uma rede sem fio convencional 802,11. A negociação pode ser manipulada por um dispositivo mal-intencionado.

|Vulnerabilidade do Wi-Fi Direct |   Mitigação do Surface Hub |
| --- | --- |
| Se os grupos são estabelecidos dinamicamente ou o dispositivo Wi-Fi Direct pode ser feito para ingressar em novos grupos, a negociação de proprietário de grupo pode ser ganhada por um dispositivo mal-intencionado que sempre especifica o valor de "intuito" máximo do grupo de proprietários do grupo de 15. (Mas a conexão falha se o dispositivo estiver configurado para ser sempre um proprietário do grupo).  | O Surface Hub aproveita o modo autônomo de Wi-Fi Direct "" modo autônomo ", que ignora a fase de negociação GO da configuração de conexão. E o Surface Hub sempre é o proprietário do grupo. |

**Desautenticação de Wi-Fi não intencional ou maliciosa:** A desautenticação de Wi-Fi é um ataque antigo no qual um invasor local pode acelerar os vazamentos de informações no processo de configuração de conexão, disparar novos Handshakes de quatro vias, direcionar o Wi-Fi Direct WPS-PBC para ataques ativos ou criar ataques de negação de serviço.

| Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| Pacotes de desautenticação podem ser enviados por um invasor não autenticado para fazer com que a estação seja reautenticada e, em seguida, para detectar o handshake resultante. Pode haver tentativas de ataques de criptografia ou de força bruta no handshake resultante. A mitigação desses ataques inclui políticas de tamanho e complexidade para chaves pré-compartilhadas, configuração do ponto de acesso (se aplicável) para detectar os níveis mal-intencionados de pacotes de desautenticação e usar o WPS para gerar automaticamente chaves fortes. No modo PBC, o usuário interage com um botão físico ou virtual para permitir uma associação arbitrária de dispositivos. Esse processo deve acontecer apenas na instalação, dentro de uma breve janela. Depois que o botão estiver automaticamente "enviado", o dispositivo aceitará todas as estações que associarem por meio de um valor PIN canônico (todos os zeros). A desautenticação pode forçar um processo de configuração repetida. |   O Surface Hub usa WPS no modo PIN ou PBC. Nenhuma configuração PSK é permitida. Esse método ajuda a impor a geração de teclas fortes. É melhor habilitar a segurança do WPS-PIN para Surface Hub. |
| Além de ataques de negação de serviço, pacotes de cancelamento de autenticação podem ser usados para disparar uma reconexão que reabrirá a janela da oportunidade para ataques ativos em relação ao WPS-PBC. |   Habilite a segurança do WPS-PIN na configuração do Surface Hub. |

**Divulgação de informações básicas sem fio:** As redes sem fio, 802,11 ou outra forma, são inerentemente ao risco de divulgação de informações. Embora essas informações sejam principalmente a conexão ou os metadados do dispositivo, esse problema continua sendo um risco conhecido para qualquer administrador de rede do 802,11. O Wi-Fi Direct com autenticação de dispositivo via WPS-PIN revela efetivamente as mesmas informações que uma rede 802.11 PSK ou empresarial.

| Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| Durante a transmissão, a configuração da conexão ou até mesmo a operação normal de conexões já criptografadas, as informações básicas sobre os dispositivos e os tamanhos de pacotes são sem fio transmitidas. Em um nível básico, um invasor local que está dentro do intervalo sem fio pode examinar os elementos de informações relevantes do 802,11 para determinar os nomes de dispositivos sem fio, os endereços MAC do equipamento de comunicação e possivelmente outros detalhes, como a versão da pilha sem fio, tamanhos de pacote ou opções de proprietário de grupo ou ponto de acesso configurado.  | A rede Wi-Fi Direct que o Surface Hub usa não pode ser protegida contra vazamentos de metadados, exatamente como para redes sem fio de 802,11 Enterprise ou PSK. A segurança física e a remoção de possíveis ameaças da proximidade sem fio pode ajudar a reduzir possíveis vazamentos de informações. |

**Ataques de spoof ou de falsificação sem fio mal:**  A falsificação do nome sem fio é uma exploração simples e bem conhecida que um invasor local pode usar para atrair a conexão de usuários insuspeitos ou invasores.

| Vulnerabilidade do Wi-Fi Direct | Mitigação do Surface Hub |
| --- | --- |
| Ao falsificar ou clonar o nome sem fio ou "SSID" da rede de destino, um invasor pode enganar o usuário para se conectar a uma rede falsa e maliciosa. Ao dar suporte a Miracast não autenticados e de junção automática, um invasor pode capturar os materiais de exibição pretendidos ou iniciar ataques de rede no dispositivo de conexão. | Embora não haja nenhuma proteção específica contra ingressar em um Surface Hub falso, essa vulnerabilidade é reduzida parcialmente de duas maneiras. Primeiro, qualquer ataque em potencial deve estar fisicamente dentro do alcance do Wi-Fi. Em segundo lugar, esse ataque só é possível durante a primeira conexão. As conexões subsequentes usam um grupo Wi-Fi Direct persistente, e o Windows lembrará e priorizará essa conexão anterior durante o uso futuro do Hub. (Observação: a falsificação do endereço MAC, do canal de Wi-Fi e do SSID simultaneamente não foi considerada para este relatório e pode resultar em um comportamento de Wi-Fi inconsistente.) Em geral, esse ponto fraco é um problema fundamental para qualquer rede sem fio 802,11 que não possua protocolos WPA2 corporativos, como EAP-TLS ou EAP-PWD, para o qual o Wi-Fi Direct não seja compatível. |

## Diretrizes de proteção do Surface Hub

O Surface Hub foi projetado para facilitar a colaboração e permitir que os usuários iniciem ou participem de reuniões com rapidez e eficiência. As configurações padrão de Wi-Fi Direct para Surface Hub são otimizadas para esse cenário.

Para segurança de interface sem fio adicional, os usuários do Surface Hub devem habilitar a configuração de segurança do WPS-PIN. Essa configuração desabilita o modo WPS-PBC e oferece autenticação de cliente. Ele fornece o nível de proteção mais forte impedindo a conexão não autorizada com o Surface Hub.

Se ainda tiver dúvidas sobre autenticação e autorização para o Surface Hub, recomendamos que você conecte o dispositivo a uma rede separada. Você pode usar Wi-Fi (como uma rede Wi-Fi "convidado") ou uma rede Ethernet separada, de preferência, uma rede física totalmente diferente. Mas uma VLAN também pode oferecer segurança adicional. É claro que essa abordagem pode impedir conexões com recursos de rede internos ou serviços e pode exigir uma configuração de rede adicional para recuperar o acesso.

Também recomendado:
- [Instalar atualizações regulares do sistema](manage-windows-updates-for-surface-hub.md) 
- Atualizar as configurações Miracast para desabilitar o modo de apresentação automática

## Saiba mais

- [Especificações do Wi-Fi Direct](http://www.wi-fi.org/discover-wi-fi/wi-fi-direct)
- [Especificação do protocolo WPS (Wireless Protected Setup)](http://www.wi-fi.org/discover-wi-fi/wi-fi-protected-setup)



