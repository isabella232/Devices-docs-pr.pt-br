---
title: Gerenciamento pelo Intune das configurações de UEFI do Surface
description: Este artigo explica como configurar um ambiente DFCI no Microsoft Intune e gerenciar as configurações de firmware para dispositivos de superfície direcionado.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 11/13/2019
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 0aa69bb229f0d76972620bc58f236e43e03075b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830498"
---
# Gerenciamento pelo Intune das configurações de UEFI do Surface

## Introdução

A capacidade de gerenciar dispositivos da nuvem simplificou drasticamente a implantação e o provisionamento de ti em todo o ciclo de vida. Com os perfis da interface de configuração do firmware do dispositivo (DFCI) incorporados ao Microsoft Intune (agora disponível no modo de [Visualização pública](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), o gerenciamento de UEFI da superfície estende a pilha de gerenciamento moderno para o nível de hardware UEFI. O DFCI é compatível com o provisionamento de Zero Touch, elimina as senhas do BIOS, fornece o controle das configurações de segurança, incluindo opções de inicialização e periféricos incorporados, e prepara a base para cenários de segurança avançada no futuro. Para obter respostas para perguntas frequentes, consulte [Ignite 2019: anunciando o gerenciamento remoto de configurações da Surface UEFI do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

### Tela de fundo

Assim como qualquer computador executando o Windows 10, os dispositivos Surface dependem do código armazenado no SoC que permite que a CPU entre em uma interface com discos rígidos, dispositivos de vídeo, portas USB e outros dispositivos. Os programas armazenados nessa memória somente leitura (ROM) são conhecidos como firmware (enquanto os programas armazenados em mídia dinâmica são conhecidos como software).

Em contraste com outros dispositivos Windows 10 disponíveis no mercado hoje em dia, a Surface oferece aos administradores de ti a capacidade de configurar e gerenciar o firmware por meio de um conjunto avançado de configurações de UEFI de configuração. Isso fornece uma camada de controle de hardware sobre o gerenciamento de políticas baseado em software, conforme implementado por políticas de gerenciamento de dispositivos móveis (MDM), Gerenciador de configurações ou política de grupo. Por exemplo, as organizações que implantam dispositivos em áreas altamente seguras com informações confidenciais podem impedir o uso da câmera, removendo a funcionalidade no nível do hardware. Do ponto de vista de um dispositivo, desativar a câmera por meio de uma configuração de firmware é equivalente a remover fisicamente a câmera. Compare a segurança adicional de gerenciamento no nível do firmware para se basear apenas nas configurações de software do sistema operacional. Por exemplo, se você desativar o serviço de áudio do Windows por meio de uma configuração de política em um ambiente de domínio, um administrador local ainda poderá habilitar o serviço novamente.

### DFCI versus SEMM

Até agora, gerenciar o firmware exigiu o cadastramento de dispositivos no modo de gerenciamento do Surface Enterprise (SEMM) com a sobrecarga de tarefas manuais de ti em andamento. Como exemplo, o SEMM requer que a equipe de ti acesse fisicamente cada computador para inserir um PIN de dois dígitos como parte do processo de gerenciamento de certificados. Embora SEMM permaneça uma boa solução para organizações em um ambiente estritamente local, a complexidade e os requisitos de ti exigem que seja caro de usar.

Agora com os novos recursos de gerenciamento de firmware UEFI integrados no Microsoft Intune, a capacidade de bloquear o hardware é simplificada e mais fácil de usar com novos recursos para provisionamento, segurança e atualização simplificada, tudo em um único console, agora unificado como [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager). A figura a seguir mostra as configurações de UEFI exibidas diretamente no dispositivo (à esquerda) e exibidas no console do Endpoint Manager (direita).

![Configurações de UEFI exibidas no dispositivo (à esquerda) e no console do Endpoint Manager (direita)](images/uefidfci.png)

De forma crucial, o DFCI permite o gerenciamento de toque zero, eliminando a necessidade de interação manual por administradores de ti. O DFCI é implantado via Windows AutoPilot usando a funcionalidade de perfis de dispositivo no Intune. Um perfil de dispositivo permite que você adicione e defina configurações que podem ser implantadas em dispositivos registrados em sua organização. Depois que o dispositivo recebe o perfil do dispositivo, os recursos e as configurações são aplicados automaticamente. Exemplos de perfis de dispositivo comuns incluem email, restrições de dispositivo, VPN, Wi-Fi e modelos administrativos. DFCI é simplesmente um perfil de dispositivo adicional que permite que você gerencie as configurações de configuração de UEFI da nuvem sem precisar manter a infraestrutura local.  

## Dispositivos com suporte

No momento, há suporte para o DFCI nos seguintes dispositivos:

- Surface Pro 7
- Surface Pro X
- Laptop Surface 3

> [!NOTE]
> Surface Pro X não é compatível com o gerenciamento de configurações de DFCI para câmera interna, áudio e Wi-Fi/Bluetooth.

## Pré-requisitos

- Os dispositivos devem ser registrados no AutoPilot do Windows por um parceiro ou distribuidor de [provedor de soluções na nuvem da Microsoft (CSP)](https://partner.microsoft.com/membership/cloud-solution-provider) .

- Antes de configurar o DFCI para Surface, você deve estar familiarizado com os requisitos de configuração do AutoPilot no [Microsoft Intune](https://docs.microsoft.com/intune/) e [Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/) (Azure AD).

## Antes de começar

Adicione seus dispositivos de superfície de destino a um grupo de segurança do Azure AD. Para obter mais informações sobre como criar e gerenciar grupos de segurança, consulte a [documentação do Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).

## Configurar o gerenciamento do DFCI para dispositivos Surface

Um ambiente DFCI requer a configuração de um perfil DFCI que contém as configurações e um perfil do AutoPilot para aplicar as configurações a dispositivos registrados. Um perfil de status de inscrição também é recomendado para garantir que as configurações sejam empurradas durante a configuração do OOBE quando os usuários iniciarem o dispositivo pela primeira vez. Este guia explica como configurar o ambiente DFCI e gerenciar as configurações de configuração de UEFI para dispositivos de superfície direcionado.

## Criar perfil do DFCI

Antes de definir as configurações da política do DFCI, crie primeiro um perfil do DFCI e atribua-o ao grupo de segurança do Azure AD que contém seus dispositivos de destino.

1. Entre em seu locatário em devicemanagement.microsoft.com.
2. No centro de administração do Microsoft Endpoint Manager, selecione **dispositivos > perfis de configuração > criar perfil** e insira um nome; por exemplo, **DFCI política de configuração.**
3. Selecione **Windows 10 e posterior** para tipo de plataforma.
4. Na lista suspensa tipo de perfil, selecione **interface de configuração do firmware do dispositivo** para abrir a DFCI Blade contendo todas as configurações de política disponíveis. Para obter informações sobre as configurações do DFCI, consulte a tabela 1 nesta página ou a [documentação do Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows). Você pode definir as configurações do DFCI durante o processo de instalação inicial ou posteriormente editando o perfil do DFCI.

    ![Criar perfil do DFCI](images/df1.png)

5. Clique em **OK** e, em seguida, selecione **criar**.
6. Selecione **tarefas** e, em **selecione grupos para incluir** , selecione o grupo de segurança do Azure AD que contém seus dispositivos de destino, conforme mostrado na figura a seguir. Clique em **Salvar**.

    ![Atribuir grupo de segurança](images/df2a.png)

## Criar perfil do AutoPilot

1. No Endpoint Manager em devicemanagement.microsoft.com, selecione **dispositivos > registro do Windows** e role para baixo até **perfis de implantação**.
2. Selecione **Criar perfil** e insira um nome; por exemplo, **meu perfil do AutoPilot**e selecione **Avançar**.
3. Selecione as seguintes configurações:

    - Modo de implantação: **controlado pelo usuário**.
    - Tipo de junção: Azure **ad associado**.

4. Deixe as configurações padrão restantes inalteradas e selecione **Avançar**, conforme mostrado na figura a seguir.

    ![Criar perfil do AutoPilot](images/df3b.png)

5. Na página atribuições, escolha **Selecionar grupos para incluir** e clique em seu grupo de segurança do Azure AD. Selecione **Avançar**.
6. Aceite o resumo e selecione **criar**. Agora, o perfil do AutoPilot é criado e atribuído ao grupo.

## Configurar a página de status de inscrição

Para garantir que os dispositivos apliquem a configuração DFCI durante o OOBE, antes que os usuários entrem, você precisa configurar o status de inscrição.

Para obter mais informações, confira [Configurar uma página de status de inscrição](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).


## Definir configurações de DFCI em dispositivos de superfície

O DFCI inclui um conjunto otimizado de políticas de configuração UEFI que fornecem um nível adicional de segurança bloqueando os dispositivos no nível de hardware. O DFCI foi projetado para ser usado em conjunto com as configurações de gerenciamento de dispositivo móvel no nível do software. Observe que as configurações do DFCI só afetam componentes de hardware incorporados a dispositivos Surface e não se estendem a periféricos conectados, como webcams USB. (No entanto, você pode usar as políticas de restrição de dispositivo no Intune para desativar o acesso a periféricos conectados no nível do software).

Você define as configurações da política do DFCI editando o perfil do DFCI do Endpoint Manager, conforme mostrado na figura abaixo. 

- No Endpoint Manager em devicemanagement.microsoft.com, selecione **dispositivos > perfis de configuração do Windows > > "nome do perfil do DFCI" > propriedades > configurações**.

    ![Definir configurações de DFCI](images/dfciconfig.png)

### Bloquear o acesso do usuário às configurações de UEFI

Para muitos clientes, a capacidade de impedir que os usuários alterem as configurações de UEFI é extremamente importante e um motivo principal para usar o DFCI. Conforme listado na tabela 1, isso é gerenciado por meio da configuração **permitir que o usuário local altere as configurações de UEFI**. Se você não editar ou definir essa configuração, os usuários locais poderão alterar qualquer configuração de UEFI não gerenciada pelo Intune. Portanto, é altamente recomendável desabilitar **permitir que o usuário local altere as configurações de UEFI.**
O restante das configurações do DFCI permite que você desative a funcionalidade que, de outra forma, estaria disponível para os usuários. Por exemplo, se você precisar proteger informações confidenciais em áreas altamente seguras, pode desativar a câmera e, se não quiser que os usuários façam a inicialização a partir de unidades USB, também é possível desativar isso.

### Tabela 1. Cenários DFCI

| Meta de gerenciamento de dispositivos                        | Etapas de configuração                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Impedir que os usuários locais alterem as configurações de UEFI | Em **recursos de segurança > permitir que o usuário local altere as configurações de UEFI**, selecione **nenhuma**.              |
| Desabilitar câmeras                               | Em **hardware embutido > câmeras**, selecione **desabilitado**.                                       |
| Desabilitar microfones e alto-falantes              | Em **hardware integrado > microfones e alto-falantes**, selecione **desabilitado**.                      |
| Desativar rádios (Bluetooth, Wi-Fi)             | Em **hardware integrado > rádios (Bluetooth, Wi-Fi, etc...)**, selecione **desabilitado**.                   |
| Desabilitar a inicialização a partir de mídia externa (USB, SD)    | Em **Opções de inicialização > hardware integrado > inicialização a partir de mídia externa (USB, SD)**, selecione **desabilitada**. |

> [!CAUTION]
> A configuração **desativar rádios (Bluetooth, Wi-Fi)** só deve ser usada em dispositivos que tenham uma conexão Ethernet com fio.
 
> [!NOTE]
>  DFCI no Intune inclui duas configurações que não se aplicam atualmente a dispositivos Surface: (1) virtualização de CPU e de e/s e (2) desabilitar a inicialização a partir de adaptadores de rede.
 
O Intune fornece marcas de escopo para delegar direitos administrativos e regras de aplicabilidade para gerenciar tipos de dispositivo. Para obter mais informações sobre o suporte ao gerenciamento de políticas e detalhes completos sobre todas as configurações do DFCI, confira a [documentação do Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).

## Registrar dispositivos no AutoPilot

Conforme mencionado acima, o DFCI só pode ser aplicado em dispositivos registrados no piloto automático do Windows pelo revendedor ou distribuidor e só tem suporte no momento, no Surface Pro 7, Surface Pro X e Surface laptop 3. Por motivos de segurança, não é possível "autoprovisionar" seus dispositivos para o AutoPilot.

## Sincronizar manualmente dispositivos do AutoPilot

Embora as configurações de política do Intune normalmente sejam aplicadas quase que imediatamente, pode haver um atraso de 10 minutos para que as configurações entrem em vigor em dispositivos de destino. Em circunstâncias raros, é possível atrasar até 8 horas. Para garantir que as configurações sejam aplicadas o mais breve possível, (por exemplo, em cenários de teste), você pode sincronizar manualmente os dispositivos de destino.

- No Endpoint Manager em devicemanagement.microsoft.com, acesse **dispositivos > registro de dispositivo > registro do windows > dispositivos do Windows AutoPilot** e selecione **sincronizar**.

 Para obter mais informações, consulte [sincronizar seu dispositivo do Windows manualmente](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

> [!NOTE]
> Ao ajustar as configurações diretamente em UEFI, você precisa garantir que o dispositivo seja completamente reiniciado para o logon padrão do Windows.

## Verificar as configurações de UEFI em dispositivos gerenciados pelo DFCI

Em um ambiente de teste, você pode verificar as configurações na interface do Surface UEFI.

1. Open Surface UEFI, que envolve o pressionamento do botão de **volume +** e **energia** ao mesmo tempo.
2. Selecione **dispositivos**. O menu UEFI refletirá as configurações definidas, conforme mostrado na figura a seguir.

    ![UEFI da superfície](images/df3.png)

    Veja como:

      - As configurações estão acinzentadas porque **permitir que o usuário local altere a configuração de UEFI** está definido como None.
      - O áudio está definido como desativado porque os **microfones e alto-falantes** são definidos como **desabilitado**.

## Removendo configurações de política de DFCI

Quando você cria um perfil do DFCI, todas as configurações definidas permanecerão em vigor em todos os dispositivos dentro do escopo de gerenciamento do perfil. Você só pode remover as configurações da política do DFCI editando o perfil do DFCI diretamente.

Se o perfil DFCI original tiver sido excluído, você poderá remover as configurações de política criando um novo perfil e editando as configurações, conforme apropriado.

## Removendo o gerenciamento de DFCI

**Para remover o gerenciamento do DFCI e devolver o dispositivo para o novo estado de fábrica:**

1. Desative o dispositivo do Intune:
    1. No Endpoint Manager em devicemanagement.microsoft.com, escolha **grupos > todos os dispositivos**. Selecione os dispositivos que você deseja desativar e, em seguida, escolha **desativar/apagar.** Para saber mais, consulte [remover dispositivos usando apagar, desativar ou cancelar o registro manual do dispositivo](https://docs.microsoft.com/intune/remote-actions/devices-wipe). 
2. Exclua o registro de piloto automático do Intune:
    1.  Escolha **registro de dispositivo > dispositivos > de registro do Windows**.
    2. Em dispositivos do Windows AutoPilot, escolha os dispositivos que você deseja excluir e, em seguida, escolha **excluir**.
3. Conecte o dispositivo à Internet com fio com adaptador Ethernet com marca da superfície. Reinicie o dispositivo e abra o menu UEFI (pressione e mantenha pressionado o botão volume-up enquanto também pressiona e libera o botão de energia).
4. Selecione **gerenciamento > configurar > atualização da rede** e, em seguida, escolha **recusar.**

Para continuar a gerenciar o dispositivo com o Intune, mas sem o gerenciamento do DFCI, registre o dispositivo no piloto automático e registre-o no Intune. O DFCI não será aplicado a dispositivos autoregistrados.

## Saiba mais
- [Ignite 2019: anunciando o gerenciamento remoto de configurações de controle de Surface do Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Piloto automático do Windows](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot e dispositivos Surface](windows-autopilot-and-surface-devices.md) 
- [Usar perfis do DFCI em dispositivos Windows no Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
