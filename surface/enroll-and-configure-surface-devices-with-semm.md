---
title: Registrar e configurar dispositivos Surface com SEMM (Surface)
description: Saiba como criar um pacote de configuração de controle de superfície de superfície para controlar as configurações do Surface UEFI, bem como registrar um dispositivo Surface no SEMM.
keywords: gerenciamento de superfície empresarial
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 183eceee47eba8b8d1e794e9e7d3efffa7a9b2e0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830590"
---
# Registrar e configurar dispositivos Surface com o SEMM

Com o modo de gerenciamento do Microsoft Surface Enterprise (SEMM), você pode definir com segurança as configurações da superfície UEFI em um dispositivo Surface e gerenciar essas configurações em dispositivos Surface em sua organização. Quando um dispositivo de superfície é gerenciado pelo SEMM, esse dispositivo é considerado *registrado* (às vezes chamado de ativado). Este artigo mostra como criar um pacote de configuração do Surface UEFI que não só controlará as configurações de controle de falha da superfície, mas também registrará um dispositivo Surface no SEMM.

Para obter uma visão geral de alto nível do SEMM, consulte [modo de gerenciamento do Microsoft Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Um método simplificado de gerenciamento do firmware da nuvem no Surface Pro 7, Surface Pro X e Surface laptop 3 já está disponível via visualização pública. Para obter mais informações, consulte [Gerenciamento do Intune de configurações de Surface UEFI](surface-manage-dfci-guide.md).

> [!NOTE]
> O SEMM tem suporte no Surface Pro X por meio do Gerenciador UEFI. Para obter mais informações, consulte [implantação, gerenciamento e manutenção do Surface Pro X](surface-pro-arm-app-management.md).

#### Baixar e instalar o Microsoft Surface UEFI Configuration
A ferramenta usada para criar pacotes SEMM é o Microsoft Surface UEFI Configurator. Você pode baixar o configurador UEFI da Microsoft Surface na página [Surface Tools para it](https://www.microsoft.com/download/details.aspx?id=46703) no centro de download da Microsoft.
Execute o arquivo do Windows Installer (. msi) do Microsoft Surface UEFI para iniciar a instalação da ferramenta. Quando o instalador for concluído, localize o Microsoft Surface UEFI Configurator na seção todos os aplicativos do menu iniciar.

>[!NOTE]
>O Microsoft Surface UEFI Configurator tem suporte somente no Windows 10.

## Criar um pacote de configuração do Surface UEFI

O pacote de configuração do Surface UEFI executa a função de aplicação de uma nova configuração de configurações da Surface UEFI a um dispositivo Surface gerenciado com SEMM e a função de registrar dispositivos Surface no SEMM. A criação de um pacote de configuração exige que você tenha um certificado de autenticação para ser usado com o SEMM para proteger a configuração das configurações de UEFI em cada dispositivo Surface. Para obter mais informações sobre os requisitos do certificado SEMM, consulte [modo de gerenciamento do Microsoft Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Para criar um pacote de configuração do Surface UEFI, siga estas etapas:

1. Abra o Microsoft Surface UEFI configurate a partir do menu iniciar.
2. Clique em **Iniciar**.
3. Clique em **pacote de configuração**, conforme mostrado na Figura 1.

   ![Criar um pacote para registro SEMM](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figura 1. Selecione pacote de configuração para criar um pacote para registro e configuração do SEMM*

4. Clique em **proteção de certificado** para adicionar o arquivo de certificado exportado à chave privada (. pfx), conforme mostrado na Figura 2. Navegue até o local do seu arquivo de certificado, selecione o arquivo e clique em **OK**.

   ![Adicionar a senha SEM certificado e a senha UEFI de superfície ao pacote de configuração](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *Figura 2. Adicionar o certificado SEMM e a senha UEFI de superfície a um pacote de configuração do Surface UEFI*

5. Quando for solicitado a confirmar a senha do certificado, digite e confirme a senha do seu arquivo de certificado e clique em **OK**.
6. Clique em **proteção por senha** para adicionar uma senha à UEFI da superfície. Esta senha será necessária sempre que você inicializar o UEFI. Se essa senha não for inserida, somente as páginas **informações do computador**, **sobre**o **gerenciamento corporativo**e de **saída** serão exibidas. Esta etapa é opcional.
7. Quando solicitado, digite e confirme a senha escolhida para a UEFI e clique em **OK**. Se você quiser limpar uma senha UEFI de superfície existente, deixe o campo de senha em branco.
8. Se você não quiser que o pacote de UEFI da superfície se aplique a um dispositivo específico, na página **escolha qual tipo de superfície deseja direcionar** , clique no controle deslizante abaixo do livro de superfície ou da superfície do Surface Pro 4 correspondente para que esteja na posição **desativado** . (Conforme mostrado na Figura 3.)
   > [!NOTE] 
   > Você deve selecionar um dispositivo, pois nenhum está selecionado por padrão.

   ![Escolher dispositivos para a compatibilidade do pacote](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *Figura 3. Escolher os dispositivos para a compatibilidade do pacote*

9. Clique em **Avançar**.
10. Se você quiser desativar um componente em dispositivos de superfície gerenciados, na página **escolher quais componentes você deseja ativar ou desativar** , clique no controle deslizante ao lado de qualquer dispositivo ou grupo de dispositivos que você deseja desativar para que o controle deslizante fique na posição **desativado** . (Mostrado na Figura 4.) A configuração padrão de cada dispositivo está **ligada**. Clique no botão **Redefinir** se desejar retornar todos os controles deslizantes para a posição padrão.

    ![Desabilitar ou habilitar componentes de superfície](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figura 4. Desabilitar ou habilitar componentes de superfície individuais*

11. Clique em **Avançar**.
12. Para habilitar ou desabilitar as opções avançadas em UEFI ou a exibição de páginas UEFI de controle de superfície, na página **escolher as configurações avançadas para seus dispositivos** , clique no controle deslizante ao lado da configuração desejada para configurar essa opção como **ativado** ou **desativado** (mostrada na Figura 5). Na seção de **página inicial da UEFI** , você pode usar os controles deslizantes para **segurança**, **dispositivos**e **inicialização** para controlar quais páginas estão disponíveis para os usuários que inicializam em uma UEFI. (Para obter mais informações sobre as configurações de Surface UEFI, consulte [gerenciar configurações](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)de controle de superfície.) Clique em **Compilar** quando terminar de selecionar as opções para gerar e salvar o pacote.

    ![Controlar configurações UEFI de superfície avançada e páginas UEFI de superfície](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figura 5. Controlar configurações de controle de superfície avançada e páginas UEFI de superfície com SEMM*

13. Na caixa de diálogo **salvar como** , especifique um nome para o pacote de configuração de UEFI de Surface, navegue até o local onde deseja salvar o arquivo e clique em **salvar**.
14. Quando o pacote for criado e salvo, a página **bem-sucedida** será exibida.

>[!NOTE]
>Grave os caracteres de impressão digital de certificado que são exibidos nesta página, conforme mostrado na Figura 6. Você precisará desses caracteres para confirmar a inscrição de novos dispositivos de superfície no SEMM. Clique em **concluir** para concluir a criação do pacote e feche o Microsoft Surface UEFI Configuration.

![Exibição de caracteres de impressão digital do certificado](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*Figura 6. Os dois últimos caracteres da impressão digital do certificado são exibidos na página com êxito*

Agora que você criou seu pacote de configuração do Surface UEFI, você pode registrar ou configurar dispositivos Surface.

>[!NOTE]
>Quando um pacote de configuração de Surface UEFI é criado, um arquivo de log é criado na área de trabalho com detalhes das configurações e opções do pacote de configuração.

## Registrar um dispositivo de superfície no SEMM
Quando o pacote de configuração do Surface UEFI é executado, os arquivos de configuração do certificado SEMM e do Surface UEFI são testados no armazenamento de firmware do dispositivo de superfície. Quando o dispositivo de superfície é reinicializado, o Surface UEFI processa esses arquivos e inicia o processo de aplicação da configuração de UEFI de superfície ou registro do dispositivo de superfície no SEMM, conforme mostrado na Figura 7.

![Processo de SEMM para configuração de configuração de superfície ou registro](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figura 7. O processo SEMM para configuração do Surface UEFI ou da inscrição de um dispositivo Surface*

Antes de começar o processo para registrar um dispositivo de superfície no SEMM, verifique se você tem os dois últimos caracteres da impressão digital de certificado disponível. Você precisará desses caracteres para confirmar o registro do dispositivo (veja a Figura 6).

Para registrar um dispositivo de superfície no SEMM com um pacote de configuração do Surface UEFI, siga estas etapas:

1. Execute o arquivo. msi do pacote de configuração do Surface UEFI no dispositivo de superfície que você deseja cadastrar no SEMM. Isso fará com que o arquivo de configuração da Surface UEFI seja provisionado no firmware do dispositivo.
2. Marque a caixa de seleção **aceito os termos do contrato de licença** para aceitar o contrato de licença de usuário final (EULA) e clique em **instalar** para iniciar o processo de instalação.
3. Clique em **concluir** para concluir a instalação do pacote de configuração do Surface UEFI e reinicie o dispositivo de superfície quando solicitado.
4. O Surface UEFI carregará o arquivo de configuração e determinará que o SEMM não está habilitado no dispositivo. A UEFI da superfície iniciará o processo de registro SEMM da seguinte maneira:
   * A UEFI da superfície verificará se o arquivo de configuração SEMM contém um certificado SEMM.
   * A UEFI da superfície solicitará que você insira os dois últimos caracteres da impressão digital do certificado para confirmar o registro do dispositivo Surface no SEMM, conforme mostrado na Figura 8.

      ![O registro SEMM requer os dois últimos caracteres da impressão digital do certificado](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figura 8. O registro no SEMM requer os dois últimos caracteres da impressão digital do certificado*

   * A UEFI da superfície armazenará o certificado SEMM no firmware e aplicará as definições de configuração especificadas no arquivo de configuração da Surface UEFI.
   
5. O dispositivo de superfície agora está registrado no SEMM e será inicializado no Windows.

Você pode verificar se um dispositivo Surface foi registrado com êxito no SEMM procurando o pacote de configuração do **Surface da Microsoft** em **programas e recursos** (conforme mostrado na Figura 9) ou nos eventos armazenados no log do **Microsoft Surface UEFI Configuration** , encontrado em **logs de aplicativos e serviços** no Visualizador de eventos (conforme mostrado na Figura 10).

![Verificar a inscrição do dispositivo de superfície no SEMM em programas e recursos](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*Figura 9. Verificar a inscrição de um dispositivo de superfície no SEMM em programas e recursos*

![Verificar o registro do dispositivo de superfície no SEMM no Visualizador de eventos](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*Figura 10. Verificar a inscrição de um dispositivo de superfície no SEMM no Visualizador de eventos*

Você também pode verificar se o dispositivo está registrado no SEMM no Surface UEFI – enquanto o dispositivo está registrado, a UEFI da superfície contém a página de **Gerenciamento da empresa** (conforme mostrado na Figura 11).

![Página de gerenciamento empresarial da Surface UEFI](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*Figura 11. Página de gerenciamento empresarial da Surface UEFI*


## Definir configurações de Surface UEFI com SEMM

Depois que um dispositivo é registrado no SEMM, você pode executar os pacotes de configuração do Surface UEFI assinados com o mesmo certificado SEMM para aplicar as novas configurações de Surface UEFI. Essas configurações serão aplicadas automaticamente na próxima vez que o dispositivo for inicializado, sem qualquer interação do usuário. Você pode usar as soluções de implantação de aplicativos como o Microsoft Endpoint Configuration Manager para implantar pacotes de configuração do Surface UEFI em dispositivos de superfície para alterar ou gerenciar as configurações no Surface UEFI.

Para obter mais informações sobre como implantar arquivos do Windows Installer (. msi) com o Configuration Manager, consulte [implantar e gerenciar aplicativos com o Gerenciador de configuração do Microsoft Endpoint](https://technet.microsoft.com/library/mt627959).

Se você tiver uma senha UEFI com uma senha, os usuários sem a senha que tentarem inicializar no Surface UEFI só terão as **informações do computador**, **sobre**as páginas de **gerenciamento corporativo**e de **saída** exibidas para elas.

Se você não tiver protegido a UEFI da superfície com uma senha ou um usuário digitar a senha corretamente, as configurações que são configuradas com o SEMM ficarão esmaecidas (indisponíveis) e o texto que algumas configurações são gerenciadas pela sua organização serão exibidos na parte superior da página, conforme mostrado na Figura 12.

![Configurações gerenciadas pelo SEMM desabilitado no Surface UEFI](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*Figura 12. As configurações gerenciadas pelo SEMM serão desabilitadas no Surface UEFI*
