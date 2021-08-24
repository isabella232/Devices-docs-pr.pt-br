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
ms.openlocfilehash: 170fdfa9fb85670ec9ed8282f5d264bf2cdbf906
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911976"
---
# <a name="surface-registration-support-for-windows-autopilot"></a>Suporte a Registro Surface para o Windows Autopilot

Um processo simplificado de registro de dispositivos Surface para Windows implantação do Autopilot agora está disponível no Suporte da Microsoft. A partir de setembro de 2020, os clientes e os CSPs (Provedores de Soluções de Nuvem da Microsoft) podem registrar dispositivos Surface enviando solicitações ao Suporte da Microsoft. Esta página descreve os requisitos para os seguintes cenários de registro do Autopilot com suporte:
 
- **Registro do Surface Device Autopilot**. Envia solicitação para registrar dispositivos Surface no Windows Autopilot.
- **Solicitação de Hash de Hardware do Dispositivo Surface.** Envia uma solicitação ao Suporte da Microsoft para fornecer hashes de hardware que os clientes ou CSPs podem usar para registrar dispositivos de auto-registro por meio do Microsoft Intune ou do Microsoft Partner Center.
- **Desregistration do Surface Device Autopilot.** Envia solicitação para excluir dispositivos do Windows Autopilot, normalmente usados em cenários de fim de vida útil do dispositivo.

Consulte a tabela a seguir para obter detalhes das informações que você precisará coletar antes de enviar solicitações de registro ao Suporte da Microsoft. Para os nomes oficiais do Modelo de Sistema de todos os dispositivos Surface, consulte a referência [SKU do Surface System.](surface-system-sku-reference.md)
 
**Tabela 1. Informações necessárias para solicitações de registro do Autopilot**
 

| Informações necessárias                   | Descrição                                                                                                                                                                                                                                                                                    | Registro do Piloto Automático | Solicitação de Hash de Hardware | Autopilot<br>Desregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory ID do locatário**   | Sua Azure Active Directory ID de locatário é um GUID (identificador global exclusivo) diferente do nome ou domínio da sua organização.<br> <br>Para encontrar sua ID de Locatário, entre no Portal do Azure [aqui](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | S                      | N                     | S                           |
| **Azure Active Directory Nome do Domínio** | Seu nome de domínio de nível superior; por exemplo, contoso.com.                                                                                                                                                                                                                                          | S                      | N                     | S                           |
| **Prova de propriedade**                 | Verifique a prova de propriedade carregando a fatura original de venda ou fatura no formato PDF. Capturas de tela não são aceitas.<br> <br>A fatura de venda ou fatura deve incluir o seguinte:<br>Números de série do dispositivo.<br>Nome da empresa.                                                           | S                      | S                     | S                           |
| **Números de série do dispositivo**              | Upload Excel arquivo no formato CSV com cada número de série de dispositivo em uma nova linha.                                                                                                                                                                                                                  | S                      | S                     | S                           |

 

## <a name="submit-support-requests"></a>Enviar solicitações de suporte

  [![Get Autopilot Registration Support for Surface.](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <a name="learn-more"></a>Saiba mais

- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md)
- [Registrar dispositivos Windows no Intune usando o Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Visão geral do Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [Referência da SKU de sistema do Surface](surface-system-sku-reference.md)

 
 
 

