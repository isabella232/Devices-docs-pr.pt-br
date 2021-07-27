---
title: Gerenciar DFCI em dispositivos Surface
description: Este artigo explica como configurar um ambiente DFCI no Microsoft Intune e gerenciar configurações de firmware para dispositivos Surface direcionados.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/13/2021
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
- Surface Laptop 4
ms.openlocfilehash: 871bead0ae5f73c546b8dbe219d71b819d3a865e
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676445"
---
# <a name="manage-dfci-on-surface-devices"></a>Gerenciar DFCI em dispositivos Surface

## <a name="introduction"></a>Introdução

A capacidade de gerenciar dispositivos da nuvem simplificou drasticamente a implantação e o provisionamento de TI em todo o ciclo de vida. Com perfis DFCI (Interface de Configuração de Firmware de Dispositivo) integrados [Microsoft Intune,](/intune/configuration/device-firmware-configuration-interface-windows)o gerenciamento uefi do Surface estende a pilha de gerenciamento moderna para o nível de hardware UEFI. O DFCI dá suporte ao provisionamento de toque zero, elimina senhas de BIOS, fornece controle de configurações de segurança, incluindo opções de inicialização e periféricos integrados, e estabelece as bases para cenários avançados de segurança no futuro. Para obter respostas para perguntas [frequentes, consulte Ignite 2019: Anunciando](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)o gerenciamento remoto das configurações do Surface UEFI do Intune .

### <a name="background"></a>Tela de fundo

Como qualquer computador que Windows 10, os dispositivos Surface dependem do código armazenado no SoC que permite que a CPU interface com discos rígidos, dispositivos de exibição, portas USB e outros dispositivos. Os programas armazenados nesta ROM (memória somente leitura) são conhecidos como firmware (enquanto os programas armazenados em mídia dinâmica são conhecidos como software).

Em contraste com outros Windows 10 disponíveis no mercado atualmente, o Surface fornece aos administradores de IT a capacidade de configurar e gerenciar o firmware por meio de um conjunto rico de configurações UEFI. Isso fornece uma camada de controle de hardware sobre o gerenciamento de política baseada em software, conforme implementado por meio de políticas de gerenciamento de dispositivo móvel (MDM), Gerenciador de Configuração ou Política de Grupo. Por exemplo, as organizações que implantam dispositivos em áreas altamente seguras com informações confidenciais podem impedir o uso da câmera removendo a funcionalidade no nível de hardware. Do ponto de vista do dispositivo, desligar a câmera por meio de uma configuração de firmware equivale a remover fisicamente a câmera. Compare a segurança adicional do gerenciamento no nível do firmware para depender apenas das configurações de software do sistema operacional. Por exemplo, se você desabilitar o serviço de Windows de áudio por meio de uma configuração de política em um ambiente de domínio, um administrador local ainda poderá habilitar o serviço.

### <a name="dfci-versus-semm"></a>DFCI versus SEMM

Anteriormente, o gerenciamento do firmware exigia o registro de dispositivos no Surface Enterprise Modo de Gerenciamento (SEMM) com a sobrecarga de tarefas manuais de uso intensivo de IT. Como exemplo, o SEMM exige que a equipe de IT acesse fisicamente cada computador para inserir um pino de dois dígitos como parte do processo de gerenciamento de certificados. Embora o SEMM continue sendo uma boa solução para as organizações em um ambiente estritamente local, sua complexidade e requisitos intensivos de IT o fazem ser caro de usar.

 Com recursos integrados de gerenciamento de firmware UEFI no Microsoft Intune, a capacidade de bloquear o hardware é simplificada e fácil de usar com novos recursos para provisionamento, segurança e atualização simplificada de tudo em um único console, agora unificado [como](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)Microsoft Endpoint Manager . A figura a seguir mostra as configurações UEFI exibidas diretamente no dispositivo (à esquerda) e exibidas no console Endpoint Manager (à direita).

![Configurações UEFI mostradas no dispositivo (à esquerda) e no console Endpoint Manager (à direita)](images/uefidfci.png)

Crucialmente, o DFCI habilita o gerenciamento de toque zero, eliminando a necessidade de interação manual por administradores de IT. O DFCI é implantado Windows Autopilot usando o recurso de perfis de dispositivo no Intune. Um perfil de dispositivo permite adicionar e configurar configurações que podem ser implantadas em dispositivos inscritos no gerenciamento em sua organização. Quando o dispositivo recebe o perfil do dispositivo, os recursos e as configurações são aplicados automaticamente. Exemplos de perfis de dispositivo comuns incluem modelos de Email, Restrições de dispositivo, VPN, Wi-Fi e Administrativo. DFCI é simplesmente um perfil de dispositivo adicional que permite que você gerencie as configurações uefi da nuvem sem precisar manter a infraestrutura local.  

## <a name="supported-devices"></a>Dispositivos com suporte

O DFCI tem suporte nos seguintes dispositivos:

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
- Surface Laptop 4

> [!NOTE]
> Surface Pro X não dá suporte ao gerenciamento de configurações DFCI para câmera, áudio e Wi-Fi/Bluetooth.

## <a name="prerequisites"></a>Pré-requisitos

- Os dispositivos devem ser registrados com Windows Autopilot por [um parceiro Provedor de Soluções na Nuvem da Microsoft (CSP)](https://partner.microsoft.com/membership/cloud-solution-provider) ou distribuidor OEM.

- Antes de configurar o DFCI para Surface, você deve estar familiarizado com os requisitos de configuração do Autopilot [no Microsoft Intune](/intune/) e [Azure Active Directory](/azure/active-directory/) (Azure AD).

## <a name="before-you-begin"></a>Antes de você começar

Adicione seus dispositivos Surface de destino a um grupo de segurança do Azure AD. Para obter mais informações sobre como criar e gerenciar grupos de segurança, consulte a [documentação do Intune.](/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)

## <a name="configure-dfci-management-for-surface-devices"></a>Configurar o gerenciamento DFCI para dispositivos Surface

Um ambiente DFCI requer a configuração de um perfil DFCI que contém as configurações e um perfil de Piloto Automático para aplicar as configurações a dispositivos registrados. Um perfil de status de registro também é recomendado para garantir que as configurações sejam pressionadas durante a instalação do OOBE quando os usuários iniciarem o dispositivo pela primeira vez. Este guia explica como configurar o ambiente DFCI e gerenciar as configurações uefi para dispositivos Surface direcionados.

## <a name="create-dfci-profile"></a>Criar perfil DFCI

Antes de configurar as configurações de política DFCI, primeiro crie um perfil DFCI e atribua-o ao grupo de segurança do Azure AD que contém seus dispositivos de destino.

1. Entre em seu locatário devicemanagement.microsoft.com.
2. No Centro de administração Microsoft Endpoint Manager, selecione Dispositivos > perfis de **configuração > Criar perfil** e inserir um nome; por exemplo, **Política de Configuração DFCI.**
3. Selecione **Windows 10 e posterior para o tipo** de plataforma.
4. Na lista listada de tipos de perfil, selecione Interface de Configuração do Firmware de **Dispositivo** para abrir a folha DFCI que contém todas as configurações de política disponíveis. Para obter informações sobre as configurações do DFCI, consulte a Tabela 1 nesta página ou a [documentação do Intune.](/intune/configuration/device-firmware-configuration-interface-windows) Você pode configurar configurações DFCI durante o processo de instalação inicial ou posterior editando o perfil DFCI.

    ![Criar perfil DFCI](images/df1.png)

5. Clique **em OK** e selecione **Criar**.
6. Selecione Atribuições e em **Selecionar grupos** para incluir selecione o grupo de segurança do Azure AD que contém seus **dispositivos** de destino, conforme mostrado na figura a seguir. Clique em **Salvar**.

    ![Atribuir grupo de segurança](images/df2a.png)

## <a name="create-autopilot-profile"></a>Criar perfil do Autopilot

1. Em Endpoint Manager no devicemanagement.microsoft.com, selecione **dispositivos > Windows registro** e role para baixo até **perfis de implantação.**
2. Selecione **Criar perfil** e insira um nome; por exemplo, **meu perfil de piloto automático**e selecione **Next**.
3. Selecione as seguintes configurações:

    - Modo de implantação: **Orientado pelo usuário**.
    - Tipo de ingresso: ingresso no **Azure AD**.

4. Deixe as configurações padrão restantes inalteradas e selecione **Next**, conforme mostrado na figura a seguir.

    ![Criar perfil do Autopilot](images/df3b.png)

5. Na página Atribuições, escolha **Selecionar grupos para incluir** e clique em seu grupo de segurança do Azure AD. Selecione **Avançar**.
6. Aceite o resumo e selecione **Criar**. O perfil do Piloto Automático agora é criado e atribuído ao grupo.

## <a name="configure-enrollment-status-page"></a>Configurar a Página de Status do Registro

Para garantir que os dispositivos apliquem a configuração DFCI durante o OOBE antes de os usuários entrarem, você precisa configurar o status de registro.

Para obter mais informações, consulte [Configurar uma página de status de registro](/intune/enrollment/windows-enrollment-status).


## <a name="configure-dfci-settings-on-surface-devices"></a>Configurar configurações DFCI em dispositivos Surface

O DFCI inclui um conjunto simplificado de políticas de configuração UEFI que fornecem um nível extra de segurança ao bloquear dispositivos no nível de hardware. O DFCI foi projetado para ser usado em conjunto com as configurações de gerenciamento de dispositivo móvel no nível do software. Observe que as configurações DFCI afetam apenas componentes de hardware integrados a dispositivos Surface e não se estendem a periféricos anexados, como webcams USB. (No entanto, você pode usar políticas de restrição de dispositivo no Intune para desativar o acesso a periféricos anexados no nível do software).

Você configura as configurações de política DFCI editando o perfil DFCI de Endpoint Manager, conforme mostrado na figura abaixo. 

- Em Endpoint Manager no devicemanagement.microsoft.com, selecione Dispositivos > Windows > Perfis de Configuração > "nome de perfil **DFCI" > Propriedades > Configurações**.

    ![Configurar configurações DFCI](images/dfciconfig.png)

### <a name="block-user-access-to-uefi-settings"></a>Bloquear o acesso do usuário às configurações uefi

Para muitos clientes, a capacidade de impedir que os usuários mudem as configurações da UEFI é fundamentalmente importante e um motivo principal para usar o DFCI. Conforme listado na Tabela 1, isso é gerenciado por meio da configuração Permitir que o **usuário local altere as configurações uefi**. Se você não editar ou configurar essa configuração, os usuários locais poderão alterar qualquer configuração uefi não gerenciada pelo Intune. Portanto, é altamente recomendável desabilitar Permitir que o usuário local altere as configurações **da UEFI.**
O restante das configurações dfci permite desativar a funcionalidade que, de outra forma, estaria disponível para os usuários. Por exemplo, se você precisar proteger informações confidenciais em áreas altamente seguras, poderá desabilitar a câmera e, se não quiser que os usuários inicializam de unidades USB, você também poderá desabilitá-la.

### <a name="table-1-dfci-scenarios"></a>Tabela 1. Cenários DFCI

| Meta de gerenciamento de dispositivos                        | Etapas de configuração                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Impedir que os usuários locais mudem as configurações da UEFI | Em Recursos de Segurança > Permitir que o usuário local altere as configurações **da UEFI,** selecione **Nenhum**.              |
| Desabilitar câmeras                               | Em **Built in Hardware > Câmeras**, selecione **Desabilitado**.                                       |
| Desabilitar microfones e alto-falantes              | Em **Built in Hardware > Microfones e alto-falantes**, selecione **Desabilitado**.                      |
| Desabilitar rádios (Bluetooth, Wi-Fi)             | Em **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc...),** selecione **Desabilitado**.                   |
| Desabilitar a inicialização de mídia externa (USB, SD)    | Em Opções internas de inicialização > hardware > inicialização de mídia externa **(USB, SD),** selecione **Desabilitado**. |

> [!CAUTION]
> A **configuração Desabilitar rádios (Bluetooth, Wi-Fi)** só deve ser usada em dispositivos que tenham uma conexão Ethernet com fio.
 
> [!NOTE]
>  O DFCI no Intune inclui duas configurações que não se aplicam atualmente a dispositivos Surface: (1) virtualização de CPU e IO e (2) Desabilitar a inicialização de adaptadores de rede.
 
O Intune fornece marcas de escopo para delegar direitos administrativos e Regras de Aplicabilidade para gerenciar tipos de dispositivo. Para obter mais informações sobre o suporte ao gerenciamento de políticas e detalhes completos sobre todas as configurações do DFCI, consulte [Microsoft Intune documentação](/intune/configuration/device-firmware-configuration-interface-windows).

## <a name="register-devices-in-autopilot"></a>Registrar dispositivos no Autopilot

Conforme mencionado acima, o DFCI só pode ser aplicado em dispositivos registrados no Windows Autopilot pelo revendedor ou distribuidor e só tem suporte no Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X e Surface Laptop 3. Por motivos de segurança, não é possível "autopro provisionar" seus dispositivos no Autopilot. Para saber mais, consulte Surface [Registration Support for Windows Autopilot](surface-autopilot-registration-support.md). 

## <a name="manually-sync-autopilot-devices"></a>Sincronizar manualmente dispositivos do Autopilot

Embora as configurações de política do Intune geralmente sejam aplicadas quase imediatamente, pode haver um atraso de 10 minutos antes que as configurações tenham efeito em dispositivos direcionados. Em raras circunstâncias, atrasos de até 8 horas são possíveis. Para garantir que as configurações se apliquem assim que possível, (como em cenários de teste), você pode sincronizar manualmente os dispositivos de destino.

- Em Endpoint Manager no devicemanagement.microsoft.com, vá para **Dispositivos > Registro** de dispositivos > Windows registro > Windows Dispositivos autopilot e selecione **Sincronizar**.

 Para obter mais informações, consulte [Sync your Windows device manualmente](/intune-user-help/sync-your-device-manually-windows).

> [!NOTE]
> Ao ajustar as configurações diretamente na UEFI, você precisa garantir que o dispositivo seja reiniciado totalmente para o logon Windows padrão.

## <a name="verifying-uefi-settings-on-dfci-managed-devices"></a>Verificando configurações uefi em dispositivos gerenciados pelo DFCI

Em um ambiente de teste, você pode verificar configurações na interface UEFI do Surface.

1. Abra a UEFI do Surface, que envolve pressionar os botões **Volume +** e **Power** ao mesmo tempo.
2. Selecione **Dispositivos**. O menu UEFI refletirá as configurações configuradas, conforme mostrado na figura a seguir.

    ![Surface UEFI](images/df3.png)

    Observe como:

      - As configurações estão acinzenadas porque Permitir que o **usuário local altere a configuração uefi** está definida como Nenhum.
      - O áudio é definido como desativado porque **microfones e alto-falantes** são definidos como **Desabilitados**.

## <a name="removing-dfci-policy-settings"></a>Removendo configurações de política DFCI

Ao criar um perfil DFCI, todas as configurações permanecerão em vigor em todos os dispositivos no escopo de gerenciamento do perfil. Você só pode remover configurações de política DFCI editando o perfil DFCI diretamente.

Se o perfil DFCI original tiver sido excluído, você poderá remover as configurações de política criando um novo perfil e editando as configurações, conforme apropriado.

## <a name="removing-dfci-management"></a>Removendo o gerenciamento dfci

**Para remover o gerenciamento DFCI e retornar o dispositivo para o novo estado de fábrica:**

1. Retire o dispositivo do Intune:
    1. Em Endpoint Manager no devicemanagement.microsoft.com, escolha **Grupos > Todos os Dispositivos**. Selecione os dispositivos que você deseja retirar e escolha **Se aposentar/apagar.** Para saber mais, consulte [Remove devices by using wipe, retire, or manualmente unenrolling the device](/intune/remote-actions/devices-wipe). 
2. Exclua o registro do Piloto Automático do Intune:
    1.  Escolha **Registro de dispositivo > Windows registro > Dispositivos**.
    2. Em Windows de piloto automático, escolha os dispositivos que você deseja excluir e escolha **Excluir**.
3. Conexão para internet com fio com adaptador ethernet da marca Surface. Reinicie o dispositivo e abra o menu UEFI (pressione e segure o botão de volume para cima enquanto também pressiona e libera o botão de energia).
4. Selecione **Gerenciamento > Configurar > Atualizar na Rede** e escolha Optar por **Não-Sair.**

Para continuar gerenciando o dispositivo com o Intune, mas sem gerenciamento DFCI, registre-o automaticamente no Autopilot e registre-o no Intune. DFCI não será aplicado a dispositivos auto-registrados.

## <a name="learn-more"></a>Saiba mais
- [Ignite 2019: Anunciando o gerenciamento remoto das configurações uefi do Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Piloto Automático](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md) 
- [Use perfis DFCI em Windows dispositivos em Microsoft Intune](/intune/configuration/device-firmware-configuration-interface-windows)
