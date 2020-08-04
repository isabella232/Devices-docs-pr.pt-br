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
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903390"
---
# Wake on Power para dispositivos Surface

Os dispositivos de superfície podem ser desligados enquanto você estiver longe de sua mesa ou configurados para o modo de hibernação para economizar a duração da bateria. Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos de superfície compatíveis sejam iniciados automaticamente quando são reconectados à alimentação. Para configurar o Wake on Power, você pode usar o modo de gerenciamento do Surface Enterprise (SEMM) por meio do Configurador da Surface ou do Gerenciador UEFI.

O recurso Wake on Power está disponível nos seguintes dispositivos:

- Catálogo de superfície 3
- Surface Pro 7
- Laptop Surface 3
- Surface Pro X 

## Visão geral e pré-requisitos

O configurador UEFI de Surface permite salvar configurações de UEFI individuais em um pacote Windows Installer. msi para distribuição para dispositivos de destino. 

> [!NOTE]
> Este artigo pressupõe que você saiba como usar o SEMM. Para obter mais informações, consulte documentação [do modo de gerenciamento do Surface Enterprise (Semm)](surface-enterprise-management-mode.md) .

## Para habilitar o Wake on Power

1.  Baixe a versão mais recente do [configurador UEFI de Surface](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Entre em seu dispositivo Surface como administrador, abra **Surface configurador UEFI**, selecione **dispositivos de superfície**e, em seguida, selecione **Avançar**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione dispositivos de superfície e selecione avançar.":::
3.  Selecione **Iniciar**e, em seguida, selecione **criar** em **pacote de configuração**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione criar pacote de configuração.":::
4.  Selecione **proteção de certificado**e adicione seu arquivo. pfx de certificado. 
5. Digite sua senha, selecione **Avançar**, adicionar **proteção por senha**, conforme apropriado, e, em seguida, selecione **Avançar**.
6.  Na página **escolha qual tipo de superfície você deseja direcionar** , selecione os dispositivos de destino conforme apropriado. Por exemplo, selecione **Surface Pro 7**.
7.  Na página **recursos avançados** , selecione **Ativar energia**, defina o recurso como **ativado**e, em seguida, selecione **Avançar**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione Ativar na energia e definido como ativado."::: 
8.  Na página **êxito** , selecione **finalizar**.

    > [!NOTE]
    > Se esta for a primeira vez que você está fornecendo configurações para seu dispositivo, você será solicitado a fornecer também os dois últimos caracteres da impressão digital do certificado. 
9.  Salve o pacote. msi. 

## Aplicar o pacote MSI 

Você pode aplicar o pacote MSI a dispositivos na rede usando ferramentas de distribuição de software como o Gerenciador de configuração do Microsoft Endpoint. Este procedimento inclui etapas para instalar o pacote em seu computador local. 

1.  Em um prompt de comando elevado, insira o caminho completo do arquivo. msi para executar o pacote. msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Na caixa de diálogo de **aviso** , selecione **OK** ou desabilitar o BitLocker, conforme apropriado.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione OK ou desabilitar o BitLocker conforme apropriado.":::
3.  Na página de boas-vindas, selecione **Avançar** para executar o pacote e aplicar a configuração UEFI recém configurada.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Uma página de boas-vindas, selecione avançar.":::
4.  Reinicie o seu dispositivo. 

O Wake on Power está configurado agora. Para testar as configurações, desligue o dispositivo, desconecte o cabo de alimentação e reconecte a energia. O dispositivo deve ser iniciado automaticamente. 

## Referências

Para obter mais informações, consulte os artigos a seguir. 

- [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
- [Wake on LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

Ainda precisa de ajuda? Vá para [comunidade da Microsoft](https://answers.microsoft.com/).