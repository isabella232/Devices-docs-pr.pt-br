---
title: Gerenciamento pelo Intune das configurações de UEFI do Surface
description: Este artigo explica como configurar um ambiente DFCI no Microsoft Intune e gerenciar configurações de firmware para dispositivos Surface direcionados.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: dde34126c726ec0ac8093a665804c4fb0f639e3e
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271565"
---
# Gerenciamento pelo Intune das configurações de UEFI do Surface

## Introdução

A capacidade de gerenciar dispositivos da nuvem simplificou drasticamente a implantação e o provisionamento de TI em todo o ciclo de vida. Com perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados ao [Microsoft Intune,](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)o gerenciamento UEFI do Surface estende a pilha de gerenciamento moderna até o nível de hardware UEFI. O DFCI dá suporte ao provisionamento com zero toque, elimina senhas do BIOS, fornece controle das configurações de segurança, incluindo opções de inicialização e periféricos integrados, e dispõe a base para cenários de segurança avançados no futuro. Para obter respostas para perguntas [frequentes, confira Ignite 2019:](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)Anunciando o gerenciamento remoto de configurações de UEFI do Surface do Intune.

### Tela de fundo

Como qualquer computador que executa o Windows 10, os dispositivos Surface dependem do código armazenado no SoC que permite que a CPU interface com discos rígidos, dispositivos de exibição, portas USB e outros dispositivos. Os programas armazenados nesta ROM (memória somente leitura) são conhecidos como firmware (enquanto os programas armazenados em mídia dinâmica são conhecidos como software).

Ao contrário de outros dispositivos Windows 10 disponíveis no mercado atualmente, o Surface oferece aos administradores de IT a capacidade de configurar e gerenciar o firmware por meio de um conjunto rico de configurações de UEFI. Isso fornece uma camada de controle de hardware sobre o gerenciamento de política baseada em software, conforme implementado por meio de políticas de gerenciamento de dispositivo móvel (MDM), Gerenciador de Configurações ou Política de Grupo. Por exemplo, as organizações que implantam dispositivos em áreas altamente seguras com informações confidenciais podem impedir o uso da câmera removendo a funcionalidade no nível de hardware. Do ponto de vista do dispositivo, desligar a câmera por meio de uma configuração de firmware equivale a remover fisicamente a câmera. Compare a segurança adicional do gerenciamento no nível do firmware para depender apenas das configurações de software do sistema operacional. Por exemplo, se você desabilitar o serviço de áudio do Windows por meio de uma configuração de política em um ambiente de domínio, um administrador local ainda poderá reabilitar o serviço.

### DFCI versus SEMM

Anteriormente, o gerenciamento do firmware exigia o registro de dispositivos no Surface Enterprise Management Mode (SEMM) com a sobrecarga de tarefas de IT manuais contínuas e intensivas. Por exemplo, o SEMM exige que a equipe de IT acesse fisicamente cada computador para inserir um pin de dois dígitos como parte do processo de gerenciamento de certificados. Embora o SEMM permaneça uma boa solução para organizações em um ambiente estritamente local, sua complexidade e requisitos intensivos de IT fazem com que seja caro de usar.

 Com os recursos integrados de gerenciamento de firmware UEFI no Microsoft Intune, a capacidade de bloquear o hardware é simplificada e mais fácil de usar com novos recursos para provisionamento, segurança e atualização simplificada de tudo em um único console, agora unificado como [Microsoft Endpoint Manager.](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) A figura a seguir mostra as configurações DE UEFI exibidas diretamente no dispositivo (à esquerda) e exibidas no console do Gerenciador de Pontos de Extremidade (à direita).

![Configurações UEFI mostradas no dispositivo (à esquerda) e no console do Endpoint Manager (à direita)](images/uefidfci.png)

Crucialmente, o DFCI habilita o gerenciamento zero de toque, eliminando a necessidade de interação manual por administradores de IT. O DFCI é implantado por meio do Windows Autopilot usando a funcionalidade de perfis de dispositivo no Intune. Um perfil de dispositivo permite adicionar e definir configurações que podem ser implantadas em dispositivos inscritos no gerenciamento em sua organização. Depois que o dispositivo recebe o perfil do dispositivo, os recursos e as configurações são aplicados automaticamente. Exemplos de perfis de dispositivo comuns incluem email, restrições de dispositivo, VPN, Wi-Fi e modelos administrativos. DFCI é simplesmente um perfil de dispositivo adicional que permite gerenciar definições de configuração UEFI da nuvem sem precisar manter a infraestrutura local.  

## Dispositivos com suporte

O DFCI é compatível com os seguintes dispositivos:

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go

> [!NOTE]
> O Surface Pro X não dá suporte ao gerenciamento de configurações DFCI para câmera, áudio e Wi-Fi/Bluetooth integrados.

## Pré-requisitos

- Os dispositivos devem ser registrados no Windows Autopilot por um parceiro [CSP (Provedor](https://partner.microsoft.com/membership/cloud-solution-provider) de Soluções na Nuvem) da Microsoft ou distribuidor OEM.

- Antes de configurar o DFCI para o Surface, você deve estar familiarizado com os requisitos de configuração do Autopilot no  [Microsoft Intune](https://docs.microsoft.com/intune/) e no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).

## Antes de começar

Adicione seus dispositivos Surface de destino a um grupo de segurança do Azure AD. Para obter mais informações sobre como criar e gerenciar grupos de segurança, consulte a [documentação do Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)

## Configurar o gerenciamento DFCI para dispositivos Surface

Um ambiente DFCI requer a configuração de um perfil DFCI que contém as configurações e um perfil do Autopilot para aplicar as configurações a dispositivos registrados. Um perfil de status de registro também é recomendado para garantir que as configurações sejam pressionadas durante a configuração OOBE quando os usuários iniciarem o dispositivo pela primeira vez. Este guia explica como configurar o ambiente DFCI e gerenciar as definições de configuração UEFI para dispositivos Surface direcionados.

## Criar perfil DFCI

Antes de definir as configurações de política DFCI, primeiro crie um perfil DFCI e atribua-o ao grupo de segurança do Azure AD que contém seus dispositivos de destino.

1. Entre em seu locatário em devicemanagement.microsoft.com.
2. No Centro de Administração do Microsoft Endpoint Manager, selecione Dispositivos > Perfis de **configuração > Criar perfil** e inserir um nome; por exemplo, Política **de Configuração DFCI.**
3. Selecione **o Windows 10 e posterior para o** tipo de plataforma.
4. Na lista drop down de tipo de perfil, selecione Interface de Configuração do **Firmware** do Dispositivo para abrir a folha DFCI que contém todas as configurações de política disponíveis. Para obter informações sobre configurações DFCI, consulte a Tabela 1 nesta página ou a [documentação do Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) Você pode definir configurações DFCI durante o processo de instalação inicial ou posterior editando o perfil DFCI.

    ![Criar perfil DFCI](images/df1.png)

5. Clique **em OK** e selecione **Criar**.
6. Selecione **Atribuições e,** em **Selecionar** grupos, para incluir, selecione o grupo de segurança do Azure AD que contém seus dispositivos de destino, conforme mostrado na figura a seguir. Clique em **Salvar**.

    ![Atribuir grupo de segurança](images/df2a.png)

## Criar perfil do Autopilot

1. No Endpoint Manager no devicemanagement.microsoft.com, selecione dispositivos > registro no **Windows** e role para baixo até perfis **de implantação.**
2. Selecione **Criar perfil** e insira um nome; por exemplo, **meu perfil do Piloto automático**e selecione **Next**.
3. Selecione as seguintes configurações:

    - Modo de implantação: **orientado pelo usuário.**
    - Tipo de ingresso: ingressado **no Azure AD.**

4. Deixe as configurações padrão restantes inalteradas e selecione **Next**, conforme mostrado na figura a seguir.

    ![Criar perfil do Autopilot](images/df3b.png)

5. Na página Atribuições, escolha **Selecionar grupos para incluir** e clique no grupo de segurança do Azure AD. Selecione **Avançar**.
6. Aceite o resumo e selecione **Criar**. O perfil do Autopilot agora é criado e atribuído ao grupo.

## Página Configurar Status do Registro

Para garantir que os dispositivos apliquem a configuração DFCI durante o OOBE antes que os usuários se inscrevam, você precisa configurar o status do registro.

Para obter mais informações, consulte [Configurar uma página de status de inscrição.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)


## Definir configurações DFCI em dispositivos Surface

O DFCI inclui um conjunto simplificado de políticas de configuração UEFI que fornecem um nível extra de segurança ao bloquear dispositivos no nível de hardware. O DFCI foi projetado para ser usado em conjunto com as configurações de gerenciamento de dispositivo móvel no nível do software. Observe que as configurações DFCI afetam apenas componentes de hardware integrados a dispositivos Surface e não se estendem a periféricos conectados, como webcams USB. (No entanto, você pode usar políticas de restrição de dispositivo no Intune para desativar o acesso a periféricos conectados no nível do software).

Você define configurações de política DFCI editando o perfil DFCI do Gerenciador de Pontos de Extremidade, conforme mostrado na figura abaixo. 

- No Endpoint Manager no devicemanagement.microsoft.com, selecione Dispositivos > Perfis de Configuração do Windows > > "Nome de perfil **DFCI" > Propriedades > Configurações.**

    ![Definir configurações DFCI](images/dfciconfig.png)

### Bloquear o acesso do usuário às configurações de UEFI

Para muitos clientes, a capacidade de impedir que os usuários mudem as configurações de UEFI é extremamente importante e um motivo principal para usar DFCI. Conforme listado na Tabela 1, isso é gerenciado por meio da configuração Permitir que o usuário local altere as configurações **de UEFI.** Se você não editar ou definir essa configuração, os usuários locais poderão alterar qualquer configuração UEFI não gerenciada pelo Intune. Portanto, é altamente recomendável desabilitar Permitir que **o usuário local altere as configurações de UEFI.**
O restante das configurações DFCI permite desativar a funcionalidade que, de outra forma, estaria disponível para os usuários. Por exemplo, se você precisar proteger informações confidenciais em áreas altamente seguras, poderá desabilitar a câmera e, se não quiser que os usuários inicializarem por unidades USB, você poderá desabilitá-la também.

### Tabela 1. Cenários DFCI

| Meta de gerenciamento de dispositivos                        | Etapas de configuração                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Impedir que os usuários locais mudem as configurações de UEFI | Em **Recursos de Segurança > permitir que o usuário local altere as configurações de UEFI,** selecione **Nenhum**.              |
| Desabilitar câmeras                               | Em **Câmeras > hardware**integrados, selecione **Desabilitado**.                                       |
| Desabilitar microfones e alto-falantes              | Under **Built in Hardware > Microphones and speakers**, select **Disabled**.                      |
| Desabilitar rádios (Bluetooth, Wi-Fi)             | Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc...)**, select **Disabled**.                   |
| Desabilitar a inicialização de mídia externa (USB, SD)    | Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**. |

> [!CAUTION]
> A **configuração Desabilitar rádios (Bluetooth, Wi-Fi)** só deve ser usada em dispositivos que tenham uma conexão Ethernet com fio.
 
> [!NOTE]
>  O DFCI no Intune inclui duas configurações que atualmente não se aplicam a dispositivos Surface: (1) CPU e virtualização de E/S e (2) Desabilitar a inicialização de adaptadores de rede.
 
O Intune fornece marcas de escopo para delegar direitos administrativos e regras de aplicabilidade para gerenciar tipos de dispositivos. Para obter mais informações sobre suporte ao gerenciamento de políticas e detalhes completos sobre todas as configurações DFCI, consulte a documentação [do Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

## Registrar dispositivos no Autopilot

Conforme mencionado acima, o DFCI só pode ser aplicado em dispositivos registrados no Windows Autopilot por seu revendedor ou distribuidor e só tem suporte no Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X e Surface Laptop 3. Por motivos de segurança, não é possível "provisionar automaticamente" seus dispositivos no Autopilot. Para saber mais, consulte Suporte ao registro do Surface [para o Windows Autopilot.](surface-autopilot-registration-support.md) 

## Sincronizar manualmente dispositivos do Autopilot

Embora as configurações de política do Intune normalmente sejam aplicadas quase imediatamente, pode haver um atraso de 10 minutos antes que as configurações tenham efeito em dispositivos direcionados. Em raras circunstâncias, são possíveis atrasos de até 8 horas. Para garantir que as configurações se apliquem assim que possível (como em cenários de teste), você pode sincronizar manualmente os dispositivos de destino.

- No Endpoint Manager no devicemanagement.microsoft.com, vá para Dispositivos > Registro de dispositivo > registro no Windows > Dispositivos **Windows Autopilot** e selecione **Sincronizar.**

 Para obter mais informações, consulte [Sincronizar seu dispositivo Windows manualmente.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)

> [!NOTE]
> Ao ajustar as configurações diretamente na UEFI, você precisa garantir que o dispositivo seja totalmente reiniciado para o logon padrão do Windows.

## Verificar configurações UEFI em dispositivos gerenciados pelo DFCI

Em um ambiente de teste, você pode verificar as configurações na interface UEFI do Surface.

1. Abra a UEFI do Surface, que envolve pressionar os botões **Volume +** e **Ligar** ao mesmo tempo.
2. Selecione **Dispositivos**. O menu UEFI refletirá as configurações configuradas, conforme mostrado na figura a seguir.

    ![Surface UEFI](images/df3.png)

    Observe como:

      - As configurações estão es cinzas porque Permitir que o usuário **local altere a** configuração UEFI está definida como Nenhum.
      - O áudio está definido como desativado porque **microfones e alto-falantes** estão definidos como **Desabilitados.**

## Removendo configurações de política DFCI

Quando você cria um perfil DFCI, todas as definições configuradas permanecerão em vigor em todos os dispositivos dentro do escopo de gerenciamento do perfil. Você só pode remover configurações de política DFCI editando o perfil DFCI diretamente.

Se o perfil DFCI original tiver sido excluído, você poderá remover as configurações de política criando um novo perfil e editando as configurações, conforme apropriado.

## Removendo o gerenciamento DFCI

**Para remover o gerenciamento DFCI e retornar o dispositivo ao novo estado de fábrica:**

1. Retire o dispositivo do Intune:
    1. No Endpoint Manager no devicemanagement.microsoft.com, escolha **Grupos > Todos os Dispositivos.** Selecione os dispositivos que você deseja retirar e escolha **Retirar/Apagar.** Para saber mais, consulte Remover dispositivos usando apagar, retirar ou [desemrollar manualmente o dispositivo.](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 
2. Exclua o registro do Autopilot do Intune:
    1.  Choose **Device enrollment > Windows enrollment > Devices**.
    2. Em dispositivos windows Autopilot, escolha os dispositivos que você deseja excluir e, em seguida, escolha **Excluir**.
3. Conecte o dispositivo à Internet com fio com adaptador ethernet da marca Surface. Reinicie o dispositivo e abra o menu UEFI (pressione e segure o botão aumentar o volume enquanto também pressiona e libera o botão de energia).
4. Selecione **Management > Configure > Refresh from Network** e escolha **Opt-out.**

Para continuar gerenciando o dispositivo com o Intune, mas sem gerenciamento DFCI, registre-o automaticamente no Autopilot e registre-o no Intune. DFCI não será aplicada a dispositivos auto-registrados.

## Saiba mais
- [Ignite 2019: Anunciando o gerenciamento remoto de configurações UEFI do Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md) 
- [Usar perfis DFCI em dispositivos Windows no Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
