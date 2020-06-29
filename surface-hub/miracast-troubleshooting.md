---
title: Solução de problemas do Miracast no Surface Hub
description: Saiba como resolver problemas com o Miracast no Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 96c7c42fe0176f275a8657165d88bf447e57772b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831166"
---
# Solução de problemas do Miracast no Surface Hub

O Surface Hub dá suporte à projeção sem fio por meio do protocolo de Miracast. A maioria dos monitores e adaptadores sem fio disponíveis atualmente usa a implementação original de Miracast. O Surface Hub usa uma versão um pouco diferente do Miracast, conhecido como **Proprietário de grupo autônomo do Miracast (AGO)**. É uma etapa de solução de problemas comum quando projeção sem fio ao Surface Hub falha ao testar a projeção sem fio em outro monitor ou adaptador. No entanto, na maioria dos casos, esses dispositivos não estão usando o Miracast AGO e não lidam com projeção sem fio da mesma maneira que o Surface Hub.

No Miracast tradicional, o dispositivo de projeção conectará o ponto de acesso configurado pelo monitor habilitado para Miracast e, em seguida, o monitor enviará o tráfego de volta para o dispositivo de projeção usando o canal de rede do dispositivo de projeção. Miracast AGO é um processo de conexão em duas etapas:

- A primeira etapa é uma conexão inicial usando 2,4 GHz. 
- Após esse handshake inicial, o dispositivo de projeção envia o tráfego para o monitor usando as configurações de canal sem fio no monitor. Se o Surface Hub estiver conectado a uma rede Wi-Fi, ao ponto de acesso, ele usará o mesmo canal como a rede conectada, caso contrário, ele usará o canal de Miracast de Configurações.

Em geral, existem dois tipos de problemas com o Miracast ao Surface Hub: [conexão](#connect-issues) e [desempenho](#performance-issues). Em ambos os casos, é uma boa ideia obter uma visão geral da atividade de rede sem fio no local do Surface Hub. Executar uma ferramenta de verificação de rede mostrará o uso de canal e de redes disponíveis no ambiente.

## Problemas de conexão

Certifique-se de que o Wi-Fi e o Miracast estarem habilitados nas Configurações no Surface Hub. 

Se você executou uma verificação de rede, você deve ver o Surface Hub Miracast listado como um ponto de acesso. Se a rede Miracast do Surface Hub aparecer na verificação, mas não for possível vê-la como um dispositivo disponível, você poderá tentar ajustar o canal Miracast usado pelo Surface Hub. 

Quando o Surface Hub é conectado a uma rede Wi-Fi ele usa as mesmas configurações de canal como o ponto de acesso Wi-Fi para o seu ponto de acesso de Miracast. Para fins de solução de problemas, desconecte o Surface Hub de quaisquer redes Wi-Fi (mas mantenha habilitado para Wi-Fi), para que você possa controlar o canal usado para Miracast. Você pode selecionar manualmente o canal de Miracast em Configurações. Você precisará reiniciar o Surface Hub após cada alteração. De modo geral, você desejará usar canais que não mostrem utilização pesada da verificação de rede.

Também é possível que o problema de conexão possa ser o resultado de um problema no dispositivo de conexão. Se o dispositivo de projeção estiver executando o Windows, ele deve ser Windows 8.1 ou mais recente para oferecer suporte completo do Miracast. Novamente, para solução de problemas, desconecte o dispositivo de projeção de quaisquer redes Wi-Fi. Isso eliminará qualquer alternação de canal entre o canal do ponto de acesso e o canal de Miracast definido no Surface Hub. Além disso, algumas configurações de política de grupo e o firewall podem ser vinculados a uma rede Wi-Fi.

### Verificar drivers

Também é uma boa ideia garantir que os drivers mais recentes e as atualizações estejam instalados no dispositivo de projeção. No Gerenciador de Dispositivos, abra o adaptador Wi-Fi e o adaptador de vídeo e verifique se há uma versão de driver atualizada. [Hotfix 3120232](https://support.microsoft.com/help/3120232/poor-wireless-performance-on-5-ghz-connections-on-surface-pro-3-and-surface-3) é altamente recomendável para Surface Pro 3 e Surface Pro 4 se eles tiverem em uma unidade de Wi-Fi mais antiga. 

### Verifique se há suporte para Miracast

Em seguida, certifique-se de que o Miracast é compatível com o dispositivo. 

1. Pressione a tecla Windows + R e digite `dxdiag`. 
2. Clique em "salvar todas as informações". 
3. Abra o dxdiag.txt salvo e localize **Miracast**. Ele deve dizer **Disponíveis, com a HDCP**. 
    
### Verificar firewall
    
O firewall do Windows pode bloquear o tráfego do Miracast. O teste mais simples é desabilitar o firewall e testar a projeção. Se o Miracast funcionar com o firewall desabilitado, adicione uma exceção para

    C:\Windows\System32\WUDFHost.exe
    Allow In/Out connections for TCP and UDP, Ports: All.

### Verificar configurações de política de grupo

Em dispositivos ingressados em domínio, a política de grupo também pode bloquear o Miracast. 

1. Use a tecla Windows + R e digite `rsop.msc` para executar o snap-in do **conjunto de políticas resultante**. Isso lhe mostrará as políticas atuais aplicadas ao computador. 
2. Reveja **Configuração do Computador** > **Configurações do Windows** > **Configurações de Segurança** > **Políticas da rede Wi-Fi (IEEE 802.11)**. Deve haver uma configuração de políticas sem fio. 
3. Clique duas vezes na configuração de políticas sem fio e uma caixa de diálogo será exibida. 
4. Abra a guia **Permissões de rede** e selecione **Permitir que todos criem todos os perfis de usuário**.

### Verificar logs de eventos

O último lugar para verificar é nos logs de eventos. Eventos de Miracast serão registrados para **Wlanautoconfig**. Isso é verdadeiro no Surface Hub e no dispositivo de projeção. Se exportar logs do Surface Hub, você poderá visualizar o Wlanautoconfig do Surface Hub na pasta **WindowsEventLog** . Erros no log de eventos podem fornecer alguns detalhes adicionais sobre onde a conexão falha.

## Problemas de desempenho

Depois da projeção sem fio estar conectada, é possível ver os problemas de desempenho que causam latência. Isso geralmente é um resultado de saturação geral do canal ou uma situação que causa a troca de canal. 

Para saturação de canal, consulte a verificação de rede e tente usar canais com menos tráfego.

A mudança de canal é causada quando o adaptador Wi-Fi precisa enviar o tráfego em vários canais. Determinados canais suportam a seleção de frequência dinâmica (DFS). DFS é usado nos canais 49 até 148. Alguns drivers de Wi-Fi mostrarão desempenho ruim quando conectado a um canal DFS. Se você estiver vendo um desempenho ruim do Miracast enquanto estiver conectado a um canal DFS, tente a projeção em um canal não DFS. Surface Hub e projeção do dispositivo devem usar canais não DFS.

Se o Surface Hub e o dispositivo de projeção estiverem ambos conectados à rede Wi-Fi, mas com pontos de acesso e canais diferentes, isso forçará o Surface Hub e o dispositivo de projeção a alternar de canal enquanto estiver conectado com o Miracast. Isso resultará em projeto sem fio ruim e baixo desempenho de rede via Wi-Fi. A alternância de canal afetará o desempenho de todo o tráfego sem fio, não apenas projeção sem fio. 

Alternância de canal também ocorrerá se o dispositivo de projeção estiver conectado a uma rede Wi-Fi usando um canal diferente do canal que o Surface Hub usa para Miracast. Portanto, uma prática recomendada é definir o canal Miracast do Hub do Surface para o mesmo canal que o ponto de acesso mais comumente usado. 

Se houver várias redes de Wi-Fi ou pontos de acesso no ambiente, algumas variações de canal são inevitáveis. Isso é melhor resolvido garantindo que todos os drivers de Wi-Fi estejam atualizados.

## Contatar o Suporte

Se tiver dúvidas ou precisar de ajuda, você pode [criar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection).
