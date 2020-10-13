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
ms.date: 10/12/2020
ms.openlocfilehash: 218f98b23adcb7bae2af92655d85144c6e5665e6
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114719"
---
# Gerenciar configurações de UEFI do Surface

Todas as gerações atuais e futuras de dispositivos Surface usam uma Unified Extensible Firmware Interface (UEFI) exclusiva pela Microsoft, especificamente para esses dispositivos. As configurações de Surface UEFI fornecem a capacidade de habilitar ou desabilitar dispositivos e componentes internos, impedir que as configurações de UEFI sejam alteradas e ajustar as configurações de inicialização do dispositivo de superfície. 

## Produtos compatíveis

O gerenciamento de UEFI tem suporte nos seguintes itens: 

- Surface Pro 4, Surface pro (5ª gen), Surface pro 6, Surface Pro 7, Surface Pro X
- Laptop Surface (1ª gen), Surface laptop 2, Surface laptop 3, Surface laptop go
- Surface Studio (1ª gen), Surface Studio 2
- Livro de superfície, livro Surface 2, livro Surface 3
- Surface Go, Surface go 2

## Suporte para gerenciamento baseado em nuvem

Com os perfis da interface de configuração do firmware do dispositivo (DFCI) incorporados ao Microsoft Intune (agora disponível no modo de visualização pública), o gerenciamento de UEFI da superfície estende a pilha de gerenciamento moderno para o nível de hardware UEFI. O DFCI é compatível com o provisionamento de Zero Touch, elimina as senhas do BIOS, fornece o controle das configurações de segurança, incluindo opções de inicialização e periféricos incorporados, e prepara a base para cenários de segurança avançada no futuro. O DFCI está disponível atualmente para o Surface Pro 7, Surface Pro X e Surface laptop 3. Para obter mais informações, consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md).

## Menu UEFI de abertura de superfície

Para ajustar as configurações de UEFI durante a inicialização do sistema:

1. Desligue sua superfície e aguarde cerca de 10 segundos para ter certeza de que está desligado.
2. Pressione e mantenha pressionado o botão **volume-up** e-ao mesmo tempo-pressione e libere o **botão de energia.**
3. Quando o logotipo da Microsoft ou do Surface aparecer na tela, continue a manter o botão **volume-up** até que a tela UEFI seja exibida.

## Página de informações do PC UEFI

A página informações do PC inclui informações detalhadas sobre o seu dispositivo Surface: 

- **Modelo** – o modelo do seu dispositivo de superfície será exibido aqui, como o Surface Book 2 ou Surface Pro 7. A configuração exata de seu dispositivo não é exibida, (como processador, tamanho do disco ou tamanho da memória). 
- **UUID** – esse número de identificação universalmente exclusivo é específico de seu dispositivo e usado para identificar o dispositivo durante a implantação ou gerenciamento. 

- **Número de Série** – esse número é usado para identificar esse dispositivo Surface específico para cenários de marcação de ativos e suporte.
- **Marca do Ativo** – a marca do ativo é atribuída ao dispositivo Surface com a [Ferramenta de Marca do Ativo](https://docs.microsoft.com/surface/assettag). 

Você também encontrará informações detalhadas sobre o firmware de seu dispositivo Surface. Os dispositivos Surface têm vários componentes internos que executam diferentes versões do firmware. A versão do firmware de cada um dos seguintes dispositivos é exibida na página **Informações do computador** (como mostrado na Figura 1): 

- Sistema UEFI 

- Controlador SAM 

- Intel Management Engine 

- Controlador Incorporado do Sistema 

- Firmware de Toque 

![Informações do sistema e informações de versão do firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*Figura 1. Informações do sistema e informações de versão do firmware*

Você pode encontrar informações atualizadas sobre a versão mais recente do firmware para o dispositivo Surface no [Histórico de Atualizações do Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para seu dispositivo. 

## Página de segurança UEFI 

![Definir configurações de segurança de UEFI do Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Figura 2. Definir configurações de segurança de UEFI do Surface*

A página segurança permite definir uma senha para proteger as configurações de UEFI. Essa senha deve ser inserida quando você inicializa o dispositivo Surface para UEFI. A senha pode conter os seguintes caracteres (conforme mostrado na Figura 3): 

- Letras maiúsculas: A-Z 

- Letras minúsculas: a-z 

- Números: 1-0 

- Caracteres especiais:! @ # $% ^& * ()? <>{} []-_ = + |.,;: ' ' " 

A senha deve ter pelo menos 6 caracteres e diferencia maiúsculas de minúsculas. 

![Adicionar uma senha para proteger as configurações de UEFI do Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figura 3. Adicionar uma senha para proteger as configurações de UEFI do Surface*

Na página Segurança também é possível alterar a configuração de Inicialização Segura no dispositivo Surface. A tecnologia de Inicialização Segura impede que o código de inicialização não autorizado inicialize no dispositivo Surface, o que protege contra infecções por malware do tipo bootkit e rootkit. Você pode desabilitar a Inicialização Segura para permitir que o dispositivo Surface inicialize sistemas operacionais de terceiros ou mídia inicializável. Você também pode configurar o Secure boot para funcionar com certificados de terceiros, como mostrado na Figura 4. Leia mais sobre a [Inicialização Segura](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) na Biblioteca do TechNet.

![Configurar a Inicialização Segura](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figura 4. Configurar a Inicialização Segura*

Dependendo do seu dispositivo, também é possível ver se o seu TPM está habilitado ou desabilitado. Se você não vir a configuração **habilitar TPM**  , abra TPM. msc no Windows para verificar o status, conforme mostrado na Figura 5. O TPM é usado para autenticar a criptografia dos dados de seu dispositivo com o BitLocker. Para saber mais, consulte [visão geral do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview). 

![Console TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figura 5. Console TPM*


## Menu UEFI: dispositivos 

A página dispositivos permite habilitar ou desabilitar dispositivos e componentes específicos, incluindo:

- Encaixe e portas USB 

- Slot de cartão MicroSD ou SD 

- Câmera Traseira 

- Câmera Frontal 

- Câmera de infravermelho (IV) 

- Wi-Fi e Bluetooth 

- Áudio integrado (alto-falantes e microfone) 

Cada dispositivo é listado com um botão deslizante que você pode mover para a posição **ativado** (ativado) ou **desativado** (desabilitado), conforme mostrado na Figura 6. 

![Habilitar e desabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Figura 6. Habilitar e desabilitar dispositivos específicos*

## Menu UEFI: configuração de inicialização 

A página de configuração de inicialização permite alterar a ordem dos dispositivos de inicialização, bem como habilitar ou desabilitar a inicialização dos seguintes dispositivos: 

- Gerenciador de Inicialização do Windows 

- Armazenamento USB 

- Rede PXE 

- Armazenamento interno 

Você pode inicializar a partir de um dispositivo específico imediatamente ou pode passar o dedo para a esquerda na entrada desse dispositivo na lista usando a tela touch. Você também pode inicializar imediatamente em um dispositivo USB ou um adaptador de Ethernet USB quando o dispositivo Surface está desligado, pressionando o botão de **Diminuir o Volume** e o botão **Ligar/Desligar** simultaneamente. 

Para que a ordem de inicialização especificada entre em vigor, você deve definir a opção **habilitar sequência de inicialização alternativa** como **ativa**, conforme mostrado na Figura 7. 

![Configurar a ordem de inicialização para o dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Figura 7. Configurar a ordem de inicialização para o dispositivo Surface* 

Você também pode ativar e desativar o suporte a IPv6 para PXE com a opção **Habilitar IPv6 para Inicialização de Rede PXE**, por exemplo, ao executar uma implantação do Windows usando o PXE, onde o servidor PXE é configurado somente para IPv4.  

## Menu UEFI: gerenciamento
A página Gerenciamento permite que você gerencie o uso do gerenciamento de UEFI de toque zero e outros recursos em dispositivos qualificados, incluindo Surface Pro 7, Surface Pro X e Surface laptop 3.  

![Gerencie o acesso a Zero Touch Management e outros recursos ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Figura 8. Gerenciar o acesso a Zero Touch Management e outros recursos* 


O gerenciamento de UEFI de Zero Touch permite que você gerencie remotamente as configurações de UEFI usando um perfil de dispositivo dentro do Intune chamado interface de configuração do firmware do dispositivo (DFCI). Se você não definir essa configuração, a capacidade de gerenciar dispositivos qualificados com o DFCI será definida como **pronto**. Para impedir o DFCI, escolha **recusar**. 

> [!NOTE]
> A página de configurações de gerenciamento de UEFI e o uso de DFCI só estão disponíveis no Surface Pro 7, Surface Pro X e Surface laptop 3.  

Para obter mais informações, consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md).

## Menu UEFI: sair 

Use o botão **reiniciar agora** na página **sair** para sair das configurações de UEFI, conforme mostrado na Figura 9. 

![Sair do UEFI do Surface e reiniciar o dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*Figura 9. Clique em Reiniciar Agora para sair do UEFI do Surface e reiniciar o dispositivo*

## Telas de inicialização UEFI Surface

Quando você atualiza o firmware do dispositivo Surface, usando o Windows Update ou instalação manual, as atualizações não são aplicadas imediatamente para o dispositivo, só durante o próximo ciclo de reinicialização. Você pode saber mais sobre o processo de atualização do firmware do Surface no [Gerenciar atualizações de driver e firmware do Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates). O progresso da atualização do firmware é exibido em uma tela com barras de progresso de cores diferentes para indicar o firmware para cada componente. A barra de progresso de cada componente é mostrada nos números de 9 a 18.

![Atualização de firmware UEFI Surface com barra de progresso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Figura 10. A atualização do firmware UEFI do Surface exibe uma barra de progresso azul*

![Firmware de controlador incorporado do sistema com a barra de progresso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Figura 11. A atualização de firmware de controlador incorporado no sistema exibe uma barra de progresso verde*

![Atualização do firmware de SAM Controller com barra de progresso laranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Figura 12. A atualização do firmware de SAM Controller exibe uma barra de progresso laranja*

![Firmware do Intel Management Engine com barra de progresso vermelho](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Figura 13. A atualização de firmware da Intel Management Engine exibe uma barra de progresso vermelho*

![Toque Surface firmware com barra de progresso cinza](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Figura 14. A atualização de firmware do Surface toque exibe uma barra de progresso cinza*

![Firmware do Surface KIP com barra de progresso verde claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figura 15. A atualização do firmware do Surface KIP exibe uma barra de progresso verde claro*

![Firmware do Surface ISH com barra de progresso rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figura 16 a atualização do firmware do Surface ISH exibe uma barra de progresso rosa clara*

![Firmware do Surface trackpad com barra de progresso cinza](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figura 17. A atualização do firmware do Surface trackpad exibe uma barra de progresso rosa*

![Firmware do Surface TCON com barra de progresso cinza claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figura 18. A atualização do firmware do Surface TCON exibe uma barra de progresso cinza claro*


![Firmware de Surface TPM com barra de progresso roxo claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figura 19. A atualização do firmware de Surface TPM exibe uma barra de progresso roxa*


>[!NOTE]
>Uma mensagem de aviso adicional que indica que a inicialização segura está desabilitada é exibida, conforme mostrado na Figura 19.

![Tela de inicialização do Surface que indica que a inicialização segura foi desabilitada](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figura 20. Tela de inicialização do Surface que indica que a inicialização segura foi desativada nas configurações de UEFI do Surface*

## Tópicos relacionados

- [Gerenciamento pelo Intune das configurações de UEFI do Surface](surface-manage-dfci-guide.md)

-  [Modo de gerenciamento empresarial do Surface](surface-enterprise-management-mode.md)
