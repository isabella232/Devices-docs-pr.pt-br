---
title: Conectar outros dispositivos e exibir seu conteúdo com o Surface Hub
description: Você pode conectar outro dispositivo ao Surface Hub para exibir seu conteúdo.
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: ''
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 6985d6a87e14df70d244457dfeddabd673bb2bdc
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911386"
---
# <a name="connect-other-devices-and-display-with-surface-hub"></a>Conectar outros dispositivos e exibir seu conteúdo com o Surface Hub


Você pode conectar outros dispositivos ao Microsoft Surface Hub para exibir seu conteúdo. Este tópico descreve o Modo Convidado, o Modo de Computador de Substituição e a funcionalidade Saída de Vídeo disponíveis por meio de conexões com fio e também lista acessórios que você pode conectar ao Surface Hub usando [Bluetooth](#bluetooth-accessories).

>[!NOTE]
>Surface Hub usará a entrada de vídeo selecionada até que uma nova conexão seja feita, a conexão existente seja interrompida ou o aplicativo Conexão está fechado.

## <a name="which-method-should-i-choose"></a>Qual método devo escolher?

Ao conectar dispositivos externos e telas a um Surface Hub, existem várias opções disponíveis. O método usado dependerá de suas necessidades e cenário. 

| Quando você deseja: | Use esse método: |
| --- | --- |
| Espelhar a tela do Surface Hub em outro dispositivo. | [Saída de Vídeo](#video-out) |
| Apresentar a tela de outro dispositivo na tela do Surface Hub e interagir com o conteúdo do dispositivo e a experiência interna do Surface Hub. | [Modo Convidado](#guest-mode) |
| Ligue o Surface Hub de um computador Windows 10 externo, desligando o computador incorporado do Surface Hub. Câmeras, microfones, alto-falantes e outros periféricos são enviados para o computador externo, além de caneta e touch. | [Modo de Computador de Substituição](#replacement-pc-mode) |


## <a name="guest-mode"></a>Modo Convidado


O Modo Convidado usa uma conexão com fio, para que as pessoas possam exibir o conteúdo de seus dispositivos no Surface Hub. Se o dispositivo de origem for baseado no Windows, ele também poderá fornecer Touchback e Inkback. O computador interno do Surface Hub usa o vídeo e o áudio do dispositivo conectado e apresenta-os no Surface Hub. Se Surface Hub encontrar um sinal High-Bandwidth HDCP (Proteção de Conteúdo Digital), a origem será exibida como uma imagem preta. Para exibir seu conteúdo sem violar os requisitos de HDCP, use o teclado numérico no lado direito do Surface Hub para escolher diretamente a fonte externa.

>[!NOTE]
>Quando uma fonte de HDCP estiver conectada, use o teclado numérico para alterar as entradas da fonte.

### <a name="ports"></a>Portas

Use estas portas no Surface Hub para o Modo Convidado.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Interface</th>
<th>Tipo</th>
<th>Descrição</th>
<th>Funcionalidades</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Porta de visor 1.1a</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>Entrada de convidado #1</p></td>
<td><ul>
<li><p>Oferece suporte simultâneo ao visor de entrada de convidado com entrada de convidado #2 e entrada de convidado #3 (um: resolução total, dois: miniatura).</p></li>
<li><p>Compatível com HDCP no modo bypass</p></li>
<li><p>Habilitado para Touchback</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>HDMI 1.4</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>Entrada de convidado #2</p></td>
<td><ul>
<li><p>Oferece suporte simultâneo ao visor de entrada de convidado com entrada de convidado #1 e entrada de convidado #3 (um: resolução total, dois: miniatura).</p></li>
<li><p>Compatível com HDCP no modo bypass</p></li>
<li><p>Habilitado para Touchback</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VGA</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>Entrada de convidado #3</p></td>
<td><ul>
<li><p>Oferece suporte simultâneo ao visor de entrada de convidado com entrada de convidado #1 e entrada de convidado #2 (um: resolução total, dois: miniatura).</p></li>
<li><p>Compatível com HDCP no modo bypass</p></li>
<li><p>Habilitado para Touchback</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Conector de 3,5 mm</p></td>
<td><p>Entrada de áudio</p></td>
<td><p>Entrada de áudio analógica</p></td>
<td><ul>
<li><p>Ingestão no computador do Surface Hub, geralmente com a entrada de vídeo VGA.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 2.0, tipo B</p></td>
<td><p>Saída USB</p></td>
<td><p>Touchback</p></td>
<td><ul>
<li><p>Devolve o acesso ao mouse, toque, teclado e caneta de dispositivos de entrada HID ao computador convidado.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="port-locations"></a>Locais de porta

Estas são as conexões de porta usadas para o Modo Convidado nos Surface Hubs de 55 e 84 polegadas.

![imagem mostrando portas de convidado em Surface Hub de 55 polegadas.](images/sh-55-guest-ports.png)

Conexões de porta com fio em Surface Hub de 55 polegadas

![imagem mostrando portas de convidado em Surface Hub de 84 polegadas.](images/sh-84-guest-ports.png)

Conexões de porta com fio em Surface Hub de 84 polegadas

### <a name="port-enumeration"></a>Enumeração de porta

Quando um Surface Hub é conectado a um computador convidado com a porta USB conectada com fio, vários dispositivos USB são descobertos e configurados. Esses dispositivos periféricos são criados para Touchback e Inkback. Os dispositivos periféricos podem ser vistos no Gerenciador de Dispositivos. O Gerenciador de Dispositivos mostrará nomes duplicados para alguns dispositivos.

**Dispositivos de interface humana**

-   Dispositivo de controle do consumidor compatível com HID

-   Caneta compatível com HID

-   Caneta compatível com HID (item duplicado)

-   Caneta compatível com HID (item duplicado)

-   Tela touch compatível com HID

-   Dispositivo de entrada USB

-   Dispositivo de entrada USB (item duplicado)

**Teclados**

-   Teclado PS/2 padrão

**Mouses e outros dispositivos apontadores**

-   Mouse compatível com HID

**Controladores de barramento serial universal**

-   Hub USB genérico

-   Dispositivo composto USB

### <a name="guest-mode-connectivity"></a>Conectividade de Modo Convidado

Sua opção de cabo de vídeo será determinada pelo que está disponível na sua entrada de origem. O Surface Hub tem três opções de entrada de vídeo: DisplayPort, HDMI e VGA. Veja o gráfico a seguir para resoluções disponíveis.

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de sinal</th>
<th>Resolução</th>
<th>Taxa de quadros</th>
<th>HDMI - RGB</th>
<th>DisplayPort</th>
<th>VGA</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Computador</p></td>
<td><p>640 x 480</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Computador</p></td>
<td><p>720 x 480</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Computador</p></td>
<td><p>1024 x 768</p></td>
<td><p>60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>HDTV</p></td>
<td><p>720p</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>HDTV</p></td>
<td><p>1080p</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

 

O áudio de origem é fornecido por cabos DisplayPort e HDMI. Se você tiver de usar VGA, o Surface Hub tem uma porta de entrada de áudio que usa um plugue de 3,5 mm. O Surface Hub também usa um cabo USB que fornece Touchback e Inkback do Surface Hub para dispositivos compatíveis com o Windows 10. O cabo USB pode ser usado com qualquer entrada de vídeo que já esteja conectada com um cabo.

Alguém usando o Modo Convidado para se conectar a um computador usaria uma destas opções:

**DisplayPort** -- Cabos DisplayPort e USB 2.0

**HDMI** -- Cabos HDMI e USB 2.0

**VGA** -- Cabo VGA, cabo de áudio de 3,5 mm e cabo USB 2.0

Se o computador que estiver usando para o Modo Convidado não for compatível com Touchback e Inkback, você não precisará do cabo USB.

## <a name="replacement-pc-mode"></a>Modo de Computador de Substituição


No Modo de Computador de Substituição, o computador incorporado do Surface Hub é desativado, e um PC externo é conectado ao Surface Hub. Conexões com portas do computador de substituição dão acesso aos principais periféricos no Surface Hub, incluindo recursos de toque, tela e caneta. Isso significa que o Surface Hub não terá a vantagem da experiência da Equipe do Windows, mas você terá a flexibilidade oferecida por fornecer e gerenciar seu próprio computador Windows.

### <a name="software-requirements"></a>Requisitos de software

Você pode executar o Surface Hub no Modo de computador de Substituição com versões de 64 bits do Windows 10 Home, Windows 10 Pro e Windows 10 Enterprise. Você pode baixar o [pacote de driver do computador de substituição do Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) do Centro de Download da Microsoft. Recomendamos que você instale esses drivers em qualquer computador que planeje usar como substituto.

### <a name="hardware-requirements"></a>Requisitos de hardware

O Surface Hub é compatível com vários tipos de hardware. Escolha a confirmação de processador e memória para o computador de substituição para que ele aceite os programas que você usará. O hardware do computador de substituição precisa dar suporte a versões de 64 bits do Windows 10.

### <a name="graphics-adapter"></a>Adaptador gráfico

No Modo de Computador de substituição, o Surface Hub dá suporte a qualquer adaptador gráfico que possa produzir um sinal DisplayPort. Você melhorará a sua experiência com um adaptador gráfico que corresponda à resolução e à taxa de atualização do Surface Hub. Por exemplo, a melhor experiência de computador de substituição recomendada no Surface Hub é com um sinal de vídeo de 120Hz.

**Surface Hubs de 55 polegadas** - Para uma melhor experiência, use uma placa gráfica com resolução de 1080p a 120 Hz.

**Surface Hubs de 84 polegadas** - Para uma melhor experiência, use uma placa gráfica com saída para quatro fluxos do DisplayPort 1.2 para produzir 2160p a 120 Hz (3840 x 2160 a uma atualização vertical de 120 Hz). Verificamos que isso funcione com NVIDIA Quadro K2200, NVIDIA Quadro K4200, NVIDIA Quadro M6000, AMD FirePro W5100, AMD FirePro W7100 e AMD FirePro W9100. Essas não são as únicas placas gráficas, há outras de outros fornecedores disponíveis. 

Consulte os drivers mais recentes diretamente com fornecedores de placas gráficas.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fornecedor de placas gráficas</th>
<th>Página de download de driver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NVIDIA</p></td>
<td><p><a href="http://nvidia.com/Download/index.aspx" data-raw-source="[http://nvidia.com/Download/index.aspx](http://nvidia.com/Download/index.aspx)">http://nvidia.com/Download/index.aspx</a></p></td>
</tr>
<tr class="even">
<td><p>AMD</p></td>
<td><p><a href="http://support.amd.com/en-us/download" data-raw-source="[http://support.amd.com/en-us/download](http://support.amd.com/en-us/download)">http://support.amd.com/en-us/download</a></p></td>
</tr>
<tr class="odd">
<td><p>Intel</p></td>
<td><p><a href="https://downloadcenter.intel.com/" data-raw-source="[https://downloadcenter.intel.com/](https://downloadcenter.intel.com/)">https://downloadcenter.intel.com/</a></p></td>
</tr>
</tbody>
</table>

 

### <a name="ports"></a>Portas

Portas de computador de substituição em Surface Hub de 55 polegadas

![imagem mostrando portas de computador de substituição no Surface Hub de 55 polegadas.](images/sh-55-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Tipo</th>
<th>Interface</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vídeo do computador</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>DP 1.2</p></td>
<td><ul>
<li><p>Exibição em tela inteira de 1080p a 120 Hz, além de áudio</p></li>
<li><p>Compatível com HDCP</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Periféricos internos</p></td>
<td><p>Saída USB</p></td>
<td><p>USB 2.0, tipo B</p></td>
<td><ul>
<li><p>Toque</p></li>
<li><p>Caneta</p></li>
<li><p>Alto-falantes</p></li>
<li><p>Microfone</p></li>
<li><p>Câmeras</p></li>
<li><p>Sensor NFC</p></li>
<li><p>Sensor de luz ambiente</p></li>
<li><p>Sensor infravermelho passivo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Hub USB</p></td>
<td><p>Saída USB</p></td>
<td><p>USB 2.0, tipo B</p></td>
<td><ul>
<li><p>Portas USB subjacentes</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

Portas de computador de substituição em Surface Hub de 84 polegadas

![imagem mostrando portas de computador de substituição no Surface Hub de 84 polegadas.](images/sh-84-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Tipo</th>
<th>Interface</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vídeo do computador</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>DP 1.2 (2x)</p></td>
<td><ul>
<li><p>Exibição em tela inteira de 2160p a 120 Hz, além de áudio</p></li>
<li><p>Compatível com HDCP</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Periféricos internos</p></td>
<td><p>Saída USB</p></td>
<td><p>USB 2.0, tipo B</p></td>
<td><ul>
<li><p>Toque</p></li>
<li><p>Caneta</p></li>
<li><p>Alto-falantes</p></li>
<li><p>Microfone</p></li>
<li><p>Câmeras</p></li>
<li><p>Sensor NFC</p></li>
<li><p>Sensor de luz ambiente</p></li>
<li><p>Sensor infravermelho passivo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Hub USB</p></td>
<td><p>Saída USB</p></td>
<td><p>USB 2.0, tipo B</p></td>
<td><ul>
<li><p>Portas USB subjacentes</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="replacement-pc-setup-instructions"></a>Instruções de configuração de computador de substituição

**Para usar o Modo de Computador de Substituição**

1.  Baixe e instale o [pacote de driver do computador de substituição do Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) no computador de substituição.

    >[!NOTE]
    >Observação: Recomendamos que você defina o computador de substituição nos modos de suspensão ou hibernação para que o Surface Hub desligue o vídeo quando não estiver sendo usado.

2.  Desligue o Surface Hub usando o botão liga/desliga ao lado do cabo de alimentação.

3.  Conecte os cabos das portas do computador de substituição do Surface Hub ao computador de substituição. Essas portas normalmente são cobertas por uma capa de plástico removível.

    Surface Hub de 55 polegadas – conecte um cabo DisplayPort e dois cabos USB.

    Surface Hub de 84 polegadas — conecte dois cabos DisplayPort e dois cabos USB.

4.  Alterne a opção de Modo para **Replacement PC**. A opção de Modo fica ao lado das portas do computador de substituição.

5.  Ligue o Surface Hub usando o botão liga/desliga ao lado do cabo de alimentação.

6.  Pressione o botão de energia no lado direito do Surface Hub.

Você pode definir o Surface Hub para usar o computador interno.

**Para voltar ao computador interno**

1.  Desligue o Surface Hub usando o botão liga/desliga ao lado do cabo de alimentação.

2.  Alterne a opção de Modo para Internal PC. A opção de Modo fica ao lado das portas do computador de substituição.

3.  Ligue o Surface Hub usando o botão liga/desliga ao lado do cabo de alimentação.

 
## <a name="video-out"></a>Saída de Vídeo
 
O Surface Hub inclui uma porta de Saída de Vídeo para espelhamento de conteúdo visual do Surface Hub para outra tela.

### <a name="ports"></a>Portas

Porta para Saída de Vídeo no Surface Hub de 55 polegadas

![Ilustração da porta de saída de vídeo.](images/video-out-55.png)

Porta para Saída de Vídeo no Surface Hub de 84 polegadas

![Ilustração da porta de saída de vídeo.](images/video-out-84.png)

<table>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Tipo</th>
<th>Interface</th>
<th>Funcionalidades</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Espelhamento da Saída de Vídeo</p></td>
<td><p>Saída de Vídeo</p></td>
<td><p>Saída de Vídeo</p></td>
<td><ul>
<li><p>Suporta conexão a um monitor padrão DisplayPort (somente suporta um x4 Link exibindo resolução 1080p60 em 24bpp)</p></li>
<li><p>Suporta o uso com monitores HDMI (suporta 1080p60) usando um adaptador DisplayPort para HDMI</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cables"></a>Cabos

Os dispositivos do Surface Hub 55" e 84" foram testados com cabos DisplayPort e HDMI certificados.  Embora os fornecedores vendam cabos mais longos que possam funcionar com o Surface Hub, somente os cabos que foram certificados por laboratórios de testes certamente funcionarão com o Hub. Por exemplo, os cabos DisplayPort são certificados apenas até três metros, mas muitos fornecedores vendem cabos com três vezes esse tamanho. Se um cabo longo for necessário, sugerimos usar HDMI.  HDMI tem muitas soluções econômicas para cabos de longa distância, inclusive o uso de repetidores. Quase todas as fontes DisplayPort alternarão automaticamente para o sinal HDMI se for detectado um coletor HDMI.


## <a name="bluetooth-accessories"></a>Acessórios Bluetooth

Você pode conectar os seguintes acessórios ao Surface Hub usando Bluetooth:

- Mouses
- Teclados
- Fones de ouvido
- Alto-falantes

>[!NOTE]
>Depois de conectar um fone de ouvido Bluetooth ou viva-voz, você precisará alterar as [configurações padrão do microfone e do alto-falante](local-management-surface-hub-settings.md).
