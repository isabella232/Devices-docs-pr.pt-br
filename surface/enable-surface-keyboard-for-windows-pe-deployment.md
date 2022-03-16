---
title: Como habilitar o teclado Surface Laptop durante a implantação do MDT
description: Ao usar o MDT para implantar Windows 10 para laptops Surface, você precisa importar drivers de teclado para usar no ambiente Windows PE.
keywords: windows 10 surface, automatize, customize, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 01/05/2022
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop Studio
- Surface Pro 8
- Windows 10
- Windows 11
ms.openlocfilehash: 8707d022ae5e3d3f34c59fab88328b5720896898
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449184"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>Como habilitar o teclado Surface Laptop durante a implantação do MDT

Este artigo aborda uma abordagem de implantação que usa o Microsoft Deployment Toolkit (MDT). Você também pode aplicar essas informações a outras metodologias de implantação. Na maioria dos tipos de dispositivos Surface, o teclado deve funcionar durante a Instalação Lite Touch (LTI). No entanto, Surface Laptop requer alguns drivers adicionais para habilitar o teclado. Para dispositivos Surface Laptop (1st Gen) e Surface Laptop 2, você deve preparar a estrutura de pastas e os perfis de seleção que permitem especificar drivers de teclado para uso durante a fase ambiente de pré-instalação do Windows (Windows PE) do LTI. Para obter mais informações sobre essa estrutura de pastas, consulte [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!TIP]
> Ao usar drivers de teclado para o Surface Laptop 2 e Surface Laptop 3 na mesma instância de inicialização Windows PE, talvez seja necessário redefinir manualmente o firmware se o teclado ou o touchpad não funcionarem no Windows PE:
>
> - Pressione e segure o botão Ligar por 30 segundos. Se você estiver conectado a uma unidade de alimentação (PSU), pressione e segure o botão Ligar até ver a luz no final do cabo PSU ser desligada brevemente antes de ligar novamente.

> [!IMPORTANT]
> Se você estiver implantando uma imagem Windows 10 em um Surface Laptop que tenha um Windows 10 no modo S pré-instalado, consulte KB 4032347, Problemas ao implantar o Windows em dispositivos Surface com Windows 10 [pré-instalados no modo S](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>Adicionar drivers de teclado ao perfil de seleção

1. Baixe o arquivo Surface Laptop .msi mais recente dos locais apropriados:
    - [Surface Laptop drivers e firmware (1ª geração)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 drivers e firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 com drivers e firmware do processador Intel](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 com drivers e firmware do processador Intel](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 com drivers e firmware do processador AMD](https://www.microsoft.com/download/102923)
    - [Surface Laptop Drivers e Firmware do Studio](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 drivers e firmware](https://www.microsoft.com/download/details.aspx?id=103503)

2. Extraia o conteúdo do arquivo Surface Laptop .msi para uma pasta que você pode facilmente localizar (por exemplo, c:\surface_laptop_drivers). Para extrair o conteúdo, abra uma janela de Prompt de Comando elevada e execute o comando do exemplo a seguir:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abra o Deployment Workbench e **expanda o** nó Compartilhamentos de Implantação e seu compartilhamento de implantação e navegue até a **pasta WindowsPEX64** .
4. Clique com o botão direito do mouse na **pasta WindowsPEX64** e selecione **Importar Drivers**.
5. Siga as instruções no Assistente de Importação de Driver para importar as pastas de driver para a pasta WindowsPEX64.

 > [!NOTE]
 > Verifique o pacote de .msi baixado para determinar o formato e a estrutura do diretório.  A estrutura de diretório começará com SurfacePlatformInstaller (arquivos .msi antigos) ou SurfaceUpdate (arquivos .msi mais novos), dependendo de quando o arquivo .msi foi lançado.

## <a name="import-drivers-for-surface-devices"></a>Importar drivers para dispositivos Surface

Importe as pastas a seguir conforme apropriado para seu Surface Laptop dispositivo.  

| Dispositivo                                | Importar pastas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Mais informações                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Laptop Studio                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol | n/d |
| Surface Pro 8                         | heci<br>ialpss2_gpio2_tgl<br>ialpss2_i2c_tgl<br>ialpss2_spi_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>msux64w10<br>netwtw08<br>surfacebattery<br>surfacehidminidriver<br>surfaceintegrationdriver<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>tbthostcontroller<br>tbthostcontrollerhsacomponent<br> |n/d |
| Surface Laptop 4 com processador Intel | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          |n/d                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 4 com processador AMD   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient |n/d                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 3 com processador Intel | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | A importação das seguintes pastas permitirá a funcionalidade completa de teclado, trackpad e toque em PE:<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>Chipset<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| Surface Laptop 2                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | Para arquivos mais .msi começando com "SurfaceUpdate", use:<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                                    |
| Surface Laptop (1ª Geração)              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | Para arquivos mais .msi começando com "SurfaceUpdate", use:<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                |

  > [!TIP]
  > Verifique o pacote de .msi baixado para determinar o formato e a estrutura do diretório.  A estrutura de diretório começará com o SurfacePlatformInstaller (arquivos .msi antigos) ou SurfaceUpdate (arquivos .msi mais novos), dependendo de quando o .msi foi lançado.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>Verificar drivers importados & configurar Windows pe

1. Verifique se a pasta WindowsPEX64 agora contém os drivers importados, conforme mostrado na figura a seguir:

   ![Imagem que mostra os drivers recém-importados na pasta WindowsPEX64 do Deployment Workbench.](./images/surface-laptop-keyboard-2.png)
1. Configure um perfil de seleção que usa a pasta WindowsPEX64, conforme mostrado na figura a seguir:

   ![Imagem que mostra a pasta WindowsPEX64 selecionada como parte de um perfil de seleção.](./images/surface-laptop-keyboard-3.png)
1. Configure as Windows PE do compartilhamento de implantação do MDT para usar o novo perfil de seleção, da seguinte forma:
    - Para **Plataforma**, selecione **x64**.
    - Para **Perfil de seleção**, selecione o novo perfil.
    - Selecione **Incluir todos os drivers do perfil de seleção**.

    ![Imagem que mostra as Windows PE do Compartilhamento de Implantação do MDT.](./images/surface-laptop-keyboard-4.png)
4. Verifique se você configurou os drivers Surface Laptop restantes usando um perfil de seleção ou uma **variável DriverGroup001**.
    - Para Surface Laptop (1ª Geração), o modelo é **Surface Laptop**. Os drivers Surface Laptop restantes devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop conforme mostrado na figura a seguir.
    - Para Surface Laptop 2, o modelo é **Surface Laptop 2**. Os drivers Surface Laptop restantes devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.
    - Para Surface Laptop 3 com processador Intel, o modelo é Surface Laptop 3. Os drivers Surface Laptop restantes estão localizados na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

    ![Imagem que mostra os drivers Surface Laptop (1ª Geração) na pasta Surface Laptop do Deployment Workbench.](./images/surface-laptop-keyboard-5.png)

Depois de configurar o Compartilhamento de Implantação do MDT para usar o novo perfil de seleção e as configurações relacionadas, continue o processo de implantação conforme descrito em [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).
