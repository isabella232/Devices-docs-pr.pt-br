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
ms.date: 04/13/2021
ms.openlocfilehash: 60ace1e2b9344faeb9f130a56686ffac4643fc37
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911316"
---
# <a name="manage-surface-uefi-settings"></a>Gerenciar configurações de UEFI do Surface

 Os dispositivos Surface PC foram projetados para utilizar uma UEFI (Interface de Firmware Extensível Unificada) exclusiva projetada pela Microsoft especificamente para esses dispositivos. As configurações da UEFI do Surface fornecem a capacidade de habilitar ou desabilitar dispositivos e componentes internos, proteger as configurações da UEFI de serem alteradas e ajustar as configurações de inicialização do dispositivo Surface.

## <a name="supported-products"></a>Produtos com suporte

O gerenciamento UEFI tem suporte no seguinte:

- Surface Pro 4, Surface Pro (5ª Geração), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X
- Surface Laptop (1ª Geração), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4
- Surface Studio (1ª Geração), Surface Studio 2
- Surface Book, Surface Book 2, Surface Book 3
- Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)

## <a name="support-for-cloud-based-management"></a>Suporte para gerenciamento baseado em nuvem

Com perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados Microsoft Intune (agora disponíveis na visualização pública), o gerenciamento uefi do Surface estende a pilha de gerenciamento moderna até o nível de hardware UEFI. O DFCI dá suporte ao provisionamento de toque zero, elimina senhas de BIOS, fornece controle de configurações de segurança, incluindo opções de inicialização e periféricos integrados, e estabelece as bases para cenários avançados de segurança no futuro. O DFCI está disponível para o Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 e Surface Pro X.  Para obter mais informações, consulte [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).

## <a name="open-surface-uefi-menu"></a>Menu Abrir UEFI do Surface

Para ajustar as configurações da UEFI durante a inicialização do sistema:

1. Desligue o Surface e aguarde cerca de 10 segundos para garantir que ele está desligado.
2. Pressione e segure o **botão Volume-up** e , ao mesmo tempo, pressione e solte o **botão Ligar.**
3. À medida que o logotipo da Microsoft ou do Surface aparecer na tela, continue a segurar o **botão Volume-up** até que a tela UEFI apareça.

## <a name="uefi-pc-information-page"></a>Página de informações do computador UEFI

A página de informações do computador inclui informações detalhadas sobre seu dispositivo Surface:

- **Modelo** – O modelo do dispositivo Surface será exibido aqui, como Surface Book 2 ou Surface Pro 7. A configuração exata de seu dispositivo não é exibida, (como processador, tamanho do disco ou tamanho da memória).
- **UUID** – esse número de identificação universalmente exclusivo é específico de seu dispositivo e usado para identificar o dispositivo durante a implantação ou gerenciamento.

- **Número de Série** – esse número é usado para identificar esse dispositivo Surface específico para cenários de marcação de ativos e suporte.
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

:::image type="content" alt-text="Configure as configurações de segurança uefi do Surface." source="images/manage-surface-uefi-fig4.png":::

*Figura 2. Definir configurações de segurança de UEFI do Surface*

A página Segurança permite definir uma senha para proteger as configurações uefi. Essa senha deve ser inserida quando você inicializa o dispositivo Surface para UEFI. A senha pode conter os seguintes caracteres (conforme mostrado na Figura 3):

- Letras maiúsculas: A-Z

- Letras minúsculas: a-z

- Números: 1-0

- Caracteres especiais: !@#$%^&*()?<>{} []-_=+|.,;''"

A senha deve ter pelo menos 6 caracteres e diferencia maiúsculas de minúsculas.

![Adicione uma senha para proteger as configurações do Surface UEFI.](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figura 3. Adicionar uma senha para proteger as configurações de UEFI do Surface*

Na página Segurança também é possível alterar a configuração de Inicialização Segura no dispositivo Surface. A tecnologia de Inicialização Segura impede que o código de inicialização não autorizado inicialize no dispositivo Surface, o que protege contra infecções por malware do tipo bootkit e rootkit. Você pode desabilitar a Inicialização Segura para permitir que o dispositivo Surface inicialize sistemas operacionais de terceiros ou mídia inicializável. Você também pode configurar a Inicialização Segura para funcionar com certificados de terceiros, conforme mostrado na Figura 4. Leia mais sobre a [Inicialização Segura](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) na Biblioteca do TechNet.

![Configurar Inicialização Segura.](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figura 4. Configurar a Inicialização Segura*

Dependendo do dispositivo, você também pode ver se o TPM está habilitado ou desabilitado. Se você não vir a configuração **Habilitar TPM,** abra tpm.msc no Windows para verificar o status, conforme mostrado na Figura 5. O TPM é usado para autenticar a criptografia dos dados de seu dispositivo com o BitLocker. Para saber mais, confira [Visão geral do BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).

![Console TPM.](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figura 5. Console TPM*

## <a name="uefi-menu-devices"></a>Menu UEFI: Dispositivos

A página Dispositivos permite habilitar ou desabilitar dispositivos e componentes específicos, incluindo:

- Porta USB de encaixe

- Slot de cartão MicroSD ou SD

- Câmera Traseira

- Câmera Frontal

- Câmera de infravermelho (IV)

- Wi-Fi e Bluetooth

- Áudio integrado (alto-falantes e microfone)

Cada dispositivo é listado com um botão de controle deslizante que você pode mover para **a** posição Ativado (habilitado) ou Desativado (desabilitado), conforme mostrado na Figura 6. ****

:::image type="content" alt-text="Habilitar e desabilitar dispositivos específicos." source="images/manage-surface-uefi-fig5a.png":::

*Figura 6. Habilitar e desabilitar dispositivos específicos*

## <a name="uefi-menu-boot-configuration"></a>Menu UEFI: Configuração de inicialização

A página Configuração de Inicialização permite alterar a ordem dos dispositivos de inicialização, bem como habilitar ou desabilitar a inicialização dos seguintes dispositivos:

- Gerenciador de Inicialização do Windows

- Armazenamento USB

- Rede PXE

- Armazenamento interno

Você pode inicializar a partir de um dispositivo específico imediatamente ou pode passar o dedo para a esquerda na entrada desse dispositivo na lista usando a tela touch. Você também pode inicializar imediatamente em um dispositivo USB ou um adaptador de Ethernet USB quando o dispositivo Surface está desligado, pressionando o botão de **Diminuir o Volume** e o botão **Ligar/Desligar** simultaneamente.

Para que a ordem de inicialização especificada entre em vigor, você deve definir a opção Habilitar Sequência de **Inicialização** Alternativa como **Ativado**, conforme mostrado na Figura 7.

:::image type="content" alt-text="Configure a ordem de inicialização do dispositivo Surface." source="images/manage-surface-uefi-fig6.png":::

*Figura 7. Configurar a ordem de inicialização para o dispositivo Surface*

Você também pode ativar e desativar o suporte a IPv6 para PXE com a opção **Habilitar IPv6 para Inicialização de Rede PXE**, por exemplo, ao executar uma implantação do Windows usando o PXE, onde o servidor PXE é configurado somente para IPv4.  

## <a name="uefi-menu-management"></a>Menu UEFI: Gerenciamento

A página Gerenciamento permite gerenciar o uso do Gerenciamento UEFI zero touch e outros recursos em dispositivos qualificados, incluindo Surface Pro 7, Surface Pro X e Surface Laptop 3.  

:::image type="content" alt-text="Gerencie o acesso ao Gerenciamento UEFI do Zero Touch e outros recursos." source="images/manage-surface-uefi-fig7a.png":::

*Figura 8. Gerenciar o acesso ao Gerenciamento uefi zero toque e outros recursos*

O Gerenciamento uefi de toque zero permite gerenciar remotamente as configurações da UEFI usando um perfil de dispositivo no Intune chamado Interface de Configuração de Firmware de Dispositivo (DFCI). Se você não configurar essa configuração, a capacidade de gerenciar dispositivos qualificados com DFCI será definida como **Pronto**. Para impedir o DFCI, selecione **Opt-Out**.

> [!NOTE]
> A página de configurações de Gerenciamento da UEFI e o uso do DFCI estão disponíveis no momento para o Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7 e Surface Pro X. Para saber mais, confira [Gerenciamento do Intune das configurações uefi do Surface](surface-manage-dfci-guide.md).

## <a name="uefi-menu-exit"></a>Menu UEFI: Exit

Use o **botão Reiniciar Agora** na página **Sair** para sair das configurações uefi, conforme mostrado na Figura 9.

:::image type="content" alt-text="Saia da UEFI do Surface e reinicie o dispositivo." source="images/manage-surface-uefi-fig7.png":::

*Figura 9. Clique em Reiniciar Agora para sair do UEFI do Surface e reiniciar o dispositivo*

## <a name="surface-uefi-boot-screens"></a>Telas de inicialização UEFI Surface

Quando você atualiza o firmware do dispositivo Surface, usando o Windows Update ou instalação manual, as atualizações não são aplicadas imediatamente para o dispositivo, só durante o próximo ciclo de reinicialização. Você pode saber mais sobre o processo de atualização de firmware do Surface em [Gerenciar e implantar atualizações](manage-surface-driver-and-firmware-updates.md)de firmware e driver do Surface. O progresso da atualização do firmware é exibido em uma tela com barras de progresso de cores diferentes para indicar o firmware para cada componente. A barra de progresso de cada componente é mostrada nas Figuras 9 a 18.

![Atualização de firmware UEFI do Surface com barra de progresso azul.](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Figura 10. A atualização do firmware UEFI do Surface exibe uma barra de progresso azul*

![Firmware do Controlador Incorporado do Sistema com barra de progresso verde.](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Figura 11. A atualização de firmware de controlador incorporado no sistema exibe uma barra de progresso verde*

![Atualização de firmware do controlador SAM com barra de progresso laranja.](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Figura 12. A atualização do firmware de SAM Controller exibe uma barra de progresso laranja*

![Firmware do Mecanismo de Gerenciamento intel com barra de progresso vermelha.](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Figura 13. A atualização de firmware da Intel Management Engine exibe uma barra de progresso vermelho*

![Firmware do surface touch com barra de progresso cinza.](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Figura 14. A atualização de firmware do Surface toque exibe uma barra de progresso cinza*

![Firmware do Surface KIP com barra de progresso verde claro.](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figura 15. A atualização de firmware DO SURFACE KIM exibe uma barra de progresso verde claro*

![Firmware ISH do Surface com barra de progresso rosa.](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figura 16 A atualização de firmware do SURFACE ISH exibe uma barra de progresso rosa claro*

![Firmware do Surface Trackpad com barra de progresso cinza.](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figura 17. A atualização de firmware do Surface Trackpad exibe uma barra de progresso rosa*

![Firmware do Surface TCON com barra de progresso cinza claro.](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figura 18. A atualização de firmware do Surface TCON exibe uma barra de progresso cinza claro*

![Firmware do Surface TPM com barra de progresso roxo claro.](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figura 19. A atualização de firmware do Surface TPM exibe uma barra de progresso roxo*

>[!NOTE]
>Uma mensagem de aviso adicional que indica que a Inicialização Segura está desabilitada, conforme mostrado na Figura 19.

![A tela de inicialização do Surface que indica que a Inicialização Segura foi desabilitada.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figura 20. Tela de inicialização do Surface que indica que a inicialização segura foi desativada nas configurações de UEFI do Surface*

## <a name="references"></a>Referências

1. Surface Go e Surface Go 2 usam uma UEFI de terceiros e não suportam DFCI.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciamento pelo Intune das configurações de UEFI do Surface](surface-manage-dfci-guide.md)

- [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
