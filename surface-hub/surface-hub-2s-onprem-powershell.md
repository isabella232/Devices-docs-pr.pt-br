---
title: Configurar contas no local 2S do Surface Hub com o PowerShell
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831095"
---
# Configurar contas no local 2S do Surface Hub com o PowerShell

## Conectar-se ao Exchange Server PowerShell

> [!IMPORTANT]
> Você precisará do FQDN (nome de domínio totalmente qualificado) para o serviço de acesso para cliente do servidor Exchange local para alguns desses cmdlets.

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## Criar a conta do dispositivo

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## Definir o processamento automático do calendário

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## Habilitar o objeto Skype for Business

> [!NOTE]
> É importante que você saiba o FQDN do pool de registradores do Skype for Business.

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## Política de caixa de correio de dispositivo móvel

Talvez seja necessário criar uma política de caixa de correio de dispositivo móvel (também conhecida como política do ActiveSync) para permitir que o Surface Hub se conecte ao seu ambiente online ou local.

## Criar uma política de caixa de correio de dispositivo móvel do Surface Hub

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## Configurações adicionais

É recomendável adicionar uma dica de usuário às salas do Surface Hub para que os usuários se lembrem de transformar a reunião em uma reunião do Skype for Business ou do teams:

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
