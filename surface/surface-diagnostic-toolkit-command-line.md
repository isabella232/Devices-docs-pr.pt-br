---
title: Executar o console de aplicativo de linha de comando com o Surface Diagnostic Toolkit for Business
description: Como executar o Surface Diagnostic Toolkit em um console de comando
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: bdd91df1f1ce105ecd19ea15e78bd9dc29d0ee95
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448464"
---
# <a name="run-command-line-app-console-with-surface-diagnostic-toolkit-for-business"></a>Executar o console de aplicativo de linha de comando com o Surface Diagnostic Toolkit for Business

Executar o Surface Diagnostic Toolkit (SDT) em um prompt de comando requer o download do console do aplicativo SDT. Depois de instalado, você pode executar o SDT em um prompt de comando por meio do console de comando Windows (cmd.exe) ou usando o Windows PowerShell, incluindo o Ambiente integrado de Scripts do PowerShell (ISE), que fornece suporte para a comcompleção automática de comandos, cópia/colar e outros recursos.  Para uma lista de dispositivos Surface com suporte no SDT, consulte [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Para executar o SDT usando comandos, você deve estar conectado à conta administrador ou entrar em uma conta que seja membro do grupo Administrador em seu dispositivo Surface.

## <a name="running-sdt-app-console"></a>Executando o console do aplicativo SDT

1. Baixe e instale o console do aplicativo SDT na página de [download do Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).

- Para dispositivos Intel/AMD, baixe: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0.exe**
- Para ARM, baixe: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0_x86.exe**

2. Use o prompt Windows de comando (cmd.exe) ou Windows PowerShell para:

- Coletar todos os arquivos de log
- Executar diagnósticos de saúde usando o Analisador de Práticas Práticas Melhores
- Verificar atualizações de firmware ou driver ausentes

>[!NOTE]
>Nesta versão, o console do aplicativo SDT dá suporte apenas a comandos únicos. Executar várias opções de linha de comando requer a execução do console exe separadamente para cada comando.

Por padrão, os arquivos de saída são salvos no mesmo local que o aplicativo de console. Consulte a tabela a seguir para ver uma lista completa de comandos.

Comando | Observações
--- | ---
-DataCollector "arquivo de saída" | Coleta detalhes do sistema em um arquivo zip. "arquivo de saída" é o caminho do arquivo para criar arquivo zip de detalhes do sistema.<br><br>**Exemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "arquivo de saída" | Verifica várias configurações e indicadores de saúde no dispositivo. "arquivo de saída" é o caminho do arquivo para criar o relatório HTML.<br><br>**Exemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Verifica Windows atualizar servidores online para ver se há atualizações de firmware e/ou driver ausentes.<br><br>**Exemplo**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | Verifica as informações de garantia no dispositivo (válido ou inválido). O "arquivo de saída" opcional é o caminho do arquivo para criar o arquivo xml. <br><br>**Exemplo**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"

>[!NOTE]
>Para executar o console de aplicativo SDT remotamente em dispositivos de destino, você pode usar uma ferramenta de gerenciamento de configuração, como Microsoft Endpoint Configuration Manager. Como alternativa, você pode criar um arquivo .zip que contém o aplicativo de console e os comandos de console apropriados e implantar de acordo com os processos de distribuição de software da sua organização.

## <a name="running-best-practice-analyzer"></a>Executando o Analisador de Práticas Práticas Práticas

Você pode executar testes BPA em componentes principais, como BitLocker, Inicialização Segura e Módulo de Plataforma Confiável (TPM) e, em seguida, a saída dos resultados para um arquivo compartilhável. A ferramenta gera uma série de tabelas com títulos codificados por cores e descritores de condição, juntamente com orientações sobre como abordar a resolução do problema.

- Verde indica que o componente está sendo executado em uma condição ideal (ideal).
- Laranja indica que o componente não está em execução em uma condição ideal (não ideal).
- Vermelho indica que o componente está em um estado anormal.

### <a name="sample-bpa-results-output"></a>Exemplo de saída de resultados BPA

<table>
<tr><th colspan="2">BitLocker</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o BitLocker está habilitado na unidade do sistema.</td></tr>
<tr><td><strong>Valor: </strong></td><td>Proteção on</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>É altamente recomendável habilitar o BitLocker para proteger seus dados.</td></tr>
</table>

<table>
<tr><th colspan="2">Inicialização Segura</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a Inicialização Segura está habilitada.</td></tr>
<tr><td><strong>Valor: </strong></td><td>True</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>É altamente recomendável habilitar a Inicialização Segura para proteger seu computador.</td></tr>
</table>

<table>
<tr><th colspan="2">Trusted Platform Module</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Garante que o TPM está funcional.</td></tr>
<tr><td><strong>Valor: </strong></td><td>True</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Sem um TPM funcional, funções baseadas em segurança, como o BitLocker, podem não funcionar corretamente.</td></tr>
</table>

<table>
<tr><th colspan="2">Espera conectada</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a espera conectada está habilitada.</td></tr>
<tr><td><strong>Valor: </strong></td><td>True</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>A espera conectada permite que um dispositivo Surface receba atualizações e notificações enquanto não está sendo usado. Para ter a melhor experiência, a espera conectada deve ser habilitada.</td></tr>
</table>

<table>
<tr><th colspan="2">Bluetooth</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se Bluetooth está habilitado.</td></tr>
<tr><td><strong>Valor: </strong></td><td>Habilitada</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2">Modo de depuração</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o sistema operacional está no modo Depuração.</td></tr>
<tr><td><strong>Valor: </strong></td><td>Normal</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>A opção de inicialização de depuração habilita ou desabilita a depuração de kernel do Windows operacional. A habilitação dessa opção pode causar instabilidade no sistema e impedir que mídias protegidas por DRM (gerenciamento de direitos digitais) possam ser reprodução.</td></tr>
</table>

<table>
<tr><th colspan="2">Assinatura de teste</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a Assinatura de Teste está habilitada.</td></tr>
<tr><td><strong>Valor: </strong></td><td>Normal</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>A Assinatura de Teste é Windows configuração de inicialização que deve ser usada apenas para testar drivers de pré-lançamento.</td></tr>
</table>

<table>
<tr><th colspan="2">Plano de Energia Ativa</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o plano de energia correto está ativo.</td></tr>
<tr><td><strong>Valor: </strong></td><td>Balanced</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>É altamente recomendável usar o plano de energia "Balanceado" para maximizar a produtividade e a duração da bateria.</td></tr>
</table>

<table>
<tr><th colspan="2">Windows Update</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o dispositivo está atualizado com Windows atualizações.</td></tr>
<tr><td><strong>Valor: </strong></td><td>Microsoft Silverlight (KB4023307), Atualização de Definição para Windows Defender Antivírus - KB2267602 (Definição 1.279.1433.0)</td></tr>
<tr><td><strong>Condição:</strong></td><td>Não é ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>A atualização para as janelas mais recentes garante que você está no firmware e drivers mais recentes. É recomendável manter sempre seu dispositivo atualizado</td></tr>
</table>

<table>
<tr><th colspan="2">Espaço livre no Disco Rígido</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se há pouco espaço livre no disco rígido.</td></tr>
<tr><td><strong>Valor: </strong></td><td>66%</td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Para melhor desempenho, seu disco rígido deve ter pelo menos 10% de sua capacidade como espaço livre.</td></tr>
</table>

<table>
<tr><th colspan="2">Dispositivos que não funcionam</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Lista de dispositivos que não estão funcionando no Gerenciador de Dispositivos.</td></tr>
<tr><td><strong>Valor: </strong></td><td></td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Dispositivos não funcionando no Gerenciador de Dispositivos podem causar problemas imprevisíveis com dispositivos Surface, como, mas não limitados a, nenhuma economia de energia para o componente de hardware respectivo.</td></tr>
</table>

<table>
<tr><th colspan="2">Monitor Externo</th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se há um monitor externo que pode ter problemas de compatibilidade.</td></tr>
<tr><td><strong>Valor: </strong></td><td></td></tr>
<tr><td><strong>Condição:</strong></td><td>Ideal</td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Verifique com o fabricante do equipamento original a compatibilidade com o dispositivo Surface.</td></tr>
</table>
