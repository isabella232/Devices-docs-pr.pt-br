---
title: Instalar a Atualização da Versão Prévia do Windows 10 Team 2020
description: A atualização mais recente do sistema operacional do Surface Hub, atualização do 2020 do Windows 10 Team, já está disponível.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 6d370db0232ae1f93d1ba6b8ff15b5ff2cfa9f10
ms.sourcegitcommit: 19d2a78242777590bd09af3ac6552c07b032e0a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11142900"
---
# Instalar a Atualização da Versão Prévia do Windows 10 Team 2020 

A versão prévia do sistema operacional do Surface Hub, o **Windows 10 Team 2020 Update Preview**, está disponível sem custo adicional do [programa Windows Insider](https://insider.windows.com). 

> [!NOTE] 
> A versão pública final da atualização do Windows 10 Team 2020 agora está disponível. Para saber mais, consulte [atualização do Windows 10 Team 2020](surface-hub-2020-update.md).

A atualização do Windows 10 Team 2020 traz grandes melhorias para a implantação e a capacidade de gerenciamento de dispositivos, juntamente com os recursos mais recentes do Windows 10. Para saber mais sobre as novidades, confira a postagem de blog a seguir: [nova atualização do sistema operacional do Surface Hub lançada para visualização pública.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) Para problemas conhecidos, confira [problemas conhecidos: atualização do Windows 10 Team 2020](surface-hub-2020-team-update-known-issues.md)
 
## Pré-requisitos

- Cadastre-se com o [programa Windows Insider](https://insider.windows.com/).
- Baixe o Windows 10 Team 2020 Update Preview Build do canal rápido do programa Windows Insider.
- Após a instalação da versão prévia, baixe as atualizações de firmware necessárias. Observação: as atualizações de firmware não podem ser desinstaladas mesmo se você decidir sair do programa Windows Insider.

## Preparar o Surface Hub

Antes de começar, verifique se o Surface Hub tem as atualizações mais recentes do Windows Update e lembre-se de salvar a chave do BitLocker associada ao seu dispositivo.

**Para verificar atualizações manualmente:**

1. Em Surface Hub, abra **configurações** e insira suas credenciais de administrador quando solicitado.
2. Navegue até **Atualizar &**  >  **atualização do Windows** Security e, em seguida, selecione **verificar se há atualizações**.

Para obter mais informações, consulte [gerenciar atualizações do Windows em Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).

**Para salvar manualmente a chave do BitLocker:**

1. Insira uma unidade USB no Surface Hub.
2. Em Surface Hub, abra **configurações** e insira suas credenciais de administrador quando solicitado.
3. Navegue até **Atualizar &**  >  **recuperação**de segurança.
4. Em **BitLocker**, selecione **salvar**. A chave do BitLocker é salva em um arquivo de texto na unidade USB.

Para obter mais informações, consulte [salvar a chave do seu BitLocker](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).
 
## Instalar o Windows 10 Team 2020 Update Preview Build

1. Em Surface Hub, abra **configurações** e insira suas credenciais de administrador quando solicitado.
2. Navegue até **privacidade > diagnóstico & comentários** e defina dados de diagnóstico como **completo**. Algumas regiões ou organizações podem precisar aplicar essa configuração pela política do MDM ou pelo arquivo PPKG:
   - **Para MDM:** Defina a seguinte política:. **/Vendor/MSFT/Policy/System/AllowTelemetry** com o valor inteiro de 3:
    
        ![Definir AllowTelemetry como 3](images/hub-2020-allow-telemetry.png)

    - **Para PPKG:** Baixe o [arquivo PPKG](https://aka.ms/HubTltmtry).

3. Navegue até **Atualizar &** programa de segurança do  >  **Windows Insider** e selecione **introdução** ao cadastrar.
4. Siga os prompts para se registrar como um Windows Insider usando sua conta corporativa (recomendado) ou sua conta pessoal da Microsoft. Para obter detalhes sobre as vantagens de se registrar na sua conta corporativa, consulte [cadastrar-se para o programa Windows Insider para empresas](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
5. Em **escolha suas configurações do insider**, selecione **rápido**.
6. Permita que o Surface Hub instale automaticamente a compilação prévia e as atualizações de firmware necessárias durante os próximos 3 a 4 dias. O dispositivo irá baixar e instalar automaticamente as atualizações durante as [janelas de manutenção](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)diárias. Por exemplo:

- Durante a primeira janela de manutenção, o Surface Hub começa a baixar a versão prévia do Windows Update.
- Durante uma segunda janela de manutenção, o dispositivo é reiniciado para concluir a atualização.
- Durante uma terceira janela de manutenção, o dispositivo baixa e instala as atualizações de firmware necessárias.

> [!IMPORTANT]
> A Microsoft recomenda reservar o Surface Hub por 3-4 dias para permitir que o dispositivo conclua a instalação da compilação prévia e as atualizações de firmware necessárias. Você pode enfrentar problemas com elementos gráficos, áudio e interface do usuário se usar o dispositivo durante esse processo.

### Se você optar por instalar manualmente a compilação prévia e atualizações de firmware necessárias:

1. Depois de cadastrar-se com o programa Windows Insider, vá para **configurações**  >  **Update & Security**  >  **Windows Update** e selecione **verificar se há atualizações** para instalar a versão prévia.
2. Após a instalação da versão preview (pode levar até 14 horas), selecione **reiniciar agora** para concluir a instalação.
3. Depois que o dispositivo for reiniciado, vá para **configurações**  >  **Atualizar &**  >  **atualização do Windows**Security e selecione **verificar se há atualizações para instalar as atualizações de firmware necessárias**.
4. Após a instalação do firmware, selecione **reiniciar agora**.

> [!WARNING]
> Você pode ver problemas de elementos gráficos, áudio e interface do usuário se instalar a versão prévia sem instalar as atualizações de firmware necessárias.

> [!NOTE]
> Se optar por sair do programa Windows Insider e reverter o Surface Hub para uma versão mais antiga do sistema operacional, você deve primeiro [redefinir seu dispositivo](https://docs.microsoft.com/surface-hub/device-reset-surface-hub). Depois disso, você precisará usar o [primeiro programa de execução](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) para reconfigurar seu dispositivo.
 

## Saiba mais

- [Problemas conhecidos: atualização para o Windows 10 Team 2020](surface-hub-2020-team-update-known-issues.md)
- [Nova atualização do sistema operacional do Surface Hub liberada para visualização pública.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Introdução ao Programa Windows Insider para Empresas](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)