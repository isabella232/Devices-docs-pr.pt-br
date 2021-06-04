---
title: Conectar outros dispositivos ao Surface Hub 2S
description: Esta página explica como conectar dispositivos externos ao Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/24/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1c4f9b4a74b50edb5587185f28a18163a02d62f9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830538"
---
# Conectar outros dispositivos ao Surface Hub 2S
Surface Hub 2S permite que você conecte dispositivos externos, espelhe a exibição no Surface Hub 2S para outro dispositivo e conecte vários periféricos de terceiros, incluindo câmeras de vídeo, telefones de conferência e dispositivos de sistema de sala.

Você pode exibir o conteúdo de seus dispositivos para o Surface Hub 2S. Se o dispositivo de origem for baseado no Windows, esse dispositivo também pode fornecer TouchBack e InkBack, que recebe vídeo e áudio do dispositivo conectado e os apresenta no Surface Hub 2S. Se o Surface Hub 2S encontrar um sinal de HDCP (proteção de conteúdo digital) de alta largura de banda, como um aparelho de DVD Blu-Ray, a fonte será exibida como uma imagem preta.

> [!NOTE]
> Surface Hub 2S usa a entrada de vídeo selecionada até que uma nova conexão seja feita, a conexão existente será interrompida ou o aplicativo conectar será fechado.

##  <a name="recommended-wired-configurations"></a>Configurações com fio recomendadas 

Em geral, é recomendável usar conexões de cabo nativas sempre que possível, como USB-C para USB-C ou HDMI para HDMI. Outras combinações, como MiniDP para HDMI ou MiniDP para USB-C, também funcionarão. Algumas configurações adicionais podem ser necessárias para otimizar a experiência de vídeo, conforme descrito nesta página.

| **Conexão** | **Funcionalidade** | **Descrição**|
| --- | --- | ---|
| HDMI + USB-C | HDMI para áudio e vídeo<br><br>USB-C para TouchBack e InkBack | USB-C suporta TouchBack e InkBack com a conexão HDMI A/V.<br><br>Use USB-C para USB-A para se conectar a computadores herdados.<br><br>**Observação:** Para obter melhores resultados, conecte o HDMI antes de conectar um cabo USB-C. Se o computador que você está usando para HDMI não for compatível com o TouchBack e o InkBack, você não precisará de um cabo USB-C. |
| USB-C <br> (por meio do módulo de computação) | Entrada de vídeo <br>Entrada de áudio | Cabo único necessário para A/V<br><br>TouchBack e InkBack têm suporte<br><br>HDCP habilitado |
| HDMI (na porta) | Vídeo, áudio no Surface Hub 2S | Cabo único necessário para A/V<br><br>TouchBack e InkBack não têm suporte<br><br>HDCP habilitado |
| Saída do MiniDP 1,2 | Saída de vídeo, como espelhamento para um projetor maior. | Cabo único necessário para A/V |

Quando você conecta um computador convidado ao Surface Hub 2S pela porta USB-C, vários dispositivos USB são descobertos e configurados. Esses dispositivos periféricos são criados para o TouchBack e o InkBack. Conforme mostrado na tabela a seguir, os dispositivos periféricos podem ser exibidos no Gerenciador de dispositivos, que mostrará nomes duplicados para alguns dispositivos, conforme mostrado na tabela a seguir.

 
|**Periférico**| **Listagem no Gerenciador de dispositivos** |
| ---------------------------- |------------- | ------------------------------|
| Dispositivos de interface humana | Dispositivo de controle do consumidor compatível com HID<br>Caneta compatível com HID<br>Caneta compatível com HID (item duplicado)<br>Caneta compatível com HID (item duplicado)<br>Tela touch compatível com HID<br>Dispositivo de entrada USB<br>Dispositivo de entrada USB (item duplicado) |
| Teclados | Teclado PS/2 padrão |
| Mouses e outros dispositivos apontadores | Mouse compatível com HID |
| Controladores USB | Hub USB genérico<br>Dispositivo composto USB |

##  <a name="connecting-video-in-to-surface-hub-2s"></a>Conectando o vídeo ao Surface Hub 2S

Você pode inserir vídeo em Surface Hub 2S usando USB-C ou HDMI, conforme indicado na tabela a seguir.  

###  <a name="surface-hub-2s-video-in-settings"></a>Configurações de vídeo do Surface Hub 2S

| **Tipo de sinal** | **Resolução** | **Taxa de quadros** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640 x 480      | 60             | X        | X         |
| Computador              | 720 x 480      | 60             | X        | X         |
| Computador              | 1024 x 768     | 60             | X        | X         |
| Computador              | 1920 x 1080    | 60             | X        | X         |
| Computador              | 3840x2560      | 30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 30             | X        | X         |

> [!NOTE]
> A resolução de 4K UHD (3840 × 2560) só tem suporte quando se conecta a portas no módulo COMPUTE. Não há suporte para as portas USB "Guest" localizadas nos lados esquerdo, superior e direito do dispositivo.

> [!NOTE]
> O vídeo de um computador externo conectado pode parecer menor quando exibido no Surface Hub 2S.

##  <a name="mirroring-surface-hub-2s-display-on-another-device"></a>Vídeo do Surface Hub do espelhamento 2S em outro dispositivo

Você pode produzir vídeo para outra exibição usando o MiniDP, conforme indicado na tabela a seguir.

###  <a name="surface-hub-2s-video-out-settings"></a>Configurações de saída de vídeo do Surface Hub 2S

| **Tipo de sinal** | **Resolução** | **Taxa de quadros** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| PC              | 640 x 480      | 60             | X          |
| Computador              | 720 x 480      | 60             | X          |
| Computador              | 1024 x 768     | 60             | X          |
| Computador              | 1920 x 1080    | 60             | X          |
| Computador              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2S inclui uma porta de saída de vídeo MiniDP para projetar conteúdo visual do Surface Hub 2S para outra exibição. Se você pretende usar o Surface Hub 2S para projetar em outro vídeo, observe as seguintes recomendações:

- **Teclado obrigatório.** Antes de começar, você precisará conectar um teclado externo compatível com Bluetooth ou Bluetooth a Surface Hub 2S. Observe que, ao contrário do Surface Hub original, um teclado para o Surface Hub 2S é vendido separadamente e não está incluído no pacote de remessa.<br><br>
- **Definir modo duplicado.** O Surface Hub 2S dá suporte a vídeo-out apenas em modo duplicado. No entanto, você ainda precisará configurar manualmente o modo de exibição quando se conectar pela primeira vez:
    1. Digite a **tecla do logotipo do Windows**  +  **P**, que abre o painel de projeto no lado direito do Surface Hub 2S e selecione modo **duplicado** .
    2. Quando tiver terminado a sessão do Surface Hub 2S, selecione **encerrar sessão**. Isso garante que a configuração duplicada seja salva para a próxima sessão.<br><br>
- **Plano para taxas de proporção diferentes.** Como outros dispositivos de superfície, o Surface Hub 2S usa uma taxa de proporção de exibição de 3:2 (a relação entre a largura e a altura da exibição). A projeção do Surface Hub 2S em monitores com taxas de proporção diferentes tem suporte. No entanto, observe que, como o Surface Hub 2S duplica a exibição, a saída MiniDP também será exibida em uma taxa de proporção de 3:2, que pode resultar em Letterboxing ou curtaining dependendo da taxa de proporção da exibição de recebimento. 

> [!NOTE]
> Se o segundo monitor usar uma taxa de proporção de 16:9 (a razão predominante para a maioria dos monitores de TV), as barras pretas poderão ser exibidas nos lados esquerdo e direito da tela espelhada. Se isso ocorrer, talvez você queira informar aos usuários que não há necessidade de ajustar a segunda tela.

##  <a name="selecting-cables"></a>Selecionar cabos

Observe as seguintes recomendações:

- **USB.** Cabos USB 3,1 Gen 2.
- **MiniDP.** Cabos DisplayPort certificados para até 3 metros de comprimento.
- **HDMI.** Se for necessário um cabo longo, o HDMI é recomendado devido à ampla disponibilidade de cabos de longa distância e de longa distância com a capacidade de instalar repetidores, se necessário.

> [!NOTE]
> A maioria das fontes DisplayPort alternará automaticamente para a sinalização HDMI se o HDMI for detectado.

##  <a name="wirelessly-connect-to-surface-hub-2s"></a>Conexão sem fio com o Surface Hub 2S

O Windows 10 nativamente suporta Miracast, que permite que você se conecte sem fio ao Surface Hub 2S.<br><br>

###  <a name="to-connect-using-miracast"></a>Para se conectar usando Miracast:

1. Em seu dispositivo Windows 10, insira a **tecla de logotipo do Windows**  +  **K**. 
2. Na janela conectar, procure o nome do seu Surface Hub 2S na lista de dispositivos próximos. Você pode encontrar o nome do seu Surface Hub 2S no canto inferior esquerdo da tela.
3. Insira um PIN se o administrador do sistema tiver habilitado a configuração de PIN para conexões Miracast. Isso exige que você insira um número PIN quando conectar-se ao Surface Hub 2S pela primeira vez.

> [!NOTE]
>Se você não vir o nome do dispositivo Surface Hub 2S como esperado, é possível que a sessão anterior tenha fechado prematuramente. Em caso afirmativo, entre no Surface Hub 2S diretamente para encerrar a sessão anterior e, em seguida, conecte-se do seu dispositivo externo.

##  <a name="connecting-peripherals-to-surface-hub-2s"></a>Conectando periféricos ao Surface Hub 2S

###  <a name="bluetooth-accessories"></a>Acessórios Bluetooth

Você pode conectar os seguintes acessórios ao Surface Hub-2S usando Bluetooth:

- Mouses
- Teclados
- Fones de ouvido
- Alto-falantes
- Surface Hub 2 canetas

> [!NOTE]
> Depois de conectar um fone de ouvido Bluetooth ou viva-voz, você precisará alterar as configurações padrão do microfone e do alto-falante. Para obter mais informações, consulte [**Gerenciamento local para configurações do Surface Hub**](https://docs.microsoft.com/surface-hub/local-management-surface-hub-settings).
