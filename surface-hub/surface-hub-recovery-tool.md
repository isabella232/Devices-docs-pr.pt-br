---
title: Uso da Ferramenta de Recuperação do Surface Hub
description: Como usar a ferramenta Surface Hub de recuperação para reimimá-lo.
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
ms.openlocfilehash: f472d42bba9270b117cfa8cb9b54eaeb020aefc4
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910976"
---
# <a name="using-the-surface-hub-recovery-tool"></a>Uso da Ferramenta de Recuperação do Surface Hub

A [ferramenta de](https://www.microsoft.com/download/details.aspx?id=52210) recuperação Microsoft Surface Hub ajuda Surface Hub imagem da unidade de estado sólido (SSD) usando um dispositivo de área de trabalho Windows 10, sem chamar o suporte ou substituir o SSD. Com essa ferramenta, você pode reimagear um SSD que tenha uma senha de Administrador desconhecida, erros de inicialização, não foi capaz de concluir uma recuperação de nuvem ou para um dispositivo que tenha uma versão mais antiga do sistema operacional. A ferramenta não corrigirá SSDs fisicamente danificados.

Para re-imagem do Surface Hub SSD usando a Ferramenta de Recuperação, você precisará remover o SSD do Surface Hub, conectar a unidade ao cabo USB-para-SATA e, em seguida, conectar o cabo ao computador desktop no qual a Ferramenta de Recuperação está instalada. Para obter mais informações sobre como remover a unidade existente do seu Surface Hub, [consulte Surface Hub SSD replacement](surface-hub-ssd-replacement.md).

> [!IMPORTANT]
> Não deixe o dispositivo dormir ou interrompa o download do arquivo de imagem.

Se a ferramenta não tiver êxito em reimaginá-la, entre em contato [Surface Hub Suporte](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="prerequisites"></a>Pré-requisitos

### <a name="mandatory"></a>Obrigatório

- Host pc executando a versão de 64 bits do Windows 10, versão 1607 ou superior.
- Acesso à rede e à Internet
- Abra a porta USB 2.0 ou superior
- Cabo USB para SATA
- 10 GB de espaço em disco livre no computador host
- SSDs fornecidos com Surface Hub ou um SSD fornecido pelo Suporte como uma substituição. SSDs não fornecidos pela Microsoft não são suportados.

### <a name="recommended"></a>Recomendações

- Conexão com a Internet de alta velocidade
- Abrir porta USB 3.0
- Cabo USB 3.0 ou superior USB para SATA
- A ferramenta de imagens foi testada com a seguinte make e modelo de cabos:
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## <a name="download-surface-hub-recovery-tool"></a>Baixar Surface Hub Ferramenta de Recuperação

Surface Hub A Ferramenta de Recuperação está disponível para download [Surface Hub Ferramentas para IT](https://www.microsoft.com/download/details.aspx?id=52210) sob o nome do arquivo **SurfaceHub_Recovery_v2.7.139.0.msi**.

> [!IMPORTANT]
> Esta versão, lançada em 11 de fevereiro de 2021, substitui a com build anterior, que não é mais funcional. Se você baixou essa ferramenta anteriormente, desinstale-a e instale a versão atual.

Para iniciar o download, clique em **Baixar**, **SurfaceHub_Recovery_v2.7.139.0.msi** na lista e clique em **Próximo.** No pop-up, escolha um dos seguintes:

- Clique **em Executar** para iniciar a instalação imediatamente.
- Clique **em Salvar** para copiar o download para seu computador para instalação posterior.

Instale Surface Hub Ferramenta de Recuperação no computador host.

## <a name="run-surface-hub-recovery-tool"></a>Executar Surface Hub Ferramenta de Recuperação

1. No computador host, selecione o botão **Iniciar,** role a lista alfabética à esquerda e selecione o atalho da ferramenta de recuperação.

    ![Microsoft Surface Hub Atalho da Ferramenta de Recuperação.](images/shrt-shortcut.png)

2. Clique em **Iniciar**.

    ![Botão Iniciar da Ferramenta de Recuperação.](images/shrt-start.png)


3. Na janela **Diretrizes,** clique em **Próximo**.

    ![Não deixe seu computador ir para orientação de sono.](images/shrt-guidance.png)

4. Na janela Selecionar imagem, clique em **RS2** ou seu **20H2**sucessor, selecione **Continuar** e selecione **Baixar imagem.**

     ![Ferramenta de Recuperação Selecione imagem.](images/shrt-select-image.png)
    ![Imagem de download da Ferramenta de Recuperação.](images/shrt-download-image.png)

5. O tempo para baixar a imagem de recuperação depende das velocidades de conexão com a Internet. Em uma conexão corporativa média, pode levar até uma hora para baixar o arquivo de imagem de 8 GB.

    ![Baixando imagem.](images/shrt-download.png)



5. Quando o download é concluído, a ferramenta instrui você a conectar uma unidade SSD. Se a ferramenta não conseguir localizar a unidade anexada, há uma boa chance de o cabo que está sendo usado não relatar o nome do SSD para Windows.  A ferramenta de imagens deve encontrar o nome da unidade como "LITEON L CH-128V2S USB Device" antes de poder continuar.  Para obter mais informações sobre como remover a unidade existente do seu Surface Hub, [consulte Surface Hub SSD replacement](surface-hub-ssd-replacement.md).

    ![Conexão SSD.](images/shrt-drive.png)

6. Quando a unidade for reconhecida, clique em **Iniciar** para iniciar o processo de re-imagem. No aviso de que todos os dados na unidade serão apagados, clique em **OK**.



    Antes de aplicar a imagem do sistema à unidade, o SSD é reparticionado e formatado. Copiar os binários do sistema levará aproximadamente 30 minutos, mas pode demorar mais, dependendo da velocidade do barramento USB, do cabo que está sendo usado ou do software antivírus instalado em seu sistema.



## <a name="troubleshooting-and-common-problems"></a>Solução de problemas e problemas comuns

Problema | Observações
--- | ---
A ferramenta falha ao imagem do SSD | Certifique-se de que você está usando um SSD fornecido de fábrica e um dos cabos testados.
O processo de reimagem aparece interrompido/congelado | É seguro fechar e reiniciar a Ferramenta de Recuperação Surface Hub sem nenhum efeito mal para o SSD.
A unidade não é reconhecida pela ferramenta | Verifique se o Surface Hub SSD está enumerado como uma unidade Lite-On, "LITEON L CH-128V2S USB Device".  Se a unidade for reconhecida como outro dispositivo nomeado, o cabo atual não será compatível. Experimente outro cabo ou um dos cabos testados listados acima.
Erro: -2147024809 | Abra o Gerenciador de Discos e remova as partições na Surface Hub unidade.  Desconecte e reconecte a unidade ao computador host. Reinicie a ferramenta de imagens novamente.

Se a ferramenta não tiver êxito em reimaginá-la, entre em contato [Surface Hub Suporte](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="version-history"></a>Histórico de versão


### <a name="version-v271390"></a>Versão v2.7.139.0

*Data de lançamento: 11 de fevereiro de 2021*<br>
Esta versão do Surface Hub Recovery Tool adiciona suporte para o seguinte:

- Atualização de segurança


### <a name="version-v201390"></a>Versão v2.0.139.0

> [!IMPORTANT]
> Esta versão não está mais funcional. Baixe a versão atual, listada acima. 

*Data de lançamento: 18 de dezembro de 2020*<br>
Esta versão do Surface Hub Recovery Tool adiciona suporte para o seguinte:
- Atualização para dar suporte Windows 10 Team Atualização 2020 (20H2)
- Melhorias na experiência do usuário
- Alterações de arquitetura
- Adições de telemetria

