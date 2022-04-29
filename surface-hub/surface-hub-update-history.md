---
title: Histórico de atualizações do Surface Hub
description: Histórico de atualizações do Surface Hub
ms.assetid: d66a9392-2b14-4cb2-95c3-92db0ae2de34
keywords: ''
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: dpandre
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 9d48779195702952314baf07636749b70ce000ab
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497944"
---
# <a name="surface-hub-update-history"></a>Histórico de atualizações do Surface Hub

O Windows foi projetado para ser um serviço, o que significa que ele melhora automaticamente por meio de atualizações periódicas de software. Normalmente, você não precisa fazer nada para obter as atualizações mais recentes do Windows 10 — elas serão baixadas e instaladas sempre que estiverem disponíveis.

A maioria das atualizações do Windows se concentra em melhorias de desempenho e segurança. Na lista abaixo, a atualização mais recente do Windows com melhorias Surface Hub específicas é listada primeiro. As atualizações são cumulativas, portanto, instalar a atualização mais recente disponível do Windows (mesmo que ela não esteja na lista abaixo) garante que você também se beneficie de melhorias em todas as atualizações anteriores. Os aplicativos da Microsoft Store são atualizados por meio da Microsoft Store (gerenciados pelo administrador do Surface Hub do sistema). Os detalhes sobre as atualizações de aplicativos são fornecidos para cada aplicativo.

> [!TIP]
> Esta página é atualizada à medida que novas atualizações são lançadas. Consulte a página [Informações importantes do Surface Hub](https://support.microsoft.com/products/surface-devices/surface-hub) para obter tópicos relacionados às versões atuais e anteriores que podem exigir sua atenção.

## <a name="windows-10-team-2020-update-20h2"></a>Atualização do Windows 10 Team 2020 (20H2)

<details>
<summary>21 de abril de 2022 — atualização para a Equipe com base em KB5011831* (Build 19042.1679 do SO)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Correção que impede que "Encerrar Sessão" ative a mensagem "Seu dispositivo precisa de uma atualização. Reiniciando para concluir o processo..." e reiniciar subsequente em alguns cenários.
* Correção que garante que o [CSP do SurfaceHub](/windows/client-management/mdm/surfacehub-csp#deviceaccount) possa ser usado com políticas SyncML que configuram contas de dispositivos no formato `DOMAIN\username`.
 
Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5011831](https://support.microsoft.com/help/5011831)
</details>

<details>
<summary>22 de março de 2022 — atualização para Team com base em KB5011543* (Build do sistema operacional 19042.1620)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Adiciona a capacidade de os administradores [instalarem aplicativos Web progressivos](install-pwa-surface-hub.md) (PWAs).
* Resolve um problema em que os Surface Hubs ingressados no Azure AD ou configurados com uma conta de administrador local não podiam sincronizar o relógio do computador.
* Resolve um problema em que o uso de sugestões de credenciais de Reuniões e Arquivos com o aplicativo Authenticator podia forçar o usuário a repetir o processo de logon.
 
Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5011543](https://support.microsoft.com/help/5011543)
</details>

<details>
<summary>Atualização de 15 de fevereiro de 2022 — para a Equipe com base no KB5010415* (Build do sistema operacional 19042.1566)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações do Surface Hub são descritas no [Windows 10 Team 2020 Update 2](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-2) e também incluem o seguinte:

* Correção que permite que os serviços do Exchange sejam desabilitados durante a configuração da Conta de Dispositivo.
* Melhora a confiabilidade de alguns cenários de instalação da Conta de Dispositivo ao usar uma caixa de correio local do Exchange.
* Melhora a confiabilidade para alguns cenários de configuração de política de MDM ao usar o CSP do SurfaceHub.
* Melhora a confiabilidade para cenários de chamada de entrada ao usar o Skype for Business.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5010415](https://support.microsoft.com/help/5010415)
</details>

<details>
<summary>25 de janeiro de 2022 — atualização para Team com base no KB5009596* (Build 19042.1503 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Resolve um problema em que os Surface Hubs não podiam relatar dados para seus espaços de trabalho configurados do Azure Log Analytics.
* Resolve um problema em que iniciar uma reunião Skype for Business de uma tela de boas-vindas de um Surface Hub pode resultar em um cliente SfB totalmente maximizada que não era minimizado.
* Resolve um problema em que os Surface Hubs ingressados no Azure AD não preencheram previamente reuniões e arquivos de login com uma lista de convidados de reunião.
* Resolve um problema em que a rotação da senha da conta de dispositivo não pôde ser habilitada em alguns cenários locais.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5009596](https://support.microsoft.com/help/5009596)
</details>

<details>
<summary>21 de janeiro de 2022 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Atualização UEFI do Surface - 694.3924.768.0
  * Melhora a segurança e a estabilidade do sistema.
* Driver da Interface do Mecanismo de Gerenciamento Intel(R) - 2120.100.0.1085
  * Melhora a segurança e a estabilidade do sistema.
</details>

<details>
<summary>22 de novembro de 2021 — atualização para Team com base em KB5007253* (Build 19042.1387 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Correção que impõe um limite de 32 caracteres ao usar a política MDM para definir 'Nome Amigável' em um Surface Hub.
* Correção que corrige o comportamento da política MDM allowStorageCard quando revertida para um valor de 1 (cartões de armazenamento permitidos) de 0.
* Atualize para permitir que o navegador Edge (Chromium) acesse os mesmos locais de arquivo acessíveis no Explorador de Arquivos, incluindo uma unidade USB anexada.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5007253](https://support.microsoft.com/help/5007253)
</details>

<details>
<summary>30 de setembro de 2021 — KB5004196, KB5004198 e KB5004199</summary>

Essas atualizações para o Surface Hub entregam o cliente da sala Teams, o agente do Centro de Administração do Teams e o agente de Salas de Reunião Gerenciadas. Os principais recursos são descritos nas [na Sala do Teams no Surface Hub](surface-hub-teams-rooms.md).
 
Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
</details>

<details>
<summary>30 de setembro de 2021 — atualização para Team com base em KB5005611* (Com build do sistema operacional 19042.1266)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Substitui o Modo de Reunião 1 (Teams preferencial/SfB disponível) pela funcionalidade do Modo 2 (somente Teams), qualquer configuração pode ser usada, mas ambas têm o mesmo efeito.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5005611](https://support.microsoft.com/help/5005611)
</details>

<details>
<summary>1º de setembro de 2021 — atualização para Team com base em KB5005101* (Build 19042.1202 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub são descritas [na atualização 1 de 2020 do Windows 10 Team](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-1) e também incluem o seguinte:

* Melhora a confiabilidade de alguns cenários de instalação da Conta de Dispositivo ao usar uma caixa de correio local do Exchange.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5005101](https://support.microsoft.com/help/5005101)
</details>

<details>
<summary>29 de julho de 2021 — atualização para Team com base em KB5004296* (Build 19042.1151 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Atualize para o recurso "Coletar logs" para incluir dados de diagnóstico do Windows no formato csv.
* Correção que garante que a limpeza da Sessão Final remova completamente todos os dados relacionados ao Edge Chromium.
* Melhora alguns cenários de credenciais pessoais com Surface Hubs ingressados no Azure AD ao usar o aplicativo Authenticator.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5004296](https://support.microsoft.com/help/5004296)
</details>

<details>
<summary>10 de junho de 2021 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Atualização UEFI do Surface - 694.3751.768.0
  * Aborda a vulnerabilidade de segurança crítica e melhora a estabilidade do sistema.
* Atualização de firmware do Surface ME - 11.8.86.3877
  * Aborda a vulnerabilidade de segurança crítica e melhora a estabilidade do sistema.
* Driver da Interface do Mecanismo de Gerenciamento Intel(R) - 2102.100.0.1044
  * Aborda a vulnerabilidade de segurança crítica e melhora a estabilidade do sistema.
</details>

<details>
<summary>13 de abril de 2021 — atualização para Team com base em KB5001330* (Build 19042.928 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Resolve um problema em que alguns dispositivos Surface Hub estavam instalando apenas atualizações de segurança do Windows mensais, em vez de todas as Windows cumulativas.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB5001330](https://support.microsoft.com/help/5001330)
</details>

<details>
<summary>13 de março de 2021 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Driver de Bluetooth Intel(R) - 22.30.0.4
  * Melhora a segurança e a estabilidade do sistema.
* Driver gráfico Intel(R) - 27.20.100.8682
  * Melhora a segurança e a estabilidade do sistema.
* Driver Wi-Fi Intel(R) - 22.30.0.11
  * Melhora a segurança e a estabilidade do sistema.
</details>

<details>
<summary>2 de fevereiro de 2021 — atualização para Team com base em KB4598291* (Build 19042.789 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Correção que permite que a sincronização de calendário com Exchange funcione quando o UPN da conta de dispositivo não for igual a seu SMTP.
* Adiciona a capacidade de os administradores [desabilitarem o uso da Autenticação Moderna](/windows/client-management/mdm/surfacehub-csp#deviceaccount-exchangemodernauthenabled) durante a sincronização de calendário com o Exchange.
* Garante que os usuários do Surface Hub não sejam solicitados a inserir credenciais de proxy depois que o recurso "Usar credenciais de conta de dispositivo" tiver sido habilitado.
* Resolve um problema em que as Windows de atualização e atualização da Loja nunca seriam concluídas se um proxy que exigisse autenticação estivesse em uso.
* Melhora a confiabilidade do aplicativo Conexão durante cenários de ingestão com fio.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB4598291](https://support.microsoft.com/help/4598291)
</details>

<details>
<summary>15 de janeiro de 2021 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Atualização de firmware do Surface SMC - 3.93.139.0
* Atualização UEFI do Surface - 694.3473.768.0
</details>

<details>
<summary>11 de dezembro de 2020 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Atualização de firmware do Surface SMC - 3.92.139.0
* Atualização UEFI do Surface - 694.3447.768.0
</details>

<details>
<summary>30 de novembro de 2020 — atualização para Team com base em KB4586853* (Build 19042.662 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluem:

* Atualize para a página Configurações de Privacidade para fornecer opções adicionais.
* Resolve um problema em que as reuniões que já tinham sido iniciadas não eram exibidas na tela de boas-vindas/iniciar.
* Resolve um problema com a recuperação de nuvem para localidades não-en-US.
* Skype for Business
  * Melhora o desempenho de áudio direcional.
  * Sons reduzidos de "toque de caneta" ao usar a Caneta durante as chamadas Skype for Business.
* Melhora a confiabilidade ao se inscrever no programa Windows Insider.
* Melhora a confiabilidade do shell Windows Team.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo. *[KB4586853](https://support.microsoft.com/help/4586853)
</details>

<details>
<summary>24 de novembro de 2020 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Atualização de firmware do Surface SMC - 3.91.139.0
  * Melhore a confiabilidade de espera conectada.
* Atualização do Firmware do Surface Touch - 3.91.139.0
  * Aprimora a resposta de toque de espera conectada.
* Atualização do Firmware de Áudio USB do Surface - 3.91.139.0
* Atualização do Firmware da Caneta Surface - 3.91.139.0
</details>

<details>
<summary>27 de outubro de 2020 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Atualização de Firmware do Surface System Aggregator - 4.14.139.0
* Atualização UEFI do Surface - 694.3386.768.0
</details>

<details>
<summary>Windows 10 Team atualização 2020 para Surface Hub — Notas gerais de versão (com build 19042.572 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas no [histórico de atualizações do Windows 10,](https://support.microsoft.com/help/4581839/windows-10-update-history) são notadas na página "[Novidades na atualização do Windows 10 Team 2020](/surface-hub/surface-hub-2020-update-whats-new)".

Consulte a página "[Instalar atualização do Windows 10 Team 2020](/surface-hub/surface-hub-2020-update)" para obter mais informações sobre disponibilidade de atualização por região, método de distribuição e tipo de dispositivo.
</details>

## <a name="windows-10-team-creators-update-1703"></a>Atualização do Windows 10 Team Creators (1703)

<details>
<summary>1º de setembro de 2020 — atualização para Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Atualização de firmware do Surface SMC - 1.177.139.0
  * Melhora cenários de reparo de campo.
* Atualização do firmware do Surface SSD - 5.14.139.0
  * Melhora a estabilidade do sistema.
* Driver do Surface Serial Hub - 9.40.139.0
  * Melhora a estabilidade do sistema.
</details>

<details>
<summary>4 de maio de 2020 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Driver de áudio USB do Surface - 15.3.6.0
  * Melhora o desempenho de áudio direcional.
* Driver de áudio de exibição Intel(R) - 10.27.0.5
  * Melhora cenários de compartilhamento de tela.
* Driver gráfico Intel(R) - 26.20.100.7263
  * Melhora a estabilidade do sistema.
* Driver do Surface System - 1.7.139.0
  * Melhora a estabilidade do sistema.
* Atualização de firmware do Surface SMC - 1.176.139.0
  * Melhora a estabilidade do sistema.
</details>

<details>
<summary>28 de fevereiro de 2020 — atualização para o Surface Hub 2S</summary>

Essa atualização é específica do Surface Hub 2S e fornece as atualizações de driver e firmware descritas abaixo:

* Driver de Integração do Surface - 13.46.139.0 
  * Melhora os cenários de brilho de exibição.
* Driver da Interface do Mecanismo de Gerenciamento Intel(R) - 1914.12.0.1256
  * Melhora a estabilidade do sistema.
* Atualização de firmware do Surface SMC - 1.161.139.0
  * Melhora o desempenho da bateria da caneta.
* Atualização UEFI do Surface - 694.2938.768.0
  * Melhora a estabilidade do sistema.
</details>

<details>
<summary>11 de fevereiro de 2020 — atualização para Team com base em KB4537765* (Build 15063.2284 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve um problema em que o Hub 2S não pode ser ouvido bem por outros participantes durante chamadas do Skype for Business.
* Melhora a confiabilidade de alguns cenários de uso de idioma RTL, árabe, hebraico e outros no Surface Hub.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4537765](https://support.microsoft.com/help/4537765)
</details>

<details>
<summary>14 de janeiro de 2020 — atualização para Team com base em KB4534296* (Com build do sistema operacional 15063.2254)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve um problema com o conjunto de log para Microsoft Surface Hub 2S.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4534296](https://support.microsoft.com/help/4534296)
</details>

<details>
<summary>24 de setembro de 2019 — atualização para Team com base em KB4516059* (Build 15063.2078 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

 * Atualize para a página das configurações de recuperação do Surface Hub 2S para refletir com precisão as opções de recuperação.
 * Atualize para a tela de boas-vindas do Surface Hub 2S para melhorar a reconhecimento do dispositivo.
 * Resolvido um problema com o plano de fundo do shell do Windows Team exibindo incorretamente.
 * Resolvido um problema com persistência de layout do Menu Iniciar quando configurado usando a política MDM.
 * Corrigido um problema em Microsoft Edge que ocorre ao navegar em alguns sites internos.
 * Corrigido um problema em Skype for Business que ocorre ao apresentar no modo de tela inteira.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>17 de agosto de 2019 — atualização para Team com base em KB4512474* (Build 15063.2021 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

 * Garante que a Saída de Vídeo no Hub 2S seja padrão para o modo "Duplicado".
 * Melhora a confiabilidade de alguns cenários de uso de idioma árabe no Surface Hub.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4503289](https://support.microsoft.com/help/4503289)
 </details>

<details>
<summary>18 de junho de 2019 — atualização para Team com base em KB4503289* (Com build do sistema operacional 15063.1897)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve um problema que impede que um usuário entre em um dispositivo Microsoft Surface Hub com uma conta do Azure Active Directory. Esse problema ocorre porque uma sessão anterior não terminou com êxito.
* Adiciona suporte para conexões TLS 1.2 a provedores de identidade e Exchange em cenários de configuração de conta de dispositivo.
* Correções para melhorar a confiabilidade do Aplicativo de Diagnóstico de Hardware no Hub 2S. 
* Correção para melhorar a consistência da experiência de instalação da primeira vez no Hub 2S. 

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>28 de maio de 2019 — atualização para Team com base em KB4499162* (Build 15063.1835 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Garante que os usuários do Surface Hub não sejam solicitados a inserir credenciais de proxy depois que o recurso "Usar credenciais de conta de dispositivo" tiver sido habilitado.
* Resolve um problema em que as conexões Skype falham periodicamente porque o áudio/vídeo não está usando o proxy correto.
* Adiciona suporte ao TLS 1.2 em Skype for Business.
* Resolve uma falha de conexão SIP no cliente Skype quando o servidor Skype tem TLS 1.0 ou TLS 1.1 desabilitado.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4499162](https://support.microsoft.com/help/4499162)
</details>

<details>
<summary>25 de abril de 2019 — atualização para Team com base em KB4493436* (Com build do sistema operacional 15063.1784)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve o problema de sincronização de vídeo e áudio com alguns dispositivos USB que estão conectados ao Surface Hub.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4493436](https://support.microsoft.com/help/4493436)
</details>

<details>
<summary>27 de novembro de 2018 — atualização para Team com base no KB4467699* (Build 15063.1478 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve um problema que impede alguns usuários de fazer logon em "Minhas Reuniões e Arquivos".

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KBKB4467699](https://support.microsoft.com/help/KB4467699)
</details>

<details>
<summary>18 de outubro de 2018 — atualização para Team com base em KB4462939* (Build 15063.1418 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Correções Skype for Business: 
  * Resolve o problema de conexão do Skype for Business ao retomar a suspensão
  * Resolve o problema de conexão de rede do Skype for Business quando o dispositivo está conectado à Internet
  * Resolve a falha do Skype for Business ao pesquisar usuários do diretório
* Resolve um problema em que o Hub relata incorretamente “nenhuma conexão com a Internet” em ambientes de proxy corporativos.
* Implementou um recurso que permite que os clientes aceitem uma nova experiência do Quadro de Comunicações.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4462939](https://support.microsoft.com/help/4462939)
</details>

<details>
<summary>31 de agosto de 2018 — atualização para Team com base em KB4343889* (Build 15063.1292 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Adiciona suporte para o Microsoft Teams
* Resolve o problema de gerenciamento de tarefas com o registro do Intune
* Permite que os administradores desabilitem os serviços de Mensagens Instantâneas e Email para o Hub
* Correções adicionais de bugs e melhorias de confiabilidade para o Skype for Business para Surface Hub

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4343889](https://support.microsoft.com/help/4343889)
</details>

<details>
<summary>21 de junho de 2018 — atualização para Team com base em KB4284830* (Build 15063.1182 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Alteração de telemetria no suporte aos requisitos de RGPD no EMEA

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4284830](https://support.microsoft.com/help/KB4284830)
</details>

<details>
<summary>17 de abril de 2018 — atualização para Team com base em KB4093117* (Build 15063.1058 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve um problema de projeção com fio
* Habilita a atualização em massa para determinadas políticas de MDM (Gerenciamento de Dispositivo Móvel)
* Resolve o problema de discagem telefônica com chamadas internacionais
* Resolve o problema de resolução de imagem quando 2 Surface Hubs juntam-se à mesma reunião
* Resolve o erro de tratamento de certificados OMS (Operations Management Suite)
* Resolve um problema de segurança ao limpar no final de uma sessão
* Resolve o problema de Miracast, quando o Surface Hub é especificado para os canais de 149 a 165
  * Os canais 149 a 165 continuarão a ser inutilizáveis na Europa, Japão ou Israel devido a regulamentações governamentais regionais

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4093117](https://support.microsoft.com/help/4093117)
</details>

<details>
<summary>23 de fevereiro de 2018 — atualização para Team com base em KB4077528* (Build 15063.907 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolvido um problema em que as configurações do MDM não estavam sendo aplicadas corretamente
* Processo de limpeza aprimorado

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4077528](https://support.microsoft.com/help/4077528)
</details>

<details>
<summary>16 de janeiro de 2018 — atualização para Team com base em KB4057144* (Build 15063.877 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Adiciona a capacidade de gerenciar o layout do menu iniciar por meio do MDM
* Correção de bugs do MDM na configuração de rotação de senha

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4057144](https://support.microsoft.com/help/4057144)
</details>

<details>
<summary>12 de dezembro de 2017 — atualização para Team com base em KB4053580* (Build 15063.786 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve flashes de vídeo da câmera (lacrimejamentos ou piscações) durante chamadas no Skype for Business
* Resolve o problema de ID do SSD do Centro de Notificação

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4053580](https://support.microsoft.com/help/4053580)
</details>

<details>
<summary>14 de novembro de 2017 — atualização para Team com base em KB4048954* (Build 15063.726 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Atualização de recursos que permite que os clientes habilitem a autenticação de rede com fio 802,1x usando a política MDM.
* Uma atualização de recurso que permite que os usuários selecionem dinamicamente um aplicativo de sua escolha ao abrir um arquivo.
* Correção que garante que a limpeza da Sessão Final remova totalmente todas as conexões entre a conta do usuário e o dispositivo.
* Correção de desempenho que melhora o tempo de limpeza, bem como o tempo de conexão do Miracast.
* Introduz a utilização de Autenticação Fácil durante reuniões ad hoc.
* Correção que garante que os componentes do serviço usem o mesmo proxy configurado no dispositivo.
* Reduz e garante mais detalhadamente a telemetria transmitida pelo dispositivo, reduzindo a utilização de largura de banda.
* Habilita um recurso que permite que os usuários forneçam comentários à Microsoft após a conclusão de uma reunião.

Consulte o [guia de administração do Surface Hub](/surface-hub/) para habilitar/desabilitar recursos e serviços do dispositivo.
*[KB4048954](https://support.microsoft.com/help/4048954)
</details>

<details>
<summary>10 de outubro de 2017 — atualização para Team com base em KB4041676* (Build 15063.674 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Skype for Business
  * Resolve o problema que exigia uma reinicialização do dispositivo ao retornar da suspensão.
  * Corrige o problema em que os contatos externos não resolviam por meio da conta do hub online do Skype.
* PowerPoint
  * Corrige o problema em que algumas apresentações do PowerPoint não projetavam no Hub.
* Geral
  * Correção para resolver o problema em que a porta USB não poderia ser desabilitada pelo Administrador do Sistema.

*[KB4041676](https://support.microsoft.com/help/4041676)
</details>

<details>
<summary>12 de setembro de 2017 — atualização para Team com base em KB4038788* (Build 15063.605 do sistema operacional) </summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Segurança
  * Resolve o problema com o Bitlocker quando o dispositivo acorda da suspensão.
* Geral
  * Reduz a frequência/quantidade de telemetria de saúde do dispositivo, melhorando o desempenho do sistema.
  * Corrige o problema que impedia o dispositivo de coletar logs do sistema.

*[KB4038788](https://support.microsoft.com/help/4038788)
</details>

<details>
<summary>1º de agosto de 2017 — atualização para Team com base em KB4032188* (Build 15063.498 do sistema operacional)</summary>

* Skype for Business 
  * Resolve o problema de logon do Skype for Business, que exigia repetir ou reiniciar o sistema.
  * Resolve o tempo de reunião exibido incorretamente do Skype for Business.
  * Correções para melhorar a confiabilidade do Surface Hub do Skype for Business.

*[KB4032188](https://support.microsoft.com/help/4032188)
</details>

<details>
<summary>27 de junho de 2017 — atualização para Team com base em KB4022716* (Build 15063.442 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve falhas de driver NVIDIA que podem exigir o Surface Hub 84" em suspensão para ser desligado, exigindo uma reinicialização manual.
* Resolvido um problema em que alguns aplicativos não conseguem iniciar em um Surface Hub 84”.

*[KB4022716](https://support.microsoft.com/help/4022716)
</details>

<details>
<summary>13 de junho de 2017 — atualização para Team com base em KB4022725* (Build 15063.413 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Geral
  * Problemas resolvidos com a queda de tinta de caneta com canetas
  * Problema resolvido causando tempo estendido para a reunião de "limpeza"

*[KB4022725](https://support.microsoft.com/help/4022725)
</details>

<details>
<summary>24 de maio de 2017 — atualização para Team com base no KB4021573* (Build 15063.328 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Geral
  * Problema resolvido com retenção de configuração de proxy durante o problema de atualização

*[KB4021573](https://support.microsoft.com/help/4021573)
</details>

<details>
<summary>9 de maio de 2017 — atualização para Team com base em KB4016871* (Build 15063.296 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Geral
  * Problema ciclo de repouso/ativação
  * Vários problemas de redefinição e recuperação foram resolvidos
  * Resolução de um problema da guia histórico de atualização
  * Problema resolvido de inicialização do serviço Miracast
* Apps
  * Correção do erro de atualização do pacote de aplicativos

*[KB4016871](https://support.microsoft.com/help/4016871)
</details>

<details>
<summary>Atualização 1703 do Windows 10 Team Creators para Surface Hub — Notas gerais de versão (Build 15063.0 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Evoluindo a experiência de tela grande 
  * Carrossel de reunião aprimorado em boas-vindas e início
  * Participe de reuniões e termine a sessão diretamente do menu Iniciar
  * Os aplicativos podem utilizar mais da tela durante uma sessão
  * Controles Skype simplificados
  * Mecanismos aprimorados para fornecer comentários
* Acessar Meu Conteúdo Pessoal*
  * Login único pessoal da tela inicial ou de boas vindas
  * Participe de reuniões e termine a sessão diretamente do menu Iniciar
  * Acessar arquivos pessoais por meio OneDrive for Business diretamente de da tela inicial
  * Login do participante pré-preenchido
  * Fluxos de autenticação simplificados com o aplicativo "Autenticador" **
* Gerenciamento & implantação 
  * Experiência OOBE simplificada por meio do provisionamento em massa
  * Serviço de recuperação de dispositivo baseado em nuvem
  * Suporte a certificados de cliente corporativo
  * Suporte aprimorado de credenciais de proxy
  * Adicionado e /aprimorado o suporte à configuração de QoS (Qualidade de Serviço) do Skype
  * Adição da capacidade de definir o volume do dispositivo padrão em Configurações
  * Suporte aprimorado de MDM para [configurações do Surface Hub](/surface-hub/remote-surface-hub-management)
* Segurança aprimorada 
  * Adição da capacidade de restringir unidades USB somente ao BitLocker
  * Adição da capacidade de desabilitar portas USB por meio do MDM
  * Adição da capacidade de desabilitar a funcionalidade “retomar sessão” no tempo limite
  * Adição de suporte com fio 802.1x
* Áudio e projeção
  * Aprimoramentos do Áudio Dolby "Alto-falante humano"
  * Sons reduzidos de "toque de caneta" ao usar a Caneta durante chamadas do Skype for Business
  * Adicionado suporte para conexões da infraestrutura Miracast
* Correções de confiabilidade e desempenho
  * Vários problemas de redefinição e recuperação foram resolvidos
  * Resolvido problema de autenticação do Surface Hub Exchange ao utilizar certificados de cliente
  * Estabilidade aprimorada da conexão de rede e credenciais Wi-Fi 
  * Correção de problemas de replicação de áudio e sincronização do Miracast durante a reprodução de vídeo
  * Configuração incluída para desabilitar o comportamento de conexão automática

*O recurso de entrada única requer o uso do Office365 e OneDrive for Business **Consulte o Guia de Administração para requisitos de serviço

</details>

## <a name="windows-10-team-anniversary-update-1607"></a>Atualização de Aniversário do Windows 10 Team (1607)

<details>
<summary>14 de março de 2017 — atualização para Team com base em KB4013429* (Build 14393.953) do sistema operacional</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Geral
  * Correção de segurança do Explorador de Arquivos para impedir a navegação para locais de arquivos restritos
* Skype for Business
  * Correção para resolver latência durante o compartilhamento de tela com base na Área de Trabalho Remota

*[KB4013429](https://support.microsoft.com/help/4013429)
</details>

<details>
<summary>10 de janeiro de 2017 — atualização para Team com base em KB4000825* (Build 14393.693 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Seleção habilitada de layouts de teclado 106/109 para uso com teclados físicos japoneses

*[KB4000825](https://support.microsoft.com/help/4000825)
</details>

<details>
<summary>13 de dezembro de 2016 — atualização para Team com base no KB3206632* (Build 14393.576 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Resolve o problema de distorção de áudio de conexão com fio

*[KB3206632](https://support.microsoft.com/help/3206632)
</details>

<details>
<summary>4 de novembro de 2016 — atualização para Team com base no KB3200970* (Build 14393.447 do sistema operacional)</summary>

Esta atualização para a atualização de aniversário do Windows 10 Team (versão 1607) para Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Correções de bugs do Skype for Business para melhorar a confiabilidade

*[KB3200970](https://support.microsoft.com/help/3200970)
</details>

<details>
<summary>25 de outubro de 2016 — atualização para Team com base em KB3197954* (Build 14393.351 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Habilitando o novo recurso Suspensãono sistema operacional e no Bios para reduzir o consumo de energia do Surface Hub e melhorar sua confiabilidade a longo prazo
* Geral
  * Resolve cenários em que o teclado na tela às vezes não aparecia
  * Resolve a mudança de aplicativo de quadro de trabalho que ocorre ocasionalmente ao abrir a reunião agendada
  * Resolve problema que impedia administradores de alterar a senha do administrador local, depois que o dispositivo foi Redefinido
  * Alteração do BIOS resolvendo o problema com o controle da barra de status durante a redefinição do dispositivo
  * Atualização UEFI para resolver problemas de energia

*[KB3197954](https://support.microsoft.com/help/3197954)
</details>

<details>
<summary>11 de outubro de 2016 — atualização para Team com base no KB3194496* (Build 14393.222 do sistema operacional)</summary>

Essa atualização traz a atualização de aniversário do Windows 10 Team para Surface Hub e inclui melhorias de qualidade e correções de segurança. (Seu dispositivo estará executando o Windows 10 versão 1607 depois de instalado.) As principais atualizações Surface Hub, ainda não descritas no [histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Skype for Business
  * Melhorias de desempenho ao ingressar em reuniões, incluindo problemas ao ingressar em uma reunião usando contas federadas
  * Suporte para VBSS (Compartilhamento de Tela Baseada em Vídeo) agora disponível no Skype for Business para Surface Hub
  * Desconexão resolvida após 5 minutos de problema de tempo ocioso
  * Falha de compartilhamento de tela hub para hub do Skype
  * Melhorias no vídeo do Skype, incluindo:
    * Perda de vídeo durante a reunião com vários apresentadores de vídeo
    * Recorte de vídeo durante chamadas
    * Vídeo de chamada de saída não exibido para outros participantes
  * Problema resolvido com o erro de login UPN
  * Problema resolvido com o bloco de discagem durante o uso de chamadas SIP (Session Initiation Protocol)
* Quadro de Comunicações
  * Agora, o usuário pode salvar e lembrar sessões do quadro do OneDrive online (por meio da funcionalidade Compartilhar)
  * Aprimorada a inicialização do Quadro de Comunicações ao remover a caneta do encaixe
* Apps
  * Aplicativo de OneDrive pré-instalado, para acesso aos arquivos pessoais e de trabalho
  * Aplicativo Fotos pré-instalado, para exibir fotos e vídeos
  * Aplicativo PowerBI pré-instalado, para exibir painéis
  * Os aplicativos do Office – Word, Excel e PowerPoint – estão todos habilitados para tinta
  * O Edge no Surface Hub agora oferece suporte a sites baseados em Flash
* Geral
  * Seleção de Dispositivo de Áudio Habilitado (para Surface Hubs anexados usando dispositivos de áudio externos)
  * Suporte habilitado para HDCP no conector de saída DisplayPort
  * Alterações na interface do usuário do sistema para configurações de otimização de usabilidade (consulte [Guias de usuário e administrador](https://www.microsoft.com/surface/support/surface-hub) para obter detalhes adicionais)
  * Correções de bugs e otimizações de desempenho para acelerar o fluxo de login do Azure Active Directory 
  * Tempo significativamente aprimorado necessário para redefinir e restaurar Surface Hub
  * A interface do usuário do Windows Defender foi adicionada dentro das configurações
  * Toque de experiência do usuário aprimorado para iniciar
  * Suporte habilitado para projeção sem fio superior a 1080p por meio Miracast, em dispositivos com suporte
  * Resolvido estados de notificação falsa "Não há nenhuma conexão com a Internet" e "Os compromissos podem estar desatualizados" o desde o início
  * Confiabilidade aprimorada do teclado na tela
  * Suporte adicional para criar pacotes de provisionamento do Surface Hub usando o Designer de Configuração e Imagens do Windows (ICD) e uma solução de monitoramento Surface Hub aprimorada no OMS (Operations Management Suite)

*[KB3194496](https://support.microsoft.com/help/3194496)
</details>

## <a name="updates-for-windows-10-version-1511"></a>Atualizações do Windows 10 Versão 1511

<details>
<summary>4 de novembro de 2016 — atualização para Team com base no KB3198586* (Build 10586.679 do sistema operacional)</summary>

Essa atualização para o Windows 10 Team (versão 1511) para Surface Hub inclui melhorias de qualidade e correções de segurança que são descritas no [histórico de atualização do Windows 10.](https://support.microsoft.com/help/4018124/windows-10-update-history) Não há itens específicos do Surface Hub nesta atualização.

*[KB3198586](https://support.microsoft.com/help/3198586)
</details>

<details>
<summary>12 de julho de 2016 — atualização para Team com base no KB3172985* (Build 10586.494 do sistema operacional)</summary>

Esta atualização inclui aprimoramentos de qualidade e correções de segurança. Nenhum recurso novo do sistema operacional foi apresentado nesta atualização. As principais alterações específicas do Surface Hub (as que ainda não estão incluídas no [histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history)) incluem:

* Corrigido o problema que causava falhas no sistema Windows
* Corrigido o problema que causava falhas repetidas do Edge
* Corrigido o problema que causava falhas no serviço de pré-desligamento
* Corrigido o problema em que alguns dados do aplicativo não foram’ removidos corretamente após uma sessão
* Driver NFC Broadcom atualizado para melhorar o desempenho do NFC
* Driver Wi-Fi Marvell atualizado para melhorar o desempenho do Miracast
* Driver Nvidia atualizado para corrigir um bug de exibição no qual os dispositivos Surface Hub de 84" mostram conteúdo esmaecido ou difuso
* Vários problemas do Skype for Business corrigidos, incluindo: 
  * Problema que fez com que o Skype for Business se desconectasse durante as reuniões
  * Problema em que os usuários não podiam ingressar em reuniões quando o organizador da reunião estava em uma configuração federada
  * Habilitando o compartilhamento de aplicativos do Skype for Business
  * Problema que causou falhas no aplicativo Skype
* Adicionado um prompt em "Configurações" para informar aos usuários que o sistema operacional pode ficar corrompido se a redefinição do dispositivo for interrompida antes da conclusão

*[KB3172985](https://support.microsoft.com/help/3172985)
</details>

<details>
<summary>14 de junho de 2016 — atualização para o Team com base em KB3163018* (Build 10586.420 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. Nenhum recurso novo do sistema operacional foi apresentado nesta atualização. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Versão restrita. Consulte 12 de julho de 2016 — [KB3172985](https://support.microsoft.com/en-us/help/3172985) (Build 10586.494 do sistema operacional) para obter detalhes específicos do pacote Surface Hub

*[KB3163018](https://support.microsoft.com/help/3163018)
</details>

<details>
<summary>10 de maio de 2016 — atualização para Team com base em KB3156421* (Build do sistema operacional 10586.318)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. Nenhum recurso novo do sistema operacional foi apresentado nesta atualização. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Problema corrigido que impedia a instalação de determinados aplicativos da Loja (OneDrive)
* Problema corrigido que fez com que a entrada por toque parasse de responder em aplicativos

*[KB3156421](https://support.microsoft.com/help/3156421)
</details>

<details>
<summary>12 de abril de 2016 — atualização para Team com base no KB3147458* (Build 10586.218 do sistema operacional)</summary>

Essa atualização para o Surface Hub inclui melhorias de qualidade e correções de segurança. Nenhum recurso novo do sistema operacional foi apresentado nesta atualização. As principais atualizações Surface Hub, ainda não descritas [no histórico de atualização do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluem:

* Problema corrigido em que o nível de volume não era redefinido corretamente entre sessões

*[KB3147458](https://support.microsoft.com/help/3147458)
</details>

## <a name="related-topics"></a>Tópicos relacionados

* [Informações sobre versões do Windows 10](https://go.microsoft.com/fwlink/p/?LinkId=724328)
* [Atualização de novembro: perguntas frequentes sobre o Windows 10](https://windows.microsoft.com/windows-10/windows-update-faq)
* [Histórico de atualizações do Microsoft Surface](https://go.microsoft.com/fwlink/p/?LinkId=724327)
* [Histórico de atualizações do Microsoft Lumia](https://go.microsoft.com/fwlink/p/?LinkId=785968)
* [Obter o Windows 10](https://go.microsoft.com/fwlink/p/?LinkId=616447)
