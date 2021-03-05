---
title: Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2
description: Este artigo inclui recomendações para garantir a melhor experiência ao usar um computador de tela grande e caneta personalizado.
keywords: Surface Hub, Windows 10, área de trabalho, instalação, configuração
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
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393589"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a>Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2

Depois de concluir o processo de instalação de migração para o Windows 10 Pro ou Enterprise, você pode executar as etapas a seguir para configurar aplicativos e configurações em seu Surface Hub 2. Estas etapas são recomendadas para garantir a melhor experiência ao usar esse computador de toque de tela grande e caneta personalizado.

Ao executar essas etapas, você pode achar útil usar um teclado e mouse com fio ou sem fio.

## <a name="configure-system-settings"></a>Configurar configurações do sistema

1. Entre com uma conta que tenha privilégios de administrador local no dispositivo.  

    - Em dispositivos ingressados no Azure AD, o usuário que executa a junção do Azure AD é adicionado automaticamente ao grupo de administradores local. Os administradores globais do Azure AD e os administradores de dispositivos do Azure AD <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> também são administradores </a> locais. 
    
    - Você pode digitar **administradores de grupo local líquido em** um prompt de comando para listar as contas que têm direitos de administrador local.
    
2. Renomeie o dispositivo usando um nome amigável, por exemplo: **username-SHub-Desktop**.

3. Selecione **Iniciar**  >  **Configurações Contas**  >  ****  >  **Sincronizar suas configurações** e desativar **configurações de** sincronização. 

    - As configurações usadas aqui se destinam a habilitar a melhor experiência de toque de tela grande e, portanto, talvez você não queira sincronizar outros dispositivos.
    
4. Reinicie o dispositivo.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>Habilitar o teclado touch e o touchpad

1. Selecione **Iniciar**  >  **Configurações**  >  **Dispositivos**  >  **Digitando** **** e ativar Mostrar o teclado touch quando não estiver no modo tablet e não houver teclado conectado.

2. Toque e segure ou clique com o botão direito do mouse na barra de tarefas e selecione Mostrar botão de **teclado** por toque e **Mostrar botão touchpad**. 

    - O teclado touch é útil para entrada direta do usuário, e o touchpad virtual ajuda com seleções precisas, dicas de tela de foco ou como uma alternativa para tocar e segurar para clicar com o botão direito do mouse. 
    
    - Veja o exemplo a seguir.

      ![Configurações de toque](images/touch.png)

3. Configure o teclado touch como QWERTY e flutuante.

    1. Selecione o **ícone Teclado** na barra de tarefas para mostrar o teclado por toque.
    
    1. No teclado touch, selecione o ícone de teclado no canto superior esquerdo para abrir as configurações do teclado.
    
    1. Selecione o próximo ou último tipo de teclado na linha superior para habilitar o QWERTY e a última opção na segunda linha para habilitar o flutuante, o que é muito útil nessa tela grande. Consulte os exemplos a seguir.

       ![Configurações de teclado](images/kbd.png)
 
4. Configure as configurações do teclado suave.

    1. Selecione o **ícone Configurações** no teclado de toque ou procure e abra **Configurações de Digitação**.
    
       ![configurações de teclado suave](images/sh2-softkeyboard.png)

    1. Habilita todas as opções em Teclado ortográfico, de digitação e de toque.


O exemplo a seguir mostra o trackpad, que é útil para navegar e selecionar opções. O teclado na tela está sendo usado para pesquisar na Microsoft Store:

![Usando o trackpad](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>Configurar Bluetooth teclado e mouse (opcional)

Conecte um teclado e um mouse se você estiver usando o dispositivo como seu dispositivo Windows principal ou use-o com frequência para digitar ou trabalhar com precisão.

Se o dispositivo Surface Hub estiver próximo de um computador, você poderá usar Mouse sem Bordas para se mover perfeitamente entre o <a href="https://aka.ms/mm" target="_blank"> Surface Hub e o </a> computador. Para obter mais informações, consulte <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Download da Microsoft em O Garage: Mouse sem Bordas. </a>

## <a name="example-of-taskbar-layout"></a>Exemplo de layout da barra de tarefas

Depois de concluir as etapas a seguir para configurar/configurar o Surface Hub 2 para Windows 10 Professional ou Enterprise, recomendamos que você utilize fixar seus aplicativos mais usados na Barra de Tarefas para um início rápido de um toque de cada aplicativo. Veja a seguir um exemplo de como sua barra de tarefas poderia ser:

 ![Layout da barra de tarefas](images/taskblyt.png)
### <a name="update-installed-apps"></a>Atualizar aplicativos instalados

Para atualizar todos os aplicativos da Loja instalados:

1. Abra o aplicativo da Microsoft Store e selecione **See more** ellipsis in the top-right corner.
2. Selecione **Downloads e atualizações.**
3. Selecionar **Obter atualizações**

### <a name="scan-for-and-install-all-windows-updates"></a>Examinar e instalar todas as Atualizações do Windows
Depois de migrar para o Windows 10 Professional ou o Windows 10 Enterprise, pode haver atualizações de recursos e manutenção disponíveis para você instalar. 

- Vá para **Configurações**  >  **Atualizar & Segurança** > e selecione Verificar se há **atualizações**.
- Se houver atualizações, instale-as, reinicie e repita o processo até que você veja a seguinte notificação:

> [!div class="mx-imgBorder"]
> ![Notificação do Windows Update "Você está atualizado"](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive for Business

Use o OneDrive for Business para compartilhar facilmente ferramentas, logs e <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> outros arquivos entre todos os </a> dispositivos de trabalho.

- O OneDrive permite que você compartilhe seus arquivos de trabalho entre seus laptops, Surface Hub Desktop e seus dispositivos móveis gerenciados pelo Intune. Os arquivos podem ser editados em qualquer dispositivo e todos os dispositivos conectados à rede serão atualizados com as alterações.

- Considerando o tamanho do SSD do Surface Hub (128 GB), se você configurar o OneDrive em seu dispositivo Surface Hub Desktop, certifique-se de que a configuração padrão é manter os arquivos online e baixar arquivos conforme você os usa.

Para configurar o OneDrive para baixar arquivos somente quando necessário, de definir a configuração **Arquivos Sob** Demanda como Salvar espaço e baixar arquivos conforme você **os usa**. Para obter mais informações, <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> consulte Query and set Files On-Demand states in Windows </a> .

![Configurações do OneDrive](images/onedrive.png)

> [!NOTE]
> Você também pode repetir essas etapas para configurar um OneDrive pessoal, mas não deixe de economizar espaço na unidade e apenas baixar arquivos conforme precisar deles.

## <a name="sharepoint-and-teams"></a>SharePoint e Teams

Os arquivos do SharePoint e do Teams Channel também podem sincronizar localmente com seus dispositivos de área de trabalho, como laptops e Surface Hubs, usando o mecanismo de sincronização do OneDrive.

Para sincronizar arquivos corporativos internos com sua unidade local com o aplicativo de sincronização do OneDrive:

1. Vá para um site do SharePoint e navegue até o diretório de documentos de nível superior para os arquivos que você está interessado em exibir ou editar do dispositivo local.

2. Selecione no botão **Sincronizar** na parte superior da faixa de opções do SharePoint.

3. Selecione em **Abrir** no pop-up **Este site está tentando abrir o Microsoft OneDrive**.

4. Verifique se os arquivos do SharePoint estão sincronizando com sua unidade local selecionando no ícone do OneDrive na parte inferior direita da barra de tarefas.

5. Verifique se a configuração está definida para manter os arquivos online e baixar os arquivos somente conforme você os usa:

    1. Abra o explorador de arquivos.
    
    2. Navegue até e clique com o botão direito do mouse no nome do SharePoint; por exemplo, **Contoso \ \<SharePoint Document Folder Name\> **.
    
    3. Selecione **Liberar espaço**.
    
    4. A coluna Status exibirá o status de arquivos e pastas. Para obter mais informações, consulte <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sincronizar arquivos do SharePoint com o cliente de sincronização do OneDrive. </a>
    
6. Os arquivos do Teams Channel são armazenados em sites do SharePoint, com todas as mesmas funcionalidades de documento do SharePoint, incluindo histórico de versão e sincronização com seus dispositivos de área de trabalho locais. Para sincronizar arquivos do Teams Channel:

    1. Navegue até o Canal do Teams de interesse e selecione a guia **Arquivos** na parte superior. Em seguida, **selecione Sincronizar**. Os arquivos iniciarão a sincronização e estarão visíveis no Explorador de Arquivos na **Área de Trabalho \ Contoso \ \<name of the Teams Channel\> **.
    
    2. Use o mesmo procedimento que você usou para sincronizar sites do SharePoint para manter os arquivos na nuvem e apenas baixá-los quando você usá-los, tocar e segurar ou clicar com o botão direito do mouse no Explorador de Arquivos no nome do Canal do Teams e, em seguida, **selecionando Liberar**espaço .

## <a name="surface-hub-pen-settings"></a>Configurações de caneta do Surface Hub

**Emparelhar a caneta Bluetooth Surface Hub**

Emparelhar a caneta para manter o firmware de caneta atualizado, definir os atalhos de caneta e obter informações sobre a carga da bateria na página de configurações do dispositivo Bluetooth ou no aplicativo Surface:

1. Selecione **Iniciar**  >  **Dispositivos de**  >  **Configurações**.

2. Selecione **Adicionar Bluetooth ou outro dispositivo**.

3. Escolha **Bluetooth**.

4. Remova o botão de cauda de caneta e balance para desconectar a conexão da bateria.

5. Coloque a tampa novamente e pressione e segure a tampa até o LED de emparelhamento piscar.

6. Nas configurações do Surface Hub Bluetooth, escolha **Surface Hub 2 Pen**.

7. Conclua a operação de emparelhamento. 

8. Se o emparelhamento não for bem-sucedido, você poderá tentar emparelhar a caneta novamente. Se isso não funcionar, você poderá testar para ver se a bateria é carregada verificando se a caneta funciona no aplicativo de Quadro de Branco. Caso não seja, substitua a bateria e tente emparelhar a caneta novamente. Se necessário, reinicie o dispositivo e tente novamente.

**Definir atalhos de caneta** A caneta Surface Hub tem um botão de atalho às vezes chamado de "clique na cauda". A configuração de atalhos exige que você primeiro emparelhe a caneta, conforme descrito anteriormente.

1. Pesquise Caneta e **selecione Caneta & configurações do Windows Ink.**

2. Na parte inferior da página, selecione Atalhos de caneta que abre a caixa de diálogo, mostrada aqui:

   ![Atalhos de caneta](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>Configuração da câmera

Você pode montar a câmera na parte superior ou em ambos os lados do dispositivo. Monte a câmera em uma posição para otimizar o ângulo da câmera se você estiver usando o Hub com um suporte de área de trabalho em vez de um carrinho ou estiver próximo do Hub. A câmera não gira automaticamente, portanto, você precisa ter uma chave hexaxa de 2 mm para girar manualmente a câmera. 

Para obter mais informações sobre como montar lateralmente a câmera e girar a câmera manualmente, consulte Orientação da lente da câmera <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> do Surface Hub 2S </a> .

## <a name="windows-hello-configuration"></a>Configuração do Windows Hello

O Surface Hub 2S que executa o Windows 10 Enterprise permite o pacote completo de aplicativos de área de trabalho Win32, bem como opções biométricas do Windows Hello. O acessório Leitor de Impressão Digital do Surface Hub 2 pode ser conectado a qualquer porta USB-C no dispositivo. 

Para solicitar um Leitor de Impressão Digital do Surface Hub 2 ou exibir especificações técnicas, consulte (surface-hub-2-essential-add-ons.md" target="_blank">Complementos essenciais para Windows 10 Pro e Enterprise no Surface Hub 2 </a> . 

Depois de inserir o leitor de impressão digital, selecione **Iniciar**  >  **Configurações**Opções de  >  ****  >  **logon**do  >  **Windows Hello Fingerprint** para registrar sua impressão digital.

Use um dispositivo certificado do Windows Hello para reconhecimento de rosto. A câmera do Surface Hub 2S não dá suporte ao reconhecimento facial do Windows Hello.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>Habilitar um ícone de atalho de Tela de Bloqueio na barra de tarefas

Para adicionar um ícone à barra de tarefas que habilita um bloqueio de tela de toque semelhante ao atalho do teclado windows-L: 

1.  Toque e segure ou clique com o botão direito do mouse na área de trabalho, selecione **Novo**  >  **Atalho**  >  **Procurar**  >  **Área de Trabalho**OK  >  ****  >  **Próximo**.

1.  Forneça um nome para o atalho, como **Bloquear meu computador**e selecione **Concluir**.

1.  Clique com o botão direito do mouse ou toque e segure o atalho recém-criado na área de trabalho e selecione **Propriedades**. Na guia **Atalho,** insira o seguinte no campo **Destino:** **Rundll32.exe User32.dll,LockWorkStation**

1.  Selecione o **botão Alterar Ícone** e navegue ** até **C:\Windows\System32\imageres.dlle selecione um ícone a ser usado. 

    Veja o exemplo a seguir:

    ![Escolher um ícone](images/lock.png)
    
1.  Selecione **OK** para salvar o atalho.

1.  Clique com o botão direito do mouse ou toque e segure o atalho e selecione **Fixar na barra de tarefas**.

1. Depois de ter fixado o atalho de bloqueio na barra de tarefas, você pode excluí-lo da área de trabalho.

## <a name="applications"></a>Aplicativos


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

Para instalar o Quadro de Whiteboard da Microsoft:

 - Selecione o **ícone do Espaço de Trabalho do Windows Ink** no canto inferior direito da barra de tarefas e baixe o Quadro de **Trabalho**.
 
   ![Espaço de trabalho de tinta](images/ink.png) 

Como alternativa, você pode instalar o Quadro de Trabalho na Microsoft Store:

1. Abra o aplicativo da Microsoft Store e pesquise **whiteboard**.

2. Escolha **Não graças** a entrar e usar em dispositivos.

3. Fixar quadro de trabalho na barra de tarefas.

### <a name="surface-app"></a>Aplicativo Surface

1. Na Microsoft Store, pesquise o **Surface**.

2. De definir **o filtro Disponível em** todos os **dispositivos**.

3. Instale o **aplicativo Surface.** Este deve ser o primeiro aplicativo listado. Talvez seja necessário associar seu MSA à Loja para instalar o aplicativo.

4. Fixar o **aplicativo Surface** na barra de tarefas.

### <a name="snip--sketch"></a>Captura e Esboço

1. Abra o **aplicativo Snip & Sketch** e fixe-o na barra de tarefas.

2. Selecione a reellipse no canto superior direito e selecione **Configurações**.

3. Em **Configurações,** a opção **Copiar automaticamente**para área de transferência, **Salvar trechos**e Várias **janelas** (opcional).

### <a name="microsoft-office"></a>Microsoft Office

1. Abra o <a href="https://portal.office.com/account#installs" target="_blank"> Portal do Office e instale seus </a> aplicativos desejados.

2. Fixar aplicativos do Office desejados na barra de tarefas.

3. Se o Outlook estiver instalado, certifique-se de definir o Outlook OST para salvar apenas o cache das últimas duas semanas. Isso reduzirá consideravelmente o uso do disco e o tempo de instalação.

    - Selecione **Configurações**  >  **da Conta de Arquivo** e selecione sua conta.
    
    - Selecione **Alterar** e de definir o controle deslizante para **Usar o Modo cache do Exchange** como 14 dias.

### <a name="microsoft-teams"></a>Microsoft Teams

1. Baixar e instalar <a href="https://teams.microsoft.com/downloads" target="_blank"> o Microsoft </a> Teams.

2. Configure as configurações para o aplicativo de início automático (opcional).

3. Fixar o Teams na barra de tarefas.

4. Considere reduzir as notificações do Teams no dispositivo para evitar distrações (opcionais).

   ![Notificações do Teams](images/teams.png)

### <a name="connect-app"></a>Conectar aplicativo

> [!IMPORTANT]
> No Windows 10, versão 2004 e posterior, o aplicativo Connect para projeção sem fio usando Miracast não é instalado por padrão, mas está disponível como um recurso opcional. Se você tiver instalado (ou atualizado para) o Windows versão 2004 ou posterior, poderá ver o seguinte na tela Projetando para este computador nas configurações:

![Project para este computador](images/sh2-project.png) 


1. Para instalar o aplicativo na página de configurações "Projetando para este computador", selecione Recursos opcionais **** Adicionar um recurso e, em seguida, instalar o aplicativo De  >  **** **exibição sem** fio.

2. Em **Alguns dispositivos Windows e Android podem projetar**para este computador quando você diz que está OK , escolha:

    - **Disponível em todos os** lugares se o dispositivo não estiver em uma rede corporativa.
    - Caso contrário, escolha **Disponível em qualquer lugar em redes seguras.**
    
3. Em **Pedir para projetar para este computador,** escolha Somente primeira **vez**.

4. Em **Exigir PIN para emparelhamento,** escolha **Nunca**.

5. Para então iniciar o aplicativo e fixá-lo na barra de tarefas, pesquise **por Connect**.

6. Abra o aplicativo. Enquanto o aplicativo estiver aberto, clique com o botão direito do mouse no ícone do aplicativo Conectar na barra de tarefas e selecione **o pino na**barra de tarefas .

7. Em seguida, feche o aplicativo Connect. **O project para esse computador pode** não funcionar, a menos que o aplicativo tenha sido executado pelo menos uma vez.

Configuração recomendada quando não estiver na rede corporativa:

![Configurações em casa](images/project1.png)

Configuração recomendada na rede corporativa:

![Configurações no trabalho](images/project2.png)

### <a name="your-phone"></a>Seu Telefone

O **aplicativo Seu Telefone** é instalado por padrão no Windows 10. Se ele não estiver presente, você também poderá instalá-lo na Windows Store.

Para obter informações sobre como configurar o aplicativo, consulte Como configurar Seu Telefone no Windows 10 e sincronizar dados entre seu <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> computador e </a> telefone. Consulte Também <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Como corrigir problemas comuns com o aplicativo Seu Telefone no Windows 10 </a> .

###  <a name="fancy-zones"></a>Zonas sofisticadas


**Zonas Sofisticadas** faz parte de uma coleção de ferramentas chamadas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> no GitHub.. É uma ótima maneira de utilizar a propriedade de tela em um Surface Hub 2, dando a você a capacidade de definir layouts fixos em sua exibição ("zonas") e, em seguida, selecione qual aplicativo será executado em cada zona. 


O [wiki do PowerToys tem](https://github.com/microsoft/PowerToys/wiki) instruções sobre como usar e personalizar cada ferramenta, incluindo [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). Em alto nível – depois de instalar o PowerToys, você pode selecionar ou criar um layout personalizado e, em seguida, segurar a tecla de turno para baixo e arrastar ou usar teclas de teclado para mover um aplicativo em execução para zonas específicas. Usar um Bluetooth ou o teclado USB e o mouse ajudarão com isso, ou você pode usar o teclado touch na tela e o touchpad.

**Dicas de power toys**
- Para receber notificações por email das atualizações de versão do PowerToys no GitHub, clique no botão "inscrever-se" na parte superior da [página](https://github.com/microsoft/PowerToys/releases).
- Depois que o PowerToys for instalado, você poderá receber notificações do Windows e/ou baixar e instalar as atualizações mais recentes configurando as configurações do PowerToys **Baixar** atualizações automaticamente para.
- Para acessar as configurações do PowerToys, **** selecione o quilate para cima Executando aplicativos na barra de tarefas e clique com o botão direito do mouse ou pressione e segure o ícone PowerToys até que o menu apareça. Selecione "Configurações".
- Na parte inferior da página de configurações do PowerToys, a opção **Baixar atualizações automaticamente** para.
- Quando uma atualização for lançada, uma notificação do Windows aparecerá, dando a você a opção de quando instalar a atualização.


### <a name="edge-chromium-browser"></a>Navegador edge Chromium

Baixe e instale o novo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> navegador edge Chromium </a> .


### <a name="surface-hub-hardware-diagnostic-tool"></a>Ferramenta de Diagnóstico de Hardware do Surface Hub

A <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> ferramenta diagnóstico de hardware do Surface Hub disponível </a> gratuitamente na Microsoft Store. A ferramenta foi projetada para ajudá-lo a garantir que o Surface Hub está em melhor desempenho. Ele contém testes para determinar se o firmware está atualizado e configurado corretamente. Testes interativos permitem confirmar que a funcionalidade essencial está funcionando conforme o esperado. Se forem encontrados problemas, os resultados poderão ser salvos e compartilhados com a equipe de suporte do Surface Hub. Clique no link para instalá-lo na Microsoft Store e fixe o aplicativo na barra de tarefas.

## <a name="additional-settings"></a>Configurações adicionais

### <a name="pen-tail-select-to-launch-whiteboard"></a>Caneta tail select to launch Whiteboard

1. Pesquise **Caneta** e selecione **Caneta & configurações do Windows Ink.**

2. Na parte inferior da página, em **Atalhos de caneta,** desempenha **Selecionar uma vez** para o Quadro de Branco da **Microsoft.** 

### <a name="power-management"></a>Gerenciamento de energia

Há várias configurações de energia disponíveis para obter a melhor experiência usando o Windows 10 Pro ou Enterprise no Surface Hub 2. Isso inclui tempos-extra de tela e computador e como eles interagem com a detecção de presença humana interna (Doppler), a proteção de senha e economia de tela e, se apropriado, como passar as configurações de energia da política de grupo destinadas a usuários de laptop/área de trabalho.

O Windows 10 Pro ou Enterprise no Surface Hub 2 impede que a tela adore por ações de toque, mouse e teclado, bem como a detecção de ocupação humana (Doppler) integrada. A detecção de ocência humana é habilitada por padrão, mas, se desejado, ela pode ser desabilitada na UEFI por meio da agregação da opção de dispositivo na ferramenta Configurador uefi do Surface como parte da migração inicial ou pela criação e aplicação de um pacote de configuração UEFI posterior. 

**Gerenciamento de Energia: Configurações de sleep de tela e computador**

1. Selecione **Iniciar**  >  **Configurações do**  >  **Sistema**Energia & de  >  **1.000.**

2. De definir o controle deslizante do modo de alimentação **como Melhor desempenho.**

3. Configure os valores de tela e de encefação para sua preferência enquanto também contabilização da detecção de presença do Doppler que acorda o dispositivo quando o movimento é detectado. Assim, como prática recomendada, é recomendável definir Tela como Desativar após **2** horas e o computador para **Desativar após 4 horas.**

**Gerenciamento de Energia: Economia de tela**

1. **Pesquise as** configurações de tela de bloqueio e abra a **tela de bloqueio.**

2. Configure **configurações de tempo de tempo de tela** e **configurações de economia de tela** para sua preferência. Os valores padrão recomendados são:

   - Economia de tela como (Nenhum) ou um protetor de tela de sua escolha.
   - Tempo de espera para 15 minutos.
   - Ao retomar, exibe a tela de logon.


**Gerenciamento de Energia: Política de Grupo**

Antes de executar o procedimento a seguir, verifique com seu departamento de IT a aprovação para excluir um dispositivo Surface Hub 2S da política de gerenciamento de energia global. Algumas configurações de gerenciamento de energia podem desabilitar a função de detecção de presença.

1. Pesquise **o Centro de Software** e abra-o.

2. Selecione **Opções**.

3. Expanda **o gerenciamento de energia**  e selecione Não aplicar configurações de energia do meu departamento de IT a este **computador**.

   ![Configurações de software](images/soft-cntr.png)

### <a name="storage-sense"></a>Sensor de armazenamento

O Surface Hub 2 tem um SSD de 128 GB para armazenamento local, portanto, é necessário considerar o uso de medidas de economia de armazenamento durante o uso normal.  Para configurar o Sentido de Armazenamento:

1.  **Pesquise as configurações de armazenamento**, que é encontrada em **Configurações do sistema**.

2.  Em **Configurações,** selecione **Ativar o sentido de armazenamento** para abrir a página **Configurações** de armazenamento.

3.  Ativar o Sentido de **Armazenamento**para .

4.  Selecione **Configurar o Sentido de Armazenamento ou execute-o** agora e configure as configurações para manter os arquivos online o máximo possível (devido ao espaço limitado da unidade).

Configurações recomendadas:

- Executar o Sentido de Armazenamento = Todos os Dias.
- Exclua arquivos temporários que meus aplicativos não estão usando = a cada 14 dias (pelo menos).
- Exclua arquivos na minha pasta Downloads se eles estão lá há mais de 30 dias.
- OneDrive: o conteúdo se tornará somente online se não for aberto por mais de 30 dias.

### <a name="tablet-mode"></a>Modo tablet

Ativar o modo Tablet, se desejado para necessidades de acessibilidade.


### <a name="sound-settings"></a>Configurações de som

1. Pesquise **as configurações de Sons** e abra esta página.

2. Selecione **Painel de Controle de Som** à direita e selecione a guia **Sons.**

3. Em **Eventos de Programa,** **desconectar** dispositivo e conexão **de dispositivo** como **nenhum**.

### <a name="silence-notifications"></a>Notificações de silêncio

1. Procure ajuda **de Foco e** abra esta página.

2. Selecione **Somente Alarmes**. Isso evitará os sobrevoos de notificação constante.

### <a name="disk-cleanup"></a>Limpeza de Disco

1. **Pesquise a Limpeza de Disco** e abra este aplicativo.

2. Em **Arquivos a ser excluído,** selecione os arquivos que você deseja excluir. 

3. Selecione Também **Limpar arquivos do sistema**.

## <a name="complete-and-verify"></a>Concluir e verificar

1. Examinar e instalar todas as Atualizações do Windows.

2. Atualizar Política de Grupo.

   1. Em um prompt de comando elevado, insira **gpupdate /force /boot /wait:0**.
   
3. Reinicie o dispositivo.

4. Verifique os aplicativos da barra de tarefas.

   - Conectar Aplicativo
   - Ícone de bloqueio
   - Captura e Esboço
   - Teams (se aplicável)
   - Office Apps (se aplicável)
   - Surface App
   - Quadro de Comunicações
    
5. Verifique a detecção de presença.

   - A detecção de presença será um ícone verde na bandeja do sistema.
    
6. Verifique se a projeção para esse computador está habilitada com o Aplicativo Connect. Depois de configurar  **o Project para essas configurações** de computador, execute o Aplicativo conectar pelo menos uma vez. (Subsequentemente, o Aplicativo Connect não precisa ser executado para projetar para o Surface Hub.)

7. Verifique as configurações de energia e de sono.

    - Screen Saver: 15 minutos, definido como (nenhum), Mystify ou Blank; verifique se a caixa de seleção para exigir senha está selecionada.
    - Tela: **Desativar após 2 horas**.
    - PC:  **Desativar após 4 horas**.
    
8. Verifique se o Windows Hello está funcionando.

9. Verifique se a sincronização das configurações está desabilitada.

10. Verifique os aplicativos de inicialização.

> [!TIP]
> Depois de instalar e configurar o Windows 10, o Surface Hub 2S pode ser gerenciado da mesma forma que qualquer outro dispositivo Windows 10.

## <a name="related-topics"></a>Tópicos relacionados

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2</a>
