---
title: Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2
description: Este artigo descreve como migrar do Windows 10 Team no Surface Hub 2 para o Windows 10 Pro ou Windows 10 Enterprise.
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
ms.openlocfilehash: 9878e64e414f4fe9ec3abfbd49adf233edc1da1d
ms.sourcegitcommit: 53d1eac8840fafbcd155798fce0d8c843f48dca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "11255483"
---
# Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2

- [Histórico de versão do artigo](#version-history)

O Surface Hub 2S vem pré-instalado com o Windows 10 Team. Esta edição personalizada do Windows 10 foi projetada para facilitar a colaboração em ambientes de sala de reunião. Agora você tem a opção de executar o Windows 10 Pro ou Enterprise para usar o Surface Hub 2S como qualquer outro computador. 

> [!IMPORTANT]
>Ao contrário de uma atualização ou migração típica, esse processo exige que você siga um procedimento prescritivo, conforme descrito neste artigo. Revise os [componentes da solução e](#solution-components) [o fluxo de trabalho de migração e instalação](#migration-and-installation-workflow-summary) antes de continuar.


> [!NOTE]
> Ao instalar o Windows 10 Pro ou Enterprise, você precisa de uma nova licença separada da sua licença existente do Windows 10 Team. 


Inicie a migração do Windows 10 Team usando um computador separado e a ferramenta para download do *Configurador UEFI do Surface.* Use a ferramenta para criar um pacote que contém uma nova configuração UEFI que você aplica ao Surface Hub 2S.  

O Configurador UEFI do Surface funciona como uma interface para o Surface Enterprise Management Mode (SEMM). Ele foi projetado para facilitar o gerenciamento centralizado de configurações de firmware em dispositivos Surface em um ambiente corporativo. Para obter mais informações, consulte a <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentação do Microsoft SEMM. </a>
 

## Componentes da solução

- Dispositivo Surface Hub 2S executando o sistema operacional Windows 10 Team
- Dispositivo separado executando o Windows 10
- Ferramenta Configurador UEFI do Surface para criar o pacote SEMM
- Imagem do sistema operacional Windows 10 Pro ou Enterprise, versão 1903 ou posterior
- Duas unidades USB com 16 GB de armazenamento, formato FAT32
- Os drivers e o firmware para o sistema operacional Windows 10 Pro e Enterprise no arquivo MSI (Microsoft Windows Installer) do Surface Hub 2
- Conexão com a Internet
- Solução de imagem (opcional)

 
## Resumo do fluxo de trabalho de migração e instalação

| Etapa  | Ação                                                                                                 | Resumo                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Verifique se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Verifique se a versão UEFI é 694.2938.768.0 ou posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Baixe o configurador UEFI do Surface e os drivers e o firmware do Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Na página <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **Ferramentas do Surface para IT,** </a> selecione **Baixar.** Em seguida, selecione e baixe o **Configurador UEFI do Surface. Arquivo MSI e** instale-o em um computador separado. Baixe os <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers e o firmware para o sistema operacional Windows 10 Pro e Enterprise no arquivo MSI do Surface Hub 2.</a> Salve-o para uso na etapa 5. |
| 3 | [Prepare o certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepare o certificado necessário para executar o Configurador UEFI do Surface. Ou use seu certificado atual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Crie um pacote SEMM.](#create-a-semm-package)                                                                               | Inicie o Configurador UEFI do Surface para criar um pacote SEMM em uma unidade USB, que conterá os arquivos de configuração que você precisa aplicar no Surface Hub 2S. Copie esses arquivos de pacote SEMM para uma pasta em seu computador.                                                                                                                                                                                          |
| 5 | [Prepare a unidade flash USB que contém imagem do Windows 10, pacote SEMM e drivers e firmware para o sistema operacional Windows 10 Pro e Enterprise no Surface Hub 2.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crie uma única unidade USB que contenha uma imagem do Windows 10. Neste exemplo, a unidade é chamada *BOOTME*. Adicione seus drivers e firmware para o Sistema Operacional Windows 10 Pro e Enterprise no Surface Hub 2 (etapa 2) e arquivos de pacote SEMM (etapa 4) à unidade *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use a *unidade BOOTME* para inicializar o Surface Hub 2S no menu UEFI e instalar o pacote SEMM.|
| 7 | [Instale o Windows 10 Pro ou Enterprise versão 1903 ou posterior.](#install-windows-10-pro-or-enterprise)                                        | Use a *unidade BOOTME* para instalar o Windows 10 Pro ou Enterprise versão 1903 ou posterior.                                                                                                                                                                                                                                                                                 |
| 8 | [Instale drivers e firmware para o Sistema Operacional Windows 10 Pro e Enterprise no Surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale os drivers e o firmware do sistema operacional Windows 10 Pro e Enterprise no arquivo <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> MSI do Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configure totalmente o Surface Hub 2S como um dispositivo de produtividade pessoal.](#configure-recommended-settings)                                        |  Habilitar configurações e aplicativos recomendados para otimizar o Surface Hub 2S como um dispositivo de produtividade pessoal.                                                                                                                                                                                                                                                                    |

### Verificar se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos

Antes de migrar o Surface Hub do Windows 10 Team para a Área de Trabalho do Windows 10, você precisa de uma versão UEFI que seja pelo menos *694.2938.768.0.*
 
**Para verificar a versão UEFI em seu sistema:**

1. Na home page do Surface Hub 2S, selecione **Iniciar**e abra o aplicativo do Surface (**Todos os Aplicativos**  >  **Surface**).

2. Selecione **o Surface** para exibir informações sobre o Surface Hub, incluindo a versão UEFI atual no dispositivo. 
   - Se a versão UEFI for *694.2938.768.0* ou posterior, como mostra a imagem a seguir, você poderá criar o pacote SEMM para habilitar a migração do sistema operacional.

       ![Captura de tela mostrando a página Seu Surface no aplicativo do Surface.](images/shm-fig1.png)
 
   - Se a versão UEFI for anterior à versão 694.2938.768.0, você precisará obter uma versão atual instalando a imagem do Windows 10 Team 2020 Update Bare Metal Recovery (BMR) ou usando o Windows Update.
   
**Para atualizar a UEFI por meio do Windows Update:**

1. No Surface Hub 2S, entre como **Administrador.** 

    >[!Note]
    > Se você não sabe seu nome de usuário ou senha de administrador, precisará redefinir o dispositivo. Para obter mais informações, consulte <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Redefinir e recuperar o Surface Hub 2S.</a>

1. Vá para **Todos os**  >  **aplicativos Atualização de**  >  **Configurações e**Segurança do Windows  >  **Update**e instale todas as atualizações. 

1. Reinicie o dispositivo. 

1. Verifique a versão UEFI usando o aplicativo Surface.

1. Neste ponto, se a versão UEFI ainda não tiver a versão 694.2938.768.0 ou posterior, você poderá repetir as etapas acima ou obter a UEFI mais recente instalando a imagem do Windows 10 Team 2020 Update Bare Metal Recovery (BMR).

**Para atualizar a UEFI por meio da imagem do Bare Metal Recovery (BMR) :**

1.  Vá para o [site de recuperação do Surface](https://support.microsoft.com/surfacerecoveryimage) e selecione Surface Hub **2S.**

3.  Insira o Número de Série do Hub (localizado na parte traseira do Hub ao lado da conexão de energia).

4.  Siga as instruções para baixar a imagem em uma unidade USB formatada por meio da instalação do Windows 10 Team 2020 Update.

5.  Depois que a atualização tiver sido concluída e o dispositivo entrar na instalação OOBE pela primeira vez, você não precisará concluir o OOBE, a versão UEFI será atualizada. Em vez disso, desliga o dispositivo mantendo pressionado o botão de energia até que a tela seja desligada. 

### Baixar firmware e drivers do Surface UEFI Configurator e do Surface Hub 2

Em um computador separado:

1. Na página <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Ferramentas do Surface para </a> IT, selecione **Baixar.**

1. Selecione e baixe o arquivo MSI do Configurador UEFI do Surface e instale-o em um computador separado. A ferramenta Configurador UEFI do Surface não pode ser executado em um Surface Hub 2S enquanto a edição Windows 10 Team estiver instalada.

1. Baixe o arquivo MSI do Windows Installer de drivers e firmware do <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub </a> 2. Você usará esse arquivo ao instalar o novo sistema operacional.

### Preparar o certificado SEMM

Se você ainda não usou o Configurador UEFI do Surface antes, precisará preparar um certificado. Esse certificado garante que, depois que um dispositivo for inscrito no SEMM, você só poderá modificar as configurações UEFI usando pacotes criados com o certificado aprovado. 

A forma como você obter um certificado depende do tamanho ou da complexidade da sua organização:

- As organizações corporativas geralmente mantêm sua própria infraestrutura para gerar certificados de acordo com as práticas de segurança padrão.

- Empresas de médio porte e outras pessoas podem optar por obter certificados de provedores parceiros. Essa opção é recomendada para organizações que não têm experiência em IT suficiente ou uma equipe de segurança de IT dedicada.

- Como alternativa, você pode gerar um certificado auto-assinado usando um script do PowerShell. Para obter mais informações, consulte os requisitos <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> de certificado do Modo de Gerenciamento do Surface </a> Enterprise. Ou você pode usar o PowerShell para criar seu próprio certificado. Para obter mais informações, consulte a <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> documentação New-SelfSignedCertificate. </a>

O pacote SEMM que o Configurador UEFI do Surface cria deve ser protegido com um certificado. O certificado verifica a assinatura dos arquivos de configuração antes que as configurações de UEFI possam ser aplicadas. Para obter mais informações, consulte a <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentação do </a> SEMM.
 
 
### Criar um pacote SEMM

1. Em um computador separado, instale a ferramenta Configurador UEFI do Surface que você baixou anteriormente. 

2. Abra o Configurador UEFI do Surface e selecione **Iniciar.**

   ![Abra o Configurador UEFI do Surface.](images/shm-fig2.png)
   
3. Selecione **Dispositivos Surface**e, em seguida, **selecione Próximo.**

   ![Selecione dispositivos Surface.](images/shm-fig3.png)
  
4. Selecione **Pacote de Configuração.**

   ![Selecione Pacote de Configuração.](images/shm-fig4.png)
  
5. Selecione **Proteção de Certificado.**

   ![Selecione Proteção de Certificado.](images/shm-fig5.png)

   Você será solicitado a adicionar seu arquivo .pfx de certificado.

   ![Adicione seu certificado.](images/shm-fig6.png)
   
7. Insira sua senha de certificado e selecione **OK.**

   ![Insira sua senha de certificado e selecione OK.](images/shm-fig7.png)

8. Selecione **Proteção por Senha** para adicionar uma senha à UEFI do Surface. Você precisará dessa senha sempre que inicializar para UEFI. É *recomendável definir* uma senha UEFI que você usará no Surface Hub 2S.

   ![Selecione Proteção por Senha.](images/shm-fig8.png)
   
9. Definir uma senha UEFI e, em seguida, selecione **OK**.

   > [!IMPORTANT]
   > Salve a senha em um local seguro que seja acessível para os administradores de IT que gerenciam o Surface Hub. Se a senha for perdida, ela não poderá ser recuperada. 

   ![Insira sua senha UEFI.](images/shm-fig9.png)

10. Selecione **Surface Hub 2S**e, em seguida, **Clique em Próximo.**

    ![Selecione o Surface Hub 2S.](images/shm-fig10.png)
   
11. Selecione **Avançar**.

    ![Selecione Avançar.](images/shm-fig10a.png)

12. Para permitir a instalação do Windows 10 Pro ou Enterprise, ative **EnableOsMigration**e selecione **Next**.

    ![Selecione Habilitar Migração O S.](images/shm-fig11.png)
    
    ![Definir Habilitar Migração do Sistema Operacional como Ativado.](images/shm-fig12.png)

### Gerenciando o registro SEMM

Registrar dispositivos no SEMM afeta como você pode gerenciar o dispositivo no futuro. Por exemplo, depois de aplicar um pacote SEMM, no menu UEFI do dispositivo, todas as configurações UEFI ficam indisponíveis (bloqueadas). Os valores padrão para outras configurações, como **IPv6 para Inicialização PXE,** também não estão disponíveis. 

Para alterar as configurações de UEFI após concluir a migração, aplique outro pacote SEMM ou desfaça o logon do dispositivo no SEMM. Se você aplicar outro pacote SEMM para alterar as configurações de UEFI, deverá usar o certificado original ao criar o novo pacote SEMM. Use a ferramenta Configurador UEFI e deixe **EnableOSMigration** desligado (não ativado, conforme mostrado nas etapas de migração originais).

#### Trabalhar com parceiros

Se sua empresa estiver terceirizando a migração para o Windows 10 Pro ou Enterprise no Surface Hub 2, talvez você queira que o parceiro transfira o certificado SEMM, o pacote SEMM e a senha UEFI para você.  Como alternativa, depois de migrar o Hub, você pode desinscrita-lo imediatamente do SEMM, o que permitirá a administração local da UEFI e a transferência do dispositivo para outra parte. No entanto, ainda é altamente recomendável usar uma senha UEFI, que pode ser configurada após a migração. Para saber mais, consulte [Gerenciar configurações de UEFI do Surface.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Reverter para o Windows 10 Team

Se, após a migração, você optar por restaurar seu dispositivo para o Windows 10 [Team,](#roll-back-to-windows-10-team)conforme descrito abaixo, é recomendável primeiro desincedir o Hub do SEMM. Para saber mais, consulte [Unenroll dispositivos Surface do SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).


#### Salvar o pacote SEMM em uma unidade USB

1. Conecte uma unidade USB ao computador. 

1. Choose **Hub 2S**, and then select **Next**.

   ![Selecionar USB](images/shm-fig13.png)

   > [!WARNING]
   > Todos os dados existentes na unidade USB são apagados quando o pacote SEMM é criado. Antes de criar o pacote SEMM, remova todos os arquivos da unidade USB que você deseja salvar.
   
2. Selecione **Build**.

   ![Selecione Build.](images/shm-fig14.png)

3. Capture uma captura de tela desta página e selecione **End**. Seu pacote SEMM agora está pronto. Ele contém o pacote SEMM *DfciUpdate.dfi* e um arquivo de texto que inclui a impressão digital SEMM (os dois últimos caracteres da impressão digital do certificado).

   ![Selecione End.](images/shm-fig15.png)
   
4. Salve os dois últimos caracteres da impressão digital do certificado. Você precisará desses caracteres para ativar o SEMM ao aplicar o pacote no Surface Hub 2S.

### Preparar uma unidade flash USB que contenha uma imagem do Windows 10, um pacote SEMM e drivers e firmware do Surface Hub 2

Você pode instalar uma imagem do Windows 10 Pro ou Enterprise (versão 1903 ou posterior) usando uma das seguintes opções:

- Sua solução de imagem atual.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Surface Deployment Accelerator </a> . Use essa ferramenta para criar uma imagem inicializável do Windows 10. A imagem pode incluir todas as atualizações atuais do Windows 10, o Office, outros aplicativos que você escolher e os drivers e firmware necessários. 

- Unidade flash USB que contém uma imagem do Windows 10 Pro ou Enterprise. Em seguida, instale drivers e firmware para o Sistema Operacional <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows 10 Pro e Enterprise no Surface Hub 2. </a>
 
O procedimento a seguir descreve como criar uma unidade flash USB a partir da mídia de instalação e, em seguida, adicionar os arquivos de pacote SEMM e os Drivers e Firmware para o Sistema Operacional Windows 10 Pro e Enterprise no arquivo MSI do Surface Hub 2. Se você estiver usando outros métodos de implantação, vá para Atualizar UEFI no [Surface Hub 2S](#update-uefi-on-surface-hub-2s-to-enable-os-migration) para habilitar a seção de migração do sistema operacional neste artigo.

> [!NOTE]
> Depois de concluir a instalação, você precisará de uma licença válida para o Windows 10 Pro ou Windows 10 Enterprise separada da sua licença existente do Windows 10 Team.

1. Para criar uma instalação do Windows 10 Pro, na página Baixar o Windows 10, siga as instruções para baixar a <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> ferramenta de criação de </a> mídia. Para baixar o Windows 10 Enterprise, vá para o Centro de Serviços de <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Licenciamento por Volume da </a> Microsoft.

1. Insira uma nova unidade de armazenamento USB. 

1. Abra a ferramenta de criação de mídia, **selecione Criar mídia de**instalação e, em seguida, selecione **Próximo**.

   ![Criar mídia de instalação.](images/shm-fig16.png)
   
1. Selecione um idioma e escolha **o Windows 10** e **64 bits (x64).** Em seguida, **selecione Next**.

   ![Selecione o idioma e escolha o Windows 10 e 64 bits. Em seguida, selecione Next.](images/shm-fig17.png)
   
1. Selecione **unidade flash USB**e, em seguida, selecione **Próximo**.

   ![Selecione a unidade flash U S B e selecione Next.](images/shm-fig18.png)
   
1. Quando o download terminar, selecione **Concluir**.

   ![Selecione Concluir.](images/shm-fig19.png)
   
1. Copie os arquivos de pacote SEMM e os drivers e o firmware do sistema operacional Windows 10 Pro e Enterprise no Surface Hub 2 (o arquivo MSI) para a raiz da unidade flash USB *(BOOTME)* que contém a imagem do Windows 10. A unidade USB BOOTME contém:

    - Sua imagem inicializável do Windows 10.
    
    - Arquivos de pacote SEMM (copiados para a raiz da unidade USB).
    
      - *DfciUpdate.dfi*.
      - Arquivo de texto que inclui a impressão digital SEMM. (Neste exemplo, o arquivo é *SurfaceUEFI_2020Aug25_1058.txt*.) O carimbo de data/hora gerado automaticamente corresponde à data em que você criou o arquivo usando o Configurador UEFI do Surface.

   - Drivers e firmware para o Sistema Operacional Windows 10 Pro e Enterprise no Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copie esse arquivo para a raiz da unidade USB.

### Atualizar a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional

1. Insira sua unidade BOOTME na porta USB-A no Surface Hub 2S. Para uma lista dos arquivos necessários, consulte a seção anterior.

2. Para inicializar na UEFI:

   1. Desligue (desligue) o Surface Hub 2S.
   1. Pressione e segure **Volume +** e pressione e solte o botão de energia.
   1. Mantenha mantendo **o volume +** até que o menu UEFI seja exibido.
   
      ![Pressione e segure o botão de volume até que o menu UEFI seja exibido.](images/shm-fig20.png)
      
3. Quando o dispositivo for reiniciado, insira a senha UEFI criada anteriormente, se aplicável (altamente recomendável).

   ![Insira a senha UEFI.](images/shm-fig22.png)
   
4. No menu UEFI, selecione **Instalação de Gerenciamento**via  >  **USB.**

   ![Selecione Gerenciamento e Instalação a partir dos EUA B.](images/shm-fig21.png)
   
5. Selecione **Reiniciar agora,** como mostra a imagem a seguir. O dispositivo é reiniciado. Ele exibe um logotipo branco da Microsoft no meio da janela e desliga.

   ![Selecione Reiniciar agora.](images/shm-fig25.png)
   
6. Pressione e solte o botão de energia. Na janela vermelha exibida, ative o Modo de Gerenciamento do Surface Enterprise. 

7. Insira a impressão digital do certificado de dois caracteres e a senha de configurações da UEFI. Em seguida, **selecione OK**.

   ![Insira a impressão digital do certificado de dois caracteres e a senha de configurações da UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Depois de ativar o SEMM em seu dispositivo, a nova configuração UEFI **EnableOSMigration** é aplicada. Você não poderá mais acessar o Windows 10 Team. Em vez disso, você deve continuar para a próxima etapa e instalar o Windows 10 Pro ou Windows 10 Enterprise. 

   O dispositivo é reiniciado. Ele exibe o logotipo branco no meio da tela e desliga novamente.

### Instalar o Windows 10 Pro ou Enterprise

1. Se sua unidade inicializável do Windows 10 Pro ou Enterprise ainda não estiver na porta USB-A do Surface Hub 2, insira-a agora. Em seguida, pressione e solte o botão de energia. 

    Quando o dispositivo é iniciado, você vê o logotipo branco no meio da tela. Em seguida, você verá um círculo giratório abaixo do logotipo branco.

3. Se o dispositivo não for inicializado automaticamente na unidade USB, desligue o dispositivo (desconecta o cabo de alimentação e conecte-o novamente). Depois de conectar o cabo de alimentação novamente, o dispositivo deve ser inicializado após alguns segundos. Em seguida, você verá o logotipo branco no meio da tela. 

    Se o dispositivo não ligar, pressione e solte o botão de energia. Imediatamente depois de ver o logotipo no meio da tela, pressione e segure o **botão Volume -** até ver o círculo giratório abaixo do logotipo branco.
 
   ![Inicializar para o Windows 10 a partir da unidade U S B.](images/shm-fig26.png)
   
4. Quando a configuração inicial pelo usuário (OOBE) for iniciada, siga as instruções para instalar o Windows 10 Pro ou Enterprise (versão 1903 ou posterior).

### Instalar drivers e firmware do Surface Hub 2

Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale drivers e firmware para o sistema operacional <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows 10 Pro e Enterprise no Surface Hub 2. </a> Após a instalação dos drivers e do firmware MSI, reinicie o dispositivo. Em seguida, depois de rea energia do Hub, mantenha o computador conectado por uma hora e reinicie o dispositivo. Você não será solicitado para a segunda reinicialização. Dependendo do estado do computador antes de migrar para o Windows 10 Pro ou Enterprise, esta segunda etapa pode ser necessária para garantir que todo o firmware tenha sido atualizado.
 
## Definir configurações recomendadas

Para configurar totalmente o Surface Hub 2S como um dispositivo de produtividade pessoal, consulte Configurar o <a href="surface-hub-2-post-install.md" target="_blank"> Windows 10 Pro ou Enterprise no Surface Hub 2. </a>

> [!NOTE]
>Se as etapas descritas neste artigo não migrarem com êxito seu dispositivo para o Windows 10 Pro ou Enterprise para o Surface Hub 2, entre em contato com o Suporte do <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface </a> Hub.

## Reverter para o Windows 10 Team

Se você quiser restaurar seu dispositivo para o Windows 10 Team, consulte Redefinir e <a href="surface-hub-2s-recover-reset.md" target="_blank"> recuperar o Surface Hub 2S. </a>

> [!NOTE]
> Antes de reverter para o Windows 10 Team, é recomendável primeiro desemrollar o Hub do SEMM. Para saber mais, consulte [Unenroll dispositivos Surface do SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).

## Histórico de versões

A tabela a seguir resume as alterações neste artigo.

| Versão | Data               | Descrição                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 de dezembro de 2020 | Fornece [](#install-surface-hub-2-drivers-and-firmware) mais informações sobre como instalar o arquivo MSI para "Drivers e firmware para o sistema operacional Windows 10 Pro e Enterprise no Surface Hub 2", avisando que uma segunda reinicialização pode ser necessária dependendo do estado do seu sistema.                                                          |
| v. 1.3  | 3 de dezembro de 2020 | Atualizado com orientações sobre como [gerenciar o registro SEMM.](#managing-semm-enrollment)                                                       |
| v. 1.2  | 29 de setembro de 2020 | Atualizações diversas que abordam os comentários de usabilidade.                                                        |
| v. 1.1  | 15 de setembro de 2020 | Foi colocada uma observação adicional na introdução que esclarece os requisitos de licenciamento para instalar um novo sistema operacional. |
| v. 1.0  | 1º de setembro de 2020  | Novo artigo.                                                                                           |
