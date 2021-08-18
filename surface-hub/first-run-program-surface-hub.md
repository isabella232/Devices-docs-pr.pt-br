---
title: Configuração da primeira vez para Surface Hub
description: O termo \ 0034;primeira execução\ 0034; se refere a uma série de etapas a serem executadas na primeira vez que você liga o Microsoft Surface Hub e significa o mesmo que \ 0034;configuração inicial pelo usuário \ 0034; (OOBE). Esta seção guiará você no processo.
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: primeira execução, Surface Hub, configuração inicial pelo usuário, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: medium
ms.openlocfilehash: 947d73febb41562b44d5ecb102511be314ad987e
ms.sourcegitcommit: 3810c4310e9f5b5b9ad7b4584eaede2789ccd946
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902900"
---
# <a name="first-time-setup-for-surface-hub"></a>Configuração da primeira vez para Surface Hub

Quando você começa a Surface Hub, o dispositivo entra automaticamente no modo de Instalação da primeira vez para orientá-lo através da configuração da conta e das configurações relacionadas.

> [!TIP]
> Você pode automatizar todo o processo de instalação com um pacote [de Provisionamento](#use-provisioning-packages) para garantir uma experiência consistente em vários Surface Hubs.

## <a name="get-started"></a>Introdução

1. Por padrão, Cortana está habilitado para orientá-lo durante o processo. Para desativar Cortana assistência, selecione o ícone de microfone.

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana está habilitado para orientá-lo durante o processo":::

2. **Selecione sua região.** Confirme a região detectada automaticamente e selecione **Sim**.

    :::image type="content" source="images/hub-setup-region.png" alt-text="Selecionar suaregião":::

3. **Confirme o layout do teclado.** Selecione **Sim**.

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="Confirmar layout do teclado":::

4. Para adicionar um segundo teclado, selecione **Adicionar layout**. Caso contrário, selecione **Ignorar**.

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="Adicionar um segundo teclado":::

5. **Conexão para uma rede.** Se você já tiver anexado um cabo Ethernet, Surface Hub se conectará automaticamente à sua rede. Como alternativa, você pode se conectar a uma rede sem fio. **Observação:** Você não pode se conectar a uma rede sem fio em hotspots (portais cativos) que redirecionam as solicitações de login para o site de um provedor. Selecione **Avançar**.

    :::image type="content" source="images/hub-setup-network.png" alt-text="Conectar a uma rede":::

6. **Aceite Windows 10 Contrato de Licença.** Selecione **Aceitar**.

    :::image type="content" source="images/hub-setup-license.png" alt-text="Aceitar Windows 10 Contrato de Licença":::

7. **Insira informações da** conta do dispositivo usando um endereço UPN (user@contoso.com) ou um endereço de domínio de nível inferior (CONTOSO\user). Use o formato que corresponde ao seu ambiente e insira a senha.

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="Inserir informações da conta do dispositivo":::

| Ambiente                                              | Formato exigido para a conta de dispositivo |
| -------------------------------------------------------- | ---------------------------------- |
| A conta de dispositivo é hospedada somente online                     | username@contoso.com               |
| A conta de dispositivo é hospedada somente no local                | CONTOSO\user                       |
| A conta de dispositivo é hospedada online e local (híbrida) | CONTOSO\user                       |

>[!NOTE]
>Embora você possa ignorar a configuração de uma conta de dispositivo, o dispositivo não será totalmente integrado à sua infraestrutura. Se você ignorar a configuração agora, você poderá adicionar uma conta do dispositivo depois usando o aplicativo Configurações.

8. **Insira sua senha** e selecione **Next.**

9. Surface Hub detecta automaticamente Exchange informações de endereço SIP e servidor do domínio inserido na etapa anterior. Ou, se necessário, forneça seu endereço Exchange servidor e selecione **Next**.

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange servidor e endereço SIP":::

10. **Nomeia esse dispositivo.** Insira um nome para seu dispositivo ou use o sugerido. **Selecione Próximo**.

    :::image type="content" source="images/hub-setup-name.png" alt-text="Nomear este dispositivo":::

- O **nome Amigável** fica visível no canto inferior esquerdo do Surface Hub 2S e é mostrado ao projetar para o dispositivo.
- O **nome do dispositivo** identifica o dispositivo quando afiliada ao Active Directory ou Azure Active Directory e ao registrar o dispositivo com o Intune.

>[!NOTE]
>Se você quiser habilitar [Miracast sobre infraestrutura](miracast-over-infrastructure.md), o nome do dispositivo precisa ser detectável por meio de DNS. Você pode conseguir isso permitindo que o Surface Hub registre automaticamente por meio do DNS dinâmico, ou criando manualmente um registro A ou AAAA para o nome do dispositivo do Surface Hub.

### <a name="configure-device-admin-accounts"></a>Configurar contas de administrador de dispositivo

Você só pode configurar administradores de dispositivos durante a instalação da primeira vez. Para obter mais informações, consulte:

- [Surface Hub afiliação de dispositivos 2S](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [Gerenciamento de grupo de administração](admin-group-management-for-surface-hub.md)

1. **Escolha o tipo de conta de administrador.** Selecione uma das seguintes opções: Serviços de Domínio do Active Directory, Azure Active Directory ou administrador local.

    :::image type="content" source="images/hub-setup-join.png" alt-text="Escolha o tipo de conta de administrador":::

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. Se você pretende usar Surface Hub em um ambiente local, poderá afiliadar o Hub aos Serviços de **Domínio do Active Directory.**  Insira as credenciais de um usuário que tenha permissões para ingressar no dispositivo no Active Directory.
2. Selecione o Grupo de Segurança do Active Directory que contém membros permitidos a entrar no aplicativo Configurações no Surface Hub 2S.
3. Selecione **Concluir**. O dispositivo será reiniciado agora.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. Se você pretende gerenciar Surface Hub na nuvem usando Microsoft Intune ou um provedor MDM, selecione **Microsoft Azure Active Directory**.
2. Selecione Próximo e entre com uma conta de trabalho ou de estudante. Se redirecionado, autenture-se usando a página de login da sua organização e forneça credenciais adicionais, se solicitado. Caso contrário, insira sua senha e selecione **Next.**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="Entrar com uma conta de trabalho ou de estudante":::

>[!NOTE]
>Para configurar quem pode usar o aplicativo Configurações para administrar Surface Hubs, certifique-se de que o registro automático do Intune está habilitado em seu locatário antes de ingressar no dispositivo no Azure AD. Em seguida, as políticas do Intune podem ser usadas para [configurar administradores](surface-hub-2s-nonglobal-admin.md) não globais nos Surface Hubs.

### <a name="local-administrator-account"></a>Conta de Administrador Local

- Insira um nome de usuário e uma senha memorável para o administrador [](surface-hub-2s-recover-reset.md) local. (Se você esquecer a senha de administrador local, precisará recuperar seu dispositivo e repetir o processo de instalação.)  

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="Insira uma senha memorável para a conta de administrador local":::

### <a name="choose-privacy-settings-for-your-device"></a>Escolha as configurações de privacidade para o seu dispositivo

- Selecione entre as configurações de privacidade disponíveis e selecione **Aceitar.**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="Escolha configurações de privacidade":::

### <a name="use-provisioning-packages"></a>Usar pacotes de provisionamento

Você pode personalizar as opções de configuração da primeira vez, permitindo que você garanta uma experiência consistente em vários Surface Hubs.

1. Para começar, revise a documentação em [Criar pacotes de provisionamento](provisioning-packages-for-surface-hub.md) e salve o pacote de provisionamento em uma unidade de pen drive usb.
2. Insira a unidade de pen drive em uma das portas USB antes de iniciar o processo de instalação.
3. Quando solicitado, escolha o pacote de provisionamento que você gostaria de usar.
4. Se você criou um arquivo CSV de vários dispositivos, poderá escolher uma configuração de dispositivo.
5. Siga as instruções para concluir a instalação da primeira vez.
