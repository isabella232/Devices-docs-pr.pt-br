---
title: Como habilitar o teclado do Surface Laptop durante a implantação do MDT
description: Ao usar o MDT para implantar o Windows 10 em laptops Surface, você precisa importar drivers de teclado para usar no ambiente do Windows PE.
keywords: windows 10 surface, automatizar, personalizar, mdt
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
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312057"
---
# Como habilitar o teclado do Surface Laptop durante a implantação do MDT

Este artigo aborda uma abordagem de implantação que usa o Microsoft Deployment Toolkit (MDT). Você também pode aplicar essas informações a outras metodologias de implantação. Na maioria dos tipos de dispositivos Surface, o teclado deve funcionar durante a Lite Touch Installation (LTI). No entanto, o Surface Laptop requer alguns drivers adicionais para habilitar o teclado. Para dispositivos Surface Laptop (1ª geração) e Surface Laptop 2, você deve preparar a estrutura de pastas e os perfis de seleção que permitem especificar drivers de teclado para uso durante a fase do Ambiente de Pré-instalação do Windows (Windows PE) do LTI. Para obter mais informações sobre essa estrutura de pastas, consulte Implantar uma imagem do [Windows 10 usando o MDT: Etapa 5: Preparar](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)o repositório de drivers.

> [!TIP]    
> Ao usar drivers de teclado para o Surface Laptop 2 e o Surface Laptop 3 na mesma instância de inicialização do Windows PE, talvez seja necessário redefinir manualmente o firmware se o teclado ou o touchpad não funcionarem no Windows PE:
>
> - Pressione e segure o botão Ligar/Desligar por 30 segundos. Se você estiver conectado a uma PSU (unidade de alimentação), pressione e segure o botão Ligar/Desligar até ver a luz no final do cabo PSU desligar brevemente antes de reconectar.

> [!IMPORTANT]
> Se você estiver implantando uma imagem do Windows 10 em um Surface Laptop que tenha o Windows 10 no modo S pré-instalado, consulte KB [4032347,](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Problemas ao implantar o Windows em dispositivos Surface com o Windows 10 pré-instalado no modo S.

Para adicionar os drivers de teclado ao perfil de seleção, siga estas etapas:

1. Baixe o arquivo MSI mais recente do Surface Laptop dos locais apropriados:
    - [Firmware e drivers do Surface Laptop (1ª geração)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Firmware e drivers do Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 com firmware e drivers de processador Intel](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extraia o conteúdo do arquivo MSI do Surface Laptop para uma pasta que você pode localizar facilmente (por exemplo, c:\surface_laptop_drivers). Para extrair o conteúdo, abra uma janela de Prompt de Comando com elevação e execute o comando a partir do exemplo a seguir:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abra o Deployment Workbench e expanda o nó **Deployment Shares** e seu compartilhamento de implantação e navegue até a **pasta WindowsPEX64.**

   ![Imagem que mostra o local da pasta WindowsPEX64 no Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. Clique com o botão direito do mouse **na pasta WindowsPEX64** e selecione **Import Drivers**.

5. Siga as instruções do Assistente para Importação de Driver para importar as pastas de driver para a pasta WindowsPEX64.  

    > [!NOTE]
    >  Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.  A estrutura de diretórios começará com SurfacePlatformInstaller (arquivos MSI mais antigos) ou SurfaceUpdate (arquivos MSI mais novos), dependendo de quando o MSI foi lançado. 

    Para dar suporte ao Surface Laptop (1ª geração), importe as seguintes pastas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Para dar suporte ao Surface Laptop 2, importe as seguintes pastas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\serialioi2c
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

     
    Para dar suporte ao Surface Laptop 3 com processador Intel, importe as seguintes pastas:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    A importação das seguintes pastas habilita a funcionalidade completa de teclado, trackpad e toque no PE para Surface Laptop 3.

    - SerialIOGPIO
    - SerialIOI2C
    - SerialIOSPI
    - SerialIOUART
    - itouch
    - Chipset
    - ChipsetLPSS
    - ChipsetNorthpeak
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
     >  Verifique o pacote MSI baixado para determinar o formato e a estrutura do diretório.  A estrutura de diretórios começará com SurfacePlatformInstaller (arquivos MSI mais antigos) ou SurfaceUpdate (arquivos MSI mais novos), dependendo de quando o MSI foi lançado. 

     Para dar suporte ao Surface Laptop (1ª geração), importe as seguintes pastas:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Para dar suporte ao Surface Laptop 2, importe as seguintes pastas:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\I2C
    - SurfacePlatformInstaller\Drivers\System\SPI
    - SurfacePlatformInstaller\Drivers\System\UART
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou para arquivos MSI mais novos que começam com "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Para dar suporte ao Surface Laptop 3 com processador Intel, importe as seguintes pastas:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Para o Surface Laptop 3 com processador Intel, o modelo é o Surface Laptop 3. Os drivers restantes do Surface Laptop estão localizados na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

6. Verifique se a pasta WindowsPEX64 agora contém os drivers importados. A pasta deve se parecer com o seguinte:  

   ![Imagem que mostra os drivers recém-importados na pasta WindowsPEX64 do Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Configure um perfil de seleção que use a pasta WindowsPEX64. O perfil de seleção deve se parecer com o seguinte:  

   ![Imagem que mostra a pasta WindowsPEX64 selecionada como parte de um perfil de seleção](./images/surface-laptop-keyboard-3.png)

8. Configure as propriedades do Windows PE do compartilhamento de implantação do MDT para usar o novo perfil de seleção, da seguinte forma:  

   - For **Platform**, select **x64**.
   - Para **o perfil de seleção,** selecione o novo perfil.
   - Selecione **Incluir todos os drivers do perfil de seleção.**
   
   ![Imagem que mostra as propriedades do Windows PE do compartilhamento de implantação do MDT](./images/surface-laptop-keyboard-4.png)

9. Verifique se você configurou os drivers restantes do Surface Laptop usando um perfil de seleção ou uma **variável DriverGroup001.**  
   - Para o Surface Laptop (1ª geração), o modelo é **o Surface Laptop.** Os drivers restantes do Surface Laptop devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, conforme mostrado na figura que segue esta lista.
   - Para o Surface Laptop 2, o modelo é **o Surface Laptop 2.** Os drivers restantes do Surface Laptop devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2. 
   - Para o Surface Laptop 3 com processador Intel, o modelo é o Surface Laptop 3. Os drivers restantes do Surface Laptop estão localizados na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

   ![Imagem que mostra os drivers regulares do Surface Laptop (1ª geração) na pasta Surface Laptop do Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Depois de configurar o Compartilhamento de Implantação do MDT para usar o novo perfil de seleção e as configurações relacionadas, continue o processo de implantação conforme descrito em Implantar uma imagem do [Windows 10 usando o MDT: Etapa 6:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)Criar a sequência de tarefas de implantação.
