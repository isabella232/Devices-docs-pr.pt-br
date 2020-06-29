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
# Salvar sua chave do BitLocker (Surface Hub)


Todo Microsoft Surface Hub é configurado automaticamente com o software de criptografia de unidade de disco BitLocker. A Microsoft recomenda veementemente que você faça o backup das chaves de recuperação do BitLocker.

Há várias maneiras de gerenciar a chave do BitLocker no Surface Hub.

1.  Se você tiver associado o Surface Hub a um domínio, o dispositivo fará o backup da chave no domínio e irá armazená-la no objeto de computador.

    Se você não encontrar a chave do BitLocker após associar o dispositivo a um domínio, é provável que seu esquema do Active Directory não ofereça suporte ao backup de chaves do BitLocker. Se você não quiser alterar o esquema, pode salvar a chave do BitLocker. Para isso, vá até Configurações e siga o procedimento para usar uma conta de administrador local, que é detalhado posteriormente nessa lista.

2.  Se você associou o Surface Hub ao Azure Active Directory (Azure AD), a chave do BitLocker será armazenada na conta que foi usada para associar o dispositivo.

3.  Se você estiver usando uma conta de administrador local para gerenciar o dispositivo, poderá salvar a chave do BitLocker acessando o aplicativo **configurações** e navegando para **Atualizar &** a &gt; **recuperação**de segurança. Insira uma unidade USB e selecione a opção de salvar a chave do BitLocker. A chave será salva em um arquivo de texto na unidade USB.


## Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





