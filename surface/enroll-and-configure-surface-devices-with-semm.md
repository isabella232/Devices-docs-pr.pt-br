---
title: Registrar e configurar dispositivos Surface com SEMM (Surface)
description: Saiba como criar um pacote de configuração UEFI do Surface para controlar as configurações da UEFI do Surface, bem como registrar um dispositivo Surface no SEMM.
keywords: surface enterprise management
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: hachinda
manager: laurawi
ms.date: 1/15/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 6df11e1c6e0b28616cb4d365e159f134195c0ecb
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472345"
---
# <a name="enroll-and-configure-surface-devices-with-semm"></a>Registrar e configurar dispositivos Surface com o SEMM

Com o Microsoft Surface Enterprise Management Mode (SEMM), você pode definir com segurança as configurações do UEFI do Surface em um dispositivo Surface e gerenciar essas configurações em dispositivos Surface em sua organização. Quando um dispositivo Surface é gerenciado pelo SEMM, esse dispositivo é considerado *registrado* (às vezes chamado de ativado). Este artigo mostra como criar um pacote de configuração UEFI do Surface que controlará as configurações da UEFI do Surface e registrará um dispositivo Surface no SEMM.

Para obter uma visão geral mais de alto nível do SEMM, consulte [o Microsoft Surface Enterprise Management Mode](surface-enterprise-management-mode.md).

Como alternativa ao SEMM, os dispositivos Surface mais recentes dão suporte ao gerenciamento remoto de um subconjunto de configurações de firmware por meio Microsoft Intune. Para obter mais informações, consulte [Intune gerenciamento de configurações uefi do Surface](surface-manage-dfci-guide.md).

> [!NOTE]
> O SEMM tem suporte no Surface Pro X somente por meio do Gerenciador de UEFI. Para obter mais informações, consulte [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).

#### <a name="download-and-install-microsoft-surface-uefi-configurator"></a>Baixar e instalar o Microsoft Surface UEFI Configurator

A ferramenta usada para criar pacotes SEMM é o Microsoft Surface UEFI Configurator. Você pode baixar o Microsoft Surface UEFI Configurator na página [Ferramentas do Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) no Centro de Download da Microsoft.
Execute o arquivo do Microsoft Surface UEFI Configurator Windows (.msi) para iniciar a instalação da ferramenta. Quando o instalador for concluído, localize o Microsoft Surface UEFI Configurator na seção Todos os Aplicativos do seu menu Iniciar.

>[!NOTE]
>O Microsoft Surface UEFI Configurator tem suporte apenas Windows 10 e Windows 11.

## <a name="create-a-surface-uefi-configuration-package"></a>Criar um pacote de configuração UEFI do Surface

O pacote de configuração UEFI do Surface executa a função de aplicar uma nova configuração das configurações uefi do Surface a um dispositivo Surface gerenciado com SEMM e a função de registrar dispositivos Surface no SEMM. A criação de um pacote de configuração exige que você tenha um certificado de assinatura a ser usado com o SEMM para proteger a configuração das configurações de UEFI em cada dispositivo Surface. Para obter mais informações sobre os requisitos para o certificado SEMM, consulte [Microsoft Surface Enterprise Management Mode](surface-enterprise-management-mode.md).

Para criar um pacote de configuração UEFI do Surface, siga estas etapas:

1. Abra o Microsoft Surface UEFI Configurator no menu Iniciar.

2. Clique em **Iniciar**.

3. Clique **em Pacote de** Configuração, conforme mostrado na Figura 1.

   ![Crie um pacote para o registro do SEMM.](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figura 1. Selecione Pacote de Configuração para criar um pacote para registro e configuração do SEMM*

4. Clique **em Proteção de** Certificado para adicionar o arquivo de certificado exportado com chave privada (.pfx), conforme mostrado na Figura 2. Navegue até o local do arquivo de certificado, selecione o arquivo e clique em **OK**.

   ![Adicione o certificado SEM e a senha UEFI do Surface ao pacote de configuração.](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to the configuration package")

   *Figura 2. Adicionar o certificado SEMM e a senha UEFI do Surface ao pacote de configuração UEFI do Surface*

5. Quando solicitado a confirmar a senha do certificado, insira e confirme a senha do arquivo de certificado e clique em **OK**.

6. Clique **em Proteção de** Senha para adicionar uma senha à UEFI do Surface. Essa senha será necessária sempre que você inicializar para UEFI. Se essa senha não for inserida, somente as informações do **computador**, **sobre**, **Enterprise** gerenciamento e páginas **de** saída serão exibidas. Esta etapa é opcional.

7. Quando solicitado, insira e confirme a senha escolhida para a UEFI do Surface e clique em **OK**. Deixe o campo de senha em branco se quiser limpar uma senha UEFI do Surface existente.

8. Se você não quiser que o pacote UEFI do Surface seja aplicado a um dispositivo específico, na página Escolher qual tipo do **Surface** você deseja direcionar, clique no controle deslizante abaixo do dispositivo correspondente para que ele esteja na **** posição Desativado, conforme mostrado na Figura 3.
   > [!TIP] 
   > Você deve selecionar um dispositivo, pois nenhum está selecionado por padrão. Role para a direita para exibir todos os dispositivos disponíveis.

   ![Escolha dispositivos para compatibilidade de pacote e role para a direita para exibir todos os dispositivos disponíveis](images/surface-semm-enroll-fig3.png "Choose devices for package compatibility")

   ![Escolha dispositivos para compatibilidade de pacote.](images/surface-semm-enroll-fig3a.png "Choose devices for package compatibility")


   *Figura 3. Escolher os dispositivos para compatibilidade de pacote*

9. Clique em **Avançar**.

10. Se você quiser desativar um componente em dispositivos Surface gerenciados, na página Escolher quais componentes deseja ativar ou **desativar**, clique no controle deslizante ao lado de qualquer dispositivo ou grupo de dispositivos que você deseja desativar para que o controle deslizante esteja na posição Desativada.**** (Mostrado na Figura 4.) A configuração padrão para cada dispositivo é **Ativado**. Clique no **botão Redefinir** para retornar todos os controles deslizantes para a posição padrão.

    ![Desabilitar ou habilitar componentes do Surface.](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figura 4. Desabilitar ou habilitar componentes individuais do Surface*

11. Clique em **Avançar**.

12. Para habilitar ou desabilitar opções avançadas no Surface UEFI ou na exibição de páginas UEFI do Surface, na página Escolher as configurações **avançadas para seus dispositivos**, clique no controle deslizante ao lado **** da configuração desejada para definir essa opção como Ativado ou **Desativado (mostrado** na Figura 5). Na seção **UeFI Front Page**, você pode usar os controles deslizantes para **Segurança, Dispositivos** e Inicialização para controlar quais páginas estão disponíveis para os usuários que inicializam no Surface UEFI. ******** (Para obter mais informações sobre as configurações de UEFI do Surface, consulte [Gerenciar configurações de UEFI do Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) Quando terminar de selecionar as opções para gerar e salvar o pacote, clique em **Compilar**. 

    ![Controlar configurações avançadas de UEFI do Surface e páginas UEFI do Surface.](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figura 5. Controlar configurações avançadas de UEFI do Surface e páginas UEFI do Surface com SEMM*

13. Na caixa **de diálogo Salvar como** , especifique o nome do pacote de configuração uefi do Surface, navegue até o local onde você deseja salvar o arquivo e clique em **Salvar**.

14. Quando o pacote é criado e salvo, a **página** Bem-sucedida é exibida.

    >[!NOTE]
    >Registre os caracteres de impressão digital do certificado exibidos nesta página, conforme mostrado na Figura 6. Você precisará desses caracteres para confirmar o registro de novos dispositivos Surface no SEMM. Clique **em Encerrar** para concluir a criação do pacote e feche o Microsoft Surface UEFI Configurator.
    
    ![Exibição de caracteres de impressão digital do certificado.](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")
    
    *Figura 6. Os dois últimos caracteres da impressão digital do certificado são exibidos na página Êxito*

Agora que você criou o pacote de configuração uefi do Surface, você pode registrar ou configurar dispositivos Surface.

>[!NOTE]
>Quando um pacote de configuração UEFI do Surface é criado, um arquivo de log é exibido na área de trabalho com detalhes das configurações e das opções do pacote de configuração.

## <a name="enroll-a-surface-device-in-semm"></a>Registrar um dispositivo Surface no SEMM
Quando o pacote de configuração UEFI do Surface é executado, o certificado SEMM e os arquivos de configuração UEFI do Surface são preparados no armazenamento de firmware do dispositivo Surface. Quando o dispositivo Surface é reinicializado, a UEFI do Surface processa esses arquivos e inicia o processo de aplicar a configuração uefi do Surface ou registrar o dispositivo Surface no SEMM, conforme mostrado na Figura 7.

![Processo semm para configuração de UEFI ou registro do Surface.](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figura 7. O processo semm para configuração do UEFI surface ou registro de um dispositivo Surface*

Antes de registrar um dispositivo Surface no SEMM, verifique se você tem os dois últimos caracteres da impressão digital do certificado em mãos. Você precisará desses caracteres para confirmar o registro do dispositivo (consulte a Figura 6).

Para registrar um dispositivo Surface no SEMM com um pacote de configuração UEFI do Surface, siga estas etapas:

1. Execute o pacote de configuração uefi do Surface .msi arquivo no dispositivo Surface que você deseja registrar no SEMM. Isso provisionará o arquivo de configuração UEFI do Surface no firmware do dispositivo.
2. Selecione os **termos aceito na** caixa de seleção Contrato de Licença para aceitar o EULA (Contrato de Licença de Usuário Final) e **** clique em Instalar para iniciar o processo de instalação.
3. Clique **em Concluir** para concluir a instalação do pacote de configuração uefi do Surface e reinicie o dispositivo Surface quando for solicitado a fazer isso.
4. A UEFI do Surface carregará o arquivo de configuração e determinará que o SEMM não está habilitado no dispositivo. Em seguida, a UEFI do Surface iniciará o processo de registro do SEMM, da seguinte maneira:
   * A UEFI do Surface verificará se o arquivo de configuração SEMM contém um certificado SEMM.
   * A UEFI do Surface solicitará que você insira os dois últimos caracteres da impressão digital do certificado para confirmar o registro do dispositivo Surface no SEMM, conforme mostrado na Figura 8.

      ![O registro semm requer os dois últimos caracteres da impressão digital do certificado.](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figura 8. O registro semm requer os dois últimos caracteres da impressão digital do certificado*

   * A UEFI do Surface armazenará o certificado SEMM no firmware e aplicará as definições de configuração especificadas no arquivo de configuração UEFI do Surface.
   
5. O dispositivo Surface agora está registrado no SEMM e será inicializado para Windows.

Você pode verificar se um dispositivo Surface foi registrado com êxito no SEMM procurando o Pacote de Configuração do **Microsoft Surface** em Programas e **Recursos (conforme** mostrado na Figura 9) ou nos eventos armazenados no log do **Microsoft Surface UEFI Configurator**, encontrado em Logs **** de Aplicativos e Serviços no Visualizador de Eventos (conforme mostrado na Figura 10).

:::image type="content" alt-text="Verifique o registro do dispositivo Surface no SEMM em Programas e Recursos." source="images/surface-semm-enroll-fig9.png":::

*Figura 9. Verificar o registro de um dispositivo Surface no SEMM em Programas e Recursos*

:::image type="content" alt-text="Verifique o registro do dispositivo Surface no SEMM Visualizador de Eventos." source="images/surface-semm-enroll-fig10.png":::

*Figura 10. Verificar o registro de um dispositivo Surface no SEMM no Visualizador de Eventos*

Você também pode verificar se o dispositivo está registrado no SEMM no Surface UEFI – enquanto o dispositivo está registrado, a UEFI do Surface conterá a página de gerenciamento do Enterprise (conforme mostrado **na** Figura 11).

:::image type="content" alt-text="Página de gerenciamento Enterprise UEFI do Surface." source="images/surface-semm-enroll-fig11.png":::

*Figura 11. A página de gerenciamento Enterprise UEFI do Surface*


## <a name="configure-surface-uefi-settings-with-semm"></a>Definir configurações de UEFI do Surface com SEMM

Depois que um dispositivo é registrado no SEMM, você pode executar pacotes de configuração UEFI do Surface assinados com o mesmo certificado SEMM para aplicar novas configurações de UEFI do Surface. Essas configurações são aplicadas automaticamente na próxima vez que o dispositivo for inicializado, sem nenhuma interação do usuário. Você pode usar soluções de implantação de aplicativo como Microsoft Endpoint Configuration Manager para implantar pacotes de configuração uefi do Surface em dispositivos Surface para alterar ou gerenciar as configurações no UeFI do Surface.

Para obter mais informações sobre como implantar arquivos Windows Installer (.msi) com o Configuration Manager, consulte [Implantar](/mem/configmgr/apps/deploy-use/deploy-applications) e gerenciar aplicativos com Microsoft Endpoint Configuration Manager.

Suponha que você tenha protegido a UEFI do Surface com uma senha. Nesse caso, os usuários sem **a** senha que tentarem inicializar para a UEFI do Surface terão apenas as informações do **computador, Sobre****, Enterprise** gerenciamento e páginas **** de saída exibidas para eles.

Se você não tiver protegido a UEFI do Surface com uma senha ou se um usuário inserir a senha corretamente, as configurações definidas com o SEMM serão esmaecidas (indisponíveis) indicando que algumas configurações são gerenciadas pela sua  **organização, conforme** mostrado na Figura 12.

:::image type="content" alt-text="Configurações gerenciados pelo SEMM estão desabilitados na UEFI do Surface." source="images/surface-semm-enroll-fig12.png":::

*Figura 12. Configurações gerenciado pelo SEMM será desabilitado na UEFI do Surface*
