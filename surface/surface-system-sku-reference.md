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
ms.date: 01/07/2022
ms.reviewer: carlol
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 4d9b845901734e23c5b83ee47f9d6608f7495b91
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338504"
---
# <a name="surface-system-sku-reference"></a>Referência da SKU de sistema do Surface

Este documento fornece uma referência que pode ser usada para várias tarefas de IT, como executar comandos ou instalar drivers com base em nomes de modelo de dispositivo/SKU. Modelo de Sistema e SKU do Sistema são variáveis armazenadas em tabelas de BIOS de Gerenciamento de Sistema (SMBIOS) na camada UEFI de dispositivos Surface. Use o nome SKU do sistema sempre que precisar diferenciar entre dispositivos com o mesmo nome do Modelo de Sistema, como Surface Pro e Surface Pro com LTE Avançado. SKUs listados na tabela a seguir referem-se a dispositivos comerciais, a menos que rotulados como Consumidor. 

| Dispositivo   | Modelo de sistema | SKU do sistema       |
| ---------- | ----------- | -------------- |
| Surface 3 Wi-FI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE North America                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fora da América do Norte e Y!mobile no Japão | Surface 3        | Surface_3_ROW                    |
| Surface Book 2 13"                                           | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                           | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                           | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                           | Surface Book 3   | Surface_Book_3_1899
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Consumidor do Surface Go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Comercial do Surface Go LTE                                    | Surface Go       | Surface_Go_1825_Commercial |
| Comercial do Surface Go 2                                      | Surface Go 2     | Surface_Go_2_1926                |
| Consumidor do Surface Go 2                                        | Surface Go 2     | Surface_Go_2_1901                |
| Surface Go 2 LTE                                             | Surface Go 2     | Surface_Go_2_1927                |
| Comercial do Surface Go 3                                      | Surface Go 3     | Surface_Go_3_1926                |
| Consumidor do Surface Go 3                                        | Surface Go 3     | Surface_Go_3_1901                |
| Surface Go 3 LTE                                             | Surface Go 3     | Surface_Go_3_2022                |
| Surface Hub 2S 50"                                           | Surface Hub 2S   | Surface Hub 2S                   |
| Surface Hub 2S 85"                                           | Surface Hub 2S   | Surface Hub 2S 85                |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Comercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Laptop 2 Consumidor                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 3 13" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop AMD de 3 15"                                     | Surface Laptop 3 | Surface_Laptop_3_1873      |
| Surface Laptop 3 15" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop AMD de 4 13"                                     | Surface Laptop 4 | Surface_Laptop_4_1958:1959    |
| Surface Laptop 4 13" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1950:1951 |
| Surface Laptop AMD de 4 15"                                     | Surface Laptop 4 | Surface_Laptop_4_1952:1953     |
| Surface Laptop 4 15" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1978:1979     |
| Surface Laptop Go                                            | Surface Laptop Go | Surface_Laptop_Go_1943      |
| Surface Laptop ES                                            | Surface Laptop ES | Surface Laptop ES            |
| Surface Laptop Studio                                        | Surface Laptop Studio | Surface_Laptop_Studio_1964 |
| Surface Pro (5ª Geração)                                        | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro com o LTE Avançado (5ª Geração)                      | Surface Pro      | Surface_Pro_1807                 |
| Surface Pro 6 Comercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Pro 6 Consumidor                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 7                                                | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro 7+                                               | Surface Pro 7+   | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+   | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 8                                                | Surface Pro 8    | Surface_Pro_8_for_Business_1983|
| Surface Pro 8 LTE                                            | Surface Pro 8    | Surface_Pro_8_for_Business_with_LTE_Advanced_1982|
| Surface Pro X com processador SQ1                             | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X com processador SQ2                             | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Pro X (Wi-Fi)                                        | Surface Pro X    | Surface_Pro_X_2010        |
| Surface Studio                                               | Surface Studio   | Surface_Studio   |
| Surface Studio 2                                             | Surface Studio 2 | Surface_Studio_2_1707_Commercial   |


## <a name="examples"></a>Exemplos

**Recuperar a SKU usando o PowerShell**  
Use o seguinte comando do PowerShell para obter as informações de SKU do sistema:

 ``` powershell  
(Get-CimInstance -Namespace root\wmi -ClassName MS_SystemInformation).SystemSKU
```

**Recuperar a SKU usando Informações do Sistema**  
Você também pode encontrar o System SKU e o System Model para um dispositivo em **Informações do Sistema**. Para fazer isso, siga estas etapas:

1. Selecione **Iniciar** e digite **MSInfo32** na caixa de pesquisa.  
1. Selecione **Informações do Sistema**.

**Usando o SKU em uma condição WMI de sequência de tarefas**  
Você pode usar as informações SKU do sistema no Microsoft Deployment Toolkit (MDT) ou Microsoft Endpoint Configuration Manager como parte de uma condição WMI de sequência de tarefas.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ```

## <a name="learn-more"></a>Saiba mais

- [Referência WMI](/windows/win32/wmisdk/wmi-reference)
- [Suporte a Registro Surface para o Windows Autopilot](surface-autopilot-registration-support.md)
