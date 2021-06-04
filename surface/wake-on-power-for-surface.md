---
title: Como habilitar o Wake on Power para Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Descreve como habilitar e desabilitar o Wake on Power para dispositivos Surface.
keywords: atualizar, implantar, driver, ltd, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271555"
---
# Wake on Power para dispositivos Surface

Os dispositivos Surface podem ser desligados enquanto você estiver longe da sua mesa ou definir o modo de hibernação para economizar a duração da bateria. Para melhorar a capacidade de gerenciamento desses dispositivos, o Wake on Power permite que dispositivos Surface compatíveis iniciem automaticamente quando eles se reconectam à energia. Para configurar o Wake on Power, você pode usar o Surface Enterprise Management Mode (SEMM) por meio do Configurador UEFI do Surface ou do Gerenciador UEFI.

O recurso Wake on Power está disponível nos seguintes dispositivos:

- Surface Pro 7+
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Laptop Go
- Surface Pro X 


##  <a name="overview-and-prerequisites"></a>Visão geral e pré-requisitos

O Configurador UEFI do Surface permite salvar configurações UEFI individuais em um pacote .msi do Windows Installer para distribuição a dispositivos de destino. 

> [!NOTE]
> Este artigo presume que você saiba como usar o SEMM. Para obter mais informações, consulte [a documentação do Surface Enterprise Management Mode (SEMM).](surface-enterprise-management-mode.md)

##  <a name="to-enable-wake-on-power"></a>Para habilitar o Wake on Power

1.  Baixe a versão mais recente do [Configurador UEFI do Surface.](https://www.microsoft.com/download/confirmation.aspx?id=46703)
2.  Entre no dispositivo Surface como administrador, abra o **Configurador UEFI**do Surface, selecione **Dispositivos Surface**e selecione **Próximo.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecione Dispositivos Surface e Clique em Próximo.":::
3.  Selecione **Iniciar**e Criar em **Pacote** **de Configuração.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Selecione Criar Pacote de Configuração.":::
4.  Selecione **Proteção de Certificado**e adicione seu arquivo .pfx de certificado. 
5. Insira sua senha, selecione **Próximo**, adicionar Proteção **por Senha,** conforme apropriado e, em seguida, selecione **Próximo**.
6.  Na página **Escolha qual tipo de Surface você deseja direcionar,** selecione seus dispositivos de destino conforme apropriado. Por exemplo, selecione **Surface Pro 7**.
7.  Na página **Recursos Avançados,** selecione a opção **** **Acioná-lo,** definir o recurso como On e, em seguida, selecione **Avançar.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Selecione a opção Acioná-la e de definida como 1."::: 
8.  Na página **Bem-sucedida,** selecione **End**.

    > [!NOTE]
    > Se esta for a primeira vez que você estiver fornecendo configurações para seu dispositivo, também será solicitado a fornecer os dois últimos caracteres da impressão digital do certificado. 
9.  Salve o pacote .msi. 

##  <a name="apply-the-msi-package"></a>Aplicar o pacote MSI 

Você pode aplicar o pacote MSI a dispositivos em sua rede usando ferramentas de distribuição de software, como o Microsoft Endpoint Configuration Manager. Esse procedimento inclui etapas para instalar o pacote no computador local. 

1.  Em um prompt de comando com elevação, insira o caminho completo do arquivo .msi para executar o pacote .msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Na caixa **de** diálogo Aviso, selecione **OK ou** desabilite o BitLocker, conforme apropriado.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecione OK ou desabilite o BitLocker conforme apropriado.":::
3.  Na página de boas-vindas, selecione **Próximo** para executar o pacote e aplicar a configuração UEFI recém-configurada.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Uma página de boas-vindas, selecione Próxima.":::
4.  Reinicie o dispositivo. 

O Wake on Power agora está configurado. Para testar as configurações, desligue o dispositivo, desconecte a energia e reconecte a energia. O dispositivo deve iniciar automaticamente. 

##  <a name="references"></a>Referências

Para obter mais informações, consulte os artigos a seguir. 

- [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
- [Adoção na LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

Ainda precisa de ajuda? Vá para [a Comunidade da Microsoft.](https://answers.microsoft.com/)