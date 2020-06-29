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
# <span data-ttu-id="b734f-103">Ferramenta de marca de ativos de superfície</span><span class="sxs-lookup"><span data-stu-id="b734f-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="b734f-104">Marca de ativos de superfície é um utilitário CLI (interface de linha de comando) que permite que você exiba, atribua e modifique um valor de marca de ativo atribuído para dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="b734f-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="b734f-105">Ele funciona no Surface Pro 3 e em todos os dispositivos de superfície mais recentes.</span><span class="sxs-lookup"><span data-stu-id="b734f-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="b734f-106">Requisitos de sistema</span><span class="sxs-lookup"><span data-stu-id="b734f-106">System requirements</span></span>

- <span data-ttu-id="b734f-107">Surface Pro 3 ou posterior</span><span class="sxs-lookup"><span data-stu-id="b734f-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="b734f-108">Firmware UEFI versão 3.9.150.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="b734f-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="b734f-109">Usar a marca de ativos de superfície</span><span class="sxs-lookup"><span data-stu-id="b734f-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="b734f-110">Para executar a marca de ativos da superfície:</span><span class="sxs-lookup"><span data-stu-id="b734f-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="b734f-111">No dispositivo Surface, baixe o **Tag.zipde ativos Surface** no [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=46703), extraia o arquivo zip e salve AssetTag.exe na pasta desejada (neste exemplo, C:\\assets).</span><span class="sxs-lookup"><span data-stu-id="b734f-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b734f-112">Para o Surface Pro X, use o aplicativo chamado **AssetTag_x86** no arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="b734f-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="b734f-113">Abra um console de comando como administrador e execute AssetTag.exe, inserindo o caminho completo da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="b734f-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="b734f-114">Reinicie a superfície.</span><span class="sxs-lookup"><span data-stu-id="b734f-114">Restart Surface.</span></span>

### <span data-ttu-id="b734f-115">Comandos da ferramenta de marca do ativo</span><span class="sxs-lookup"><span data-stu-id="b734f-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="b734f-116">Nos exemplos a seguir, AssetTag.exe é salvo em um diretório em um computador local (C:\assets).</span><span class="sxs-lookup"><span data-stu-id="b734f-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="b734f-117">Para obter a marca de ativos proposto, execute AssetTag-g.</span><span class="sxs-lookup"><span data-stu-id="b734f-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="b734f-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b734f-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="b734f-119">Para limpar a marca de ativos proposto, execute AssetTag-s.</span><span class="sxs-lookup"><span data-stu-id="b734f-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="b734f-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b734f-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="b734f-121">Para definir a marca de ativo proposto, execute AssetTag-s testassettag12.</span><span class="sxs-lookup"><span data-stu-id="b734f-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="b734f-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b734f-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="b734f-123">O valor da marca de ativos deve conter entre 1 e 36 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b734f-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="b734f-124">Os caracteres válidos incluem A-Z, a-z, 0-9, ponto final (.) e hífen (-).</span><span class="sxs-lookup"><span data-stu-id="b734f-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="b734f-125">Gerenciando marcas de ativos</span><span class="sxs-lookup"><span data-stu-id="b734f-125">Managing asset tags</span></span>

<span data-ttu-id="b734f-126">Você pode exibir a marca de ativos existente nas configurações de UEFI em informações do dispositivo (**painel de controle > recuperação > inicialização avançada > reiniciar agora**.)</span><span class="sxs-lookup"><span data-stu-id="b734f-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="b734f-127">A figura a seguir mostra os resultados da execução da ferramenta de etiqueta de ativos no Surface go.</span><span class="sxs-lookup"><span data-stu-id="b734f-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="b734f-128">Resultados da execução da ferramenta de marca do ativo Surface no Surface go.</span><span class="sxs-lookup"><span data-stu-id="b734f-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="b734f-129">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="b734f-129">Figure 1.</span></span>** <span data-ttu-id="b734f-130">Resultados da execução da ferramenta de marca do ativo Surface na superfície go</span><span class="sxs-lookup"><span data-stu-id="b734f-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="b734f-131">Como alternativa, você pode usar o WMI para consultar a marca de ativos existente em um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b734f-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="b734f-132">(Get-WmiObject-consulta "selecionar \* de Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="b734f-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="b734f-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b734f-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="b734f-134">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b734f-134">Using PowerShell</span></span>

<span data-ttu-id="b734f-135">Você pode usar o script abaixo como uma maneira de obter o valor proposto e interpretar os erros.</span><span class="sxs-lookup"><span data-stu-id="b734f-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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
