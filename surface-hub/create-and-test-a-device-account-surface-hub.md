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
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831019"
---
# Criar e testar uma conta de dispositivo (Surface Hub)


Este tópico apresenta como criar e testar a conta de dispositivo que o Microsoft Surface Hub usa para se comunicar com o Microsoft Exchange e o Skype.

Uma **conta de dispositivo** é uma conta de recurso do Exchange que o Surface Hub usa para:

-   Exibir seu calendário de reunião
-   Ingressar em equipes ou chamadas do Skype for Business
-   Enviar email (por exemplo, enviar conteúdo do quadro de comunicações de uma reunião por email)

Depois que a conta do dispositivo for provisionada em um Surface Hub, as pessoas poderão adicionar essa conta a um convite de reunião da mesma maneira que convidariam uma sala de reunião. 

## Visão geral da configuração

Esta tabela explica as etapas principais e as decisões de configuração para criar uma conta de dispositivo. 
 
| Etapa | Descrição                     |  Finalidade                             |
|------|---------------------------------|--------------------------------------|
| um    | Criada uma caixa de correio de recurso do Exchange habilitada para logon (Exchange 2013 ou posterior, ou Exchange Online) | Essa caixa de correio de recurso permite que o dispositivo mantenha um calendário de reunião, receba solicitações de reunião e envie emails. Ela deve ser habilitada para logon para ser provisionada para um Surface Hub. |
| 2    | Configurar as propriedades da caixa de correio | A caixa de correio deve ser configurada com as propriedades corretas para proporcionar a melhor experiência de reunião no Surface Hub. Para obter mais informações sobre as propriedades da caixa de correio, consulte [Propriedades da caixa de correio](exchange-properties-for-surface-hub-device-accounts.md). |
| 3D    | Aplicar uma política de caixa de correio de dispositivo móvel compatível à caixa de correio | O Surface Hub é gerenciado usando com o MDM (gerenciamento de dispositivo móvel), e não por meio de políticas de caixa de correio de dispositivo móvel. Para compatibilidade, a conta de dispositivo deve ter uma política de caixa de correio de dispositivo móvel onde a configuração de **PasswordEnabled** seja definida como False. Caso contrário, o Surface Hub não poderá sincronizar informações de email e calendário. |
| 4    | Habilitar caixa de correio com o Skype for Business (Lync Server 2013 ou posterior, ou Skype for Business Online) | O Skype for Business deve estar habilitado para usar recursos de conferência, como chamadas de vídeo, mensagens instantâneas e compartilhamento de tela.  |
| 5    | (Opcional) Incluir ID de Dispositivo do ActiveSync na Lista Branca | Sua organização pode ter uma política global que impeça que as contas de dispositivo sincronizem emails e informações de calendário. Em caso afirmativo, você precisará permitir a identificação de dispositivo do ActiveSync do Surface Hub. |
| 5    | (Opcional) Desabilitar a validade da senha | Para simplificar o gerenciamento, você pode desativar a validade da senha para a conta de dispositivo e permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo. Para obter mais informações sobre gerenciamento de senhas, consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md).  |

## Etapas de configuração detalhadas 

É recomendável configurar suas contas de dispositivo usando o PowerShell remoto. Há scripts do PowerShell disponíveis para ajudar a criar e validar contas de dispositivo. Para obter mais informações sobre scripts do PowerShell e instruções, consulte [Apêndice a: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md). 

Para conferir as etapas detalhadas usando o PowerShell para provisionar uma conta de dispositivo, escolha uma opção da tabela, com base na implantação de sua organização. 

| Implantação da organização             |  Descrição                  |
|---------------------------------|--------------------------------------|
| [Implantação online (Office 365)](online-deployment-surface-hub-device-accounts.md) | O ambiente de sua organização está implantado inteiramente no Office 365. |
| [Implantação local (floresta única)](on-premises-deployment-surface-hub-device-accounts.md) | Sua organização tem servidores controlados e usados para hospedar o Active Directory, o Exchange e o Skype for Business (ou Lync) em um ambiente de floresta única. |
| [Implantação local (várias florestas)](on-premises-deployment-surface-hub-multi-forest.md) | Sua organização tem servidores controlados e usados para hospedar o Active Directory, o Exchange e o Skype for Business (ou Lync) em um ambiente de várias florestas. |
| [Implantação híbrida](hybrid-deployment-surface-hub-device-accounts.md) | Sua organização tem uma combinação de serviços, sendo alguns hospedados no local e alguns hospedados online por meio do Office 365. |
| [Implantação online ou híbrida usando o ambiente Skype Hybrid Voice](skype-hybrid-voice.md) | Sua organização tem o Skype for Business para pools domésticos e servidores Exchange na nuvem, e usa um pool local do Skype for Business 2015 ou do Cloud Connector edition conectado via PSTN (Rede Telefônica Pública Comutada). |


Se você preferir usar uma interface gráfica do usuário, algumas etapas podem ser executadas por meio da interface do usuário, em vez do PowerShell. Para obter mais informações, consulte [Criando uma conta de dispositivo usando a interface do usuário](create-a-device-account-using-office-365.md).

## Verificação da conta e testes

Há dois métodos disponíveis que podem ser usados para validar e testar uma conta de dispositivo do Surface Hub: [scripts de verificação da conta](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts) e o [app Diagnóstico de Hardware do Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g). O script de verificação da conta validará uma conta de dispositivo criado anteriormente usando o PowerShell do seu desktop. O app Diagnóstico de Hardware do Surface Hub está instalado no seu Surface Hub e fornece comentários detalhados sobre falhas de início de sessão e de comunicação. Ambas são ferramentas valiosas para testar as contas de dispositivo recém-criado e devem ser usadas para garantir a disponibilidade ideal da conta.

 

 

 





