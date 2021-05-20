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
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4308ce1ea8ff382dc15706e68d2d706d0fd33f5f
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576751"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Gerenciar o Surface Hub com um provedor MDM

Surface Hub permite que os administradores de TI gerenciem configurações e políticas usando um provedor de gerenciamento de dispositivo móvel (MDM), como Microsoft Intune. Surface Hub tem um componente de gerenciamento integrado para se comunicar com o servidor de gerenciamento. Não é necessário instalar clientes adicionais no dispositivo.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Registrar Surface Hub gerenciamento de MDM 

Você pode registrar o Surface no Microsoft Intune ou em outro provedor MDM por meio do registro manual ou automático.

### <a name="manual-enrollment"></a>Registro manual

1. Abra o **Configurações** e entre como administrador local. Selecione **Surface Hub**  >  **gerenciamento de dispositivos** e selecione **+Gerenciamento de dispositivos.**
2. Você será solicitado a entrar com a conta a ser usada para seu provedor MDM. Após a autenticação, o dispositivo se registra automaticamente com seu provedor MDM.

> [!TIP]
> Se você estiver usando o Intune e o endereço do servidor não for detectado, **digite manage.microsoft.com**.
   
> [!NOTE]
> O registro do MDM usa os detalhes da conta fornecidos para autenticação. A conta deve ter permissões para registrar um dispositivo Windows, bem como uma licença do Intune (ou as promissões de registro equivalentes configuradas no provedor MDM de terceiros).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Registro Automático — afiliada ao Azure AD

Durante o processo de instalação inicial, ao afiliar o Surface Hub com um locatário Azure Active Directory (AD) que tenha o registro automático do Intune habilitado, o dispositivo se registrará automaticamente no Intune. Para saber mais, consulte os métodos de registro do [Intune para Windows dispositivos](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). A afiliação do Azure AD e o registro automático do Intune são necessários para que o Surface Hub seja um “dispositivo compatível” no Intune. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Gerenciar Surface Hub Windows 10 Team configurações com o Intune

O bloco de construção base do gerenciamento de configurações de política no Intune e em outros provedores MDM é o protocolo Open Mobile Alliance-Device Management (OMA-DM) baseado em XML. Windows 10 implementa o OMA-DM XML por meio de um dos muitos provedores de serviços de Configuração (CSPs) disponíveis com nomes como CSP AccountManagement, CSP DeviceStatus, WiFi-CSP e assim por diante. Para uma lista completa, consulte [CSPs com suporte em Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

Microsoft Intune e outros provedores de MDM usam CSPs para fornecer uma interface do usuário que permite configurar configurações de política em perfis de configuração. O Intune usa o CSP do Surface Hub para seu perfil integrado — restrições de **dispositivo (Windows 10 Team)** — permite que você configure configurações básicas, como impedir que o Surface Hub "acorde" sempre que alguém se mover por perto dentro de seu intervalo de proximidade. Para gerenciar configurações e recursos do Hub fora do perfil integrado do Intune, você precisará usar um perfil personalizado, conforme [mostrado abaixo](#create-custom-configuration-profile). 

Para resumir, as opções para configurar e gerenciar configurações de política no Intune incluem o seguinte: 
 
- **Criar um perfil de restrição de dispositivo.** Use o perfil integrado do Intune e configure as configurações diretamente na interface do usuário do Intune. Consulte [Criar perfil de restrição de dispositivo](#create-device-restriction-profile).
- **Criar um perfil de configuração de dispositivo.**  Selecione um modelo focado em um recurso ou tecnologia específico, como o Microsoft Defender ou certificados de segurança. Consulte [Criar perfil de configuração do dispositivo](#create-device-configuration-profile).
- **Criar um perfil de configuração personalizado.**  Estenda seu escopo de gerenciamento usando um OMA Uniform Resource Identifier (OMA URI) de qualquer um dos [CSPs suportados no Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). Consulte [Criar perfil de configuração personalizado](#create-custom-configuration-profile).

> [!NOTE]
> Os perfis devem ser atribuídos aos grupos de dispositivos que contêm os dispositivos Surface Hub inscritos.

## <a name="create-device-restriction-profile"></a>Criar perfil de restrição de dispositivo

1. Entre no centro [**de administração Microsoft Endpoint Manager,**](https://endpoint.microsoft.com/)selecione **Perfis**de  >  **Configuração de**  >  **+** **Dispositivos Criar perfil**.
2. Em **Plataforma,** selecione **Windows 10 e posterior** >
3. Em ****Tipo de**perfil, selecione** **Modelos** e selecione **Restrições de dispositivo (Windows 10 Team)**
4. Selecione **Criar**, adicionar um nome e selecione **Next.**
6. Agora você pode navegar e escolher entre as configurações de restrição de dispositivo predefinidas para Surface Hub nas seguintes categorias: aplicativos e experiência, percepções operacionais do Azure, manutenção, sessão e projeção sem fio. O exemplo mostrado na figura a seguir especifica uma janela de manutenção de 4 horas e um tempo de tempo de 15 minutos para tela, sono e retomada de sessão.

     ![Configurar Surface Hub configurações com o perfil de restrição de dispositivo do Intune](images/sh-device-restrictions.png)

Para obter mais informações sobre como criar e gerenciar perfis, consulte [Restrict devices features using policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
Para obter mais informações sobre como gerenciar Surface Hub recursos e configurações, [consulte Surface Hub Windows 10 Team restrições de dispositivo em Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Criar perfil de configuração do dispositivo

1. Entre no centro [**de administração Microsoft Endpoint Manager,**](https://endpoint.microsoft.com/)selecione **Perfis**de  >  **Configuração de**  >  **Dispositivos + Criar perfil**.
2. Em **Plataforma,** selecione **Windows 10 e posterior** >
3. Em **Tipo de perfil,** selecione **Modelos** e escolha entre os seguintes modelos com suporte em Surface Hub:

    - Restrições de dispositivo (Windows 10 Team), conforme descrito na [seção anterior](#create-device-restriction-profile).
    - Microsoft Defender para Ponto de Extremidade (Windows 10 Desktop)
    - Certificado PKCS
    - Certificado importado PKCS
    - Certificado SCEP
    - Certificado confiável

## <a name="create-custom-configuration-profile"></a>Criar perfil de configuração personalizado

Você pode estender o [](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) escopo de gerenciamento criando um perfil personalizado usando um URI OMA de qualquer um dos [CSPs](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)com suporte em Microsoft Surface Hub . Cada configuração em um CSP tem um OMA-URI correspondente que você pode definir usando perfis de configuração personalizados no Intune. Para obter detalhes sobre os CSPs com suporte Surface Hub, você pode fazer referência aos seguintes recursos: 

- [Referência de provedor de serviços de configuração](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [CSPs de políticas suportados pelo Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [CSP SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> O gerenciamento da conta de dispositivo usando configurações do [CSP surfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) não é possível no momento com o Intune e requer o uso de um provedor MDM de terceiros.

Para implementar configurações de política baseadas em CSP, comece gerando um URI OMA e adicione-o a um perfil de configuração personalizado no Intune.

### <a name="generate-oma-uri-for-target-setting"></a>Gerar URI OMA para a configuração de destino
 
Para gerar o URI OMA para qualquer configuração:

1. Na [documentação do CSP,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)identifique o nó raiz do CSP. Geralmente, isso se parece **com ./Vendor/MSFT/ <name of CSP> **. 
    - **Exemplo:** O nó raiz do [CSP surfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) **é ./Vendor/MSFT/SurfaceHub**.
2. Identifique o caminho do nó da configuração que você quer usar. 
    - **Exemplo:** O caminho do nó para a configuração para habilitar a projeção sem fio é **InBoxApps/WirelessProjection/Enabled**.
3. Acrescente o caminho do nó ao nó raiz para gerar o OMA URI. 
    - **Exemplo:** O URI OMA da configuração para habilitar a projeção sem fio é **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. O tipo de dados também é indicado na documentação do CSP. Os tipos de dados mais comuns são:
    - char (cadeia de caracteres)
    - int (inteiro)
    - bool (booliano)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>Adicionar URI OMA ao perfil de configuração personalizado

1. Em Endpoint Manager, selecione **Perfis**de  >  **Configuração de**  >  **Dispositivos Criar perfil**.
2. Em Plataforma, **selecione Windows 10 e posterior.** Em Perfil, selecione **Personalizado**e, em seguida, selecione **Criar.**
3. Adicione um nome e uma descrição opcional e selecione **Next.**
4. Em **Configuração configurações**  >  **OMA-URI Configurações**, selecione **Adicionar**.

  
## <a name="manage-specific-surface-hub-features"></a>Gerenciar recursos Surface Hub específicos

Esta seção destaca informações sobre recursos que você pode gerenciar por meio do Intune ou outro provedor MDM. Isso inclui:

- [Qualidade do Serviço (QoS)](#quality-of-service-settings)
- [Microsoft Teams e Skype for Business](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>Configurações de qualidade do serviço

Para garantir a qualidade ideal de vídeo e áudio no Surface Hub, adicione as seguintes configurações de QoS ao dispositivo. 

| Nome | Descrição | OMA-URI | Tipo | Valor |
|:------ |:------------- |:--------- |:------ |:------- |
|**Portas de áudio**| Intervalo de porta de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | String  | 3478-3479 |
|**DSCP de Áudio**| Marcação de portas de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Inteiro | 46 |
|**Porta de vídeo**| Intervalo de porta de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | String  | 3480 |
|**DSCP de vídeo**| Marcação de portas de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Inteiro | 34 |
|**Porta de Compartilhamento**| Intervalo de Porta de Compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | String  | 3481 |
|**Compartilhamento de DSCP**| Marcação de portas de compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | Inteiro | 18 |
|**Portas de áudio P2P**| Intervalo de porta de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | String  | 50000-50019 |
|**DSCP de Áudio P2P**| Marcação de portas de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Inteiro | 46 |
|**Portas de vídeo P2P**| Intervalo de porta de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | String  | 50020-50039 |
|**DSCP de vídeo P2P**| Marcação de portas de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Inteiro | 34 |
|**Portas de compartilhamento P2P**| Intervalo de Porta de Compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | String  | 50040-50059 |
|**DSCP de compartilhamento P2P**| Marcação de portas de compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | Inteiro | 18 |


#### <a name="skype-for-business-qos-settings"></a>Configurações da QoS do Skype for Business

| Nome                 | Descrição           | OMA-URI                                                                    | Tipo    | Valor                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Portas de áudio          | Intervalo de porta de áudio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | String  | 50000-50019                    |
| DSCP de Áudio           | Marcação de portas de áudio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | Inteiro | 46                             |
| Origem da mídia de áudio   | Nome do aplicativo Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Portas de vídeo          | Intervalo de porta de vídeo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | String  | 50020-50039                    |
| DSCP de vídeo           | Marcação de portas de vídeo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | Inteiro | 34                             |
| Origem de mídia de vídeo   | Nome do aplicativo Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Compartilhamento de portas        | Intervalo de Porta de Compartilhamento    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | String  | 50040-50059                    |
| Compartilhamento de DSCP         | Marcação de portas de compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | Inteiro | 18                             |
| Fonte de mídia de compartilhamento | Nome do aplicativo Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Ambas as tabelas mostram intervalos de porta padrão. Os administradores podem alterar os intervalos de porta no painel de controle do Skype for Business e do Teams.

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams e Skype for Business configurações

Você pode criar um perfil de configuração personalizado para gerenciar Teams reuniões coordenadas, participação de proximidade e outros recursos. Para saber mais, consulte [Manage Microsoft Teams configuration on Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config).

#### <a name="changing-default-business-communications-platform"></a>Alterar a plataforma de comunicações comerciais padrão

A plataforma de comunicações comerciais padrão Surface Hub varia dependendo de como você instala o Windows 10 Team 2020 Update (também conhecido como Windows 10 20H2). Se você re-Surface Hub para Windows 10 20H2, o Microsoft Teams será definido como padrão, com Skype for Business funcionalidade disponível (Modo 1). Se você atualizar seu Hub de uma versão anterior do sistema operacional, o Skype for Business permanecerá como padrão, com Teams funcionalidade disponível (Modo 0), a menos que você já tenha configurado o Teams como seu padrão. 

Para alterar a instalação padrão, use um [perfil personalizado](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) definindo o modo Teams App da seguinte forma:  

- Modo 0 — Skype for Business com a funcionalidade do Microsoft Teams para reuniões agendadas.
- Modo 1 — Microsoft Teams com a funcionalidade do Skype for Business para reuniões agendadas.
- Modo 2 — Somente Microsoft Teams.

| Nome | Descrição | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**ID do aplicativo Teams**|Nome do aplicativo|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo do aplicativo Teams**|Modo do Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Inteiro| 0, 1 ou 2|










