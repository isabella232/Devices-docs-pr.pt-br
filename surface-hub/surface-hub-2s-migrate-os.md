---
title: Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2
description: Este artigo descreve como migrar da equipe do Windows 10 no Surface Hub 2 para o Windows 10 pro ou Windows 10 Enterprise.
keywords: Área de trabalho do Surface Hub, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/03/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 01c5c8a5c6b9f7ed657829fe792fc9eecd1facb5
ms.sourcegitcommit: 5d02cca9ca8c0a252798c2fc0a89dbda81911c44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195396"
---
# Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2

O Surface Hub 2S vem pré-instalado com o Windows 10 Team. Esta edição personalizada do Windows 10 foi projetada para facilitar a colaboração em ambientes de sala de reunião. Agora você tem a opção de executar o Windows 10 pro ou Enterprise para usar o Surface Hub 2S da mesma forma que qualquer outro computador. 

> [!IMPORTANT]
>Ao contrário de uma atualização ou migração típica, esse processo requer que você siga um procedimento prescritiva, conforme descrito neste artigo. Examine os [componentes da solução](#solution-components) e a [migração e o fluxo de trabalho de instalação](#migration-and-installation-workflow-summary) antes de continuar.


> [!NOTE]
> Ao instalar o Windows 10 pro ou Enterprise, você precisa de uma nova licença separada da sua licença existente do Windows 10 Team. 


Inicie a migração da equipe do Windows 10 usando um computador separado e o *configurador UEFI da superfície*de ferramenta para download. Use a ferramenta para criar um pacote que contém uma nova configuração de UEFI que você aplica ao Surface Hub 2S.  

O configurador UEFI da superfície funciona como uma interface no modo de gerenciamento do Surface Enterprise (SEMM). Ele foi projetado para facilitar o gerenciamento centralizado das configurações de firmware em dispositivos de superfície em um ambiente corporativo. Para obter mais informações, consulte a <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentação do Microsoft Semm</a>
 

## Componentes da solução

- Dispositivo Surface Hub 2S executando o sistema operacional da equipe do Windows 10
- Dispositivo separado executando o Windows 10
- Ferramenta configurador UEFI da Surface para criar o pacote SEMM
- Imagem do Windows 10 pro ou Enterprise OS, versão 1903 ou posterior
- Duas unidades USB com 16 GB de armazenamento, formato FAT32
- Os drivers e firmware para Windows 10 pro e Enterprise OS no arquivo do Surface Hub 2 Microsoft Windows Installer (MSI)
- Conexão com a Internet
- Solução de imagem (opcional)

 
## Resumo do fluxo de trabalho de migração e instalação

| Etapa  | Ação                                                                                                 | Resumo                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| um | [Verifique se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Certifique-se de que a versão UEFI seja 694.2938.768.0 ou posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Baixe os drivers e o firmware da Surface configuradora do Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Na página <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **ferramentas de superfície para ti** </a> , selecione **baixar**. Em seguida, selecione e baixe o **configurador UEFI de Surface. MSI** e instale o arquivo em um computador separado. Baixe os <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers e firmware para Windows 10 pro e Enterprise os no arquivo MSI Surface Hub 2.</a> Salve-o para uso na etapa 5. |
| 3D | [Prepare o certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepare o certificado necessário para executar o configurador UEFI da Surface. Ou use seu certificado atual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Crie um pacote SEMM.](#create-a-semm-package)                                                                               | Inicie o configurador UEFI da Surface para criar um pacote SEMM em uma unidade USB, que conterá os arquivos de configuração que você precisa aplicar no Surface Hub 2S. Copie esses arquivos de pacote SEMM para uma pasta em seu computador.                                                                                                                                                                                          |
| 5 | [Prepare a unidade flash USB que contém a imagem do Windows 10, o pacote SEMM e OS drivers e firmware para Windows 10 pro e Enterprise OS no Surface Hub 2.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crie uma única unidade USB que contenha uma imagem do Windows 10. Neste exemplo, a unidade é chamada *BOOTME*. Adicione seus drivers e firmware para Windows 10 pro e Enterprise OS no Surface Hub 2 (etapa 2) e SEMM arquivos de pacote (etapa 4) à unidade *BOOTME* .                                                                                                                                                                                                  |
| 5 | [Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use a unidade *BOOTME* para inicializar o Surface Hub 2s ao menu UEFI e instalar o pacote Semm.|
| 7 | [Instale o Windows 10 pro ou Enterprise versão 1903 ou posterior.](#install-windows-10-pro-or-enterprise)                                        | Use a unidade *BOOTME* para instalar o Windows 10 pro ou Enterprise versão 1903 ou posterior.                                                                                                                                                                                                                                                                                 |
| 08 | [Instale drivers e firmware para Windows 10 pro e Enterprise OS no Surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale os <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers e firmware para Windows 10 pro e Enterprise os no arquivo MSI do Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 222 | [Configure completamente o Surface Hub 2S como um dispositivo de produtividade pessoal.](#configure-recommended-settings)                                        |  Habilite as configurações e os aplicativos recomendados para otimizar o Surface Hub 2S como um dispositivo de produtividade pessoal.                                                                                                                                                                                                                                                                    |

### Verifique se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos

Antes de migrar o Surface Hub da equipe do Windows 10 para a área de trabalho do Windows 10, você precisa de uma versão UEFI que seja pelo menos *694.2938.768.0*.
 
**Para verificar a versão UEFI em seu sistema:**

1. Na home page do Surface Hub 2s, selecione **Iniciar**e, em seguida, abra o aplicativo Surface (superfície de**todos os aplicativos**  >  **Surface**).

2. Selecione **sua superfície** para exibir informações sobre o Surface Hub, incluindo a versão UEFI atual no dispositivo. 
   - Se a versão UEFI for *694.2938.768.0* ou posterior, conforme mostrado na imagem a seguir, você pode criar o pacote Semm para habilitar a migração do sistema operacional.

       ![Captura de tela mostrando a página de superfície no aplicativo Surface.](images/shm-fig1.png)
 
   - Se a versão UEFI for anterior à versão 694.2938.768.0, você precisará obter uma versão atual instalando a imagem do Window 10 Team 2020 Update Bare Metal Recovery (BMR) ou usando o Windows Update.
   
**Para atualizar a UEFI via Windows Update:**

1. No Surface Hub 2S, entre como **administrador**. 
    >[!Note]
    > Se você não souber seu nome de usuário ou senha de administrador, será necessário redefinir o dispositivo. Para obter mais informações, consulte <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> redefinir e recuperar para Surface Hub 2s.</a>

1. Vá para **todas**as configurações de aplicativos  >  **Settings**  >  **atualização e segurança**do  >  **Windows Update**e instale todas as atualizações. 
1. Reinicie o dispositivo. 
1. Verifique a versão UEFI usando o aplicativo Surface. 
1. Nesse ponto, se a versão de UEFI ainda não tiver a versão 694.2938.768.0 ou posterior, você pode repetir as etapas acima ou obter a UEFI mais recente instalando a imagem de BMR (recuperação bare-metal) do Windows 10 Team 2020 Update.

**Para atualizar a UEFI usando a imagem de recuperação bare-metal (BMR):**

1.  Vá para o [site de recuperação de superfície](https://support.microsoft.com/surfacerecoveryimage) e selecione **Surface Hub 2s**
3.  Digite o número de série do seu hub (localizado no lado traseiro do Hub ao lado da conexão de energia).
4.  Siga as instruções para baixar a imagem em uma unidade USB formatada por meio da instalação da atualização do Windows 10 Team 2020.
5.  Após a atualização ser completada e o dispositivo entrar na configuração do OOBE First setup, você não precisará concluir OOBE, a versão UEFI será atualizada. Em vez disso, desligue o dispositivo segurando o botão de energia até que a tela seja desativada. 

### Baixar os drivers e o firmware da Surface configuradora do Surface Hub 2

Em um computador separado:

1. Na <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> página ferramentas de superfície para ti </a> , selecione **baixar**.  
1. Selecione e baixe o arquivo MSI do Configurador UEFI do Surface e instale-o em um computador separado. A ferramenta de configurador UEFI de Surface não pode ser executada em um Surface Hub 2S enquanto a edição do Windows 10 Team está instalada.

1. Baixe os <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers do Surface Hub 2 e o arquivo MSI do Windows Installer do firmware </a> . Você usará esse arquivo quando instalar o novo sistema operacional.

### Preparar o certificado SEMM

Se você ainda não usou o configurador UEFI da Surface antes, será necessário preparar um certificado. Esse certificado garante que depois que um dispositivo é registrado no SEMM, você pode modificar as configurações de UEFI somente usando pacotes criados com o certificado aprovado. 

O modo como você recebe um certificado depende do tamanho ou da complexidade da sua organização:

- Geralmente, as organizações corporativas mantêm sua própria infraestrutura para gerar certificados de acordo com as práticas de segurança padrão.

- Empresas de médio porte e outras pessoas podem optar por obter certificados de provedores de parceiros. Essa opção é recomendada para organizações que não têm experiência de ti suficiente ou uma equipe de segurança de ti dedicada.

- Você também pode gerar um certificado auto-assinado usando um script do PowerShell. Para obter mais informações, consulte <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> requisitos do certificado do modo de gerenciamento da empresa Surface </a> . Ou você pode usar o PowerShell para criar seu próprio certificado. Para obter mais informações, consulte a <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> documentação do New-SelfSignedCertificate </a> .

O pacote SEMM que a Surface configuradora cria deve ser protegido com um certificado. O certificado verifica a assinatura de arquivos de configuração antes que as configurações de UEFI possam ser aplicadas. Para obter mais informações, consulte a <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentação do Semm </a> .
 
 
### Criar um pacote SEMM

1. Em um computador separado, instale a ferramenta de configurador UEFI do Surface que você baixou anteriormente. 

2. Abra o configurador UEFI da superfície e selecione **Iniciar**.

   ![Abrir o configurador UEFI de superfície aberta.](images/shm-fig2.png)
   
3. Selecione **dispositivos de superfície**e, em seguida, selecione **Avançar**.

   ![Selecione dispositivos de superfície.](images/shm-fig3.png)
  
4. Selecione **pacote de configuração**.

   ![Selecione pacote de configuração.](images/shm-fig4.png)
  
5. Selecione **proteção de certificado**.

   ![Selecione proteção de certificado.](images/shm-fig5.png)

   Você será solicitado a adicionar seu arquivo. pfx de certificado.

   ![Adicione seu certificado.](images/shm-fig6.png)
   
7. Digite sua senha de certificado e selecione **OK**.

   ![Digite sua senha de certificado e selecione OK.](images/shm-fig7.png)

8. Selecione **proteção por senha** para adicionar uma senha à UEFI da superfície. Você precisará dessa senha sempre que inicializar a UEFI. É *altamente recomendável* que você defina uma senha UEFI que você usará no Surface Hub 2s.

   ![Selecione proteção por senha.](images/shm-fig8.png)
   
9. Defina uma senha UEFI e, em seguida, selecione **OK**.

   > [!IMPORTANT]
   > Salve a senha em um local seguro que seja acessível para seus administradores de ti que gerenciam o Surface Hub. Se a senha for perdida, não será possível recuperá-la. 

   ![Digite sua senha UEFI.](images/shm-fig9.png)

10. Selecione **Surface Hub 2s**e, em seguida, selecione **Avançar**.

    ![Selecione Surface Hub 2S.](images/shm-fig10.png)
   
11. Selecione **Avançar**.

    ![Selecione Avançar.](images/shm-fig10a.png)

12. Para permitir a instalação do Windows 10 pro ou Enterprise, ative o **EnableOsMigration**e, em seguida, selecione **Avançar**.

    ![Selecione habilitar a migração do s.](images/shm-fig11.png)
    
    ![Defina habilitar migração do sistema operacional como ativado.](images/shm-fig12.png)

### Gerenciando o registro de SEMM

A inscrição de dispositivos no SEMM afeta a maneira como você pode gerenciar o dispositivo em andamento. Por exemplo, depois de aplicar um pacote SEMM, no menu UEFI do dispositivo, todas as configurações de UEFI não estarão disponíveis (bloqueadas). Os valores padrão para outras configurações, como **IPv6 para inicialização PXE** , também estão indisponíveis. 

Para alterar as configurações de UEFI após concluir a migração, aplique outro pacote SEMM ou cancele o registro do dispositivo do SEMM. Se você aplicar outro pacote SEMM para alterar as configurações de UEFI, será necessário usar o certificado original quando criar o novo pacote de SEMM. Use a ferramenta de configurador UEFI e deixe o **EnableOSMigration** desligado (não em, conforme mostrado nas etapas de migração originais).

#### Trabalhando com parceiros

Se a sua empresa estiver terceirizando a migração para o Windows 10 pro ou Enterprise no Surface Hub 2, talvez você queira que o parceiro transfira o certificado SEMM, o pacote SEMM e a senha UEFI para você.  Como alternativa, depois de migrar o Hub, você pode desregistrá-lo imediatamente do SEMM, o que permitirá a administração local da UEFI e da transferência do dispositivo para outro participante. No entanto, ainda é altamente recomendável usar uma senha UEFI, que pode ser configurada após a migração. Para saber mais, consulte [gerenciar configurações de Surface UEFI](https://docs.microsoft.com/surface/manage-surface-uefi-settings). 

#### Retornando à equipe do Windows 10

Se, após a migração, você optar por restaurar seu dispositivo para a equipe do Windows 10, [conforme descrito abaixo](#roll-back-to-windows-10-team), é recomendável primeiro cancelar o registro do hub de Semm. Para saber mais, consulte não [registrar dispositivos de superfície do Semm](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).


#### Salvar o pacote SEMM em uma unidade USB

1. Conecte uma unidade USB ao seu computador. 
1. Escolha **Hub 2s**e, em seguida, selecione **Avançar**.

   ![Selecionar USB](images/shm-fig13.png)

   > [!WARNING]
   > Todos os dados existentes na unidade USB são apagados quando o pacote SEMM é criado. Antes de compilar o pacote SEMM, remova todos os arquivos da unidade USB que você deseja salvar.
   
2. Selecione **Compilar**.

   ![Selecione Compilar.](images/shm-fig14.png)

3. Capture uma captura de tela desta página e selecione **terminar**. Seu pacote SEMM está pronto. Ele contém o pacote SEMM *DfciUpdate. DFI* e um arquivo de texto que inclui a impressão digital Semm (os dois últimos caracteres da impressão digital do certificado).

   ![Selecione finalizar.](images/shm-fig15.png)
   
4. Salve os dois últimos caracteres da impressão digital do certificado. Você precisará desses caracteres para ativar o SEMM quando aplicar o pacote no Surface Hub 2S.

### Preparar uma unidade flash USB que contenha uma imagem do Windows 10, um pacote SEMM e drivers e firmware Surface Hub 2

Você pode instalar uma imagem do Windows 10 pro ou Enterprise (versão 1903 ou posterior) usando uma das seguintes opções:

- Sua solução atual para imagens.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Acelerador de Deployment Surface </a> . Use esta ferramenta para criar uma imagem inicializável do Windows 10. A imagem pode incluir todas as atualizações atuais do Windows 10, o Office, outros aplicativos que você escolher e os drivers e firmware obrigatórios. 

- Unidade flash USB que contém uma imagem do Windows 10 pro ou Enterprise. Em seguida, instale <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers e firmware para Windows 10 pro e Enterprise os no Surface Hub 2 </a> .
 
O procedimento a seguir descreve como criar uma unidade flash USB da mídia de instalação e, em seguida, adicionar os arquivos de pacote SEMM e os drivers e firmware para o Windows 10 pro e o sistema operacional empresarial no arquivo MSI do Surface Hub 2. Se você estiver usando outros métodos de implantação, vá para a seção [atualizar a UEFI no Surface Hub 2s para habilitar a migração do sistema operacional](#update-uefi-on-surface-hub-2s-to-enable-os-migration) neste artigo.

> [!NOTE]
> Depois de concluir a instalação, você precisará de uma licença válida para o Windows 10 pro ou Windows 10 Enterprise que seja separada da sua licença existente do Windows 10 Team.

1. Para criar uma instalação do Windows 10 pro, na <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> página baixar o Windows 10 </a> , siga as instruções para baixar a ferramenta de criação de mídia. Para baixar o Windows 10 Enterprise, vá para o <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> centro de serviços de licenciamento por volume da Microsoft </a> .

2. Insira uma nova unidade de armazenamento USB. 
1. Abra a ferramenta de criação de mídia, selecione **criar mídia de instalação**e, em seguida, selecione **Avançar**.

   ![Criar mídia de instalação.](images/shm-fig16.png)
   
3. Selecione um idioma e, em seguida, escolha **Windows 10** e **64 bits (x64)**. Em seguida, selecione **Avançar**.

   ![Selecione idioma e escolha Windows 10 e 64 bits. Em seguida, selecione avançar.](images/shm-fig17.png)
   
4. Selecione **unidade flash USB**e, em seguida, selecione **Avançar**.

   ![Selecione a unidade flash S B e selecione avançar.](images/shm-fig18.png)
   
5. Quando o download terminar, selecione **concluir**.

   ![Selecione concluir.](images/shm-fig19.png)
   
6. Copie os arquivos de pacote SEMM e os drivers e firmware para Windows 10 pro e Enterprise OS no Surface Hub 2 (o arquivo MSI) para a raiz da unidade flash USB (*BOOTME*) que contém a imagem do Windows 10. A unidade USB BOOTME contém:

    - Sua imagem inicializável do Windows 10.
    
    - Arquivos de pacote SEMM (copiados para a raiz da unidade USB).
    
      - *DfciUpdate. DFI*.
      - Arquivo de texto que inclui a impressão digital SEMM. (Neste exemplo, o arquivo é *SurfaceUEFI_2020Aug25_1058.txt*.) O carimbo de data/hora de data gerado automaticamente corresponde à data em que você criou o arquivo usando o configurador UEFI de Surface.

   - Drivers e firmware para Windows 10 pro e Enterprise OS no Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copie esse arquivo para a raiz da unidade USB.

### Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional

1. Insira sua unidade BOOTME na porta USB-A no Surface Hub 2S. Para obter uma lista de arquivos obrigatórios, consulte a seção anterior.

2. Para inicializar o UEFI:

   1. Desative o (desligar) seu Surface Hub 2S.
   1. Pressione e mantenha pressionado o **volume +** e, em seguida, pressione e solte o botão de energia.
   1. Mantenha a retenção do **volume +** até que o menu UEFI seja exibido.
   
      ![Pressione e mantenha pressionado o botão volume-up até que o menu UEFI seja exibido.](images/shm-fig20.png)
      
3. Quando o dispositivo for reiniciado, insira a senha UEFI que você criou anteriormente, se aplicável (altamente recomendado).

   ![Digite a senha UEFI.](images/shm-fig22.png)
   
4. No menu UEFI, selecione **Management**  >  **instalação de gerenciamento do USB**.

   ![Selecione gerenciamento e instalação a partir de U S B.](images/shm-fig21.png)
   
5. Selecione **reiniciar agora**, conforme mostrado na imagem a seguir. O dispositivo é reiniciado. Ele exibe um logotipo branco da Microsoft no meio da janela e, em seguida, desliga.

   ![Selecione reiniciar agora.](images/shm-fig25.png)
   
6. Pressione e libere o botão de energia. Na janela vermelha exibida, ative o modo de gerenciamento de organização Surface. 

7. Insira sua impressão digital do certificado de dois caracteres e a senha das configurações de UEFI. Em seguida, selecione **OK**.

   ![Insira sua impressão digital do certificado de dois caracteres e a senha das configurações de UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Depois de ativar o SEMM em seu dispositivo, o novo **EnableOSMigration** de configuração UEFI será aplicado. Você não poderá mais acessar a equipe do Windows 10. Em vez disso, você deve continuar para a próxima etapa e instalar o Windows 10 pro ou o Windows 10 Enterprise. 

   O dispositivo é reiniciado. Ele exibe o logotipo branco no meio da tela e, em seguida, desliga novamente.

### Instalar o Windows 10 pro ou Enterprise

1. Se sua unidade Windows 10 pro ou Enterprise inicializável ainda não estiver na porta USB-A do Surface Hub 2-A, insira-A agora. Em seguida, pressione e solte o botão de energia. 

    Quando o dispositivo for iniciado, você verá o logotipo branco no meio da tela. Em seguida, você vê um círculo girando abaixo do logotipo branco.

3. Se o dispositivo não inicializar automaticamente na unidade USB, desligue o dispositivo (desconecte o cabo de alimentação e conecte-o novamente). Depois de conectar o cabo de alimentação novamente, o dispositivo deve ser inicializado após alguns segundos. Em seguida, você verá o logotipo branco no meio da tela. 

    Se o dispositivo não acender, pressione e libere o botão de energia. Logo após ver o logotipo no meio da tela, pressione e mantenha pressionado o botão volume até ver o círculo girando abaixo do logotipo branco.
 
   ![Inicialize no Windows 10 a partir da unidade U S B.](images/shm-fig26.png)
   
4. Quando a configuração do OOBE (configuração inicial pelo programa) for iniciada, siga as instruções para instalar o Windows 10 pro ou Enterprise (versão 1903 ou posterior).

### Instalar drivers e firmware do Surface Hub 2

Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers e firmware para Windows 10 pro e Enterprise os no Surface Hub 2 </a> .
 
## Configurar as definições recomendadas

Para configurar completamente o Surface Hub 2S como um dispositivo de produtividade pessoal, consulte <a href="surface-hub-2-post-install.md" target="_blank"> Configurar o Windows 10 pro ou Enterprise no Surface Hub 2 </a> .

> [!NOTE]
>Se as etapas descritas neste artigo não migrarem com êxito seu dispositivo para o Windows 10 pro ou Enterprise para Surface Hub 2, entre em contato com o <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> suporte do Surface Hub </a> .

## Reverter para a equipe do Windows 10

Se você quiser restaurar seu dispositivo para a equipe do Windows 10, consulte <a href="surface-hub-2s-recover-reset.md" target="_blank"> redefinir e recuperar para Surface Hub 2s </a> .

> [!NOTE]
> Antes de reverter para a equipe do Windows 10, é recomendável primeiro cancelar o registro do hub de SEMM. Para saber mais, consulte não [registrar dispositivos de superfície do Semm](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).

## Histórico de versões

A tabela a seguir resume as alterações deste artigo.

| Versão | Data               | Descrição                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| m. 1,3  | 3 de dezembro de 2020 | Atualização com diretrizes sobre o gerenciamento de registro de SEMM                                                        |
| m. 1,2  | 29 de setembro de 2020 | Atualizações diversas que tratam dos comentários de usabilidade.                                                        |
| m. 1,1  | 15 de setembro de 2020 | Você fez uma observação adicional na introdução que esclarece os requisitos de licenciamento para instalar um novo sistema operacional. |
| m. 1.0  | 1 de setembro de 2020  | Novo artigo.                                                                                           |
