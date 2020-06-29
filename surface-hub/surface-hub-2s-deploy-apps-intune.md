---
title: Implantar aplicativos no Surface Hub 2S usando o Intune
description: Saiba como você pode implantar aplicativos em Surface Hub 2S usando o Intune.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830524"
---
# Implantar aplicativos no Surface Hub 2S usando o Intune

Você pode instalar aplicativos adicionais para atender às necessidades da sua equipe ou da sua organização.

## Diretrizes de desenvolvedor

- O Surface Hub executa apenas [aplicativos da Plataforma Universal do Windows (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp). Os aplicativos criados usando o [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) não serão executados no Surface Hub.
- Os aplicativos devem ser voltados para a [família de dispositivos universais](https://msdn.microsoft.com/library/windows/apps/dn894631) ou família de dispositivos da Equipe do Windows.
- O Surface hub só dá suporte [a aplicativos licenciados offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) da [Microsoft Store para empresas](https://businessstore.microsoft.com/store).
- Por padrão, os aplicativos devem ser assinados pela Microsoft Store para serem instalados. Durante o processo de teste e desenvolvimento, você também pode optar por executar os aplicativos UWP assinados pelo desenvolvedor colocando o dispositivo no modo de desenvolvedor.
- Ao desenvolver e enviar aplicativos para a Microsoft Store, defina a disponibilidade da família de dispositivos e as opções de licenciamento organizacional para garantir que os aplicativos estejam disponíveis para serem executados no Surface Hub.
- Você precisa de credenciais de administrador para instalar aplicativos no Surface Hub. Projetado para uso em salas de reunião e outros espaços compartilhados, o Surface Hub impede que usuários regulares acessem a Microsoft Store para baixar e instalar aplicativos.

## Diretrizes de implantação

Você pode implantar aplicativos da plataforma universal do Windows (UWP) em Surface Hub 2S usando o Intune, facilitando a implantação do aplicativo em dispositivos.

1. Para implantar aplicativos, habilite o MDM para a sua organização. No portal do Intune, selecione o **Intune** como sua autoridade de MDM (recomendado). <br>

    ![Escolher autoridade do MDM](images/sh2-set-intune5.png)

2. Habilite a Microsoft Store para empresas no Intune. Abra o Intune, selecione **aplicativos cliente**  >  **Microsoft Store para empresas.** <br>

    ![Habilitar a loja para empresas](images/sh2-deploy-apps-sync.png)

3. No Intune, abra **a Microsoft Store para empresas** e selecione **configurações**  >  **distribuir**  >  **ferramentas de gerenciamento**. Escolha o **Microsoft Intune** como sua ferramenta de gerenciamento. <br>

    ![Adicionar o Intune como sua ferramenta de gerenciamento](images/sh2-set-intune8.png)

4. Na Microsoft Store para empresas, selecione **configurações**de compra de compras  >  **Shop**  >  **Shopping Experience**e, em seguida, selecione **Mostrar aplicativos offline**. Os aplicativos offline fazem referência a aplicativos que podem ser sincronizados com o Intune e implantados de forma centralizada em um dispositivo.
5. Depois de habilitar compras offline, você pode adquirir licenças offline para aplicativos que você pode sincronizar com o Intune e implantar como licenciamento de dispositivo.
6. Em **Intune**  >  **aplicativos cliente**do Intune  >  ,**Microsoft Store para empresas**, selecione **sincronizar**.
7. Na página aplicativos cliente, procure o aplicativo na lista de aplicativos. Atribua os aplicativos ao grupo de dispositivos ou grupos desejado. Selecione **tarefas**  >  **Adicionar grupo**. <br>

![* Atribuição de aplicativos a grupos *](images/sh2-assign-group.png) <br>

8. Em tipo de atribuição, escolha **obrigatório**. <br>

![* Atribuição de aplicativos a grupos *](images/sh2-add-group.png) <br>

9. Para os grupos selecionados, escolha **Licenciamento de dispositivo** e, em seguida, selecione **OK** e salve a tarefa. <br>
 
![* Atribuição de aplicativos a grupos *](images/sh2-apps-assign.png)
