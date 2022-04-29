---
title: Configurar Windows 10/11 Pro ou Enterprise no Surface Hub 2
description: Este artigo inclui recomendações para garantir a melhor experiência ao usar um computador com toque de tela grande e caneta personalizado.
keywords: Surface Hub, Windows 10, desktop, instalação, configuração
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
ms.openlocfilehash: 2b645ef580eda85a91bf282c8772c42c09cbb67d
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497764"
---
# <a name="configure-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>Configurar Windows 10/11 Pro ou Enterprise no Surface Hub 2

Depois de migrar para o Windows 10/11 Pro ou Enterprise, você pode definir aplicativos e configurações para garantir a melhor experiência usando esse computador de tela grande e caneta personalizado.

Ao executar essas etapas, você pode achar útil usar um teclado com ou sem fio e mouse.

## <a name="configure-system-settings"></a>Definir configurações do sistema

1. Entre com uma conta que tenha privilégios de administrador local no dispositivo.  

    - O usuário que executa o Azure AD em Azure AD ingressados é adicionado automaticamente ao grupo de administradores local.  Azure AD administradores globais e Azure AD de dispositivos também <a href="/azure/active-directory/devices/assign-local-admin" target="_blank">são administradores locais</a>. 

    - Você pode digitar **administradores net localgroup em** um prompt de comando para listar as contas que têm direitos de administrador local.
    
2. Renomeie o dispositivo usando um nome amigável, por exemplo, **username-SHub-Desktop**.

3. Selecione **Iniciar** >  **Configurações** >  **AccountsSync** >  **suas configurações** e desative **as configurações de sincronização**. 

    - As configurações usadas aqui destinam-se a habilitar a melhor experiência de toque em tela grande e, portanto, talvez você não queira sincronizar outros dispositivos.
    
4. Reinicie o dispositivo.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>Habilitar o teclado virtual e o touchpad

1. Selecione **Iniciar** >  **Configurações** >  **DevicesTyping** >  e ative Mostrar o teclado virtual quando não estiver no modo tablet e não **houver teclado anexado**.****

2. Toque e segure ou clique com o botão direito do mouse na barra **** de tarefas e selecione o botão Mostrar teclado virtual e **o botão Mostrar touchpad**. 

    - O teclado virtual é útil para entrada direta do usuário, e o touchpad virtual ajuda com seleções precisas, dicas de tela focalizadas ou como uma alternativa para tocar e segurar para clicar com o botão direito do mouse. 
    
    - Veja o exemplo a seguir.

      ![Configurações de toque.](images/touch.png)

3. Configure o teclado virtual para QWERTY e flutuante.

    1. Selecione o **ícone teclado** na barra de tarefas para mostrar o teclado virtual.
    
    1. No teclado virtual, selecione o ícone de teclado no canto superior esquerdo para abrir as configurações do teclado.
    
    1. Selecione o próximo tipo de teclado na linha superior para habilitar o QWERTY e a última opção na segunda linha para habilitar o flutuante, o que é útil nessa tela grande. Consulte os exemplos a seguir.

       ![Configurações do teclado.](images/kbd.png)
 
4. Defina as configurações de teclado flexível.

    1. Selecione o **Configurações** no teclado virtual ou pesquise e abra **as configurações de Digitação**.
    
       ![configurações de teclado flexível.](images/sh2-softkeyboard.png)

    1. Habilite todas as opções em Ortografia, Digitação e Teclado virtual.


O exemplo a seguir mostra o trackpad, que é útil para navegar e selecionar opções. O teclado na tela está sendo usado para pesquisar o Microsoft Store:

![Usando o trackpad.](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>Configurar Bluetooth teclado e mouse (opcional)

Conexão um teclado e mouse se você usar o dispositivo como seu dispositivo Windows primário, ou você geralmente usá-lo para digitação ou trabalho de precisão.

Se o Surface Hub estiver próximo a um computador, <a href="https://aka.ms/mm" target="_blank"> você poderá usar o Mouse</a> sem Bordas para se mover perfeitamente entre o Surface Hub e o computador. Para obter mais informações, confira <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> o download da Microsoft no The Garage: Mouse sem Bordas. </a>

## <a name="example-of-taskbar-layout"></a>Exemplo de layout da barra de tarefas

Depois de concluir as etapas abaixo para configurar o Surface Hub 2 para Windows 10/11 Pro ou Enterprise, recomendamos que você utilize a fixação de seus aplicativos mais usados na Barra de Tarefas para uma rápida inicialização de um toque de cada aplicativo. Veja abaixo um exemplo da aparência da barra de tarefas:

 ![Layout da barra de tarefas.](images/taskblyt.png)
### <a name="update-installed-apps"></a>Atualizar aplicativos instalados

Para atualizar todos os aplicativos da Store instalados:

1. Abra o Microsoft Store aplicativo e selecione **Ver mais** reticências no canto superior direito.
2. Selecione **Downloads e atualizações.**
3. Selecionar **Obter atualizações**

### <a name="scan-for-and-install-all-windows-updates"></a>Verificar e instalar todas as Windows atualizações

Após a migração, pode haver atualizações de recursos e manutenção disponíveis para instalação. 

- Vá para **Configurações** >  **Atualizar & segurança** > e selecione **Verificar se há atualizações**.
- Se houver atualizações, instale-as, reinicialize e repita o processo até que você veja a seguinte notificação:

> [!div class="mx-imgBorder"]
> ![Windows Update notificação "Você está atualizado".](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive for Business

Use <a href="/onedrive/onedrive" target="_blank"> OneDrive for Business</a> para compartilhar facilmente ferramentas, logs e outros arquivos entre todos os seus dispositivos de trabalho.

- OneDrive permite que você compartilhe seus arquivos de trabalho entre seus laptops, Surface Hub Desktop e seus dispositivos móveis gerenciados Intune aplicativos. Os arquivos podem ser editados em qualquer dispositivo e todos os dispositivos conectados à rede serão atualizados com as alterações.

- Considerando o tamanho do SSD do Surface Hub (128 GB), se você configurar o OneDrive em seu dispositivo de área de trabalho do Surface Hub, verifique se a configuração padrão é manter os arquivos online e baixar arquivos conforme usá-los.

Para configurar OneDrive para baixar arquivos somente quando necessário, defina a configuração Arquivos Sob Demanda como Economizar espaço e baixar arquivos **conforme você os usa**.**** Para obter mais informações, consulte <a href="/onedrive/files-on-demand-windows" target="_blank"> Consultar e definir estados de arquivos sob demanda Windows</a>.

![OneDrive configurações.](images/onedrive.png)

> [!NOTE]
> Você também pode repetir essas etapas para configurar um OneDrive pessoal, mas certifique-se de conservar o espaço da unidade e apenas baixar arquivos conforme necessário.

## <a name="sharepoint-and-teams"></a>SharePoint e Teams

SharePoint e arquivos Teams Channel também podem ser sincronizados localmente com seus dispositivos desktop, como laptops e Surface Hubs, usando o Sincronização do OneDrive.

Para sincronizar arquivos corporativos internos com sua unidade local com o Sincronização do OneDrive aplicativo:

1. Acesse um site SharePoint e navegue até o diretório de documentos de nível superior para arquivos que você está interessado em exibir ou editar do seu dispositivo local.

2. Selecione o botão **Sincronizar** na parte superior da faixa SharePoint opções.

3. Selecione em **Abrir** no pop-up **Este site está tentando abrir Microsoft OneDrive**.

4. Verifique se os SharePoint estão sincronizando com a unidade local selecionando o ícone OneDrive na parte inferior direita da barra de tarefas.

5. Verifique se a configuração está definida para manter os arquivos online e baixe os arquivos somente conforme você os usa:

    1. Abra o explorador de arquivos.
    
    2. Navegue até e clique com o botão direito do SharePoint nome; por exemplo, **Contoso \ \<SharePoint Document Folder Name\>**.
    
    3. Selecione **Liberar espaço**.
    
    4. A coluna Status exibirá o status de arquivos e pastas. Para obter mais informações, consulte <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sincronizar SharePoint arquivos com o Sincronização do OneDrive cliente</a>.
    
6. Teams arquivos de canal são armazenados em sites SharePoint, com a mesma funcionalidade SharePoint documento, incluindo o histórico de versões e a sincronização com seus dispositivos de área de trabalho local. Para sincronizar arquivos Teams Channel:

    1. Navegue até o Teams canal de interesse e selecione **a guia** Arquivos na parte superior. Em seguida, selecione **Sincronizar**. Os arquivos começarão a sincronizar e estarão visíveis no Explorador de Arquivos desktop **\ Contoso \ \<name of the Teams Channel\>**.
    
    2. Use o mesmo procedimento usado para sincronizar sites do SharePoint para manter os arquivos na nuvem e baixá-los somente quando usá-los, toque e segure ou clique com o botão direito do mouse no Explorador de Arquivos no nome do canal do Teams e, em seguida, selecione Liberar **espaço.**

## <a name="surface-hub-pen-settings"></a>Surface Hub de caneta

**Emparelhar a Bluetooth Surface Hub Caneta**

Emparelhe a caneta para manter o firmware da caneta atualizado, defina os atalhos de caneta e obtenha informações sobre a carga da bateria na página Bluetooth configurações do dispositivo ou no aplicativo Surface:

1. Selecione **Start** >  **Configurações** >  **Devices**.

2. Selecione **Adicionar Bluetooth ou outro dispositivo**.

3. Escolha **Bluetooth**.

4. Remova o botão da parte final da caneta e agite para desconectar a conexão da bateria.

5. Coloque a tampa novamente e pressione e segure a tampa até o LED de emparelhamento piscar.

6. Nas configurações Surface Hub Bluetooth, escolha **Surface Hub 2 Caneta**.

7. Conclua a operação de emparelhamento. 

8. Se o emparelhamento não for bem-sucedido, tente emparelhar a caneta novamente. Se isso não funcionar, você poderá testar para ver se a bateria está carregada verificando se a caneta funciona no aplicativo Whiteboard. Caso contrário, substitua a bateria e tente emparelhar a caneta novamente.  Se necessário, reinicie o dispositivo e tente novamente.

**Definir atalhos de caneta** A Surface Hub caneta tem um botão de atalho às vezes chamado de "clique final". Configurar atalhos exige que você primeiro emparelhe a caneta, conforme descrito anteriormente.

1. Pesquise Caneta e selecione **As configurações & Windows Ink caneta**.

2. Próximo à parte inferior da página, selecione Atalhos de caneta que abre a caixa de diálogo, mostrado aqui:

   ![Atalhos de caneta.](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>Configuração da câmera

Você pode montar a câmera na parte superior ou em qualquer lado do dispositivo. Monte a câmera em uma posição para otimizar o ângulo da câmera se você estiver usando o Hub com um suporte da área de trabalho em vez de um carrinho ou estiver perto do Hub. A câmera não gira automaticamente, portanto, você precisa ter uma tecla hexadecimal de 2mm para girar manualmente a câmera. 

Para obter mais informações sobre como montar lateralmente a câmera e girar a câmera manualmente, <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> consulte Surface Hub orientação da lente da câmera</a> 2S.

## <a name="windows-hello-configuration"></a>Windows Hello configuração

Surface Hub 2S executando Windows 10/11 Pro ou Enterprise permite o pacote completo de aplicativos de área de trabalho Win32, bem como opções de Windows Hello biométricas. O Surface Hub acessório leitor de impressão digital 2 pode ser conectado a qualquer porta USB-C no dispositivo. 

Para solicitar um Leitor de Impressão Digital do Surface Hub 2 ou exibir especificações técnicas, consulte (surface-hub-2-essential-add-ons.md" target="_blank"Complementos essenciais do >para Windows 10 Pro e Enterprise no Surface Hub 2</a>. 

Depois de inserir o leitor de impressão digital, selecione **Iniciar** >  **Configurações** >  **DecontasSign-in** > **** >  **Windows Hello impressão digital** para registrar sua impressão digital.

Use um Windows Hello certificado para reconhecimento facial. A Surface Hub 2S não dá suporte Windows Hello reconhecimento facial.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>Habilitar um ícone de atalho de Tela de Bloqueio na barra de tarefas

Para adicionar um ícone à barra de tarefas que habilita um bloqueio de tela de toque semelhante ao atalho de teclado Windows-L: 

1.  Toque e segure ou clique com o botão direito do mouse **na** área de trabalho, selecione NewShortcutBrowseDesktopOKNext**** > .**************** >  >  >  > 

1.  Forneça um nome para o atalho, como **Bloquear meu computador** e, em seguida, selecione **Concluir**.

1.  Clique com o botão direito do mouse ou toque e segure o atalho recém-criado na área de trabalho e selecione **Propriedades**. Na guia **Atalho** , insira o seguinte **no campo Destino** : **Rundll32.exe User32.dll,LockWorkStation**

1.  Selecione o **botão Alterar Ícone** , ** navegue atéC:\Windows\System32\imageres.dll** e selecione um ícone a ser usado. 

    Veja o exemplo a seguir:

    ![Escolha um ícone.](images/lock.png)
    
1.  Selecione **OK** para salvar o atalho.

1.  Clique com o botão direito do mouse ou toque e segure o atalho e selecione **Fixar na barra de tarefas**.

1. Depois de fixar o atalho de bloqueio na barra de tarefas, você pode excluí-lo da área de trabalho.

## <a name="applications"></a>Aplicativos


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

Para instalar o Microsoft Whiteboard:

 - Selecione o **Espaço de Trabalho do Windows Ink** ícone no canto inferior direito da barra de tarefas e baixe **o Whiteboard**.
 
   ![Workspace à tinta.](images/ink.png) 

Como alternativa, você pode instalar o Whiteboard do Microsoft Store:

1. Abra Microsoft Store aplicativo e pesquise **o Whiteboard**.

2. Escolha **Não obrigado** para entrar e usar em todos os dispositivos.

3. Fixe o Quadro de Comunicações na barra de tarefas.

### <a name="surface-app"></a>Aplicativo Surface

1. No Microsoft Store, pesquise o **Surface**.

2. Defina **o filtro Disponível para** Todos **os dispositivos**.

3. Instale o **aplicativo Surface** . Esse deve ser o primeiro aplicativo listado. Talvez seja necessário associar a MSA à Loja para instalar o aplicativo.

4. Fixe o **aplicativo Surface** na barra de tarefas.

### <a name="snip--sketch"></a>Captura e Esboço

1. Abra o **aplicativo Snip & Sketch** e fixe-o na barra de tarefas.

2. Selecione as reticências no canto superior direito e selecione **Configurações**.

3. No **Configurações**, **ative a Cópia** Automática na área de transferência, **salve trechos** e **várias janelas** (opcional).

### <a name="microsoft-office"></a>Microsoft Office

1. Abra o <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> e instale os aplicativos desejados.

2. Fixe os Office aplicativos desejados na barra de tarefas.

3. Se Outlook estiver instalado, certifique-se de definir o Outlook OST para salvar apenas o cache das últimas duas semanas. Isso reduzirá muito o uso do disco e o tempo de instalação.

    - Selecione **FileAccount** **** >  Configurações e selecione sua conta.
    
    - Selecione **Alterar** e defina o controle deslizante **para Usar o Modo Exchange Armazenado em** Cache como 14 dias.

### <a name="microsoft-teams"></a>Microsoft Teams

1. Baixe e instale Microsoft Teams <a href="https://teams.microsoft.com/downloads" target="_blank"> </a>.

2. Defina as configurações para iniciar automaticamente o aplicativo (opcional).

3. Fixe Teams na barra de tarefas.

4. Considere reduzir Teams notificações no dispositivo para evitar distrações (opcionais).

   ![Teams notificações.](images/teams.png)

### <a name="connect-app"></a>Conexão aplicativo

> [!IMPORTANT]
> No Windows 10, versão 2004 e posterior, o aplicativo Conexão para projeção sem fio usando o Miracast não é instalado por padrão, mas está disponível como um recurso opcional. Se você instalou (ou atualizou para) Windows versão 2004 ou posterior, poderá ver o seguinte na tela Projetar para este computador nas configurações:

![Project para este computador.](images/sh2-project.png) 


1. Para instalar o aplicativo na página de configurações "Projetar para este computador", **** >  selecione Recursos opcionaisAdibilize um recurso e instale o aplicativo **De exibição sem** fio.****

2. Em **Alguns Windows e dispositivos Android podem projetar** para este computador quando você diz que está ok, escolha:

    - **Disponível em todos os** lugares se o dispositivo não estiver em uma rede corporativa.
    - Caso contrário, escolha **Disponível em qualquer lugar em redes seguras**.
    
3. Em **Pedir para projetar para este computador**, escolha **somente a primeira vez**.

4. Em **Exigir PIN para emparelhamento**, escolha **Nunca**.

5. Para iniciar o aplicativo e fixá-lo na barra de tarefas, pesquise **Conexão**.

6. Abra o aplicativo. Enquanto o aplicativo estiver aberto, clique com o botão direito do mouse no ícone Conexão aplicativo na barra de tarefas e selecione **fixar na barra de tarefas**.

7. Em seguida, feche o Conexão aplicativo. **Project para este computador pode** não funcionar, a menos que o aplicativo tenha sido executado pelo menos uma vez.

Configuração recomendada quando não estiver na rede corporativa:

![Configurações em casa.](images/project1.png)

Configuração recomendada na rede corporativa:

![Configurações no trabalho.](images/project2.png)

### <a name="your-phone"></a>Seu Telefone

O **aplicativo Telefone** aplicativo é instalado por padrão no Windows 10. Se ele não estiver presente, você também poderá instalá-lo da Windows Store.

Para obter informações sobre como configurar o aplicativo, <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> consulte Como configurar seu Telefone no Windows 10 e sincronizar dados entre seu computador e telefone</a>. Consulte também <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Como corrigir problemas comuns com seu aplicativo Telefone no Windows 10</a>.

###  <a name="fancy-zones"></a>Zonas sofisticadas


**Zonas Sofisticadas** faz parte de uma coleção de ferramentas chamadas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> no GitHub.. É uma ótima maneira de utilizar o estado real da tela em um Surface Hub 2, fornecendo a capacidade de definir layouts fixos em sua exibição ("zonas") e, em seguida, selecionar qual aplicativo será executado em cada zona. 


O [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) tem instruções sobre como usar e personalizar cada ferramenta, incluindo [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). Em um alto nível – depois de instalar o PowerToys, você pode selecionar ou criar um layout personalizado e, em seguida, manter a tecla shift pressionada e arrastar ou usar teclas de teclado para mover um aplicativo em execução para zonas específicas. Usar um Bluetooth ou usb e mouse ajudará com isso, ou você pode usar o teclado virtual e o touchpad na tela.

**Dicas de brinquedos de energia**
- Para receber notificações por email PowerToys atualizações de versão no GitHub, clique no botão "inscrever-se" na parte superior da [página](https://github.com/microsoft/PowerToys/releases).
- Depois PowerToys estiver instalado, você poderá receber notificações do Windows e/ou baixar e instalar as atualizações mais recentes definindo as configurações do PowerToys para as qual baixar atualizações automaticamente****.
- Para acessar as configurações do PowerToys, selecione os aplicativos em execução na barra **** de tarefas e, em seguida, clique com o botão direito do mouse ou pressione e segure o ícone PowerToys até que o menu seja exibido. Selecione "Configurações".
- Na parte inferior da página PowerToys configurações, **ative as atualizações de** download automaticamente.
- Quando uma atualização for lançada, uma Windows será exibida, dando a você a opção de quando instalar a atualização.


### <a name="edge-chromium-browser"></a>Navegador Chromium edge

Baixe e instale o novo navegador <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Chromium Edge</a>.


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub de Diagnóstico de Hardware

A <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub de Diagnóstico de</a> Hardware disponível gratuitamente no Microsoft Store. A ferramenta foi projetada para ajudá-lo a garantir que seu Surface Hub esteja funcionando da melhor maneira possível. Ele contém testes para determinar se o firmware está atualizado e configurado corretamente. Os testes interativos permitem confirmar que a funcionalidade essencial está funcionando conforme o esperado. Se forem encontrados problemas, os resultados poderão ser salvos e compartilhados com a equipe de suporte do Surface Hub. Clique no link para instalá-lo do Microsoft Store e fixe o aplicativo na barra de tarefas.

## <a name="additional-settings"></a>Configurações adicionais

### <a name="pen-tail-select-to-launch-whiteboard"></a>Caneta final selecionada para iniciar o Quadro de Comunicações

1. Pesquise **a Caneta** e selecione **As configurações & Windows Ink Caneta**.

2. Próximo à parte inferior da página, em **Atalhos de caneta**, defina **Selecionar uma vez** para **Microsoft Whiteboard**. 

### <a name="power-management"></a>Gerenciamento de energia

Há várias configurações de energia disponíveis para obter a melhor experiência usando Windows 10/11 Pro ou Enterprise no Surface Hub 2. Isso inclui tempos limite de tela e computador e como eles interagem com a detecção de presença humana interna (Doppler), a proteção por senha e a proteção de senha e, se apropriado, como passar as configurações de energia da política de grupo destinadas a usuários de laptop/área de trabalho.

Windows 10/11 Pro ou Enterprise no Surface Hub 2 impede que a tela entre em  sono por toque, mouse e ações de teclado, bem como a detecção de ocupação humana interna (Doppler). A detecção de ocupação humana está habilitada por padrão, mas, se desejado, ela pode ser desabilitada na UEFI alternando a opção de dispositivo na ferramenta Configurador uefi do Surface como parte da migração inicial ou criando e aplicando um pacote de configuração UEFI posterior. 

**Gerenciamento de energia: configurações de compartilhamento de tela e computador**

1. Selecione **Iniciar** >  **Configurações** >  **SystemPower** >  **& sleep**.

2. Defina o controle deslizante do modo de energia **para o melhor desempenho**.

3. Configure os valores de tela e  sono de acordo com sua preferência, enquanto também contabilize a detecção de presença do Doppler que ativa o dispositivo quando o movimento é detectado. Da mesma forma, como prática recomendada, é recomendável definir a tela para desligar após **2** horas e o computador desligar após **4 horas.**

**Gerenciamento de energia: economia de tela**

1. Pesquise **a Tela de Bloqueio** e abra **as configurações da tela de bloqueio**.

2. **Defina as configurações de tempo limite da** tela **e as configurações de proteção de tela** de acordo com sua preferência. Os valores padrão recomendados são:

   - Economia de tela para (Nenhum) ou uma salvação de tela de sua escolha.
   - Tempo de espera para 15 minutos.
   - Ao retomar, exiba a tela de logon.


**Gerenciamento de energia: Política de Grupo**

Antes de executar o procedimento a seguir, verifique com seu departamento de TI a aprovação para excluir um dispositivo Surface Hub 2S da política de gerenciamento de energia global. Algumas configurações de gerenciamento de energia podem desabilitar a função de detecção de presença.

1. Procure o **Centro de Software** e abra-o.

2. Selecione **Opções**.

3. Expanda **o gerenciamento de**  energia **e selecione Não aplicar configurações de energia do meu departamento de TI a este computador**.

   ![Configurações de software.](images/soft-cntr.png)

### <a name="storage-sense"></a>Sensor de armazenamento

O Surface Hub 2 tem um SSD de 128 GB para armazenamento local, portanto, é necessário considerar o uso de medidas de economia de armazenamento durante o uso normal.  Para configurar Armazenamento Sense:

1.  **Pesquise as configurações de armazenamento**, que são **encontradas nas configurações do sistema**.

2.  Em **Configurações**, selecione **Ativar o sensor de armazenamento** para abrir a **página Armazenamento** configurações.

3.  Ativar Armazenamento **Sentido.**

4.  Selecione **Configurar Armazenamento Sense ou** execute-o agora e defina as configurações para manter os arquivos online o máximo possível (devido ao espaço limitado na unidade).

Configurações recomendadas:

- Executar Armazenamento Sentido = Todos os dias.
- Exclua arquivos temporários que meus aplicativos não estão usando = a cada 14 dias (pelo menos).
- Exclua arquivos na minha pasta Downloads se eles estiverem lá por mais de 30 dias.
- OneDrive: o conteúdo ficará online somente se não for aberto por mais de 30 dias.

### <a name="tablet-mode"></a>Modo tablet

Ative o modo Tablet, se desejado, para necessidades de acessibilidade.


### <a name="sound-settings"></a>Configurações de som

1. **Pesquise as configurações de Sons** e abra esta página.

2. Selecione **Som Painel de Controle** à direita e selecione a **guia** Sons.

3. Em **Eventos de Programa**, **defina o dispositivo Conexão** **e a Desconexão do Dispositivo** como **Nenhum**.

### <a name="silence-notifications"></a>Notificações de silêncio

1. Pesquise **a assistência de Foco** e abra esta página.

2. Selecione **Somente Alarmes**. Isso evitará submenus de notificação constante.

### <a name="disk-cleanup"></a>Limpeza de Disco

1. **Pesquise a Limpeza de Disco** e abra este aplicativo.

2. Em **Arquivos a serem excluídos**, selecione os arquivos que você deseja excluir. 

3. Selecione Também **Limpar arquivos do sistema**.

## <a name="complete-and-verify"></a>Concluir e verificar

1. Verifique e instale todas as Windows atualizações.

2. Atualize Política de Grupo.

   1. Em um prompt de comando com privilégios elevados, insira **gpupdate /force /boot /wait:0**.
   
3. Reinicie o dispositivo.

4. Verifique os aplicativos da barra de tarefas.

   - Conexão aplicativo
   - Ícone Bloquear
   - Captura e Esboço
   - Teams (se aplicável)
   - Office aplicativos (se aplicável)
   - Surface App
   - Quadro de Comunicações
    
5. Verifique a detecção de presença.

   - A detecção de presença será um ícone verde na bandeja do sistema.
    
6. Verifique se a projetar para este computador está habilitada com o Conexão App. Depois de definir **Project configurações** deste computador, execute o aplicativo Conexão pelo menos uma vez. (Subsequentemente, o Conexão aplicativo não precisa estar em execução para projetar para Surface Hub.)

7. Verifique as configurações de energia e  sono.

    - Economia de tela: 15 minutos, definido como (nenhum), Mystify ou Blank; verifique se a caixa de seleção para exigir senha está marcada.
    - Tela: **Desative após 2 horas**.
    - PC:  **Desligar após 4 horas**.
    
8. Verifique Windows Hello está funcionando.

9. Verifique se a sincronização das configurações está desabilitada.

10. Verifique os aplicativos de inicialização.

> [!TIP]
> Depois de instalar e configurar o Windows 10, o Surface Hub 2S pode ser gerenciado como qualquer outro Windows 10 ou Windows 11 dispositivo.

## <a name="related-topics"></a>Tópicos relacionados

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migrar para Windows 10/11 Pro ou Enterprise no Surface Hub 2</a>
