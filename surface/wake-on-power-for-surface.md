---
title: Como habilitar o Wake on Power para Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Descreve como habilitar e desabilitar o Wake on Power para dispositivos Surface.
keywords: atualização, implantação, Driver, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902989"
---
# Wake on Power para dispositivos Surface

Os dispositivos de superfície podem ser desligados enquanto estiverem longe da mesa ou definidas para o modo de hibernação para economizar bateria. Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos de superfície compatíveis sejam iniciados automaticamente quando reconectados à alimentação. Configurar o Wake on Power requer o uso do modo de gerenciamento do Surface Enterprise (SEMM) por meio do Configurador UEFI ou do Gerenciador UEFI.

O Wake on Power é um recurso disponível nos seguintes dispositivos:

- Catálogo de superfície 3
- Surface Pro 7
- Laptop Surface 3
- Surface Pro X 

## Visão geral e pré-requisitos

Você pode usar o configurador UEFI de Surface para definir configurações individuais de UEFI salvas em um pacote do Windows Installer. msi para distribuição para dispositivos de destino. 

> [!NOTE]
> Este artigo pressupõe que você esteja familiarizado com o uso do SEMM. Para obter mais informações, consulte documentação [do modo de gerenciamento do Surface Enterprise (Semm)](surface-enterprise-management-mode.md) .

## Para habilitar o Wake on Power

1.  Baixe a versão mais recente do [configurador UEFI de Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Conecte-se ao seu dispositivo Surface como administrador, abra o **configurador UEFI do Surface**, selecione **dispositivos de superfície**e, em seguida, selecione **Avançar**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
3.  Selecione **Iniciar** e, em **pacote de configuração** , selecione **criar**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione criar pacote de configuração.":::
4.  Selecione **proteção de certificado** e adicione seu arquivo. pfx de certificado. Depois de inserir a senha, selecione **Avançar**. Adicione **proteção por senha**, conforme apropriado, e, em seguida, selecione **Avançar**.
5.  Na página **escolha qual tipo de superfície você deseja direcionar** , selecione os dispositivos de destino conforme apropriado. Por exemplo, **Surface Pro 7**.
6.  Na página **recursos avançados** , selecione **Ativar no Power** e definido como **ativado**. Selecione **Avançar**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione Ativar na energia e definido como ativado."::: 
7.  Na página **êxito** , selecione **finalizar**. Se esta for a primeira vez que você fornece configurações ao seu dispositivo, você será solicitado a fornecer os dois últimos caracteres da impressão digital do certificado. 
8.  Salve o pacote. msi. 

## Aplicar o pacote MSI 

Você pode aplicar o pacote MSI a dispositivos em sua rede usando ferramentas de distribuição de software como o Microsoft Endpoint Configuration Manager. Este procedimento inclui etapas para instalar o pacote em seu computador local. 

1.  Abra um prompt de comando elevado e insira o caminho completo do arquivo. msi para executar o pacote. msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Na caixa de diálogo de **aviso** , selecione **OK** ou desabilitar o BitLocker conforme apropriado.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione OK ou desabilitar o BitLocker conforme apropriado.":::
3.  Na página de boas-vindas, selecione **Avançar** para executar o pacote e aplicar a configuração UEFI recém configurada.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Uma página de boas-vindas, selecione avançar.":::
4.  Reinicie o seu dispositivo. 

O Wake on Power está configurado agora. Para testar a configuração, desligue o dispositivo, desconecte o cabo de alimentação e reconecte a energia. O dispositivo será iniciado automaticamente. 

## Mais informações

Para obter mais informações, consulte os artigos a seguir. 

- [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
- [Wake on LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

Ainda precisa de ajuda? Vá para [comunidade da Microsoft](https://answers.microsoft.com/).