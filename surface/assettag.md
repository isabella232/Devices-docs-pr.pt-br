---
title: Ferramenta de marca de ativos surface
description: Este tópico explica como usar a Ferramenta de Marca do Surface Asset.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.date: 06/29/2021
manager: laurawi
ms.openlocfilehash: b130f6b0bf52dc1c3a28231a2330cae51a5ef44a
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643827"
---
# <a name="surface-asset-tag-tool"></a>Ferramenta de marca de ativos surface

A Marca do Surface Asset é um utilitário cli (interface de linha de comando) que permite exibir, atribuir e modificar um valor de marca de ativo atribuído para dispositivos Surface. Ele funciona no Surface Pro 3 e em todos os dispositivos Surface mais novos.

## <a name="system-requirements"></a>Requisitos de sistema

- Surface Pro 3 ou posterior

- Firmware UEFI versão 3.9.150.0 ou posterior

## <a name="using-surface-asset-tag"></a>Usando a marca surface asset

Para executar a marca surface asset:

1. No dispositivo Surface, baixe o **Surface Asset Tag.zip** do Centro de Download da [Microsoft,](https://www.microsoft.com/download/details.aspx?id=46703)extraia o arquivo zip e salve AssetTag.exe na pasta desejada (neste exemplo, C:\\assets).

    > [!NOTE]
    > Para Surface Pro X, use o aplicativo chamado **AssetTag_x86** no arquivo ZIP.

2. Abra um console de comando como administrador e execute AssetTag.exe, inserindo o caminho completo para a ferramenta.

3. Reinicie o Surface.

    > [!NOTE]
    > Depois de definir a marca de ativo, uma segunda reinicialização é necessária antes de ser exibida no WMI.

### <a name="asset-tag-tool-commands"></a>Comandos da ferramenta De marca de ativos

Nos exemplos a seguir, AssetTag.exe é salvo em um diretório em uma máquina local (C:\assets).

Para obter a marca de ativo proposta, execute **AssetTag -g**:

```console
C:\assets\AssetTag.exe -g
```

Para limpar a marca de ativo proposta, execute **AssetTag -s**:

```console
C:\assets\AssetTag.exe -s
```

Para definir a marca de ativo proposta, execute **Testassettag -s assetTag12**:

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>O valor da marca de ativo deve conter entre 1 e 36 caracteres. Os caracteres válidos incluem A-Z, a-z, 0-9, ponto (.) e hífen (-).

## <a name="managing-asset-tags"></a>Gerenciando marcas de ativos

Você pode exibir a marca de ativo existente nas configurações UEFI em Informações do Dispositivo ( Painel de Controle > Recuperação >**Inicialização Avançada > Reiniciar agora**.)

A figura abaixo mostra os resultados da execução da Ferramenta de Marca de Ativo no Surface Go.

![Resultados da execução da ferramenta Surface Asset Tag no Surface Go.](images/assettag-fig1.png)

> **Figura 1.** Resultados da execução da ferramenta Surface Asset Tag no Surface Go

Como alternativa, você pode usar o WMI para consultar a marca de ativo existente em um dispositivo:

(Get-WmiObject -query "Select * from Win32_SystemEnclosure")

### <a name="example"></a>Exemplo

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a>Usando o PowerShell

Você pode usar o script abaixo como uma maneira de obter o valor proposto e interpretar quaisquer erros.

```powershell
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim("\`r\`n")

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output ("Good Tag = " + $asset\_tag)  
} else {  
Write-Output (  
"Failure: Code = " + $asset\_tag\_return\_code +  
"Tag = " + $asset\_tag +  
"Message = " + $error\_message)

}
```
