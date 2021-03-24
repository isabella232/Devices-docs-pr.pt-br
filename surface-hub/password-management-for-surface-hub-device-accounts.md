---
title: Gerenciamento de senhas (Surface Hub)
description: Toda conta de dispositivo do Microsoft Surface Hub requer uma senha para autenticar e habilitar recursos no dispositivo.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: senha, gerenciamento de senhas, giro de senha, conta de dispositivo
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445577"
---
# <a name="password-management-surface-hub"></a>Gerenciamento de senhas (Surface Hub)

Toda conta de dispositivo do Microsoft Surface Hub requer uma senha para autenticar e habilitar recursos no dispositivo. Por motivos de segurança, convém alterar (ou "girar") essa senha regularmente. No entanto, se a senha da conta de dispositivo mudar, a conta que estava anteriormente armazenada no Surface Hub será inválida, e todos os recursos que dependem da conta de dispositivo serão desabilitados. Você precisará atualizar a senha da conta de dispositivo no Surface Hub, no aplicativo Configurações, para reabilitar esses recursos.

Para simplificar o gerenciamento de senhas para suas contas de dispositivos Surface Hub, há duas opções:

1.  Desativar a expiração de senha para a conta de dispositivo.
2.  Permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo.


## <a name="turn-off-password-rotation-for-the-device-account"></a>Desativar a rotação de senha para a conta de dispositivo

Defina a propriedade **PasswordNeverExpires** da conta de dispositivo como True. Você deve verificar se isso atende aos requisitos de segurança da sua organização.


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>Permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo

O Surface Hub pode alterar automaticamente a senha de uma conta de dispositivo sem exigir que você a atualize manualmente. Você pode habilitar esse recurso em **Configurações**  >  **contas do Surface Hub.**  >  **** Se você ativar Rotação de Senha, o Surface Hub tentará alterar a senha a cada 7 dias durante o horário de manutenção. As senhas não são mudadas durante uma reunião. Se 7 dias se passaram desde a última rotação de senha, mas o Surface Hub estava desligado, ele tentará alterar a senha imediatamente quando estiver ligado ou a cada 10 minutos até ter êxito.

As senhas geradas automaticamente contêm de 15 a 32 caracteres, incluindo uma combinação de letras maiúsculas e minúsculas, números e caracteres especiais. Observe que, quando a senha da conta do dispositivo for alterada, você não será mostrado a nova senha. Se você precisar entrar na conta ou fornecer a senha novamente (por exemplo, se quiser alterar as configurações da conta de dispositivo no Surface Hub), será necessário usar o Active Directory ou o portal de administração do Microsoft 365 para redefinir a senha.

> [!IMPORTANT]
> O formato usado ao adicionar a conta de dispositivo ao Surface Hub tem um impacto sobre qual opção de [afiliação](prepare-your-environment-for-surface-hub.md) de dispositivo deve ser usada para que a rotação de senha funcione. Se adicionar a conta no **formato domínio\nome** de usuário, afiliada o Hub ao Active Directory local durante a configuração inicial. Se adicionar a conta no `username@domain.com` formato, afiliada o Hub com o Azure Active Directory durante a configuração inicial. Caso contrário, rotação de senha não funcionará.
