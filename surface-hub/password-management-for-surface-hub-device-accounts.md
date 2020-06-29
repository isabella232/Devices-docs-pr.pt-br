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
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831104"
---
# Gerenciamento de senhas (Surface Hub)

Toda conta de dispositivo do Microsoft Surface Hub requer uma senha para autenticar e habilitar recursos no dispositivo. Por motivos de segurança, convém alterar (ou "girar") essa senha regularmente. No entanto, se a senha da conta de dispositivo mudar, a conta que estava anteriormente armazenada no Surface Hub será inválida, e todos os recursos que dependem da conta de dispositivo serão desabilitados. Você precisará atualizar a senha da conta de dispositivo no Surface Hub, no aplicativo Configurações, para reabilitar esses recursos.

Para simplificar o gerenciamento de senhas para suas contas de dispositivos Surface Hub, há duas opções:

1.  Desativar a expiração de senha para a conta de dispositivo.
2.  Permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo.


## Desativar a rotação de senha para a conta de dispositivo

Defina a propriedade **PasswordNeverExpires** da conta de dispositivo como True. Você deve verificar se isso atende aos requisitos de segurança da sua organização.


## Permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo

O Surface Hub pode gerenciar a senha da conta de um dispositivo alterando-a com frequência sem exigir que você atualize manualmente as informações da conta de dispositivo. Você pode habilitar esse recurso em **Configurações**. Uma vez habilitado, a senha da conta de dispositivo mudará semanalmente durante o horário de manutenção.

Observe que, quando a senha da conta de dispositivo for alterada, você não verá a nova senha. Se você precisar entrar na conta, ou fornecer a senha novamente (por exemplo, se desejar alterar as configurações da conta de dispositivo no Surface Hub), será necessário usar o Active Directory ou o portal de administração do Office 365 para redefinir a senha.

> [!IMPORTANT]
> Se a sua organização usa uma topologia híbrida (alguns serviços são hospedados no local e alguns são hospedados online por meio do Office 365), você deverá configurar a conta de dispositivo no formato **domínio\nome de usuário**. Caso contrário, rotação de senha não funcionará.
