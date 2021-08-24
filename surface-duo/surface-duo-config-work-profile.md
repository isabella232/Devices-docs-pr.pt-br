---
title: Configure o Android Enterprise Work Profile para Surface Duo
description: Este artigo explica como configurar o perfil de trabalho no Surface Duo.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 380c5fc625983119a516f5d0e2294af70e0dbd29
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911196"
---
# <a name="configure-android-enterprise-work-profile-for-surface-duo"></a>Configure o Android Enterprise Work Profile para Surface Duo

Direcionados para implantações BYOD, os perfis de trabalho fornecem um espaço separado no Duo para aplicativos e dados de trabalho, dando às organizações controle total de seus dados, aplicativos e políticas de segurança sem impedir que os funcionários usem seus dispositivos para aplicativos e dados pessoais.

### <a name="set-up-android-enterprise-work-profile"></a>Configurar o Perfil de Trabalho Enterprise Android

Use perfis de trabalho para gerenciar dados corporativos e aplicativos em dispositivos Android de propriedade do usuário. Por padrão, o registro de dispositivos de perfil de trabalho de propriedade pessoal está habilitado e não requer mais configuração de administrador.  

**Para habilitar Enterprise Perfil de Trabalho:**

- Em Endpoint Manager, selecione **Dispositivos**  >  **Android**  >  **Android registro** e selecione **Dispositivos Pessoais com perfil de trabalho**.
<br><br>
 ![Habilitar Enterprise Perfil de Trabalho.](images/enroll-start.png)

 
**Entrar no Surface Duo com o Perfil de Trabalho Enterprise Android**

1. Instale o Portal da Empresa aplicativo da Google Play Store e entre com sua conta de estudante ou trabalho da Microsoft.<br><br>
![Entre no Surface Duo.](images/duo-wp-1.png)
 
2. Na página Instalação do Access, selecione **Iniciar**.<br><br>
![Begin.](images/duo-wp-2.png)

3. Revise as informações na página de privacidade e selecione **Continuar**.<br><br>
 ![Continue.](images/duo-wp-3.png)
<br><br>
 ![Selecione continuar.](images/duo-wp-4.png)
 
4. Quando a configuração do perfil de trabalho for concluída, selecione **Continuar** para ativar e registrar o dispositivo.<br><br>
 ![Selecione continuar a ativar e registrar o dispositivo.](images/duo-wp-5.png)

5. Selecione **Continuar**.<br><br>
 ![Selecione continuar novamente.](images/duo-wp-6.png)

6. Quando você tiver ativado o perfil de trabalho, selecione **Continuar** para atualizar as configurações do dispositivo. Neste exemplo, o perfil de trabalho aplica uma configuração MDM para exigir uma senha alfanumérica de 6 dígitos mais forte. <br><br>

     ![Exemplo de senha alfanumérica.](images/duo-wp-7.png)<br><br>
7. Selecione **Resolver** para inserir a autenticação necessária e selecione **Continuar** para concluir a configuração do Perfil de Trabalho. <br><br>
     ![Selecione continuar para concluir a instalação.](images/duo-wp-8.png)<br><br>
     ![concluir a instalação.](images/duo-wp-9.png)<br><br>

## <a name="learn-more"></a>Saiba mais

- [Configurar o registro de dispositivos Enterprise de perfil de trabalho do Android](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

