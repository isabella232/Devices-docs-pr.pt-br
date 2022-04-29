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
ms.openlocfilehash: e126799fe023d97468e58c01b003ce4b605f2db7
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497784"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Gerenciar o Surface Hub com um provedor MDM

Surface Hub permite que os administradores de TI gerenciem configurações e políticas usando um provedor de MDM (gerenciamento de dispositivo móvel), como Microsoft Intune. Surface Hub tem um componente de gerenciamento interno para se comunicar com o servidor de gerenciamento. Não é necessário instalar clientes adicionais no dispositivo.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Registrando Surface Hub gerenciamento de MDM 

Você pode registrar o Surface no Microsoft Intune ou em outro provedor de MDM por meio do registro manual ou automático.

### <a name="manual-enrollment"></a>Registro manual

1. Abra o **Configurações** aplicativo e entre como administrador local. Selecione **Surface Hub** >  **Degerenciamento de** dispositivo e, em seguida, **selecione +Gerenciamento de dispositivos**.
2. Você será solicitado a entrar com a conta a ser usada para seu provedor de MDM. Após a autenticação, o dispositivo é registrado automaticamente no provedor de MDM.

> [!TIP]
> Se você estiver usando Intune e o endereço do servidor não for detectado, **insira manage.microsoft.com**.
   
> [!NOTE]
> O registro do MDM usa os detalhes da conta fornecidos para autenticação. A conta deve ter permissões para registrar um dispositivo Windows, bem como uma licença do Intune (ou as promissões de registro equivalentes configuradas em seu provedor de MDM de terceiros).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Registro Automático — Azure AD afiliado

Durante o processo de configuração inicial, ao afiliar o Surface Hub com um locatário do Azure Active Directory (AD) que tenha o registro automático Intune habilitado, o dispositivo será registrado automaticamente no Intune. Para saber mais, consulte Intune [de registro para Windows dispositivos](/intune/enrollment/windows-enrollment-methods). A afiliação do Azure AD e o registro automático do Intune são necessários para que o Surface Hub seja um “dispositivo compatível” no Intune. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Gerenciar Surface Hub Windows 10 Team configurações com Intune

O bloco de construção básico do gerenciamento de configurações de política no Intune e em outros provedores de MDM é o protocolo OMA-DM (Open Mobile Alliance-Device Management) baseado em XML. Windows implementa o XML OMA-DM por meio de um dos muitos CSPs (provedores de serviços de configuração) disponíveis com nomes como CSP accountManagement, CSP deviceStatus, WiFi-CSP e assim por diante. Para obter uma lista completa, consulte [os CSPs com suporte Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

Microsoft Intune e outros provedores de MDM usam CSPs para fornecer uma interface do usuário que permite definir as configurações de política nos perfis de configuração. Intune usa o CSP do Surface Hub para seu perfil interno – restrições de dispositivo **(Windows 10 Team)** – permitindo que você defina configurações básicas, como impedir que o Surface Hub "ativação" sempre que alguém se mover por perto dentro de seu intervalo de proximidade. Para gerenciar as configurações e recursos do Hub Intune o perfil interno do Intune, você precisará usar um perfil personalizado, conforme [mostrado abaixo](#create-custom-configuration-profile). 

Para resumir, as opções para definir e gerenciar as configurações de política Intune incluem o seguinte: 
 
- **Criar um perfil de restrição de dispositivo.** Use Intune perfil interno e defina as configurações diretamente na Intune interface do usuário. Consulte [Criar perfil de restrição de dispositivo](#create-device-restriction-profile).
- **Crie um perfil de configuração de dispositivo.**  Selecione um modelo focado em um recurso ou tecnologia específico, como o Microsoft Defender ou certificados de segurança. Consulte [Criar perfil de configuração do dispositivo](#create-device-configuration-profile).
- **Crie um perfil de configuração personalizado.**  Estenda seu escopo de gerenciamento usando um URI de OMA (Uniform Resource Identifier) do OMA de qualquer um dos [CSPs](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) com suporte Microsoft Surface Hub. Consulte [Criar perfil de configuração personalizado](#create-custom-configuration-profile).

> [!NOTE]
> Os perfis devem ser atribuídos a grupos de dispositivos que contêm os dispositivos Surface Hub registrados.

## <a name="create-device-restriction-profile"></a>Criar perfil de restrição de dispositivo

1. Entre no Microsoft Endpoint Manager [**de administração**](https://endpoint.microsoft.com/), selecione **Perfis** **DevicesConfiguration** >  **Criar** > **+** perfil.
2. Em **Plataforma**, selecione **Windows 10 e posterior** >
3. Em ****Tipo de perfil **,** selecione **Modelos** e, em seguida, selecione **Restrições de dispositivo (Windows 10 Team)**
4. Selecione **Criar**, adicione um nome e, em seguida, **selecione Avançar.**
6. Agora você pode procurar e escolher entre as configurações predefinidas de restrição de dispositivo para Surface Hub entre as seguintes categorias: aplicativos e experiência, insights operacionais do Azure, manutenção, sessão e projeção sem fio. O exemplo mostrado na figura a seguir especifica uma janela de manutenção de 4 horas e um tempo limite de 15 minutos para tela, suspensão e retomada de sessão.

     ![Defina Surface Hub configurações com o perfil Intune restrição de dispositivo.](images/sh-device-restrictions.png)

Para obter mais informações sobre como criar e gerenciar perfis, consulte [Restringir recursos de dispositivos usando a política Microsoft Intune](/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
Para obter mais informações sobre como gerenciar Surface Hub recursos e configurações, consulte Windows 10 Team configurações para permitir ou restringir recursos no Surface Hub [usando Intune](/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Criar perfil de configuração do dispositivo

1. Entre no Microsoft Endpoint Manager [**de administração**](https://endpoint.microsoft.com/), selecione **Perfis** **DevicesConfiguration** >  > **+ Criar perfil**.
2. Em **Plataforma**, selecione **Windows 10 e posterior** >
3. Em **Tipo de** perfil, **selecione Modelos** e escolha um dos seguintes modelos com suporte no Surface Hub:

    - Restrições de dispositivo (Windows 10 Team), conforme descrito na [seção anterior](#create-device-restriction-profile).
    - Microsoft Defender para Ponto de Extremidade (Windows 10 Desktop)
    - Certificado PKCS
    - Certificado PKCS importado
    - Certificado SCEP
    - Certificado confiável

## <a name="create-custom-configuration-profile"></a>Criar perfil de configuração personalizada

Você pode estender o escopo de gerenciamento criando [](/mem/intune/configuration/custom-settings-configure) um perfil personalizado usando um URI OMA de qualquer [um dos CSPs com suporte no Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). Cada configuração em um CSP tem um OMA-URI correspondente que você pode definir usando perfis de configuração personalizados em Intune. Para obter detalhes sobre os CSPs compatíveis com Surface Hub, você pode referenciar os seguintes recursos: 

- [Referência de provedor de serviços de configuração](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [CSPs de políticas suportados pelo Microsoft Surface Hub](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [CSP SurfaceHub](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> Atualmente, o gerenciamento da conta de dispositivo usando configurações do [CSP do SurfaceHub](/windows/client-management/mdm/surfacehub-csp) não é possível com o Intune e requer o uso de um provedor de MDM de terceiros.

Para implementar configurações de política baseadas em CSP, comece gerando um URI OMA e, em seguida, adicione-o a um perfil de configuração personalizado Intune.

### <a name="generate-oma-uri-for-target-setting"></a>Gerar o URI do OMA para a configuração de destino
 
Para gerar o URI do OMA para qualquer configuração:

1. Na [documentação do CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport), identifique o nó raiz do CSP. Geralmente, isso se parece **com ./Vendor/MSFT/NameOfCSP**. 
    - **Exemplo:** O nó raiz do [CSP do SurfaceHub](/windows/client-management/mdm/surfacehub-csp) **é ./Vendor/MSFT/SurfaceHub**.
2. Identifique o caminho do nó da configuração que você quer usar. 
    - **Exemplo:** O caminho do nó para a configuração para habilitar a projeção sem fio é **InBoxApps/WirelessProjection/Enabled**.
3. Acrescente o caminho do nó ao nó raiz para gerar o OMA URI. 
    - **Exemplo:** O URI do OMA para a configuração para habilitar a projeção sem fio **é ./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. O tipo de dados também é indicado na documentação do CSP. Os tipos de dados mais comuns são:
    - char (cadeia de caracteres)
    - int (inteiro)
    - bool (booliano)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>Adicionar o URI do OMA ao perfil de configuração personalizado

1. Em Endpoint Manager, selecione **DevicesConfiguration****** >  **profilesCreate** >  profile.
2. Em Plataforma, selecione **Windows 10 e posterior.** Em Perfil, selecione **Personalizar** e, em seguida, **selecione Criar.**
3. Adicione um nome e uma descrição opcional e selecione **Avançar.**
4. Em **Configuração de configuração** >  **de Configurações URI**, selecione **Adicionar**.

  
## <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams e Skype for Business configurações

Esta seção realça Teams e Skype for Business configurações que você pode gerenciar por meio Intune ou outro provedor de MDM. Isso inclui:

- [QoS (Qualidade de Serviço)](#quality-of-service-settings)
- [Gerenciar Teams recursos específicos](#manage-teams-specific-features)

### <a name="quality-of-service-settings"></a>Configurações de qualidade de serviço

Para garantir a qualidade ideal de vídeo e áudio Surface Hub, adicione as seguintes configurações de QoS ao dispositivo. 

| Nome                 | Descrição           | OMA-URI                                                                 | Tipo    | Valor                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| Portas de áudio          | Intervalo de porta de áudio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortMatchCondition    | String  | 50000-50019                    |
| DSCP de Áudio           | Marcação de portas de áudio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | Inteiro | 46                             |
| Portas de vídeo          | Intervalo de porta de vídeo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortMatchCondition    | String  | 50020-50039                    |
| DSCP de vídeo           | Marcação de portas de vídeo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | Inteiro | 34                             |
| Compartilhamento de portas        | Intervalo de portas de compartilhamento    | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/SourcePortMatchCondition  | String  | 50040-50059                    |
| Compartilhamento de DSCP         | Marcação de portas de compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/DSCPAction                | Inteiro | 18                             |

> [!NOTE]
> A tabela mostra intervalos de portas padrão. Os administradores podem alterar os intervalos de porta no painel de controle do Skype for Business e do Teams.

### <a name="manage-teams-specific-features"></a>Gerenciar Teams recursos específicos

Você pode criar um perfil de configuração personalizado para gerenciar Teams reuniões coordenadas, ingresso por proximidade e outros recursos. Para saber mais, confira [Gerenciar Microsoft Teams configuração no Surface Hub](/microsoftteams/rooms/surface-hub-manage-config).

### <a name="changing-default-app-for-meetings--calls"></a>Alterando o aplicativo padrão para reuniões & chamadas

O aplicativo padrão para reuniões & chamadas no Surface Hub varia dependendo de como você instala o Windows 10 Team 2020 Update (também conhecido como Windows 10 20H2 Team Edition). Se você re-image um Surface Hub para Windows 10 20H2, Microsoft Teams será definido como o padrão, com Skype for Business não disponível (Modo 1). Se você atualizar o Hub de uma versão anterior do sistema operacional, o Skype for Business permanecerá como o padrão, com a funcionalidade Teams disponível (Modo 0), a menos que você já tenha configurado o Teams como padrão. 

Para alterar a instalação padrão, use um [perfil personalizado](/mem/intune/configuration/custom-settings-configure) para definir o Teams Modo de Reunião da seguinte maneira:  

- Modo 0 — Skype for Business com a funcionalidade do Microsoft Teams para reuniões agendadas.
- Modo 1 — Microsoft Teams somente.

| Nome | Descrição | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**ID do aplicativo Teams**|Nome do aplicativo|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo do aplicativo Teams**|Modo do Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Inteiro| 0 ou 1|


