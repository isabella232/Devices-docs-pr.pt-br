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
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385139"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a>Preparar o ambiente para o Surface Hub 2S

## <a name="office-365-readiness"></a>Preparação do Office 365

Se você usar Exchange Online, Skype for Business Online, Microsoft Teams ou Microsoft Whiteboard e pretende gerenciar o Surface Hub 2S com o Intune, primeiro revise os requisitos do [Office 365](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)para pontos de extremidade .

Os pontos de extremidade do Office 365 ajudam a otimizar sua rede enviando todas as solicitações de rede confiáveis do Office 365 diretamente através do firewall, ignorando todas as inspeções ou processamento adicionais no nível de pacote. Esse recurso reduz a latência e seus requisitos de capacidade de perímetro.

A Microsoft atualiza regularmente o serviço do Office 365 com novos recursos e funcionalidades, que podem alterar portas, URLs e endereços IP necessários. Para avaliar, configurar e manter-se atualizado com as alterações, inscreva-se no Endereço IP do [Office 365 e no serviço Web de URL.](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

> [!NOTE]
> O Surface Hub funciona com o Microsoft Teams, o Skype for Business Server 2019, o Skype for Business Server 2015 ou o Skype for Business Online.
Plataformas anteriores, como o Lync Server 2013, não têm suporte. O Surface Hub não tem suporte em ambientes GCC-High ou DoD.


## <a name="device-affiliation"></a>Afiliação de dispositivo

Use a afiliação de dispositivo para gerenciar o acesso do usuário ao aplicativo Configurações no Surface Hub 2S.
Com o sistema operacional Windows 10 Team (que é executado no Surface Hub 2S), somente os usuários autorizados podem ajustar as configurações usando o aplicativo Configurações. Como a escolha da afiliação pode afetar a disponibilidade de recursos, planeje-se adequadamente para garantir que os usuários possam acessar recursos conforme o pretendido.

> [!NOTE]
> Você só pode definir a afiliação de dispositivo durante a configuração inicial do OOBE (experiência inicial). Se você precisar redefinir a afiliação de dispositivo, precisará repetir a configuração OOBE.

## <a name="no-affiliation"></a>Sem afiliação

Nenhuma afiliação é como ter o Surface Hub 2S em um grupo de trabalho com uma conta de Administrador local diferente em cada Surface Hub 2S. Se você escolher Nenhuma afiliação, deverá salvar localmente [a Chave do BitLocker em uma unidade de pen drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq). Você ainda pode registrar o dispositivo com o Intune; no entanto, somente o administrador local pode acessar o aplicativo Configurações usando as credenciais de conta configuradas durante o OOBE. Você pode alterar a senha da conta de administrador do aplicativo Configurações.

## <a name="active-directory-domain-services"></a>Active Directory Domain Services

Se você afiliada o Surface Hub 2S aos Serviços de Domínio do Active Directory local, precisará gerenciar o acesso ao aplicativo Configurações usando um grupo de segurança em seu domínio. Isso ajuda a garantir que todos os membros do grupo de segurança tenham permissões para alterar as configurações no Surface Hub 2S. Observe também o seguinte:

- Quando o Surface Hub 2S se afiliada aos Seus Serviços de Domínio do Active Directory local, a chave BitLocker pode ser salva no Esquema do Active Directory. Para obter mais informações, [consulte Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).

- As CAs Raiz Confiáveis da sua organização são empurradas para o mesmo contêiner no Surface Hub 2S, o que significa que você não precisa importá-los usando um pacote de provisionamento.

- Você ainda pode registrar o dispositivo com o Intune para gerenciar centralmente as configurações no Surface Hub 2S.

## <a name="azure-active-directory"></a>Azure Active Directory

Quando você optar por afiliadar seu Surface Hub 2S com o Azure Active Directory (Azure AD), qualquer usuário no Grupo de Segurança de Administradores Globais pode entrar no aplicativo Configurações no Surface Hub 2S. Você também pode configurar contas de administrador não globais que limitem permissões ao gerenciamento do aplicativo Configurações no Surface Hub 2S. Isso permite que você escopo permissões de administrador somente para o Surface Hub 2S e impedir o acesso de administrador potencialmente indesejado em um domínio inteiro do Azure AD. 

Se você habilitar o Registro Automático do Intune para sua organização, o Surface Hub 2S se registrará automaticamente no Intune. A chave BitLocker do dispositivo é salva automaticamente no Azure AD. 

Para saber mais sobre como gerenciar o Surface Hub com o Azure AD, consulte: 

 - [Gerenciamento de grupo de administração](admin-group-management-for-surface-hub.md)
 - [Configurar contas administrativas não globais no Surface Hub 2S](surface-hub-2s-nonglobal-admin.md)

