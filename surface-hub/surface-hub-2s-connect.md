---
title: Conectar dispositivos ao Surface Hub 2S
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
ms.openlocfilehash: e3d1aa79ad056e790d5dc6a46f299cbaa9b5f9b0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497471"
---
# <a name="connect-devices-to-surface-hub-2s"></a>Conectar dispositivos ao Surface Hub 2S

O Surface Hub 2S permite conectar dispositivos externos, espelhar a exibição no Surface Hub 2S a outro dispositivo e conectar vários periféricos de terceiros, incluindo câmeras de conferência de vídeo, telefones de conferência e dispositivos de sistema de salas.

Você pode exibir conteúdo de seus dispositivos para Surface Hub 2S. Se o dispositivo de origem for baseado em Windows, esse dispositivo também poderá fornecer TouchBack e InkBack, que usa vídeo e áudio do dispositivo conectado e os apresenta no Surface Hub 2S. Se Surface Hub 2S encontrar um sinal High-Bandwidth de PROTEÇÃO de Conteúdo Digital (HDCP), como um DVD Blu-ray, a origem será exibida como uma imagem preta.

> [!NOTE]
> Surface Hub 2S usa a entrada de vídeo selecionada até que uma nova conexão seja estabelecida, a conexão existente seja interrompida ou o aplicativo Conexão seja fechado.

## <a name="recommended-wired-configurations"></a>Configurações com fio recomendadas 

Em geral, é recomendável usar conexões de cabo nativas sempre que possível, como USB-C para USB-C ou HDMI para HDMI. Outras combinações, como MiniDP para HDMI ou MiniDP para USB-C, também funcionarão. Algumas configurações adicionais podem ser necessárias para otimizar a experiência de saída de vídeo, conforme descrito nesta página.

| **Conexão** | **Funcionalidade** | **Descrição**|
| --- | --- | ---|
| HDMI + USB-C | HDMI-in para áudio e vídeo<br><br>USB-C para TouchBack e InkBack | O USB-C dá suporte a TouchBack e InkBack com a conexão HDMI A/V.<br><br>Use USB-C para USB-A para se conectar a computadores herdados.<br><br>**NOTA:** Para obter melhores resultados, conecte o HDMI antes de conectar um cabo USB-C. Se o computador que você está usando para HDMI não for compatível com TouchBack e InkBack, você não precisará de um cabo USB-C. |
| USB-C <br> (por meio do módulo de computação) | Entrada de vídeo <br>Entrada de áudio | Cabo único necessário para A/V<br><br>Há suporte para TouchBack e InkBack<br><br>HDCP habilitado |
| HDMI (na porta) | Vídeo, Áudio no Surface Hub 2S | Cabo único necessário para A/V<br><br>Não há suporte para TouchBack e InkBack<br><br>HDCP habilitado |
| Saída do MiniDP 1.2 | Vídeo-out, como espelhamento para um projetor maior. | Cabo único necessário para A/V |

Quando você conecta um computador convidado ao Surface Hub 2S por meio da porta USB-C, vários dispositivos USB são descobertos e configurados. Esses dispositivos periféricos são criados para TouchBack e InkBack. Conforme mostrado na tabela a seguir, os dispositivos periféricos podem ser exibidos no Gerenciador de Dispositivos, que mostrará nomes duplicados para alguns dispositivos, conforme mostrado na tabela a seguir.

 
|**Periférico**| **Listagem no Gerenciador de Dispositivos** |
| ---------------------------- |------------- | ------------------------------|
| Dispositivos de interface humana | Dispositivo de controle do consumidor compatível com HID<br>Caneta compatível com HID<br>Caneta compatível com HID (item duplicado)<br>Caneta compatível com HID (item duplicado)<br>Tela touch compatível com HID<br>Dispositivo de entrada USB<br>Dispositivo de entrada USB (item duplicado) |
| Teclados | Teclado PS/2 padrão |
| Mouses e outros dispositivos apontadores | Mouse compatível com HID |
| Controladores USB | Hub USB genérico<br>Dispositivo composto USB |

## <a name="connecting-video-in-to-surface-hub-2s"></a>Conectando vídeo ao Surface Hub 2S

Você pode inserir vídeo para Surface Hub 2S usando USB-C ou HDMI, conforme indicado na tabela a seguir.  

### <a name="surface-hub-2s-video-in-settings"></a>Surface Hub configurações de vídeo 2S

| **Tipo de sinal** | **Resolução** | **Taxa de quadros** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| Computador              | 640 x 480      | 60             | X        | X         |
| Computador              | 720 x 480      | 60             | X        | X         |
| Computador              | 1024 x 768     | 60             | X        | X         |
| Computador              | 1920 x 1080    | 60             | X        | X         |
| Computador              | 3840x2560      | 30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 30             | X        | X         |

> [!NOTE]
> A resolução UHD de 4K (3840×2560) só tem suporte ao se conectar a portas no módulo de computação. Não há suporte para ele nas portas USB "convidado" localizadas nos lados esquerdo, superior e direito do dispositivo.

> [!NOTE]
> O vídeo de um computador externo conectado pode parecer menor quando exibido no Surface Hub 2S.

## <a name="mirroring-surface-hub-2s-display-on-another-device"></a>Exibição Surface Hub 2S em outro dispositivo

Você pode gerar vídeo para outra exibição usando MiniDP, conforme indicado na tabela a seguir.

### <a name="surface-hub-2s-video-out-settings"></a>Surface Hub configurações de saída de vídeo 2S

| **Tipo de sinal** | **Resolução** | **Taxa de quadros** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| Computador              | 640 x 480      | 60             | X          |
| Computador              | 720 x 480      | 60             | X          |
| Computador              | 1024 x 768     | 60             | X          |
| Computador              | 1920 x 1080    | 60             | X          |
| Computador              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2S inclui uma porta de saída de vídeo MiniDP para projetar conteúdo visual de Surface Hub 2S para outra exibição. Se você planeja usar o Surface Hub 2S para projetar em outra exibição, observe as seguintes recomendações:

- **Teclado necessário.** Antes de começar, você precisará conectar um teclado externo com ou Bluetooth com fio ao Surface Hub 2S. Observe que, ao contrário do Surface Hub original, um teclado para Surface Hub 2S é vendido separadamente e não está incluído no pacote de envio.<br><br>
- **Defina o modo duplicado.** Surface Hub 2S dá suporte à saída de vídeo somente no modo duplicado. No entanto, você ainda precisará configurar manualmente o modo de exibição quando se conectar pela primeira vez:
    1. Insira o **Windows keyP** +  do logotipo, que abre o painel Project à direita do Surface Hub 2S e, em seguida, selecione **o modo** Duplicado.****
    2. Quando terminar a sessão do Surface Hub 2S, selecione **Encerrar Sessão**. Isso garante que a configuração duplicada seja salva para a próxima sessão.<br><br>
- **Planeje taxas de proporção diferentes.** Como outros dispositivos Surface, o Surface Hub 2S usa uma taxa de proporção de exibição de 3:2 (a relação entre a largura e a altura da tela). Há suporte para Surface Hub 2S em exibições com taxas de proporção diferentes. Observe, no entanto, que como Surface Hub 2S duplica a exibição, a saída do MiniDP também será exibida apenas em uma taxa de proporção de 3:2, o que pode resultar em caixas de texto ou cortinas, dependendo da taxa de proporção da exibição de recebimento. 

> [!NOTE]
> se o segundo monitor usar uma taxa de proporção de 16:9 (a taxa predominante para a maioria dos monitores de TV), as barras pretas poderão aparecer nos lados esquerdo e direito da tela espelhada. Se isso ocorrer, talvez você queira informar aos usuários que não há necessidade de ajustar a segunda exibição.

## <a name="selecting-cables"></a>Selecionando cabos

Observe as seguintes recomendações:

- **USB.** Cabos USB 3.1 Gen 2.
- **MiniDP.** Cabos DisplayPort certificados para até 3 metros de comprimento.
- **HDMI.** Se for necessário um cabo longo, o HDMI será recomendado devido à ampla disponibilidade de cabos de longa distância e econômicos com a capacidade de instalar repetidores, se necessário.

> [!NOTE]
> A maioria das fontes DisplayPort alternará automaticamente para a sinalização HDMI se o HDMI for detectado.

## <a name="wirelessly-connect-to-surface-hub-2s"></a>Conectar-se sem fio ao Surface Hub 2S

Windows 10/11 dá suporte nativo Miracast, que permite que você se conecte sem fio ao Surface Hub 2S.<br><br>

### <a name="to-connect-using-miracast"></a>Para se conectar usando Miracast:

1. No dispositivo Windows 10/11, insira **Windows keyK do** +  **logotipo**. 
2. Na janela Conexão, procure o nome do Surface Hub 2S na lista de dispositivos próximos. Você pode encontrar o nome do Surface Hub 2S no canto inferior esquerdo da tela.
3. Insira um PIN se o administrador do sistema tiver habilitado a configuração de PIN para Miracast conexões. Isso exige que você insira um número de PIN ao se conectar Surface Hub 2S pela primeira vez.

> [!NOTE]
>Se você não vir o nome do dispositivo Surface Hub 2S conforme o esperado, é possível que a sessão anterior foi fechada prematuramente. Nesse caso, entre no Surface Hub 2S diretamente para encerrar a sessão anterior e, em seguida, conecte-se do dispositivo externo.

## <a name="connecting-peripherals-to-surface-hub-2s"></a>Conectando periféricos ao Surface Hub 2S

### <a name="bluetooth-accessories"></a>Acessórios Bluetooth

Você pode conectar os seguintes acessórios ao Surface Hub-2S usando Bluetooth:

- Mouses
- Teclados
- Fones de ouvido
- Alto-falantes
- Surface Hub duas canetas

> [!NOTE]
> Depois de conectar um fone de ouvido Bluetooth ou viva-voz, você precisará alterar as configurações padrão do microfone e do alto-falante. Para obter mais informações, consulte [Gerenciamento local para configurações do Surface Hub](local-management-surface-hub-settings.md).
