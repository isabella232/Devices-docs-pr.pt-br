---
title: Preparar o ambiente para o Surface Hub 2S
description: Saiba o que você precisa fazer para preparar seu ambiente para o Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 38f02b885a0ac2789ffc82f1ab38dc57fea5e841
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830438"
---
# Preparar o ambiente para o Surface Hub 2S

## Preparação do Office 365

Se você usa o Exchange Online, o Skype for Business Online, o Microsoft Teams ou o Microsoft whiteboard e pretende gerenciar o Surface Hub 2S com o Intune, primeiro revise os [requisitos do Office 365 para pontos de extremidade](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).

Os pontos de extremidade do Office 365 ajudam a otimizar sua rede enviando todas as solicitações de rede do Office 365 confiáveis diretamente por meio do firewall, ignorando a inspeção ou o processamento adicional do nível do pacote. Esse recurso reduz a latência e os requisitos de capacidade do perímetro.

A Microsoft atualiza regularmente o serviço do Office 365 com novos recursos e funcionalidades, o que pode alterar portas, URLs e endereços IP necessários. Para avaliar, configurar e manter-se atualizado com as alterações, assine o [endereço IP do Office 365 e o serviço Web de URL](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

## Afiliação de dispositivo

Use a afiliação de dispositivo para gerenciar o acesso do usuário ao aplicativo configurações no Surface Hub 2S.
Com o sistema operacional Windows 10 Team Edition (executado no Surface Hub 2S), somente os usuários autorizados podem ajustar as configurações usando o aplicativo configurações. Como a escolha da afiliação pode afetar a disponibilidade do recurso, planeje apropriadamente para garantir que os usuários possam acessar os recursos como pretendidos.

> [!NOTE]
> Você só pode definir a afiliação de dispositivo durante a configuração inicial do OOBE (configuração inicial pelo quadro). Se você precisar redefinir a afiliação de dispositivo, será necessário repetir a configuração do OOBE.

## Sem afiliação

Nenhuma afiliação é como ter o Surface Hub 2S em um grupo de trabalho com uma conta de administrador local diferente em cada Surface Hub 2S. Se você escolher não afiliação, deve salvar localmente a [chave do BitLocker em um pen drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq). Você ainda pode registrar o dispositivo com o Intune; no entanto, somente o administrador local pode acessar o aplicativo configurações usando as credenciais de conta configuradas durante OOBE. Você pode alterar a senha da conta de administrador no aplicativo configurações.

## Active Directory Domain Services

Se você afiliada o Surface Hub 2S com os serviços de domínio do Active Directory locais, será necessário gerenciar o acesso ao aplicativo configurações usando um grupo de segurança no seu domínio. Isso ajuda a garantir que todos os membros do grupo de segurança tenham permissões para alterar as configurações no Surface Hub 2S. Observe também o seguinte:

- Quando o Surface Hub 2S afiliado com os serviços de domínio do Active Directory local, a chave do BitLocker pode ser salva no esquema do Active Directory. Para obter mais informações, consulte [preparar sua organização para o BitLocker: planejamento e políticas](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies). 
- As CAs raiz confiáveis da sua organização são empurradas para o mesmo contêiner no Surface Hub 2S, o que significa que você não precisa importá-las usando um pacote de provisionamento.
- Você ainda pode registrar o dispositivo com o Intune para gerenciar as configurações de forma centralizada no seu Surface Hub 2S.

## Azure Active Directory

Quando você opta por associar seu Surface Hub 2S ao Azure Active Directory (Azure AD), qualquer usuário no grupo de segurança administradores globais pode entrar no aplicativo configurações no Surface Hub 2S. No momento, nenhum outro grupo pode ser delegado para entrar no aplicativo configurações no Surface Hub 2S.

Se você tiver habilitado o registro automático do Intune para a sua organização, o Surface Hub 2S se registrará automaticamente no Intune. A chave do BitLocker do dispositivo é salva automaticamente no Azure AD. Ao afiliar o Surface Hub 2S com o Azure AD, o logon único e a autenticação fácil não funcionarão.
