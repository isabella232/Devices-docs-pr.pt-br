---
title: Ferramenta de marca de ativos de superfície
description: Este tópico explica como usar a ferramenta de marca de ativo de superfície.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830289"
---
# Ferramenta de marca de ativos de superfície

Marca de ativos de superfície é um utilitário CLI (interface de linha de comando) que permite que você exiba, atribua e modifique um valor de marca de ativo atribuído para dispositivos Surface. Ele funciona no Surface Pro 3 e em todos os dispositivos de superfície mais recentes.

## Requisitos de sistema

- Surface Pro 3 ou posterior

- Firmware UEFI versão 3.9.150.0 ou posterior

## Usar a marca de ativos de superfície 

Para executar a marca de ativos da superfície:

1.  No dispositivo Surface, baixe o **Tag.zipde ativos Surface** no [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=46703), extraia o arquivo zip e salve AssetTag.exe na pasta desejada (neste exemplo, C:\\assets).

    > [!NOTE]
    > Para o Surface Pro X, use o aplicativo chamado **AssetTag_x86** no arquivo zip. 

2.  Abra um console de comando como administrador e execute AssetTag.exe, inserindo o caminho completo da ferramenta.

3.  Reinicie a superfície.

### Comandos da ferramenta de marca do ativo   
Nos exemplos a seguir, AssetTag.exe é salvo em um diretório em um computador local (C:\assets). 

Para obter a marca de ativos proposto, execute AssetTag-g.

**Exemplo**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 Para limpar a marca de ativos proposto, execute AssetTag-s.
 
 **Exemplo**
 
   ```
C:\assets\AssetTag.exe -s
  ```
Para definir a marca de ativo proposto, execute AssetTag-s testassettag12.

**Exemplo**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>O valor da marca de ativos deve conter entre 1 e 36 caracteres. Os caracteres válidos incluem A-Z, a-z, 0-9, ponto final (.) e hífen (-).


## Gerenciando marcas de ativos

Você pode exibir a marca de ativos existente nas configurações de UEFI em informações do dispositivo (**painel de controle > recuperação > inicialização avançada > reiniciar agora**.)

A figura a seguir mostra os resultados da execução da ferramenta de etiqueta de ativos no Surface go.

![Resultados da execução da ferramenta de marca do ativo Surface no Surface go.
](images/assettag-fig1.png)

> **Figura 1.** Resultados da execução da ferramenta de marca do ativo Surface na superfície go

Como alternativa, você pode usar o WMI para consultar a marca de ativos existente em um dispositivo:

(Get-WmiObject-consulta "selecionar * de Win32_SystemEnclosure")

**Exemplo**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### Usando o PowerShell

Você pode usar o script abaixo como uma maneira de obter o valor proposto e interpretar os erros.

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```
