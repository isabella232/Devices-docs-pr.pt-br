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
ms.openlocfilehash: c5b6a083d543649eab899d2fea36327d08f8bc29
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830231"
---
# <span data-ttu-id="a9bac-103">Configurar o menu Iniciar do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a9bac-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="a9bac-104">A [atualização de 17 de janeiro de 2018 para o Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) habilita os menus Iniciar personalizados em dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a9bac-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="a9bac-105">Você aplica o layout do menu Iniciar personalizado usando o gerenciamento de dispositivo móvel (MDM).</span><span class="sxs-lookup"><span data-stu-id="a9bac-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="a9bac-106">Quando você aplica um layout do menu Iniciar personalizado ao Surface Hub, os usuários não podem fixar, desafixar ou desinstalar os apps de Iniciar.</span><span class="sxs-lookup"><span data-stu-id="a9bac-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <span data-ttu-id="a9bac-107">Como aplicar um menu Iniciar personalizado ao Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a9bac-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="a9bac-108">O menu Iniciar personalizado é definido em um arquivo XML de layout de Iniciar.</span><span class="sxs-lookup"><span data-stu-id="a9bac-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="a9bac-109">Você tem duas opções para criar o arquivo XML de layout de Iniciar:</span><span class="sxs-lookup"><span data-stu-id="a9bac-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="a9bac-110">Editar o [XML padrão de Iniciar do Surface Hub](#default)</span><span class="sxs-lookup"><span data-stu-id="a9bac-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="a9bac-111">- ou -</span><span class="sxs-lookup"><span data-stu-id="a9bac-111">-or-</span></span>

- <span data-ttu-id="a9bac-112">Configure o menu Iniciar desejado em um desktop (fixando somente os apps disponíveis no Surface Hub) e depois [exporte o layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span><span class="sxs-lookup"><span data-stu-id="a9bac-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="a9bac-113">Para adicionar um bloco com um link da Web ao menu iniciar do desktop, vá para o link no Microsoft Edge, selecione `...` no canto superior direito e selecione **Fixar esta página em Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="a9bac-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="a9bac-114">Consulte [um layout de Iniciar que inclui um link do Microsoft Edge](#edge) para obter um exemplo de como os links aparecerão no XML.</span><span class="sxs-lookup"><span data-stu-id="a9bac-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="a9bac-115">Para editar o XML padrão ou o layout exportado, familiarize-se com o [XML do layout de Iniciar](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span><span class="sxs-lookup"><span data-stu-id="a9bac-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="a9bac-116">Existem algumas [diferenças entre o layout de Iniciar em um desktop e em um Surface Hub.](#differences)</span><span class="sxs-lookup"><span data-stu-id="a9bac-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="a9bac-117">Quando você tiver o menu Iniciar definido em um XML de layout de Iniciar, [crie uma política de MDM para aplicar o layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span><span class="sxs-lookup"><span data-stu-id="a9bac-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />
## <span data-ttu-id="a9bac-118">Diferenças entre o Surface Hub e o menu Iniciar de desktop</span><span class="sxs-lookup"><span data-stu-id="a9bac-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="a9bac-119">Há algumas diferenças importantes entre a personalização do menu Iniciar para o Surface Hub e uma área de trabalho do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="a9bac-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="a9bac-120">Você não pode usar **DesktopApplicationTile** ( https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) em seu XML de layout inicial porque não há suporte para aplicativos da área de trabalho do Windows (Win32) no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a9bac-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="a9bac-121">Você não pode usar o XML de layout de Iniciar para definir a barra de tarefas ou na tela de boas-vindas para o Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a9bac-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="a9bac-122">O Surface Hub dá suporte a um máximo de 6 colunas (6 blocos 1x1), mas você **deve** definir `GroupCellWidth=8` mesmo que o Surface Hub só exiba os blocos nas colunas de 0 a 5, e não colunas 6 e 7.</span><span class="sxs-lookup"><span data-stu-id="a9bac-122">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="a9bac-123">O Surface Hub dá suporte a um máximo de 6 linhas (6 blocos 1x1)</span><span class="sxs-lookup"><span data-stu-id="a9bac-123">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="a9bac-124">, que é usado para links, abrirá o link no Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a9bac-124">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />
## <span data-ttu-id="a9bac-125">Exemplo: Layout Padrão de Iniciar do Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a9bac-125">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
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
## <span data-ttu-id="a9bac-126">Exemplo: Layout de Iniciar que inclui um link do Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a9bac-126">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="a9bac-127">Este exemplo mostra um link para um site e um link para um arquivo .pdf.</span><span class="sxs-lookup"><span data-stu-id="a9bac-127">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="a9bac-128">O bloco secundário do Microsoft Edge usa um ícone de 150 x 150 pixels.</span><span class="sxs-lookup"><span data-stu-id="a9bac-128">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

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
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
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
><span data-ttu-id="a9bac-129">O valor padrão para `ForegroundText` é Light; não é necessário incluir `ForegroundText` em seu XML, a menos que você esteja alterando o valor para escuro.</span><span class="sxs-lookup"><span data-stu-id="a9bac-129">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>
