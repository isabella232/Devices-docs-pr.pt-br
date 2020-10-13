---
title: Referência de SKU do sistema (Surface)
description: Consulte uma referência do modelo do sistema e nomes de SKU do sistema.
keywords: UEFI, configuração, firmware, seguro, Semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ec1d53a4bdbcaaf6606dcb0e52fc81de92a2a53b
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114539"
---
# Referência de SKU do sistema

Este documento fornece uma referência do modelo do sistema e nomes de SKU do sistema que você pode usar para determinar rapidamente o estado do computador de um dispositivo específico usando o PowerShell ou WMI.

O modelo do sistema e o SKU do sistema são variáveis armazenadas nas tabelas do SMBIOS (System Management BIOS) na camada UEFI de dispositivos Surface. Use o nome SKU do sistema sempre que precisar diferenciar os dispositivos com o mesmo nome de modelo do sistema, como Surface pro e Surface pro com LTE Advanced.

| Dispositivo   | Modelo do sistema | SKU do sistema       |
| ---------- | ----------- | -------------- |
| Superfície 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE em&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| América do norte da superfície 3 LTE                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fora da América do Norte e Y! celular no Japão | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro com LTE Avançado                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13 "                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15 "                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13 "                                        | Catálogo de superfície 3   | Surface_Book_3_1900                |
| Surface Book 3 15 "                                        | Catálogo de superfície 3   | Surface_Book_3_1899
| Surface go LTE comercial | Sistema go | Surface_Go_1825_Commercial |
| Consumidor do Surface go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface go comercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Ir para a superfície 2                                                 | Ir para a superfície 2     | Surface_Go_2_1927                |
| Cliente Surface pro 6                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Laptop Surface 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Laptop Surface 2 comercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X com processador SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface laptop 3 13 "Intel | Laptop Surface 3 | Surface_Laptop_3_1867:1868 |
| Surface laptop 3 15 "Intel | Laptop Surface 3 | Surface_Laptop_3_1872      |
| Surface laptop 3 15 "AMD   | Laptop Surface 3 | Surface_Laptop_3_1873      | 
| Usar o laptop Surface  | Usar o laptop Surface | Surface_Laptop_Go_1943      | 

## Exemplos 

**Recuperando a SKU usando o PowerShell**  
Use o seguinte comando do PowerShell para extrair as informações de SKU do sistema:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Recuperando o SKU usando as informações do sistema**  
Você também pode encontrar a SKU do sistema e o modelo do sistema para um dispositivo em **informações do sistema**. Para fazer isso, siga estas etapas:

1. Selecione **Iniciar**e, em seguida, digite **msinfo32** na caixa de pesquisa.  
1. Selecione **informações do sistema**.

**Usar a SKU em uma sequência de tarefas WMI Condition**  
Você pode usar as informações de SKU do sistema no Microsoft Deployment Toolkit (MDT) ou Microsoft Endpoint Configuration Manager como parte de uma condição WMI de sequência de tarefas.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
