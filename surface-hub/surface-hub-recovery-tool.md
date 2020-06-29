---
title: Uso da Ferramenta de Recuperação do Surface Hub
description: Como usar a ferramenta de recuperação do Surface Hub para recriar a imagem do SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gerenciar o Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831155"
---
# Uso da Ferramenta de Recuperação do Surface Hub

A [ferramenta de recuperação do Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) ajuda você a recriar uma nova imagem da unidade de estado sólido (SSD) do Hub Surface usando um dispositivo de desktop do Windows 10, sem ligar para o suporte ou para substituir a SSD. Com essa ferramenta, você pode renovar uma imagem do SSD com uma senha de administrador desconhecida, erros de inicialização, não foi possível concluir uma recuperação na nuvem ou para um dispositivo que tenha uma versão mais antiga do sistema operacional. A ferramenta não corrigirá o SSDs fisicamente danificado.

Para recriar a imagem da SSD do Surface Hub usando a ferramenta de recuperação, você precisará remover a SSD do Surface Hub, conectar a unidade ao cabo USB-para-SATA e conectar o cabo ao computador desktop no qual a ferramenta de recuperação está instalada. Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte [substituição da SSD do Surface Hub](surface-hub-ssd-replacement.md).

> [!IMPORTANT]
> Não deixe que o dispositivo vá para o modo de suspensão ou interrompa o download do arquivo de imagem.

Se a ferramenta não conseguir reportar sua unidade, entre em contato com o [suporte do Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## Pré-requisitos

### Obrigatório

- PC host executando a versão de 64 bits do Windows 10, versão 1607 ou posterior.
- Acesso à rede e à Internet
- Abrir porta USB 2,0 ou superior
- Cabo USB-para-SATA
- 10 GB de espaço livre em disco no computador host
- O SSDs é fornecido com o Surface Hub ou um SSD fornecido pelo suporte como substituto. Não há suporte para o SSDs não fornecido pela Microsoft.

### Recomendações

- Conexão à Internet de alta velocidade
- Porta USB 3,0 aberta
- Cabo USB 3,0 ou superior USB para SATA
- A ferramenta de imagem foi testada com a marca e o modelo de cabos a seguir:
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## Baixar a ferramenta de recuperação do Surface Hub

A ferramenta de recuperação do Surface Hub está disponível para download em [Ferramentas do Surface Hub para ele](https://www.microsoft.com/download/details.aspx?id=52210) sob o nome do arquivo **SurfaceHub_Recovery_v1.14.137.0.msi**.

Para iniciar o download, clique em **baixar**, escolha **SurfaceHub_Recovery_v1.14.137.0.msi** na lista e clique em **Avançar**. No menu pop-up, escolha uma das seguintes opções:

- Clique em **executar** para iniciar a instalação imediatamente.
- Clique em **salvar** para copiar o download para o seu computador para instalação posterior.

Instale a ferramenta de recuperação do Surface Hub no PC host.

## Executar a ferramenta de recuperação do Surface Hub

1. No PC host, selecione o botão **Iniciar** , Role pela lista em ordem alfabética à esquerda e selecione o atalho da ferramenta de recuperação.

    ![Atalho da ferramenta de recuperação do Microsoft Surface Hub](images/shrt-shortcut.png)

2. Clique em **Iniciar**.

    ![Botão Iniciar da ferramenta de recuperação](images/shrt-start.png)

3. Na janela **orientação** , clique em **Avançar**.

    ![Não deixe que sua máquina vá para a orientação de repouso](images/shrt-guidance.png)

4. clique em **Sim** para baixar a imagem. O tempo para baixar a imagem de recuperação depende de velocidades de conexão à Internet. Em uma conexão corporativa média, pode levar até uma hora para baixar o arquivo de imagem 8 GB.

    ![Baixar a imagem?](images/shrt-download.png)

5. Quando o download estiver concluído, a ferramenta instruirá você a conectar uma unidade SSD. Se a ferramenta não conseguir localizar a unidade anexada, há uma boa chance de que o cabo que está sendo usado não relate o nome da SSD para Windows.  A ferramenta de geração de imagens deve encontrar o nome da unidade como "dispositivo USB LITEON L CH-128V2S" para poder continuar.  Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte [substituição da SSD do Surface Hub](surface-hub-ssd-replacement.md).

    ![Conexão SSD](images/shrt-drive.png)

6. Quando a unidade for reconhecida, clique em **Iniciar** para começar o processo de recriação de imagens. No aviso de que todos os dados na unidade serão apagados, clique em **OK**.

    ![Iniciar a recriação da imagem do SSD](images/shrt-drive-start.png)

    Antes de aplicar a imagem do sistema à unidade, a SSD é reparticionada e formatada. Copiar os binários do sistema levará aproximadamente 30 minutos, mas poderá demorar mais dependendo da velocidade do barramento USB, do cabo que está sendo usado ou do software antivírus instalado no seu sistema.

    ![Cópia concluída](images/shrt-done.png)

    ![Recriação de imagem concluída](images/shrt-complete.png)

## Solução de problemas e problemas comuns

Problema | Observações
--- | ---
A ferramenta falha ao fazer a imagem do SSD | Certifique-se de que você esteja usando uma SSD fornecida na fábrica e um dos cabos testados.
O processo de recriação de imagem parece interrompido/congelado | É seguro fechar e reiniciar a ferramenta de recuperação do Surface Hub sem nenhum efeito ineficiente na SSD.
A unidade não é reconhecida pela ferramenta | Verifique se a SSD do Surface Hub é enumerada como uma unidade Lite, "LITEON L CH-128V2S USB Device".  Se a unidade for reconhecida como outro dispositivo nomeado, o cabo atual não será compatível. Tente outro cabo ou um dos cabos testados listados acima.
Erro:-2147024809 | Abra o Gerenciador de disco e remova as partições na unidade do Surface Hub.  Desconecte e reconecte a unidade ao computador host. Reinicie a ferramenta de imagem.

Se a ferramenta não conseguir reportar sua unidade, entre em contato com o [suporte do Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).
