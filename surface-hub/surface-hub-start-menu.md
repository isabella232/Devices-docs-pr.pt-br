---
title: Configurar o menu Iniciar do Surface Hub
description: Use o MDM para personalizar o menu Iniciar no Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: ff08b8ab6e59af77761fb365980af261c47030a9
ms.sourcegitcommit: 09a47921ec2e565a92ba2baa61e181d218706ad9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "11921820"
---
# <a name="configure-surface-hub-start-menu"></a>Configurar o menu Iniciar do Surface Hub

A [atualização de 17 de janeiro de 2018 para o Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) habilita os menus Iniciar personalizados em dispositivos Surface Hub. Você aplica o layout do menu Iniciar personalizado usando o gerenciamento de dispositivo móvel (MDM).

Quando você aplica um layout do menu Iniciar personalizado ao Surface Hub, os usuários não podem fixar, desafixar ou desinstalar os apps de Iniciar. 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a>Como aplicar um menu Iniciar personalizado ao Surface Hub

O menu Iniciar personalizado é definido em um arquivo XML de layout de Iniciar. Você tem duas opções para criar o arquivo XML de layout de Iniciar:

- Editar o [XML padrão de Iniciar do Surface Hub](#default)

    - ou -

- Configure o menu Iniciar desejado em um desktop (fixando somente os apps disponíveis no Surface Hub) e depois [exporte o layout](/windows/configuration/customize-and-export-start-layout#export-the-start-layout).

>[!TIP]
>Para adicionar um bloco com um link da Web ao menu iniciar do desktop, vá para o link no Microsoft Edge, selecione `...` no canto superior direito e selecione **Fixar esta página em Iniciar**. Consulte [um layout de Iniciar que inclui um link do Microsoft Edge](#edge) para obter um exemplo de como os links aparecerão no XML.

Para editar o XML padrão ou o layout exportado, familiarize-se com o [XML do layout de Iniciar](/windows/configuration/start-layout-xml-desktop). Existem algumas [diferenças entre o layout de Iniciar em um desktop e em um Surface Hub.](#differences)

Quando você tiver o menu Iniciar definido em um XML de layout de Iniciar, [crie uma política de MDM para aplicar o layout.](/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a>Diferenças entre o Surface Hub e o menu Iniciar de desktop

Há algumas diferenças importantes entre a personalização do menu Iniciar para o Surface Hub e uma área de trabalho do Windows 10:

- Não é possível usar **[DesktopApplicationTile](/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile)** em seu XML de layout inicial porque Windows aplicativos de área de trabalho (Win32) não são suportados no Surface Hub.
- Você não pode usar o XML de layout de Iniciar para definir a barra de tarefas ou na tela de boas-vindas para o Surface Hub.  
- A política de layout de início deve ser atribuída somente a dispositivos, não usuários.
- A configuração OMA-URI a ser usada na política é `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- O Surface Hub dá suporte a um máximo de 6 colunas (6 blocos 1x1), mas você **deve** definir `GroupCellWidth=8` mesmo que o Surface Hub só exiba os blocos nas colunas de 0 a 5, e não colunas 6 e 7.
- O Surface Hub dá suporte a um máximo de 6 linhas (6 blocos 1x1)
- `SecondaryTile`, que é usado para links, abrirá o link no Microsoft Edge.


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a>Exemplo: Layout Padrão de Iniciar do Surface Hub

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:DesktopApplicationTile
            DesktopApplicationID="MSEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a>Exemplo: Layout de Iniciar que inclui um link do Microsoft Edge

Este exemplo mostra um link para um site e um link para um arquivo .pdf. O azulejo secundário para Microsoft Edge usa um ícone de 150 x 150 pixels.

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
          <start:DesktopApplicationTile
              DesktopApplicationID="MSEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
>O valor padrão para é claro; você não precisa incluir em seu XML, a menos que você esteja alterando o `ForegroundText` valor para `ForegroundText` escuro.
