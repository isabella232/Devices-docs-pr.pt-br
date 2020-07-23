---
title: Instalar o Windows 10 Team 2020 Update Preview Build
description: A atualização mais recente do sistema operacional do Surface Hub, atualização do 2020 do Windows 10 Team, já está disponível.
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894107"
---
# Instalar o Windows 10 Team 2020 Update Preview Build 

A atualização mais recente do sistema operacional do Surface Hub, **atualização do 2020 do Windows 10 Team**, agora está disponível sem custo adicional para os dispositivos Hub de Surface 50-Inch e Surface hub 2s 55-inch do [programa Windows Insider](https://insider.windows.com). O modelo Surface Hub 84-inch será compatível na versão final da atualização do Windows 10 Team 2020.

A atualização do Windows 10 Team 2020 traz grandes melhorias para a implantação e a capacidade de gerenciamento de dispositivos, juntamente com os recursos mais recentes do Windows 10. Para saber mais sobre as novidades, confira a postagem de blog a seguir: [nova atualização do sistema operacional do Surface Hub lançada para visualização pública.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) Para problemas conhecidos, confira a seção "problemas conhecidos" abaixo.
 
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
2. Navegue até **Atualizar &**  >  **programa do Windows Insider** Security e escolha **introdução**.
3. Siga os prompts para se registrar como um Windows Insider usando sua conta corporativa (recomendado) ou sua conta pessoal da Microsoft. Para obter detalhes sobre as vantagens de se registrar na sua conta corporativa, consulte [cadastrar-se para o programa Windows Insider para empresas](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
4. Em **escolha suas configurações do insider**, selecione **rápido**.
5. Permita que o Surface Hub instale automaticamente a compilação prévia e as atualizações de firmware necessárias durante os próximos 3 a 4 dias. O dispositivo irá baixar e instalar automaticamente as atualizações durante as [janelas de manutenção](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)diárias. Por exemplo:

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
 
## Problemas conhecidos: versão prévia da atualização do Windows 10 Team 2020

### Problemas de elementos gráficos, áudio e interface do usuário 

Você pode enfrentar vários problemas de interface do usuário e elementos gráficos se instalar a versão prévia, mas não instale imediatamente as atualizações de firmware necessárias posteriormente. A Microsoft planeja corrigir esses problemas na versão Build da atualização do Windows 10 Team 2020.

### Surface Hub 84-polegada: problemas de interface do usuário e elementos gráficos

Você pode enfrentar vários problemas de interface do usuário e elementos gráficos se instalar a versão prévia em um dispositivo 84-polegada Surface Hub de primeira geração. O Surface Hub 84-inch será compatível na versão final da atualização do Windows 10 Team 2020.

### A conexão é afetada quando as políticas de acesso condicional são aplicadas

- A conexão falha ao tentar entrar em aplicativos como o Microsoft whiteboard. Os usuários devem entrar primeiro em [minhas reuniões e arquivos](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) no menu iniciar.

- Entrar falha se sua conta de usuário estiver registrada em um locatário do Azure AD diferente do usado pelo Surface Hub para ingressar no Azure AD.

A Microsoft planeja corrigir esses problemas na versão Build da atualização do Windows 10 Team 2020.

### O Windows Update solicita a instalação de novos drivers quando nenhum estiver disponível

Ao acessar **as configurações**  >  **Update & Security**  >  **Windows Update** após instalar a atualização do Windows 10 Team 2020 e as atualizações de firmware necessárias, você poderá ver o seguinte erro: 

- "Um driver atual em seu computador pode ser melhor do que o driver que estamos tentando instalar. Continuaremos tentando instalar. " 

Este erro pode ser ignorado com segurança. A Microsoft está investigando ativamente esse problema.

### Não é possível instalar políticas do Surface Hub usando pacotes de provisionamento

Os pacotes de provisionamento que usam políticas do provedor de serviços de configuração do Surface Hub (CSP) falham ao instalar. Por enquanto, use o Microsoft Intune ou outro provedor de gerenciamento de dispositivos móveis (MDM) para aplicar as políticas do Surface Hub. A Microsoft planeja corrigir esse problema na versão Build da atualização do Windows 10 Team 2020.

### Solicitação para remover unidade USB prematuramente durante a primeira execução

Ao usar um pacote de provisionamento para configurar o Surface Hub durante a primeira execução, você será solicitado a remover a unidade USB antes que o dispositivo possa ler o arquivo de configuração do Surface Hub. Ignore a mensagem se você estiver usando um arquivo de configuração para configurar sua conta de dispositivo. A Microsoft está investigando ativamente esse problema.
 
### Não é possível definir as configurações de proxy durante a primeira execução

Se você usar um proxy para se conectar à Internet, talvez tenha limitado a conectividade com a Internet durante o primeiro programa de execução. A Microsoft planeja corrigir esse problema na versão Build da atualização do Windows 10 Team 2020.
 
### Um erro é exibido quando você baixa os aplicativos da Microsoft Store

Para baixar um aplicativo da Microsoft Store, será exibida uma solicitação para entrar. Um problema conhecido faz com que um erro seja exibido durante a entrada, mas isso não afeta sua capacidade de baixar aplicativos. A Microsoft está investigando ativamente esse problema.

### Hub Surface 2S perde a conexão Wi-Fi intermitentemente

Tente desconectar seu dispositivo e conectá-lo novamente ou usando um cabo Ethernet para se conectar à Internet. A Microsoft está investigando ativamente esse problema.

### Hub de Surface 2S falha continuamente ao sair do estado de suspensão

O Surface Hub 2S pode falhar intermitentemente ao sair do estado de suspensão e parecer parar de responder em uma tela mostrando o logotipo da Microsoft. Tente desconectar seu dispositivo e conectá-lo novamente. 

Para evitar esse problema:

1. Em Surface Hub, abra **configurações** e insira suas credenciais de administrador quando solicitado.
2. Navegue até sessão do **Surface Hub**  >  **& energia**. 
3. Em **quando o dispositivo vai para o estado de suspensão, use esta configuração de energia**, selecione **standby conectado.**
4. Em **quando não houver uma pessoa, coloque o dispositivo em suspensão após**, selecione **nunca.**

A Microsoft planeja corrigir esse problema em uma atualização de firmware antes da versão final da atualização do Windows 10 Team 2020.

### Problemas de projeção quando o aplicativo de conexão não está no modo de exibição

- Quando você usa um cabo para projetar no Surface Hub, o touchback para de funcionar se você navegar para fora do aplicativo conectar.
- Quando você projetar no Surface Hub usando o Miracast, a conexão sem fio cai logo depois de sair do aplicativo Connect.

A Microsoft está investigando ativamente esses problemas.

### O Skype for Business não está usando proxy para tráfego de mídia

Para alguns dispositivos que usam um proxy, o Skype for Business pode entrar, mas não usará o servidor proxy para tráfego de mídia. A Microsoft está investigando ativamente esse problema.

Convidamos você para compartilhar suas ideias e sugestões com o suporte da Microsoft.

## Saiba mais

- [Nova atualização do sistema operacional do Surface Hub liberada para visualização pública.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Introdução ao Programa Windows Insider para Empresas](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)