---
title: Visão geral do Surface Laptop SE
description: Este artigo fornece uma visão geral do Surface Laptop ES para educação.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/11/2022
ms.reviewer: hachidan
manager: laurawi
audience: itpro
appliesto:
- Windows 11
ms.openlocfilehash: 2d16d63dda53bbfffbf5d7d9cb080c4e595217a5
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472580"
---
# <a name="surface-laptop-se-overview"></a>Visão geral do Surface Laptop SE

Surface Laptop ES fornece uma experiência de dispositivo gerenciado que simplifica o aprendizado para alunos a um custo acessível. Ele é executado Windows 11 ES, um sistema operacional de primeira nuvem, e vem [pré-carregado](#pre-installed-apps) com aplicativos amplamente usados, como Microsoft Teams, Word, PowerPoint, Excel, OneNote, Edge, Minecraft: Education Edition, Flipgrid e muito mais. 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop ES mostrando Windows 11 ES menu Iniciar":::<br>
*Figura 1. Surface Laptop ES mostrando Windows 11 ES menu Iniciar*

o Surface Laptop ES dá suporte à maioria dos aplicativos de que os alunos e educadores precisam, incluindo PWAs (Aplicativos Web progressivos), UWPs (aplicativos Plataforma Universal do Windows) e um conjunto coletado de aplicativos [win32 & Microsoft Store](#install-optional-apps). Ao contrário de outros dispositivos Surface, Surface Laptop ES impede que os usuários instalem seus próprios aplicativos. Em vez disso, os administradores de TI ou os clientes potenciais técnicos gerenciam [dispositivos Surface Laptop ES](/mem/intune/fundamentals/what-is-intune) usando o Microsoft Endpoint Manager, que inclui Microsoft Intune, [Microsoft Intune for Education](https://www.microsoft.com/education/intune) e o novo Portal de Gerenciamento do [Surface](surface-management-portal.md). 

> [!NOTE]
> Este artigo destina-se a administradores de TI e funcionários educacionais que implantam e gerenciam dispositivos para usuários escolares. Para obter informações gerais ou pedir, consulte [Surface Laptop ES Laptop Slim para Estudantes](https://www.microsoft.com/surface/business/surface-laptop-se).

## <a name="simplified-deployment-management--security"></a>Implantação simplificada, gerenciamento & segurança

- Conclua a implantação de baixo toque para novos dispositivos usando Windows Autopilot, aplicando rapidamente políticas e instalando aplicativos. Windows Autopilot fornece implantação de baixo toque e geração de imagens prontos para uso, com muitos aplicativos e políticas pré-instalados e pré-configurados. A TI pode ajustar facilmente as configurações do dispositivo, incluindo configurações de firmware, e instalar os aplicativos de que os alunos precisam para que tudo esteja pronto quando ligarem o dispositivo pela primeira vez.
- Depois que os dispositivos são implantados, o Microsoft Intune fornece gerenciamento remoto simplificado durante todo o ano letivo, dando à TI a capacidade de gerenciar aplicativos, controlar a segurança e a privacidade e gerar relatórios de conformidade.
- Bloqueie o sistema operacional com bloqueio de tampa quando o laptop estiver fechado e controle o acesso físico com o Slot de Segurança Kensington Nano integrado™.
- Uma dobradiça não exposta recentemente projetada, um chassi de plástico e uma borda de plástico ao redor da tela que sai para o painel fornecem durabilidade extra para atender melhor às necessidades e demandas de uso do aluno.
- Intune e DFCI dão suporte a atualizações seguras de dispositivo e gerenciamento para a camada de firmware. Os administradores de TI podem controlar elementos de hardware, como microfones, portas USB, câmeras e Bluetooth, e remover energia para periféricos. O empacotamento surface digitalizável exclusivo permite a fácil identificação de dispositivos, com o número da ID do dispositivo permanecendo o mesmo quando se trata de registrar novamente.

### <a name="surface-management-portal"></a>Portal de Gerenciamento do Surface

Ao registrar o Surface Laptop ES para gerenciamento de nuvem e os usuários fizerem logon pela primeira vez, as informações desses dispositivos Surface fluem automaticamente para o Portal de Gerenciamento do [Surface](surface-management-portal.md), fornecendo um único painel de controle para atividades de administrador de dispositivo específicas do Surface. Você pode obter informações sobre conformidade do dispositivo, atividade de suporte e cobertura de garantia. Veja rapidamente o status de cada dispositivo, quais ainda estão em garantia ou expirando em breve e o status das solicitações de suporte ativas.

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Portal de Gerenciamento de Superfície mostrando a cobertura de garantia para Surface Laptop ES":::
*Figura 2. Portal de Gerenciamento de Superfície mostrando a cobertura de garantia para Surface Laptop ES*

## <a name="common-admin-scenarios"></a>Cenários comuns de administrador

| Cenário                                                            | Descrição                                                                                                                                                                                                                                                                                                                          | Saiba mais                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Configurar remotamente Surface Laptop ES dispositivos com Windows Autopilot | Windows Autopilot fornece implantação de baixo toque e geração de imagens prontos para uso, com muitos aplicativos e políticas pré-instalados e pré-configurados. A TI pode ajustar facilmente as configurações do dispositivo, incluindo configurações de firmware, e instalar os aplicativos de que os alunos precisam para que tudo esteja pronto quando ligarem o dispositivo pela primeira vez.                 |[Configurar o Intune para dispositivos education com o Windows Autopilot](/intune-education/windows-autopilot-setup)<br><br>[Como devo registrar meus dispositivos?](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| Implantar atualizações por meio do Intune para Educação                             | Os administradores de TI podem usar Microsoft Intune push para enviar atualizações do sistema operacional e do aplicativo Surface Laptop ES dispositivos em toda a escola ao longo do ano. Se necessário, eles podem desabilitar elementos de hardware como a câmera ou Bluetooth em um dispositivo individual ou redefinir um dispositivo específico se um aluno estiver enfrentando problemas técnicos. |[Gerenciar dispositivos que executam Windows 11 ES](/intune-education/windows-11-se-overview)<br><br>[Recursos e documentação do Microsoft Education](/microsoft-365/education/)<br><br>[Introdução com o Intune para Educação](/microsoft-365/education/deploy/intune-for-education)<br><br>[Usar o Intune para Educação para gerenciar grupos, aplicativos e configurações](/microsoft-365/education/deploy/use-intune-for-education) |
| Substituir dispositivos conforme necessário                                           | Se os alunos quebrarem a tela ou danificarem o dispositivo, os administradores de TI poderão implantar rapidamente dispositivos sobressalentes, transferindo as identidades de nuvem dos alunos para os novos dispositivos.                                                                                                  |[Ações de dispositivo remoto no Intune para Educação](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| Implantar novos aplicativos por meio Intune                                          | Se os professores solicitarem um novo aplicativo, os administradores de TI poderão instalá-lo remotamente em todos os dispositivos de alunos usando Intune.                                                                                                                                                                                                                            |[Instalar aplicativos para todos os usuários](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| Redefinir dispositivos por meio Intune                                            | Quando os alunos entregarem seus dispositivos Surface Laptop ES no final do ano letivo, os administradores de TI poderão usar o Intune para redefinir os dispositivos para a próxima classe que precisará deles no início do próximo ano letivo.                                                                                                           |[Usar a redefinição do Autopilot para reconfigurar dispositivos com o Intune for Education](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>Aplicativos pré-instalados

Surface LaptopES vem com os seguintes aplicativos pré-instalados:  

- Microsoft Excel
- Flipgrid
- Música do Groove
- Mapas
- Microsoft Edge
- Microsoft News
- Microsoft Teams
- Microsoft To Do
- Microsoft Whiteboard
- Minecraft Education Edition
- Bloco de notas
- Microsoft Office
- OneDrive
- OneNote
- Outlook na Web
- Paint
- Fotos
- PowerPoint
- Ferramenta de captura
- Notas autoadesivas
- Aplicativo Surface
- Surface Diagnostic Toolkit
- Dicas
- Gravador de Voz
- Tempo
- Word

## <a name="install-optional-apps"></a>Instalar aplicativos opcionais

Os administradores de TI podem instalar [aplicativos adicionais](/education/windows/windows-11-se-overview#available-apps), como Chrome ou Zoom, por meio Intune. Observe que não há nenhuma loja de aplicativos para Surface Laptop ES. Consulte as instruções a seguir para concluir a implantação do aplicativo: 

- [Implantação de aplicativos](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>Capacidade de reparo

Surface Laptop ES Surface Laptop ES é projetado para habilitar técnicos qualificados para serviços de dispositivos localmente substituindo rapidamente os componentes principais:

- Exibir Módulo  
- Bucket & teclado
- Módulo & Wi-Fi locutor
- Bateria
- Pés

As escolas podem usar um Provedor de Serviços Autorizados ou seus próprios técnicos qualificados para reparar dispositivos no local seguindo o "Guia de Serviço Surface Laptop ES" fornecido pela Microsoft, disponível nos Guias de Serviço do [Surface](https://www.microsoft.com/download/100440).

Para saber mais, confira:

- [Surface Laptop ES vídeo de reparo](https://youtu.be/fVjjSqfp75g)
- [Principais soluções de suporte para dispositivos Surface](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop ES técnicas

| Recurso                     | Descrição                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dimensões**              | - 11,17" x 7,6" x 0,70" (283,70 mm x 193,05 mm x 17,85 mm)                                                                                                                                                |
| ****<sup>Armazenamento 1</sup>     | - A bordo, Cartão Multimídia Inserido (eMMC) de 64 GB ou 128 GB                                                                                                                                                 |
| **Display**                 | - Tela: Módulo de Exibição de Cristal Líquido TFT de 11,6"<br>- Resolução de exibição: 1366 x 768 (135 PPI)<br>- Taxa de Proporção: 16:9<br>- Taxa de contraste: 800:1 (típico)<br>- Luminância: 220 nits<br>- Sem vidro de cobertura |
| **Bateria**                 | - 35Wh (nominal), 33,9Wh (min)<br>- 16 horas de duração da bateria <sup>2</sup>                                                                                                                                              |
| **Memória**                  | - 4 GB ou 8 GB DDR4 (2400 MHz min)                                                                                                                                                                          |
| **CPU/elementos gráficos**          | - Processador Intel® Celeron® N4020/Intel® UHD Graphics 600<br>- Processador Intel® Celeron® N4120/Intel® UHD Graphics 600                                                                                |
| **Connections**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x conector DC do tipo barril<br>- Entrada de fone de ouvido/microfone de 1 x 3,5 mm                                                                                                           |
| **Segurança**                | - TPM de firmware em todas as configurações (Comercial)<br>- Slot do Nano Security Lock                                                                                                                        |
| **Câmeras, vídeo, & áudio** | - Câmera frontal de 1MP com vídeo de até 720p 30fps<br>- Alto-falantes estéreo de 2W<br>- Microfone digital único                                                                                              |
| **Software**                | - Windows 11 ES<br>- Microsoft 365 para Educação3<sup></sup>                                                                                                                                                         |
| **Sem fio**                | - Wi-Fi: 802.11ac (2x2)<br>- Bluetooth LE sem fio 5.0                                                                                                                                                    |
| **Sensores**                 | - 1 x sensor de efeito hall                                                                                                                                                                                  |
| **Exterior**                | - Maiúsculas e minúsculas: todo o corpo de plástico não pintado<br>- Cores: Glaciar<br>- Botões físicos: energia e volume no teclado<br>- Dobradiça: ângulo aberto de 135 graus                                                          |
| **Espessura**                  | - 2,45 lb. (1.111,3 g)                                                                                                                                                                                    |
| **Teclado e trackpad**   | - Teclado Windows Padrão para 11,6" sem luz de fundo<br>- Padrão sem trackpad de precisão flutuante                                                                                                      |
| **Térmicas**                | - Passivamente esporádico                                                                                                                                                                                        |
| **Alimentação**            | - In-box, 45W com carregador de barril dc                                                                                                                                                                      |
| **Na caixa**              | - Dispositivo Surface<br>- Fonte de alimentação<br>– Guia de Início Rápido<br>- Documentos de segurança e garantia                                                                                                              |
| **Garantia**<sup> 4</sup>    | - Garantia de hardware limitada de um ano                                                                                                                                                                      |

## <a name="references"></a>Referências

1. As atualizações e o software do sistema usam espaço de armazenamento significativo. O armazenamento disponível está sujeito a alterações com base no software do sistema e no uso de atualizações e aplicativos. 1 GB = 1 bilhão de bytes. 1 TB = 1.000 GB. Consulte [o Surface Armazenamento](https://support.microsoft.com/help/4023513/surface-surface-storage?) para obter mais detalhes.
2. A vida útil da bateria varia significativamente com base no uso, na configuração de rede e no recurso, na intensidade do sinal, nas configurações e em outros fatores. Confira o [teste de bateria do Surface e o desempenho estimado](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) para obter detalhes.
3. Requer a qualificação Microsoft 365 ou Office 365 licença; vendida separadamente. [Compare Microsoft 365 educação](https://aka.ms/EDU-Plan-Comparison).
4. A Garantia Limitada da Microsoft está além dos seus direitos de direito do consumidor.


## <a name="learn-more"></a>Saiba mais

- [Solicitar Surface Laptop ES](https://www.microsoft.com/surface/business/surface-laptop-se)
- [Introdução Surface Laptop ES educação](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows 11 SE para Educação](/education/windows/windows-11-se-overview)
- [Gerenciar dispositivos que executam Windows 11 ES](/intune-education/windows-11-se-overview)
- [Configurar o Intune para dispositivos education com o Windows Autopilot](/intune-education/windows-autopilot-setup)
- [Recursos e documentação do Microsoft Education](/microsoft-365/education/)
- [Outlook na Web](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
- [Uma solução de software de hardware & para educação](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/a-purpose-built-hardware-amp-software-solution-for-education/ba-p/1419013)