---
title: Referência de SKU do sistema (Surface)
description: Consulte uma referência de nomes de SKU do sistema e modelo do sistema.
keywords: uefi, configurar, firmware, seguro, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 2140faf346229842bffc4f9348041f4667b94686
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271365"
---
# Referência de SKU do sistema

Este documento fornece uma referência aos nomes de SKU do sistema e modelo do sistema que você pode usar para determinar rapidamente o estado do computador de um dispositivo específico usando o PowerShell ou wMI.

System Model and System SKU are variables that are stored in the System Management BIOS (SMBIOS) tables in the UEFI layer of Surface devices. Use o nome SKU do sistema sempre que precisar diferenciar entre dispositivos com o mesmo nome de modelo de sistema, como Surface Pro e Surface Pro com LTE Avançado.

| Dispositivo   | Modelo do sistema | SKU do sistema       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE na América do Norte                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fora da América do Norte e Y!mobile no Japão | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro com LTE Avançado                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE Comercial | System Go | Surface_Go_1825_Commercial |
| Consumidor do Surface Go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Comercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Consumidor do Surface Pro 6                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Comercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Consumidor do Surface Laptop 2                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Comercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X com processador SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 

## Exemplos 

**Recuperar a SKU usando o PowerShell**  
Use o seguinte comando do PowerShell para obter as informações da SKU do sistema:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Recuperar a SKU usando informações do sistema**  
Você também pode encontrar a SKU do sistema e o modelo do sistema para um dispositivo em **Informações do Sistema.** Para fazer isso, siga estas etapas:

1. Selecione **Iniciar**e digite **MSInfo32** na caixa de pesquisa.  
1. Selecione **Informações do Sistema.**

**Usando a SKU em uma condição WMI de sequência de tarefas**  
Você pode usar as informações de SKU do sistema no Microsoft Deployment Toolkit (MDT) ou no Microsoft Endpoint Configuration Manager como parte de uma condição WMI de sequência de tarefas.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
