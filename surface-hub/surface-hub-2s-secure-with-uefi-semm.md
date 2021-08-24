---
title: Proteger e gerenciar Surface Hub 2S com SEMM
description: Saiba mais sobre como proteger o Surface Hub 2S com SEMM.
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
ms.openlocfilehash: b22bfc39c07facb84ca57438ec16038492f85d15
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911036"
---
# <a name="secure-and-manage-surface-hub-2s-with-semm-and-uefi"></a>Proteger e gerenciar o Surface Hub 2S com SEMM e UEFI

Novo no Surface Hub 2S, você pode usar o SEMM para gerenciar a configuração UEFI do dispositivo.
Use o Configurador UEFI do Microsoft Surface para controlar os seguintes componentes:

- LAN com fio
- Câmeras
- Bluetooth
- Wi-Fi
- Sensor de ocupação

Use o Configurador UEFI do Microsoft Surface para ativar ou desativar as seguintes configurações UEFI:

- Iniciar

    - Inicialização de IPv6 para PXE
    - Inicialização alternativa
    - Bloqueio da ordem de inicialização
    - Inicialização USB
- UEFI Front Page

    - Devices
    - Iniciar
    - Data/Hora

## <a name="create-uefi-configuration-image"></a>Criar imagem de configuração UEFI

Ao contrário de outros dispositivos Surface, você não pode usar um arquivo MSI ou uma imagem do Win PE para aplicar essas configurações no Surface Hub 2S. Em vez disso, você precisa criar uma imagem USB para carregar no dispositivo. Para criar uma Surface Hub de configuração uefi do 2S, baixe e instale a versão mais recente do Configurador UEFI do Microsoft Surface na página Ferramentas do [Surface para](https://www.microsoft.com/download/details.aspx?id=46703) IT no Centro de Download da Microsoft. Para obter mais informações sobre como usar UEFI e SEMM, consulte [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).

## <a name="to-configure-uefi-on-surface-hub-2s"></a>Para configurar a UEFI no Surface Hub 2S

1. Inicie o Configurador UEFI e, na primeira tela, escolha **Pacote de Configuração**.<br><br>
![* Inicie o Configurador UEFI e escolha Pacote de Configuração*.](images/sh2-uefi1.png) <br> <br>
2. Para adicionar o certificado ao pacote, você deve ter um certificado válido com a chave privada em um formato de arquivo .pfx para assinar e proteger o pacote. Selecione **+ Proteção de Certificado.** <br>
![* Selecione + Proteção de Certificado *.](images/sh2-uefi2.png) <br><br>
3. Insira a senha da chave privada do certificado.<br>
![* Insira a senha da chave privada do certificado *.](images/sh2-uefi3.png) <br><br>
4. Depois de importar a chave privada, continue criando o pacote.<br>
![* Continue criando o pacote *.](images/sh2-uefi4.png) <br><br>
5. Escolha **Hub** e **Surface Hub 2S** como o destino do pacote de configuração UEFI.<br>
![* Escolha Hub e Surface Hub 2S como o destino do pacote de configuração UEFI *.](images/sh2-uefi5.png) <br><br>
6. Escolha os componentes e configurações que você deseja ativar ou desativar no Surface Hub 2S.<br>
![* Escolha os componentes e configurações que você deseja ativar ou desativar *.](images/sh2-uefi6.png) <br><br>
7. Use a opção USB para exportar o arquivo.<br>
![* Use a opção USB para exportar o arquivo *.](images/sh2-uefi8.png) <br><br>
8. Insira e escolha a unidade USB que você gostaria de usar para este pacote. A unidade USB será formatada e você perderá todas as informações que tiver sobre ela.<br>
![* Insira e escolha a unidade USB do pacote *.](images/sh2-uefi9.png) <br><br>
9. Após a criação bem-sucedida do pacote, o Configurador exibirá os dois últimos caracteres da impressão digital do certificado. Você precisa desses caracteres ao importar para a configuração para Surface Hub 2S.<br>
![* Configuração bem-sucedida do pacote *.](images/sh2-uefi10.png) <br>

## <a name="to-boot-into-uefi"></a>Para inicializar em UEFI

Desativar o Surface Hub 2S. Pressione e segure o **botão Aumentar o Volume** e pressione o botão **Ligar.** Mantenha o botão Volume Para Cima até que o menu UEFI apareça.
