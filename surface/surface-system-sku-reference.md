---
title: Referência da SKU de sistema do Surface
description: Consulte uma referência de nomes do System Model e SKU do sistema para todos os dispositivos Surface.
keywords: uefi, configure, firmware, secure, semm, Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/19/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: bf3fb926c5e66f5f02f921f1c0d4fbe5f016f02d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577041"
---
# <a name="surface-system-sku-reference"></a>Referência da SKU de sistema do Surface

Este documento fornece uma referência que pode ser usada para várias tarefas de IT, como registrar dispositivos Surface com Windows Autopilot ou verificar o estado do computador de um dispositivo específico com PowerShell ou WMI.

Modelo de Sistema e SKU do Sistema são variáveis armazenadas nas tabelas de BIOS de Gerenciamento do Sistema (SMBIOS) na camada UEFI de dispositivos Surface. Use o nome SKU do sistema sempre que precisar diferenciar entre dispositivos com o mesmo nome do Modelo de Sistema, como Surface Pro e Surface Pro com LTE Avançado.

| Dispositivo   | Modelo de sistema | SKU do sistema       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE North America                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fora da América do Norte e Y!mobile no Japão | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro com LTE Avançado                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Comercial do Surface Go LTE | System Go | Surface_Go_1825_Commercial |
| Consumidor do Surface Go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 Consumidor                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Comercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Consumidor                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Comercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X com processador SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop AMD de 3 15"   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 
| Surface Laptop 4 13" Intel | Surface Laptop 4 | Surface_Laptop_4_1950:1951 |
| Surface Laptop 4 15" Intel | Surface Laptop 4 | Surface_Laptop_4_1978:1979     |
| Surface Laptop AMD de 4 15"   | Surface Laptop 4 | Surface_Laptop_4_1952:1953     | 
| Surface Laptop AMD de 4 13"   | Surface Laptop 4 | Surface_Laptop_4_1958:1959    | 
| Surface Hub 2S 50"  | Surface Hub 2S | Surface Hub 2S   | 
| Surface Hub 2S 85"  | Surface Hub 2S | Surface Hub 2S 85   | 

## <a name="examples"></a>Exemplos 

**Recuperar a SKU usando o PowerShell**  
Use o seguinte comando do PowerShell para obter as informações de SKU do sistema:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Recuperar a SKU usando Informações do Sistema**  
Você também pode encontrar o System SKU e o System Model para um dispositivo em **Informações do Sistema**. Para fazer isso, siga estas etapas:

1. Selecione **Iniciar**e digite **MSInfo32** na caixa de pesquisa.  
1. Selecione **Informações do Sistema**.

**Usando o SKU em uma condição WMI de sequência de tarefas**  
Você pode usar as informações SKU do sistema no Microsoft Deployment Toolkit (MDT) ou Microsoft Endpoint Configuration Manager como parte de uma condição WMI de sequência de tarefas.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

## <a name="learn-more"></a>Saiba mais

- [Referência WMI](https://docs.microsoft.com/windows/win32/wmisdk/wmi-reference)
- [Suporte a Registro Surface para o Windows Autopilot](surface-autopilot-registration-support.md)
