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
ms.date: 03/03/2021
ms.localizationpriority: medium
ms.openlocfilehash: d09a95d25b4f4ae86d64acd7d7f16f004f991ce3
ms.sourcegitcommit: 5c904229a0257297be7f724c264e484d2c4b5168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387493"
---
# <a name="manage-settings-with-an-mdm-provider-surface-hub"></a>Gerenciar configurações com um provedor de MDM (Surface Hub)

O Surface Hub e outros dispositivos Windows 10 permitem que os administradores de TI gerenciem configurações e políticas usando um provedor de MDM (gerenciamento de dispositivo móvel). Um componente de gerenciamento interno se comunica com o servidor de gerenciamento, portanto, não é necessário instalar clientes adicionais no dispositivo. Para obter mais informações, consulte [Gerenciamento de dispositivo móvel Windows 10](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx).

O Surface Hub foi validado com os provedores de MDM de primeira parte da Microsoft:
- Microsoft Intune autônomo
- MDM local com o Microsoft Endpoint Configuration Manager

Você também pode gerenciar Surface Hubs usando qualquer provedor de MDM de terceiros que possa se comunicar com o Windows 10 usando o protocolo MDM.

## <a name="enroll-a-surface-hub-into-mdm"></a><a href="" id="enroll-into-mdm"></a>Registrar um Surface Hub em MDM
Você pode registrar seus Surface Hubs usando registro em massa, manual ou automático.

### <a name="bulk-enrollment"></a>Registro em massa
**Para configurar o registro em massa**
- O Surface Hub dá suporte para o [CSP de provisionamento](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) para registro em massa no MDM. Para obter mais informações, consulte [Registro em massa no Windows 10](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx).<br>
--OU--
- Se você tiver uma infraestrutura local do Microsoft Endpoint Configuration Manager, consulte Como registrar em massa dispositivos com o Gerenciamento de Dispositivos Móveis local no [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm).

### <a name="manual-enrollment"></a>Registro manual
**Para configurar o registro manual**
1. No Surface Hub, abra **Configurações**.
2. Digite as credenciais de administrador de dispositivo quando solicitado.
3. Selecione **Este dispositivo**e navegue até **Gerenciamento de dispositivos**.
4. Em **Gerenciamento de dispositivos**, selecione **+ Gerenciamento de dispositivos**.
5. Siga as instruções na caixa de diálogo para se conectar ao seu provedor de MDM.

### <a name="automatic-enrollment-via-azure-active-directory-join"></a>Registro automático por meio da junção do Azure Active Directory

O Surface Hub agora dá suporte à capacidade de registrar-se automaticamente no Intune, juntando-se ao dispositivo ao Azure Active Directory. 

A primeira etapa é configurar o registro automático do MDM. Consulte [Habilitar o registro automático do Windows 10.](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)

Em seguida, quando os dispositivos são [configurados](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page) durante a primeira executar, escolha a opção para ingressar no Azure Active Directory, consulte Configurar administradores para esta página de dispositivo

## <a name="manage-surface-hub-settings-with-mdm"></a>Gerenciar as configurações do Surface Hub com o MDM

Você pode usar o MDM para gerenciar algumas [configurações do CSP do Surface Hub](#supported-surface-hub-csp-settings) e algumas [configurações do Windows 10](#supported-windows-10-settings). Dependendo do provedor de MDM usado, você pode definir essas configurações usando uma interface do usuário interna ou implantando SyncML personalizado. O Microsoft Intune e o Microsoft Endpoint Configuration Manager oferecem experiências internas para ajudar a criar modelos de política para o Surface Hub. Consulte a documentação de seu provedor de MDM para saber como criar e implantar SyncML.

### <a name="supported-surface-hub-csp-settings"></a>Configurações do CSP do Surface Hub com suporte

Você pode definir as configurações do Surface Hub na tabela a seguir usando o MDM. A tabela identifica se a configuração tem suporte com o Microsoft Intune, o Microsoft Endpoint Configuration Manager ou o SyncML.

Para obter mais informações, consulte [Provedor de serviços de configuração SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     Configuração                                      |                                                    Nó no CSP SurfaceHub                                                    |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                Horas de manutenção                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       Sim                        |                       Sim                       |             Sim             |
|              Ligar a tela automaticamente usando sensores de movimento               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       Sim                        |                       Sim                       |             Sim             |
|                      Exigir um PIN para projeção sem fio                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       Sim                        |                       Sim                       |             Sim             |
|                            Habilitar projeção sem fio                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                 Canal Miracast a ser usado para projeção sem fio                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|              Conectar-se ao seu espaço de trabalho do Operations Management Suite               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                         Imagem de fundo da tela de boas-vindas                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       Sim                        | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Informações de reunião exibidas na tela de boas-vindas                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       Sim                        | Sim.<br> [Use uma configuração personalizada.] (#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager |             Sim             |
|                      Nome amigável para a projeção sem fio                       |                                                     Properties/FriendlyName                                                      | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                   Conta de dispositivo                                                 | DeviceAccount/*`<name_of_policy>`* <br> Consulte [CSP SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). |                        Não                        |                       Não                        |             Sim             |
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

### <a name="supported-windows-10-settings"></a>Configurações do Windows 10 com suporte

Além das configurações específicas do Surface Hub, há inúmeras configurações comuns a todos os dispositivos Windows 10. Essas configurações são definidas na [Referência de provedor de serviços de configuração](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference). 

As tabelas a seguir incluem informações sobre as configurações do Windows 10 que foram validadas com o Surface Hub. Há uma tabela com configurações para estas áreas: segurança, navegador, Atualizações do Windows, Windows Defender, reinicialização remota, certificados e logs. Cada tabela identifica se a configuração tem suporte com o Microsoft Intune, o Microsoft Endpoint Configuration Manager ou o SyncML.

#### <a name="security-settings"></a>Configurações de segurança

|      Configuração       |                                            Detalhes                                             |                                                                          Referência de CSP                                                                           |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Permitir Bluetooth   |                      Mantenha isso habilitado para dar suporte para periféricos Bluetooth.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
| Políticas de Bluetooth | Use para definir o nome do dispositivo Bluetooth e bloquear publicidade, descoberta e emparelhamento automático. |                     Bluetooth/*`<name of policy>`* <br> Consulte [CSP da Política](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|    Permitir câmera    |                           Mantenha isso habilitado para o Skype for Business.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|   Permitir localização   |                        Mantenha isso habilitado para dar suporte a aplicativos, como o Mapas.                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   Sim. <br> .                    | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|  Permitir telemetria   |                    Mantenha isso habilitado para ajudar a Microsoft a melhorar o Surface Hub.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    Sim. <br>                     | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|  Permitir Unidades USB  |                     Mantenha isso habilitado para dar suporte a unidades USB no Surface Hub                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows. 

#### <a name="browser-settings"></a>Configurações do navegador

|                          Configuração                          |                                                                        Detalhes                                                                        |                                                                             Referência de CSP                                                                              |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         Homepages                         |                                               Use para configurar as homepages padrão no Microsoft Edge.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                       Permitir cookies                       |                    O Surface Hub exclui os cookies automaticamente no final de uma sessão. Use isso para bloquear cookies em uma sessão.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                   Permitir ferramentas de desenvolvedor                   |                                                   Use para evitar que os usuários utilizem as Ferramentas de Desenvolvedor F12.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                    Permitir não rastrear                     |                                                          Use para habilitar cabeçalhos Não Rastrear.                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                       Permitir pop-ups                       |                                                         Use para bloquear as janelas pop-up do navegador.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                 Permitir sugestões de pesquisa                  |                                                  Use para bloquear sugestões de pesquisa na barra de endereços.                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|                     Permitir Windows Defender SmartScreen                     |                                                       Mantenha isso habilitado para ativar o Windows Defender SmartScreen.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
| Impedir que você ignore Windows Defender avisos do SmartScreen para sites |     Para segurança extra, use para impedir que os usuários ignorem Windows Defender avisos do SmartScreen e os bloqueiem de acessar sites potencialmente mal-intencionados.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|  Impedir que você ignore Windows Defender avisos do SmartScreen para arquivos   | Para segurança extra, use para impedir que os usuários ignorem Windows Defender avisos do SmartScreen e os bloqueiem de baixar arquivos não verificados do Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="windows-update-settings"></a>Configurações do Windows Update

|                      Configuração                      |                                                                                                           Detalhes                                                                                                            |                                                                    Referência de CSP                                                                    |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Usar Branch Atual ou Branch Atual para Negócios |                                                       Use para configurar o Windows Update for Business – veja [Atualizações do Windows](manage-windows-updates-for-surface-hub.md).                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Adiar atualizações de recursos               |                                                                                                          Veja acima.                                                                                                          | [Update/DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Adiar atualizações de qualidade               |                                                                                                          Veja acima.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Pausar atualizações de recursos               |                                                                                                          Veja acima.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Pausar atualizações de qualidade               |                                                                                                          Veja acima.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|           Configurar dispositivo para usar o WSUS            |                                            Use para conectar o Surface Hub ao WSUS em vez do Windows Update – veja [Atualizações do Windows](manage-windows-updates-for-surface-hub.md).                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|               Otimização de entrega               | Use o compartilhamento de conteúdo ponto a ponto para reduzir problemas de largura de banda durante atualizações. Consulte [Configurar a Otimização de Entrega para o Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization) para obter detalhes. |         DeliveryOptimization/*`<name of policy>`* <br> Consulte [CSP da Política](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="windows-defender-settings"></a>Configurações do Windows Defender

|      Configuração      |                                              Detalhes                                               |                                                     Referência de CSP                                                      |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Políticas do Defender |            Use para definir várias configurações do Defender, inclusive uma hora de verificação agendada.            | Defender/*`<name of policy>`* <br> Consulte [CSP da Política](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
|  Status do Defender  | Use para iniciar uma verificação do Defender, forçar uma atualização de inteligência de segurança, consultar quaisquer ameaças detectadas. |                   [CSP Defender](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Sim                        |                       Sim                       |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="remote-reboot"></a>Reinicialização remota

|                       Configuração                        |                                                          Detalhes                                                          |                                                             Referência de CSP                                                             |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Reiniciar o dispositivo imediatamente             | Use em conjunto com o Monitor do Azure para minimizar os custos de suporte – consulte [Monitor your Microsoft Surface Hub](monitor-surface-hub.md). |        ./Vendor/MSFT/Reboot/RebootNow <br> Consulte [CSP de reinicialização](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       Sim                        |                       Não                        |             Sim             |
|    Reinicie o dispositivo em data e hora agendadas    |                                                        Consulte acima.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> Consulte [CSP de reinicialização](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |
| Reiniciar o dispositivo diariamente em data e hora agendadas |                                                        Consulte acima.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> Consulte [CSP de reinicialização](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="install-certificates"></a>Instalar certificados

|             Configuração             |                           Detalhes                            |                                           Referência de CSP                                            |                                                         Tem suporte com<br>Intune?                                                          |                                                                  Tem suporte com<br>Configuration Manager?                                                                  | Tem suporte com<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Instalar certificados CA confiáveis | Use para implantar certificados CA raiz e intermediários confiáveis. | [CSP RootCATrustedCertificates](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | Sim. <br> Consulte [Configurar perfis de certificado do Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | Sim. <br> Consulte [Como criar perfis de certificado no Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles). |             Sim             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="collect-logs"></a>Coletar registros

|     Configuração      |                      Detalhes                       |                                     Referência de CSP                                      | Tem suporte com<br>Intune? | Tem suporte com<br>Configuration Manager? | Tem suporte com<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| Coletar logs do ETW | Use remotamente para coletar logs do ETW do Surface Hub. | [CSP DiagnosticLog](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            Não             |                    Não                    |             Sim             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="set-network-quality-of-service-qos-policy"></a>Definir qualidade de rede de política de serviço (QoS)

|        Configuração         |                                                            Detalhes                                                             |                                                    Referência de CSP                                                     |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Definir política de QoS de rede | Use para definir uma política de QoS para executar um conjunto de ações no tráfego de rede. Isso é útil para priorizar os pacotes de rede do Skype. | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="set-network-proxy"></a>Definir proxy de rede

|      Configuração      |                               Detalhes                               |                                                Referência de CSP                                                 |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Definir proxy de rede | Use para configurar um servidor proxy para conexões Wi-Fi e Ethernet. | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

#### <a name="configure-start-menu"></a>Configurar o menu Iniciar

|       Configuração        |                                                                       Detalhes                                                                        |                                                        Referência de CSP                                                         |            Tem suporte com<br>Intune?             |    Tem suporte com<br>Configuration Manager?     | Tem suporte com<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Configurar o menu Iniciar | Use para configurar quais apps serão exibidos no menu Iniciar. Para obter mais informações, consulte [Configurar o menu Iniciar do Surface Hub](surface-hub-start-menu.md) | [CSP de Política: Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | Sim <br> [Use uma política personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sim.<br> [Use uma configuração personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sim             |

\*As configurações com suporte com o SyncML também podem ser definidas em um pacote de provisionamento do Designer de Configuração do Windows.

### <a name="generate-oma-uris-for-settings"></a>Gerar OMA URIs para configurações 
Você precisa usar o URI OMA de uma configuração para criar uma política personalizada no Intune ou uma configuração personalizada no Microsoft Endpoint Configuration Manager.

**Para gerar o OMA URI para qualquer configuração na documentação do CSP**
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


## <a name="example-manage-surface-hub-settings-with-microsoft-intune"></a>Exemplo: Gerenciar as configurações do Surface Hub com o Microsoft Intune

Você pode usar o Microsoft Intune para gerenciar as configurações do Surface Hub. Para as configurações personalizadas, siga as instruções em [Como definir as configurações de dispositivo personalizado no Microsoft Intune](https://docs.microsoft.com/intune/custom-settings-configure). Para **Plataforma**, selecione **Windows 10 e posteriores** e, em **Tipo de perfil**, selecione **Restrições de dispositivo (Windows 10 Team)**.



## <a name="example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager"></a>Exemplo: Gerenciar configurações do Surface Hub com o Microsoft Endpoint Configuration Manager
O Configuration Manager dá suporte ao gerenciamento de dispositivos modernos que não exigem que o cliente do Configuration Manager os gerencie, incluindo o Surface Hub. Se você já usar o Configuration Manager para gerenciar outros dispositivos em sua organização, poderá continuar a usar o console do Configuration Manager como seu único local para gerenciar Surface Hubs.

> [!NOTE]
> Essas instruções se baseiam no branch atual do Configuration Manager.

**Para criar um item de configuração para configurações do Surface Hub**

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
19. Conclua o assistente. <br> Você pode ver o novo item de configuração no nó **Itens de Configuração** do espaço de trabalho **Ativos e Conformidade**.

Para obter mais informações, consulte [Create configuration items for Windows 8.1 and Windows 10 devices managed without the Microsoft Endpoint Configuration Manager client](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)











