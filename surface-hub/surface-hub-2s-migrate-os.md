---
title: Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2
description: Como migrar do Windows 10 Team no Surface Hub 2 para o Windows 10 Pro ou Windows 10 Enterprise.
keywords: Área de Trabalho do Surface Hub, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297634"
---
# Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2

- [Histórico de versão do artigo](#version-history)

O Surface Hub 2S vem com o Windows 10 Team instalado. Esta edição personalizada do Windows 10 facilita a colaboração em ambientes de sala de reunião. Agora você pode executar o Windows 10 Pro ou Enterprise para usar o Surface Hub 2S como qualquer outro computador.

> [!IMPORTANT]
> Esse processo de migração requer que você siga o procedimento específico descrito neste artigo. Antes de continuar, leia os [componentes da solução e](#solution-components) o [fluxo de trabalho de migração e instalação.](#migration-and-installation-workflow-summary)

> [!NOTE]
> Ao instalar o Windows 10 Pro ou Enterprise, você precisa de uma nova licença separada da sua licença existente do Windows 10 Team.

Inicie a migração do Windows 10 Team usando um computador separado e a ferramenta configurador *UEFI do Surface* para download. A ferramenta cria um pacote que contém uma nova configuração UEFI que você aplica ao Surface Hub 2S.  

O Configurador UEFI do Surface funciona como uma interface para o Surface Enterprise Management Mode (SEMM). Ele permite o gerenciamento centralizado de configurações de firmware em dispositivos Surface em um ambiente corporativo. Para obter mais informações, consulte [o Modo de Gerenciamento empresarial do Microsoft Surface.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
## Componentes da solução

- Dispositivo Surface Hub 2S executando o Windows 10 Team
- Dispositivo separado executando o Windows 10
- Ferramenta Configurador UEFI do Surface para criar o pacote SEMM
- Imagem do sistema operacional Windows 10 Pro ou Enterprise, versão 1903 ou posterior
- Duas unidades USB com 16 GB de armazenamento, formato FAT32
- Os drivers e o firmware do Windows 10 Pro e Enterprise em um arquivo MSI (Microsoft Windows Installer) do Surface Hub 2
- Conexão com a Internet
- Solução de imagem (opcional)
 
## Resumo do fluxo de trabalho de migração e instalação

| Etapa  | Ação                                                                                                 | Resumo                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Verifique a versão UEFI no Surface Hub 2S.](#verify-the-uefi-version-on-surface-hub-2s)                                  | A versão UEFI deve ser *a versão 694.2938.768.0* ou posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Baixe o Configurador UEFI do Surface e os drivers e firmware do Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Na página **[Ferramentas do Surface para IT,](https://www.microsoft.com/download/details.aspx?id=46703)** selecione </a> **Baixar.** Em seguida, selecione e baixe o **arquivo MSI do Configurador UEFI**do Surface e instale-o em um computador separado. Baixe também os [drivers e o firmware do sistema operacional Windows 10 Pro e Enterprise no arquivo MSI do Surface Hub 2.](https://www.microsoft.com/download/details.aspx?id=101974)</a> Salve este pacote para uso na etapa 5. |
| 3 | [Prepare o certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepare o certificado necessário para executar o Configurador UEFI do Surface ou use seu certificado atual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Crie um pacote SEMM.](#create-a-semm-package)                                                                               | Inicie o Configurador UEFI do Surface para criar um pacote SEMM em uma unidade USB. Esse pacote conterá os arquivos de configuração que você precisa aplicar no Surface Hub 2S. Copie esses arquivos de pacote SEMM para uma pasta em seu computador.                                                                                                                                                                                          |
| 5 | [Carregue uma unidade flash USB com imagem do Windows 10, o pacote SEMM, drivers e firmware.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crie uma unidade USB que contenha uma imagem do Windows 10. Neste exemplo, a unidade é chamada *BOOTME*. Adicione os drivers e o firmware para o Sistema Operacional Windows 10 Pro e Enterprise no Surface Hub 2 (da etapa 2) e os arquivos de pacote SEMM (da etapa 4) para a unidade *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Atualize o UEFI no Surface Hub 2S para habilitar a migração do sistema operacional.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use a *unidade BOOTME* para inicializar o Surface Hub 2S no menu UEFI e instalar o pacote SEMM.|
| 7 | [Instale o Windows 10 Pro ou Enterprise.](#install-windows-10-pro-or-enterprise)                                        | Use a *unidade BOOTME* para instalar o Windows 10 Pro ou Enterprise versão 1903 ou posterior.                                                                                                                                                                                                                                                                                 |
| 8 | [Instale drivers e firmware para Windows 10 Pro e Enterprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale os drivers e o firmware do sistema operacional Windows 10 Pro e Enterprise no arquivo <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> MSI do Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configure o Surface Hub 2S como um dispositivo de produtividade pessoal.](#configure-recommended-settings)                                        |  Habilita as configurações e aplicativos recomendados para otimizar o Surface Hub 2S como um dispositivo de produtividade pessoal.                                                                                                                                                                                                                                                                    |

### Verificar a versão UEFI no Surface Hub 2S

Antes de migrar o Surface Hub do Windows 10 Team para a Área de Trabalho do Windows 10, você precisa da versão UEFI *694.2938.768.0* ou posterior.
 
**Para verificar a versão UEFI em seu sistema:**

1. Na home page do Surface Hub 2S, selecione **Iniciar**e abra o aplicativo do Surface (**Todos os Aplicativos**  >  **Surface**).

2. Selecione **o Surface** para exibir informações sobre o Surface Hub, incluindo a versão UEFI atual no dispositivo. 
   - Se a versão UEFI for *694.2938.768.0* ou posterior, como mostra a imagem a seguir, você poderá criar o pacote SEMM para habilitar a migração do sistema operacional.

       ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)
 
   - Se a versão UEFI for anterior à *versão 694.2938.768.0*, use um dos métodos a seguir para obter uma versão mais recente
   
#### Atualizar UEFI por meio do Windows Update

1. No Surface Hub 2S, entre como **Administrador.**

    >[!Note]
    > Se você não sabe seu nome de usuário ou senha de administrador, precisará redefinir o dispositivo. Para obter mais informações, consulte [Redefinir e recuperar o Surface Hub 2S.](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)

1. Vá para **Atualizações**  >  **de Configurações de**Todos os  >  **Aplicativos e Segurança**do Windows  >  **Update**e instale todas as atualizações.
1. Reinicie o dispositivo.
1. Verifique a versão UEFI usando o aplicativo Surface. Se a versão UEFI não for a *versão 694.2938.768.0* ou posterior, repita essas etapas ou use o procedimento a seguir para obter a versão uefi mais recente.

#### Atualizar a UEFI por meio da imagem de recuperação bare-metal (BMR)

1.  Vá para o [site de recuperação do Surface](https://support.microsoft.com/surfacerecoveryimage) e selecione Surface Hub **2S.**
3.  Insira o número de série do Hub. Ele está localizado na parte traseira do Hub ao lado da conexão de energia.
4.  Siga as instruções para baixar a imagem em uma unidade USB formatada instalando o Windows 10 Team 2020 Update.
5.  Após a atualização, o dispositivo entra na configuração inicial pelo usuário (OOBE). Não é necessário concluir a configuração. A versão UEFI já está atualizada. Em vez disso, desliga o dispositivo mantendo pressionado o botão de energia até que a tela seja desligada.

### Baixar firmware e drivers do Surface UEFI Configurator e do Surface Hub 2

Em um computador separado, siga estas etapas:

1. Na página <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Ferramentas do Surface para </a> IT, selecione **Baixar.**  
1. Selecione e baixe o arquivo MSI do Configurador UEFI do Surface e instale-o em um computador separado. A ferramenta Configurador UEFI do Surface não pode ser executado em um Surface Hub 2S enquanto o Windows 10 Team Edition estiver instalado.

1. Baixe os [drivers do Surface Hub 2 e o arquivo MSI do Windows Installer](https://www.microsoft.com/download/details.aspx?id=101974)do firmware. Você usará esse arquivo ao instalar o novo sistema operacional.

### Preparar o certificado SEMM

Se você ainda não usou o Configurador UEFI do Surface antes, precisará preparar um certificado. Esse certificado garante que, depois que um dispositivo for inscrito no SEMM, você só poderá modificar as configurações UEFI usando pacotes criados com o certificado aprovado.

A forma como você obter um certificado depende do tamanho ou da complexidade da sua organização:

- As organizações corporativas geralmente mantêm sua própria infraestrutura para gerar certificados de acordo com as práticas de segurança padrão.

- Empresas de médio porte e outras pessoas geralmente optam por obter certificados de provedores parceiros. Essa opção é recomendada para organizações que não têm tanto conhecimento em IT ou que não têm uma equipe de segurança de IT dedicada.

- Como alternativa, você pode gerar um certificado auto-assinado usando um script do PowerShell. Para obter mais informações, consulte os requisitos [de certificado do Modo de Gerenciamento do Surface Enterprise.](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements) Ou você pode usar o PowerShell para criar seu próprio certificado. Para obter mais informações, consulte a [documentação New-SelfSignedCertificate.](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)

O pacote SEMM que o Configurador UEFI do Surface cria deve ser protegido com um certificado. O certificado verifica a assinatura dos arquivos de configuração antes que as configurações de UEFI possam ser aplicadas. Para obter mais informações, consulte a [documentação do SEMM.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
### Criar um pacote SEMM

1. Em um computador separado, instale a ferramenta Configurador UEFI do Surface que você baixou anteriormente.

1. Abra o Configurador UEFI do Surface e selecione **Iniciar.**

   ![Tela inicial do Configurador UEFI do Surface.](images/shm-fig2.png)
   
1. Selecione **Dispositivos Surface**e, em seguida, **selecione Próximo.**

   ![A captura de tela mostra a opção Dispositivos Surface selecionada.](images/shm-fig3.png)
  
1. Selecione **Pacote de Configuração.**

   ![Screenshot shows "Select Configuration Package" selected.](images/shm-fig4.png)
  
1. Selecione **Proteção de Certificado.**

   ![Screenshot shows were to choose "Select Certificate Protection".](images/shm-fig5.png)

   Você será solicitado a adicionar seu arquivo .pfx de certificado.

   ![Screenshot shows where to add your certificate file.](images/shm-fig6.png)
   
1. Insira sua senha de certificado e selecione **OK.**

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. Selecione **Proteção por Senha** para adicionar uma senha à UEFI do Surface. Você precisará dessa senha sempre que inicializar para a UEFI. *É recomendável definir uma senha UEFI que você usará no Surface Hub 2S.*

   ![Screenshot shows where to select Password Protection.](images/shm-fig8.png)
   
1. Definir uma senha UEFI e, em seguida, selecione **OK**.

   > [!IMPORTANT]
   > Salve a senha em um local seguro que seja acessível para os administradores de IT que gerenciam o Surface Hub. *Se essa senha for perdida, ela não poderá ser recuperada.*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. Selecione **Surface Hub 2S**e, em seguida, **Clique em Próximo.**

    ![A captura de tela mostra onde selecionar o Surface Hub 2S.](images/shm-fig10.png)
   
1. Selecione **Próximo** novamente.

    ![Screenshot shows to select Next under "Choose which components".](images/shm-fig10a.png)

1. Para permitir a instalação do Windows 10 Pro ou Enterprise, ative **EnableOsMigration**e selecione **Next**.

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)
    
    ![Screenshot shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### Gerenciar o registro SEMM

Registrar um dispositivo no SEMM afeta como você pode gerenciá-lo. Por exemplo, depois de aplicar um pacote SEMM, todas as configurações UEFI ficam indisponíveis (bloqueadas) no menu UEFI do dispositivo. Os valores padrão para outras configurações, como **IPv6 para Inicialização PXE,** também não estão disponíveis.

Para alterar as configurações de UEFI após concluir a migração, aplique outro pacote SEMM ou desfaça o logon do dispositivo no SEMM. Se você aplicar outro pacote SEMM para alterar as configurações de UEFI, deverá usar o certificado original ao criar o novo pacote SEMM. Use a ferramenta Configurador UEFI e deixe **EnableOSMigration** *desligado* (não *ativado* como nas etapas de migração originais).

#### Se você trabalha com parceiros

Se sua empresa terceiriza a migração do Surface Hub 2 para o Windows 10 Pro ou Enterprise, talvez você queira que o parceiro transfira o certificado SEMM, o pacote SEMM e a senha UEFI para você. Ou, depois de migrar o Hub, você pode desemrollá-lo imediatamente do SEMM. Esta etapa permite a administração local da UEFI e a transferência do dispositivo para outra parte. Mas ainda recomendamos que você use uma senha UEFI, que pode ser configurada após a migração. Para saber mais, consulte [Gerenciar configurações de UEFI do Surface.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Para reverter para o Windows 10 Team

Se você optar por restaurar seu dispositivo para a Equipe do Windows 10 após a migração, conforme descrito mais adiante neste [artigo,](#to-roll-back-to-windows-10-team)recomendamos que primeiro você desincense o Hub do SEMM. Para saber mais, consulte [Unenroll dispositivos Surface do SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).

#### Salvar o pacote SEMM em uma unidade USB

1. Conecte uma unidade USB ao computador.
1. Choose **Hub 2S**, and then select **Next**.

   ![A captura de tela mostra onde selecionar o Hub 2S](images/shm-fig13.png)

   > [!WARNING]
   > Todos os dados existentes na unidade USB serão apagados quando o pacote SEMM for criado. Antes de criar o pacote SEMM, remova todos os arquivos necessários da unidade USB.
   
1. Selecione **Build**.

   ![Screenshot shows where to select Build.](images/shm-fig14.png)

1. Capture uma captura de tela desta página e selecione **End**. Seu pacote SEMM agora está pronto. Ele contém o pacote SEMM *DfciUpdate.dfi* e um arquivo de texto que inclui a impressão digital *SEMM*, que é os dois últimos caracteres da impressão digital do certificado.

   ![Screenshot shows where to select End.](images/shm-fig15.png)
   
4. Salve os dois últimos caracteres da impressão digital do certificado. Você precisará desses caracteres para ativar o SEMM ao aplicar o pacote no Surface Hub 2S.

### Carregar uma unidade flash USB com uma imagem do Windows 10, um pacote SEMM e drivers e firmware do Surface Hub 2

Você pode instalar uma imagem do Windows 10 Pro ou Enterprise (versão *1903* ou posterior) usando uma das seguintes opções:

- Sua solução de imagem atual.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator). Use essa ferramenta para criar uma imagem inicializável do Windows 10. A imagem pode incluir todas as atualizações atuais do Windows 10, o Microsoft Office, outros aplicativos e os drivers e firmware necessários.

- Uma unidade flash USB que contém uma imagem do Windows 10 Pro ou Enterprise. Em [seguida, instale drivers e firmware para Windows 10 Pro e Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) no Surface Hub 2.
 
As etapas a seguir mostram como criar uma unidade flash USB a partir da mídia de instalação e, em seguida, adicionar os arquivos de pacote SEMM e os drivers e firmware do Sistema Operacional Windows 10 Pro e Enterprise no arquivo MSI do Surface Hub 2. Se você usar outro método de implantação, vá para Atualizar UEFI no [Surface Hub 2S](#update-uefi-on-surface-hub-2s-to-enable-os-migration) para habilitar a seção de migração do sistema operacional deste artigo.

> [!NOTE]
> Depois de concluir a instalação, você precisará de uma licença válida para o Windows 10 Pro ou Windows 10 Enterprise separada da sua licença existente do Windows 10 Team.

1. Para criar uma instalação do Windows 10 Pro, siga as instruções para baixar a ferramenta de criação de mídia em [Baixar o Windows 10.](https://www.microsoft.com/software-download/windows10) Para baixar o Windows 10 Enterprise, vá para o Centro de Serviços de [Licenciamento por Volume da Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

1. Insira uma nova unidade de armazenamento USB.
1. Abra a ferramenta de criação de mídia, **selecione Criar mídia de**instalação e, em seguida, selecione **Próximo**.

   ![Screenshot shows the option to create installation media.](images/shm-fig16.png)
   
3. Selecione um idioma e selecione **Windows 10** e **64 bits (x64).** Em seguida, **selecione Next**.

   ![Screenshot shows where you select the language, O S edition, and architecture type.](images/shm-fig17.png)
   
4. Selecione **unidade flash USB**e, em seguida, selecione **Próximo**.

   ![Screenshot shows where to select U S B flash drive.](images/shm-fig18.png)
   
5. Quando o download terminar, selecione **Concluir**.

   ![A tela relata que a unidade U S B está pronta e inclui um botão Concluir.](images/shm-fig19.png)
   
6. Copie os arquivos de pacote SEMM e os drivers e o firmware do sistema operacional Windows 10 Pro e Enterprise no Surface Hub 2 (o arquivo MSI) para a raiz da unidade flash USB *(BOOTME)* que contém a imagem do Windows 10. A unidade USB BOOTME conterá:

    - Sua imagem inicializável do Windows 10.
    
    - Os arquivos de pacote SEMM, copiados para a raiz da unidade USB:
    
      - *DfciUpdate.dfi*.
      - Um arquivo de texto que inclui a impressão digital SEMM. (Neste exemplo, o arquivo é *SurfaceUEFI_2020Aug25_1058.txt*.) O carimbo de data e hora gerado automaticamente corresponde à data em que você criou o arquivo usando o Configurador UEFI do Surface.

   - Os drivers e o firmware do Sistema Operacional Windows 10 Pro e Enterprise no Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copie esse arquivo para a raiz da unidade USB.

### Atualizar a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional

1. Insira sua unidade BOOTME na porta USB-A no Surface Hub 2S. Para uma lista de seus conteúdos necessários, consulte a seção anterior.

1. Para inicializar na UEFI:

   1. Desligue (desligue) o Surface Hub 2S.
   1. Pressione e segure **Volume +** e pressione e solte o botão de energia. Mantenha mantendo **o volume +** até que o menu UEFI seja exibido.
   
      ![O desenho mostra os botões de volume e energia.](images/shm-fig20.png)
      
3. Quando o dispositivo for reiniciado, insira a senha UEFI criada anteriormente, se aplicável (recomendado).

   ![Tela de senha do sistema.](images/shm-fig22.png)
   
4. No menu UEFI, selecione **Gerenciamento**. Em seguida,  **selecione Instalar do USB**.

   ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)
   
5. Selecione **Reiniciar agora,** como mostra a imagem a seguir. O dispositivo será reiniciado agora. Ele exibirá um logotipo branco da Microsoft no meio da janela e será desligado.

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)
   
6. Pressione e solte o botão de energia. Na caixa de diálogo vermelha exibida, opte por ativar o Modo de Gerenciamento do Surface Enterprise.

7. Insira a impressão digital do certificado de dois caracteres e a senha de configurações da UEFI. Em seguida, **selecione OK**.

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)
 
   > [!NOTE]
   > Depois de ativar o SEMM em seu dispositivo, a nova configuração UEFI **EnableOSMigration** é aplicada. Você não pode mais acessar o Windows 10 Team. Em vez disso, você deve continuar para a próxima etapa e instalar o Windows 10 Pro ou Windows 10 Enterprise.

   O dispositivo é reiniciado. Ele exibe o logotipo branco no meio da tela e desliga novamente.

### Instalar o Windows 10 Pro ou Enterprise

1. Se sua unidade inicializável do Windows 10 Pro ou Enterprise ainda não estiver na porta USB-A do Surface Hub 2, insira-a agora. Em seguida, pressione e solte o botão de energia.

    Quando o dispositivo for iniciado, você verá o logotipo branco no meio da tela. Em seguida, um círculo giratório aparece abaixo do logotipo branco.

3. Se o dispositivo Surface não for inicializado automaticamente na unidade USB, desligue o dispositivo (desconecta o cabo de alimentação e conecte-o novamente). Depois de conectar o cabo de alimentação novamente, o dispositivo deve ser inicializado após alguns segundos. Em seguida, você verá o logotipo branco no meio da tela.

    Se o dispositivo não ligar, pressione e solte o botão de energia. Imediatamente depois de ver o logotipo no meio da tela, pressione e segure o botão de volume até ver o círculo giratório abaixo do logotipo branco.
 
   ![Imagem dos botões de volume e energia.](images/shm-fig26.png)
   
4. Quando a configuração inicial pelo usuário (OOBE) for iniciada, siga as instruções para instalar o Windows 10 Pro ou Enterprise (versão 1903 ou posterior).

### Instalar drivers e firmware do Surface Hub 2

Para garantir que o Surface Hub 2 está atualizado, instale drivers e firmware para [Windows 10 Pro e Enterprise.](https://www.microsoft.com/download/details.aspx?id=101974) Em seguida, reinicialize o dispositivo. Mantenha o Surface ligado por uma hora e reinicialize-o novamente. Você não será solicitado para a segunda reinicialização. Essa pausa e uma reinicialização extra garantem que o firmware tenha sido totalmente atualizado.
 
## Definir configurações recomendadas

Para configurar o Surface Hub 2S como um dispositivo de produtividade pessoal, consulte Configurar o [Windows 10 Pro ou Enterprise no Surface Hub 2.](surface-hub-2-post-install.md)

> [!NOTE]
>Se você não conseguir migrar seu dispositivo para o Windows 10 Pro ou Enterprise para o Surface Hub 2 seguindo as etapas descritas neste artigo, entre em contato com o Suporte do [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Para reverter para o Windows 10 Team

Se você quiser restaurar seu dispositivo para o Windows 10 Team, consulte Redefinir e [recuperar o Surface Hub 2S.](surface-hub-2s-recover-reset.md)

> [!NOTE]
> Antes de reverter para o Windows 10 Team, recomendamos que você primeiro desemrolle o Surface Hub do SEMM. Para saber mais, consulte [Unenroll dispositivos Surface do SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).

## Histórico de versões

A tabela a seguir resume as alterações neste artigo.

| Versão | Data               | Descrição                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 de dezembro de 2020 | Fornece [](#install-surface-hub-2-drivers-and-firmware) mais informações sobre como instalar o arquivo MSI para "Drivers e firmware para o sistema operacional Windows 10 Pro e Enterprise no Surface Hub 2", avisando que uma segunda reinicialização pode ser necessária dependendo do estado do seu sistema.                                                          |
| v. 1.3  | 3 de dezembro de 2020 | Atualizado com orientações sobre como [gerenciar o registro SEMM.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 29 de setembro de 2020 | Atualizações diversas que abordam os comentários de usabilidade.                                                        |
| v. 1.1  | 15 de setembro de 2020 | Foi colocada uma observação adicional na introdução que esclarece os requisitos de licenciamento para instalar um novo sistema operacional. |
| v. 1.0  | 1º de setembro de 2020  | Novo artigo.                                                                                           |
