---
title: Visão geral da segurança do Surface Duo
description: Este artigo destaca como o Surface Duo oferece segurança de nível empresarial em um dispositivo móvel por meio do sistema operacional Android e UEFI de engenharia da Microsoft.
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
ms.openlocfilehash: 91eb893dbdc6dae93cf402a602b64a83309388e8
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326102"
---
# Visão geral da segurança do Surface Duo

O Surface Duo tem proteção integrada em todas as camadas com hardware, firmware e software profundamente integrados para manter seus dispositivos, identidades e dados seguros. Como um dispositivo Android 10, o Surface Duo utiliza recursos de segurança do Android no nível do sistema operacional e na camada de serviços do Google. O sistema operacional Android aproveita os controles de segurança tradicionais do sistema operacional para proteger os dados do usuário e os recursos do sistema, protege a integridade do dispositivo contra malware e fornece isolamento de aplicativo. Além disso, o Google fornece vários serviços em camadas sobre o sistema operacional que, quando combinados com a segurança do sistema operacional Android, ajudam a proteger continuamente o usuário do Android.

- **UEFI de engenharia personalizada.** Exclusiva para o Surface Duo, entre dispositivos Android, é a INTERFACE de Firmware Extensível (UEFI) personalizada da Microsoft, que permite controle total sobre componentes de firmware. A Microsoft oferece segurança de nível Empresarial ao Surface Duo escrevendo ou revendo cada linha de código de firmware internamente, permitindo que a Microsoft responda de forma direta e ágil a possíveis ameaças de firmware e reduza os riscos de segurança da cadeia de fornecedores.
- **Inicialização Verificada.** A partir do nível de hardware ao entrar, a Inicialização Verificada se esforça para garantir que o código executado venha apenas de uma fonte confiável. Ele estabelece uma cadeia completa de confiança , desde a raiz de confiança protegida por hardware até o carregador de inicialização, partição de inicialização e outras partições verificadas. Quando o Surface Duo é inicializado, cada estágio verifica a integridade e a autenticidade do próximo estágio antes de entregar a execução.
- **Separação de aplicativos.** A área de segurança do aplicativo isola e protege aplicativos Android, impedindo que aplicativos mal-intencionados acessem informações privadas. A criptografia obrigatória e a manipulação de chaves ajudam a proteger os dados em trânsito e em repouso , mesmo que os dispositivos caiam nas mãos erradas. A criptografia é protegida com chaves de repositório de chaves, que armazenam chaves criptográficas em um contêiner, dificultando a extração de um dispositivo.
- **Google Play Protect.** Na camada de software, o Surface Duo usa a detecção de ameaças do Google Play Protect, que verifica todos os aplicativos, incluindo aplicativos públicos do Google Play, aplicativos do sistema atualizados pela Microsoft e operadoras e aplicativos de sideload.
- **Microsoft Defender ATP.** O software de proteção contra malware e antivírus de nível empresarial para o Window 10 agora está disponível para dispositivos Android gerenciados pelo Intune. Para saber mais, confira [o Microsoft defender ATP para Android.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android) 


## Segurança de gerenciamento de dispositivo móvel

O Surface Duo é protegido em um ambiente corporativo usando uma solução Enterprise Mobility Management (EMM) que fornece um conjunto consistente de ferramentas de proteção, tecnologias e práticas recomendadas que você pode adaptar para atender aos seus requisitos organizacionais e de conformidade. Uma ampla variedade de APIs de gerenciamento fornece aos departamentos de IT as ferramentas para ajudar a evitar o vazamento de dados e impor a conformidade em uma variedade de cenários. As opções de suporte de vários perfis e gerenciamento de dispositivos permitem a separação de dados pessoais e de trabalho, ajudando a manter os dados da empresa seguros.

A segurança MDM se baseia em um conjunto crescente de tecnologias de configuração para permitir que os usuários sejam produtivos em qualquer lugar, além de proteger a propriedade intelectual corporativa crítica. Isso inclui políticas de proteção de aplicativos, políticas de restrição de dispositivos e tecnologias relacionadas projetadas para permitir que você cumprir metas específicas, dependendo do seu ambiente , se sua empresa consiste em entregar pedidos de compra de restaurantes, gerenciar serviços de TI para escritórios comerciais ou lidar com informações confidenciais de segurança nacional. 

Por exemplo, talvez você queira reforçar a autenticação de dispositivo, exigindo que os usuários insiram um pin alfanumérico de seis dígitos juntamente com a autenticação de 2 fatores.  você pode restringir os dispositivos que os usuários podem registrar para ajudar a garantir que você permaneça em conformidade com os limites de licenciamento ou evitar conceder acesso a telefones "jailbroken" ou outros tipos de dispositivo sem suporte.
O Intune e outros EMMs fornecem às organizações a flexibilidade de gerenciar dispositivos de acordo com suas necessidades.

## Políticas de proteção de aplicativos

As políticas de proteção de aplicativo (APP) são regras que garantem que os dados de uma organização permaneçam seguros ou contidos em um aplicativo gerenciado. Uma política pode ser uma regra imposta quando o usuário tenta acessar ou mover dados "corporativos" ou um conjunto de ações que são proibidas ou monitoradas quando o usuário está dentro do aplicativo. Um aplicativo gerenciado é um aplicativo que tem políticas de proteção de aplicativo aplicadas a ele e pode ser gerenciado pelo Intune.

As políticas de proteção de aplicativos permitem que você gerencie e proteja os dados da sua organização em um aplicativo. Muitos aplicativos de produtividade, como os aplicativos do Microsoft Office, podem ser gerenciados pelo MAM do Intune. Veja a lista oficial de [aplicativos protegidos do Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-supported-intune-apps) disponíveis para uso público.

## Considerações de segurança para gerenciar o Surface Duo

O crescente número de configurações de política disponíveis em soluções de gerenciamento de dispositivo móvel permite que as organizações ajustem os níveis de proteção para atender às suas necessidades específicas. Para ajudar as organizações a priorizar as configurações de segurança do Surface Duo (ou qualquer outro dispositivo Android), o Intune introduziu sua estrutura de configuração de segurança [do Android Enterprise](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework) organizada em vários cenários de configuração distintos, fornecendo orientações para o perfil de trabalho e cenários totalmente gerenciados.
 

| Nível de segurança                                                                                                       | Direcionado para                                                                                                                                                                      | Resumo                                                                                                                                                                                     | Informações de configurações                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Segurança básica do perfil de trabalho - Nível 1                                                                                | Dispositivos pessoais com acesso a dados do trabalho ou da escola.                                                                                                                             | Apresenta requisitos de senha, separa dados pessoais e de trabalho e valida o atestado de dispositivo Android.                                                                               | [Configurações de nível 1 de perfil de trabalho](https://microsoft.sharepoint.com/teams/EpsilonAdminGuide/Shared%20Documents/General/•%09https:/docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-basic-security) |
| Alta segurança do perfil de trabalho - Nível 3<br>(Devido às convenções de estrutura, este é o próximo nível acima do Nível 1.)<br> ** | Dispositivos usados por usuários ou grupos exclusivamente de alto risco. Por exemplo, os usuários que lidam com dados altamente confidenciais em que a divulgação não autorizada causa uma perda considerável de material. | Introduz a defesa contra ameaças móveis ou o Microsoft Defender ATP, define a versão mínima do Android como 8.0, estabelece políticas de senha mais fortes e restringe ainda mais o trabalho e a separação pessoal. | [Configurações de nível 3 de perfil de trabalho](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| Segurança básica totalmente gerenciada - Nível 1                                                                                | Configuração de segurança mínima para um dispositivo corporativo, aplicável à maioria dos usuários móveis que acessam dados corporativos ou de estudante.                                                          | Apresenta os requisitos de senha, define a versão mínima do Android como 8.0 e aplica certas restrições de dispositivo.                                                                          | [Configurações de Nível 1 totalmente gerenciadas](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| Segurança totalmente gerenciada aprimorada Nível 2                                                                              | Dispositivos em que os usuários acessam informações confidenciais ou confidenciais.                                                                                                                | Aprova políticas de senha mais fortes e desabilita os recursos de usuário/conta.                                                                                                                   | [Reações de Nível 2 totalmente gerenciadas](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| Nível 3 de alta segurança totalmente gerenciado                                                                                  | Dispositivos usados por usuários ou grupos exclusivamente de alto risco. Por exemplo, os usuários que lidam com dados altamente confidenciais em que a divulgação não autorizada causa uma perda considerável de material. | Aumenta a versão mínima do Android para 10.0, introduz a defesa contra ameaças móveis ou o Microsoft Defender ATP e impõe restrições de dispositivo adicionais.                                     | [Configurações de Nível 3 totalmente gerenciadas](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |
 
Como em qualquer estrutura, as configurações dentro de um nível correspondente talvez precisem ser ajustadas com base nas necessidades da organização, pois a segurança deve avaliar o ambiente de ameaças, os riscos e o impacto na usabilidade.
 
 
**Saiba mais**


- [Estrutura de configuração de segurança do Android Enterprise](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework)
- [Visão geral das políticas de proteção de aplicativos](https://docs.microsoft.com/mem/intune/apps/app-protection-policy)
- [Configurações de política de proteção de aplicativo Android no Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)
- [Definir restrições de registro](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)
- [White paper do Android Enterprise Security](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
 