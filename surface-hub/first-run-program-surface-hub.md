---
title: Primeira configuração para Surface Hub
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
ms.openlocfilehash: 551867ccbb041fe292d9ec60f38bb89acfbc764e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472441"
---
# <a name="first-time-setup-for-surface-hub"></a>Primeira configuração para Surface Hub

Quando você inicia o Surface Hub, o dispositivo entra automaticamente no modo de instalação pela primeira vez para guiá-lo pela configuração da conta e pelas configurações relacionadas.

> [!TIP]
> Você pode automatizar todo o processo de instalação com um [pacote de provisionamento](#use-provisioning-packages) para garantir uma experiência consistente em vários Surface Hubs.

## <a name="get-started"></a>Introdução

1. Por padrão, Cortana é habilitado para orientar você pelo processo. Para desativar a Cortana, selecione o ícone de microfone.

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana está habilitado para guiá-lo durante o processo.":::

2. **Selecione sua região.** Confirme a região detectada automaticamente e selecione **Sim**.

    :::image type="content" source="images/hub-setup-region.png" alt-text="Selecione sua região.":::

3. **Confirme o layout do teclado.** Selecione **Sim**.

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="Confirme o layout do teclado.":::

4. Para adicionar um segundo teclado, selecione **Adicionar layout**. Caso contrário, selecione **Ignorar**.

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="Adicione um segundo teclado.":::

5. **Conexão uma rede.** Se você já tiver anexado um cabo Ethernet, Surface Hub se conectará automaticamente à sua rede. Como alternativa, você pode se conectar a uma rede sem fio. **Nota:** Você não pode se conectar a uma rede sem fio em pontos de acesso (portais cativos) que redirecionam solicitações de entrada para o site de um provedor. Selecione **Avançar**.

    :::image type="content" source="images/hub-setup-network.png" alt-text="Conexão uma rede.":::

6. **Aceite Windows 10 de Licença.** Selecione **Aceitar**.

    :::image type="content" source="images/hub-setup-license.png" alt-text="Aceite Windows 10 de Licença.":::

7. **Insira informações da conta de** dispositivo usando um endereço UPN (user@contoso.com) ou um endereço de domínio de nível inferior (CONTOSO\user). Use o formato que corresponde ao seu ambiente e insira a senha.

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="Insira as informações da conta do dispositivo.":::

| Ambiente                                              | Formato exigido para a conta de dispositivo |
| -------------------------------------------------------- | ---------------------------------- |
| A conta de dispositivo é hospedada somente online                     | username@contoso.com               |
| A conta do dispositivo é hospedada somente no local                | CONTOSO\user                       |
| A conta de dispositivo é hospedada online e localmente (híbrida) | CONTOSO\user                       |

>[!NOTE]
>Embora você possa ignorar a configuração de uma conta de dispositivo, o dispositivo não será totalmente integrado à sua infraestrutura. Se você ignorar a configuração agora, você poderá adicionar uma conta do dispositivo depois usando o aplicativo Configurações.

8. **Insira sua senha** e selecione **Avançar.**

9. Surface Hub detecta automaticamente Exchange servidor e informações de endereço SIP do domínio inserido na etapa anterior. Ou, se necessário, forneça o endereço Exchange servidor e selecione **Avançar**.

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange servidor e endereço SIP.":::

10. **Nomeie este dispositivo.** Insira um nome para seu dispositivo ou use o sugerido. **Selecione Avançar**.

    :::image type="content" source="images/hub-setup-name.png" alt-text="Nomeie este dispositivo.":::

- O **nome amigável** é visível no canto inferior esquerdo do Surface Hub 2S e é mostrado ao projetar para o dispositivo.
- O **nome do** dispositivo identifica o dispositivo quando afiliado ao Active Directory ou Azure Active Directory e ao registrar o dispositivo com Intune.

>[!IMPORTANT]
>Se você planeja afiliar o Surface Hub com o Active Directory, o nome do dispositivo deve atender aos requisitos padrão para nomes de computador no [AD](/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou#computer-names); caso contrário, a instalação falhará.

>[!NOTE]
>Se você quiser habilitar [Miracast sobre infraestrutura](miracast-over-infrastructure.md), o nome do dispositivo precisa ser detectável por meio de DNS. Você pode conseguir isso permitindo que o Surface Hub registre automaticamente por meio do DNS dinâmico, ou criando manualmente um registro A ou AAAA para o nome do dispositivo do Surface Hub.

### <a name="configure-device-admin-accounts"></a>Configurar contas de administrador de dispositivo

Você só pode configurar administradores de dispositivos durante a primeira instalação. Para obter mais informações, consulte:

- [Surface Hub afiliação de dispositivo 2S](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [Gerenciamento de grupo de administração](admin-group-management-for-surface-hub.md)

1. **Escolha o tipo de conta de administrador.** Selecione uma das seguintes opções: Active Directory Domain Services, Azure Active Directory administrador local.

    :::image type="content" source="images/hub-setup-join.png" alt-text="Escolha o tipo de conta de administrador.":::

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. Se você pretende usar Surface Hub em um ambiente local, poderá afiliador o **Hub com Active Directory Domain Services**.  Insira as credenciais de um usuário que tenha permissões para ingressar o dispositivo no Active Directory.
2. Selecione o Grupo de Segurança do Active Directory que contém membros com permissão para entrar no aplicativo Configurações no Surface Hub 2S.
3. Selecione **Concluir**. O dispositivo será reiniciado agora.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. Se você pretende gerenciar Surface Hub da nuvem usando Microsoft Intune ou um provedor de MDM, selecione **Microsoft Azure Active Directory**.
2. Selecione Avançar e entre com uma conta corporativa ou de estudante. Se redirecionado, autentique-se usando a página de entrada da sua organização e forneça credenciais adicionais, se solicitado. Caso contrário, insira sua senha e selecione **Avançar.**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="Entre com uma conta corporativa ou de estudante.":::

>[!NOTE]
>Para configurar quem pode usar o aplicativo Configurações para administrar o Surface Hubs, verifique se o registro automático do Intune está habilitado em seu locatário antes de ingressar o dispositivo no Azure AD. Intune políticas podem ser usadas para [configurar administradores não globais](surface-hub-2s-nonglobal-admin.md) nos Surface Hubs.

### <a name="local-administrator-account"></a>Conta de Administrador Local

- Insira um nome de usuário e uma senha memorável para o administrador local. (Se você esquecer a senha de administrador local[](surface-hub-2s-recover-reset.md), precisará recuperar seu dispositivo e repetir o processo de instalação.)  

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="Insira uma senha fácil de lembrar para a conta de administrador local.":::

### <a name="choose-privacy-settings-for-your-device"></a>Escolha as configurações de privacidade para o seu dispositivo

- Selecione entre as configurações de privacidade disponíveis e selecione **Aceitar.**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="Escolha as configurações de privacidade.":::

### <a name="use-provisioning-packages"></a>Usar pacotes de provisionamento

Você pode personalizar as opções de configuração da primeira vez, permitindo que você garanta uma experiência consistente em vários Surface Hubs.

1. Para começar, examine a documentação em [Criar pacotes de provisionamento](provisioning-packages-for-surface-hub.md) e salve o pacote de provisionamento em uma unidade usb.
2. Insira a unidade usb em uma das portas USB quando você vir a página Contrato de Licença (etapa 6 nas etapas de instalação acima).
3. Quando solicitado, escolha o pacote de provisionamento que você deseja usar.
4. Se você criou um arquivo CSV de vários dispositivos, poderá escolher uma configuração de dispositivo.
5. Siga as instruções para concluir a instalação pela primeira vez.
