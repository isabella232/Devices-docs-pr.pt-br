---
title: Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos
description: Como executar o kit de ferramentas de diagnóstico de Surface em um console de comando
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
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830176"
---
# Executar o Kit de Ferramentas de Diagnóstico Surface para Empresas usando comandos

A execução do SDT (Kit de ferramentas de diagnóstico de Surface) em um prompt de comando requer o download do console de aplicativo padrão. Depois de instalado, você pode executar o SDT em um prompt de comando via console de comando do Windows (cmd.exe) ou usando o Windows PowerShell, incluindo o ambiente de script integrado do PowerShell (ISE), que oferece suporte à conclusão automática de comandos, copiar/colar e outros recursos.  Para obter uma lista de dispositivos de superfície com suporte no SDT, consulte [implantar o kit de ferramentas de diagnóstico de superfície para empresas](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Para executar o SDT usando comandos, você deve estar conectado à conta de administrador ou conectado a uma conta que seja membro do grupo administrador em seu dispositivo Surface.

## Executando o console de aplicativo SDT

Baixe e instale o console de aplicativo SDT na [página Surface Tools para download de ti](https://www.microsoft.com/download/details.aspx?id=46703). Você pode usar o prompt de comando do Windows (cmd.exe) ou o Windows PowerShell para: 

- Coletar todos os arquivos de log.
- Execute o diagnóstico de integridade usando o analisador de práticas recomendadas.
- Verifique se há atualizações de firmware ou drivers ausentes na atualização.

>[!NOTE]
>Nesta versão, o console do aplicativo SDT suporta somente comandos únicos. Executar várias opções de linha de comando requer a execução do console exe separadamente para cada comando. 

Por padrão, os arquivos de saída são salvos no mesmo local que o aplicativo do console. Veja a tabela a seguir para obter uma lista completa de comandos.

Comando | Observações
--- | ---
-Datacoletor "arquivo de saída" | Coleta detalhes do sistema em um arquivo zip. "arquivo de saída" é o caminho de arquivo para criar arquivo zip de detalhes do sistema.<br><br>**Exemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-BPA "arquivo de saída" | Verifica várias configurações e indicadores de integridade no dispositivo. "arquivo de saída" é o caminho de arquivo para criar o relatório HTML.<br><br>**Exemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Verifica se há firmware ausente e/ou atualizações de driver em servidores online do Windows Update.<br><br>**Exemplo**:<br>Microsoft.Surface.Diagnostics.App.Console.exe-windowsupdate
-garantia "arquivo de saída" | Verifica as informações de garantia no dispositivo (válidas ou inválidas). O "arquivo de saída" opcional é o caminho do arquivo para criar o arquivo XML. <br><br>**Exemplo**: <br>Microsoft.Surface.Diagnostics.App.Console.exe – garantia "warranty.xml"


>[!NOTE]
>Para executar o console do aplicativo SDT remotamente em dispositivos de destino, você pode usar uma ferramenta de gerenciamento de configuração, como o Gerenciador de configuração do Microsoft Endpoint. Como alternativa, você pode criar um arquivo. zip que contém o aplicativo console e os comandos de console apropriados e implantar os processos de distribuição de software de sua organização de acordo com o aplicativo. 

## Executando o analisador de práticas recomendadas 

Você pode executar testes de BPA em componentes essenciais como BitLocker, inicialização segura e Trusted Platform Module (TPM) e, em seguida, produzir os resultados em um arquivo compartilhável. A ferramenta gera uma série de tabelas com títulos codificados por cores e descritores de condição juntamente com orientações sobre como abordar a solução do problema. 

- Verde indica que o componente está em execução em uma condição ideal (ideal).
- Laranja indica que o componente não está em execução em uma condição ideal (não ideal).
- Vermelho indica que o componente está em um estado anormal. 

### Exemplo de saída de resultados de BPA

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o BitLocker está habilitado na unidade do sistema.</td></tr>
<tr><td><strong>Valores</strong></td><td>Proteção ativada</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>É altamente recomendável habilitar o BitLocker para proteger seus dados.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Inicialização Segura</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a inicialização segura está habilitada.</td></tr>
<tr><td><strong>Valores</strong></td><td>True</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>É altamente recomendável habilitar a inicialização segura para proteger seu computador.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Trusted Platform Module</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Garante que o TPM seja funcional.</td></tr>
<tr><td><strong>Valores</strong></td><td>True</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>Sem um TPM funcional, as funções baseadas em segurança como o BitLocker podem não funcionar corretamente.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Conectado em espera</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a conexão em espera está habilitada.</td></tr>
<tr><td><strong>Valores</strong></td><td>True</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>Conectado em espera permite que um dispositivo de superfície Receba atualizações e notificações enquanto não está sendo usado. Para obter a melhor experiência, o standby conectado deve ser habilitado.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o Bluetooth está habilitado.</td></tr>
<tr><td><strong>Valores</strong></td><td>Habilitado</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de depuração</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o sistema operacional está no modo de depuração.</td></tr>
<tr><td><strong>Valores</strong></td><td>Normal</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>A opção de inicialização de depuração habilita ou desabilita a depuração de kernel do sistema operacional Windows. Habilitar essa opção pode causar instabilidade do sistema e impedir a reprodução de mídia protegida do DRM (direitos digitais managemend).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Assinatura de teste</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se a assinatura de teste está habilitada.</td></tr>
<tr><td><strong>Valores</strong></td><td>Normal</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>O teste de assinatura é uma configuração de inicialização do Windows que só deve ser usada para testar os drivers de pré-lançamento.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Plano de energia ativo</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o plano de energia correto está ativo.</td></tr>
<tr><td><strong>Valores</strong></td><td>Equilibrada</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>É altamente recomendável usar o plano de energia "balanceado" para maximizar a produtividade e a vida útil da bateria.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se o dispositivo está atualizado com as atualizações do Windows.</td></tr>
<tr><td><strong>Valores</strong></td><td>Microsoft Silverlight (KB4023307), atualização de definição para Windows Defender Antivirus-KB2267602 (definição 1.279.1433.0)</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="ff9500">Não é ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>A atualização para o Windows mais recente verifica se você está usando o firmware e os drivers mais recentes. Recomendamos sempre manter seu dispositivo atualizado</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espaço livre em disco rígido</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se há pouco espaço livre no disco rígido.</td></tr>
<tr><td><strong>Valores</strong></td><td>66%</td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>Para obter o melhor desempenho, seu disco rígido deve ter pelo menos 10% da capacidade de espaço livre.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Dispositivos não funcionais</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Lista de dispositivos não funcionais no Gerenciador de dispositivos.</td></tr>
<tr><td><strong>Valores</strong></td><td></td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>Os dispositivos não funcionais no Gerenciador de dispositivos podem causar problemas imprevisíveis com dispositivos de superfície como, mas não se limitando a, sem economia de energia para o respectivo componente de hardware.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Monitor externo</font></th></tr>
<tr><td><strong>Descrição:</strong></td><td>Verifica se há um monitor externo que pode ter problemas de compatibilidade.</td></tr>
<tr><td><strong>Valores</strong></td><td></td></tr>
<tr><td><strong>Problema</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Orienta</strong></td><td>Verifique se o fabricante do equipamento original tem compatibilidade com o seu dispositivo Surface.</td></tr>
</table>
