---
title: Monitorar o Microsoft Surface Hub
description: O monitoramento de dispositivos Microsoft Surface Hub é ativado por meio do Microsoft Operations Management Suite (OMS).
ms.assetid: 1D2ED317-DFD9-423D-B525-B16C2B9D6942
ms.reviewer: ''
manager: laurawi
keywords: monitorar o Surface Hub, Microsoft Operations Management Suite OMS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 108f24036a0e02295cf2a5588bb6b51e517eba8d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830647"
---
# Monitorar o Microsoft Surface Hub

O monitoramento de dispositivos Microsoft Surface Hub é ativado por meio do Microsoft Operations Management Suite (OMS). O [Operations Management Suite](https://go.microsoft.com/fwlink/?LinkId=718138) é uma solução de gerenciamento de TI da Microsoft que ajuda você a gerenciar e proteger sua infraestrutura de TI inteira, incluindo os Surface Hubs.


O Surface Hub é oferecido como uma solução de Log Analytics no OMS, permitindo que você colete e exiba dados de uso e confiabilidade em todos os seus Surface Hubs. Use a solução Surface Hub para:
- Inventariar seus Surface Hubs.
- Exibir um instantâneo dos dados de uso e confiabilidade para reuniões do Skype, projeção com e sem fio e aplicativos em seus Surface Hubs.
- Criar alertas personalizados para responder rapidamente caso seus Surface Hubs relatem problemas de hardware ou software.

## Adicionar o Surface Hub ao Operations Management Suite

1. **Entre no Operations Management Suite (OMS)**. Você pode usar uma conta da Microsoft ou uma conta Corporativa ou de Estudante para criar um espaço de trabalho. Se sua empresa já estiver usando o Azure Active Directory (Azure AD), use uma conta Corporativa ou de Estudante quando entrar no OMS. Usar uma conta Corporativa ou de Estudante permite que você use identidades do Azure AD para gerenciar permissões no OMS.
2. **Crie um novo espaço de trabalho do OMS**. Insira um nome para o espaço de trabalho, selecione a região do espaço de trabalho e forneça o endereço de email que você deseja associar ao espaço de trabalho. Selecione **Criar**.
3. **Vincule a assinatura do Azure ao seu espaço de trabalho**. Se sua organização já tiver uma assinatura do Azure, você poderá vinculá-la ao espaço de trabalho. Observe que talvez seja necessário solicitar acesso ao administrador do Azure da organização.

    > [!NOTE] 
    > Se sua organização não tiver uma assinatura do Azure, crie uma nova ou selecione a assinatura do Azure OMS padrão na lista. O espaço de trabalho é aberto.

4. **Adicione a solução Surface Hub**. Na Galeria de Soluções, selecione o bloco **Surface Hub** e, em seguida, selecione **Adicionar** na página de detalhes da solução. A solução agora fica visível no seu espaço de trabalho.

## Usar o painel do Surface Hub
Na página **Visão geral** no espaço de trabalho do OMS, clique no bloco Surface Hub para ver o painel do Surface Hub. Use o painel para obter um instantâneo dos dados de uso e confiabilidade em todos os seus Surface Hubs. Clique em cada exibição no painel para ver dados detalhados, modificar a consulta conforme desejado e criar alertas.

> [!NOTE]
> A maioria desses modos de exibição mostra dados dos últimos 30 dias, mas isso está sujeito à política de retenção de dados de sua assinatura.

**Ativar Surface Hubs**

Use esse modo de exibição para obter um inventário de todos os seus Surface Hubs. Uma vez conectado ao OMS, cada Surface Hub periodicamente envia um evento de "pulsação" ao servidor. Esse modo de exibição mostra Surface Hubs que relataram uma pulsação nas últimas 24 horas.

<!--
**Skype meetings**

Use this view to get usage data for Skype over the past 30 days. The graph shows the total number of Skype Meetings started across your Surface Hubs, and a breakdown between scheduled meetings, ad hoc meetings, and PSTN calls.
-->
 
**Projeção sem fio**

Use esse modo de exibição para obter dados de uso e confiabilidade para projeção sem fio nos últimos 30 dias. O gráfico mostra o número total de conexões sem fio em todos os Surface Hubs, o que indica se as pessoas em sua organização estão usando esse recurso. Se for um número baixo, ele poderá sugerir uma necessidade de oferecer treinamento para ajudar as pessoas na organização a aprender como se conectar sem fio a um Surface Hub.
 
Além disso, o gráfico mostra uma divisão de conexões bem-sucedidas e malsucedidas. Se você vir um alto número de conexões malsucedidas, os dispositivos podem não dar suporte adequadamente à projeção sem fio usando Miracast. Para obter o melhor desempenho, a Microsoft sugere que os dispositivos executem um driver WDI Wi-Fi e um driver gráfico WDDM 2.0. Use o modo de exibição de detalhes para saber se problemas de projeção sem fio são comuns com dispositivos específicos.
 
Quando uma conexão falhar, os usuários também poderão fazer o seguinte se estiverem usando um notebook ou um telefone Windows:
- Remova o dispositivo emparelhado de **Configurações** > **Dispositivos** > **Dispositivos conectados** e tente se conectar novamente.
- Reinicialize o dispositivo.
 
**Projeção com fio**

Use esse modo de exibição para obter dados de uso e confiabilidade para projeção com fio nos últimos 30 dias. Se o gráfico mostrar um alto número de conexões malsucedidas, isso pode indicar um problema de conectividade em seu pipeline audiovisual. Por exemplo, se você usa um repetidor HDMI ou um painel de controle central, talvez eles precisem ser reiniciados.
 
**Uso de aplicativos**

Use esse modo de exibição para obter dados de uso de aplicativos em seus Surface Hubs nos últimos 30 dias. Os dados são provenientes de inicializações de aplicativos nos Surface Hubs, não incluindo o Skype for Business. Esse modo de exibição ajuda você a entender quais aplicativos do Surface Hub são mais valiosos em sua organização. Se você está implantando novos aplicativos de linha de negócios em seu ambiente, isso também pode ajudá-lo a entender a frequência com que eles estão sendo usados.
 
**Falhas de aplicativos**

Use esse modo de exibição para obter dados de confiabilidade de aplicativos em seus Surface Hubs nos últimos 30 dias. Os dados são provenientes de falhas de aplicativos nos Surface Hubs. Esse modo de exibição ajuda você a detectar e notificar os desenvolvedores sobre o comportamento inadequado de aplicativos nativos e de linha de negócios.
 
**Consultas de exemplo**

Use isso para criar alertas personalizados com base em um conjunto recomendado de consultas. Os alertas o ajudam a responder rapidamente se os seus Surface Hubs relatarem problemas de software ou hardware. Para obter mais informações, consulte [Configurar alertas usando consultas de exemplo](#set-up-alerts-with-sample-queries).

## Configurar alertas com consultas de exemplo

Use alertas para responder rapidamente se os seus Surface Hubs relatarem problemas de software ou hardware. As regras de alerta automaticamente executam pesquisas de log de acordo com uma agenda, e executam uma ou mais ações se os resultados corresponderem a critérios específicos. Para obter mais informações, consulte [Alertas em Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/).
 
A solução Log Analytics do Surface Hub vem com um conjunto de consultas de exemplo para ajudá-lo a configurar os alertas apropriados e entender como resolver problemas que você possa encontrar. Use-os como ponto de partida para planejar sua estratégia de monitoramento e suporte.

Esta tabela descreve as consultas de exemplo na solução Surface Hub:

| Tipo de alerta | Impacto | Correção recomendada | Detalhes |
| ---------- | ------ | ----------------------- | ------- |
| Software   | Erro  | **Reinicialize o dispositivo**. <br> Reinicialize manualmente ou usando o [Provedor de serviços de configuração de reinicialização](https://msdn.microsoft.com/library/windows/hardware/mt720802(v=vs.85).aspx). <br> Sugira que isso seja feito entre reuniões para minimizar o impacto para as pessoas da organização. | Condições de gatilho: <br> - Um processo crítico no sistema operacional Surface Hub, como o shell, a projeção ou o Skype, trava ou não responde. <br> - O dispositivo não relatou uma pulsação nas últimas 24 horas. Isso pode acontecer devido a um problema de conectividade de rede, uma falha de hardware relacionada à rede ou um erro no sistema de relatório de dados de diagnóstico. |
| Software   | Erro  | **Verifique seu serviço do Exchange**. <br> Verifique: <br> - O serviço está disponível. <br> - A senha da conta de dispositivo está atualizada. Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter detalhes.| Dispara quando há um erro de sincronização do calendário do dispositivo com o Exchange. |
| Software   | Erro  | **Verifique seu serviço Skype for Business**. <br> Verifique: <br> - O serviço está disponível. <br> - A senha da conta de dispositivo está atualizada. Consulte [Gerenciamento de senhas](password-management-for-surface-hub-device-accounts.md) para obter detalhes. <br> - O nome de domínio do Skype for Business está configurado corretamente. Consulte [Configurar um nome de domínio](use-fully-qualified-domain-name-surface-hub.md). | Dispara quando o Skype apresenta falha na conexão. |
| Software   | Erro  | **Redefina o dispositivo**. <br> Isso leva algum tempo; portanto, você deve colocar o dispositivo offline. <br> Para obter mais informações, consulte [Redefinição do dispositivo](device-reset-surface-hub.md).| Dispara quando há um erro de limpeza de dados do usuário e do aplicativo no final de uma sessão. Quando essa operação falha repetidamente, o dispositivo é bloqueado para proteger os dados do usuário. Você deve redefinir o dispositivo para continuar. |
| Hardware   | Aviso | **Nenhuma**. Indica impacto insignificante na funcionalidade.| Dispara quando há um erro com qualquer um dos componentes de hardware a seguir: <br> - Slots de caneta virtual <br> - Driver NFC <br> - Driver de hub USB <br> - Driver Bluetooth <br> - Sensor de proximidade <br> - Desempenho gráfico (driver de placa de vídeo) <br> - Unidade de disco rígido incompatível <br> - Nenhum teclado/mouse detectado |
| Hardware   | Erro | **Contate o suporte da Microsoft**. <br> Indica o impacto na funcionalidade principal (por exemplo, a conectividade de Internet, toque, projeção e Skype). <br> **Observação** Alguns eventos, como a pulsação, incluem o número de série do dispositivo que você pode usar ao contatar o suporte.| Dispara quando há um erro com qualquer um dos componentes de hardware a seguir. <br> **Componentes que afetam o Skype**: <br> - Driver de alto-falante <br> - Driver de microfone <br> - Driver de câmera <br> **Componentes que afetam a projeção com fio e sem fio**: <br> - Driver de touchback com fio <br> - Driver de ingestão com fio <br> - Driver de adaptador sem fio <br> - Erro do Wi-Fi Direct <br> **Outros componentes**: <br> - Driver de digitalizador de toque <br> - Erro de adaptador de rede (não relatado ao OMS)|

**Para configurar um alerta**
1. Na solução Surface Hub, selecione uma das consultas de exemplo.
2. Modifique a consulta conforme desejado. Consulte a referência da pesquisa Log Analytics para saber mais.
3. Clique em **Alerta** na parte superior da página para abrir a tela **Adicionar Regra de Alerta**. Consulte [Alertas no Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/) para obter detalhes sobre as opções para configurar o alerta.
4. Clique em **Salvar** para concluir a regra de alerta. Ela começará a ser executada imediatamente.

## Registrar seu Surface Hub

Para que o Surface Hub se conecte a e registre-se no serviço OMS, ele deve ter acesso ao número da porta de seus domínios e às URLs. Esta tabela lista as portas de que o OMS precisa. Para obter mais informações, consulte [Definir as configurações de proxy e firewall no Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-proxy-firewall/).

>[!NOTE]
>Atualmente, o Surface Hub não oferece suporte para o uso de um servidor proxy para se comunicar com o serviço OMS.

| Recurso do agente              | Portas | Ignorar a inspeção HTTPS? |
| --------------------------- | ----- | ------------------------ |
| *.ods.opinsights.azure.com  | 443   | Sim |
| *.oms.opinsights.azure.com  | 443   | Sim |
| *.blob.core.windows.net     | 443   | Sim |
| ods.systemcenteradvisor.com | 443   | Não  |

O Microsoft Monitoring Agent, usado para conectar dispositivos ao OMS, é integrado ao sistema operacional do Surface Hub; portanto, não é necessário instalar clientes adicionais para conectar o Surface Hub ao OMS.
 
Uma vez que o espaço de trabalho do OMS esteja configurado, há várias maneiras de registrar seus dispositivos Surface Hub:
- [Aplicativo Configurações](#enroll-using-the-settings-app)
- [Pacote de provisionamento](#enroll-using-a-provisioning-package)
- [Provedor MDM](#enroll-using-a-mdm-provider), como o Microsoft Intune e o Configuration Manager
 
Você precisará da ID de espaço de trabalho e da chave primária do seu espaço de trabalho OMS. Você pode obter essas informações no portal do OMS.
 
### Registrar usando o aplicativo Configurações

**Para registrar usando o aplicativo Configurações**

1. No Surface Hub, inicie **Configurações**.
2. Insira as credenciais de administrador de dispositivo quando solicitado.
3. Selecione **Este dispositivo**e navegue até **Gerenciamento de dispositivos**.
4. Em **Monitoramento**, selecione **Definir configurações do OMS**.
5. Na caixa de diálogo Configurações do OMS, selecione **Habilitar monitoramento**.
6. Digite a ID e a chave primária do seu espaço de trabalho do OMS. Você pode obter essas informações no portal do OMS.
7. Clique em **OK** para concluir a configuração.
 
Uma caixa de diálogo de confirmação aparecerá informando se a configuração do OMS foi ou não aplicada com êxito ao dispositivo. Se foi, o dispositivo começará a enviar dados ao OMS.

### Registrar usando um pacote de provisionamento
Você pode usar um pacote de provisionamento para registrar seu Surface Hub. Para obter mais informações, consulte [Criar pacotes de provisionamento](provisioning-packages-for-certificates-surface-hub.md).
 
### Registrar usando um provedor MDM
Você pode registrar o Surface Hub no OMS usando o CSP SurfaceHub. O Intune e o Configuration Manager oferecem experiências internas para ajudar a criar modelos de política para o Surface Hub. Para obter mais informações, consulte [Gerenciar configurações com um provedor de MDM (Surface Hub)](manage-settings-with-mdm-for-surface-hub.md).

## Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





