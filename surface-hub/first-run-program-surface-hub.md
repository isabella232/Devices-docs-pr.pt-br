---
title: Programa de primeira execução (Surface Hub)
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
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: af6f6cc71a94d075341637499fe98f8206157e49
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576571"
---
# <a name="first-run-program-surface-hub"></a>Programa de primeira execução (Surface Hub)


O termo "primeira execução" se refere a uma série de etapas que você vai executar na primeira vez que ligar o Microsoft Surface Hub e significa o mesmo que "configuração inicial pelo usuário" (OOBE). Esta seção guiará você no processo.

Agora, você já deve ter passado por todas as etapas anteriores:

-   [Preparar o ambiente para o Surface Hub](prepare-your-environment-for-surface-hub.md)
-   [Instalar fisicamente seu dispositivo do Surface Hub](physically-install-your-surface-hub-device.md), e
-   [Planilha de instalação](setup-worksheet-surface-hub.md)

Pressupondo que é o caso, a primeira execução deve ser simples e rápida.
O procedimento normal passa por seis etapas:

1.  [Página "Olá"](#first-page)
2.  [Configurar sua página](#set-up-for-you)
3.  [Página da conta do dispositivo](#device-account)
4.  [Página Nomear este dispositivo](#name-this-device)
5.  [Configure administradores para esta página do dispositivo](#setup-admins)
6.  [Atualizar o Surface Hub](#update-surface-hub)

Cada uma dessas seções também contém informações sobre os caminhos que podem ser tomadas quando algo for diferente. Por exemplo, a maioria dos Surface Hubs usarão uma conexão de rede com fio, mas alguns deles serão configurados em uma conexão sem fio. Os detalhes são descritos onde apropriado.

>[!NOTE]
>Você deve ter o teclado separado que veio com seu Surface Hub configurado e pronto antes de começar. Veja o guia de instalação do Surface Hub para obter detalhes.

 

## <a name="hi-there-page"></a><a href="" id="first-page"></a>Página "Olá"


Esta é a primeira tela que será exibida quando você ligar o Surface Hub pela primeira vez. É onde você digita as informações de localização no seu dispositivo.

>[!NOTE]
>Isso também é onde você começar o processo de implementação de um pacote de provisionamento opcional. Consulte [Criar pacotes de provisionamento](provisioning-packages-for-certificates-surface-hub.md) se for isso que você estiver fazendo.

 Selecione um idioma e as opções de instalação inicial serão exibidas.

![Imagem mostrando a lista de verificação das opções do ICD.](images/setuplocale.png)

### <a name="details"></a>Detalhes

Se os valores padrão mostrados estiverem corretos, você poderá clicar em **Avançar** para continuar. Caso contrário, você precisará inserir dados nas caixas apropriadas.

-   **País/região:** selecione o país ou região onde o Surface Hub será usado.
-   **Idioma do aplicativo:** aplicativos e recursos serão exibidos nesse idioma e formato.
-   **Layout do teclado:** selecione o layout do teclado para os teclados virtual e físico que serão usados no seu dispositivo.
-   **Fuso horário:** selecione o fuso horário em que o Surface Hub será usado.

### <a name="what-happens"></a>O que ocorre?

>[!NOTE]
> Depois que as configurações nesta página são inseridas, você não poderá voltar a essa tela, a menos que você redefina o dispositivo (veja [Redefinir dispositivo](device-reset-surface-hub.md)). Certifique-se de que as configurações estão definidas corretamente antes de prosseguir.

 

Quando as configurações são aceitas, o dispositivo ir procurar por uma conexão de rede com fio. Se a conexão for estabelecida, ele exibirá a [página Configurar sua página](#set-up-for-you). Se houver um problema com a conexão com fio, o dispositivo exibirá a [página Configuração de rede](#network-setup).

Se nenhuma conexão com fio puder ser encontrada, então o dispositivo tentará configurar uma conexão sem fio e exibirá a [página Configuração de rede](#network-setup).

## <a name="network-setup-page"></a><a href="" id="network-setup"></a>página Configuração de rede


Se o seu dispositivo não detectar uma conexão com fio que possa ser usada para se conectar a uma rede ou à Internet, você verá esta página. Aqui você pode se conectar a uma rede sem fio ou ignorar o processo de conexão de rede.

![Imagem mostrando a página Configuração de rede.](images/setupnetworksetup-1.png)

### <a name="details"></a>Detalhes

Essa tela é mostrada somente se o dispositivo falhar ao detectar uma rede com fio. Se você vir essa tela, você tem três opções:

-   Você pode selecionar uma das redes sem fio mostradas. Se a rede estiver protegida, você será levado a uma página de logon. Consulte [Configuração de rede sem fio](#wireless) para obter detalhes.
-   Clique em **Ignorar esta etapa** para ignorar a conexão a uma rede. Você será levado para a [página Configurar sua página](#set-up-for-you).
    >[!NOTE]
    >Se você ignorar isso, o dispositivo não terá uma conexão de rede e nada que requer uma conexão de rede funcionará no seu Surface Hub, incluindo as atualizações do sistema e sincronização de email e calendário. Você pode se conectar a uma rede sem fio posteriormente usando Configurações (consulte [Gerenciamento de rede sem fio](wireless-network-management-for-surface-hub.md)).

     

-   Você pode conectar um cabo de rede enquanto essa tela está visível. O dispositivo irá detectá-lo e adicionará **Próximo** na tela. Clique em **Próximo** para continuar a fazer a conexão com fio.

### <a name="what-happens"></a>O que ocorre?

Se o dispositivo tiver uma conexão com fio quando ele for iniciado e puder estabelecer uma conexão de Internet ou de rede, essa página não será exibida. Se você deseja conectar o dispositivo a uma conexão sem fio, verifique se nenhum cabo Ethernet está conectado na primeira execução, o que levará você para essa tela. Não importa como você escolha configurar agora, você pode [usar as Configurações](wireless-network-management-for-surface-hub.md) para configurar diferentes conexões mais tarde.

Se você deseja se conectar a uma rede sem fio protegida dessa página, clique na rede de sua preferência e forneça as informações necessárias (credenciais de senha ou conta) para se conectar. Consulte [Configuração de rede sem fio](#wireless).

## <a name="wireless-network-setup"></a><a href="" id="wireless"></a>Configuração de rede sem fio


Esta página será mostrada quando você selecionar uma rede sem fio protegida.

![Imagem mostrando a página de configuração de rede sem fio.](images/setupnetworksetup-3.png)

### <a name="details"></a>Detalhes

-   **Nome de usuário:** insira o nome de usuário para a rede sem fio selecionada.
-   **Senha:** esta é a senha para a rede.

### <a name="what-happens"></a>O que ocorre?

O dispositivo tentará se conectar à rede especificada. Se ele conseguir, você será levado para a [página Configurar sua página](#set-up-for-you).

## <a name="network-proxy-setup"></a><a href="" id="proxy"></a>Configuração de proxy de rede


Esta página será mostrada quando o dispositivo detectar uma conexão com fio com conectividade limitada. Você tem três opções:

-   Você pode selecionar uma rede sem fio para usar ao invés da conexão com fio limitada.

-   Você pode ignorar a conexão a uma rede selecionando **Ignorar esta etapa**. Você será levado para a [página Configurar sua página](#set-up-for-you).

    > [!NOTE]
    > Se você ignorar isso, o dispositivo não terá uma conexão de rede e nada que requer uma conexão de rede funcionará no seu Surface Hub, incluindo sincronização de email e calendário. Você pode se conectar a uma rede sem fio posteriormente usando Configurações (consulte [Gerenciamento de rede sem fio](wireless-network-management-for-surface-hub.md)).

-   Você pode selecionar **Inserir configurações de proxy**, que permitirá especificar como usar o proxy de rede. Você será levado para a próxima tela.

    ![Imagem mostrando a página de proxy de rede.](images/setupnetworksetup-2.png)

    Esta é a tela que você verá se tiver clicado em **Inserir configurações de proxy** na tela anterior.

    ![Imagem mostrando detalhes de ajuste do sensor proxy.](images/setupnetworksetup-4.png)

### <a name="details"></a>Detalhes

Para fazer uma conexão de rede, você precisará preencher o nome do script ou sensor proxy e porta.

-   **Script de proxy:** forneça o endereço de um script de proxy.
-   **Sensor proxy e porta:** você pode fornecer o endereço do sensor proxy e a porta.

### <a name="what-happens"></a>O que ocorre?

Quando você clica em **Próximo**, o dispositivo tentará se conectar ao servidor proxy. Se ele conseguir, você será levado para a [página Configurar sua página](#set-up-for-you).

Você pode ignorar a conexão a uma rede selecionando **Ignorar esta etapa**. Você será levado para a [página Configurar sua página](#set-up-for-you).

>[!NOTE]
>Se você ignorar isso, o dispositivo não terá uma conexão de rede e nada que requer uma conexão de rede funcionará no seu Surface Hub, incluindo sincronização de email e calendário. Você pode se conectar a uma rede sem fio posteriormente usando Configurações (consulte [Gerenciamento de rede sem fio](wireless-network-management-for-surface-hub.md)).

 

## <a name="set-up-for-you-page"></a><a href="" id="set-up-for-you"></a>Configurar sua página


Essa tela é meramente informativa e mostra quais ajustes recomendados foram habilitados por padrão.

![Imagem mostrando a configuração da sua página.](images/setupsetupforyou.png)

### <a name="details"></a>Detalhes

Você deve ler esta tela e observar quais serviços foram habilitados por padrão. Todos eles podem ser alterados usando o aplicativo Configurações se necessário, mas você deve ter cuidado com os efeitos dessa ação. Consulte a [Introdução ao Surface Hub](intro-to-surface-hub.md) para obter detalhes.

Ao terminar a revisão dos ajustes, clique em **Avançar** para continuar.

### <a name="what-happens"></a>O que ocorre?

As configurações mostradas na página já foram feitas e não podem ser alteradas até a primeira execução ser completada.

## <a name="device-account-page"></a><a href="" id="device-account"></a>Página da conta do dispositivo


Nessa página, o Surface Hub solicitará as credenciais da conta do dispositivo que você configurou anteriormente. (Consulte [Criar e testar uma conta de dispositivo](create-and-test-a-device-account-surface-hub.md).) O Surface Hub tentará descobrir várias propriedades da conta e poderá solicitar mais informações em outra página, se ele não tiver êxito.

>[!NOTE]
>Esta seção não cobre erros específicos que podem ocorrer durante a primeira execução. Consulte [Solucionar problemas do Surface Hub](troubleshoot-surface-hub.md) para obter mais informações sobre erros.


![Imagem mostrando a página Inserir informações da conta do dispositivo.](images/setupdeviceacct.png)

### <a name="details"></a>Detalhes

Use um **nome UPN** ou um **domínio\\nome de usuário** como o identificador da conta no primeiro campo de entrada. Use o formato que corresponde ao seu ambiente e digite a senha.


|                      Ambiente                      | Formato exigido para a conta de dispositivo |
|-------------------------------------------------------|------------------------------------|
|         A conta de dispositivo é hospedada somente online.         |        nomedousuário@domínio.com         |
|        A conta de dispositivo é hospedada somente no local.         |          DOMÍNIO\nomedousuário           |
| A conta de dispositivo é hospedada online e no local (híbrida). |          DOMÍNIO\nomedousuário           |

Clique em **Ignorar a configuração de uma conta do dispositivo** para ignorar a configuração de uma conta do dispositivo. No entanto, se você não definir uma conta do dispositivo, o dispositivo não será totalmente integrado à sua infraestrutura. Por exemplo, as pessoas não poderão:

-   Ver um calendário de reunião na tela de boas-vindas
-   Iniciar uma reunião a partir da tela de boas-vindas
-   Enviar quadros de comunicações por e-mail pelo OneNote
-   Usar o Skype for Business para fazer reuniões

Se você ignorar a configuração agora, você poderá adicionar uma conta do dispositivo depois usando o aplicativo Configurações.

Se você clicar em **Ignorar a configuração de uma conta do dispositivo**, o dispositivo exibirá uma caixa de diálogo mostrando o que acontecerá se o dispositivo não tiver uma conta do dispositivo. Se você escolher **Ignorar etapa**, você será enviado para a [página Nomear este dispositivo](#name-this-device).

![A imagem mostrando a mensagem é exibida para confirmar se você deseja ignorar a criação de uma conta de dispositivo.](images/setupskipdeviceacct.png)

### <a name="what-happens"></a>O que ocorre?

O dispositivo usará o nome UPN ou DOMÍNIO\\Nome de usuário e senha da conta do dispositivo para fazer o seguinte:

-   Verifique se a conta existe no Active Directory (AD) ou no Active Directory do Azure (Azure AD):

    -   Se um UPN tiver sido inserido: o dispositivo procurará a conta no Azure AD.
    -   Se um DOMÍNIO\\Nome de usuário tiver sido inserido: o dispositivo procurará a conta no AD.
-   Procure o servidor do Microsoft Exchange para a caixa de correio da conta.
-   Procure o endereço Session Initiation Protocol (SIP) para a conta.
-   Puxe os atributos de nome e alias de exibição da conta.

## <a name="exchange-server-page"></a><a href="" id="exchange-server"></a>Página do servidor do Exchange


Essa página será mostrada somente se houver um problema. Normalmente, isso significa que a conta do dispositivo que você forneceu foi encontrada no Active Directory (AD) ou no Azure Active Directory (Azure AD), mas o servidor Exchange da conta não foi detectado.

![Imagem mostrando a página do servidor Exchange.](images/setupexchangeserver-01.png)

### <a name="details"></a>Detalhes

Insira o nome do servidor Exchange em que a caixa de correio da conta do dispositivo está hospedada.

Clique em **Ignorar a configuração dos serviços do Exchange** para pular esta etapa. Se você fizer isso, as pessoas não poderão:

-   Ver um calendário de reunião na tela de boas-vindas.
-   Iniciar uma reunião a partir da tela de boas-vindas.
-   Enviar quadros de comunicações por e-mail pelo OneNote.

Consulte a [Introdução ao Surface Hub](intro-to-surface-hub.md) para obter detalhes sobre as dependências de configuração.

Você pode habilitar os serviços do Exchange para uma conta do dispositivo mais tarde usando o aplicativo Configurações.

Se você clicar em **Ignorar a configuração dos serviços do Exchange**, o dispositivo exibirá uma caixa de diálogo mostrando o que vai acontecer. Se você escolher **Ignorar etapa**, os serviços do Exchange não serão configurados.

![Imagem mostrando a mensagem de confirmação que é exibida quando você ignora a configuração dos serviços do Exchange.](images/setupexchangeserver-02.png)

### <a name="what-happens"></a>O que ocorre?

O Surface Hub tentará validar a conta do dispositivo no servidor do Exchange que você inserir aqui. Se o servidor do Exchange pode ser acessado e validado, a primeira execução prosseguirá.

Se você optar por ignorar a configuração dos serviços do Exchange, o Surface Hub irá parar de procurar pelo servidor do Exchange, e nenhum serviço do Exchange (email e calendário) serão habilitados.

## <a name="exchange-policies-page"></a><a href="" id="exchange-policies"></a>Página de políticas do Exchange


Esta página será mostrada quando:

-   A conta do dispositivo está usando uma política do Exchange Active Sync (EAS) onde a política PasswordEnabled é definida como 1.
-   Não há nenhuma conexão com o Exchange.
-   Exchange retorna um código de status indicando um erro. (Por exemplo: a conta foi provisionada para muitos dispositivos.)
-   Os protocolos suportados pelo Exchange não são aceitos pelo Surface Hub.
-   O Exchange retorna o XML incorreto.

![Imagem mostrando a página de políticas do Exchange.](images/setupexchangepolicies.png)

### <a name="details"></a>Detalhes

Esta página é meramente informativa, portanto, nenhuma entrada é necessária. No entanto, você tem duas opções para prosseguir: ignorando ou repetindo a validação que causou o erro. Antes de decidir qual opção é a melhor, leia a seguinte seção **O que acontece?** . Você poderá corrigir o problema em outro lugar, antes de você clicar em uma das opções.

-   **Clique aqui para continuar usando políticas sem suporte**: clique para continuar a primeira execução. O Surface Hub não poderá usar os serviços do Exchange ou de sincronizar.
-   **Repetir**: verifique novamente a política do servidor Exchange.

### <a name="what-happens"></a>O que ocorre?

O Surface Hub verifica se a política EAS da conta do dispositivo tem a política PasswordEnabled definida como 0 (False). Se esse não for o caso, o email e calendário não podem ser sincronizados e o Surface Hub não pode usar os serviços do Exchange. Você pode usar suas ferramentas de gerenciamento do Exchange em um computador para verificar que a conta do dispositivo tem a política PasswordEnabled definida como 0. Se esse não for o caso, você pode configurar novamente a conta e clicar em **Tentar novamente** aqui.

Se a política já foi configurada corretamente, verifique se seu dispositivo está conectado corretamente à rede ou na Internet e pode acessar o servidor do Exchange, pois essa página também será mostrada se o Surface Hub não conseguir acessar o servidor do Exchange.

Outro motivo possível de não conseguir acessar o Exchange é devido a autenticação baseada em certificado. Você pode acabar nesta página devido a problemas de certificado. Observe que se o dispositivo exibe os códigos de erro 0x80072F0D ou0X800C0019, em seguida, é necessário um certificado. Devido ao provisionamento ser feito na primeira página do processo de primeira execução, desabilite os serviços do Exchange, clicando em **Clique aqui para continuar a usar políticas sem suporte**e depois instale os certificados corretos por meio do aplicativo Configurações.

Se você optar por ignorar essa verificação, o Surface Hub parará de procurar pelo servidor do Exchange e de validar as políticas EAS e nenhum serviço do Exchange será habilitado. Consulte a [Introdução ao Surface Hub](intro-to-surface-hub.md) para obter detalhes sobre as dependências de configuração.

## <a name="name-this-device-page"></a><a href="" id="name-this-device"></a>Página Nomear este dispositivo


Esta página solicita que você forneça dois nomes que serão usados para identificar o Surface Hub.

![Imagem mostrando a página Nomear este dispositivo.](images/setupnamedevice.png)

### <a name="details"></a>Detalhes

Se os valores padrão mostrados estiverem corretos, você poderá clicar em **Avançar** para continuar. Caso contrário, insira os dados em uma ou ambas as caixas de texto.

-   **Nome amigável:** esse é o nome que as pessoas verão quando desejarem estabelecer uma conexão sem fio com o Surface Hub.
-   **Nome do dispositivo:** pode ser definido como qualquer nome exclusivo conforme descrito na tela.

Desde que os dois nomes estejam dentro dos requisitos de tamanho e não usem caracteres restritos, clicar em **Próximo** levará você para a próxima página, [Configurar administradores para este dispositivo](#setup-admins).

### <a name="what-happens"></a>O que ocorre?

O Surface Hub requer dois nomes para o dispositivo, que terão como padrão:

-   **Nome amigável:** assume como padrão o Nome de exibição da conta do dispositivo
-   **Nome do dispositivo:** assume como padrão o alias da conta do dispositivo

Embora qualquer um dos nomes possam ser alterados posteriormente, tenha em mente que:

-   O nome amigável deve ser reconhecível e diferente para que as pessoas possam distinguir um Surface Hub de outro ao tentar se conectar sem fio.
-   Se você optar por ingressar no domínio do dispositivo, o nome do dispositivo não deve ser igual a de qualquer outro dispositivo no domínio do Active Directory da conta. O dispositivo não pode ingressar no domínio se estiver usando o mesmo nome de outro dispositivo do domínio.

>[!NOTE]
>Se você quiser habilitar [Miracast sobre infraestrutura](miracast-over-infrastructure.md), o nome do dispositivo precisa ser detectável por meio de DNS. Você pode conseguir isso permitindo que o Surface Hub registre automaticamente por meio do DNS dinâmico, ou criando manualmente um registro A ou AAAA para o nome do dispositivo do Surface Hub.

## <a name="set-up-admins-for-this-device-page"></a><a href="" id="setup-admins"></a>Configure administradores para esta página do dispositivo


Nessa página, você deverá escolher entre várias opções de como deseja configurar contas de administrador para gerenciar seu dispositivo localmente.

Como cada Surface Hub pode ser usado por qualquer número de funcionários autenticados, as configurações são bloqueadas para que eles não possam alterar a cada sessão. Apenas os administradores podem definir as configurações no dispositivo e nesta página, você poderá escolher quais tipos de administradores têm esse privilégio.

>[!NOTE]
>A finalidade desta página é principalmente determinar quem pode configurar o dispositivo pela interface do usuário do dispositivo. Ou seja, quem pode realmente visitar um dispositivo, fazer logon, abrir o aplicativo Configurações e alterar as Configurações.

 

![Imagem mostrando a página Configurar administradores para este dispositivo.](images/setupsetupadmins.png)

### <a name="details"></a>Detalhes

Escolha uma das três opções disponíveis:

-   **Usar o Microsoft Azure Active Directory**
-   **Usar os Serviços de Domínio do Active Directory**
-   **Usar um administrador local**

### <a name="what-happens"></a>O que ocorre?

Isso é o que acontece quando você escolhe uma opção.

-   **Usar o Microsoft Azure Active Directory**

    Clicar nessa opção permite que você ingresse o dispositivo no Azure AD. Depois que você clicar em **Próximo**, o dispositivo será reiniciado para aplicar algumas configurações e, em seguida, você será levado para a página [Usar o Microsoft Azure Active Directory](#use-microsoft-azure) e será solicitado que digite as credenciais que podem permitir que você participe do Azure AD. Membros da função Administradores Globais do Azure da organização ingressada poderão usar o Configurações app. As pessoas específicas que poderão utilizar depende de sua assinatura do Azure AD e de como você definiu as configurações da sua organização Azure AD.
    
    > [!IMPORTANT]
    > Para configurar quem pode usar o aplicativo Configurações para administrar Surface Hubs, certifique-se de que o registro automático do [Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) está habilitado em seu locatário antes de ingressar no dispositivo no Azure AD. Em seguida, as políticas do Intune podem ser usadas para [configurar administradores](surface-hub-2s-nonglobal-admin.md) não globais nos Surface Hubs.

-   **Usar o Active Directory Domain Services**

    Clique nesta opção para ingressar o dispositivo ao AD. Depois que você clicar em **Próximo**, você será levado para a página [Use os Serviços de Domínio do Active Directory](#use-active-directory) e será solicitado que digite as credenciais que podem permitir que você participe do domínio especificado. Depois de se inscrever, você pode escolher um grupo de segurança do domínio associado e as pessoas do grupo de segurança poderão usar o aplicativo Configurações.

-   **Use um administrador local**

    Escolher essa opção permitirá que você crie um administrador local único. Este admin não será salvo por qualquer serviço de diretório, portanto, recomendamos que você escolha esse caso somente se o dispositivo não tem acesso ao Azure AD ou AD. Depois que você criar o nome de usuário e senha do administrador na página [Usar um administrador local](#use-a-local-admin) , você terá que inserir novamente as mesmas credenciais sempre que você abrir o aplicativo Configurações.

    Observe que um administrador local deve ter acesso físico ao Surface Hub para fazer logon.

>[!NOTE]
>Depois de concluir esse processo, você não poderá mudar a opção de administração do dispositivo, a menos que você redefina o dispositivo.

 

### <a name="use-microsoft-azure-active-directory"></a><a href="" id="use-microsoft-azure"></a>Usar o Microsoft Azure Active Directory

Se você decidiu associar o seu Surface Hub ao Active Directory do Azure (Azure AD), você verá esta página **O que acontecerá em seguida**. Leia-a e clique em **Próximo** para ir para **Vamos entrar na página**.

Participar do Azure AD tem dois benefícios principais:

1.  Alguns funcionários da sua organização poderão acessar o dispositivo como administradores e poderão iniciar o aplicativo Configurações para configurar o dispositivo. As pessoas que têm permissões de administrador serão definidas na sua assinatura do Azure AD.

2.  Se o Azure AD estiver conectado a uma solução de gerenciamento de dispositivo móvel (MDM), o dispositivo será associado a essa solução do MDM para que você possa aplicar políticas e configuração.

    ![Imagem mostrando mensagem quando você associa o Surface Hub ao Azure Active Directory.](images/setupjoiningazuread-1.png)

### <a name="details"></a>Detalhes

A entrada a seguir é necessária:

-   **UPN do usuário:** o nome UPN de uma conta que pode ingressar no Azure AD.
-   **Senha:** a senha da conta que você está usando para ingressar no Azure AD.

![Imagem mostrando informações de logon da conta.](images/setupjoiningazuread-2.png)

Se você chegar a este ponto e não tiver credenciais válidas para uma conta do Azure AD, o dispositivo permitirá que você continue com a criação de uma conta de administrador local. Clique em **Configurar o Windows com uma conta local em vez disso**.

![Imagem mostrando a página Configurar uma conta de administrador.](images/setupjoiningazuread-3.png)

### <a name="what-happens"></a>O que ocorre?

Depois que você inserir credenciais da conta Azure AD válidas, o dispositivo tentará ingressar na organização do Azure AD associada. Se isso tiver êxito, o dispositivo irá provisionar funcionários na organização para ser administradores locais no dispositivo. Se seu locatário Azure AD foi configurado para ele, o dispositivo também será inscrito no MDM.

### <a name="use-active-directory-domain-services"></a><a href="" id="use-active-directory"></a>Use os Serviços de Domínio do Active Directory

Esta página pedirá as credenciais para ingressar em um domínio para que o Surface Hub possa provisionar um grupo de segurança como administradores do dispositivo.

Depois do dispositivo ter sido ingressado no domínio, você deve especificar um grupo de segurança do domínio que tenha ingressado. Esse grupo de segurança será provisionado como administradores no Surface Hub e qualquer pessoa do grupo de segurança poderá inserir suas credenciais de domínio para acessar as Configurações.

![Imagem mostrando a página Configurar administradores usando ingresso no domínio.](images/setupdomainjoin.png)

### <a name="details"></a>Detalhes

A entrada a seguir é necessária:

-   **Domínio:** esse é o nome de domínio totalmente qualificado (FQDN) do domínio em que você deseja ingressar. Um grupo de segurança do domínio pode ser usado para gerenciar o dispositivo.
-   **Nome de usuário:** o nome de usuário de uma conta que tenha permissão suficiente para ingressar no domínio especificado. 
-   **Senha:** a senha da conta.

Depois que as credenciais forem verificadas, você será solicitado a digitar um nome do grupo de segurança. Essa entrada é obrigatória.

![Imagem mostrando a página Inserir um grupo de segurança.](images/setupsecuritygroup-1.png)

### <a name="what-happens"></a>O que ocorre?

Usando o domínio fornecido, as credenciais de conta da [página Usar os Serviços de Domínio do Active Directory](#use-active-directory) e o nome do dispositivo da página [Nomear esse dispositivo](#name-this-device), o Surface Hub tentará ingressar no domínio. Se a associação é bem-sucedida, a primeira execução continuará e solicitará um grupo de segurança. Se a associação não for bem-sucedida, a primeira execução interromperá e solicitaremos que você alterar as informações fornecidas.

Se a associação for bem-sucedida, você verá a página **Inserir um grupo de segurança** . Quando você clicar no botão **Selecionar** nesta página, o dispositivo irá procurar pelo grupo de segurança especificado no seu domínio. Se localizado, o grupo será verificado. Clique em **Finalizar** para completar o primeiro processo de execução.

>[!NOTE]
>Se o domínio se associar ao Surface Hub, você não poderá sair do dispositivo sem restaurá-lo.

 

### <a name="use-a-local-admin"></a>Use um administrador local

Se decidir não usar o Azure Active Directory (Azure AD) ou Active Directory (AD) para gerenciar o Surface Hub, você precisará criar uma conta de administrador local.

![Imagem mostrando Configurar uma conta de administrador para o administrador local.](images/setuplocaladmin.png)

### <a name="details"></a>Detalhes

A entrada a seguir é necessária:

-   **Nome de usuário:** esse é o nome de usuário da conta de administrador local que será criada para esse Surface Hub.
-   **Senha:** esta é a senha da conta do dispositivo.
-   **Digite novamente a senha:** verificação da senha como na caixa anterior.

### <a name="what-happens"></a>O que ocorre?

Esta página tentará criar uma nova conta de administrador usando as credenciais que você inserir aqui. Se for bem-sucedida, a primeira execução terminará. Caso contrário, você será solicitado a fornecer credenciais diferentes.

## <a name="update-the-surface-hub"></a><a href="" id="update-surface-hub"></a>Atualizar o Surface Hub


>[!IMPORTANT]
>Antes de fazer as atualizações, certifique-se de ler [Salvar sua chave do BitLocker](save-bitlocker-key-surface-hub.md) para certificar-se de que você tem um backup da chave.

 

Para obter os recursos e correções mais recentes, você deve atualizar seu Surface Hub assim que terminar todas as etapas anteriores da primeira execução.

1.  Certifique-se de que o dispositivo tenha acesso aos servidores Windows Update. 
2.  Abra as Configurações, clique em **Atualização e segurança** e, em seguida, em **Windows Update**. Clique em **Verificar se há atualizações**.
3.  Se houver atualizações disponíveis, elas serão baixadas. Depois que o download for concluído, clique no botão **Atualizar agora** para instalar as atualizações.
4.  Siga os avisos na tela depois que as atualizações forem instaladas. Talvez seja necessário reiniciar o dispositivo.

 

 





