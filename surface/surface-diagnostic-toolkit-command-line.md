---
title: Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327325"
---
# Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos

Executar o Surface Diagnostic Toolkit (SDT) em um prompt de comando requer o download do console do aplicativo SDT. Depois de instalado, você pode executar o SDT em um prompt de comando por meio do console de comando do Windows (cmd.exe) ou usando o Windows PowerShell, incluindo o IsE (Ambiente de Script Integrado) do PowerShell, que fornece suporte para a comcompleção automática de comandos, cópia/colar e outros recursos.  Para uma lista de dispositivos Surface com suporte no SDT, consulte [Implantar o Surface Diagnostic Toolkit for Business.](surface-diagnostic-toolkit-business.md)

>[!NOTE]
>Para executar o SDT usando comandos, você deve estar conectado à conta de Administrador ou conectado a uma conta que seja membro do grupo Administrador no dispositivo Surface.

## Executando o console do aplicativo SDT

Baixe e instale o console do aplicativo SDT na página [de download do Surface Tools for IT.](https://www.microsoft.com/download/details.aspx?id=46703) Você pode usar o prompt de comando do Windows (cmd.exe) ou o Windows PowerShell para: 

- Coletar todos os arquivos de log.
- Execute diagnósticos de saúde usando o Analisador de Práticas Práticas Melhores.
- Verifique se há atualizações de firmware ou driver ausentes.

>[!NOTE]
>Nesta versão, o console do aplicativo SDT dá suporte apenas a comandos únicos. A execução de várias opções de linha de comando requer a execução do exe do console separadamente para cada comando. 

Por padrão, os arquivos de saída são salvos no mesmo local do aplicativo de console. Consulte a tabela a seguir para ver uma lista completa de comandos.

Comando | Observações
--- | ---
-DataCollector "output file" | Coleta detalhes do sistema em um arquivo zip. "arquivo de saída" é o caminho do arquivo para criar o arquivo zip de detalhes do sistema.<br><br>**Exemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | Verifica várias configurações e indicadores de saúde no dispositivo. "arquivo de saída" é o caminho do arquivo para criar o relatório HTML.<br><br>**Exemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Verifica se há atualizações de firmware e/ou driver ausentes nos servidores online do Windows Update.<br><br>**Exemplo**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | Verifica informações de garantia no dispositivo (válidas ou inválidas). O "arquivo de saída" opcional é o caminho do arquivo para criar o arquivo xml. <br><br>**Exemplo**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"


>[!NOTE]
>Para executar o console do aplicativo SDT remotamente em dispositivos de destino, você pode usar uma ferramenta de gerenciamento de configuração, como o Microsoft Endpoint Configuration Manager. Como alternativa, você pode criar um arquivo .zip contendo o aplicativo de console e os comandos de console apropriados e implantar de acordo com os processos de distribuição de software da sua organização. 

## Executando o Analisador de Práticas Práticas Melhores 

Você pode executar testes BPA nos principais componentes, como BitLocker, Inicialização Segura e Trusted Platform Module (TPM) e, em seguida, a saída dos resultados para um arquivo compartilhável. A ferramenta gera uma série de tabelas com títulos codificados por cores e descritores de condição, juntamente com orientações sobre como abordar a resolução do problema. 

- Verde indica que o componente está em execução em uma condição ideal (ideal).
- Laranja indica que o componente não está em execução em uma condição ideal (não ideal).
- Vermelho indica que o componente está em um estado anormal. 

### Exemplo de saída de resultados BPA

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o BitLocker está habilitado na unidade do sistema.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Proteção 1</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>É altamente recomendável habilitar o BitLocker para proteger seus dados.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Inicialização Segura</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a Inicialização Segura está habilitada.</td></tr>
<tr><td><strong>Valor:</strong></td><td>True</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>É altamente recomendável habilitar a Inicialização Segura para proteger seu computador.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Trusted Platform Module</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Garante que o TPM está funcional.</td></tr>
<tr><td><strong>Valor:</strong></td><td>True</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Sem um TPM funcional, funções baseadas em segurança, como o BitLocker, podem não funcionar corretamente.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de Espera Conectado</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o Modo de Espera Conectado está habilitado.</td></tr>
<tr><td><strong>Valor:</strong></td><td>True</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>O modo de espera conectado permite que um dispositivo Surface receba atualizações e notificações enquanto não está sendo usado. Para uma melhor experiência, o Modo de Espera Conectado deve estar habilitado.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o Bluetooth está habilitado.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Habilitado</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de Depuração</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o sistema operacional está no modo de depuração.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>A opção de inicialização de depuração habilita ou desabilita a depuração de kernel do sistema operacional Windows. A habilitação dessa opção pode causar instabilidade no sistema e impedir a reprodução de mídia protegida por DRM (gerenciamento de direitos digitais).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Assinatura de teste</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a Assinatura de Teste está habilitada.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Assinatura de teste é uma configuração de inicialização do Windows que só deve ser usada para testar drivers de pré-lançamento.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Plano De Energia Ativo</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o plano de energia correto está ativo.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Balanceado</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>É altamente recomendável usar o plano de energia "Balanceado" para maximizar a produtividade e a duração da bateria.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o dispositivo está atualizado com as atualizações do Windows.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Microsoft Silverlight (KB4023307), Atualização de Definição para Windows Defender Antivírus - KB2267602 (Definição 1.279.1433.0)</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="ff9500">Não ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Atualizar para as janelas mais recentes garante que você está no firmware e nos drivers mais recentes. É recomendável sempre manter seu dispositivo atualizado</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espaço livre no disco rígido</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se há pouco espaço livre no disco rígido.</td></tr>
<tr><td><strong>Valor:</strong></td><td>66%</td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Para melhor desempenho, seu disco rígido deve ter pelo menos 10% de sua capacidade como espaço livre.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Dispositivos que não estão funcionando</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Lista de dispositivos que não funcionam no Gerenciador de Dispositivos.</td></tr>
<tr><td><strong>Valor:</strong></td><td></td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Dispositivos que não estão funcionando no Gerenciador de Dispositivos podem causar problemas imprevisíveis com dispositivos Surface, como, mas não limitado a, nenhuma economia de energia para o componente de hardware respectivo.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Monitor Externo</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se há um monitor externo que possa ter problemas de compatibilidade.</td></tr>
<tr><td><strong>Valor:</strong></td><td></td></tr>
<tr><td><strong>Condição:</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Diretrizes:</strong></td><td>Verifique com o fabricante do equipamento original a compatibilidade com o dispositivo Surface.</td></tr>
</table>
