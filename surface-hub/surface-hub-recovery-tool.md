---
title: Uso da Ferramenta de Recuperação do Surface Hub
description: Como usar a Ferramenta de Recuperação do Surface Hub para fazer uma nova imagem do SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gerenciar o Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 34a05eeabd284e0ad43317577b8e7ff9348ffe21
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327335"
---
# Uso da Ferramenta de Recuperação do Surface Hub

A Ferramenta de Recuperação do [Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) ajuda você a fazer a imagem da unidade de estado sólido (SSD) do Surface Hub usando um dispositivo de área de trabalho do Windows 10, sem chamar o suporte ou substituir o SSD. Com essa ferramenta, você pode reimage um SSD que tenha uma senha de Administrador desconhecida, erros de inicialização, não foi possível concluir uma recuperação na nuvem ou para um dispositivo que tenha uma versão mais antiga do sistema operacional. A ferramenta não corrigirá SSDs fisicamente danificados.

Para fazer uma nova imagem do SSD do Surface Hub usando a Ferramenta de Recuperação, você precisará remover o SSD do Surface Hub, conectar a unidade ao cabo USB para SATA e, em seguida, conectar o cabo ao computador desktop no qual a Ferramenta de Recuperação está instalada. Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte Substituição [de SSD do Surface Hub.](surface-hub-ssd-replacement.md)

> [!IMPORTANT]
> Não deixe o dispositivo entrar em sleep ou interromper o download do arquivo de imagem.

Se a ferramenta não tiver êxito na imagem da unidade, entre em contato com o [Suporte do Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Pré-requisitos

### Obrigatório

- Computador host executando a versão de 64 bits do Windows 10, versão 1607 ou superior.
- Acesso à rede e à Internet
- Abrir porta USB 2.0 ou superior
- Cabo USB para SATA
- 10 GB de espaço livre em disco no computador host
- SSDs fornecidos com o Surface Hub ou um SSD fornecido pelo Suporte como um substituto. Não há suporte para SSDs fornecidos pela Microsoft.

### Recomendações

- Conexão com a Internet de alta velocidade
- Abrir porta USB 3.0
- Cabo USB 3.0 ou superior USB para SATA
- A ferramenta de imagem foi testada com a seguinte make e modelo de cabos:
    - Startech USB312SAT3CB
    - Blackwill RCUC16001
    - Ugrren 20231

## Baixar a Ferramenta de Recuperação do Surface Hub

A Ferramenta de Recuperação do Surface Hub está disponível para download das Ferramentas [do Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210)  para IT sob o nome de arquivo **SurfaceHub_Recovery_v2.7.139.0.msi**.

> [!IMPORTANT]
> Esta versão, lançada em 11 de fevereiro de 2021, substitui o build anterior, que não é mais funcional. Se você baixou essa ferramenta anteriormente, descarte e use a versão atual.

Para iniciar o download, clique em **Baixar,** **SurfaceHub_Recovery_v2.7.139.0.msi** na lista e clique em **Próximo.** No pop-up, escolha uma das seguintes:

- Clique **em Executar** para iniciar a instalação imediatamente.
- Clique **em** Salvar para copiar o download para o computador para instalação posterior.

Instale a Ferramenta de Recuperação do Surface Hub no computador host.

## Executar a Ferramenta de Recuperação do Surface Hub

1. No computador host, selecione o **botão** Iniciar, role pela lista alfabética à esquerda e selecione o atalho da ferramenta de recuperação.

    ![Atalho da Ferramenta de Recuperação do Microsoft Surface Hub](images/shrt-shortcut.png)

2. Clique em **Iniciar**.

    ![Botão Iniciar da Ferramenta de Recuperação](images/shrt-start.png)


3. Na janela **Diretrizes,** clique em **Próximo.**

    ![Não deixe seu computador ir para as diretrizes de sleep](images/shrt-guidance.png)

4. Na janela Selecionar imagem, clique em **RS2** ou em seu sucessor **20H2,** selecione Continuar e, em **seguida,** selecione **Baixar imagem.**

     ![Imagem de download da Ferramenta de ](images/shrt-select-image.png) ![ Recuperação Selecionar imagem](images/shrt-download-image.png)

5. O tempo para baixar a imagem de recuperação depende das velocidades de conexão com a Internet. Em uma conexão corporativa média, pode levar até uma hora para baixar o arquivo de imagem de 8 GB.

    ![Baixando imagem](images/shrt-download.png)



5. Quando o download for concluído, a ferramenta instrui você a conectar uma unidade SSD. Se a ferramenta não conseguir localizar a unidade anexada, é possível que o cabo que está sendo usado não reporte o nome do SSD para o Windows.  A ferramenta de imagem deve encontrar o nome da unidade como "LITEON L CH-128V2S USB Device" antes de continuar.  Para obter mais informações sobre como remover a unidade existente do Surface Hub, consulte Substituição [de SSD do Surface Hub.](surface-hub-ssd-replacement.md)

    ![Conectar SSD](images/shrt-drive.png)

6. Quando a unidade for reconhecida, clique em **Iniciar** para iniciar o processo de re-imagem. No aviso de que todos os dados na unidade serão apagados, clique em **OK.**



    Antes de aplicar a imagem do sistema à unidade, o SSD é reparticionado e formatado. Copiar os binários do sistema levará aproximadamente 30 minutos, mas pode demorar mais, dependendo da velocidade do barramento USB, do cabo que está sendo usado ou do software antivírus instalado no sistema.



## Solução de problemas e problemas comuns

Problema | Observações
--- | ---
A ferramenta falha ao imagem do SSD | Certifique-se de que você está usando um SSD fornecido por fábrica e um dos cabos testados.
O processo de re-imagem aparece interrompido/congelado | É seguro fechar e reiniciar a Ferramenta de Recuperação do Surface Hub sem nenhum efeito no SSD.
A unidade não é reconhecida pela ferramenta | Verifique se o SSD do Surface Hub está enumerado como uma unidade Lite-On, "LITEON L CH-128V2S USB Device".  Se a unidade for reconhecida como outro dispositivo nomeado, seu cabo atual não será compatível. Tente outro cabo ou um dos cabos testados listados acima.
Erro: -2147024809 | Abra o Gerenciador de Disco e remova as partições na unidade do Surface Hub.  Desconecte e reconecte a unidade ao computador host. Reinicie a ferramenta de imagem novamente.

Se a ferramenta não tiver êxito na imagem da unidade, entre em contato com o [Suporte do Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Histórico de versões


### Versão v2.7.139.0

*Data do lançamento: 11 de fevereiro de 2021*<br>
Esta versão da Ferramenta de Recuperação do Surface Hub adiciona suporte para o seguinte:

- Atualização de segurança


### Versão v2.0.139.0

> [!IMPORTANT]
> Esta versão não está mais funcional. Baixe a versão atual, listada acima. 

*Data do lançamento: 18 de dezembro de 2020*<br>
Esta versão da Ferramenta de Recuperação do Surface Hub adiciona suporte para o seguinte:
- Atualização para dar suporte ao Windows 10 Team 2020 Update (20H2)
- Melhorias na experiência do usuário
- Alterações de arquitetura
- Adições de telemetria

