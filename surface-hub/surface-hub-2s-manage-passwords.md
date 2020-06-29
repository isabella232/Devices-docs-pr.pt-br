---
title: Gerenciar rotação de senha de conta de dispositivo
description: Saiba como configurar contas locais do Surface Hub 2S com o PowerShell
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831094"
---
# <span data-ttu-id="3e769-104">Gerenciar rotação de senha de conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="3e769-104">Manage device account password rotation</span></span>

<span data-ttu-id="3e769-105">Você pode configurar o Surface Hub 2S para alterar automaticamente a senha de uma conta de dispositivo sem exigir que você atualize manualmente as informações da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e769-105">You can configure Surface Hub 2S to automatically change a device account password without requiring you to manually update the device account information.</span></span>

<span data-ttu-id="3e769-106">Se você ativar a rotação de senha, o Surface Hub 2S alterará a senha a cada 7 dias.</span><span class="sxs-lookup"><span data-stu-id="3e769-106">If you turn on Password Rotation, Surface Hub 2S changes the password every 7 days.</span></span> <span data-ttu-id="3e769-107">As senhas geradas automaticamente contêm 15-32 caracteres, incluindo uma combinação de letras maiúsculas e minúsculas, números e caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="3e769-107">The automatically generated passwords contain 15-32 characters including  a combination of uppercase and lowercase letters, numbers, and special characters.</span></span>

<span data-ttu-id="3e769-108">As senhas não são alteradas durante uma reunião.</span><span class="sxs-lookup"><span data-stu-id="3e769-108">Passwords do not change during a meeting.</span></span> <span data-ttu-id="3e769-109">Se o Surface Hub 2S estiver desativado, ele tentará alterar a senha imediatamente quando ativado ou a cada 10 minutos até que tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="3e769-109">If Surface Hub 2S is turned off, it attempts to change the password immediately when turned on or every 10 minutes until successful.</span></span>
