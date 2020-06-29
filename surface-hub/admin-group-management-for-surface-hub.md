---
title: Gerenciamento de grupo de administração (Surface Hub)
description: Cada Microsoft Surface Hub pode ser configurado individualmente, abrindo o aplicativo Configurações no dispositivo.
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: gerenciamento de grupo de administração, aplicativo Configurações, configurar o Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 716e409bf988e7178ec45e21165aad070d027eee
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831020"
---
# Gerenciamento de grupo de administração (Surface Hub)


Cada Surface Hub pode ser configurado localmente usando-se o aplicativo Configurações no dispositivo. Para evitar que usuários não autorizados alterem configurações, o aplicativo Configurações requer credenciais de administrador para abrir o aplicativo.


## Gerenciamento de grupo de administração

Você pode configurar contas de administrador para o dispositivo de uma destas três maneiras:

-   Criar uma conta de administrador local
-   Ingressar o dispositivo a um domínio Active Directory (AD)
-   Ingresso do dispositivo no Azure Active Directory (Azure AD)


### Criar uma conta de administrador local

Para criar um administrador local, [opte por usar um administrador local durante a primeira execução](first-run-program-surface-hub.md#use-a-local-admin). Isso criará uma conta de administrador local única no Surface Hub com o nome de usuário e a senha de sua preferência. Use essas credenciais para abrir o aplicativo Configurações.

Observe que as informações da conta de administrador local não são apoiadas por nenhum serviço de diretório. Recomendamos que você escolha um administrador local somente se o dispositivo não tiver acesso ao Active Directory (AD) ou Azure Active Directory (Azure AD). Se você decidir alterar a senha do administrador local, poderá fazer isso em Configurações. No entanto, se você quiser mudar de uma conta de administrador local para um grupo de seu domínio ou do locatário do Azure AD, precisará [redefinir o dispositivo](device-reset-surface-hub.md) e executar o programa de configuração inicial novamente.

### Ingressar o dispositivo a um domínio Active Directory (AD)

Você pode ingressar o Surface Hub ao seu domínio do AD para permitir que os usuários de um grupo de segurança especificado definam as configurações. Durante a primeira execução, opte por usar o [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services). Você precisará fornecer as credenciais que são capazes de ingressar no domínio de sua preferência e o nome de um grupo de segurança existente. Qualquer pessoa que for membro desse grupo de segurança pode inserir suas credenciais e desbloquear Configurações.

#### O que acontece quando você ingressa seu Surface Hub a um domínio?
Os Surface Hubs usam o ingresso no domínio para:
- Conceder direitos de administrador a membros de um grupo de segurança especificado no AD.
- Fazer backup da chave de recuperação do BitLocker do dispositivo armazenando-a no objeto de computador no AD. Consulte [Salvar sua chave do BitLocker](save-bitlocker-key-surface-hub.md) para saber os detalhes.
- Sincronizar o relógio do sistema com o controlador de domínio para comunicação criptografada

O Surface Hub não dá suporte à aplicação de políticas de grupo ou certificados do controlador de domínio.

> [!NOTE]
> Se o Surface Hub perder a confiança no domínio (por exemplo, se você remover o Surface Hub do domínio depois de ingressá-lo), não será possível autenticar o dispositivo e abrir Configurações. Se você optar por remover a relação de confiança do Surface Hub com seu domínio, [redefina o dispositivo](device-reset-surface-hub.md) primeiro.


### Ingresso do dispositivo no Azure Active Directory (Azure AD)

Você pode ingressar o Surface Hub no Azure AD para permitir que os profissionais de TI de seu locatário do Azure AD definam as configurações. Durante a primeira execução, opte por usar o [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory). Você precisará fornecer as credenciais que são capazes de ingressar o locatário do Azure AD de sua preferência. Depois que você ingressar no Azure AD, as pessoas adequadas receberão direitos de administrador no dispositivo.

Por padrão, todos os **administradores globais** receberão direitos de administrador em um Surface Hub associado ao Azure AD. Com o **Azure AD Premium** ou **Enterprise Mobility Suite (EMS)**, você pode adicionar mais administradores:
1.  No [portal clássico do Azure](https://manage.windowsazure.com/), clique em **Active Directory** e, em seguida, clique no nome do diretório da organização.
2.  Na página **Configurar**, em **Dispositivos** > **Os administradores adicionais podem Ingressar no Azure AD com seus dispositivos**, clique em **Selecionados**.
3.  Clique em **Adicionar** e selecione os usuários que você deseja adicionar como administradores em seu Surface Hub e outros dispositivos associados ao Azure AD.
4.  Quando terminar, clique no botão de marca de seleção para salvar as alterações.

#### O que acontece quando você ingressa seu Surface Hub no Azure AD?
Os Surface Hubs usam ingresso no Azure AD para:
- Conceder direitos de administrador aos usuários apropriados em seu locatário do Azure AD.
- Fazer backup da chave de recuperação do BitLocker do dispositivo armazenando-a na conta que foi usada para ingressar o dispositivo no Azure AD. Consulte [Salvar sua chave do BitLocker](save-bitlocker-key-surface-hub.md) para saber os detalhes.

### Registro automático via Azure Active Directory Join

O Surface Hub agora oferece suporte à capacidade de registrar-se automaticamente no Intune ao ingressar no seu dispositivo no Azure Active Directory. 

Para obter mais informações, consulte [habilitar o registro automático do Windows 10](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

### Qual devo escolher?

Se sua organização estiver usando o AD ou Azure AD, recomendamos que você ingresse em domínio ou no Azure AD, principalmente por motivos de segurança. As pessoas poderão autenticar e desbloquear Configurações com suas próprias credenciais, e podem ser movidas ou excluídas dos grupos de segurança associados ao seu domínio.

| Opção                                            | Requisitos                            | Quais credenciais podem ser usadas para acessar o aplicativo Configurações?  |
|---------------------------------------------------|-----------------------------------------|-------|
| Criar uma conta de administrador local                      | Nenhum                                    | O nome de usuário e a senha especificados durante a primeira execução |
| Ingressar no domínio do Active Directory (AD)              | Sua organização usa o AD               | Qualquer usuário do AD de um grupo de segurança específico em seu domínio |
| Ingresso do dispositivo no Azure Active Directory (Azure AD) | Sua organização usa o Azure AD Basic   | Somente administradores globais |
| &nbsp;                                            | Sua organização usa o Azure AD Premium ou Enterprise Mobility Suite (EMS) | Administradores globais e administradores adicionais |


