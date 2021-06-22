---
title: Visão geral da segurança do Surface
description: Este artigo fornece uma visão geral da segurança do dispositivo Surface
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/04/2021
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 67ba96129d69cafaa7a1b24ce3dde98767b676ef
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614040"
---
# <a name="surface-security-overview"></a>Visão geral da segurança do Surface

Os avanços recentes na pesquisa de segurança demonstram que, à medida que mais proteções são internas no sistema operacional e nos serviços conectados, os invasores estão procurando por outras vias de exploração com o firmware surgindo como um alvo principal.

Hoje, gerenciar o firmware do dispositivo é uma experiência inconsistente e geralmente envolve provedores de terceiros, tornando o firmware difícil de monitorar e complicado de manter. Em última análise, isso pode limitar a capacidade dos fabricantes de hardware de detectar e adiar atualizações o tempo limite em resposta a ameaças.

O Microsoft Surface usa uma abordagem unificada para proteção de firmware e segurança de dispositivos desde 2015 por meio da propriedade completa de ponta a ponta do design de hardware, desenvolvimento de firmware interno e uma abordagem holística para atualizações e gerenciamento de dispositivos.

Para o Surface, nossa Interface de Firmware Extensível Unificada (UEFI) 1 é mantida no local, atualizada regularmente por meio do Windows Update e implantada perfeitamente para gerenciamento por meio do <sup> [](#references) Windows Autopilot, minimizando o risco e maximizando o controle no nível do firmware antes de o dispositivo </sup> ser inicializado. A Microsoft fornece total transparência da base de código em nossa UEFI por meio do Código Aberto Project [Mu](https://microsoft.github.io/mu/) no GitHub, gerenciado por Microsoft Endpoint Manager.

## <a name="microsoft-designed-and-built-components"></a>Componentes criados e projetados pela Microsoft

Cada camada do Surface do chip para a nuvem é desenvolvida e mantida pela Microsoft, dando a você controle final, proteção proativa e tranquilidade em qualquer lugar e no entanto, o trabalho é feito. Os dispositivos Surface são navegáveis com os protocolos de segurança mais fortes que a Microsoft oferece e permite o gerenciamento simplificado que reduzem a complexidade de IT que ajuda os usuários a se concentrarem no trabalho.

O Surface impulsiona a segurança por meio de uma abordagem aprofundada de defesa utilizando uma camada de sub-componentes independentes de defesa. Do chip para a nuvem, ou uma UEFI que garante uma raiz de confiança para o Microsoft Defender for Endpoint com AI que funciona para impedir, detectar, investigar e responder a ameaças avançadas, o Surface impõe a posição de que o surface integrado da Microsoft é melhor do que o bolt-on.

| Recurso                         | Descrição                                                                                                                                                                                                                                                                                                                         | Saiba mais                                                                                                                                                                   |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| UEFI criado pela Microsoft            | Software que configura o dispositivo e inicializa Windows 10<br>Controla a inicialização inicial do dispositivo e Windows 10 e, em seguida, fornece serviços de tempo de execução de firmware para o sistema operacional. garante significativamente mais controle sobre o hardware de um dispositivo por meio do gerenciamento on-prem do SEMM e do gerenciamento baseado em nuvem DFCI por meio de Microsoft Endpoint Manager | [Gerenciar configurações de UEFI do Surface](manage-surface-uefi-settings.md)                                                                        |
| TPM físico 2.0                | Módulo de Plataforma Confiável - Microcontrolador dedicado projetado para proteger o hardware por meio de chaves criptográficas integradas.<br>Criptografa e armazena chaves (BitLocker, Windows Hello, Credenciais do AD,)<br>PCR - Configuração da Plataforma Registra que as medidas seguras e as métricas relevantes para detectar alterações na configuração anterior  | [Visão geral da tecnologia Trusted Platform Module](/windows/security/information-protection/tpm/trusted-platform-module-overview)                 |
| Windows Hello para Empresas      | Substitui senhas por autenticação forte de dois fatores em PCs e dispositivos móveis. Essa autenticação biométrica consiste em um novo tipo de credencial de usuário que está vinculado a um dispositivo e usa uma biometria ou PIN.                                                                                                                   | [Como Windows Hello para Empresas funciona - Microsoft 365 Segurança](/windows/security/identity-protection/hello-for-business/hello-how-it-works) |
| Criptografia integrada           | A criptografia integrada é habilitada pelo BitLocker para proteger e criptografar seus dados e Windows Hello habilitar o logon sem senha, combinado com TPM físico e UEFI.                                                                                                                                                                 | [BitLocker (Windows 10) - Microsoft 365 Segurança](/windows/security/information-protection/bitlocker/bitlocker-overview)                     |
| Proteção Avançada contra Ameaças do Microsoft Defender para Ponto de extremidade | Fornece uma plataforma de segurança de ponto de extremidade empresarial projetada para ajudar as redes corporativas a impedir, detectar, investigar e responder a ameaças avançadas.                                                                                                                                                                               | [Proteção Avançada contra Ameaças do Microsoft Defender para Ponto de extremidade](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)                 |

## <a name="factory-level-security-protocols-and-inspection"></a>Inspeção e protocolos de segurança de nível de fábrica

Do firmware ao sistema operacional e a cada componente de hardware antes do assembly final, os dispositivos Surface estão seguros contra ataques de cadeia de fornecimento em nossas instalações de desenvolvimento e manufatura fisicamente protegidas.

Por definição, uma cadeia de fornecimento segura fornece produtos concluídos que atendem a metas operacionais, de qualidade e de desempenho. Simplificando, uma cadeia de fornecimento segura garante que todos os componentes sejam originais e livres de manipulação ou sabotagem não autorizada ou mal-intencionada. Fabricamos dispositivos em fábricas altamente protegidas, onde tudo, desde o firmware UEFI até o sistema operacional, vem diretamente da Microsoft. Nenhum fornecedor de BIOS de terceiros está envolvido. Essa é uma parte forte de como protegemos contra ataques de cadeia de fornecimento para produtos Surface. Reduzimos o Surface de ataque em nossa UEFI removendo qualquer código nãousado, incluindo funções SMM do modo de gerenciamento do sistema que são dispositivos que não precisam.

A proteção de instalações contra ataques, intrusões e outras ameaças externas baseadas na Internet exige um investimento contínuo em áreas-chave, incluindo:

- Inspeção rigorosa e teste de todos os componentes nos locais de assembly finais.
- Mantendo altos níveis de segurança física na fábrica.
- Uso apenas de firmware, drivers e sistema operacional & desenvolvidos pela Microsoft.
- Logística segura e entrega de operadora confiável de dispositivos Surface diretamente para revendedores da Microsoft.

Ao sair da fábrica, os dispositivos Surface for Business são protegidos por meio Windows Atualização em todo o ciclo de vida.

## <a name="advanced-windows-security-features"></a>Recursos avançados Windows segurança

A escalada de ataques de privilégios é o melhor amigo de um ator mal-intencionado, e eles geralmente direcionam informações confidenciais armazenadas na memória. Esses tipos de ataques podem transformar um pequeno comprometimento do modo de usuário em um comprometimento total do sistema operacional e do dispositivo. Para combater esses tipos de ataques, a Microsoft desenvolveu a segurança baseada em virtualização (VBS) e a integridade de código protegido pelo Hypervisor (HVCI, também conhecida como integridade de memória). O VBS e o HVCI usam o poder dos recursos de hardware, como a virtualização, para oferecer melhor proteção contra malware comum e sofisticado, realizando operações de segurança confidenciais em um ambiente isolado.

O Surface acompanha Windows recursos avançados de segurança de hardware habilitados para dar aos clientes uma segurança ainda mais forte interna e ativada por padrão.

## <a name="virtualization-based-security"></a>Segurança baseada em virtualização

A segurança baseada em virtualização, ou VBS, usa recursos de virtualização de hardware para criar e isolar uma região segura de memória do sistema operacional normal. Windows pode usar esse "modo de segurança virtual" para hospedar várias soluções de segurança, fornecendo a eles uma proteção muito maior contra vulnerabilidades no sistema operacional e impedindo o uso de explorações mal-intencionadas que tentam vencer proteções.

### <a name="hypervisor-enforced-code-integrity-hvci"></a>Hypervisor-Enforced integridade de código (HVCI)

O HVCI usa o VBS para reforçar significativamente a imposição da política de integridade de código. A integridade do código do modo kernel verifica todos os drivers e binários do modo kernel antes de serem iniciados e impede que drivers não assinados ou arquivos do sistema são carregados na memória do sistema. Conforme mostrado no diagrama a seguir, o HVCI é executado em um ambiente de execução isolado e verifica a integridade do código do kernel de acordo com a política de assinatura do kernel.

O VBS e o HVCI estão habilitados fora da caixa nos seguintes dispositivos Surface:

- Surface Laptop 4
- Surface Pro 7+
- Surface Book 3,
- Surface Laptop Go,
- Surface Pro X

## <a name="secure-boot-and-boot-guard"></a>Proteção de inicialização e inicialização segura

A Raiz da Confiança dos dispositivos Surface verifica assinaturas e medidas para garantir que cada estágio seja seguro e autêntico antes de permitir que a próxima fase de inicialização prossiga. Habilitada pela UEFI e pelo TPM 2.0, a Inicialização Segura garante que apenas o código assinado, medido e implementado corretamente possa ser executado em um dispositivo Surface.

Conforme mostrado na Figura 2, a integridade do firmware é verificada em cada estágio, desde pressionar o botão de energia para executar o sistema operacional.

 > [!div class="mx-imgBorder"]
 > ![Figura 1. Inicialização segura para dispositivos Surface ](images/secboot.png)
  *Figura 1. Inicialização segura para dispositivos Surface*

| Etapa  | Fase de inicialização segura                                                                                                                                                                                                                                      |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | A segurança é instanciada sempre que o botão de energia é pressionado a partir de uma raiz de confiança fornecida pelo TPM. Quando um dispositivo é ligado pela primeira vez, o sistema executa uma série de verificações de segurança para garantir que o firmware do dispositivo não tenha sido adulterado ou corrompido. |
| **2** | Quando ligado, o SoC usa uma chave de fornecedor de chipset para validar e inicia o carregamento de microcódigo usando o ACM (Authenticated Code Module) (em dispositivos baseados em Intel).                                                                              |
| **3** | O ACM mede o código UEFI antes de carregá-lo e compara-o à medida conhecida no Registro de Configuração de Plataforma do TPM [PCR] para garantir que o código UEFI não tenha sido alterado.                                                                |
| **4** | Antes de permitir que a UEFI seja executado, o Boot Guard verifica se a UEFI está assinada com uma chave surface OEM. O módulo UEFI inicialmente verificado é a segurança da SEC e as seções PRÉ-EFI DO PE mostradas no diagrama.                                                |
| **5** | A seção DOI verifica se há uma assinatura surface no ambiente de execução de driver, o módulo DXE, conforme ele é carregado. O módulo DXE inclui a fase de seleção do dispositivo de inicialização.                                                                          |
| **6** | Depois que o dispositivo de inicialização é selecionado, a UEFI lê o dispositivo de inicialização e verifica a assinatura do carregador de inicialização do sistema operacional antes de permitir que ele seja executado.                                                                                                             |
| **7** | Em seguida, o sistema operacional verifica suas assinaturas em seu componente principal à medida que ele traz o sistema operacional.

### <a name="malware-protection"></a>Proteção contra malware

Para ajudar a proteger seu dispositivo contra ataques de software mal-intencionados, o Surface habilita a inicialização segura para garantir que uma versão autentica do Windows 10 seja iniciada e que o firmware seja tão original quanto era quando saiu da fábrica.

O SoC em dispositivos Surface tem um processador de segurança separado de todos os outros núcleos. Quando você inicia o dispositivo Surface pela primeira vez, apenas o processador de segurança é iniciado antes que qualquer outra coisa possa ser carregada. A inicialização segura é usada para verificar se os componentes do processo de inicialização, incluindo drivers e o sistema operacional, são validados em relação a um banco de dados de assinaturas válidas e conhecidas. Isso ajuda a evitar que os ataques de um sistema cloanado ou modificado, com um código mal-intencionado, sejam exibidos de forma diferente. Para saber mais, confira [visão geral da inicialização segura](/windows-hardware/design/device-experiences/oem-secure-boot).

Depois que o sistema operacional for verificado como proveniente da Microsoft e seu dispositivo Surface concluir com êxito o processo de inicialização, o dispositivo examinará o código executável. Nossa abordagem para a proteção do sistema operacional envolve identificar a assinatura do código de todos os executáveis, permitindo que somente os que passarem nossas restrições sejam carregados no tempo de execução. Esse método de assinatura de código permite que o sistema operacional verifique o autor e confirme que o código não foi alterado antes de ser executado no dispositivo.

## <a name="drtm-protection-in-amd-devices"></a>Proteção DRTM em dispositivos AMD

Dispositivos Surface que contêm processadores AMD implementam a Inicialização Segura de maneira equivalente. Surface Laptop 4 com processador AMD Ryzen Microsoft Surface Edition protege o firmware do power-on inicial usando a Raiz Dinâmica das Medições de Confiança (DRTM). O DRTM controla todas as CPUs, forçando a execução ao longo de um caminho medido e restabelece a confiança em vários estágios para verificar a integridade do firmware/software do sistema. A transição para esse estado confiável fornece proteção adicionada contra possíveis ataques nos estágios de inicialização.

O DRTM protege as medidas garantindo que elas sejam criptografadas usando a Criptografia total de memória do sistema (TSME). Depois que o TSME for definido, se não puder ser limpo, exceto por uma redefinição do sistema. Uma nova chave de criptografia para cada redefinição garante a criptografia de uso único para segurança.

As chamadas de tempo de execução para o Modo de Gerenciamento do Sistema (SMM) são executadas no nível mais alto, o que pode ser arriscado se o código SMM tiver algum problema. Surface Laptop 4 com AMD Ryzen protege o sistema interceptando o SMI (System Management Interrupts) e expedindo a execução do código SMM para um nível menor (usuário) para proteger o sistema contra acesso inválido a códigos e dados. A proteção SMM usa proteções de hardware para restringir o código, os dados e os recursos do sistema que podem ser acessados, reforçando ainda mais a proteção contra incidentes inadvertentes ou mal-intencionados.

Surface Laptop 4 com AMD Ryzen oferece suporte a Diretrizes de Resiliência de Firmware de Plataforma [NIST 800-193](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-193.pdf), além do suporte robusto de atualização de firmware. O mecanismo de atualização resiliente para firmware de inicialização usa um mecanismo de Recuperação A-B que fornece recuperação automática para uma cópia de backup do firmware caso a sequência de inicialização detecte uma cópia corrompida do firmware durante a inicialização.

Para saber mais sobre DRTM e SMM, consulte [How a Windows Defender System Guard helps protect Windows 10 - Windows security | Microsoft Docs](/windows/security/threat-protection/windows-defender-system-guard/how-hardware-based-root-of-trust-helps-protect-windows)

## <a name="remote-device-management-control"></a>Controle de gerenciamento de dispositivo remoto

Os administradores de TI podem gerenciar remotamente dispositivos Surface sem precisar tocar fisicamente em todos os dispositivos. Microsoft Endpoint Manager com o Intune e o Windows Autopilot permite o gerenciamento remoto completo de dispositivos Surface a partir do Azure Cloud, fornecendo dispositivos totalmente configurados aos usuários durante a inicialização. Os recursos wipe e retire permitem que a IT reutilizar um dispositivo facilmente para um novo usuário remoto e apagar um dispositivo que foi roubado. Isso permite recursos de resposta rápida e segura em caso de perda ou roubo de um dispositivo Surface, permitindo que você remova remotamente todos os dados da empresa e reconfigure o Surface como um dispositivo totalmente novo.

| Recurso                                        | Descrição                                                                                                                                                                                                                                                                                                                                                                                                        | Saiba mais                                                                                                                                                                                                                                                              |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DCFI (Interface de Configuração do Firmware de Dispositivo) | Fornece gerenciamento de firmware remoto em escala de nuvem com provisionamento de dispositivo de toque zero. A PRÓPRIA UEFI da Microsoft permite uma implementação DCFI mais forte, permitindo que as organizações desabilitem elementos de hardware e bloqueiem remotamente a UEFI usando o Intune. ¹                                                                                                                                                                          | [Gerenciamento pelo Intune das configurações de UEFI do Surface](surface-manage-dfci-guide.md)<br> <br>[Gerenciar configurações de UEFI do Surface](manage-surface-uefi-settings.md)                                          |
| SEMM (Modo de Gerenciamento Enterprise Surface)      | Habilita o envolvimento corporativo centralizado das configurações de firmware UEFI em ambientes locais, híbridos e de nuvem.¹                                                                                                                                                                                                                                                                                           | [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)                                                                                                                                                       |
| Windows Update para Empresas                    | Permite que os administradores de WINDOWS 10 mantenha os dispositivos Windows 10 em sua organização sempre atualizados com as defesas de segurança mais recentes, recursos de Windows e firmware do Surface conectando diretamente esses sistemas ao serviço Windows Update. Você pode usar soluções de Política de Grupo ou MDM, como Microsoft Intune, para configurar as configurações de atualização Windows para Empresas que controlam como e quando os dispositivos Surface são atualizados. | [Windows Update para Empresas](/windows/deployment/update/waas-manage-updates-wufb)<br> <br>[Gerenciar e implantar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md) |

## <a name="references"></a>Referências

1. Surface Go e Surface Go 2 usam uma UEFI de terceiros e não suportam DFCI. O DFCI está disponível para o Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 e Surface Pro X. 

## <a name="learn-more"></a>Saiba mais

- [Os novos PCs surface habilitam a segurança baseada em virtualização (VBS) por padrão para capacitar os clientes a fazer mais, com segurança](https://www.microsoft.com/security/blog/2021/01/11/new-surface-pcs-enable-virtualization-based-security-vbs-by-default-to-empower-customers-to-do-more-securely/)
- [Estudo destaca a função crítica da proteção de firmware do Surface](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/study-highlights-critical-role-of-surface-firmware-protection/ba-p/2245244)
- [Aprimorando a segurança e a conformidade com o Microsoft Surface e Microsoft 365](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/enhancing-security-and-compliance-with-microsoft-surface-and/ba-p/2283062)
- [Gerenciar configurações de UEFI do Surface](manage-surface-uefi-settings.md)
- [Gerenciamento pelo Intune das configurações de UEFI do Surface](surface-manage-dfci-guide.md)
- [Project Mu](https://microsoft.github.io/mu/)
