---
title: Salvar sua chave do BitLocker (Surface Hub)
description: Todo Microsoft Surface Hub é configurado automaticamente com o software de criptografia de unidade de disco BitLocker. A Microsoft recomenda veementemente que você faça o backup das chaves de recuperação do BitLocker.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, chaves de recuperação do Bitlocker
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831050"
---
# <span data-ttu-id="42d9f-105">Salvar sua chave do BitLocker (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="42d9f-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="42d9f-106">Todo Microsoft Surface Hub é configurado automaticamente com o software de criptografia de unidade de disco BitLocker.</span><span class="sxs-lookup"><span data-stu-id="42d9f-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="42d9f-107">A Microsoft recomenda veementemente que você faça o backup das chaves de recuperação do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="42d9f-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="42d9f-108">Há várias maneiras de gerenciar a chave do BitLocker no Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="42d9f-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="42d9f-109">Se você tiver associado o Surface Hub a um domínio, o dispositivo fará o backup da chave no domínio e irá armazená-la no objeto de computador.</span><span class="sxs-lookup"><span data-stu-id="42d9f-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="42d9f-110">Se você não encontrar a chave do BitLocker após associar o dispositivo a um domínio, é provável que seu esquema do Active Directory não ofereça suporte ao backup de chaves do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="42d9f-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="42d9f-111">Se você não quiser alterar o esquema, pode salvar a chave do BitLocker. Para isso, vá até Configurações e siga o procedimento para usar uma conta de administrador local, que é detalhado posteriormente nessa lista.</span><span class="sxs-lookup"><span data-stu-id="42d9f-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="42d9f-112">Se você associou o Surface Hub ao Azure Active Directory (Azure AD), a chave do BitLocker será armazenada na conta que foi usada para associar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42d9f-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="42d9f-113">Se você estiver usando uma conta de administrador local para gerenciar o dispositivo, poderá salvar a chave do BitLocker acessando o aplicativo **configurações** e navegando para **Atualizar &** a &gt; **recuperação**de segurança.</span><span class="sxs-lookup"><span data-stu-id="42d9f-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="42d9f-114">Insira uma unidade USB e selecione a opção de salvar a chave do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="42d9f-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="42d9f-115">A chave será salva em um arquivo de texto na unidade USB.</span><span class="sxs-lookup"><span data-stu-id="42d9f-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="42d9f-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="42d9f-116">Related topics</span></span>

[<span data-ttu-id="42d9f-117">Gerenciar o Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="42d9f-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="42d9f-118">Guia do administrador do Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="42d9f-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





