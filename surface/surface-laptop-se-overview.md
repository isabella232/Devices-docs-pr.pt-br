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
ms.openlocfilehash: a99c3241eea0099b90de9c64ff840306aa98e58d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448315"
---
# <a name="surface-laptop-se-overview"></a>Visão geral do Surface Laptop SE

Surface Laptop ES fornece uma experiência de dispositivo gerenciado que simplifica o aprendizado para alunos a um custo acessível. Ele executa Windows 11 ES, um sistema operacional de primeira nuvem, e vem [pré-carregado](#pre-installed-apps) com aplicativos amplamente usados como Microsoft Teams, Word, PowerPoint, Excel, OneNote, Edge, Minecraft: Education Edition, Flipgrid e muito mais. 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop ES mostrando Windows 11 ES menu Iniciar":::<br>
*Figura 1. Surface Laptop ES mostrando Windows 11 ES menu Iniciar*

Surface Laptop ES oferece suporte à maioria dos aplicativos que os alunos e educadores precisam, incluindo PWAs (Aplicativos Web Progressivos), Aplicativos da Plataforma universal de Windows (UWPs) e um conjunto de aplicativos [win32 & Microsoft Store](#install-optional-apps). Ao contrário de outros dispositivos Surface, Surface Laptop ES impede que os usuários instalem seus próprios aplicativos. Em vez disso, os administradores de TECNOLOGIA ou os leads técnicos gerenciam Surface Laptop ES [dispositivos usando](/mem/intune/fundamentals/what-is-intune) Microsoft Endpoint Manager, o que inclui Microsoft Intune, [Microsoft Intune para](https://www.microsoft.com/education/intune) Educação e o novo Portal de Gerenciamento de [Superfície](surface-management-portal.md). 

> [!NOTE]
> Este artigo destina-se a administradores de IT e funcionários de educação que implantam e gerenciam dispositivos para usuários escolares. Para obter informações gerais ou solicitar, consulte [Surface Laptop ES Laptop Fino para Alunos](https://www.microsoft.com/surface/business/surface-laptop-se).

## <a name="simplified-deployment-management--security"></a>Implantação simplificada, gerenciamento & segurança

- Conclua a implantação de toque baixo para novos dispositivos usando Windows Autopilot, aplicando rapidamente políticas e instalando aplicativos. Windows Autopilot fornece implantação de baixo toque e imagens fora da caixa, com muitos aplicativos e políticas pré-instalados e pré-configurados. A IT pode ajustar facilmente as configurações do dispositivo, incluindo configurações de firmware, e instalar os aplicativos de que os alunos precisam para que tudo esteja pronto para ir quando eles ativarem o dispositivo pela primeira vez.
- Depois que os dispositivos são implantados, Microsoft Intune oferece gerenciamento remoto simplificado durante todo o ano escolar, dando à IT a capacidade de gerenciar aplicativos, controlar a segurança e a privacidade e gerar relatórios de conformidade.
- Bloqueie o sistema operacional com bloqueio de tampa quando o laptop estiver fechado e controle o acesso físico com o Slot de Segurança Integrado kensington Nano™.
- Uma dobradiça não exposta recentemente projetada, um chassi de plástico e uma borda de plástico ao redor da tela que sai para o biseão fornecem mais durabilidade para atender melhor às necessidades e demandas de uso do aluno.
- O Intune e o DFCI suportam atualizações de dispositivo seguro e gerenciamento para a camada de firmware. Os administradores de IT podem controlar elementos de hardware, como microfones, portas USB, câmeras e Bluetooth e remover energia para periféricos. A embalagem surface digitalizável exclusiva permite a fácil identificação de dispositivos, com o número da ID do dispositivo permanecendo o mesmo quando chegar a hora de se registrar de novo.

### <a name="surface-management-portal"></a>Portal de Gerenciamento do Surface

Quando você se registra Surface Laptop ES gerenciamento de nuvem e os usuários fizerem logoff pela primeira vez, as informações desses dispositivos Surface fluem automaticamente para o Portal de Gerenciamento do Surface, dando a você um único painel de vidro para atividades de administrador de dispositivos específicos do [Surface](surface-management-portal.md). Você pode obter informações sobre conformidade do dispositivo, atividade de suporte e cobertura de garantia. Consulte rapidamente o status de cada dispositivo, quais ainda estão em garantia ou expirando em breve, e o status das solicitações de suporte ativas.

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Surface Management Portal mostrando a cobertura de garantia para Surface Laptop ES":::
*Figura 2. Surface Management Portal mostrando a cobertura de garantia para Surface Laptop ES*

## <a name="common-admin-scenarios"></a>Cenários de administração comuns

| Cenário                                                            | Descrição                                                                                                                                                                                                                                                                                                                          | Saiba mais                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Configurar remotamente Surface Laptop ES dispositivos com Windows Autopilot | Windows Autopilot fornece implantação e imagens de baixo toque fora da caixa, com muitos aplicativos e políticas pré-instalados e pré-configurados. A IT pode ajustar facilmente as configurações do dispositivo, incluindo configurações de firmware, e instalar os aplicativos de que os alunos precisam para que tudo esteja pronto para ir quando eles ativarem o dispositivo pela primeira vez.                 |[Configurar o Intune para dispositivos Education com Windows Autopilot](/intune-education/windows-autopilot-setup)<br><br>[Como registrar meus dispositivos?](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| Implantar atualizações via Intune para Educação                             | Os administradores de usar Microsoft Intune para empurrar as atualizações do sistema operacional e do aplicativo para Surface Laptop ES dispositivos em toda a escola durante todo o ano. Se necessário, eles podem desabilitar elementos de hardware como a câmera ou Bluetooth em um dispositivo individual ou redefinir um dispositivo específico se um aluno estiver enfrentando problemas técnicos. |[Gerenciar dispositivos executando Windows 11 ES](/intune-education/windows-11-se-overview)<br><br>[Recursos e documentação do Microsoft Education](/microsoft-365/education/)<br><br>[Começar com o Intune para Educação](/microsoft-365/education/deploy/intune-for-education)<br><br>[Usar o Intune para Educação para gerenciar grupos, aplicativos e configurações](/microsoft-365/education/deploy/use-intune-for-education) |
| Substituir dispositivos conforme necessário                                           | Se os alunos quebrarem a tela ou danificarem o dispositivo, os administradores de IT poderão implantar rapidamente dispositivos de reposição, transferindo as identidades de nuvem dos alunos para os novos dispositivos.                                                                                                  |[Ações de dispositivo remoto no Intune para Educação](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| Implantar novos aplicativos via Intune                                          | Se os professores solicitarem um novo aplicativo, os administradores de IT poderão instalá-lo remotamente em todos os dispositivos de alunos usando o Intune.                                                                                                                                                                                                                            |[Instalar aplicativos para todos os usuários](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| Redefinir dispositivos via Intune                                            | Quando os alunos Surface Laptop ES seus dispositivos de Surface Laptop ES no final do ano letivo, os administradores de IT podem usar o Intune para redefinir os dispositivos para a próxima classe que precisará deles no início do próximo ano letivo.                                                                                                           |[Usar Redefinição do Autopilot para reconfigurar dispositivos com o Intune para Educação](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>Aplicativos pré-instalados

Surface LaptopES vem com os seguintes aplicativos pré-instalados:  

- Microsoft Excel
- Flipgrid
- Groove música
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
- Ferramenta Snipping
- Notas grudentas
- Aplicativo Surface
- Surface Diagnostic Toolkit
- Dicas
- Gravador de Voz
- Tempo
- Word

## <a name="install-optional-apps"></a>Instalar aplicativos opcionais

Os administradores de IT podem instalar [aplicativos adicionais](/education/windows/windows-11-se-overview#available-apps) , como o Chrome ou o Zoom via Intune. Observe que não há nenhuma loja de aplicativos para Surface Laptop ES. Consulte as instruções a seguir para concluir a implantação do aplicativo: 

- [Implantação de aplicativos](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>Capacidade de reparo

Surface Laptop ES Surface Laptop ES foi projetado para habilitar técnicos qualificados para fazer o serviço local de dispositivos substituindo rapidamente os componentes principais:

- Módulo de exibição  
- Bucket & teclado
- Módulo & Wi-Fi alto-falante
- Bateria
- Pés

As escolas podem usar um Provedor de Serviços Autorizados ou seus próprios técnicos qualificados para reparar dispositivos no local seguindo o "Guia de Serviço Surface Laptop ES" fornecido pela Microsoft, disponível nos Guias de Serviço do [Surface](https://www.microsoft.com/download/100440).

Para saber mais, confira:

- [Surface Laptop ES vídeo de reparo](https://youtu.be/fVjjSqfp75g)
- [Principais soluções de suporte para dispositivos Surface](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop ES de tecnologia

| Recurso                     | Descrição                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dimensões**              | - 11,17" x 7,6" x 0,70" (283,70 mm x 193,05 mm x 17,85 mm)                                                                                                                                                |
| ****<sup>Armazenamento 1</sup>     | - A bordo, cartão multimídia incorporado (eMMC) de 64 GB ou 128 GB                                                                                                                                                 |
| **Display**                 | - Tela: Módulo de exibição de vidro líquido TFT de 11,6"<br>- Resolução de exibição: 1366 x 768 (135 PPI)<br>- Proporção: 16:9<br>- Taxa de contraste: 800:1 (típico)<br>- Luminância: 220 nits<br>- Sem vidro de cobertura |
| **Bateria**                 | - 35Wh (nominal), 33,9Wh (mín)<br>- 16 horas de duração da bateria <sup>2</sup>                                                                                                                                              |
| **Memória**                  | - 4 GB ou 8 GB DDR4 (2400 MHz min)                                                                                                                                                                          |
| **CPU/Gráficos**          | - Processador Intel® Celeron® N4020 / Intel® UHD Graphics 600<br>- Processador Intel® Celeron® N4120 / Intel® UHD Graphics 600                                                                                |
| **Connections**             | - 1 x USB-A<br>- 1 x USB-C<br>- Conector DC do tipo 1 x barril<br>- 1 x 3,5 mm Headphone/Mic Jack                                                                                                           |
| **Segurança**                | - TPM de firmware em todas as configurações (Comercial)<br>- Slot de Bloqueio de Segurança Nano                                                                                                                        |
| **Câmeras, vídeo, & áudio** | - Câmera frontal de 1MP com vídeo de até 720p 30fps<br>- Alto-falantes estéreo de 2W<br>- Microfone digital único                                                                                              |
| **Software**                | - Windows 11 ES<br>- Microsoft 365 para Educação3<sup></sup>                                                                                                                                                         |
| **Sem fio**                | - Wi-Fi: 802.11ac (2x2)<br>- Bluetooth SEM fio 5.0 LE                                                                                                                                                    |
| **Sensores**                 | - 1 x sensor de efeito Hall                                                                                                                                                                                  |
| **Exterior**                | - Invólucro: todo o corpo de plástico não pintado<br>- Cores: Glaciar<br>- Botões físicos: Energia e volume no teclado<br>- Dobradiça: ângulo aberto de 135 graus                                                          |
| **Espessura**                  | - 2,45 lb. (1.111,3 g)                                                                                                                                                                                    |
| **Teclado e trackpad**   | - Teclado Windows padrão para 11,6" sem backlight<br>- Padrão sem trackpad de precisão flutuante                                                                                                      |
| **Térmicos**                | - Arrefessado passivamente                                                                                                                                                                                        |
| **Fonte de alimentação**            | - In-box, 45W com carregador de barril dc                                                                                                                                                                      |
| **Na caixa**              | - Dispositivo Surface<br>- Fonte de energia<br>- Guia de Início Rápido<br>- Documentos de segurança e garantia                                                                                                              |
| ****<sup> Garantia 4</sup>    | - Garantia de hardware limitada de um ano                                                                                                                                                                      |

## <a name="references"></a>Referências

1. Os softwares e atualizações do sistema usam espaço de armazenamento significativo. O armazenamento disponível está sujeito a alterações com base no software do sistema e nas atualizações e no uso de aplicativos. 1 GB = 1 bilhão de bytes. 1 TB = 1.000 GB. Consulte [Surface Armazenamento](https://support.microsoft.com/help/4023513/surface-surface-storage?) para obter mais detalhes.
2. A duração da bateria varia significativamente com base no uso, configuração de rede e recurso, intensidade do sinal, configurações e outros fatores. Consulte [Teste de bateria surface e desempenho estimado](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) para obter detalhes.
3. Requer a qualificação Microsoft 365 ou Office 365 licença; vendida separadamente. [Compare Microsoft 365 planos de educação](https://aka.ms/EDU-Plan-Comparison).
4. A Garantia Limitada da Microsoft está além dos seus direitos de direito do consumidor.


## <a name="learn-more"></a>Saiba mais

- [Solicitar Surface Laptop ES](https://www.microsoft.com/surface/business/surface-laptop-se)
- [Apresentando Surface Laptop ES para Educação](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows 11 SE para Educação](/education/windows/windows-11-se-overview)
- [Gerenciar dispositivos executando Windows 11 ES](/intune-education/windows-11-se-overview)
- [Configurar o Intune para dispositivos Education com Windows Autopilot](/intune-education/windows-autopilot-setup)
- [Recursos e documentação do Microsoft Education](/microsoft-365/education/)
- [Outlook na Web](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
