---
title: Suporte ao registro de Surface para o piloto automático do Windows
description: Este artigo descreve os requisitos para o envio de solicitações de registro de piloto automático para o suporte da Microsoft.
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
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016461"
---
# Suporte ao registro de Surface para o piloto automático do Windows

Um processo simplificado para registrar dispositivos Surface para a implantação do piloto automático do Windows agora está disponível no suporte da Microsoft. A partir de setembro de 2020, clientes e provedores de soluções na nuvem da Microsoft (CSPs) podem registrar dispositivos de superfície enviando solicitações ao suporte da Microsoft. Esta página descreve os requisitos dos seguintes cenários de registro de piloto automático compatíveis:
 

- **Registro de piloto automático do dispositivo Surface**. Envia a solicitação para registrar dispositivos Surface no piloto automático do Windows.
- **Solicitação de hash de hardware do dispositivo Surface.** Envia a solicitação para o suporte da Microsoft para fornecer a você os hashes de hardware que os clientes ou CSPs podem usar para registrar automaticamente os dispositivos via Microsoft Intune ou o Microsoft Partner Center.
- **Cancelamento de registro do piloto automático do dispositivo Surface.** Envia a solicitação de exclusão de dispositivos do Windows AutoPilot, geralmente usada em cenários de fim da vida útil do dispositivo.

Consulte a tabela a seguir para obter detalhes sobre as informações que você precisará coletar antes de enviar solicitações de registro para o suporte da Microsoft.
 
**Tabela 1. Informações necessárias para solicitações de registro do AutoPilot**
 

| Informações necessárias                   | Descrição                                                                                                                                                                                                                                                                                    | Registro do AutoPilot | Solicitação de hash de hardware | AutoPilot<br>Cancelamento |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **ID de locatário do Azure Active Directory**   | Sua ID de locatário do Azure Active Directory é um identificador globalmente exclusivo (GUID) diferente do nome da sua organização ou do domínio.<br> <br>Para localizar sua ID de locatário, entre no portal do Azure [aqui](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | Y                      | N                     | Y                           |
| **Nome de domínio do Azure Active Directory** | Seu nome de domínio de nível superior; por exemplo, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Comprovante de propriedade**                 | Verifique a prova de propriedade carregando a fatura ou fatura original no formato PDF. Capturas de tela não são aceitas.<br> <br>A fatura ou fatura deve incluir o seguinte:<br>Números de série do dispositivo.<br>Nome da empresa.                                                           | Y                      | Y                     | Y                           |
| **Números de série do dispositivo**              | Carregue o arquivo do Excel no formato CSV com cada número de série do dispositivo em uma nova linha.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Enviar solicitações de suporte

  [![Get suporte ao registro de piloto automático para Surface](images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Saiba mais

- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md)
- [Registrar dispositivos Windows no Intune usando o Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Visão geral do Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

