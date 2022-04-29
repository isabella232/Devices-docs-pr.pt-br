---
title: Noções básicas do sistema operacional (Surface Hub)
description: Este tópico explica aspectos exclusivos do sistema operacional Windows Team no Surface Hub e como ele difere de Windows 10 ou Windows 11 Enterprise.
keywords: histórico de alterações
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/15/2022
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 5be9c0ba3f23832d2e3d9b66a746e9f1f0772e63
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497334"
---
# <a name="operating-system-essentials-surface-hub"></a>Noções básicas do sistema operacional (Surface Hub)

O Surface Hub operacional, Windows 10 Team, originado com Windows 10 Enterprise, fornecendo suporte avançado para gerenciamento corporativo, segurança e outros recursos. No entanto, existem diferenças importantes entre eles. Enquanto a edição Enterprise foi criada para computadores, o Windows 10 Team foi projetado desde o início para telas grandes e salas de reunião. Ao avaliar os requisitos de segurança e gerenciamento Surface Hub, é recomendável considerá-lo como um novo sistema operacional. Este artigo destaca as principais diferenças entre Windows 10 Team em Surface Hub e versões corporativas do Windows 10 ou Windows 11.

## <a name="convert-surface-hub-to-run-pro-or-enterprise-desktop"></a>Converter Surface Hub para executar Pro ou Enterprise desktop

Você pode alterar o sistema operacional no Surface Hub 2S migrando para Windows 10 ou Windows 11 Pro/Enterprise. Para saber mais, consulte o seguinte:

- [Anunciando a disponibilidade de Windows 10 Pro e Enterprise no Surface Hub 2](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107).

- [Migrar para Windows 10, Windows 11 Pro ou Enterprise no Surface Hub 2](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a>Interface do usuário

### <a name="shell-os-user-interface"></a>Shell (interface de usuário do sistema operacional)

O shell do Surface Hub foi projetado desde o início para ser otimizado para toque e tela grande. Ele não usa o mesmo shell que Windows 10 ou Windows 11 Enterprise.

*Políticas da organização que isso pode afetar:* 

- Configurações relacionados a controles no shell Windows 10 ou Windows 11 Enterprise não se aplicam a Surface Hub.

### <a name="lock-screen-and-screensaver"></a>Tela de bloqueio e proteção de tela

O Surface Hub não tem uma tela de bloqueio ou uma proteção de tela, mas tem uma funcionalidade semelhante denominada tela de boas-vindas. A tela de boas-vindas mostra reuniões agendadas do calendário da conta de dispositivo e pontos de entrada fáceis para os principais aplicativos do Surface Hub - Skype for Business, Quadro de comunicações e Connect.

*Políticas da organização que isso pode afetar:* 

- Configurações de tela de bloqueio, tempo limite de tela e proteção de tela não se aplicam ao Surface Hub.

### <a name="user-sign-in"></a>Logon do usuário

O Surface Hub foi projetado para ser usado em espaços públicos, como salas de reunião. Ao contrário de computadores Windows, qualquer pessoa pode ir até um Surface Hub e usá-lo sem precisar que um usuário realize logon. Para habilitar essa funcionalidade comunitária, o Surface Hub não dá suporte Windows entrada da mesma maneira que o Windows 10 ou o Windows 11 Enterprise (por exemplo, conectar um usuário ao sistema operacional e usar essas credenciais em todo o sistema operacional). Em vez disso, há sempre um local, conectado automaticamente, onde usuários de baixo nível de privilégios se conectam ao Surface Hub. Não dá suporte a logon de quaisquer usuários adicionais, incluindo os usuários admin (por exemplo, quando um administrador entra, eles não estão conectados ao sistema operacional).

Os usuários podem fazer logon em um Surface Hub, mas eles não serão registrados no sistema operacional. Por exemplo, quando um usuário entra em Aplicativos ou em Minhas reuniões e Arquivos, os usuários são registrado apenas para os aplicativos ou serviços, não para o sistema operacional. Como resultado, o usuário conectado é capaz de recuperar seus arquivos de nuvem em reuniões pessoais armazenadas na nuvem, e essas credenciais são descartadas quando **Finalizar a sessão** é ativado.

*Políticas da organização que isso pode afetar:* 

- Em geral, o Surface Hub usa recursos de bloqueio em vez de controle de acesso do usuário para reforçar a segurança. Políticas relacionados a requisitos de senha, logon interativo, contas de usuário e controle de acesso não se aplicam ao Surface Hub.

### <a name="saving-and-browsing-files"></a>Salvando e procurando arquivos

Os usuários têm acesso a um conjunto limitado de diretórios no Surface Hub:
- Música
- Vídeos
- Documentos
- Imagens
- Downloads

Os arquivos salvos localmente nesses diretórios são excluídos quando os usuários pressionam **Encerrar sessão**. Para salvar o conteúdo criado durante uma reunião, os usuários devem salvar arquivos em uma unidade USB ou no OneDrive.

*Políticas da organização que isso pode afetar:* – Políticas relacionadas a permissões de acesso e propriedade de arquivos e pastas não se aplicam a Surface Hub. Os usuários não podem procurar e salvar arquivos em diretórios do sistema e pastas de rede.

## <a name="applications"></a>Aplicativos

### <a name="default-applications"></a>Aplicativos padrão

Com poucas exceções, os aplicativos Plataforma Universal do Windows (UWP) padrão no Surface Hub também estão disponíveis em Windows 10 ou Windows 11 computadores.

Aplicativos UWP pré-instalados no Surface Hub:

- Alarmes e Relógio
- Calculadora
- Connect
- Excel Mobile
- Hub de Feedback
- Explorador de Arquivos
- Introdução
- Mapas
- Microsoft Edge
- Microsoft Power BI
- Microsoft Teams
- Microsoft Whiteboard
- OneDrive
- Fotos
- PowerPoint Mobile
- Configurações
- Store
- Dicas
- Word Mobile

*Políticas da organização que isso pode afetar:* 

- Use diretrizes para Windows 10 ou Windows 11 Enterprise para determinar os recursos e os requisitos de rede para aplicativos padrão no Surface Hub.

### <a name="installing-apps-drivers-and-services"></a>Instalar aplicativos, drivers e serviços

Para ajudar a preservar a natureza de aplicativo do dispositivo, o Surface Hub suporta apenas a instalação de aplicativos da Plataforma Universal do Windows (UWP) e não oferece suporte à instalação de aplicativos Win32 clássicos, serviços e drivers. Além disso, apenas administradores têm acesso para instalar aplicativos UWP.

*Políticas da organização que isso pode afetar:* 

- Os funcionários podem usar somente os aplicativos que foram instalados por administradores, ajudando a atenuar o uso não intencional. O Surface Hub não oferece suporte à instalação de agentes do Win32 exigidos pela maioria das tradicionais ferramentas de gerenciamento e monitoramento de computadores.

## <a name="security-and-lockdown"></a>Segurança e bloqueio

Para Surface Hub ser usado em espaços públicos, como salas de reunião, seu sistema operacional personalizado implementa muitos dos recursos de segurança e bloqueio disponíveis no Windows 10 ou Windows 11. Para saber mais, confira [Surface Hub de segurança](surface-hub-security.md)

Surface Hub implementa estes recursos Windows segurança:

- [Inicialização Segura](/windows-hardware/design/device-experiences/oem-secure-boot)
- [Controle de Aplicativos do Windows Defender e proteção baseada em virtualização da integridade do código](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Políticas de restrição de aplicativo usando o AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)
- [Criptografia de Unidade de Disco BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Trusted Platform Module (TPM)](/windows/security/information-protection/tpm/trusted-platform-module-top-node)
- [Microsoft Defender Antivírus em Windows](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)
- [Controle de Conta de Usuário (UAC)](/windows/security/identity-protection/user-account-control/user-account-control-overview) para acessar o aplicativo Configurações

Estes recursos do Surface Hub fornecem segurança adicional:

- Firmware UEFI personalizado
- Shell personalizado e dispositivo de limites do menu Iniciar para funções de reunião
- O Explorador de Arquivos personalizado apenas concede acesso a arquivos e pastas em Meus Documentos
- O aplicativo Configurações personalizado permite apenas que administradores modifiquem as configurações do dispositivo
- O download de drivers Plug and Play avançados está desabilitado

*Políticas da organização que isso pode afetar:*

- Considere estes recursos ao executar sua avaliação de segurança para o Surface Hub.

## <a name="management"></a>Gerenciamento

### <a name="device-settings"></a>Configurações do dispositivo

As configurações do dispositivo podem ser configuradas por meio do aplicativo Configurações. O Configurações aplicativo é personalizado para Surface Hub, mas também contém muitas configurações conhecidas do Windows 10 ou Windows 11 Desktop. Um prompt de Controle de Conta de Usuário (UAC) é exibido ao abrir o aplicativo Configurações para verificar as credenciais de administrador, mas isso não registrará o administrador.

*Políticas da organização que isso pode afetar:* 

- Os funcionários podem usar o Surface Hub para reuniões, mas não podem modificar as configurações do dispositivo. Além dos recursos de bloqueio, isso garante que os funcionários só usem o dispositivo para funções de reunião.

### <a name="administrative-features"></a>Recursos administrativos

Os recursos administrativos no Windows 10 ou no Windows 11 Enterprise, como o Console de Gerenciamento da Microsoft, Executar, Prompt de Comando, PowerShell, Editor do Registro e Gerenciador de Tarefas não têm suporte no Surface Hub. O aplicativo Configurações contém todos os recursos administrativos disponíveis localmente no Surface Hub.

#### <a name="event-viewer"></a>Visualizador de eventos

Windows 10 Team atualização 2020 adiciona suporte para o Windows Visualizador de Eventos, que é idêntico ao [Visualizador de Eventos](/host-integration-server/core/windows-event-viewer1) instalado no Windows 10 Pro ou Windows 10 Enterprise. 

**Para abrir o Visualizador de Eventos:**

1. Entre **no Configurações com** credenciais de administrador.
2. Selecione **Atualizar &** **SecurityLogs** >  e, em Visualizador de Eventos, selecione **Abrir**. 

Para saber mais, confira [Windows Visualizador de Eventos](/host-integration-server/core/windows-event-viewer1).

### <a name="remote-management-and-monitoring"></a>Gerenciamento remoto e monitoramento

Surface Hub dá suporte ao gerenciamento remoto por meio de soluções de MDM (gerenciamento de dispositivo [](/mem/intune/) móvel), como Microsoft Intune e monitoramento por meio do [Azure Monitor](/azure/azure-monitor/). 

*Políticas da organização que isso pode afetar:* 

- O Surface Hub não dá suporte à instalação de agentes do Win32 exigida pela maioria das tradicionais ferramentas de gerenciamento e monitoramento de computador, como o System Center Operations Manager.

### <a name="group-policy"></a>Política de Grupo

Surface Hub não dá suporte a Windows Política de Grupo, incluindo auditoria. Em vez disso, use MDM para aplicar políticas ao seu Surface Hub. Para obter mais informações sobre MDM, consulte [Gerenciar configurações com um provedor de MDM](manage-settings-with-mdm-for-surface-hub.md).

*Políticas da organização que isso pode afetar:* 

- Use MDM para gerenciar o Surface Hub em vez de política de grupo.

### <a name="remote-assistance"></a>Assistência remota

O Surface Hub não oferece suporte à assistência remota.

*Políticas da organização que isso pode afetar:* 

- As políticas relacionadas à assistência remota não se aplicam ao Surface Hub.

## <a name="network"></a>Rede

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a>Ingresso em domínio e ingresso no Azure Active Directory (Azure AD) 

O Surface Hub usa o ingresso em domínio e o ingresso no Azure AD principalmente para fornecer um grupo de administração salvo por diretório. Não há suporte para junção híbrida. Os usuários não podem fazer logon com uma conta de domínio. Para obter mais informações, consulte [Gerenciamento de grupo de administração](admin-group-management-for-surface-hub.md).

*Políticas da organização que isso pode afetar:* 

- As configurações de política de grupo não são aplicadas quando um Surface Hub é ingressado em seu domínio. As configurações de política relacionadas à associação de domínio não se aplicam Surface Hub.

### <a name="accessing-domain-resources"></a>Acessando recursos do domínio

Os usuários podem se conectar ao Microsoft Edge para acessar sites de intranet e recursos online (como o Office 365). Se seu Surface Hub estiver configurado com uma conta de dispositivo, o sistema irá usá-la para acessar o Exchange e o Skype for Business. No entanto, o Surface Hub não oferece suporte para acessar recursos do domínio, como compartilhamentos de arquivos e impressoras.

*Políticas da organização que isso pode afetar:* 

- As políticas relacionadas ao acesso a objetos de domínio não se aplicam ao Surface Hub.

### <a name="diagnostic-data"></a>Dados de diagnóstico

O Surface Hub sistema operacional usa o Windows experiência do usuário conectado e o componente telemetria para coletar e transmitir dados de diagnóstico. Para obter mais informações, consulte [Configurar os dados de diagnóstico do Windows em sua organização](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).

*Políticas da organização que isso pode afetar:* 

- Configure os níveis de dados de Surface Hub da mesma maneira que você faz para Windows 10 ou Windows 11 Enterprise.
