---
title: Criar e testar uma conta de dispositivo (Surface Hub)
description: Este tópico apresenta como criar e testar a conta de dispositivo que o Microsoft Surface Hub usa para se comunicar com o Microsoft Exchange e o Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: criar e testar conta de dispositivo, conta de dispositivo, Surface Hub e Microsoft Exchange, Surface Hub e Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 685359f1371a1bef8bd216223a98b934c997a1d8
ms.sourcegitcommit: 879e80200aea26f6705c887fa392db5db35b99ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2021
ms.locfileid: "11475085"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>Criar e testar uma conta de dispositivo (Surface Hub)

A criação de uma conta de dispositivo surface hub (também conhecida como conta de recurso/caixa de correio de sala) permite que o Surface Hub receba, aprove ou declina solicitações de reunião e participe de reuniões.

Depois que a conta do dispositivo for provisionada em um Surface Hub, as pessoas poderão adicionar essa conta a um convite de reunião da mesma maneira que convidariam uma sala de conferência. 

Você pode configurar a conta do dispositivo durante a configuração do [OOBE (Experiência](first-run-program-surface-hub.md)DeSemana). Se necessário, você também pode alterá-lo posteriormente em **Configurações**  >  **contas do Surface Hub.**  >  ****

## <a name="configuration-overview"></a>Visão geral da configuração

Esta tabela explica as etapas principais e as decisões de configuração para criar uma conta de dispositivo.
 
| Etapa | Descrição                     |  Finalidade                             |
|------|---------------------------------|--------------------------------------|
| 1    | Criar uma caixa de correio de sala habilitada para logon (Exchange Online ou Exchange Server 2016 e posterior) | Esse tipo de caixa de correio permite que o dispositivo mantenha um calendário de reunião, receba solicitações de reunião e envie emails. Ele deve ser habilitado para logon para ser usado com um Surface Hub. |
| 2    | Configurar as propriedades da caixa de correio | A caixa de correio deve ser configurada com as propriedades corretas para proporcionar a melhor experiência de reunião no Surface Hub. Para obter mais informações sobre as propriedades da caixa de correio, consulte [Propriedades da caixa de correio](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Verifique se o EWS (Serviços Web do Exchange) está habilitado e a autenticação multifafação (MFA) está desabilitada | O Surface Hub usa o EWS para sincronizar seu calendário. Se você não permitir o EWS em seu ambiente por padrão, a caixa de correio do Hub precisará habilitar explicitamente. À medida que o Surface Hub registra o Exchange em segundo plano sem a interação do usuário, ele não pode responder a prompts interativos, como MFA. A conta de dispositivo que você criar deve ser excluída desses requisitos de autenticação. Caso contrário, o Surface Hub não poderá sincronizar informações de email e calendário. |
| 4    | Habilitar a conta para o Teams ou o Skype for Business (Skype for Business Server 2015 e posterior) | O Skype for Business ou o Teams devem estar habilitados para usar recursos de conferência, como chamadas de vídeo, mensagens de IM e compartilhamento de tela. Para obter mais informações sobre as licenças que habilitam o Teams, consulte [Licenciamento da](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing) Sala de Reunião do Teams e Descrição do serviço do [Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description) |
| 5    | (Opcional) Desabilitar a validade da senha | Para simplificar o gerenciamento, você pode desativar a validade da senha para a conta de dispositivo e permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo. Para obter mais informações sobre gerenciamento de senhas, consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md).  |
| 6    | (Opcional) Configurar políticas do Exchange para permitir o ActiveSync | Com determinadas implantações do Active Directory Exchange Server & local, o ActiveSync será usado para sincronizar as informações de email e calendário da conta de dispositivo. Para obter mais informações sobre as políticas a ser configuradas, consulte [ActiveSync policies for Surface Hub accounts](apply-activesync-policies-for-surface-hub-device-accounts.md). |

> [!NOTE]  
> A conta do dispositivo Surface Hub não dá suporte a IdPs (Provedores de Identidade federados) de terceiros e deve ser autenticada por meio do Active Directory ou do Azure Active Directory.

## <a name="detailed-configuration-steps"></a>Etapas de configuração detalhadas 

Recomendamos configurar suas contas de dispositivo Surface Hub usando Windows PowerShell. A Microsoft [ forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de recursos ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de dispositivo surface hub compatíveis. Se preferir, você pode escolher uma opção na tabela abaixo e seguir as etapas detalhadas do PowerShell com base na implantação da sua organização.

| Implantação da organização             |  Descrição                  |        Formato a ser usado durante a instalação do Surface Hub
|---------------------------------|--------------------------------------|
| [Implantação online (Microsoft 365 ou Office 365)](https://docs.microsoft.com/microsoftteams/rooms/with-office-365) |O ambiente da sua organização é totalmente implantado no Microsoft 365 ou No Office 365. | nomedousuário@domínio.com |
| [Implantação híbrida (Local do Exchange)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-on-premises) | Sua organização tem uma combinação de serviços, com Exchange Server hospedados no local e o Microsoft Teams online. | username@domain.com se [a Autenticação Moderna](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) Híbrida estiver habilitada no Exchange, DOMÍNIO\nome de usuário caso contrário |
| [Implantação híbrida (Exchange Online)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-online) | Sua organização tem uma combinação de serviços, com o Skype for Business Server hospedado no local e o Exchange Online. | username@domain.com se [a Autenticação Moderna](https://docs.microsoft.com/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) Híbrida estiver habilitada em SfB, DOMÍNIO\nome de usuário caso contrário |
| [Implantação local (floresta única)](https://docs.microsoft.com/microsoftteams/rooms/with-skype-for-business-server-2015) | Sua organização tem servidores que ele controla, onde o Active Directory, o Exchange e o Skype for Business Server estão hospedados em um ambiente de floresta única.  | DOMÍNIO\nomedousuário |
| [Implantação local (várias florestas)](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | Sua organização tem servidores que ele controla, onde o Active Directory, o Exchange e o Skype for Business Server estão hospedados em um ambiente de várias florestas. | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>Verificação da conta e testes

Há dois métodos disponíveis que você pode usar para validar e testar uma conta de dispositivo Surface Hub: [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) e o aplicativo de Diagnóstico de [Hardware do Surface Hub.](https://www.microsoft.com/store/apps/9nblggh51f2g) O script de provisionamento de conta pode validar uma conta de dispositivo criada anteriormente usando o PowerShell em seu computador. O app Diagnóstico de Hardware do Surface Hub está instalado no seu Surface Hub e fornece comentários detalhados sobre falhas de início de sessão e de comunicação. Ambas são ferramentas valiosas para testar as contas de dispositivo recém-criado e devem ser usadas para garantir a disponibilidade ideal da conta.
