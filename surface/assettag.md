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
# <a name="surface-asset-tag-tool"></a><span data-ttu-id="f9258-103">Ferramenta de marca de ativos surface</span><span class="sxs-lookup"><span data-stu-id="f9258-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="f9258-104">A Marca do Surface Asset é um utilitário cli (interface de linha de comando) que permite exibir, atribuir e modificar um valor de marca de ativo atribuído para dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="f9258-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="f9258-105">Ele funciona no Surface Pro 3 e em todos os dispositivos Surface mais novos.</span><span class="sxs-lookup"><span data-stu-id="f9258-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="f9258-106">Requisitos de sistema</span><span class="sxs-lookup"><span data-stu-id="f9258-106">System requirements</span></span>

- <span data-ttu-id="f9258-107">Surface Pro 3 ou posterior</span><span class="sxs-lookup"><span data-stu-id="f9258-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="f9258-108">Firmware UEFI versão 3.9.150.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="f9258-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <a name="using-surface-asset-tag"></a><span data-ttu-id="f9258-109">Usando a marca surface asset</span><span class="sxs-lookup"><span data-stu-id="f9258-109">Using Surface Asset Tag</span></span>

<span data-ttu-id="f9258-110">Para executar a marca surface asset:</span><span class="sxs-lookup"><span data-stu-id="f9258-110">To run Surface Asset Tag:</span></span>

1. <span data-ttu-id="f9258-111">No dispositivo Surface, baixe o **Surface Asset Tag.zip** do Centro de Download da [Microsoft,](https://www.microsoft.com/download/details.aspx?id=46703)extraia o arquivo zip e salve AssetTag.exe na pasta desejada (neste exemplo, C:\\assets).</span><span class="sxs-lookup"><span data-stu-id="f9258-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download  Center](https://www.microsoft.com/download/details.aspx?id=46703),  extract the zip file, and save AssetTag.exe in desired folder (in  this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9258-112">Para Surface Pro X, use o aplicativo chamado **AssetTag_x86** no arquivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="f9258-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span>

2. <span data-ttu-id="f9258-113">Abra um console de comando como administrador e execute AssetTag.exe, inserindo o caminho completo para a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="f9258-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3. <span data-ttu-id="f9258-114">Reinicie o Surface.</span><span class="sxs-lookup"><span data-stu-id="f9258-114">Restart Surface.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9258-115">Depois de definir a marca de ativo, uma segunda reinicialização é necessária antes de ser exibida no WMI.</span><span class="sxs-lookup"><span data-stu-id="f9258-115">After setting the asset tag, a second reboot is required before it appears in WMI.</span></span>

### <a name="asset-tag-tool-commands"></a><span data-ttu-id="f9258-116">Comandos da ferramenta De marca de ativos</span><span class="sxs-lookup"><span data-stu-id="f9258-116">Asset Tag tool commands</span></span>

<span data-ttu-id="f9258-117">Nos exemplos a seguir, AssetTag.exe é salvo em um diretório em uma máquina local (C:\assets).</span><span class="sxs-lookup"><span data-stu-id="f9258-117">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span>

<span data-ttu-id="f9258-118">Para obter a marca de ativo proposta, execute **AssetTag -g**:</span><span class="sxs-lookup"><span data-stu-id="f9258-118">To get the proposed asset tag, run **AssetTag -g**:</span></span>

```console
C:\assets\AssetTag.exe -g
```

<span data-ttu-id="f9258-119">Para limpar a marca de ativo proposta, execute **AssetTag -s**:</span><span class="sxs-lookup"><span data-stu-id="f9258-119">To clear the proposed asset tag, run **AssetTag -s**:</span></span>

```console
C:\assets\AssetTag.exe -s
```

<span data-ttu-id="f9258-120">Para definir a marca de ativo proposta, execute **Testassettag -s assetTag12**:</span><span class="sxs-lookup"><span data-stu-id="f9258-120">To set the proposed asset tag, run **AssetTag -s testassettag12**:</span></span>

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="f9258-121">O valor da marca de ativo deve conter entre 1 e 36 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f9258-121">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="f9258-122">Os caracteres válidos incluem A-Z, a-z, 0-9, ponto (.) e hífen (-).</span><span class="sxs-lookup"><span data-stu-id="f9258-122">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>

## <a name="managing-asset-tags"></a><span data-ttu-id="f9258-123">Gerenciando marcas de ativos</span><span class="sxs-lookup"><span data-stu-id="f9258-123">Managing asset tags</span></span>

<span data-ttu-id="f9258-124">Você pode exibir a marca de ativo existente nas configurações UEFI em Informações do Dispositivo ( Painel de Controle > Recuperação >**Inicialização Avançada > Reiniciar agora**.)</span><span class="sxs-lookup"><span data-stu-id="f9258-124">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="f9258-125">A figura abaixo mostra os resultados da execução da Ferramenta de Marca de Ativo no Surface Go.</span><span class="sxs-lookup"><span data-stu-id="f9258-125">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![Resultados da execução da ferramenta Surface Asset Tag no Surface Go.](images/assettag-fig1.png)

> **<span data-ttu-id="f9258-127&quot;>Figura 1.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9258-127&quot;>Figure 1.</span></span>** <span data-ttu-id=&quot;f9258-128&quot;>Resultados da execução da ferramenta Surface Asset Tag no Surface Go</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9258-128&quot;>Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id=&quot;f9258-129&quot;>Como alternativa, você pode usar o WMI para consultar a marca de ativo existente em um dispositivo:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9258-129&quot;>Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id=&quot;f9258-130&quot;>(Get-WmiObject -query &quot;Select \* from Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="f9258-130">(Get-WmiObject -query "Select \* from Win32_SystemEnclosure")</span></span>

### <a name="example"></a><span data-ttu-id="f9258-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f9258-131">Example</span></span>

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a><span data-ttu-id="f9258-132">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9258-132">Using PowerShell</span></span>

<span data-ttu-id="f9258-133">Você pode usar o script abaixo como uma maneira de obter o valor proposto e interpretar quaisquer erros.</span><span class="sxs-lookup"><span data-stu-id="f9258-133">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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
