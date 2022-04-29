---
title: Instale a Atualização do Windows 10 Team 2020
description: Obtenha a atualização mais recente do sistema operacional Surface Hub, Windows 10 Team atualização 2020.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 7474787351a9371fb09fa10348ac9f6591b81f6b
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497824"
---
# <a name="install-windows-10-team-2020-update"></a>Instale a Atualização do Windows 10 Team 2020 

O novo sistema operacional Surface Hub, **a Atualização Windows 10 Team 2020**, com base no Windows 10 versão 20H2, agora está disponível para o Surface Hub 2S e o Surface Hub original (v1). 

- Confira também: [Problemas conhecidos: Windows 10 Team atualização de 2020](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>Distribuição

Você pode obter Windows atualização 2020 usando um dos seguintes métodos:

- **Windows Update for Business**.
- **Imagem de recuperação bare-metal (BMR**). Opção recomendada para clientes que ingressam em seus dispositivos Azure Active Directory ou não permitem que seus dispositivos recebam atualizações da Internet. Para começar, consulte [Baixar uma imagem de recuperação para o Surface](https://support.microsoft.com/surfacerecoveryimage).
- **Windows Update.** A disponibilidade varia de acordo com a região/país, conforme mostrado na tabela a seguir:

| Fase | País/Região                         | Começando          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Austrália, Canadá, Bélgica, México | Outubro de 2020  |
| 2     | Reino Unido, Japão, Suíça, Itália          | Novembro de 2020 |
| 3     | Alemanha, Países Baixos                   | Final de fevereiro de 2021 |
| 4     | Global                                 | Início de março de 2021 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>Manutenção dos Surface Hubs com Windows 10 Team Edition 1703 

O suporte completo de manutenção [para Windows 10 Team Edition versão 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) está agendado para continuar até 16 de março de 2021.

### <a name="2s-devices"></a>Dispositivos 2S 

Os clientes em todas as regiões podem atualizar seus dispositivos Surface Hub 2S para a Atualização de 2020 por meio do Windows Update, Windows Update for Business ou usando a imagem de recuperação bare-metal (BMR), conforme explicado em Redefinir e recuperar para [o Surface Hub 2S](surface-hub-2s-recover-reset.md).

### <a name="v1-devices"></a>Dispositivos V1 

Os clientes em todas as regiões podem atualizar seus dispositivos Surface Hub v1 para a Atualização de 2020 por meio do Windows Update, Windows Update for Business ou usando a Ferramenta de Recuperação [Surface Hub](surface-hub-recovery-tool.md). KB5000749 deve ser instalado para receber a atualização no ar. Para saber mais, confira o [blog do Surface IT Pro](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).
 
## <a name="whats-new"></a>Novidades

Windows 10 Team atualização de 2020 traz melhorias importantes para a implantação e a capacidade de gerenciamento de dispositivos, juntamente com os recursos Windows mais recentes. Para saber mais, confira [As novidades da atualização Windows 10 Team 2020](surface-hub-2020-update-whats-new.md).
 
## <a name="before-you-begin"></a>Antes de começar

Antes de instalar o Windows 10 Team Atualização 2020, salve a chave do BitLocker associada ao seu dispositivo. 

**Para salvar manualmente a chave do BitLocker**

1. Insira uma unidade USB no Surface Hub.
2. No Surface Hub, abra **Configurações** e insira suas credenciais de administrador quando solicitado.
3. Navegue **até Update &** **SecurityRecovery** > .
4. Em **BitLocker**, selecione **Salvar**. A chave do BitLocker é salva em um arquivo de texto na unidade USB.

Para saber mais, confira [Salvar sua chave do BitLocker](save-bitlocker-key-surface-hub.md).

## <a name="learn-more"></a>Saiba mais

- [Novidades na atualização do Windows 10 Team 2020](surface-hub-2020-update-whats-new.md)
- [Atualização para a versão de lançamento do Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
