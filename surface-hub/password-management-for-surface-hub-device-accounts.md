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
# <span data-ttu-id="765b6-104">Gerenciamento de senhas (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="765b6-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="765b6-105">Toda conta de dispositivo do Microsoft Surface Hub requer uma senha para autenticar e habilitar recursos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="765b6-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="765b6-106">Por motivos de segurança, convém alterar (ou "girar") essa senha regularmente.</span><span class="sxs-lookup"><span data-stu-id="765b6-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="765b6-107">No entanto, se a senha da conta de dispositivo mudar, a conta que estava anteriormente armazenada no Surface Hub será inválida, e todos os recursos que dependem da conta de dispositivo serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="765b6-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="765b6-108">Você precisará atualizar a senha da conta de dispositivo no Surface Hub, no aplicativo Configurações, para reabilitar esses recursos.</span><span class="sxs-lookup"><span data-stu-id="765b6-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="765b6-109">Para simplificar o gerenciamento de senhas para suas contas de dispositivos Surface Hub, há duas opções:</span><span class="sxs-lookup"><span data-stu-id="765b6-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="765b6-110">Desativar a expiração de senha para a conta de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="765b6-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="765b6-111">Permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="765b6-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <span data-ttu-id="765b6-112">Desativar a rotação de senha para a conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="765b6-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="765b6-113">Defina a propriedade **PasswordNeverExpires** da conta de dispositivo como True.</span><span class="sxs-lookup"><span data-stu-id="765b6-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="765b6-114">Você deve verificar se isso atende aos requisitos de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="765b6-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <span data-ttu-id="765b6-115">Permitir que o Surface Hub mude automaticamente a senha da conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="765b6-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="765b6-116">O Surface Hub pode gerenciar a senha da conta de um dispositivo alterando-a com frequência sem exigir que você atualize manualmente as informações da conta de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="765b6-116">The Surface Hub can manage a device account’s password by changing it frequently without requiring you to manually update the device account’s information.</span></span> <span data-ttu-id="765b6-117">Você pode habilitar esse recurso em **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="765b6-117">You can enable this feature in **Settings**.</span></span> <span data-ttu-id="765b6-118">Uma vez habilitado, a senha da conta de dispositivo mudará semanalmente durante o horário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="765b6-118">Once enabled, the device account's password will change weekly during maintenance hours.</span></span>

<span data-ttu-id="765b6-119">Observe que, quando a senha da conta de dispositivo for alterada, você não verá a nova senha.</span><span class="sxs-lookup"><span data-stu-id="765b6-119">Note that when the device account’s password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="765b6-120">Se você precisar entrar na conta, ou fornecer a senha novamente (por exemplo, se desejar alterar as configurações da conta de dispositivo no Surface Hub), será necessário usar o Active Directory ou o portal de administração do Office 365 para redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="765b6-120">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Office 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="765b6-121">Se a sua organização usa uma topologia híbrida (alguns serviços são hospedados no local e alguns são hospedados online por meio do Office 365), você deverá configurar a conta de dispositivo no formato **domínio\nome de usuário**.</span><span class="sxs-lookup"><span data-stu-id="765b6-121">If your organization uses a hybrid topology (some services are hosted on-premises and some are hosted online through Office 365), you must setup the device account in **domain\username** format.</span></span> <span data-ttu-id="765b6-122">Caso contrário, rotação de senha não funcionará.</span><span class="sxs-lookup"><span data-stu-id="765b6-122">Otherwise, password rotation will not work.</span></span>
