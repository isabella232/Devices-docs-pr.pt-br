---
title: Configuração da primeira vez para Surface Hub 2S
description: Saiba como concluir a configuração da primeira vez para o Surface Hub 2S.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830633"
---
# Configuração da primeira vez para Surface Hub 2S

Quando você inicia pela primeira vez o Surface Hub 2S, o dispositivo entra automaticamente no modo de configuração inicial para orientá-lo por meio de configuração de conta e configurações relacionadas.

## Configurando a conta do Surface Hub 2S

1. **Configure sua localidade.** Digite a região, o idioma, o layout do teclado e as informações do fuso horário. Selecione **Avançar**.

   ![* Configurar sua localidade *](images/sh2-run1.png) <br>
1. **Conecte-se a uma rede sem fio.** Escolha sua rede sem fio preferencial e selecione **Avançar.**

- Essa opção não é mostrada se estiver conectada usando um cabo Ethernet.
- Você não pode se conectar a uma rede sem fio em pontos de acesso (portais prisioneiros) que redirecionem solicitações de entrada para um site do provedor.

3. **Insira as informações da conta do dispositivo.** Use **domínio** \ usuário para ambientes locais e híbridos e o **usuário \ @example. com** para ambientes online. Selecione **Avançar.**

   ![* Insira as informações da conta do dispositivo *](images/sh2-run2.png) <br>
1. **Insira informações adicionais.** Se solicitado, forneça o endereço do servidor do Exchange e selecione **Avançar.**

    ![* Insira mais informações; por exemplo, nome do servidor Exchange *](images/sh2-run3.png) <br>

1. **Nomeie este dispositivo.** Insira um nome para o seu dispositivo ou use o sugerido com base no nome para exibição e nome do princípio do usuário [UPN] da sua conta. **Selecione Avançar**.

- O **nome amigável** fica visível no canto inferior esquerdo do Surface Hub 2S e é exibido durante a projeção para o dispositivo.

- O **nome do dispositivo** identifica o dispositivo quando associado ao Active Directory ou ao Active Directory do Azure, e ao registrar o dispositivo com o Intune.

  ![* Nomeie este dispositivo *](images/sh2-run4.png) <br>
 
## Configurando contas de administradores de dispositivos

Você só pode configurar administradores de dispositivo durante a primeira configuração. Para obter mais informações, confira [Surface Hub 2s Device afiliation](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).

 Na janela **Configurar administradores para este dispositivo** , selecione uma das seguintes opções: serviços de domínio do Active Directory, Active Directory do Azure ou administrador local.

   ![* Configurar administradores para este dispositivo *](images/sh2-run5.png) <br>

### Active Directory Domain Services

1. Insira as credenciais de um usuário que tem permissões para ingressar no dispositivo no Active Directory.

    ![* Configurar administradores usando ingresso no domínio *](images/sh2-run6.png) <br>

2. Selecione o grupo de segurança do Active Directory que contém os membros permitidos para fazer logon no aplicativo configurações no Surface Hub 2S.

    ![* Insira um grupo de segurança *](images/sh2-run7.png) <br>
1. Selecione **concluir**. O dispositivo será reiniciado.

### Azure Active Directory

Ao escolher associar seu dispositivo ao Azure Active Directory, o dispositivo será reiniciado imediatamente e exibirá a página a seguir. Selecione **Avançar**.

![* Se a sua organização usa o Office 365 ou outros serviços comerciais da Microsoft, registraremos este dispositivo com a sua organização *](images/sh2-run8.png) <br>

1. Digite o endereço de email ou o UPN de uma conta **com o Intune plano 1** ou superior e, em seguida, selecione **Avançar.**

    ![* Insira uma conta corporativa ou de estudante *](images/sh2-run9.png) <br>

2. Se for redirecionado, autentique usando a página de entrada da sua organização e fornecerá informações de logon adicionais, se solicitado. O dispositivo será reiniciado.

## Conta de administrador local

- Insira um nome de usuário e senha para seu administrador local. O dispositivo será reiniciado.

     ![* Configurar uma conta de administrador *](images/sh2-run10.png) <br>
 
## Usando pacotes de provisionamento

Se você inserir um pen drive com um pacote de aprovisionamento em uma das portas USB ao iniciar o Surface Hub 2S, o dispositivo exibirá a página a seguir.

1. Insira as configurações solicitadas e selecione **Configurar**.

    ![* Insira as configurações regionais para o pacote de provisionamento *](images/sh2-run11.png) <br>

    ![* Provisionar este dispositivo em mídia removível *](images/sh2-run12.png) <br>
2. Escolha o pacote de provisionamento que você gostaria de usar.

   ![* Escolha o pacote de provisionamento a ser usado *](images/sh2-run13.png) <br>

3. Se você criou um arquivo CSV de vários dispositivos, poderá escolher uma configuração de dispositivo. Para obter mais informações, consulte [criar pacotes de provisionamento para o Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).


    ![* Selecione uma conta de dispositivo e um nome amigável do seu arquivo de configuração *](images/sh2-run14.png) <br>

4. Siga as instruções para concluir a configuração da primeira vez.
