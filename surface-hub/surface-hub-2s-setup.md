---
title: Instalação da primeira vez para o Surface Hub 2S
description: Saiba como concluir a instalação da primeira vez para o Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 9cbce8bf0cc9c729af4cd052167fef016197274f
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442189"
---
# <a name="first-time-setup-for-surface-hub-2s"></a>Instalação da primeira vez para o Surface Hub 2S

Quando você inicia o Surface Hub 2S pela primeira vez, o dispositivo entra automaticamente no modo de Instalação da primeira vez para orientá-lo através da configuração da conta e das configurações relacionadas.

## <a name="configuring-surface-hub-2s-account"></a>Configurando a conta do Surface Hub 2S

1. **Configure sua localidade.** Insira informações de região, idioma, layout do teclado e fuso horário. Selecione **Avançar**.

   ![* Configure sua localidade *](images/sh2-run1.png)

1. **Conecte-se a uma rede sem fio.** Escolha sua rede sem fio preferida e selecione **Next.**

   - Essa opção não será mostrada se estiver conectada usando um cabo Ethernet.

   - Você não pode se conectar a uma rede sem fio em hotspots (portais cativos) que redirecionam as solicitações de login para o site de um provedor.

3. **Insira informações da conta do dispositivo.** Use **domínio\usuário** para ambientes locais e híbridos e **user\@example.com** para ambientes online. Selecione **Próximo.**

   ![* Insira informações da conta do dispositivo *](images/sh2-run2.png)

1. **Insira informações adicionais.** Se solicitado, forneça seu endereço de servidor do Exchange e selecione **Next.**

   ![* Insira mais informações; por exemplo, nome do servidor exchange*](images/sh2-run3.png)

1. **Nomeia esse dispositivo.** Insira um nome para seu dispositivo ou use o sugerido com base no nome de exibição da sua conta e no nome de princípio do usuário [UPN]. **Selecione Próximo**.

   - O **nome Amigável** fica visível no canto inferior esquerdo do Surface Hub 2S e é mostrado ao projetar para o dispositivo.

   - O **nome do dispositivo** identifica o dispositivo quando afiliada ao Active Directory ou ao Azure Active Directory e ao registrar o dispositivo com o Intune.

   ![* Nome deste dispositivo*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a>Configurando contas de administrador de dispositivo

Você só pode configurar administradores de dispositivos durante a instalação da primeira vez. Para obter mais informações, consulte [a afiliação de dispositivos do Surface Hub 2S](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation).

Na janela **Administradores de** Instalação para este dispositivo, selecione uma das seguintes opções: Serviços de Domínio do Active Directory, Azure Active Directory ou Administrador Local.

![* Administradores de instalação para este dispositivo *](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. Insira as credenciais de um usuário que tenha permissões para ingressar no dispositivo no Active Directory.

    ![* Administradores de instalação usando a junção de domínio *](images/sh2-run6.png)

2. Selecione o Grupo de Segurança do Active Directory que contém membros permitidos para fazer logoff no aplicativo Configurações no Surface Hub 2S.

   ![* Insira um grupo de segurança *](images/sh2-run7.png)

1. Selecione **Concluir**. O dispositivo será reiniciado agora.

### <a name="azure-active-directory"></a>Azure Active Directory

Ao optar por afiliadar seu dispositivo ao Azure Active Directory, o dispositivo será reiniciado imediatamente e exibirá a página a seguir.

![* Se sua organização usa o Office 365 ou outros serviços comerciais da Microsoft, registraremos esse dispositivo com sua organização*](images/sh2-run8.png)

1. Selecione **Avançar**.

1. Insira o endereço de email ou UPN de uma conta com o Plano 1 ou superior do **Intune** e selecione **Próximo.**

   ![* Insira conta de trabalho ou de estudante*](images/sh2-run9.png)

1. Se redirecionado, autenticar usando a página de logon da sua organização e fornecer informações de logon adicionais, se solicitado. O dispositivo será reiniciado agora.

## <a name="local-administrator-account"></a>Conta de Administrador Local

- Insira um nome de usuário e uma senha para o administrador local. O dispositivo será reiniciado.

  ![* Configurar uma conta de administrador*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a>Usando pacotes de provisionamento

Se você inserir uma unidade de pen drive com um pacote de provisionamento em uma das portas USB ao iniciar o Surface Hub 2S, o dispositivo exibirá a página a seguir.

1. Insira as configurações solicitadas e selecione **Configurar**.

   ![* Insira configurações regionais para o pacote de provisionamento*](images/sh2-run11.png)

   ![* Provisione este dispositivo de mídia removível*](images/sh2-run12.png)

2. Escolha o pacote de provisionamento que você gostaria de usar.

   ![* Escolha o pacote de provisionamento a ser usado*](images/sh2-run13.png)

3. Se você criou um arquivo CSV de vários dispositivos, poderá escolher uma configuração de dispositivo. Para obter mais informações, consulte [Create provisioning packages for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).

   ![* Selecione uma conta de dispositivo e um nome amigável no arquivo de configuração*](images/sh2-run14.png)

4. Siga as instruções para concluir a instalação da primeira vez.
