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
ms.date: 07/23/2020
ms.localizationpriority: Medium
ms.openlocfilehash: a031fd7fd861e5d45194ec1a8c391621a2bcb71a
ms.sourcegitcommit: 5fa5efefd510ce6f435d7142fb2f2cc08b520da9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078741"
---
# Gerenciar o Surface Hub 2S com o Intune

## Registrar o Surface Hub 2S com o Intune

O Surface Hub 2S permite que os administradores de TI gerenciem as configurações e as políticas usando um provedor de MDM (gerenciamento de dispositivo móvel). O Surface Hub 2S possui um componente de gerenciamento interno que se comunica com o servidor de gerenciamento, portanto, não é necessário instalar clientes adicionais no dispositivo.

### Registro manual

1. Abra o aplicativo **configurações** no Surface Hub 2S e entre como administrador local. Selecione **Surface Hub** > **Gerenciamento de dispositivo** e, em seguida, selecione **+** para adicionar.
2. Você será solicitado a fazer logon com a conta a ser usada para o Intune. Após a autenticação, o dispositivo será registrado automaticamente com o Intune.

   ![Registrar o Surface Hub 2S com o Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> A conta usada para autenticação será a conta de registro do Intune e deve ser licenciada para o Intune.

### Registro automático - afiliado do Azure Active Directory 

Durante o processo de instalação inicial, ao afiliar um Surface Hub com um locatário do Azure AD com o registro automático do Intune habilitado, o dispositivo será registrado automaticamente com o Intune. Para obter mais informações, confira [Métodos de registro para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods).  A afiliação do Azure AD e o registro automático do Intune são necessários para que o Surface Hub seja um “dispositivo compatível” no Intune. 

## Gerenciando configurações de equipe do Windows 10 com o Intune

1. Conecte-se ao **Microsoft Endpoint Manager**, selecione perfis de configuração de **dispositivos**  >  **Configuration profiles**  >  **Criar perfil**. 
2. Em **plataforma**, selecione **Windows 10 e restrições de dispositivo mais recentes**  >  **(equipe do Windows 10)** e, em seguida, selecione **criar**. 
3. Agora você pode navegar e selecionar as configurações de restrição de dispositivo predefinidas para o Surface Hub e o Surface Hub 2S.

 ![Definir restrições de dispositivos para o Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Essas configurações abrangem as seguintes categorias: aplicativos e experiência, insights operacionais do Azure, manutenção, sessão e projeção sem fio.  

## Provedores de serviços de configuração com suporte (CSPs)

Além das políticas disponíveis diretamente pelo console do Intune, há vários provedores de serviços de configuração (CSPs) que são mapeados para arquivos ou chaves do registro. 

Geralmente, a Microsoft fornece novos CSPs com cada nova versão do sistema operacional Windows 10. A [atualização 2020 do Windows 10 Team](surface-hub-install-2020preview.md), disponível em versão prévia por meio do programa Windows Insider, inclui mais de 20 políticas de gerenciamento de dispositivos novas e atualizadas para Surface Hub e Surface Hub 2s. Essas políticas de MDM dão aos administradores de ti maior controle sobre atualizações de aplicativos da Microsoft Store, configurações de projeção sem fio, como Miracast sobre infraestrutura, configurações de rede, como qualidade de serviço e autenticação com fio 802.1 x e novas configurações relacionadas a privacidade/RGPD.

Para obter mais informações, consulte os seguintes recursos: 

- [Referência de provedor de serviços de configuração](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [CSP SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [CSPs de políticas suportados pelo Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)

## Configurações da Qualidade de Serviço (QoS)

Para garantir a qualidade ideal de vídeo e áudio no Surface Hub 2S, adicione as seguintes configurações de QoS ao dispositivo. 

### Configurações de QoS do Microsoft Teams 

| Nome | Descrição | OMA-URI | Tipo | Valor |
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

| Nome | Descrição | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**ID do aplicativo Teams**|Nome do aplicativo|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo do aplicativo Teams**|Modo do Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Inteiro| 0, 1 ou 2|
