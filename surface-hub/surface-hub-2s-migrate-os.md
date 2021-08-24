---
title: Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2
description: Como migrar do Windows 10 Team no Surface Hub 2 para Windows 10 Pro ou Windows 10 Enterprise.
keywords: Surface Hub Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: bdf39a2e664aa9abbd2fbf4790aec0b04c084f64
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911876"
---
# <a name="migrate-to-windows-10-pro-or-enterprise-on-surface-hub-2"></a>Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2

- [Histórico da versão do artigo](#version-history)

Surface Hub 2S vem com Windows 10 Team instalado. Esta edição personalizada do Windows 10 facilita a colaboração em ambientes de sala de reunião. Agora você pode executar Windows 10 Pro ou Enterprise usar seu Surface Hub 2S muito parecido com qualquer outro computador.

> [!IMPORTANT]
> Esse processo de migração exige que você siga o procedimento específico descrito neste artigo. Antes de continuar, leia [Componentes de solução](#solution-components) e [Migração e fluxo de trabalho de instalação.](#migration-and-installation-workflow-summary)

> [!NOTE]
> Ao instalar o Windows 10 Pro ou Enterprise no Surface Hub 2S, você precisa de uma nova licença distinta da licença de Windows 10 Team existente fornecida com o dispositivo.

Inicie a migração Windows 10 Team usando um computador separado e a ferramenta configurável *do Surface UEFI para* download. A ferramenta cria um pacote que contém uma nova configuração UEFI que você aplica ao Surface Hub 2S.  

O Surface UEFI Configurator funciona como uma interface no Surface Enterprise Management Mode (SEMM). Ele permite o gerenciamento centralizado das configurações de firmware em dispositivos Surface em um ambiente corporativo. Para obter mais informações, consulte [Microsoft Surface Enterprise Modo de Gerenciamento](/surface/surface-enterprise-management-mode).
 
## <a name="solution-components"></a>Componentes da solução

- Surface Hub dispositivo 2S executando Windows 10 Team
- Dispositivo separado executando Windows 10
- Ferramenta Configurador UEFI do Surface para criar o pacote SEMM
- Windows 10 Pro ou Enterprise do sistema operacional, versão 1903 ou posterior
- Duas unidades USB com 16 GB de armazenamento, formato FAT32
- Os drivers e o firmware para Windows 10 Pro e Enterprise em um arquivo Surface Hub 2 Microsoft Windows Installer (MSI)
- Conexão com a Internet
- Solução de imagens (opcional)
 
## <a name="migration-and-installation-workflow-summary"></a>Resumo do fluxo de trabalho de migração e instalação

| Etapa  | Ação                                                                                                 | Resumo                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Verifique a versão UEFI no Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).                                  | A versão UEFI deve ser a *versão 694.2938.768.0* ou posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Baixe o Surface UEFI Configurator e o Surface Hub 2 drivers e firmware.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Na página **[Ferramentas do Surface para IT,](https://www.microsoft.com/download/details.aspx?id=46703)** selecione </a> **Baixar**. Em seguida, selecione e baixe o **arquivo MSI do Surface UEFI Configurator**e instale-o em um computador separado. Baixe também drivers e firmware para Windows 10 Pro e Enterprise sistema operacional no Surface Hub [2 MSI.](https://www.microsoft.com/download/details.aspx?id=101974)</a> Salve este pacote para uso na etapa 5. |
| 3 | [Preparar o certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepare o certificado necessário para executar o Surface UEFI Configurator ou use seu certificado atual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Crie um pacote SEMM.](#create-a-semm-package)                                                                               | Inicie o Configurador UEFI do Surface para criar um pacote SEMM em uma unidade USB. Este pacote conterá os arquivos de configuração que você precisa aplicar no Surface Hub 2S. Copie esses arquivos de pacote SEMM para uma pasta em seu computador.                                                                                                                                                                                          |
| 5 | [Carregue uma unidade flash USB com Windows 10 imagem, o pacote SEMM e drivers e firmware.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crie uma unidade USB que contenha uma Windows 10 imagem. Neste exemplo, a unidade é chamada *BOOTME*. Adicione os drivers e o firmware para Windows 10 Pro e Enterprise sistema operacional no Surface Hub 2 (da etapa 2) e nos arquivos de pacote SEMM (da etapa 4) para a unidade *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use a *unidade BOOTME* para inicializar o Surface Hub 2S no menu UEFI e instalar o pacote SEMM.|
| 7 | [Instale Windows 10 Pro ou Enterprise.](#install-windows-10-pro-or-enterprise)                                        | Use a *unidade BOOTME* para instalar Windows 10 Pro ou Enterprise versão 1903 ou posterior.                                                                                                                                                                                                                                                                                 |
| 8 | [Instale drivers e firmware para Windows 10 Pro e Enterprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale os drivers e o firmware do sistema operacional Windows 10 Pro e Enterprise no arquivo <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 MSI.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configure Surface Hub 2S como um dispositivo de produtividade pessoal.](#configure-recommended-settings)                                        |  Habilita as configurações e aplicativos recomendados para otimizar Surface Hub 2S como um dispositivo de produtividade pessoal.                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>Verificar a versão UEFI no Surface Hub 2S

Antes de migrar Surface Hub do Windows 10 Team para Windows 10 Desktop, você precisa da UEFI versão *694.2938.768.0* ou posterior.
 
**Para verificar a versão UEFI em seu sistema:**

1. Na home page Surface Hub 2S, selecione **Iniciar**e abra o aplicativo Surface (**Todos os**  >  **Aplicativos Surface**).

2. Selecione **Seu Surface para** exibir informações sobre Surface Hub, incluindo a versão UEFI atual no dispositivo. 
   - Se a versão UEFI for *694.2938.768.0* ou posterior, conforme a imagem a seguir mostra, você pode criar o pacote SEMM para habilitar a migração do sistema operacional.

       ![Captura de tela mostra a página "Seu Surface" no aplicativo Surface.](images/shm-fig1.png)
 
   - Se a versão UEFI for anterior à versão *694.2938.768.0*, use um dos métodos a seguir para obter uma versão mais recente
   
#### <a name="update-uefi-via-windows-update"></a>Atualizar a UEFI por meio Windows Atualização

1. Em seu Surface Hub 2S, entre como **Administrador**.

    >[!Note]
    > Se você não sabe seu nome de usuário ou senha de administrador, precisará redefinir o dispositivo. Para obter mais informações, consulte [Reset and recovery for Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).

1. Acesse Todos **os aplicativos**  >  **Configurações**  >  **Atualização**e Segurança  >  **Windows Atualização**e instale todas as atualizações.
1. Reinicie o dispositivo.
1. Verifique a versão UEFI usando o aplicativo Surface. Se a versão UEFI não for a versão *694.2938.768.0* ou posterior, repita essas etapas ou use o procedimento a seguir para obter a versão UEFI mais recente.

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>Atualizar a UEFI por meio da imagem de recuperação de bare metal (BMR)

1.  Vá para o [site de recuperação do Surface](https://support.microsoft.com/surfacerecoveryimage) e selecione Surface Hub **2S**.
3.  Insira o número de série do Hub. Ele está localizado na parte de trás do Hub ao lado da conexão de energia.
4.  Siga as instruções para baixar a imagem em uma unidade USB formatada instalando o Windows 10 Team 2020 Update.
5.  Após a atualização, o dispositivo inscreverá a configuração do OOBE (experiência fora de caixa de entrada). Você não precisa concluir a instalação. A versão UEFI já foi atualizada. Em vez disso, desligar o dispositivo segurando o botão de energia até que a tela seja desligada.

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>Baixar o Surface UEFI Configurator e Surface Hub 2 drivers e firmware

Em um computador separado, siga estas etapas:

1. Na página <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Ferramentas do Surface para </a> IT, selecione **Baixar**.  
1. Selecione e baixe o arquivo MSI do Surface UEFI Configurator e instale-o em um computador separado. A ferramenta Configurador UEFI surface não pode ser executado em um Surface Hub 2S enquanto Windows 10 Team edição está instalada.

1. Baixe os [drivers Surface Hub 2 e o arquivo MSI do instalador Windows firmware.](https://www.microsoft.com/download/details.aspx?id=101974) Você usará esse arquivo quando instalar o novo sistema operacional.

### <a name="prepare-the-semm-certificate"></a>Preparar o certificado SEMM

Se você ainda não usou o Surface UEFI Configurator antes, você precisa preparar um certificado. Esse certificado garante que, depois que um dispositivo for inscrito no SEMM, você só poderá modificar as configurações uefi usando pacotes criados com o certificado aprovado.

A forma como você obter um certificado depende do tamanho ou da complexidade da sua organização:

- Enterprise geralmente mantêm sua própria infraestrutura para gerar certificados de acordo com as práticas de segurança padrão.

- Empresas de médio porte e outras pessoas geralmente optam por obter certificados de provedores parceiros. Essa opção é recomendada para organizações que não têm tanto conhecimento em IT ou que não têm uma equipe de segurança de IT dedicada.

- Como alternativa, você pode gerar um certificado auto-assinado usando um script do PowerShell. Para obter mais informações, consulte os requisitos de certificado do [Surface Enterprise Modo de Gerenciamento.](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements) Ou você pode usar o PowerShell para criar seu próprio certificado. Para obter mais informações, consulte [a documentação do certificado auto-assinado.](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate)

O pacote SEMM que o Surface UEFI Configurator cria deve ser protegido com um certificado. O certificado verifica a assinatura de arquivos de configuração antes que as configurações da UEFI possam ser aplicadas. Para obter mais informações, consulte a [documentação do SEMM.](/surface/surface-enterprise-management-mode)
 
### <a name="create-a-semm-package"></a>Criar um pacote SEMM

1. Em um computador separado, instale a ferramenta Configurator UEFI do Surface que você baixou anteriormente.

1. Abra o Configurador UEFI do Surface e selecione **Iniciar**.

   ![Tela inicial do Surface UEFI Configurator.](images/shm-fig2.png)
   
1. Selecione **Dispositivos Surface**e, em seguida, selecione **Next**.

   ![Captura de tela mostra a opção Dispositivos Surface selecionada.](images/shm-fig3.png)
  
1. Selecione **Pacote de Configuração**.

   ![A captura de tela mostra "Selecionar Pacote de Configuração" selecionado.](images/shm-fig4.png)
  
1. Selecione **Proteção de Certificados**.

   ![Os programas de captura de tela eram para escolher "Selecionar Proteção de Certificado".](images/shm-fig5.png)

   Você será solicitado a adicionar seu arquivo .pfx de certificado.

   ![Captura de tela mostra onde adicionar seu arquivo de certificado.](images/shm-fig6.png)
   
1. Insira a senha do certificado e selecione **OK**.

   ![Captura de tela mostra campos para inserir e confirmar a senha do certificado.](images/shm-fig7.png)

1. Selecione **Proteção de Senha** para adicionar uma senha à UEFI do Surface. Você precisará dessa senha sempre que for inicializado na UEFI. *É recomendável definir uma senha UEFI que você usará no Surface Hub 2S.*

   ![Captura de tela mostra onde selecionar Proteção de Senha.](images/shm-fig8.png)
   
1. De definir uma senha UEFI e selecione **OK**.

   > [!IMPORTANT]
   > Salve a senha em um local seguro que seja acessível aos administradores de IT que gerenciam Surface Hub. *Se essa senha for perdida, ela não poderá ser recuperada.*

   ![Captura de tela mostra onde você definiu a senha UEFI.](images/shm-fig9.png)

1. Selecione **Surface Hub 2S**e selecione **Próximo**.

    ![Captura de tela mostra onde selecionar Surface Hub 2S.](images/shm-fig10.png)
   
1. Selecione **Próximo** novamente.

    ![A captura de tela mostra para selecionar Next em "Escolher quais componentes".](images/shm-fig10a.png)

1. Para permitir a instalação de Windows 10 Pro ou Enterprise, ative **EnableOsMigration**e selecione **Next**.

    ![Captura de tela mostra onde selecionar Habilitar Migração O S.](images/shm-fig11.png)
    
    ![Captura de tela mostra onde definir Habilitar a migração do sistema operacional para ativado.](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>Gerenciar registro semm

Registrar um dispositivo no SEMM afeta como você pode gerenciá-lo. Por exemplo, depois de aplicar um pacote SEMM, todas as configurações UEFI ficam indisponíveis (bloqueadas) no menu UEFI do dispositivo. Os valores padrão para outras configurações, como **IPv6 para Inicialização PXE,** também não estão disponíveis.

Para alterar as configurações da UEFI depois de concluir a migração, aplique outro pacote SEMM ou desempacore o dispositivo do SEMM. Se você aplicar outro pacote SEMM para alterar as configurações uefi, você deve usar o certificado original ao criar o novo pacote SEMM. Use a ferramenta Configurator UEFI e deixe **EnableOSMigration** *desligado* *(não* ativado como nas etapas de migração originais).

#### <a name="if-you-work-with-partners"></a>Se você trabalhar com parceiros

Se sua empresa terceirizar Surface Hub migração de Surface Hub 2 para Windows 10 Pro ou Enterprise, talvez você queira que o parceiro transfira o certificado SEMM, o pacote SEMM e a senha UEFI para você. Ou, depois de migrar o Hub, você pode desemrollá-lo imediatamente do SEMM. Esta etapa permite a administração local da UEFI e a transferência do dispositivo para outra parte. Mas ainda recomendamos que você use uma senha UEFI, que pode ser configurada após a migração. Para saber mais, consulte [Manage Surface UEFI settings](/surface/manage-surface-uefi-settings). 

#### <a name="to-roll-back-to-windows-10-team"></a>Para reverter para Windows 10 Team

Se você optar por restaurar seu dispositivo para Windows 10 Team após a migração, conforme descrito posteriormente neste [artigo,](#to-roll-back-to-windows-10-team)recomendamos que você primeiro desemsenrole o Hub do SEMM. Para saber mais, consulte [Unenroll Surface devices from SEMM](/surface/unenroll-surface-devices-from-semm).

#### <a name="save-the-semm-package-to-a-usb-drive"></a>Salvar o pacote SEMM em uma unidade USB

1. Conexão uma unidade USB para seu computador.
1. Escolha **Hub 2S**e selecione **Próximo**.

   ![Captura de tela mostra onde selecionar Hub 2S.](images/shm-fig13.png)

   > [!WARNING]
   > Todos os dados existentes na unidade USB serão apagados quando o pacote SEMM for criado. Antes de criar o pacote SEMM, remova todos os arquivos necessários da unidade USB.
   
1. Selecione **Criar**.

   ![Captura de tela mostra onde selecionar Build.](images/shm-fig14.png)

1. Capture uma captura de tela desta página e selecione **Fim**. Seu pacote SEMM agora está pronto. Ele contém o pacote SEMM *DfciUpdate.dfi* e um arquivo de texto que inclui a impressão digital *SEMM*, que é os dois últimos caracteres da impressão digital do certificado.

   ![Captura de tela mostra onde selecionar End.](images/shm-fig15.png)
   
4. Salve os dois últimos caracteres da impressão digital do certificado. Você precisará desses caracteres para ativar o SEMM quando aplicar o pacote no Surface Hub 2S.

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>Carregar uma unidade flash USB com uma imagem Windows 10, pacote SEMM e Surface Hub 2 drivers e firmware

Você pode instalar uma imagem Windows 10 Pro ou Enterprise (versão *1903* ou posterior) usando uma das seguintes opções:

- Sua solução de imagens atual.

- [Acelerador de Implantação do Surface](/surface/microsoft-surface-deployment-accelerator). Use essa ferramenta para criar uma imagem inicializável Windows 10 imagem. A imagem pode incluir todas as atualizações Windows 10, Microsoft Office, outros aplicativos e os drivers e firmware necessários.

- Uma unidade flash USB que contém uma imagem Windows 10 Pro ou Enterprise usb. Essa opção não terá Wi-Fi disponível até após a instalação do OOBE (out-of-box-experience). Depois que a instalação for concluída, instale os drivers e firmware necessários Surface Hub [2](https://www.microsoft.com/download/details.aspx?id=101974) para Windows 10 Pro e Enterprise no dispositivo.
 
As etapas a seguir mostram como criar uma unidade flash USB a partir da mídia de instalação e, em seguida, adicionar os arquivos de pacote SEMM e os drivers e firmware para o sistema operacional Windows 10 Pro e Enterprise no arquivo Surface Hub 2 MSI. Se você usar outro método de implantação, vá para a seção Atualizar UEFI no [Surface Hub 2S](#update-uefi-on-surface-hub-2s-to-enable-os-migration) para habilitar a seção migração do sistema operacional deste artigo.

> [!NOTE]
> Depois de concluir a instalação, você precisará de uma licença válida para Windows 10 Pro ou Windows 10 Enterprise que seja separada da sua licença de Windows 10 Team existente.

1. Para criar uma instalação Windows 10 Pro, siga as instruções para baixar a ferramenta de criação de mídia em [Baixar Windows 10](https://www.microsoft.com/software-download/windows10). Para baixar Windows 10 Enterprise, vá para o Centro de Serviços de [Licenciamento por Volume da Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

1. Insira uma nova unidade de armazenamento USB.
1. Abra a ferramenta de criação de mídia, selecione **Criar mídia de**instalação e selecione **Próximo**.

   ![Captura de tela mostra a opção para criar mídia de instalação.](images/shm-fig16.png)
   
3. Selecione um idioma e selecione **Windows 10** e **64 bits (x64)**. Em seguida, selecione **Next**.

   ![A captura de tela mostra onde você seleciona o idioma, a edição O S e o tipo de arquitetura.](images/shm-fig17.png)
   
4. Selecione **Unidade flash USB**e, em seguida, selecione **Next**.

   ![Captura de tela mostra onde selecionar unidade flash U S B.](images/shm-fig18.png)
   
5. Quando o download terminar, selecione **Concluir**.

   ![A tela relata que a unidade U S B está pronta e inclui um botão Concluir.](images/shm-fig19.png)
   
6. Copie os arquivos de pacote SEMM e os drivers e firmware para o sistema operacional Windows 10 Pro e Enterprise no Surface Hub 2 (o arquivo MSI) para a raiz da unidade flash USB (*BOOTME*) que contém sua imagem Windows 10. A unidade USB BOOTME conterá:

    - Sua Windows 10 inicializável.
    
    - Os arquivos de pacote SEMM, copiados para a raiz da unidade USB:
    
      - *DfciUpdate.dfi*.
      - Um arquivo de texto que inclui a impressão digital SEMM. (Neste exemplo, o arquivo é *SurfaceUEFI_2020Aug25_1058.txt*.) O carimbo de data/hora gerado automaticamente corresponde à data em que você criou o arquivo usando o Surface UEFI Configurator.

   - Os drivers e o firmware para Windows 10 Pro e Enterprise sistema operacional no Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copie esse arquivo para a raiz da unidade USB.

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>Atualizar a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional

1. Insira sua unidade BOOTME na porta USB-A no Surface Hub 2S. Para ver uma lista de seus conteúdos necessários, consulte a seção anterior.

1. Para inicializar em UEFI:

   1. Desativar (desligar) seu Surface Hub 2S.
   1. Pressione e segure **Volume +** e pressione e solte o botão de energia. Mantenha a **segurando Volume +** até que o menu UEFI apareça.
   
      ![O desenho mostra o volume e os botões de energia.](images/shm-fig20.png)
      
3. Quando o dispositivo for reiniciado, insira a senha UEFI que você criou anteriormente, se aplicável (recomendado).

   ![Tela de senha do sistema.](images/shm-fig22.png)
   
4. No menu UEFI, selecione **Gerenciamento**. Em seguida,  **selecione Instalar no USB**.

   ![A captura de tela mostra onde selecionar Gerenciamento e, em seguida, "Instalar a partir da U.S B".](images/shm-fig21.png)
   
5. Selecione **Reiniciar agora**, como mostra a imagem a seguir. O dispositivo será reiniciado agora. Ele exibirá um logotipo da Microsoft branco no meio da janela e desligará.

   ![Captura de tela mostra uma mensagem solicitando que você reinicie.](images/shm-fig25.png)
   
6. Pressione e solte o botão de energia. Na caixa de diálogo vermelha exibida, escolha ativar o Surface Enterprise Modo de Gerenciamento.

7. Insira sua impressão digital de certificado de dois caracteres e sua senha de configurações uefi. Em seguida, **selecione OK**.

   ![A captura de tela mostra a caixa de diálogo confirmar a ativação onde você inserirá a impressão digital do certificado de dois caracteres e a senha de configurações da UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Depois de ativar o SEMM em seu dispositivo, a nova configuração UEFI **EnableOSMigration** será aplicada. Você não pode mais acessar Windows 10 Team. Em vez disso, você deve continuar para a próxima etapa e instalar Windows 10 Pro ou Windows 10 Enterprise.

   O dispositivo é reiniciado. Ele exibe o logotipo branco no meio da tela e, em seguida, desliga novamente.

### <a name="install-windows-10-pro-or-enterprise"></a>Instalar Windows 10 Pro ou Enterprise

1. Se sua unidade inicializável Windows 10 Pro ou Enterprise já não estiver na porta USB-A 2 Surface Hub 2, insira-a agora. Em seguida, pressione e solte o botão de energia.

    Quando o dispositivo for iniciado, você verá o logotipo branco no meio da tela. Em seguida, um círculo giratório aparece abaixo do logotipo branco.

3. Se o dispositivo Surface não for inicializado automaticamente na unidade USB, desligue o dispositivo (desligue o cabo de alimentação e conecte-o novamente). Depois de conectar o cabo de alimentação novamente, o dispositivo deve ser inicializado após alguns segundos. Em seguida, você verá o logotipo branco no meio da tela.

    Se o dispositivo não ligar, pressione e solte o botão de energia. Imediatamente depois de ver o logotipo no meio da tela, pressione e segure o botão Volume para baixo até ver o círculo giratório abaixo do logotipo branco.
 
   ![Imagem dos botões de volume e de energia.](images/shm-fig26.png)
   
4. Quando a instalação do OOBE (experiência inicial) for iniciada, siga as instruções para instalar Windows 10 Pro ou Enterprise (versão 1903 ou posterior).

### <a name="install-surface-hub-2-drivers-and-firmware"></a>Instalar Surface Hub 2 drivers e firmware

Para garantir que o Surface Hub 2 está atualizado, instale drivers e firmware para Windows 10 Pro [e Enterprise](https://www.microsoft.com/download/details.aspx?id=101974). Em seguida, reinicie o dispositivo. Mantenha o Surface ligado por uma hora e reinicie-o novamente. Você não será solicitado para a segunda reinicialização. Essa pausa e reinicialização extra garantem que o firmware tenha sido totalmente atualizado.
 
## <a name="configure-recommended-settings"></a>Configurar configurações recomendadas

Para configurar Surface Hub 2S como um dispositivo de produtividade pessoal, consulte [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Se você não puder migrar com êxito seu dispositivo para Windows 10 Pro ou Enterprise para o Surface Hub 2 seguindo as etapas descritas neste artigo, entre em contato com Surface Hub [Suporte](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="to-roll-back-to-windows-10-team"></a>Para reverter para Windows 10 Team

Se você deseja restaurar seu dispositivo para Windows 10 Team, consulte Redefinir e recuperar para Surface Hub [2S](surface-hub-2s-recover-reset.md).

> [!NOTE]
> Antes de reverter para Windows 10 Team, recomendamos que você primeiro desembolse o Surface Hub do SEMM. Para saber mais, consulte [Unenroll Surface devices from SEMM](/surface/unenroll-surface-devices-from-semm).

## <a name="version-history"></a>Histórico de versão

A tabela a seguir resume as alterações neste artigo.

| Versão | Data               | Descrição                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 de dezembro de 2020 | Fornece [](#install-surface-hub-2-drivers-and-firmware) mais informações sobre como instalar o arquivo MSI para "Drivers e firmware para o sistema operacional Windows 10 Pro e Enterprise no Surface Hub 2", avisando que uma segunda reinicialização pode ser necessária, dependendo do estado do seu sistema.                                                          |
| v. 1.3  | 3 de dezembro de 2020 | Atualizado com orientações sobre como [gerenciar o registro SEMM.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 29 de setembro de 2020 | Atualizações diversas que abordam comentários de usabilidade.                                                        |
| v. 1.1  | 15 de setembro de 2020 | Colocou uma observação adicional na introdução que esclarece os requisitos de licenciamento para a instalação de um novo sistema operacional. |
| v. 1.0  | 1º de setembro de 2020  | Novo artigo.                                                                                           |
