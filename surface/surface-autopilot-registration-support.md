---
title: Suporte a Registro Surface para o Windows Autopilot
description: Este artigo descreve os requisitos para enviar solicitações de registro do Autopilot ao Suporte da Microsoft.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 4ff3803701ffe71e1c5c0c36200c40e833a7fb25
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271385"
---
# Suporte a Registro Surface para o Windows Autopilot

Um processo simplificado de registro de dispositivos Surface para a implantação do Windows Autopilot agora está disponível no Suporte da Microsoft. A partir de setembro de 2020, os clientes e os CSPs (Provedores de Soluções na Nuvem da Microsoft) podem registrar dispositivos Surface enviando solicitações ao Suporte da Microsoft. Esta página descreve os requisitos para os seguintes cenários de registro do Autopilot com suporte:
 

- **Registro do Surface Device Autopilot.** Envia uma solicitação para registrar dispositivos Surface no Windows Autopilot.
- **Solicitação de hash de hardware do dispositivo Surface.** Envia uma solicitação ao Suporte da Microsoft para fornecer hashes de hardware que os clientes ou CSPs podem usar para registrar dispositivos por meio do Microsoft Intune ou do Microsoft Partner Center.
- **Desregistração do Surface Device Autopilot.** Envia uma solicitação para excluir dispositivos do Windows Autopilot, normalmente usado em cenários de fim de vida útil do dispositivo.

Consulte a tabela a seguir para obter detalhes das informações que você precisará coletar antes de enviar solicitações de registro ao Suporte da Microsoft.
 
**Tabela 1. Informações necessárias para solicitações de registro do Autopilot**
 

| Informações necessárias                   | Descrição                                                                                                                                                                                                                                                                                    | Registro do Autopilot | Solicitação de Hash de Hardware | Autopilot<br>Desregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **ID de locatário do Azure Active Directory**   | Sua ID de locatário do Azure Active Directory é um identificador global exclusivo (GUID) que é diferente do nome ou domínio da sua organização.<br> <br>Para encontrar sua ID de locatário no Portal do Azure [aqui.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Nome de domínio do Azure Active Directory** | Seu nome de domínio de nível superior; por exemplo, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Prova de propriedade**                 | Verifique a prova de propriedade carregando a fatura ou a fatura original em formato PDF. Capturas de tela não são aceitas.<br> <br>A fatura ou a fatura deve incluir o seguinte:<br>Números de série do dispositivo.<br>Nome da empresa.                                                           | Y                      | Y                     | Y                           |
| **Números de série do dispositivo**              | Carregue o arquivo do Excel no formato CSV com cada número de série de dispositivo em uma nova linha.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Enviar solicitações de suporte

  [![GEt Autopilot Registration Support for Surface](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Saiba mais

- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md)
- [Registrar dispositivos Windows no Intune usando o Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Visão geral do Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

