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
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 3b3b5ed47e3a34369c6890aac051436db1f42347
ms.sourcegitcommit: f8f32455b1230742c58ee74004cbaaad037069b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328205"
---
# Gerenciar o Surface Hub 2S com o Intune

## Registrar o Surface Hub 2S com o Intune

O Surface Hub 2S permite que os administradores de TI gerenciem as configurações e as políticas usando um provedor de MDM (gerenciamento de dispositivo móvel). O Surface Hub 2S possui um componente de gerenciamento interno que se comunica com o servidor de gerenciamento, portanto, não é necessário instalar clientes adicionais no dispositivo.

### Registro manual

1. Abra o **aplicativo Configurações** no Surface Hub 2S e entre como um administrador local. Selecione **Surface Hub** > **Gerenciamento de dispositivo** e, em seguida, selecione **+** para adicionar.
2. Você será solicitado a fazer logon com a conta a ser usada para o Intune. Após a autenticação, o dispositivo será registrado automaticamente com o Intune.

   ![Registrar o Surface Hub 2S com o Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> A conta usada para autenticação será a conta de registro do Intune e deve ser licenciada para o Intune.

### Registro automático - afiliado do Azure Active Directory 

Durante o processo de instalação inicial, ao afiliar um Surface Hub com um locatário do Azure AD com o registro automático do Intune habilitado, o dispositivo será registrado automaticamente com o Intune. Para obter mais informações, confira [Métodos de registro para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods).  A afiliação do Azure AD e o registro automático do Intune são necessários para que o Surface Hub seja um “dispositivo compatível” no Intune. 

## Gerenciando as configurações do Windows 10 Team com o Intune

1. Entre no **Microsoft Endpoint Manager**, selecione **Perfis de**  >  **configuração de**  >  **dispositivos Criar perfil.** 
2. Em **Plataforma,** selecione **Restrições de dispositivo do Windows 10**e  >  **posteriores (Windows 10 Team)** e, em seguida, **selecione Criar**. 
3. Agora você pode procurar e selecionar configurações de restrição de dispositivo predefinidas para o Surface Hub e o Surface Hub 2S.

 ![Definir restrições de dispositivos para o Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Essas configurações abrangem as seguintes categorias: Aplicativos e experiência, insights operacionais do Azure, manutenção, sessão e projeção sem fio.  

## Provedores de serviços de Configuração suportados (CSPs)

Além das políticas disponíveis diretamente por meio do console do Intune, há vários CSPs (provedores de serviços de configuração) que são mapeados para arquivos ou chaves do Registro. 

A Microsoft normalmente fornece novos CSPs com cada nova versão do sistema operacional Windows 10. A [Atualização do Windows 10 Team 2020](surface-hub-2020-update.md) inclui mais de 20 políticas de gerenciamento de dispositivo novas e atualizadas para o Surface Hub e o Surface Hub 2S. Essas políticas MDM dão aos administradores de TI um controle aprimorado sobre as atualizações de aplicativos da Microsoft Store, configurações de projeção sem fio, como Miracast sobre infraestrutura, configurações de rede como Qualidade de Serviço e autenticação com fio 802.1x e novas configurações relacionadas à privacidade/RGPD.

Para obter mais informações, veja os seguintes recursos: 

- [Referência de provedor de serviços de configuração](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [CSP SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [CSPs de políticas suportados pelo Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Novidades na atualização do Surface Hub Team 2020](surface-hub-2020-update-whats-new.md)

## Configurações da Qualidade de Serviço (QoS)

Para garantir a qualidade ideal de vídeo e áudio no Surface Hub 2S, adicione as seguintes configurações de QoS ao dispositivo. 

### Configurações de QoS do Microsoft Teams 

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


### Configurações da QoS do Skype for Business

| Nome                 | Descrição           | OMA-URI                                                                    | Tipo    | Valor                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Portas de áudio          | Intervalo de porta de áudio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | String  | 50000-50019                    |
| DSCP de Áudio           | Marcação de portas de áudio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | Inteiro | 46                             |
| Origem da mídia de áudio   | Nome do aplicativo Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Portas de vídeo          | Intervalo de porta de vídeo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | String  | 50020-50039                    |
| DSCP de vídeo           | Marcação de portas de vídeo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | Inteiro | 34                             |
| Origem de mídia de vídeo   | Nome do aplicativo Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Portas de compartilhamento        | Intervalo de Porta de Compartilhamento    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | String  | 50040-50059                    |
| Compartilhamento de DSCP         | Marcação de portas de compartilhamento | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | Inteiro | 18                             |
| Compartilhamento de fonte de mídia | Nome do aplicativo Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Ambas as tabelas mostram intervalos de porta padrão. Os administradores podem alterar os intervalos de porta no painel de controle do Skype for Business e do Teams.

## Configurações do Microsoft Teams

Você pode definir várias configurações do Microsoft Teams usando o Intune.

### Modos

O Surface Hub 2S vem instalado com o Microsoft Teams no modo 0, que é compatível com o Microsoft Teams e com o Skype for Business. Os modos funcionam conforme descrito abaixo:

- Modo 0 — Skype for Business com a funcionalidade do Microsoft Teams para reuniões agendadas.
- Modo 1 — Microsoft Teams com a funcionalidade do Skype for Business para reuniões agendadas.
- Modo 2 — Somente Microsoft Teams.

Para ajustar o modo, adicione as seguintes configurações a um perfil [de configuração de dispositivo personalizado.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| Nome | Descrição | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**ID do aplicativo Teams**|Nome do aplicativo|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo do aplicativo Teams**|Modo do Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Inteiro| 0, 1 ou 2|

### Reuniões coordenadas e junção de proximidade

Os recursos de reunião coordenada do Teams e de participação de proximidade podem ser [configurados](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) por meio de um arquivo XML implantado por meio de um perfil do Intune.
