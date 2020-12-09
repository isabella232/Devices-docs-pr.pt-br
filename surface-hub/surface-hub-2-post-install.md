---
title: Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2
description: Este artigo inclui recomendações para garantir a melhor experiência ao usar um computador com tela e um toque de tela grande personalizado.
keywords: Surface Hub, Windows 10, área de trabalho, instalar, configuração
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
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203544"
---
# Configurar o Windows 10 Pro ou Enterprise no Surface Hub 2

Depois de concluir o processo de instalação da migração para o Windows 10 pro ou Enterprise, você pode executar as seguintes etapas para definir aplicativos e configurações no Surface Hub 2. Essas etapas são recomendadas para garantir a melhor experiência ao usar esse computador de tela e o toque de tela grandes personalizados.

Ao executar essas etapas, talvez seja útil usar um mouse e um teclado com fio ou sem fio.

## Definir configurações do sistema

1. Entre com uma conta que tenha privilégios de administrador local no dispositivo.  

    - Nos dispositivos associados ao Azure AD, o usuário que executa a junção do Azure AD é automaticamente adicionado ao grupo administrador local. Os administradores globais do Azure AD e os administradores de dispositivos do Azure AD <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> também são administradores locais </a> . 
    
    - Você pode digitar **net localgroup Administrators** em um prompt de comando para listar as contas que têm direitos de administrador local.
    
2. Renomeie o dispositivo usando um nome amigável, por exemplo: **nome_do_usuário-SHub-área de trabalho**.

3. Selecione **Iniciar**  >  **configurações**  >  **contas**  >  **sincronizar suas configurações** e desativar **as configurações de sincronização** . 

    - As configurações usadas aqui se destinam a habilitar a melhor experiência de toque em tela grande e, portanto, talvez você não queira sincronizar outros dispositivos.
    
4. Reinicie o dispositivo.

## Habilitar o teclado virtual e o touchpad

1. Toque e segure ou clique com o botão direito do mouse na barra de tarefas e selecione **Mostrar botão do teclado virtual** e **botão Mostrar Touchpad**. 

    - O teclado virtual é útil para entrada direta do usuário, e o touchpad virtual ajuda com seleções precisas, dicas de tela focalizadas ou como uma alternativa de tocar e segurar para clique com o botão direito do mouse. 
    
    - Veja o exemplo a seguir.

      ![Configurações de toque](images/touch.png)

2. Configurar o teclado de toque para QWERTY e flutuante.

    1. Selecione o ícone de **teclado** na barra de tarefas para mostrar o teclado virtual.
    
    2. No teclado virtual, selecione o ícone de teclado no canto superior esquerdo para abrir as configurações de teclado.
    
    3. Selecione o próximo ao último tipo de teclado na linha superior para habilitar a QWERTY e a última opção na segunda linha para habilitar a flutuante, o que é muito útil nesta tela grande. Consulte os exemplos a seguir.

       ![Configurações do teclado](images/kbd.png)
 
3. Defina as configurações do teclado virtual.

    1. Selecione o ícone **configurações** no teclado virtual ou procure e abra configurações de **digitação**.
    
       ![configurações do teclado virtual](images/sh2-softkeyboard.png)

    1. Habilite todas as opções em ortografia, digitação e toque do teclado.


O exemplo a seguir mostra o trackpad, que é útil para navegar e selecionar opções. O teclado na tela está sendo usado para pesquisar a Microsoft Store:

![Usando o trackpad](images/store.png)

## Configurar mouse e teclado Bluetooth (opcional)

Conecte um teclado e um mouse se estiver usando o dispositivo como seu dispositivo principal do Windows ou use-o com frequência para a digitação ou a precisão do trabalho.

Se o dispositivo do Surface Hub estiver próximo a um computador, você pode usar <a href="https://aka.ms/mm" target="_blank"> o mouse sem bordas </a> para se mover diretamente entre o Surface Hub e o computador. Para obter mais informações, consulte <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> o download da Microsoft na garagem: mouse sem bordas. </a>

## Exemplo de layout da barra de tarefas

Depois de concluir as etapas abaixo para configurar/configurar o Surface Hub 2 para Windows 10 Professional ou Enterprise, recomendamos que você use a fixação dos aplicativos mais usados para a barra de tarefas para uma inicialização rápida com um só toque de cada aplicativo. Veja a seguir um exemplo de como a barra de tarefas poderia se parecer com o seguinte:

 ![Layout da barra de tarefas](images/taskblyt.png)
### Atualizar aplicativos instalados

Para atualizar todos os aplicativos da loja instalados:

1. Abra o aplicativo da Microsoft Store e selecione **Ver mais** reticências no canto superior direito.
2. Selecione **downloads e atualizações.**
3. Selecione **obter atualizações**

### Procurar e instalar todas as atualizações do Windows
Após a migração para o Windows 10 Professional ou Windows 10 Enterprise, talvez haja atualizações de serviço e manutenção disponíveis para você instalar. 

- Vá para **configurações**  >  **Atualizar &** > de segurança e, em seguida, selecione **verificar se há atualizações**.
- Se houver alguma atualização, instale-a, reinicialize e repita o processo até que você veja a seguinte notificação:

> [!div class="mx-imgBorder"]
> ![Notificação do Windows Update ' você está atualizado '](images/wustatus.png)


## OneDrive for Business

Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> o onedrive for Business </a> para compartilhar facilmente ferramentas, logs e outros arquivos entre todos os seus dispositivos de trabalho.

- O OneDrive permite que você compartilhe seus arquivos de trabalho entre seus laptops, a área de trabalho do Surface Hub e seus dispositivos móveis gerenciados pelo Intune. Os arquivos podem ser editados em qualquer dispositivo, e todos os dispositivos conectados à rede serão atualizados com as alterações.

- Considerando o tamanho da SSD do Surface Hub (128 GB), se você configurar o OneDrive em seu dispositivo de área de trabalho do Surface Hub, verifique se a configuração padrão é manter os arquivos online e baixar os arquivos conforme você os usa.

Para configurar o OneDrive para baixar arquivos somente quando necessário, defina a configuração de **arquivos sob demanda** para **economizar espaço e baixar arquivos conforme você os usa**. Para obter mais informações, consulte <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> consultar e definir os Estados de arquivos sob demanda no Windows </a> .

![Configurações do OneDrive](images/onedrive.png)

> [!NOTE]
> Você também pode repetir essas etapas para configurar um OneDrive pessoal, mas lembre-se de conservar o espaço da unidade e apenas baixar arquivos conforme necessário.

## SharePoint e Teams

Os arquivos de canal do SharePoint e do teams também podem ser sincronizados localmente com seus dispositivos de área de trabalho, como laptops e Surface Hub, usando o mecanismo de sincronização do OneDrive.

Para sincronizar arquivos corporativos internos para sua unidade local com o aplicativo de sincronização do OneDrive:

1. Vá para um site do SharePoint e navegue até o diretório de documentos de nível superior dos arquivos nos quais você está interessado em exibir ou editar a partir do seu dispositivo local.

2. Selecione o botão **sincronizar** na parte superior da faixa de opções do SharePoint.

3. Selecionar ao **abrir** no pop-up **este site está tentando abrir o Microsoft onedrive**.

4. Verifique se os arquivos do SharePoint estão sincronizando com a unidade local selecionando no ícone do OneDrive na parte inferior direita da barra de tarefas.

5. Verifique se a configuração está definida para manter os arquivos online e baixe os arquivos somente quando você os usa:

    1. Abra o explorador de arquivos.
    
    2. Acesse e clique com o botão direito do mouse no seu nome do SharePoint; por exemplo, **Contoso \ \<SharePoint Document Folder Name\> **.
    
    3. Selecione **liberar espaço**.
    
    4. A coluna status mostrará o status de arquivos e pastas. Para obter mais informações, consulte <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> sincronizar arquivos do SharePoint com o cliente de sincronização do onedrive </a> .
    
6. Os arquivos de canal de equipe são armazenados nos sites do SharePoint, com todas as mesmas funcionalidades de documentos do SharePoint, incluindo histórico de versão e sincronização para seus dispositivos de área de trabalho locais. Para sincronizar arquivos de canais de equipe:

    1. Navegue até o canal de interesse do Teams e selecione a guia **arquivos** na parte superior. Em seguida, selecione **sincronizar**. Os arquivos começarão a ser sincronizados e ficarão visíveis no explorador de arquivos **da área \<name of the Teams Channel\> de trabalho \ Contoso \ **.
    
    2. Use o mesmo procedimento usado para sincronizar os sites do SharePoint para manter os arquivos na nuvem e apenas baixá-los quando forem usados, toque e segure ou clique com o botão direito do mouse no explorador de arquivos no nome do canal do Teams e, em seguida, selecione **liberar espaço**.

## Configurações da caneta do Surface Hub

**Emparelhar a caneta do Hub da superfície Bluetooth**

Emparelhar a caneta para manter o firmware da caneta atualizado, definir os atalhos da caneta e obter informações sobre a carga da bateria na página de configurações do dispositivo Bluetooth ou no aplicativo Surface:

1. Selecione **Iniciar**  >  **configurações**de  >  **dispositivos**.

2. Selecione **Adicionar Bluetooth ou outro dispositivo**.

3. Escolha **Bluetooth**.

4. Remova o botão de cauda da caneta e agite para desconectar a conexão da bateria.

5. Recoloque a tampa e pressione e segure a tampa até que o LED de emparelhamento pisque.

6. Nas configurações de Bluetooth do Surface Hub, escolha **Surface Hub 2 caneta**.

7. Concluir a operação de emparelhamento. 

8. Se o emparelhamento não for bem-sucedido, você pode tentar emparelhar a caneta novamente. Se isso não funcionar, você pode testar para ver se a bateria está carregada verificando se a caneta funciona no aplicativo do quadro de comunicações. Caso contrário, substitua a bateria e, em seguida, tente emparelhar a caneta novamente. Se necessário, reinicie o dispositivo e tente novamente.

**Definir atalhos de caneta** A caneta do Surface Hub tem um botão de atalho, às vezes chamado de "fim do clique". A configuração de atalhos requer que você primeiro Emparelhe a caneta, conforme descrito anteriormente.

1. Procure caneta e selecione **caneta & configurações de tinta do Windows**.

2. Próximo à parte inferior da página, selecione atalhos de caneta que abrem a caixa de diálogo, mostrada aqui:

   ![Atalhos de caneta](images/sh2-pen-shortcuts.png)

## Configuração da câmera

Você pode montar a câmera na parte superior ou em qualquer um dos lados do dispositivo. Monte a câmera em uma posição para otimizar o ângulo da câmera se você estiver usando o Hub com um suporte de área de trabalho em vez de um carrinho ou se estiver próximo ao Hub. A câmera não gira automaticamente, portanto você precisa ter uma chave hex 2mm para girar manualmente a câmera. 

Para saber mais sobre como montar a câmera lado a lado e girar a câmera manualmente, consulte <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> orientação do Surface Hub 2s orientação da lente da câmera </a> .

## Configuração do Windows Hello

O Surface Hub 2S executando o Windows 10 Enterprise permite o pacote completo de aplicativos da área de trabalho Win32, bem como as opções biométricas do Windows Hello. O acessório de leitor de impressão digital Surface Hub 2 pode ser conectado a qualquer porta USB-C do dispositivo. 

Para solicitar um leitor de Surface Hub 2 ou exibir especificações técnicas, consulte (surface-hub-2-essential-add-ons.md "target =" _blank ">Complementos essenciais para o Windows 10 pro e Enterprise no Surface Hub 2 </a> . 

Depois de inserir o leitor de impressão digital, selecione **Iniciar**  >  **configurações**  >  **conta**  >  **Opções de entrada**e  >  **impressão digital do Windows Hello** para registrar sua impressão digital.

Use um dispositivo certificado com Windows Hello para o reconhecimento de rosto. A câmera Surface Hub 2S não dá suporte ao reconhecimento facial do Windows Hello.

## Habilitar um ícone de atalho da tela de bloqueio na barra de tarefas

Para adicionar um ícone à barra de tarefas que permite o bloqueio de tela com um toque semelhante ao atalho de teclado do Windows-L: 

1.  Toque e segure ou clique com o botão direito do mouse na área de trabalho, selecione **novo**  >  **atalho**  >  **navegar**na  >  **área de trabalho**  >  **OK**  >  **Avançar**.

1.  Forneça um nome para o atalho, como **bloquear meu PC**e, em seguida, selecione **concluir**.

1.  Clique com o botão direito do mouse ou toque e mantenha pressionado o atalho recém-criado na área de trabalho e selecione **Propriedades**. Na guia **atalho** , insira o seguinte no campo de **destino** : **Rundll32.exe User32.dll, LockWorkStation**

1.  Selecione o botão **Alterar ícone** e navegue até **C:\Windows\System32\imageres.dll** e selecione um ícone para usar. 

    Veja o exemplo a seguir:

    ![Escolher um ícone](images/lock.png)
    
1.  Selecione **OK** para salvar o atalho.

1.  Clique com o botão direito do mouse ou toque e segure o atalho e selecione **fixar na barra de tarefas**.

1. Depois de fixar o atalho de bloqueio à barra de tarefas, você pode excluí-lo da área de trabalho.

## Aplicativos


### Microsoft Whiteboard

Para instalar o Microsoft whiteboard:

 - Selecione o ícone do **espaço de trabalho do Windows Ink** no canto inferior direito da barra de tarefas e baixe o **whiteboard**.
 
   ![Espaço de trabalho à tinta](images/ink.png) 

Você também pode instalar o whiteboard na Microsoft Store:

1. Abra o aplicativo da Microsoft Store e pesquise por **whiteboard**.

2. Escolha **não graças** para entrar e usar entre dispositivos.

3. Fixar quadro de comunicações na barra de tarefas.

### Aplicativo Surface

1. Na Microsoft Store, procure por **Surface**.

2. Defina o filtro **disponível em** **todos os dispositivos**.

3. Instale o aplicativo **Surface** . Este deve ser o primeiro aplicativo listado. Talvez seja necessário associar o MSA à loja para instalar o aplicativo.

4. Fixar o aplicativo **Surface** à barra de tarefas.

### Captura e Esboço

1. Abra o aplicativo **corte & esboço** e fixe-o na barra de tarefas.

2. Selecione as reticências no canto superior direito e selecione **configurações**.

3. Em **configurações**, ative **a cópia automática para a área de transferência**, **salve recortes**e **várias janelas** (opcional).

### Microsoft Office

1. Abra o <a href="https://portal.office.com/account#installs" target="_blank"> portal do Office </a> e instale os aplicativos desejados.

2. Fixar aplicativos do Office desejados na barra de tarefas.

3. Se o Outlook estiver instalado, certifique-se de definir o OST do Outlook para salvar somente as últimas duas últimas semanas do cache. Isso reduzirá consideravelmente o uso do disco e o tempo de configuração.

    - Selecione **File**  >  **configurações de conta** de arquivo e selecione sua conta.
    
    - Selecione **alterar** e defina o controle deslizante para **usar o modo cache do Exchange** como 14 dias.

### Microsoft Teams

1. Baixe e instale <a href="https://teams.microsoft.com/downloads" target="_blank"> o Microsoft Teams </a> .

2. Definir configurações para iniciar o aplicativo automaticamente (opcional).

3. Fixar equipes na barra de tarefas.

4. Considere reduzir as notificações do Microsoft Teams no dispositivo para evitar distrações (opcional).

   ![Notificações do teams](images/teams.png)

### Conectar o aplicativo

> [!IMPORTANT]
> No Windows 10, versão 2004 e posterior, a projeção conectar aplicativo para conexão sem fio que usa Miracast não é instalada por padrão, mas está disponível como um recurso opcional. Se você instalou (ou atualizou para) a versão 2004 ou posterior do Windows, poderá ver o seguinte na tela projetando a this PC em configurações:

![Projeto para este PC](images/sh2-project.png) 


1. Para instalar o aplicativo na página de configurações "Projetando para este PC", selecione **recursos opcionais**  >  **Adicionar um recurso** e instalar o aplicativo de **exibição sem fio** .

2. Em **alguns dispositivos Windows e Android podem projetar neste computador quando você disser que está ok**, escolha:

    - **Disponível em qualquer lugar** se o dispositivo não estiver em uma rede corporativa.
    - Caso contrário, escolha **disponível em todos os lugares em redes seguras**.
    
3. Em **pedir projeto para este PC**, escolha **primeira vez apenas**.

4. Em **exigir PIN para emparelhamento**, escolha **nunca**.

5. Para iniciar o aplicativo e fixá-lo na barra de tarefas, procure **Connect**.

6. Abra o aplicativo. Enquanto o aplicativo estiver aberto, clique com o botão direito do mouse no ícone conectar aplicativo na barra de tarefas e selecione **fixar na barra de tarefas**.

7. Em seguida, feche o aplicativo conectar. O **Project para este computador** pode não funcionar a menos que o aplicativo tenha sido executado pelo menos uma vez.

Configuração recomendada quando não estiver na rede corporativa:

![Configurações em casa](images/project1.png)

Configuração recomendada na rede corporativa:

![Configurações no trabalho](images/project2.png)

### Seu Telefone

O aplicativo de **telefone** é instalado por padrão no Windows 10. Se não estiver presente, você também poderá instalá-lo na Windows Store.

Para obter informações sobre como configurar o aplicativo, consulte <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> como configurar seu telefone no Windows 10 e sincronizar dados entre seu PC e telefone </a> . Veja também <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> como corrigir problemas comuns com o aplicativo de telefone no Windows 10 </a> .

###  Zonas decorativas


As **zonas decorativas** fazem parte de uma coleção de ferramentas chamadas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> no github. É uma ótima maneira de usar o estado real da tela em um Surface Hub 2 oferecendo a você a capacidade de definir layouts fixos em seu vídeo ("zonas") e, em seguida, selecionar qual aplicativo será executado em cada zona. 


O [wiki do PowerToy](https://github.com/microsoft/PowerToys/wiki) tem instruções sobre como usar e personalizar cada ferramenta, incluindo o [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). Em um nível alto – após a instalação do PowerToys, você pode selecionar ou criar um layout personalizado e, em seguida, manter a tecla Shift pressionada e arrastar ou usar as teclas do teclado para mover um aplicativo em execução para zonas específicas. Usar um teclado Bluetooth ou USB e um mouse ajudará com isso, ou você pode usar o teclado virtual e o touchpad.

**Dicas do Power Toys**
- Para receber notificações por email de atualizações de versão do PowerToy no GitHub, clique no botão "inscrição" na parte superior da [página](https://github.com/microsoft/PowerToys/releases).
- Após a instalação do PowerToys, você pode receber notificações do Windows e/ou baixar e instalar as atualizações mais recentes configurando as configurações do PowerToys **baixar atualizações automaticamente** para ativado.
- Para acessar as configurações do PowerToys, selecione a guia up Carat **executando aplicativos** na barra de tarefas e clique com o botão direito do mouse ou pressione e mantenha pressionado o ícone do PowerToys até que o menu seja exibido. Selecione "configurações".
- Na parte inferior da página de configurações do PowerToy, ative o **download de atualizações automaticamente** para ativado.
- Quando uma atualização for liberada, uma notificação do Windows será exibida oferecendo a opção de quando instalar a atualização.


### Navegador do Edge Chromium

Baixe e instale o novo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> navegador Chromium do Edge </a> .


### Ferramenta de diagnóstico de hardware do Surface Hub

A <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> ferramenta de diagnóstico de hardware do Surface Hub </a> disponível gratuitamente na Microsoft Store. A ferramenta foi projetada para ajudar você a garantir que seu Surface Hub esteja se apresentando o melhor. Ele contém testes para determinar se o seu firmware está atualizado e configurado corretamente. Testes interativos permitem que você confirme que a funcionalidade essencial está funcionando conforme esperado. Se forem encontrados problemas, os resultados poderão ser salvos e compartilhados com a equipe de suporte do Surface Hub. Clique no link para instalá-lo na Microsoft Store e, em seguida, fixe o aplicativo na barra de tarefas.

## Configurações adicionais

### Cauda da caneta selecione para iniciar o quadro de comunicações

1. Procure **caneta** e selecione **caneta & configurações de tinta do Windows**.

2. Próximo à parte inferior da página, em **atalhos de caneta** , defina **selecionar uma vez** para o **Microsoft whiteboard**. 

### Gerenciamento de energia

Há várias configurações de energia disponíveis para obter a melhor experiência com o Windows 10 pro ou Enterprise no Surface Hub 2. Isso inclui tempos limite de tela e do PC e como eles interagem com a detecção de presença humana (Doppler) interna, a proteção de tela e a proteção por senha e, em seguida, se for apropriado como passar configurações de energia de política de grupo para usuários de laptop/desktop.

O Windows 10 pro ou Enterprise no Surface Hub 2 mantém a tela de entrar no estado de suspensão por ações de toque, mouse e teclado, além da detecção de ocupação humana interna (Doppler). A detecção de ocupação humana é habilitada por padrão, mas, se desejado, pode ser desabilitada na UEFI alternando a opção de dispositivo na ferramenta configurador UEFI do Surface como parte da migração inicial ou criando e aplicando um pacote de configuração UEFI mais recente. 

**Gerenciamento de energia: configurações de tela e suspensão do computador**

1. Selecione **Iniciar**  >  **configurações**  >  **sistema**  >  **alimentação & suspender**.

2. Defina o controle deslizante do modo de energia para **obter o melhor desempenho**.

3. Configure os valores de tela e de repouso para sua preferência enquanto também faz a Doppler de detecção de presença do que ativa o dispositivo quando o movimento é detectado. Portanto, como prática recomendada, é recomendável definir a tela para desligar **após 2 horas** e o computador para **desligar após 4 horas.**

**Gerenciamento de energia: proteção de tela**

1. Pesquisar a **tela de bloqueio** e abrir **as configurações da tela de bloqueio**.

2. Defina **as configurações de tempo limite de tela** e **as configurações de proteção de tela** para sua preferência. Os valores padrão recomendados são:

   - Proteção de tela para (nenhum) ou uma proteção de tela de sua escolha.
   - Tempo de espera para 15 minutos.
   - Ao continuar, exiba a tela de logon.


**Gerenciamento de energia: política de grupo**

Antes de executar o procedimento a seguir, verifique com seu departamento de ti para aprovação para excluir um dispositivo Surface Hub 2S da política global de gerenciamento de energia. Algumas configurações de gerenciamento de energia podem desabilitar a função de detecção de presença.

1. Procure pela **central de software** e abra-a.

2. Selecione **Opções**.

3. Expanda o **Gerenciamento de energia**  e selecione **não aplicar configurações de energia do meu departamento de ti para este computador**.

   ![Configurações de software](images/soft-cntr.png)

### Sensor de armazenamento

O Surface Hub 2 tem uma SSD de 128 GB para armazenamento local, portanto, é necessário considerar o uso das medidas de salvamento de armazenamento durante o uso normal.  Para configurar o sensor de armazenamento:

1.  Procure **configurações de armazenamento**, que se encontra em **configurações do sistema**.

2.  Em **configurações**, selecione **ativar o sensor de armazenamento** para abrir a página Configurações de **armazenamento** .

3.  Mude o sensor de armazenamento para **ligado**.

4.  Selecione **Configurar o sensor de armazenamento ou executá-lo agora** e defina as configurações para manter os arquivos online o máximo possível (devido a espaço limitado na unidade).

Configurações recomendadas:

- Executar detecção de armazenamento = todos os dias.
- Exclua os arquivos temporários que os meus aplicativos não estão usando = a cada 14 dias (pelo menos).
- Exclua os arquivos na pasta Meus downloads se eles estiverem lá por mais de = 30 dias.
- OneDrive: o conteúdo ficará online apenas se não for aberto por mais de 30 dias.

### Modo tablet

Ative o modo tablet, se quiser, para atender às necessidades de acessibilidade.


### Configurações de som

1. Procure **configurações de sons** e abra esta página.

2. Selecione o **painel de controle de som** à direita e selecione a guia **sons** .

3. Em **eventos do programa** , defina **conexão do dispositivo** e **dispositivo desconectar** para **nenhum**.

### Notificações de silêncio

1. Pesquise o **Assistente de foco** e abra esta página.

2. Selecione **apenas alarmes**. Isso evitará submenus de notificação constante.

### Limpeza de Disco

1. Procure por **limpeza de disco** e abra este aplicativo.

2. Em **arquivos a serem excluídos**, selecione os arquivos que você deseja excluir. 

3. Além disso, selecione **limpar arquivos do sistema**.

## Concluir e verificar

1. Procure e instale todas as atualizações do Windows.

2. Atualize a política de grupo.

   1. Em um prompt de comando elevado, digite **gpupdate/force/boot/Wait: 0**.
   
3. Reinicie o dispositivo.

4. Verifique os aplicativos da barra de tarefas.

   - Conectar o aplicativo
   - Ícone de cadeado
   - Captura e Esboço
   - Equipes (se aplicável)
   - Aplicativos do Office (se aplicável)
   - Aplicativo Surface
   - Quadro de Comunicações
    
5. Verificar a detecção de presença.

   - A detecção de presença será um ícone verde na bandeja do sistema.
    
6. Verifique se a projeção neste computador está habilitada com o aplicativo conectar. Depois de configurar o  **Project para estas** configurações do computador, execute o aplicativo conectar pelo menos uma vez. (Subsequentemente, o aplicativo de conexão não precisa estar em execução para projetar para o Surface Hub.)

7. Verifique as configurações de energia e suspensão.

    - Proteção de tela: 15 minutos, definir como (nenhum), polígonos ou ficar em branco; Verifique se a caixa de seleção Requer senha está selecionada.
    - Tela: **desative após 2 horas**.
    - PC:  **desative após 4 horas**.
    
8. Verifique se o Windows Hello está funcionando.

9. Verifique se a sincronização suas configurações está desabilitada.

10. Verifique os aplicativos de inicialização.

> [!TIP]
> Após a instalação e a configuração do Windows 10, o Surface Hub 2S pode ser gerenciado assim como qualquer outro dispositivo com o Windows 10.

## Tópicos relacionados

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2</a>
