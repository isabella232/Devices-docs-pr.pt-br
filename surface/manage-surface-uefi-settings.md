---
title: Gerenciar configurações de UEFI do Surface
description: Use as configurações de UEFI do Surface para habilitar ou desabilitar dispositivos ou componentes, definir configurações de segurança e ajustar as configurações de inicialização do dispositivo Surface.
keywords: firmware, segurança, recursos, configurar, hardware
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 04/01/2022
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e38fb3ae8a25fddfcb64985a64b41d4d2e084178
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472650"
---
# <a name="manage-surface-uefi-settings"></a>Gerenciar configurações de UEFI do Surface

 Os dispositivos Surface PC foram projetados para utilizar uma UEFI (Unified Extensible Firmware Interface) exclusiva projetada pela Microsoft especificamente para esses dispositivos. As configurações de UEFI do Surface fornecem a capacidade de habilitar ou desabilitar dispositivos e componentes internos, proteger as configurações de UEFI contra alterações e ajustar as configurações de inicialização do dispositivo Surface.

## <a name="supported-products"></a>Produtos com suporte

O gerenciamento de UEFI é compatível com o seguinte:

- Surface Pro 4, Surface Pro (5ª geração), Surface Pro 6, Surface Pro 7, Surface Pro 7+ (somente SKUs comerciais), Surface Pro 8 (somente SKUs comerciais), Surface Pro X
- Surface Laptop (1ª geração), Surface Laptop 2, Surface Laptop 3 (somente processadores Intel), Surface Laptop Go, Surface Laptop 4 (somente SKUs comerciais), Surface Laptop ES
- Surface Studio (1ª geração), Surface Studio 2
- Surface Book (todas as gerações)
- Surface Laptop Studio (somente SKUs comerciais)
- Surface Go, Surface Go [21<sup></sup>](#references), Surface Go 3 (somente SKUs comerciais)

>[!TIP]
> Os SKUs comerciais (também conhecidos como Surface for Business) executam Windows 10 Pro/Enterprise ou SKUs de consumidor do Windows 11 Pro/Enterprise; executam Windows 10/Windows 11 Home. Na UEFI, as SKUs comerciais são os únicos modelos a serem exibidos na página [Dispositivos e](#uefi-devices-page) [na página Gerenciamento](#uefi-management-page). Para saber mais, confira [Exibir as informações do sistema](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 


## <a name="support-for-cloud-based-management"></a>Suporte para gerenciamento baseado em nuvem

Com perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados Microsoft Intune (agora disponíveis em versão prévia pública), o gerenciamento uefi do Surface estende a pilha de gerenciamento moderna até o nível de hardware UEFI. A DFCI dá suporte ao provisionamento sem toque, elimina senhas de BIOS, fornece controle das configurações de segurança , incluindo opções de inicialização e periféricos internos, e estabelece as bases para cenários de segurança avançados no futuro. A DFCI está disponível atualmente para Surface Laptop ES, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 e Surface Pro X. Para obter mais informações, consulte [Intune gerenciamento de configurações de UEFI do Surface](surface-manage-dfci-guide.md).

## <a name="open-surface-uefi-menu"></a>Abrir o menu UEFI do Surface

Para ajustar as configurações de UEFI durante a inicialização do sistema:

1. Desligue o Surface e aguarde cerca de 10 segundos para verificar se ele está desligado.
2. Pressione e segure o **botão aumentar o volume** e, ao mesmo tempo, pressione e solte o **botão Ligar/Desligar.**
3. À medida que o logotipo da Microsoft ou do Surface for exibido na tela, continue a manter o **botão aumentar o volume** até que a tela UEFI seja exibida.

## <a name="uefi-pc-information-page"></a>Página de informações do COMPUTADOR UEFI

A página de informações do computador inclui informações detalhadas sobre seu dispositivo Surface:

- **Modelo** – o modelo do dispositivo Surface será exibido aqui, como Surface Book 2 ou Surface Pro 7. A configuração exata do dispositivo não é mostrada (como processador, tamanho do disco ou tamanho da memória).
- **UUID** – esse número de identificação universalmente exclusivo é específico de seu dispositivo e usado para identificar o dispositivo durante a implantação ou gerenciamento.

- **Número de** série – esse número identifica esse dispositivo Surface específico para cenários de marcação e suporte de ativos.
- **Marca do Ativo** – a marca do ativo é atribuída ao dispositivo Surface com a [Ferramenta de Marca do Ativo](assettag.md).

Você também encontrará informações detalhadas sobre o firmware de seu dispositivo Surface. Os dispositivos Surface têm vários componentes internos que executam diferentes versões do firmware. A versão do firmware de cada um dos seguintes dispositivos é exibida na página **Informações do computador** (como mostrado na Figura 1):

- Sistema UEFI

- Controlador SAM

- Intel Management Engine

- Controlador Incorporado do Sistema

- Firmware de Toque

:::image type="content" alt-text="Informações do sistema e informações de versão do firmware." source="images/manage-surface-uefi-figure-1.png":::

*Figura 1. Informações do sistema e informações de versão do firmware*

Você pode encontrar informações atualizadas sobre a versão mais recente do firmware para o dispositivo Surface no [Histórico de Atualizações do Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para seu dispositivo.

## <a name="uefi-security-page"></a>Página Segurança uefi

:::image type="content" alt-text="Defina as configurações de segurança uefi do Surface." source="images/manage-surface-uefi-fig4.png":::

*Figura 2. Definir configurações de segurança de UEFI do Surface*

A página Segurança permite que você defina uma senha para proteger as configurações de UEFI. Essa senha deve ser inserida quando você inicializa o dispositivo Surface para UEFI. A senha pode conter os seguintes caracteres (conforme mostrado na Figura 3):

- Letras maiúsculas: A-Z

- Letras minúsculas: a-z

- Números: 1-0

- Caracteres especiais: !@#$%^&*()?<>{}[]-_=+|.,;:''"

A senha deve ter pelo menos seis caracteres e diferencia maiúsculas de minúsculas.

![Adicione uma senha para proteger as configurações de UEFI do Surface.](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figura 3. Adicionar uma senha para proteger as configurações de UEFI do Surface*

Na página Segurança, você também pode alterar a configuração de Inicialização Segura em seu dispositivo Surface. A tecnologia de Inicialização Segura impede que o código de inicialização não autorizado inicialize no dispositivo Surface, o que protege contra infecções por malware do tipo bootkit e rootkit. Você pode desabilitar a Inicialização Segura para permitir que o dispositivo Surface inicialize sistemas operacionais de terceiros ou mídia inicializável. Você também pode configurar a Inicialização Segura para trabalhar com certificados de terceiros, conforme mostrado na Figura 4. Para saber mais, confira [Inicialização Segura](/windows-hardware/design/device-experiences/oem-secure-boot).

![Configurar Inicialização Segura.](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figura 4. Configurar a Inicialização Segura*

Dependendo do dispositivo, você também poderá ver se o TPM está habilitado ou desabilitado. Se você não vir a configuração Habilitar **TPM**, abra tpm.msc no Windows para verificar o status, conforme mostrado na Figura 5. O TPM é usado para autenticar a criptografia para os dados do dispositivo com o BitLocker. Para saber mais, confira a [visão geral do BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).

![Console do TPM.](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figura 5. Console do TPM*

## <a name="uefi-devices-page"></a>Página Dispositivos UEFI

A página Dispositivos permite habilitar ou desabilitar componentes específicos em dispositivos qualificados, incluindo Surface Pro 8, Surface Go 3, Surface Laptop Studio, Surface Pro 7+, Surface Pro 7, Surface Pro X, Surface Laptop 4, Surface Laptop 3, Surface Laptop ES e Surface Book 3. Os componentes consistem no seguinte:

- Encaixe da porta USB

- Slot de cartão MicroSD ou SD

- Câmera Traseira

- Câmera Frontal

- Câmera de infravermelho (IV)

- Wi-Fi e Bluetooth

- Áudio integrado (alto-falantes e microfone)

Cada dispositivo é listado com um botão de controle deslizante que pode ser movido para a posição **Ativado (habilitado** ) ou **Desativado (** desabilitado), conforme mostrado na Figura 6.

:::image type="content" alt-text="Habilitar e desabilitar dispositivos específicos." source="images/manage-surface-uefi-fig5a.png":::

*Figura 6. Habilitar e desabilitar dispositivos específicos*

## <a name="uefi-boot-configuration-page"></a>Página de configuração de inicialização uefi

A página Configuração de Inicialização permite alterar a ordem dos dispositivos de inicialização, bem como habilitar ou desabilitar a inicialização dos seguintes dispositivos:

- Gerenciador de Inicialização do Windows

- Armazenamento USB

- Rede PXE

- Armazenamento interno

Você pode inicializar de um dispositivo específico imediatamente ou deslizar o dedo para a esquerda na entrada desse dispositivo na lista usando a tela touch. Você também pode inicializar imediatamente em um dispositivo USB ou um adaptador de Ethernet USB quando o dispositivo Surface está desligado, pressionando o botão de **Diminuir o Volume** e o botão **Ligar/Desligar** simultaneamente.

Para que a ordem de inicialização especificada entre em vigor, defina **** a opção Habilitar Sequência de Inicialização Alternativa como **Ativado**, conforme mostrado na Figura 7.

:::image type="content" alt-text="Configure a ordem de inicialização do dispositivo Surface." source="images/manage-surface-uefi-fig6.png":::

*Figura 7. Configurar a ordem de inicialização para o dispositivo Surface*

Você também pode ativar e desativar o suporte a IPv6 para PXE com a opção Habilitar **IPv6** para Inicialização de Rede PXE, por exemplo, ao executar uma implantação do Windows usando PXE em que o servidor PXE está configurado somente para IPv4.  

## <a name="uefi-management-page"></a>Página de Gerenciamento de UEFI

A página Gerenciamento permite que você gerencie o uso do Gerenciamento uefi do Zero Touch e outros recursos em dispositivos qualificados, incluindo Surface Pro 8, Surface Go 3, Surface Laptop Studio, Surface Pro 7+, Surface Pro 7, Surface Pro X, Surface Laptop 4, Surface Laptop 3, Surface Laptop ES e Surface Book 3. 

:::image type="content" alt-text="Gerencie o acesso ao Gerenciamento uefi do Zero Touch e outros recursos." source="images/manage-surface-uefi-fig7a.png":::

*Figura 8. Gerenciar o acesso ao Gerenciamento uefi do Zero Touch e outros recursos*

O Gerenciamento uefi de toque zero permite gerenciar remotamente as configurações de UEFI usando um perfil de dispositivo dentro Intune chamada DFCI (Interface de Configuração de Firmware de Dispositivo). Se você não definir essa configuração, a capacidade de gerenciar dispositivos qualificados com DFCI será definida como **Pronto**. Para impedir a DFCI, selecione **Recusar**.

> [!NOTE]
> A página de configurações de Gerenciamento uefi e o uso da DFCI estão disponíveis atualmente para Surface Laptop ES, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 e Surface Pro X.  Para saber mais, confira [Intune de configurações de UEFI do Surface](surface-manage-dfci-guide.md).

## <a name="uefi-exit-page"></a>Página De saída uefi

Use o **botão Reiniciar Agora** na **página Sair** para sair das configurações de UEFI, conforme mostrado na Figura 9.

:::image type="content" alt-text="Saia da UEFI do Surface e reinicie o dispositivo." source="images/manage-surface-uefi-fig7.png":::

*Figura 9. Clique em Reiniciar Agora para sair do UEFI do Surface e reiniciar o dispositivo*

## <a name="surface-uefi-boot-screens"></a>Telas de inicialização UEFI Surface

Quando você atualiza o firmware do dispositivo Surface usando Windows Update instalação manual ou manual, as atualizações não são aplicadas imediatamente ao dispositivo, mas durante o próximo ciclo de reinicialização. Você pode saber mais sobre o processo de atualização de firmware do Surface em [Gerenciar e implantar atualizações de driver e firmware do Surface](manage-surface-driver-and-firmware-updates.md). O progresso da atualização do firmware é exibido em uma tela com barras de progresso de cores diferentes para indicar o firmware de cada componente. A barra de progresso de cada componente é mostrada nas Figuras 9 a 18.

![Atualização de firmware UEFI do Surface com barra de progresso azul.](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Figura 10. A atualização do firmware UEFI do Surface exibe uma barra de progresso azul*

![Firmware do Controlador Inserido do Sistema com barra de progresso verde.](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Figura 11. A atualização de firmware de controlador incorporado no sistema exibe uma barra de progresso verde*

![Atualização de firmware do controlador SAM com barra de progresso laranja.](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Figura 12. A atualização do firmware de SAM Controller exibe uma barra de progresso laranja*

![Firmware do Intel Management Engine com barra de progresso vermelha.](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Figura 13. A atualização de firmware da Intel Management Engine exibe uma barra de progresso vermelho*

![Firmware de toque surface com barra de progresso cinza.](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Figura 14. A atualização de firmware do Surface toque exibe uma barra de progresso cinza*

![Firmware do Surface KIP com barra de progresso verde claro.](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figura 15. A atualização de firmware do Surface KIP exibe uma barra de progresso verde claro*

![Firmware ISH do Surface com barra de progresso rosa.](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figura 16 A atualização de firmware do ISH do Surface exibe uma barra de progresso rosa claro*

![Firmware do Surface Trackpad com barra de progresso cinza.](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figura 17. A atualização do firmware do Surface Trackpad exibe uma barra de progresso rosa*

![Firmware do Surface TCON com barra de progresso cinza claro.](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figura 18. A atualização de firmware do Surface TCON exibe uma barra de progresso cinza claro*

![Firmware do Surface TPM com barra de progresso roxo claro.](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figura 19. A atualização de firmware do Surface TPM exibe uma barra de progresso roxa*

>[!NOTE]
>Uma mensagem de aviso adicional que indica que a Inicialização Segura está desabilitada é exibida, conforme mostrado na Figura 19.

![Tela de inicialização do Surface que indica que a Inicialização Segura foi desabilitada.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figura 20. Tela de inicialização do Surface que indica que a inicialização segura foi desativada nas configurações de UEFI do Surface*

## <a name="references"></a>Referências

1. O Surface Go e o Surface Go 2 usam uma UEFI de terceiros e não dão suporte à DFCI. A DFCI está disponível atualmente para Surface Laptop ES, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 e Surface Pro X.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciamento pelo Intune das configurações de UEFI do Surface](surface-manage-dfci-guide.md)

- [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
