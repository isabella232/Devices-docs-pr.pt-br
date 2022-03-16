---
title: Visão geral da segurança do Surface Duo
description: Este artigo destaca como o Surface Duo oferece segurança de nível empresarial em um dispositivo móvel por meio do sistema operacional Android e UEFI projetado pela Microsoft.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 677839038d8990aa7cb88800dabd51ace565e472
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449154"
---
# <a name="surface-duo-security-overview"></a>Visão geral da segurança do Surface Duo

O Surface Duo tem proteção interna em todas as camadas com hardware, firmware e software profundamente integrados para proteger seus dispositivos, identidades e dados. Como um dispositivo Android 10, o Surface Duo utiliza recursos de segurança do Android no nível do sistema operacional e na camada de serviços do Google. O sistema operacional Android aproveita controles de segurança do sistema operacional tradicionais para proteger os dados do usuário e os recursos do sistema, protege a integridade do dispositivo contra malware e fornece isolamento de aplicativos. Além disso, o Google fornece vários serviços em camadas sobre o sistema operacional que, quando combinados com a segurança do sistema operacional Android, ajudam a proteger continuamente o usuário android.

- **UEFI de engenharia personalizada.** Exclusivo do Surface Duo, entre dispositivos Android, é a INTERFACE de Firmware Extensível Unificada (UEFI) personalizada da Microsoft, que permite o controle total sobre componentes de firmware. A Microsoft fornece Enterprise segurança de nível para o Surface Duo escrevendo ou revisando todas as linhas de código de firmware internamente, permitindo que a Microsoft responda de forma direta e ágil a possíveis ameaças de firmware e reduza os riscos de segurança da cadeia de fornecimento.
- **Inicialização verificada.** A partir do nível de hardware ao entrar, a Inicialização Verificada se esforça para garantir que o código executado só venha de uma fonte confiável. Ele estabelece uma cadeia completa de confiança , desde a raiz de confiança protegida pelo hardware até o carregador de inicialização, a partição de inicialização e outras partições verificadas. Quando o Surface Duo é inicializado, cada estágio verifica a integridade e a autenticidade do próximo estágio antes de entregar a execução.
- **Separação de aplicativos.** A área de proteção de aplicativos isola e protege aplicativos Android, impedindo que aplicativos mal-intencionados acessem informações privadas. A criptografia obrigatória e a manipulação de chaves ajudam a proteger dados em trânsito e em repouso, mesmo que os dispositivos caiam em mãos erradas. A criptografia é protegida com chaves keystore, que armazenam chaves criptográficas em um contêiner, tornando mais difícil extrair de um dispositivo.
- **Google Play Protect.** Na camada de software, o Surface Duo usa a detecção de ameaças do Google Play Protect, que verifica todos os aplicativos, incluindo aplicativos públicos do Google Play, aplicativos de sistema atualizados pela Microsoft e operadoras e aplicativos com sideload.
- **Microsoft Defender ATP.** O software de proteção contra antivírus e malware de nível empresarial para a Janela 10 agora está disponível para dispositivos Android gerenciados pelo Intune. Para saber mais, confira [Microsoft defender ATP para Android](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android).

## <a name="mobile-device-management-security"></a>Segurança de gerenciamento de dispositivo móvel

O Surface Duo é protegido em um ambiente corporativo usando uma solução de Gerenciamento de Mobilidade (EMM) Enterprise que fornece um conjunto consistente de ferramentas de proteção, tecnologias e práticas recomendadas que você pode adaptar para atender aos seus requisitos organizacionais e de conformidade. Uma ampla variedade de APIs de gerenciamento fornece aos departamentos de IT as ferramentas para ajudar a evitar o vazamento de dados e impor a conformidade em vários cenários. As opções de suporte a vários perfis e gerenciamento de dispositivos permitem a separação de dados pessoais e de trabalho, ajudando a manter os dados da empresa seguros.

A segurança do MDM é criada com base em um conjunto em expansão de tecnologias de configuração para permitir que os usuários sejam produtivos em tempo hábil, além de proteger a propriedade intelectual corporativa crítica. Isso inclui políticas de proteção de aplicativos, políticas de restrição de dispositivos e tecnologias relacionadas projetadas para permitir que você atender a metas específicas, dependendo do seu ambiente, se sua empresa consiste em fornecer pedidos de retirada de restaurante, gerenciar serviços de TI para escritórios dentários ou lidar com informações confidenciais de segurança nacional.

Por exemplo, talvez você queira fortalecer a autenticação de dispositivo exigindo que os usuários insiram um pino alfanumérico de 6 dígitos juntamente com a autenticação de dois fatores. Talvez você queira restringir os dispositivos em que os usuários podem se inscrever para ajudá-lo a permanecer em conformidade com os limites de licenciamento ou evitar conceder acesso a telefones "jailbroken" ou outros tipos de dispositivo sem suporte. O Intune e outras EMMs permitem que as organizações gerenciem dispositivos de acordo com suas necessidades.

## <a name="app-protection-policies"></a>Políticas de proteção de aplicativos

As políticas de proteção de aplicativos (APP) são regras que garantem que os dados de uma organização permaneçam seguros ou contidos em um aplicativo gerenciado. Uma política pode ser uma regra imposta quando o usuário tenta acessar ou mover dados "corporativos" ou um conjunto de ações que são proibidas ou monitoradas quando o usuário está dentro do aplicativo. Um aplicativo gerenciado é um aplicativo que tem políticas de proteção de aplicativos aplicadas a ele e pode ser gerenciado pelo Intune.

As políticas de proteção de aplicativos permitem que você gerencie e proteja os dados da sua organização em um aplicativo. Muitos aplicativos de produtividade, como os Microsoft Office aplicativos, podem ser gerenciados pelo MAM do Intune. Consulte a lista oficial de [Microsoft Intune aplicativos protegidos](/mem/intune/apps/apps-supported-intune-apps) disponíveis para uso público.

## <a name="security-considerations-for-managing-surface-duo"></a>Considerações de segurança para gerenciar o Surface Duo

O número crescente de configurações de política disponíveis em soluções de gerenciamento de dispositivo móvel permite que as organizações ajustem níveis de proteção para atender às suas necessidades específicas. Para ajudar as organizações a priorizar as configurações de segurança do Surface Duo (ou qualquer outro dispositivo Android), o Intune introduziu sua estrutura de configuração de segurança do [Android Enterprise](/mem/intune/enrollment/android-configuration-framework) organizada em vários cenários de configuração distintos, fornecendo orientações para o perfil de trabalho e cenários totalmente gerenciados.

| Nível de segurança                                                                                                       | Direcionado para                                                                                                                                                                      | Resumo                                                                                                                                                                                     | Configurações informações                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Segurança básica do perfil de trabalho - Nível 1                                                                                | Dispositivos pessoais com acesso a dados de trabalho ou de estudante.                                                                                                                             | Introduz requisitos de senha, separa dados pessoais e de trabalho e valida o atestado de dispositivo Android.                                                                               | [Configurações de nível 1 do perfil de trabalho](/mem/intune/enrollment/android-work-profile-security-settings) |
| Alta segurança do perfil de trabalho - Nível 3<br>(Devido às convenções de estrutura, este é o próximo nível acima do Nível 1.)<br>  | Dispositivos usados por usuários ou grupos que são exclusivamente de alto risco. Por exemplo, os usuários que manipulam dados altamente confidenciais em que a divulgação não autorizada causa uma perda considerável de material. | Introduz a defesa contra ameaças móveis ou o Microsoft Defender ATP, define a versão mínima do Android como 8.0, estabelece políticas de senha mais fortes e restringe ainda mais o trabalho e a separação pessoal. | [Configurações de nível 3 do perfil de trabalho](/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| Segurança básica totalmente gerenciada - Nível 1                                                                                | Configuração de segurança mínima para um dispositivo empresarial, aplicável à maioria dos usuários móveis que acessam dados corporativos ou escolares.                                                          | Introduz os requisitos de senha, define a versão mínima do Android como 8.0 e decreta determinadas restrições de dispositivo.                                                                          | [Configurações de Nível 1 totalmente gerenciadas](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| Nível 2 de segurança totalmente gerenciado aprimorado                                                                              | Dispositivos em que os usuários acessam informações confidenciais ou confidenciais.                                                                                                                | Decreta políticas de senha mais fortes e desabilita os recursos de usuário/conta.                                                                                                                   | [Settngs de Nível 2 totalmente gerenciados](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| Nível 3 de alta segurança totalmente gerenciado                                                                                  | Dispositivos usados por usuários ou grupos que são exclusivamente de alto risco. Por exemplo, os usuários que manipulam dados altamente confidenciais em que a divulgação não autorizada causa uma perda considerável de material. | Aumenta a versão mínima do Android para 10.0, introduz a defesa contra ameaças móveis ou o Microsoft Defender ATP e impõe restrições adicionais de dispositivo.                                     | [Configurações de Nível 3 totalmente gerenciadas](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |

 Como em qualquer estrutura, as configurações em um nível correspondente podem precisar ser ajustadas com base nas necessidades da organização, pois a segurança deve avaliar o ambiente de ameaças, o risco e o impacto na usabilidade.

## <a name="learn-more"></a>Saiba mais

- [Estrutura de configuração de segurança do Android Enterprise](/mem/intune/enrollment/android-configuration-framework)
- [Visão geral das políticas de proteção de aplicativos](/mem/intune/apps/app-protection-policy)
- [Configurações da política de proteção de aplicativos Android Microsoft Intune](/mem/intune/apps/app-protection-policy-settings-android)
- [Definir restrições de registro](/mem/intune/enrollment/enrollment-restrictions-set)
- [White paper Enterprise Segurança do Android](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
