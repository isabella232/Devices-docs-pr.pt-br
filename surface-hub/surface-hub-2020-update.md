---
title: Instale a Atualização do Windows 10 Team 2020
description: Obter a atualização mais recente do sistema operacional Surface Hub, Windows 10 Team 2020 Update.
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
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470409"
---
# <a name="install-windows-10-team-2020-update"></a>Instale a Atualização do Windows 10 Team 2020 

O novo sistema operacional Surface Hub, **Windows 10 Team 2020 Update**, com base no Windows 10 versão 20H2, agora está disponível para o Surface Hub 2S e o Surface Hub original (v1). 

- Consulte também: [Problemas conhecidos: Atualização do Windows 10 Team 2020](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>Distribuição

Você pode obter a Atualização do Windows 2020 usando um dos seguintes métodos:

- **Windows Update para Empresas**.
- **Imagem de recuperação de metal nu (BMR).** Opção recomendada para os clientes que ingressarem em seus dispositivos no Azure Active Directory ou não permitirem que seus dispositivos recebam atualizações da Internet. Para começar, consulte [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).
- **Windows Update.** A disponibilidade varia de acordo com a região/país, conforme a tabela a seguir:

| Fase | País/Região                         | Iniciando          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Austrália, Canadá, Bélgica, México | Outubro de 2020  |
| 2     | Reino Unido, Japão, Suíça, Itália          | Novembro de 2020 |
| 3     | Alemanha, Países Baixos                   | Final de fevereiro de 2021 |
| 4     | Global                                 | Início de março de 2021 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>Manutenção de Surface Hubs com Windows 10 Team Edition versão 1703 

O suporte de manutenção completa para [o Windows 10 Team Edition versão 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) está agendado para continuar até 16 de março de 2021.

### <a name="2s-devices"></a>Dispositivos 2S 

Os clientes em todas as regiões podem atualizar seus dispositivos Surface Hub 2S para a Atualização 2020 por meio do Windows Update, do Windows Update para Empresas ou usando a imagem de recuperação de bare metal (BMR), conforme explicado em Redefinir e recuperar para [o Surface Hub 2S](surface-hub-2s-recover-reset.md).

### <a name="v1-devices"></a>Dispositivos V1 

Os clientes em todas as regiões podem atualizar seus dispositivos do Surface Hub v1 para a Atualização 2020 por meio do Windows Update, do Windows Update para Empresas ou usando a Ferramenta de Recuperação do [Surface Hub.](surface-hub-recovery-tool.md) O KB5000749 deve ser instalado para receber a atualização no ar. Para saber mais, confira [o Blog do Surface IT Pro](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).
 
## <a name="whats-new"></a>Novidades

A Atualização do Windows 10 Team 2020 traz melhorias importantes para a implantação e a capacidade de gerenciamento de dispositivos, juntamente com os recursos mais recentes do Windows 10. Para saber mais, confira [Novidades no Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).
 
## <a name="before-you-begin"></a>Antes de começar

Antes de instalar o Windows 10 Team 2020 Update, certifique-se de salvar a chave BitLocker associada ao dispositivo. 

**Para salvar manualmente sua chave BitLocker**

1. Insira uma unidade USB no Surface Hub.
2. No Surface Hub, abra **Configurações** e insira suas credenciais de administrador quando solicitado.
3. Navegue **até Atualizar & Recuperação de**  >  **Segurança**.
4. Em **BitLocker,** selecione **Salvar**. A chave BitLocker é salva em um arquivo de texto na unidade USB.

Para saber mais, confira [Salvar a tecla BitLocker](save-bitlocker-key-surface-hub.md).

## <a name="learn-more"></a>Saiba mais

- [Novidades na atualização do Windows 10 Team 2020](surface-hub-2020-update-whats-new.md)
- [Atualização para a versão de lançamento do Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
