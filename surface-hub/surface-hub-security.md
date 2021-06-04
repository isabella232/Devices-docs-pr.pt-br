---
title: Visão geral da segurança do Surface Hub
description: Esta página explica o design profundo da proteção do Surface Hub e descreve os aperfeiçoamentos de segurança do Surface Hub 2S, proteções de segurança sem fio e recursos relacionados.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: coveminer
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 01/26/2021
ms.localizationpriority: High
ms.openlocfilehash: 446166618161fc54a77bab94b2d61ad85359a082
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304844"
---
# Visão geral da segurança do Surface Hub

O Surface Hub fornece uma experiência de dispositivo bloqueada com o firmware da plataforma personalizada executando o sistema operacional Windows 10 Team. O dispositivo resultante tem o único Kiosk (quiosque seguro) tradicional, só executa o que é necessário, além de fornecer uma moderna aparência. Desenvolvido para dar suporte a uma experiência de usuário colaborativo avançada, o Surface Hub está protegido contra ameaças à segurança em constante evolução.

Desenvolvido no Windows 10, o Surface Hub oferece segurança moderna de nível empresarial, permitindo que os administradores de TI imponham a proteção de dados com BitLocker, módulo de plataforma confiável 2,0 (TPM), além da segurança de nuvem com o Windows Defender (também conhecido como Microsoft Defender).

##  <a name="defense-in-depth-security"></a>Segurança de defesa intensa

Os protocolos de segurança serão iniciados assim que o Surface Hub estiver ativado. A partir do nível do firmware, o Surface Hub carregará apenas o sistema operacional e seus componentes em resposta a várias verificações de segurança. O Surface Hub emprega uma estratégia chamada Defense em profundidade que envolve a camada de subcomponentes de defesa independente para proteger todo o sistema no caso de falha parcial. Essa prática setorial tem sido comprovadamente muito eficaz para reduzir explorações unilaterais potencias e desvantagens dos subcomponentes.

A UEFI (Unified Extensible Firmware Interface) moderna é configurada estaticamente e com segurança pela Microsoft para inicializar apenas um sistema operacional Windows 10 Team autenticado do armazenamento interno.  Cada linha de código que é executada no Surface Hub tem sua assinatura verificada antes da execução. Somente os aplicativos assinados pela Microsoft, como parte do sistema operacional ou instalado pela Microsoft Store, podem ser executados no Surface Hub. Os aplicativos que não atenderem a esses requisitos serão bloqueados.

Os sistemas de segurança do Surface Hub incluem os seguintes:

- **Defesas em tempo de inicialização.** Carrega apenas componentes do sistema operacional confiável do Surface Hub.
- **Defesas do sistema operacional.** Protege contra a execução de softwares ou códigos indesejados ou mal-intencionados.
- **Defesas de Interface do usuário.** Fornece uma interface do usuário que é segura para os usuários finais, evitando o acesso a atividades potencialmente arriscadas, como executar executáveis a partir da linha de comando.

###  <a name="boot-time-defenses"></a>Defesas em tempo de inicialização.

O SoC tem um processador de segurança separado de cada outro núcleo. Quando você inicia o Surface Hub pela primeira vez, apenas o processador de segurança é iniciado antes de qualquer coisa poder ser carregada.

![Fases de inicialização do Hub mostrando proteções do processador de segurança](images/hub-sec-1.png)

#### Inicialização Segura

A inicialização segura é usada para verificar se os componentes do processo de inicialização, incluindo drivers e o sistema operacional, são validados em relação a um banco de dados de assinaturas válidas e conhecidas. No Surface Hub, uma assinatura específica da plataforma deve ser validada antes do sistema operacional autorizado do Windows Team seja carregado. Isso ajuda a evitar que os ataques de um sistema cloanado ou modificado, com um código mal-intencionado, sejam exibidos de forma diferente.  Para saber mais, confira [visão geral da inicialização segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

###  <a name="operating-system-defenses"></a>Defesas do sistema operacional

Uma vez que o sistema operacional seja verificado à medida que a Microsoft e o Surface Hub concluírem com êxito o processo de inicialização, o dispositivo investigará o código executável. Nossa abordagem para a proteção do sistema operacional envolve identificar a assinatura do código de todos os executáveis, permitindo que somente os que passarem nossas restrições sejam carregados no tempo de execução. Esse método de assinatura de código permite que o sistema operacional verifique o autor e confirme que o código não foi alterado antes de ser executado no dispositivo.

O Surface Hub usa um recurso de assinatura de código conhecido como UMCI (integridade de código do modo de usuário) no Windows Application Control (antes conhecido como o Device Guard). As configurações de política estão definidas para permitir apenas aplicativos que atendem a um dos seguintes requisitos:

- Aplicativos da plataforma universal do Windows (Microsoft Store) [oficialmente certificados](https://docs.microsoft.com/windows/uwp/publish/the-app-certification-process).
- Aplicativos assinados com a CA (autoridade de certificação) da Microsoft Production Root exclusiva, que só pode ser assinada por funcionários da Microsoft com acesso autorizado a esses certificados.
- Aplicativos assinados com o Surface Hub Production Root C.

O arquivo de configuração é assinado usando a AC da Microsoft Production Root, projetada para impedir que restrições sejam removidas ou modificadas por terceiros. Todos os outros executáveis neste ponto são simplesmente bloqueados no nível do tempo de execução do sistema operacional e impedidos de acessar a capacidade de processamento. Essa redução da superfície de ataque fornece as seguintes proteções:

- Nenhum modo de documento herdados
- Nenhum mecanismo de script herdado
- Nenhuma linguagem de marcação vetorial
- Nenhum objeto auxiliar do navegador
- Nenhum controle ActiveX

Além de bloquear códigos não assinados ou assinados incorretamente por meio do UMCI, o Surface Hub usa o controle do aplicativo Windows para bloquear componentes do Windows, como o prompt de comando, PowerShell e gerenciador de tarefas. Essas proteções refletem um recurso fundamental de design do Surface Hub como um dispositivo de computação seguro. Para obter mais informações, consulte:

- [Visão geral do controle de aplicativo](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Controle de aplicativos do Windows Defender e proteção de integridade de código baseada na virtualização](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

###  <a name="user-interface-defenses"></a>Defesas de Interface do usuário.

Enquanto as proteções de tempo de inicialização e proteções de bloqueio do sistema operacional oferecem segurança fundamental, a interface do usuário fornece uma camada adicional projetada para reduzir ainda mais o risco. Para impedir que um código mal-intencionado atinja o dispositivo por meio de drivers, o Surface Hub não baixa os drivers avançados para dispositivos plug and play (PnP). Os dispositivos que utilizam drivers básicos, como unidades flash USB ou periféricos de Surface Hub certificados (auto-falantes, microfones, câmeras) funcionam como esperado, mas os sistemas avançados, como impressoras, não.

As proteções da interface do usuário também simplificam a interface do usuário, evitando ainda mais a execução de software ou código mal-intencionado. Os seguintes elementos da interface de usuário do Surface Hub a segurança principal fornecida pela assinatura de código:

- **Explorador de arquivos.** O Surface Hub tem um explorador de arquivos personalizado que permite o acesso rápido a músicas, vídeos, documentos, imagens e pastas de downloads, sem expor os usuários a arquivos de programas ou sistemas. Outros locais no disco rígido local não estão disponíveis por meio do explorador de arquivos. Além disso, vários tipos de arquivo em execução, como. exe, e arquivos de instalação. msi não podem ser executados, fornecendo outra camada de segurança contra executáveis possivelmente mal-intencionados.

- **Iniciar e todos os aplicativos.** Os componentes iniciar e todos os aplicativos do Surface Hub não expõem o acesso ao comando prompt, ao PowerShell ou a outros componentes do Windows bloqueados por meio do controle de aplicativo. Além disso, a funcionalidade de executar do Windows geralmente acessada em computadores na caixa de pesquisa é desativada para o Surface Hub.

##  <a name="security-enhancements-in-surface-hub-2s"></a>Aperfeiçoamentos de segurança no Surface Hub 2S

Embora o Surface Hub e o Surface Hub 2S executem o mesmo software de sistema operacional, alguns recursos exclusivos do Surface Hub 2S fornecem recursos adicionais de gerenciamento e segurança, permitindo que os administradores de TI realizem as seguintes tarefas:

- Gerenciar as configurações de UEFI com o SEMM
- Recuperar o Hub com o USB inicializável
- Proteger a conta do dispositivo com rotação de senha

###  <a name="manage-uefi-settings-with-semm"></a>Gerenciar as configurações de UEFI com o SEMM

A UEFI é uma interface entre as partes da plataforma de hardware subjacente e o sistema operacional. No Surface Hub, uma implementação de UEFI personalizada permite o controle granular sobre essas configurações e impede que qualquer entidade que não seja da Microsoft altere as configurações de UEFI do dispositivo, ou a inicialização em uma unidade removível para modificar ou alterar o sistema operacional.

Em um nível alto, durante o processo de provisionamento de fábrica, a UEFI do Surface Hub é pré-configurada para habilitar a inicialização segura e está definida para ser inicializada somente a partir da unidade de estado sólido interna (SSD), com acesso aos menus UEFI bloqueados e os atalhos removidos. Isso lacra o acesso à UEFI e assegura que o dispositivo só possa ser inicializado no sistema operacional Windows Team instalado no Surface Hub.

Quando gerenciado por meio do SEMM (modo de gerenciamento do Microsoft Surface Enterprise), os administradores de TI podem implantar configurações UEFI em dispositivos de Hub em uma organização. Isso inclui a capacidade de habilitar ou desabilitar componentes de hardware internos, proteger as configurações de UEFI contra alterações por usuários não autorizados e ajustar as configurações de inicialização.

![Configurações de UEFI do Surface Hub](images/hub-sec-2.png)

Os administradores podem implementar dispositivos SEMM e Surface Hub 2S registrados usando o [configurador UEFI do Surface baixado](https://www.microsoft.com/download/details.aspx?id=46703). Para saber mais, confira [proteger e gerenciar o Surface Hub 2S com SEMM e o UEFII](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm).
Protegido usando um certificado para proteger a configuração contra violação ou remoção não autorizada, o SEMM habilita o gerenciamento dos seguintes componentes:

- LAN com fio
- Câmera
- Bluetooth
- Wi-Fi
- Sensor de ocupação
- Inicialização de IPv6 para PXE
- Inicialização alternativa
- Bloqueio da ordem de inicialização
- Inicialização USB
- Interface de página inicial UEFI
    - Devices
    - Iniciar
    - Data/Hora

    
###  <a name="recover-hub-with-bootable-usb"></a>Recuperar o Hub com o USB inicializável

O Surface Hub 2S permite que os administradores reinstalem o dispositivo para as configurações de fábrica usando uma imagem de recuperação até 20 minutos. Geralmente, você só precisaria fazer isso se o Surface Hub não estiver mais funcionando. A recuperação também será útil se você tiver perdido a chave do BitLocker ou se não tiver mais credenciais de administrador para o aplicativo de configurações.

###  <a name="harden-device-account-with-password-rotation"></a>Proteger a conta do dispositivo com rotação de senha

O Surface Hub usa uma conta de dispositivo, também conhecida como "conta room", para se autenticar com o Exchange, o Microsoft Teams e outros serviços. Quando você habilita a rotação de senha, o Hub 2S gera automaticamente uma nova senha a cada sete dias, consistindo em 15-32 caracteres com uma combinação de letras maiúsculas e minúsculas, números e caracteres especiais. Como ninguém conhece a senha, a rotação de senha da conta do dispositivo reduz de forma eficaz o risco associado contra erros humanos e possíveis ataques de segurança de engenharia social.

##  <a name="windows-10-enterprise-grade-security"></a>Segurança de nível empresarial do Windows 10

Além de configurações e recursos específicos do Surface Hub abordados neste documento, o Surface Hub também usa os recursos de segurança padrão do Windows 10. Como por exemplo:

- **BitLocker**. A SSD do Surface Hub é equipada com BitLocker para proteger os dados no dispositivo. A configuração acompanha os padrões do setor. Para obter mais informações, consulte [visão geral do BitLocker](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).
- **Windows Defender.** O mecanismo anti-malware do Windows Defender é executado continuamente no Surface Hub e funciona para corrigir automaticamente ameaças encontradas no Surface Hub. O mecanismo do Windows Defender recebe atualizações automaticamente e é gerenciável por meio das ferramentas de gerenciamento remoto para os administradores de TI. O mecanismo do Windows Defender é um exemplo perfeito de nossa abordagem de defesa de profundidade: se um Malware puder encontrar uma maneira de fornecer uma solução de segurança baseada em codificadores de código central, ele será pego aqui. Para obter mais informações, confira [controle de aplicativos do Windows Defender e proteção de integridade de código baseada na virtualização](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control).
- **Drivers plug and play.** Para impedir que um código mal-intencionado atinja o dispositivo por meio de drivers, o Surface Hub não baixa os drivers avançados para dispositivos PnP. Isso permite que os dispositivos que utilizam drivers básicos, como unidades flash USB, funcionem como esperado enquanto bloqueiam sistemas mais avançados, como impressoras.
- **Módulo de plataforma confiável 2.0.** O Surface Hub tem um módulo de plataforma confiável (dTPM) padrão do setor para gerar e armazenar hashes e chaves criptográficas. O dTPM protege as teclas usadas para a verificação de fases de inicialização, a chave mestra BitLocker, a tecla de logon sem senha e muito mais. O dTPM atende à certificação [de nível 2 FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation), o padrão de segurança do governo dos Estados Unidos e é compatível com [critérios comuns](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria) certificação usada em todo o mundo.

##  <a name="wireless-security-for-surface-hub"></a>Segurança sem fio para Surface Hub

O Surface Hub usa a tecnologia Wi-Fi Direct/Miracast e os padrões associados 802.11, WPA2 (Wi-Fi Protected Access) e WPS (Wireless Protected Setup). Como o dispositivo dá suporte apenas para WPS (em vem de WPA2 PSK (Pre-Shared Key) ou WPA2 Enterprise), problemas tradicionalmente associados à criptografia 802.11 são simplificados por padrão.

O Miracast faz parte do padrão Vídeo Wi-Fi, que por si só é compatível com o protocolo Wi-Fi Direct. Esses padrões têm suporte em dispositivos móveis modernos para compartilhamento de tela e colaboração.

Wi-Fi Direct ou Wi-Fi "ponto a ponto" (P2P) é um padrão lançado pela Wi-Fi Alliance para redes "Ad-Hoc". Isso permite que os dispositivos com suporte se comuniquem diretamente e criem grupos de redes sem a necessidade de um ponto de acesso Wi-Fi tradicional ou uma conexão de Internet.

A segurança do Wi-Fi Direct é fornecida pelo WPA2 usando o padrão WPS. Os dispositivos podem ser autenticados usando o PIN numérico, um botão de envio físico ou virtual, ou uma mensagem fora da faixa, usando a comunicação em breve. O Surface Hub dá suporte a ambos os botões de envio por padrão, assim como métodos PIN. Para saber mais, confira [Como o Surface Hub resolve problemas de segurança do Wi-Fi Direct](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct).

##  <a name="learn-more"></a>Saiba mais

- [Visão geral da inicialização segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

- [Visão geral do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

- [Visão geral do controle de aplicativo](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Proteger e gerenciar o Surface Hub 2S com SEMM e UEFI](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)

- [Como o Surface Hub resolve problemas de segurança do Wi-Fi Direct](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)

- [Controle de aplicativos do Windows Defender e proteção de integridade de código baseada na virtualização](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

- [Ferramentas Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703)

- [FIPS 140-2 nível 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)

- [Certificações de critérios comuns](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)
