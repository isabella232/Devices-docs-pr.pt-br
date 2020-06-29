---
title: Gerenciar o Surface Hub 2S com o Intune
description: Aprenda a atualizar e gerenciar o Surface Hub 2S usando o Intune.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1d1b836c18a41982497bb28c57f379408c04f8a5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831093"
---
# Gerenciar o Surface Hub 2S com o Intune

## Registrar o Surface Hub 2S com o Intune

O Surface Hub 2S permite que os administradores de TI gerenciem as configurações e as políticas usando um provedor de MDM (gerenciamento de dispositivo móvel). O Surface Hub 2S possui um componente de gerenciamento interno que se comunica com o servidor de gerenciamento, portanto, não é necessário instalar clientes adicionais no dispositivo.

### Registro manual

1. Entre como administrador local no Surface Hub 2S e abra o aplicativo **Configurações**. Selecione **Surface Hub** > **Gerenciamento de dispositivo** e, em seguida, selecione **+** para adicionar.
2. Após a autenticação, o dispositivo será registrado automaticamente com o Intune.

   ![Registrar o Surface Hub 2S com o Intune](images/sh2-set-intune1.png)<br>

### Registro automático - afiliado do Azure Active Directory 

Durante o processo de instalação inicial, ao afiliar um Surface Hub com um locatário do Azure AD com o registro automático do Intune habilitado, o dispositivo será registrado automaticamente com o Intune. Para obter mais informações, confira [Métodos de registro para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods).  A afiliação do Azure AD e o registro automático do Intune são necessários para que o Surface Hub seja um “dispositivo compatível” no Intune. 

## Configurações do Windows 10 Team Edition

Selecione o Windows 10 Team para configurações predefinidas de restrição de dispositivos para o Surface Hub e o Surface Hub 2S.

 ![Definir restrições de dispositivos para o Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Essas configurações incluem experiência do usuário e comportamento do aplicativo, registro do Azure Log Analytics, configuração de manutenção do Windows, configurações de sessão e configurações do Miracast. Para obter uma lista completa das configurações disponíveis do Windows 10 Team, confira [CPS do SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp).

## Provedores adicionais de serviço de configuração compatíveis (CSPs)

Para obter mais CSPs compatíveis, confira [CSPs do Surface Hub no Windows 10](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

## Configurações da Qualidade de Serviço (QoS)

Para garantir a qualidade ideal de vídeo e áudio no Surface Hub 2S, adicione as seguintes configurações de QoS ao dispositivo. 

### Configurações de QoS do Microsoft Teams 

|**Nome**|**Descrição**|**OMA-URI**|**Tipo**|**Valor**|
|:------ |:------------- |:--------- |:------ |:------- |
|**Portas de áudio**| Intervalo de porta de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | String  | 3478-3479 |
|**DSCP de Áudio**| Marcação de portas de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Inteiro | 46 |
|**Porta de vídeo**| Intervalo de porta de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | String  | 3480 |
|**DSCP de vídeo**| Marcação de portas de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Inteiro | 34 |
|**Portas de áudio P2P**| Intervalo de porta de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | String  | 50000-50019 |
|**DSCP de Áudio P2P**| Marcação de portas de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Inteiro | 46 |
|**Portas de vídeo P2P**| Intervalo de porta de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | String  | 50020-50039 |
|**DSCP de vídeo P2P**| Marcação de portas de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Inteiro | 34 |


### Configurações da QoS do Skype for Business

| Nome               | Descrição         | OMA-URI                                                                  | Tipo    | Valor                          |
| ------------------ | ------------------- | ------------------------------------------------------------------------ | ------- | ------------------------------ |
| Portas de áudio        | Intervalo de porta de áudio    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition  | String  | 50000-50019                    |
| DSCP de Áudio         | Marcação de portas de áudio | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                | Inteiro | 46                             |
| Origem da mídia de áudio | Nome do aplicativo Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |
| Portas de vídeo        | Intervalo de porta de vídeo    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition  | String  | 50020-50039                    |
| DSCP de vídeo         | Marcação de portas de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                | Inteiro | 34                             |
| Origem de mídia de vídeo | Nome do aplicativo Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Ambas as tabelas mostram intervalos de porta padrão. Os administradores podem alterar os intervalos de porta no painel de controle do Skype for Business e do Teams.

## Configurações do modo do Microsoft Teams

Você pode definir o modo de aplicativo Microsoft Teams usando o Intune. O Surface Hub 2S vem instalado com o Microsoft Teams no modo 0, que é compatível com o Microsoft Teams e com o Skype for Business. Você pode ajustar os modos conforme mostrado a seguir.

### Modos:

- Modo 0 — Skype for Business com a funcionalidade do Microsoft Teams para reuniões agendadas.
- Modo 1 — Microsoft Teams com a funcionalidade do Skype for Business para reuniões agendadas.
- Modo 2 — Somente Microsoft Teams.

Para definir modos, adicione as seguintes configurações a um Perfil de Configuração de Dispositivo personalizado.

|**Nome**|**Descrição**|**OMA-URI**|**Tipo**|**Valor**|
|:--- |:--- |:--- |:--- |:--- |
|**ID do aplicativo Teams**|Nome do aplicativo|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo do aplicativo Teams**|Modo do Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Inteiro| 0, 1 ou 2|
