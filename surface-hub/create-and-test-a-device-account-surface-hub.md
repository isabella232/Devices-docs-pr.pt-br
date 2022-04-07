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
ms.openlocfilehash: c925cb952c7fd04a86d824dfba99a373c07b313e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472620"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>Criar e testar uma conta de dispositivo (Surface Hub)

Criar uma Surface Hub de dispositivo (também conhecida como uma conta de recurso/caixa de correio de sala) permite que o Surface Hub receba, aprove ou recuse solicitações de reunião e ingresse em reuniões.

Depois que a conta do dispositivo for provisionada em um Surface Hub, as pessoas poderão adicionar essa conta a um convite de reunião da mesma maneira que convidariam uma sala de conferência. 

Você pode configurar a conta do dispositivo durante a configuração de [OOBE (](first-run-program-surface-hub.md)Experiência Inicial de Uso). Se necessário, você também pode alterá-lo posteriormente **em Configurações** >  **Surface Hub** >  **Accounts**.

## <a name="configuration-overview"></a>Visão geral da configuração

Esta tabela explica as etapas principais e as decisões de configuração para criar uma conta de dispositivo.
 
| Etapa | Descrição                     |  Finalidade                             |
|------|---------------------------------|--------------------------------------|
| 1    | Criar uma caixa de correio de sala habilitada para logon (Exchange Online ou Exchange Server 2016 e posterior) | Esse tipo de caixa de correio permite que o dispositivo mantenha um calendário de reunião, receba solicitações de reunião e envie emails. Ele deve ser habilitado para logon para ser usado com um Surface Hub. |
| 2    | Configurar as propriedades da caixa de correio | A caixa de correio deve ser configurada com as propriedades corretas para proporcionar a melhor experiência de reunião no Surface Hub. Para obter mais informações sobre as propriedades da caixa de correio, consulte [Propriedades da caixa de correio](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Verifique se Exchange Serviços Web (EWS) está habilitado e se a MFA (autenticação multifator) está desabilitada | O Surface Hub usa o EWS para sincronizar seu calendário. Se você não permitir o EWS em seu ambiente por padrão, a caixa de correio do Hub precisará habilita-la explicitamente. Conforme o Surface Hub faz logon Exchange em segundo plano sem interação do usuário, ele não pode responder a nenhum prompt interativo, como MFA. A conta de dispositivo que você cria deve ser excluída desses requisitos de autenticação. Caso contrário, o Surface Hub não poderá sincronizar informações de email e calendário. |
| 4    | Habilitar a conta para Teams ou Skype for Business (Skype for Business Server 2015 e posterior) | Skype for Business ou Teams devem ser habilitados para usar recursos de conferência, como chamadas de vídeo e compartilhamento de tela. Para obter mais informações sobre as licenças que habilitam Teams, consulte [Teams Sala de Reunião licenciamento](/MicrosoftTeams/rooms/rooms-licensing) e Teams [serviço.](/office365/servicedescriptions/teams-service-description) Os Teams e os aplicativos SfB no Surface Hub não são compatíveis com as políticas de Acesso Condicional do [Azure AD](/azure/active-directory/conditional-access/concept-conditional-access-policies) que exigem informações do dispositivo (por exemplo, conformidade). A conta de dispositivo que você cria deve ser excluída dessas políticas de AC. Caso contrário, Surface Hub não poderá usar nenhum recurso de conferência. |
| 5    | (Opcional) Desabilitar a validade da senha | Para simplificar o gerenciamento, você pode desativar a validade da senha para a conta de dispositivo e permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo. Para obter mais informações sobre gerenciamento de senhas, consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md).  |

> [!NOTE]  
> A Surface Hub de dispositivo não dá suporte a IdPs (provedores de identidade federados) de terceiros e deve ser autenticada por meio do Active Directory ou Azure Active Directory.

## <a name="detailed-configuration-steps"></a>Etapas de configuração detalhadas 

As etapas de configuração da conta do dispositivo podem ser diferentes com base no ambiente. Selecione o cenário de implantação na tabela abaixo para encontrar as etapas apropriadas e anote a coluna "Formatar para usar" para configurar o Surface Hubs depois que as contas forem provisionadas.

| Implantação da organização             |  Descrição                  |        Formato a ser usado durante a Surface Hub configuração
|---------------------------------|--------------------------------------|
| [Implantação online (Microsoft 365)](/MicrosoftTeams/rooms/with-office-365?tabs=m365-admin-center) |O ambiente da sua organização é implantado inteiramente Microsoft 365. | nomedousuário@domínio.com |
| [Implantação híbrida (Exchange local)](/MicrosoftTeams/rooms/with-office-365?tabs=exchange-server) | Sua organização tem uma combinação de serviços, com Exchange Server hospedados no local e Microsoft Teams online. | username@domain.com se a [Autenticação Moderna Híbrida](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) estiver habilitada no Exchange, DOMÍNIO\nome de usuário caso contrário |
| [Implantação híbrida (Exchange Online)](/skypeforbusiness/deploy/deploy-clients/hybrid-deployments) | Sua organização tem uma combinação de serviços, com Skype for Business Server hospedados localmente e Exchange Online. | username@domain.com se a [Autenticação Moderna Híbrida](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) estiver habilitada em SfB, DOMAIN\username caso contrário |
| [Implantação local (floresta única)](/skypeforbusiness/deploy/deploy-clients/single-forest-on-premises-deployments) | Sua organização tem servidores que ela controla, onde o Active Directory, Exchange e Skype for Business Server são hospedados em um ambiente de floresta única.  | DOMÍNIO\nomedousuário |
| [Implantação local (várias florestas)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | Sua organização tem servidores que ela controla, onde o Active Directory, Exchange e Skype for Business Server estão hospedados em um ambiente de várias florestas. | ACCOUNTFOREST\username |

Para implantações online, também há um assistente de implantação disponível [para Microsoft 365](https://admin.microsoft.com/Adminportal/Home#/modernonboarding/surfacehubsetupguide) administradores diretamente no centro de administração do M365. Esse assistente pode ajudar a criar novas contas de dispositivo ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas Surface Hub dispositivo compatíveis.
