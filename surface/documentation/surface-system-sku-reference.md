---
title: Referência da SKU de sistema do Surface
description: Este tópico fornece uma referência dos nomes de SKU do sistema que você pode usar para determinar rapidamente o estado do computador de um dispositivo específico.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830378"
---
# Referência de SKU do sistema Surface
Este documento fornece uma referência dos nomes de SKU do sistema que você pode usar para determinar rapidamente o estado do computador de um dispositivo específico usando o PowerShell, o WMI e as ferramentas relacionadas. 

O SKU do sistema é uma variável (juntamente com o modelo do sistema e outras) armazenada nas tabelas do SMBIOS (System Management BIOS) na camada UEFI de dispositivos Surface.  Use o nome SKU do sistema sempre que precisar diferenciar os dispositivos com o mesmo nome de modelo do sistema, como Surface pro e Surface pro com LTE Advanced. 

| **Dispositivo**| **Modelo do sistema** | **SKU do sistema**|
| --- | ---| --- |
| Superfície 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE em&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| América do norte da superfície 3 LTE                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fora da América do Norte e do T-Mobile no Japão | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro com LTE Avançado                                | Surface Pro      | Surface_Pro_1807                 |
| Livro Surface 2 13inch                                        | Surface Book 2   | Surface_Book_1832                |
| Livro Surface 2 15inch                                        | Surface Book 2   | Surface_Book_1793                |
| Consumidor do Surface go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface go comercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Ir para a superfície 2                                                 | Ir para a superfície 2     | Surface_Go_2_1927                |
| Cliente Surface pro 6                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Laptop Surface 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Laptop Surface 2 comercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |

## Usando as variáveis de SKU do sistema 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### Informações do sistema
Você também pode encontrar a SKU do sistema e o modelo do sistema para um dispositivo em informações do sistema. 
- Clique em **Iniciar**  >   **msinfo32**.  

### WMI
Você pode usar variáveis de SKU do sistema em uma condição WMI de sequência de tarefas no Microsoft Deployment Toolkit (MDT) ou no Microsoft Endpoint Configuration Manager. Por exemplo: 

    - Namespace WMI – Root\WMI
    - Consulta WQL – selecione * FROM MS_SystemInformation em que SystemSKU = "Surface_Pro_1796"

 
 
 


