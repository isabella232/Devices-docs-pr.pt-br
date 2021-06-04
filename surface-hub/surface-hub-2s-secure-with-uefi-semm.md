---
title: Proteger e gerenciar Surface Hub 2S com SEMM
description: Saiba mais sobre a proteção do Surface Hub 2S com o SEMM.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830420"
---
# Proteger e gerenciar o Surface Hub 2S com SEMM e UEFI

Novo no Surface Hub 2S, você pode usar SEMM para gerenciar a configuração de UEFI do dispositivo.
Use o configurador UEFI da Microsoft Surface para controlar os seguintes componentes:

- LAN com fio
- Câmeras
- Bluetooth
- Wi-Fi
- Sensor de ocupação

Use o configurador UEFI da Microsoft Surface para ativar ou desativar as seguintes configurações de UEFI:

- Iniciar

    - Inicialização de IPv6 para PXE
    - Inicialização alternativa
    - Bloqueio da ordem de inicialização
    - Inicialização USB
- Página inicial da UEFI

    - Devices
    - Iniciar
    - Data/Hora

##  <a name="create-uefi-configuration-image"></a>Criar a imagem de configuração UEFI

Ao contrário de outros dispositivos de superfície, você não pode usar um arquivo MSI ou uma imagem do PE PE para aplicar essas configurações no Surface Hub 2S. Em vez disso, você precisa criar uma imagem USB para carregar no dispositivo. Para criar uma imagem de configuração UEFI do Surface Hub 2S, baixe e instale a versão mais recente do Microsoft Surface UEFI Configuration da página [Surface Tools para it](https://www.microsoft.com/download/details.aspx?id=46703) no centro de download da Microsoft. Para obter mais informações sobre como usar UEFI e SEMM, consulte [modo de gerenciamento do Microsoft Surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode).

##  <a name="to-configure-uefi-on-surface-hub-2s"></a>Para configurar o UEFI no Surface Hub 2S

1. Inicie o configurador UEFI e, na primeira tela, escolha **pacote de configuração**.<br><br>
![* Iniciar o configurador UEFI e escolher pacote de configuração *](images/sh2-uefi1.png) <br> <br>
2. Para adicionar o certificado ao seu pacote, você deve ter um certificado válido com a chave privada em um formato de arquivo. pfx para assinar e proteger o pacote. Selecione **+ proteção de certificado.** <br>
![* Selecionar + proteção de certificado *](images/sh2-uefi2.png) <br><br>
3. Digite a senha da chave privada do certificado.<br>
![* Insira a senha da chave privada do certificado *](images/sh2-uefi3.png) <br><br>
4. Após importar a chave privada, continue a criar o pacote.<br>
![* Continuar a criar o pacote *](images/sh2-uefi4.png) <br><br>
5. Escolha **Hub** e **Surface Hub 2s** como o destino para o pacote de configuração UEFI.<br>
![* Escolha Hub e Surface Hub 2S como o destino para o pacote de configuração UEFI *](images/sh2-uefi5.png) <br><br>
6. Escolha os componentes e configurações que você deseja ativar ou desativar no Surface Hub 2S.<br>
![* Escolha os componentes e configurações que você deseja ativar ou desativar *](images/sh2-uefi6.png) <br><br>
7. Use a opção USB para exportar o arquivo.<br>
![* Use a opção USB para exportar o arquivo *](images/sh2-uefi8.png) <br><br>
8. Insira e escolha a unidade USB que você deseja usar para este pacote. A unidade USB será formatada e você perderá as informações que elas contêm.<br>
![* Insira e escolha a unidade USB para seu pacote *](images/sh2-uefi9.png) <br><br>
9. Após a criação bem-sucedida do pacote, o configurador mostrará os dois últimos caracteres da impressão digital do seu certificado. Você precisa desses caracteres ao importar para a configuração para o Surface Hub 2S.<br>
![* Configuração bem-sucedida do pacote *](images/sh2-uefi10.png) <br>

##  <a name="to-boot-into-uefi"></a>Para inicializar na UEFI

Desative o Surface Hub 2S. Pressione e mantenha pressionado o botão **volume up** e pressione o botão de **energia** . Mantenha pressionado o botão aumentar volume até que o menu UEFI seja exibido.
