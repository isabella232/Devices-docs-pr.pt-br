---
title: Gerenciar configurações com um provedor de MDM (Surface Hub)
description: O Microsoft Surface Hub fornece uma solução de gerenciamento empresarial para ajudar os administradores de TI a gerenciar políticas e aplicativos de negócios nesses dispositivos usando uma solução de MDM (gerenciamento de dispositivo móvel).
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: gerenciamento de dispositivo móvel, MDM, gerenciar políticas
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/07/2018
ms.localizationpriority: medium
ms.openlocfilehash: 2bee8b58b7978923c6e60e43f9e10a85dc4bec06
ms.sourcegitcommit: 17170c03206d190851b5f8e794fcc83ebbed7b5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103897"
---
# Gerenciar configurações com um provedor de MDM (Surface Hub)

O Surface Hub e outros dispositivos Windows 10 permitem que os administradores de TI gerenciem configurações e políticas usando um provedor de MDM (gerenciamento de dispositivo móvel). Um componente de gerenciamento interno se comunica com o servidor de gerenciamento, portanto, não é necessário instalar clientes adicionais no dispositivo. For more information, see [Windows 10 mobile device management](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx).

Surface Hub has been validated with Microsoft's first-party MDM providers:
- Microsoft Intune standalone
- On-premises MDM with Microsoft Endpoint Configuration Manager

You can also manage Surface Hubs using any third-party MDM provider that can communicate with Windows 10 using the MDM protocol.

## <a href="" id="enroll-into-mdm"></a>Enroll a Surface Hub into MDM
You can enroll your Surface Hubs using bulk, manual, or automatic enrollment.

### Bulk enrollment
**Para configurar o registro em massa**
- O Surface Hub dá suporte para o [CSP de provisionamento](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) para registro em massa no MDM. Para obter mais informações, consulte [Registro em massa no Windows 10](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx).<br>
--OR--
- If you have an on-premises Microsoft Endpoint Configuration Manager infrastructure, see [How to bulk enroll devices with On-premises Mobile Device Management in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm).

### Manual enrollment
**Para configurar o registro manual**
1. No Surface Hub, abra **Configurações**.
2. Digite as credenciais de administrador de dispositivo quando solicitado.
3. Selecione **Este dispositivo**e navegue até **Gerenciamento de dispositivos**.
4. Em **Gerenciamento de dispositivos**, selecione **+ Gerenciamento de dispositivos**.
5. Follow the instructions in the dialog to connect to your MDM provider.

### Automatic enrollment via Azure Active Directory join

Surface Hub now supports the ability to automatically enroll in Intune by joining the device to Azure Active Directory. 

First step is to set up Automatic MDM enrollment. See [Enable Windows 10 automatic enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

Then, when devices are setup during First-run, pick the option to join to Azure Active Directory, see [Set up admins for this device page](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page)

## Manage Surface Hub settings with MDM

Você pode usar o MDM para gerenciar algumas [configurações do CSP do Surface Hub](#supported-surface-hub-csp-settings) e algumas [configurações do Windows 10](#supported-windows-10-settings). Depending on the MDM provider that you use, you may set these settings using a built-in user interface, or by deploying custom SyncML. Microsoft Intune and Microsoft Endpoint Configuration Manager provide built-in experiences to help create policy templates for Surface Hub. Refer to documentation from your MDM provider to learn how to create and deploy SyncML.

### Configurações do CSP do Surface Hub com suporte

You can configure the Surface Hub settings in the following table using MDM. The table identifies if the setting is supported with Microsoft Intune, Microsoft Endpoint Configuration Manager, or SyncML.

For more information, see [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     Configuração                                      |                                                    Nó no CSP SurfaceHub                                                    |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                Horas de manutenção                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       Sim                        |                       Sim                       |             Sim             |
|              Ligar a tela automaticamente usando sensores de movimento               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       Sim                        |                       Sim                       |             Sim             |
|                      Exigir um PIN para projeção sem fio                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       Sim                        |                       Sim                       |             Sim             |
|                            Habilitar projeção sem fio                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                 Canal Miracast a ser usado para projeção sem fio                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|              Conectar-se ao seu espaço de trabalho do Operations Management Suite               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                         Imagem de fundo da tela de boas-vindas                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Informações de reunião exibidas na tela de boas-vindas                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       Sim                        | Yes.<br> [Use a custom setting.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager |             Yes             |
|                      Nome amigável para a projeção sem fio                       |                                                     Properties/FriendlyName                                                      | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|                   Device account                                                 | DeviceAccount/*`<name_of_policy>`* <br> Consulte [CSP SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). |                        Não                        |                       Não                        |             Sim             |
|                               Especificar o domínio do Skype                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Iniciar automaticamente o Conectar App quando a projeção for iniciada               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                                Definir o volume padrão                                |                                                     Properties/DefaultVolume                                                     |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                                Definir o tempo limite da tela                                |                                                     Properties/ScreenTimeout                                                     |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                               Definir o tempo limite da sessão                                |                                                    Properties/SessionTimeout                                                     |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                                Definir o tempo limite de suspensão                                 |                                                     Properties/SleepTimeout                                                      |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                   Permitir que a sessão seja retomada depois que a tela ficar ociosa                   |                                                  Properties/AllowSessionResume                                                   |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|             Permitir que a conta de dispositivo seja usada para autenticação de proxy             |                                                  Properties/AllowAutoProxyAuth                                                   |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
| Desabilitar o preenchimento automático do diálogo de entrada com convidados de reuniões agendadas |                                               Properties/DisableSignInSuggestions                                                |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|              Desabilitar o recurso "Minhas reuniões e arquivos" no menu Iniciar               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    Sim </br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                     Defina o LanProfile para Autenticação de 802.1 x com Fio                     |                                                         Dot3/LanProfile                                                          | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                    Defina o EapUserData para Autenticação de 802.1 x com Fio                     |                                                         Dot3/EapUserData                                                         | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

### Configurações do Windows 10 com suporte

Além das configurações específicas do Surface Hub, há inúmeras configurações comuns a todos os dispositivos Windows 10. Essas configurações são definidas na [Referência de provedor de serviços de configuração](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference). 

As tabelas a seguir incluem informações sobre as configurações do Windows 10 que foram validadas com o Surface Hub. There is a table with settings for these areas: security, browser, Windows Updates, Windows Defender, remote reboot, certificates, and logs. Each table identifies if the setting is supported with Microsoft Intune, Microsoft Endpoint Configuration Manager, or SyncML.

#### Security settings

|      Configuração       |                                            Detalhes                                             |                                                                          Referência de CSP                                                                           |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Permitir Bluetooth   |                      Mantenha isso habilitado para dar suporte para periféricos Bluetooth.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
| Políticas de Bluetooth | Use para definir o nome do dispositivo Bluetooth e bloquear publicidade, descoberta e emparelhamento automático. |                     Bluetooth/*`<name of policy>`* <br> Consulte [CSP da Política](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|    Permitir câmera    |                           Mantenha isso habilitado para o Skype for Business.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|   Permitir localização   |                        Mantenha isso habilitado para dar suporte a aplicativos, como o Mapas.                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   Sim. <br> .                    | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|  Permitir telemetria   |                    Mantenha isso habilitado para ajudar a Microsoft a melhorar o Surface Hub.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|  Permitir Unidades USB  |                     Mantenha isso habilitado para dar suporte a unidades USB no Surface Hub                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows. 

#### Configurações do navegador

|                          Configuração                          |                                                                        Detalhes                                                                        |                                                                             Referência de CSP                                                                              |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         Homepages                         |                                               Use para configurar as homepages padrão no Microsoft Edge.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                       Permitir cookies                       |                    O Surface Hub exclui os cookies automaticamente no final de uma sessão. Use isso para bloquear cookies em uma sessão.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                   Permitir ferramentas de desenvolvedor                   |                                                   Use para evitar que os usuários utilizem as Ferramentas de Desenvolvedor F12.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                    Permitir não rastrear                     |                                                          Use para habilitar cabeçalhos Não Rastrear.                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                       Permitir pop-ups                       |                                                         Use para bloquear as janelas pop-up do navegador.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                 Permitir sugestões de pesquisa                  |                                                  Use para bloquear sugestões de pesquisa na barra de endereços.                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|                     Allow Windows Defender SmartScreen                     |                                                       Keep this enabled to turn on Windows Defender SmartScreen.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
| Prevent ignoring Windows Defender SmartScreen warnings for websites |     For extra security, use to stop users from ignoring Windows Defender SmartScreen warnings and block them from accessing potentially malicious websites.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|  Prevent ignoring Windows Defender SmartScreen warnings for files   | For extra security, use to stop users from ignoring Windows Defender SmartScreen warnings and block them from downloading unverified files from Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Configurações do Windows Update

|                      Configuração                      |                                                                                                           Detalhes                                                                                                            |                                                                    Referência de CSP                                                                    |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Use Current Branch or Current Branch for Business |                                                       Use para configurar o Windows Update for Business – veja [Atualizações do Windows](manage-windows-updates-for-surface-hub.md).                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Adiar atualizações de recursos               |                                                                                                          Veja acima.                                                                                                          | [Update/DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Adiar atualizações de qualidade               |                                                                                                          Veja acima.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Pausar atualizações de recursos               |                                                                                                          Veja acima.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Pausar atualizações de qualidade               |                                                                                                          Veja acima.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|           Configurar dispositivo para usar o WSUS            |                                            Use para conectar o Surface Hub ao WSUS em vez do Windows Update – veja [Atualizações do Windows](manage-windows-updates-for-surface-hub.md).                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Otimização de entrega               | Use o compartilhamento de conteúdo ponto a ponto para reduzir problemas de largura de banda durante atualizações. Consulte [Configurar a Otimização de Entrega para o Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization) para obter detalhes. |         DeliveryOptimization/*`<name of policy>`* <br> Consulte [CSP da Política](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Configurações do Windows Defender

|      Configuração      |                                              Detalhes                                               |                                                     Referência de CSP                                                      |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Políticas do Defender |            Use para definir várias configurações do Defender, inclusive uma hora de verificação agendada.            | Defender/*`<name of policy>`* <br> Consulte [CSP da Política](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|  Defender status  | Use to initiate a Defender scan, force a Security intelligence update, query any threats detected. |                   [Defender CSP](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Yes                        |                       Sim                       |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Reinicialização remota

|                       Configuração                        |                                                          Detalhes                                                          |                                                             Referência de CSP                                                             |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Reiniciar o dispositivo imediatamente             | Use em conjunto com o OMS para minimizar os custos de suporte – consulte [Monitorar o Microsoft Surface Hub](monitor-surface-hub.md). |        ./Vendor/MSFT/Reboot/RebootNow <br> Consulte [CSP de reinicialização](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       Sim                        |                       Não                        |             Sim             |
|    Reinicie o dispositivo em data e hora agendadas    |                                                        Consulte acima.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> Consulte [CSP de reinicialização](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
| Reiniciar o dispositivo diariamente em data e hora agendadas |                                                        Consulte acima.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> Consulte [CSP de reinicialização](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Instalar certificados

|             Configuração             |                           Detalhes                            |                                           Referência de CSP                                            |                                                         Tem suporte com<br>Intune?                                                          |                                                                  Tem suporte com<br>Configuration Manager?                                                                  | Tem suporte com<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Instalar certificados CA confiáveis | Use para implantar certificados CA raiz e intermediários confiáveis. | [CSP RootCATrustedCertificates](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | Sim. <br> Consulte [Configurar perfis de certificado do Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | Yes. <br> See [How to create certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles). |             Yes             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Coletar registros

|     Configuração      |                      Detalhes                       |                                     Referência de CSP                                      | Tem suporte com<br>Intune? | Tem suporte com<br>Configuration Manager? | Tem suporte com<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| Collect ETW logs | Use remotamente para coletar logs do ETW do Surface Hub. | [CSP DiagnosticLog](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            Não             |                    Não                    |             Sim             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Definir qualidade de rede de política de serviço (QoS)

|        Configuração         |                                                            Detalhes                                                             |                                                    Referência de CSP                                                     |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Set Network QoS Policy | Use para definir uma política de QoS para executar um conjunto de ações no tráfego de rede. Isso é útil para priorizar os pacotes de rede do Skype. | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Definir proxy de rede

|      Configuração      |                               Detalhes                               |                                                Referência de CSP                                                 |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Set Network proxy | Use para configurar um servidor proxy para conexões Wi-Fi e Ethernet. | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### Configurar o menu Iniciar

|       Configuração        |                                                                       Detalhes                                                                        |                                                        Referência de CSP                                                         |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Configure Start menu | Use para configurar quais apps serão exibidos no menu Iniciar. Para obter mais informações, consulte [Configurar o menu Iniciar do Surface Hub](surface-hub-start-menu.md) | [CSP de Política: Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

### Generate OMA URIs for settings 
You need to use a setting's OMA URI to create a custom policy in Intune, or a custom setting in Microsoft Endpoint Configuration Manager.

**To generate the OMA URI for any setting in the CSP documentation**
1. Na documentação do CSP, identifique o nó raiz do CSP. Geralmente, ele tem o seguinte formato `./Vendor/MSFT/<name of CSP>` <br>
*Por exemplo, o nó raiz do [CSP SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) é `./Vendor/MSFT/SurfaceHub`.*
2. Identifique o caminho do nó da configuração que você quer usar. <br>
*Por exemplo, o caminho do nó da configuração para habilitar a projeção sem fio é `InBoxApps/WirelessProjection/Enabled`.*
3. Acrescente o caminho do nó ao nó raiz para gerar o OMA URI. <br>
*Por exemplo, o OMA URI da configuração para permitir a projeção sem fio é `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`.*

O tipo de dados também é indicado na documentação do CSP. Os tipos de dados mais comuns são:
- char (cadeia de caracteres)
- int (inteiro)
- bool (booliano)


## Exemplo: Gerenciar as configurações do Surface Hub com o Microsoft Intune

Você pode usar o Microsoft Intune para gerenciar as configurações do Surface Hub. Para as configurações personalizadas, siga as instruções em [Como definir as configurações de dispositivo personalizado no Microsoft Intune](https://docs.microsoft.com/intune/custom-settings-configure). For **Platform**, select **Windows 10 and later**, and in **Profile type**, select **Device restrictions (Windows 10 Team)**.



## Example: Manage Surface Hub settings with Microsoft Endpoint Configuration Manager
Configuration Manager supports managing modern devices that do not require the Configuration Manager client to manage them, including Surface Hub. If you already use Configuration Manager to manage other devices in your organization, you can continue to use the Configuration Manager console as your single location for managing Surface Hubs.

> [!NOTE]
> These instructions are based on the current branch of Configuration Manager.

**To create a configuration item for Surface Hub settings**

1. No espaço de trabalho **Ativos e Conformidade** do console do Configuration Manager, clique em **Visão Geral** > **Configurações de Conformidade** > **Itens de Configuração**.
2. Na guia **Página Inicial**, no grupo **Criar**, clique em **Criar Item de Configuração**.
3. Na página **Geral** do Assistente para Criar Item de Configuração, especifique um nome e uma descrição opcional para o item de configuração.
4. Em **Configurações para dispositivos gerenciados sem o cliente do Configuration Manager**, selecione **Windows 8.1 e Windows 10** e clique em **Avançar**.

    ![exemplo de interface do usuário](images/configmgr-create.png)
5. Na página **Plataformas com Suporte**, expanda **Windows 10** e selecione **Todas as versões do Windows 10 Team e posteriores**. Desmarque as outras plataformas Windows e clique em **Avançar**.

    ![selecionar plataforma](images/configmgr-platform.png)
7. Na página **Configurações do Dispositivo**, em **Grupos de configurações do dispositivo**, selecione **Windows 10 Team**.


8. Na página **Windows 10 Team**, defina as configurações necessárias.

    ![Windows 10 Team](images/configmgr-team.png)
9. Você precisará criar configurações personalizadas para gerenciar as configurações que não estão disponíveis na página Windows 10 Team. Na página **Configurações do Dispositivo**, marque a caixa de seleção **Definir configurações adicionais que não estejam nos grupos de configurações padrão**.

    ![configurações adicionais](images/configmgr-additional.png)
10. Na página **Configurações Adicionais**, clique em **Adicionar**.
11. Na caixa de diálogo **Procurar Configurações**, clique em **Criar Configuração**.
12. Na caixa de diálogo **Criar Configuração**, na guia **Geral**, especifique um nome e uma descrição opcional para a configuração personalizada.
13. Em **Tipo de configuração**, selecione **OMA URI**.
14. Preencha o formulário para criar uma nova configuração e clique em **OK**.

    ![Configuração do OMA URI](images/configmgr-oma-uri.png)
15. Na caixa de diálogo **Procurar Configurações**, em **Configurações disponíveis**, selecione a nova configuração você criou e clique em **Selecionar**.
16. Na caixa de diálogo **Criar Regra**, preencha o formulário para especificar uma regra para a configuração e clique em **OK**.
17. Repita as etapas de 9 a 15 para cada configuração personalizada que você deseja adicionar ao item de configuração.
18. Ao terminar, na caixa de diálogo **Procurar Configurações**, clique em **Fechar**.
19. Conclua o assistente. <br> You can view the new configuration item in the **Configuration Items** node of the **Assets and Compliance** workspace.

For more information, see [Create configuration items for Windows 8.1 and Windows 10 devices managed without the Microsoft Endpoint Configuration Manager client](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client).

## Related topics

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)











