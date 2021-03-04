---
title: Noções básicas do sistema operacional (Surface Hub)
description: Este tópico explica os aspectos exclusivos do sistema operacional Windows 10 Team e como ele difere do Windows 10 Enterprise.
keywords: histórico de alterações
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: f3ffcc46912fba3313e4489f5713b6ffcacf2d8a
ms.sourcegitcommit: 5c904229a0257297be7f724c264e484d2c4b5168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387476"
---
# <a name="operating-system-essentials-surface-hub"></a>Noções básicas do sistema operacional (Surface Hub)

O sistema operacional do Surface Hub, o Windows 10 Team, é baseado no Windows 10 Enterprise, fornecendo suporte avançado para gerenciamento empresarial, segurança e outros recursos. No entanto, existem diferenças importantes entre eles. Enquanto a edição Enterprise foi criada para computadores, o Windows 10 Team foi projetado desde o início para telas grandes e salas de reunião. Quando você avaliar requisitos de segurança e gerenciamento do Surface Hub, é melhor considerá-lo como um novo sistema operacional. Este artigo destina-se a ajudar a destacar as principais diferenças entre o Windows 10 Team no Surface Hub e no Windows 10 Enterprise, e o que significam as diferenças para sua organização.

A partir de setembro de 2020, os clientes têm a opção de migrar para o Windows 10 Pro ou Enterprise no Surface Hub 2S. Para saber mais, consulte o seguinte:

- [Anunciando a disponibilidade do Windows 10 Pro e Enterprise no Surface Hub 2](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107).

- [Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a>Interface do usuário

### <a name="shell-os-user-interface"></a>Shell (interface de usuário do sistema operacional)

O shell do Surface Hub foi projetado desde o início para ser otimizado para toque e tela grande. Ele não usa o mesmo shell do Windows 10 Enterprise.

*Políticas da organização que isso pode afetar:* <br> Configurações relacionadas a controles no shell do Windows 10 Enterprise não se aplicam ao Surface Hub.

### <a name="lock-screen-and-screensaver"></a>Tela de bloqueio e proteção de tela

O Surface Hub não tem uma tela de bloqueio ou uma proteção de tela, mas tem uma funcionalidade semelhante denominada tela de boas-vindas. A tela de boas-vindas mostra reuniões agendadas do calendário da conta de dispositivo e pontos de entrada fáceis para os principais aplicativos do Surface Hub - Skype for Business, Quadro de comunicações e Connect.

*Políticas da organização que isso pode afetar:* <br> Configurações de tela de bloqueio, tempo limite de tela e proteção de tela não se aplicam ao Surface Hub.

### <a name="user-sign-in"></a>Logon do usuário

O Surface Hub foi projetado para ser usado em espaços públicos, como salas de reunião. Ao contrário de computadores Windows, qualquer pessoa pode ir até um Surface Hub e usá-lo sem precisar que um usuário realize logon. Para habilitar essa funcionalidade pública, o Surface Hub não oferece suporte a entrada do Windows da mesma maneira que o Windows 10 Enterprise (por exemplo, fazer logon em um usuário para o sistema operacional usando essas credenciais em todo o sistema operacional). Em vez disso, há sempre um local, conectado automaticamente, onde usuários de baixo nível de privilégios se conectam ao Surface Hub. Não dá suporte a logon de quaisquer usuários adicionais, incluindo os usuários admin (por exemplo, quando um administrador entra, eles não estão conectados ao sistema operacional).

Os usuários podem fazer logon em um Surface Hub, mas eles não serão registrados no sistema operacional. Por exemplo, quando um usuário entra em Aplicativos ou em Minhas reuniões e Arquivos, os usuários são registrado apenas para os aplicativos ou serviços, não para o sistema operacional. Como resultado, o usuário conectado é capaz de recuperar seus arquivos de nuvem em reuniões pessoais armazenadas na nuvem, e essas credenciais são descartadas quando **Finalizar a sessão** é ativado.


*Políticas da organização que isso pode afetar:* <br> Em geral, o Surface Hub usa recursos de bloqueio em vez de controle de acesso do usuário para reforçar a segurança. Políticas relacionados a requisitos de senha, logon interativo, contas de usuário e controle de acesso não se aplicam ao Surface Hub.

### <a name="saving-and-browsing-files"></a>Salvando e procurando arquivos

Os usuários têm acesso a um conjunto limitado de diretórios no Surface Hub:
- Música
- Vídeos
- Documentos
- Imagens
- Downloads

Os arquivos salvos localmente nesses diretórios são excluídos quando os usuários pressionam **Encerrar sessão**. Para salvar o conteúdo criado durante uma reunião, os usuários devem salvar arquivos em uma unidade USB ou no OneDrive.

*Políticas da organização que isso pode afetar:* <br> Políticas relacionadas a permissões de acesso e propriedade de arquivos e pastas não e aplicam ao Surface Hub. Os usuários não podem procurar e salvar arquivos em diretórios do sistema e pastas de rede.

## <a name="applications"></a>Aplicativos

### <a name="default-applications"></a>Aplicativos padrão

Com algumas exceções, os aplicativos padrão da Plataforma Universal do Windows (UWP) no Surface Hub também estão disponíveis em computadores com Windows 10.

Aplicativos UWP pré-instalados no Surface Hub:
- Alarmes e Relógio
- Calculadora
- Connect
- Excel Mobile
- Hub de Feedback
- Explorador de Arquivos*
- Introdução
- Mapas
- Microsoft Edge
- Microsoft Power BI
- OneDrive
- Fotos
- PowerPoint Mobile
- Configurações*
- Skype for Business*
- Loja
- Quadro de comunicações*
- Word Mobile

*Aplicativos com um asterisco (&ast;) são exclusivos do Surface Hub*

*Políticas da organização que isso pode afetar:* <br> Use as diretrizes para o Windows 10 Enterprise para determinar os recursos e requisitos de rede para aplicativos padrão no Surface Hub.

### <a name="installing-apps-drivers-and-services"></a>Instalar aplicativos, drivers e serviços

Para ajudar a preservar a natureza de aplicativo do dispositivo, o Surface Hub suporta apenas a instalação de aplicativos da Plataforma Universal do Windows (UWP) e não oferece suporte à instalação de aplicativos Win32 clássicos, serviços e drivers. Além disso, apenas administradores têm acesso para instalar aplicativos UWP.

*Políticas da organização que isso pode afetar:* <br> Os funcionários podem usar somente os aplicativos que foram instalados por administradores, ajudando a atenuar o uso não intencional. O Surface Hub não oferece suporte à instalação de agentes do Win32 exigidos pela maioria das tradicionais ferramentas de gerenciamento e monitoramento de computadores.

## <a name="security-and-lockdown"></a>Segurança e bloqueio

Para o Surface Hub ser usado em espaços públicos, como salas de reunião, seu sistema operacional personalizado implementa vários dos recursos de segurança e de bloqueio disponíveis no Windows 10.

O Surface Hub implementa estes recursos de segurança do Windows 10:
- [Inicialização segura UEFI](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)
- [UMCI (integridade de código do modo de usuário) com o Device Guard](https://technet.microsoft.com/itpro/windows/keep-secure/introduction-to-device-guard-virtualization-based-security-and-code-integrity-policies)
- [Políticas de restrição de aplicativo usando o AppLocker](https://technet.microsoft.com/itpro/windows/keep-secure/applocker-overview)
- [Criptografia de Unidade de Disco BitLocker](https://technet.microsoft.com/itpro/windows/keep-secure/bitlocker-overview)
- [Trusted Platform Module (TPM)](https://technet.microsoft.com/itpro/windows/keep-secure/trusted-platform-module-overview)
- [Windows Defender](https://technet.microsoft.com/itpro/windows/keep-secure/windows-defender-in-windows-10)
- [Controle de Conta de Usuário (UAC)](https://technet.microsoft.com/itpro/windows/keep-secure/user-account-control-overview) para acessar o aplicativo Configurações

Estes recursos do Surface Hub fornecem segurança adicional:
- Firmware UEFI personalizado
- Shell personalizado e dispositivo de limites do menu Iniciar para funções de reunião
- O Explorador de Arquivos personalizado apenas concede acesso a arquivos e pastas em Meus Documentos
- O aplicativo Configurações personalizado permite apenas que administradores modifiquem as configurações do dispositivo
- O download de drivers Plug and Play avançados está desabilitado

*Políticas da organização que isso pode afetar:* <br> Considere estes recursos ao executar sua avaliação de segurança para o Surface Hub.

## <a name="management"></a>Gerenciamento

### <a name="device-settings"></a>Configurações do dispositivo

As configurações do dispositivo podem ser configuradas por meio do aplicativo Configurações. O aplicativo Configurações é personalizado para o Surface Hub, mas também contém muitas configurações familiares do Windows 10 Desktop. Um prompt de Controle de Conta de Usuário (UAC) é exibido ao abrir o aplicativo Configurações para verificar as credenciais de administrador, mas isso não registrará o administrador.

*Políticas da organização que isso pode afetar:* <br> Os funcionários podem usar o Surface Hub para reuniões, mas não podem modificar as configurações do dispositivo. Além dos recursos de bloqueio, isso garante que os funcionários só usem o dispositivo para funções de reunião.

### <a name="administrative-features"></a>Recursos administrativos

O Surface Hub não oferece suporte ao recursos administrativos no Windows 10 Enterprise, tais como o Console de Gerenciamento Microsoft, Executar, Prompt de Comando, PowerShell, Editor do Registro, Visualizador de Eventos e Gerenciador de Tarefas. O aplicativo Configurações contém todos os recursos administrativos disponíveis localmente no Surface Hub.

### <a name="remote-management-and-monitoring"></a>Gerenciamento remoto e monitoramento

O Surface Hub dá suporte ao gerenciamento remoto por meio de soluções de gerenciamento de dispositivo móvel (MDM), como [o Microsoft Intune](https://docs.microsoft.com/intune/) e monitoramento por meio do [Azure Monitor](https://azure.microsoft.com/services/monitor/). 

*Políticas da organização que isso pode afetar:* <br> O Surface Hub não dá suporte à instalação de agentes do Win32 exigida pela maioria das tradicionais ferramentas de gerenciamento e monitoramento de computador, como o System Center Operations Manager.

### <a name="group-policy"></a>Política de Grupo

O Surface Hub não dá suporte à Política de Grupo do Windows, incluindo auditoria. Em vez disso, use MDM para aplicar políticas ao seu Surface Hub. Para obter mais informações sobre MDM, consulte [Gerenciar configurações com um provedor de MDM](manage-settings-with-mdm-for-surface-hub.md).

*Políticas da organização que isso pode afetar:* <br> Use MDM para gerenciar o Surface Hub em vez de política de grupo.

### <a name="remote-assistance"></a>Assistência remota

O Surface Hub não oferece suporte à assistência remota.

*Políticas da organização que isso pode afetar:* <br> As políticas relacionadas à assistência remota não se aplicam ao Surface Hub.

## <a name="network"></a>Rede

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a>Ingresso em domínio e ingresso no Azure Active Directory (Azure AD) 

O Surface Hub usa o ingresso em domínio e o ingresso no Azure AD principalmente para fornecer um grupo de administração salvo por diretório. Os usuários não podem fazer logon com uma conta de domínio. Para obter mais informações, consulte [Gerenciamento de grupo de administração](admin-group-management-for-surface-hub.md).

*Políticas da organização que isso pode afetar:* <br> Políticas de grupo não são aplicadas quando um Surface Hub é associado ao seu domínio. Políticas relacionados à associação ao domínio não se aplicam ao Surface Hub.

### <a name="accessing-domain-resources"></a>Acessando recursos do domínio

Os usuários podem se conectar ao Microsoft Edge para acessar sites de intranet e recursos online (como o Office 365). Se seu Surface Hub estiver configurado com uma conta de dispositivo, o sistema irá usá-la para acessar o Exchange e o Skype for Business. No entanto, o Surface Hub não oferece suporte para acessar recursos do domínio, como compartilhamentos de arquivos e impressoras.

*Políticas da organização que isso pode afetar:* <br> As políticas relacionadas ao acesso a objetos de domínio não se aplicam ao Surface Hub.

<!--
### Endpoints



*Organization policies that this may affect:* <br> 
-->

### <a name="diagnostic-data"></a>Dados de diagnóstico

O sistema operacional do Surface Hub usa o componente de Experiência do Usuário Conectado e Telemetria do Windows 10 para coletar e transmitir dados de diagnóstico. Para obter mais informações, consulte [Configurar os dados de diagnóstico do Windows em sua organização](https://technet.microsoft.com/itpro/windows/manage/configure-windows-diagnostic-data-in-your-organization).

*Políticas da organização que isso pode afetar:* <br> Configure os níveis de dados de diagnóstico para o Surface Hub da mesma maneira que você faz para o Windows 10 Enterprise.
