---
title: Como habilitar o teclado Surface Laptop durante a implantação do MDT
description: Ao usar o MDT para implantar Windows 10 laptops Surface, você precisa importar drivers de teclado para usar no ambiente Windows PE.
keywords: windows 10 surface, automate, customize, mdt
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
ms.openlocfilehash: d207d0843e23f68713597c12a529ab5574fa695e
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497914"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>Como habilitar o teclado Surface Laptop durante a implantação do MDT

Este artigo aborda uma abordagem de implantação que usa o MDT (Microsoft Deployment Toolkit). Você também pode aplicar essas informações a outras metodologias de implantação. Na maioria dos tipos de dispositivos Surface, o teclado deve funcionar durante a LTI (Instalação do Lite Touch). No entanto, Surface Laptop requer alguns drivers adicionais para habilitar o teclado. Para dispositivos Surface Laptop (1ª geração) e Surface Laptop 2, você deve preparar a estrutura de pastas e os perfis de seleção que permitem especificar drivers de teclado para uso durante a fase Windows PE (Ambiente de Pré-Instalação do Windows) do LTI. Para obter mais informações sobre essa estrutura de pastas, consulte [Implantar uma imagem Windows 10 usando o MDT: Etapa 5: Preparar o repositório de drivers](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!TIP]
> Ao usar drivers de teclado para Surface Laptop 2 e Surface Laptop 3 na mesma instância de inicialização do Windows PE, talvez seja necessário redefinir manualmente o firmware se o teclado ou touchpad não funcionar no Windows PE:
>
> - Pressione e segure o botão Ligar/Desligar por 30 segundos. Se você estiver conectado a uma PSU (unidade de alimentação), pressione e segure o botão Ligar até ver a luz no final do cabo PSU desligar brevemente antes de ligar novamente.

> [!IMPORTANT]
> Se você estiver implantando uma imagem do Windows 10 em um Surface Laptop que tenha o Windows 10 no modo S pré-instalado, consulte KB 4032347, Problemas ao implantar o [Windows em](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues) dispositivos Surface com o Windows 10 pré-instalado no modo S.

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>Adicionar drivers de teclado ao perfil de seleção

1. Baixe o arquivo Surface Laptop .msi mais recente dos locais apropriados:
    - [Surface Laptop drivers e firmware (1ª geração)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 drivers e firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 com drivers e firmware do processador Intel](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 com drivers e firmware do processador Intel](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 com drivers e firmware do processador AMD](https://www.microsoft.com/download/102923)
    - [firmware e drivers do Surface Laptop Studio](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 drivers e firmware](https://www.microsoft.com/download/details.aspx?id=103503)

2. Extraia o conteúdo do arquivo Surface Laptop .msi para uma pasta que você pode localizar facilmente (por exemplo, c:\surface_laptop_drivers). Para extrair o conteúdo, abra uma janela de Prompt de Comando com privilégios elevados e execute o comando do exemplo a seguir:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abra o Deployment Workbench e expanda **** o nó Compartilhamentos de Implantação e seu compartilhamento de implantação e navegue até a **pasta WindowsPEX64**.
4. Clique com o botão direito do **mouse na pasta WindowsPEX64** e selecione **Importar Drivers**.
5. Siga as instruções no Assistente para Importar Driver para importar as pastas de driver para a pasta WindowsPEX64.

 > [!NOTE]
 > Verifique o pacote .msi baixado para determinar o formato e a estrutura do diretório.  A estrutura de diretório será iniciada com SurfacePlatformInstaller (arquivos .msi mais antigos) ou SurfaceUpdate (arquivos .msi mais recentes), dependendo de quando o arquivo .msi foi liberado.

## <a name="import-drivers-for-surface-devices"></a>Importar drivers para dispositivos Surface

Importe as pastas a seguir conforme apropriado para seu Surface Laptop dispositivo.

| Dispositivo                                    | Importar pastas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Mais informações                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Laptop Studio**                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol                                                                                                                                                                                                                                                 | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Pro 8**                         | intelthcbase<br>ManagementEngine<br>surfaceacpiplatformextension<br>SurfaceBattery<br>SurfaceCoverClick<br>SurfaceEthernetAdapter<br>SurfaceHidMini<br>SurfaceHotPlug<br>surfaceintegrationdriver<br>SurfaceSar<br>SurfaceSerialHub<br>surfacetimealarmacpifilter<br>surfacetypecoverv7fprude<br>SurfaceUcmUcsiHidClient<br>surfacevirtualfunctionenum<br>tbtslimhostcontroller<br>TglChipset<br>TglSerial                                                                                                                                                                     | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 com processador Intel** | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 com processador AMD**   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 3 com processador Intel** | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | A importação das seguintes pastas habilitará a funcionalidade completa de teclado, trackpad e toque no PE:<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>Itouch<br>Chipset<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| **Surface Laptop 2**                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | Para arquivos .msi mais recentes que começam com "SurfaceUpdate", use:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                               |
| **Surface Laptop (1ª geração)**              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | Para arquivos .msi mais recentes que começam **com "SurfaceUpdate"**, use:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                       |

  > [!TIP]
  > Verifique o pacote .msi baixado para determinar o formato e a estrutura do diretório.  A estrutura de diretório será iniciada com SurfacePlatformInstaller (arquivos .msi mais antigos) ou SurfaceUpdate (arquivos .msi mais recentes), dependendo de quando o .msi foi liberado.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>Verifique se os drivers importados & configurar Windows pe

1. Verifique se a pasta WindowsPEX64 agora contém os drivers importados, conforme mostrado na figura a seguir:

   ![Imagem que mostra os drivers recém-importados na pasta WindowsPEX64 do Deployment Workbench.](./images/surface-laptop-keyboard-2.png)
1. Configure um perfil de seleção que usa a pasta WindowsPEX64, conforme mostrado na figura a seguir:

   ![Imagem que mostra a pasta WindowsPEX64 selecionada como parte de um perfil de seleção.](./images/surface-laptop-keyboard-3.png)
1. Configure as Windows PE do compartilhamento de implantação do MDT para usar o novo perfil de seleção, da seguinte maneira:
    - Para **Plataforma**, selecione **x64**.
    - Para **o perfil seleção**, selecione o novo perfil.
    - Selecione **Incluir todos os drivers do perfil de seleção**.

    ![Imagem que mostra as Windows PE do Compartilhamento de Implantação do MDT.](./images/surface-laptop-keyboard-4.png)
4. Verifique se você configurou os drivers Surface Laptop restantes usando um perfil de seleção ou uma **variável DriverGroup001**.
    - Para Surface Laptop (1ª geração), o modelo é **Surface Laptop**. Os drivers Surface Laptop restantes devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, conforme mostrado na figura a seguir.
    - Para Surface Laptop 2, o modelo é **Surface Laptop 2**. Os drivers Surface Laptop restantes devem residir na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.
    - Por Surface Laptop 3 com processador Intel, o modelo é Surface Laptop 3. Os drivers Surface Laptop restantes estão localizados na pasta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

    ![Imagem que mostra os drivers Surface Laptop regulares (1ª geração) na pasta Surface Laptop do Deployment Workbench.](./images/surface-laptop-keyboard-5.png)

Depois de configurar o Compartilhamento de Implantação do MDT para usar o novo perfil de seleção e as configurações relacionadas, continue o processo de implantação conforme descrito em Implantar uma imagem [Windows 10 usando o MDT: Etapa 6: Criar a](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence) sequência de tarefas de implantação.
