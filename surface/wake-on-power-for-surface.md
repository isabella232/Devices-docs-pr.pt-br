---
title: Wake on Power para dispositivos Surface
ms.author: greglin
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Descreve como habilitar e desabilitar o Wake em dispositivos Power for Surface.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 12/08/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 44508875254d2e3d004afef710b43ada2911de08
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448654"
---
# <a name="wake-on-power-for-surface-devices"></a>Wake on Power para dispositivos Surface

Os dispositivos Surface podem ser desligados enquanto você está longe da sua mesa ou definir o modo de hibernação para economizar a vida útil da bateria. Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos Surface compatíveis iniciem automaticamente quando eles são reconectados à energia. Para configurar Wake on Power, você pode usar o Surface Enterprise Modo de Gerenciamento (SEMM) por meio do Surface UEFI Configurator ou do Gerenciador uefi.

O recurso Wake on Power está disponível nos seguintes dispositivos:

- Surface Pro 8 (somente SKUs comerciais)
- Surface Pro 7+ (somente SKUs comerciais)
- Surface Pro X (todos os SKUs)
- Surface Pro 7 (todos os SKUs)
- Surface Go 3 (somente SKUs comerciais)
- Surface Laptop Studio (somente SKUs comerciais)
- Surface Book 3 (todos os SKUs)
- Surface Laptop 4 (somente SKUs comerciais)
- Surface Laptop 3 (todos os SKUs)
- Surface Laptop Go (todos os SKUs)


>[!TIP]
> As SKUs comerciais (também conhecidas como Surface for Business) são executados Windows 10 Pro/Enterprise ou Windows 11 Pro/Enterprise; os SKUs do consumidor são executados Windows 10/Windows 11 Home. Para saber mais, confira [Exibir as informações do sistema](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 

## <a name="overview-and-prerequisites"></a>Visão geral e pré-requisitos

O Configurador UEFI do Surface permite salvar configurações uefi individuais em um pacote Windows installer .msi para distribuição para dispositivos de destino. 

> [!NOTE]
> Este artigo supõe que você saiba como usar o SEMM. Para obter mais informações, consulte [a documentação do Surface Enterprise Modo de Gerenciamento (SEMM](surface-enterprise-management-mode.md)).

## <a name="to-enable-wake-on-power"></a>Para habilitar Wake on Power

1.  Baixe a versão mais recente do [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Entre no dispositivo Surface como administrador, abra o **Configurador UEFI do Surface**, selecione **Dispositivos Surface** e selecione **Próximo**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione Dispositivos Surface e selecione Próximo.":::
3.  Selecione **Iniciar** e, em seguida, selecione **Criar** em **Pacote de Configuração**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione Criar Pacote de Configuração.":::
4.  Selecione **Proteção de Certificado** e adicione seu arquivo .pfx de certificado. 
5. Insira sua senha, selecione **Próximo**, adicione **Proteção de Senha**, conforme apropriado, e selecione **Próximo**.
6.  Na página **Escolher qual tipo surface você deseja direcionar** , selecione seus dispositivos de destino conforme apropriado. Por exemplo, selecione **Surface Pro 7**.
7.  Na página **Recursos Avançados** , selecione **Acordar no Power**, de definir o recurso como **On** e, em seguida, selecione **Avançar**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione Acordar no Power e de definir como On."::: 
8.  Na página **Bem-sucedido** , selecione **Fim**.

    > [!NOTE]
    > Se essa for a primeira vez que você estiver fornecendo configurações para seu dispositivo, você também será solicitado a fornecer os dois últimos caracteres da impressão digital do certificado. 
9.  Salve o .msi pacote. 

## <a name="apply-the-msi-package"></a>Aplicar o pacote MSI 

Você pode aplicar o pacote MSI a dispositivos em toda a sua rede usando ferramentas de distribuição de software, como Microsoft Endpoint Configuration Manager. Este procedimento inclui etapas para instalar o pacote no computador local. 

1.  Em um prompt de comando elevado, insira o caminho completo do arquivo .msi para executar o .msi pacote. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Na caixa **de diálogo** Aviso, selecione **OK** ou desabilite BitLocker, conforme apropriado.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione OK ou desabilite o BitLocker conforme apropriado.":::
3.  Na página Bem-vindo, selecione **Próximo** para executar o pacote e aplicar a configuração UEFI recém-configurada.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Uma página bem-vindo, selecione Próximo.":::
4.  Reinicie o dispositivo. 

Wake on Power agora está configurado. Para testar as configurações, desligue o dispositivo, desconecte a energia e reconecte a energia. O dispositivo deve ser ativado automaticamente. 

## <a name="references"></a>Referências

Para obter mais informações, consulte os artigos a seguir. 

- [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
- [Acordar na LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

Ainda precisa de ajuda? Vá para [o Microsoft Community](https://answers.microsoft.com/).