---
title: Como habilitar o teclado do laptop Surface durante a implantação do MDT
description: Ao usar o MDT para implantar o Windows 10 em laptops Surface, você precisa importar drivers de teclado para usar no ambiente Windows PE.
keywords: superfície do Windows 10, automatizar, personalizar, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830281"
---
# Como habilitar o teclado do laptop Surface durante a implantação do MDT

Este artigo aborda uma abordagem de implantação que usa o Microsoft Deployment Toolkit (MDT). Você também pode aplicar essas informações a outras metodologias de implantação. Na maioria dos tipos de dispositivos Surface, o teclado deve funcionar durante a instalação do Lite Touch (LTI). No entanto, o Surface laptop requer alguns drivers adicionais para ativar o teclado. Para laptop Surface (1ª gen) e dispositivos Surface laptop 2, você deve preparar a estrutura de pastas e os perfis de seleção que permitem especificar os drivers de teclado para uso durante a fase de Windows PE (ambiente de pré-instalação do Windows) do LTI. Para obter mais informações sobre essa estrutura de pastas, consulte [implantar uma imagem do Windows 10 usando o MDT: etapa 5: preparar o repositório de drivers](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!NOTE]
> No momento, não há suporte para adicionar drivers de teclado 2 de Surface laptop 2 e Surface laptop 3 na mesma instância de inicialização do Windows PE devido a um conflito de driver; em vez disso, use instâncias separadas.

> [!IMPORTANT]
> Se você estiver implantando uma imagem do Windows 10 em um laptop Surface com o Windows 10 no modo S pré-instalado, consulte KB [4032347, problemas ao implantar o Windows em dispositivos Surface com o Windows 10 pré-instalado no modo S](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

Para adicionar os drivers do teclado ao perfil de seleção, siga estas etapas:

1. Baixe o arquivo MSI do laptop de superfície mais recente nos locais apropriados:
    - [Firmware e drivers de laptop Surface (1ª gen)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Firmware e drivers do Surface laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Laptop Surface 3 com drivers e firmware do processador Intel](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extraia o conteúdo do arquivo MSI do laptop Surface para uma pasta que você pode localizar facilmente (por exemplo, c:\ surface_laptop_drivers). Para extrair o conteúdo, abra uma janela de prompt de comando elevado e execute o comando do seguinte exemplo:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abra o Workbench de implantação e expanda o nó **compartilhamentos de implantação** e o compartilhamento de implantação e navegue até a pasta **WindowsPEX64** .

   ![Imagem que mostra o local da pasta WindowsPEX64 no Workbench de implantação](./images/surface-laptop-keyboard-1.png)

4. Clique com o botão direito do mouse na pasta **WindowsPEX64** e selecione **importar drivers**.
5. Siga as instruções no assistente de importação de driver para importar as pastas do driver para a pasta WindowsPEX64.  

> [!NOTE]
>  Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.  A estrutura do diretório começará com o SurfacePlatformInstaller (arquivos MSI mais antigos) ou com o SurfaceUpdate (arquivos MSI mais recentes), dependendo de quando o MSI foi lançado. 

Para dar suporte ao laptop Surface (1ª gen), importe as seguintes pastas:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

Para dar suporte a Surface laptop 2, importe as seguintes pastas:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
Para dar suporte ao laptop 4 do Surface com processador Intel, importe as seguintes pastas:

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

A importação das seguintes pastas habilitará a funcionalidade completa do teclado, do trackpad e do toque no PE para laptops Surface 3.

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- itouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
- ManagementEngine
- SurfaceAcpiNotify
- SurfaceBattery
- SurfaceDockIntegration
- SurfaceHidMini
- SurfaceHotPlug
- SurfaceIntegration
- SurfaceSerialHub
- SurfaceService
- SurfaceStorageFwUpdate


    > [!NOTE]
    >  Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.  A estrutura do diretório começará com o SurfacePlatformInstaller (arquivos MSI mais antigos) ou com o SurfaceUpdate (arquivos MSI mais recentes), dependendo de quando o MSI foi lançado. 

    Para dar suporte ao laptop Surface (1ª gen), importe as seguintes pastas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Para dar suporte a Surface laptop 2, importe as seguintes pastas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou para arquivos MSI mais recentes começando com "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Para dar suporte ao laptop 4 do Surface com processador Intel, importe as seguintes pastas:

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Para o laptop de Surface 3 com processador Intel, o modelo é o laptop Surface 3. Os drivers de laptop da superfície restante estão localizados na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 3.

6. Verifique se a pasta WindowsPEX64 agora contém os drivers importados. A pasta deve ser semelhante à seguinte:  

   ![Imagem que mostra os drivers recém importados na pasta WindowsPEX64 do Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Configurar um perfil de seleção que usa a pasta WindowsPEX64. O perfil de seleção deve ser semelhante ao seguinte:  

   ![Imagem que mostra a pasta WindowsPEX64 selecionada como parte de um perfil de seleção](./images/surface-laptop-keyboard-3.png)

8. Configure as propriedades do Windows PE do compartilhamento de implantação do MDT para usar o novo perfil de seleção, da seguinte maneira:  

   - Para a **plataforma**, selecione **x64**.
   - Para o **perfil de seleção**, selecione o novo perfil.
   - Selecione **incluir todos os drivers do perfil de seleção**.
   
   ![Imagem que mostra as propriedades do Windows PE do compartilhamento de implantação do MDT](./images/surface-laptop-keyboard-4.png)

9. Verifique se você configurou os drivers de laptop da superfície restante usando um perfil de seleção ou uma variável **DriverGroup001** .  
   - Para laptop Surface (1ª gen), o modelo é o **laptop Surface**. Os drivers de laptop da superfície restante devem residir na pasta de \MDT de implantação do Share\Out-of-Box Drivers\Windows10\X64\Surface laptop, conforme mostrado na figura que segue esta lista.
   - Para o Surface laptop 2, o modelo é o **laptop Surface 2**. Os drivers de laptop da superfície restante devem residir na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 2. 
   - Para o laptop de Surface 3 com processador Intel, o modelo é o laptop Surface 3. Os drivers de laptop da superfície restante estão localizados na pasta de implantação do \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface laptop 3.

   ![Imagem que mostra os drivers de laptop de superfície normal (1ª gen) na pasta de laptop Surface do Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Depois de configurar o compartilhamento de implantação do MDT para usar o novo perfil de seleção e as configurações relacionadas, continue o processo de implantação conforme descrito em [implantar uma imagem do Windows 10 usando o MDT: etapa 6: criar a sequência de tarefas de implantação](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).
