---
title: Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2
description: Este artigo descreve o processo de migração da equipe do Windows 10 no Surface Hub 2 para o Windows 10 pro ou o Windows 10 Enterprise.
keywords: Área de trabalho do Surface Hub, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/29/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0c6a52d1023377f51ae6a63879e54b86db16cb9a
ms.sourcegitcommit: 35f64110ce8e0c0b019b02023d746f648f554c1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088625"
---
# Migrar para o Windows 10 Pro ou para o Enterprise no Surface Hub 2

## Introdução

O Surface Hub 2S vem pré-instalado com o Windows 10 Team, uma edição personalizada do Windows 10 desenvolvida para facilitar a colaboração em ambientes de sala de reunião. Agora você tem a opção de executar o Windows 10 pro ou Enterprise para usar o Surface Hub 2S da mesma forma que qualquer outro computador. 

> [!IMPORTANT]
>Ao contrário de uma atualização ou migração típica, esse processo requer que você siga um procedimento prescritiva, conforme descrito nesta página. Examine os [componentes da solução](#solution-components) e a [migração e o fluxo de trabalho de instalação](#migration-and-installation-workflow-summary) antes de prosseguir.


> [!NOTE]
> Ao instalar o Windows 10 pro ou Enterprise, você precisará de uma nova licença separada da sua licença existente do Windows 10 Team. 


Você inicia a migração da equipe do Windows 10 usando um computador separado e uma ferramenta para download-- **Surface configurador UEFI** --para criar um pacote contendo uma nova configuração de UEFI que você aplica ao Surface Hub 2s.  O configurador UEFI do Surface funciona como uma interface no modo de gerenciamento do Surface Enterprise (SEMM), projetado para facilitar o gerenciamento centralizado das configurações de firmware em dispositivos de superfície em um ambiente corporativo. Para saber mais sobre o SEMM, confira [documentação do modo de gerenciamento do Surface Enterprise da Microsoft](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 

## Componentes da solução

- Dispositivo Surface Hub 2S executando o sistema operacional de equipe do Windows 10
- Dispositivo separado executando o Windows 10
- Ferramenta configurador UEFI da Surface para criar o pacote SEMM
- Imagem do Windows 10 pro ou Enterprise OS, versão 1903 ou posterior
- Duas unidades USB com 16 GB de armazenamento, formato FAT32
- Drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2, Windows Installer. Arquivo MSI
- Conexão com a Internet
- Solução de imagem (opcional)

 
## Resumo do fluxo de trabalho de migração e instalação

| Etapa  | Ação                                                                                                 | Resumo                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| um | [Verifique se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Certifique-se de que a versão UEFI seja 694.2938.768.0 ou posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Baixar os drivers e o firmware da Surface configuradora do Surface Hub 2](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Selecione o botão baixar na página [ferramentas de superfície para ti](https://www.microsoft.com/download/details.aspx?id=46703) , selecione e baixe o **configurador UEFI de Surface. MSI** e instale o arquivo em um computador separado. Baixe [drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. MSI](https://www.microsoft.com/download/details.aspx?id=101974) e salve o arquivo para usá-lo para uso na etapa 5. |
| 3D | [Preparar certificado SEMM](#prepare-semm-certificate)                                                                          | Prepare o certificado obrigatório para executar o configurador UEFI de Surface ou use seu certificado atual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Criar pacote SEMM](#create-semm-package)                                                                               | Inicie o configurador UEFI da Surface para criar um pacote SEMM em uma unidade USB que conterá os arquivos de configuração necessários para aplicar no Surface Hub 2S. Copie esses arquivos de pacote SEMM para uma pasta em seu computador.                                                                                                                                                                                          |
| 5 | [Preparar a unidade flash USB contendo a imagem do Windows 10, o pacote SEMM e os drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crie uma única unidade USB (chamada **BOOTME** neste exemplo) contendo uma imagem do Windows 10. Adicione seus drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2 (etapa 2) e SEMM arquivos de pacote (etapa 4) à unidade **BOOTME** .                                                                                                                                                                                                  |
| 5 | [Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use a unidade **BOOTME** para inicializar o Surface Hub 2s ao menu UEFI e instalar o pacote Semm.|
| 7 | [Instalar o Windows 10 pro ou Enterprise versão 1903 ou posterior](#install-windows-10-pro-or-enterprise)                                        | Use a unidade **BOOTME** para instalar o **Windows 10 pro ou Enterprise** versão 1903 ou posterior.                                                                                                                                                                                                                                                                                 |
| 08 | [Instalar drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2](#install-surface-hub-2-drivers-and-firmware)                                        | Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale [drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. Arquivo MSI](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                  |
| 222 | [Configurar completamente o Surface Hub 2S como um dispositivo de produtividade pessoal](#next-steps)                                        |  Habilite o conjunto de aplicativos e configurações recomendadas para otimizar o uso do Surface Hub 2S como um dispositivo de produtividade pessoal.                                                                                                                                                                                                                                                                    |

### Verifique se a versão UEFI no Surface Hub 2S atende aos requisitos mínimos

A versão UEFI mínima exigida antes da migração do Surface Hub da equipe do Windows 10 para a área de trabalho do Windows 10 é **694.2938.768.0**.
 
**Para verificar a versão UEFI atual em seu sistema:**

1. Na tela inicial do Surface Hub 2s, selecione **Iniciar** e abra a **SurfaceApp** (toda a superfície de**aplicativos**  >  **Surface**).

2. Selecione **sua superfície** para exibir informações sobre o Surface Hub, incluindo a versão atual do UEFI no dispositivo. Se a versão UEFI for **694.2938.768.0** ou posterior, conforme mostrado abaixo, a UEFI estará qualificada para que você crie o pacote Semm para habilitar a migração do sistema operacional.

    ![Abrir o aplicativo Surface & selecionar sua superfície](images/shm-fig1.png)
 
3. Se a versão UEFI for anterior à versão **694.2938.768.0**, será necessário obter uma versão atual usando o Windows Update.

**Para atualizar a UEFI a partir do Windows Update:**

1. No Surface Hub 2s, entre como **administrador**, vá para todas as configurações de **aplicativos**  >  **Settings** >  **atualização e segurança**  >  do**Windows Update** e instale todas as atualizações e, em seguida, reinicie o dispositivo. Verifique a versão UEFI usando o aplicativo Surface. Observação: se você não souber seu nome de usuário ou senha de administrador, será necessário redefinir o dispositivo. Para saber mais, consulte [redefinir e recuperar para Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

2. Repita essas etapas até que a versão de UEFI seja **694.2938.768.0** ou posterior.

3. Se você ainda não vir o UEFI atualizado após várias tentativas, verifique o **histórico de atualização** e procure por quaisquer instâncias de instalações de firmware com falha. Talvez seja necessário redefinir o dispositivo (atualização de**configurações**  >  **&**  >  **dispositivo de redefinição**de segurança).

### Baixar os drivers e o firmware da Surface configuradora do Surface Hub 2

Em um computador separado:

- Baixe o Microsoft [Surface UEFI configurate](https://www.microsoft.com/download/details.aspx?id=46703) de ferramentas Surface para ele. O configurador UEFI de Surface não pode ser executado no Surface Hub 2S, enquanto a equipe do Windows 10 está instalada.

- Baixe [drivers Surface Hub 2 e firmware Windows Installer. Arquivo MSI](https://www.microsoft.com/download/details.aspx?id=101974) a ser aplicado ao instalar o novo sistema operacional.

### Preparar certificado SEMM

Se esta for a primeira vez que você usa o configurador UEFI da Surface, você precisará preparar um certificado. Esse certificado garante que depois que um dispositivo é registrado no SEMM, somente pacotes criados com o certificado aprovado podem ser usados para modificar as configurações de UEFI. A forma como você adquire um certificado pode variar dependendo do tamanho ou da complexidade da sua organização:

- Geralmente, grandes organizações corporativas mantêm sua própria infraestrutura de certificado para gerar certificados por práticas de segurança padrão.

- Empresas de médio porte e outras pessoas podem optar por obter um certificado de provedores de terceiros. Esta é a opção recomendada para organizações sem conhecimento de ti suficiente ou equipe de segurança de ti dedicada.

- Você também pode gerar um certificado autoassinado com um script do PowerShell, de acordo com a documentação a seguir: [requisitos de certificado do modo de gerenciamento empresarial Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). Ou use o PowerShell para criar seu próprio certificado por meio da seguinte documentação: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).

O pacote SEMM criado usando a ferramenta do Configurador UEFI do Surface deve ser protegido com um certificado para verificar a assinatura de arquivos de configuração antes que as configurações de UEFI possam ser aplicadas. Para saber mais, consulte documentação do [modo de gerenciamento da empresa Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode) .
 
 
### Criar pacote SEMM

1. Instale a ferramenta de **configurador UEFI do Surface** baixada anteriormente para um computador separado. 
2. Abra o **configurador UEFI da superfície** e selecione **Iniciar**.

   ![Configurador UEFI do Open Surface](images/shm-fig2.png)
   
3. Selecione **Surface Devices** e, em seguida, selecione **Avançar**.

   ![Selecionar dispositivos de superfície](images/shm-fig3.png)
  
4. Selecione **pacote de configuração**.

   ![Selecionar pacote de configuração](images/shm-fig4.png)
  
5. Selecione **proteção de certificado**.

   ![Selecionar proteção de certificado](images/shm-fig5.png)

6. Você será solicitado a adicionar seu arquivo. pfx de certificado.

   ![Você será solicitado a adicionar seu certificado](images/shm-fig6.png)
   
7. Digite sua **senha de certificado** e selecione **OK**.

   ![Digite sua senha de certificado e selecione OK](images/shm-fig7.png)

8. Selecione **proteção por senha** para adicionar uma senha à UEFI da superfície. Esta senha será necessária sempre que você inicializar o UEFI. É **altamente recomendável** definir uma senha UEFI que será usada no Surface Hub 2s.

   ![Clique em proteção por senha](images/shm-fig8.png)
   
9. Defina uma **senha UEFI** e selecione **OK**.

 > [!IMPORTANT]
   > Salve a senha em um local seguro acessível para administradores de ti em sua organização responsável por gerenciar hubs de superfície. Se a senha for perdida, não haverá processo de recuperação. 

   ![Digite sua senha UEFI](images/shm-fig9.png)

10. Selecione **Surface Hub 2s** e, em seguida, selecione **Avançar**.

   ![Selecionar Surface Hub 2S](images/shm-fig10.png)
   
11. Selecione **Avançar**.

    ![Selecione Avançar](images/shm-fig10a.png)

12. Para permitir a instalação do Windows 10 pro ou Enterprise, selecione **EnableOsMigration.**

    ![Selecione habilitar a migração do sistema operacional](images/shm-fig11.png)
    
13. Defina **EnableOSMigration** como **ativado** e selecione **Avançar**.

    ![Definir habilitar migração do sistema operacional como ativado](images/shm-fig12.png)

> [!NOTE]
> Depois de aplicar um pacote SEMM, todas as configurações de UEFI serão exibidas como acinzentadas (bloqueadas) no menu UEFI do dispositivo. Isso inclui valores padrão para outras configurações, como IPv6 para inicialização PXE. Para modificar as configurações de UEFI, você precisará aplicar outro pacote SEMM ou cancelar o registro do dispositivo do SEMM.

#### Salvar pacote SEMM na unidade USB

1. Conecte uma unidade USB ao seu computador. Escolha **Hub 2s** e, em seguida, selecione **Avançar**.

   ![Selecionar USB](images/shm-fig13.png)
   
2. Selecione **Compilar**.

   ![Selecione criar](images/shm-fig14.png)

3. Capture uma captura de tela desta página e selecione **terminar**. Seu pacote SEMM agora está pronto e contém o pacote SEMM **DfciUpdate. DFI** e um arquivo de texto com a impressão digital Semm (os dois últimos caracteres da impressão digital do certificado).

   ![Selecione encerrar](images/shm-fig15.png)
   
4. Salve os últimos 2 caracteres da impressão digital do certificado, o que é necessário para ativar o SEMM ao aplicar o pacote no Surface Hub 2S.

### Preparar a unidade flash USB contendo a imagem do Windows 10, o pacote SEMM e os drivers e o firmware do Surface Hub 2

Você pode instalar uma imagem do Windows 10 pro ou Enterprise (versão 1903 ou posterior) usando uma das seguintes opções:

- Sua solução atual para imagens.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) permite que você crie uma imagem inicializável do Windows 10, que pode incluir todas as atualizações atuais do Windows 10, o Office, outros aplicativos de sua escolha, bem como os drivers e o firmware obrigatórios. 

- Unidade flash USB com o Windows 10 pro ou a imagem empresarial, seguida  [da instalação de drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
Este procedimento descreve como criar uma unidade flash USB da mídia de instalação e adicionar os arquivos de pacote SEMM e drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2. Arquivo MSI. Se você estiver usando outros métodos de implantação, vá para a seção a seguir: [atualizar a UEFI no Surface Hub 2s para habilitar a migração do sistema operacional](#update-uefi-on-surface-hub-2s-to-enable-os-migration).

> [!NOTE]
> Uma vez instalado, você precisará de uma licença válida para o Windows 10 pro ou o Windows 10 Enterprise.

1. Para criar uma instalação do Windows 10 pro, siga as instruções na página [baixar o Windows 10](https://www.microsoft.com/software-download/windows10) para usar a ferramenta de **criação de mídia** . Para baixar o Windows 10 Enterprise, vá para o [centro de serviços de licenciamento por volume da Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

2. Insira uma nova unidade de **armazenamento USB** . Inicie a ferramenta de **criação de mídia** , selecione **criar mídia de instalação** e, em seguida, selecione **Avançar**.

   ![Criar mídia de instalação](images/shm-fig16.png)
   
3. Selecione idioma, Windows 10 e 64 bits (x64) e, em seguida, selecione **Avançar**.

   ![Selecione o idioma, o Windows 10 e o 64 bits & Selecione Avançar](images/shm-fig17.png)
   
4. Selecione **unidade flash USB** e selecione **Avançar**.

   ![Selecione unidade flash USB e selecione avançar](images/shm-fig18.png)
   
5. Quando o download for concluído, selecione **concluir**.

   ![Selecionar concluir](images/shm-fig19.png)
   
6. Copie os arquivos de pacote SEMM e drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2 (. MSI file) para a raiz da unidade flash USB (**BOOTME**) que contém a imagem do Windows 10. A unidade USB BOOTME contém:

    - Sua imagem inicializável do Windows 10
    - Arquivos de pacote SEMM (copiados para a raiz da unidade USB)
        - DfciUpdate. DFI
        - Arquivo de texto com a impressão digital SEMM. (Neste exemplo: SurfaceUEFI_2020Aug25_1058.txt. O carimbo de data/hora de geração automática corresponde à data em que você criou o arquivo usando o configurador UEFI da Surface.)
    - Drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)

### Atualize a UEFI no Surface Hub 2S para habilitar a migração do sistema operacional

1. Insira sua unidade **BOOTME** na porta USB-a no Surface Hub 2s.

2. Para inicializar o UEFI:

   1. Primeira desligamento (desligar) seu Surface Hub 2S.
   1. Pressione e mantenha pressionado o **volume +** e, em seguida, pressione e libere o botão de **energia** .
   1. Mantenha a retenção do **volume +** até que o menu UEFI seja exibido.
   
      ![Mantenha a retenção do volume + até que o menu UEFI seja exibido](images/shm-fig20.png)
      
3. Quando o dispositivo for reiniciado, insira a senha UEFI que você criou anteriormente, se aplicável (altamente recomendado).

   ![Quando o dispositivo for reiniciado, insira seu paassword UEFI](images/shm-fig22.png)
   
4. No menu UEFI, selecione **Management**  >  **instalação de gerenciamento do USB**.

   ![Selecionar gerenciamento & instalar a partir do USB](images/shm-fig21.png)
   
5. Selecione **reiniciar agora**, como mostrado a seguir. O dispositivo será reiniciado e exibirá o logotipo branco de 4 quadrados no meio da tela e ele será desligado.

   ![Selecione reiniciar agora](images/shm-fig25.png)
   
6. Pressione e solte o botão de energia, uma tela vermelha será exibida solicitando que você ative o modo de gerenciamento do Surface Enterprise. 

7. Insira sua **impressão digital**de dois caracteres, sua **senha de configurações de UEFI** e selecione **OK**.

   ![Digite a impressão digital do certificado de 2 caracteres](images/shm-fig23.png)
 
   > [!NOTE]
   > Depois de ativar o SEMM em seu dispositivo, a nova configuração de **EnableOSMigration** de UEFI será aplicada. Você não poderá mais acessar a equipe do Windows 10 e deve passar para a próxima etapa e instalar o Windows 10 pro ou o Windows 10 Enterprise. 

8. O dispositivo será reinicializado, exibirá o logotipo branco de quatro quadrados no meio da tela e, em seguida, novamente será desligado

### Instalar o Windows 10 pro ou Enterprise

1. Se a unidade Windows 10 pro ou Enterprise inicializável ainda não estiver na porta do Surface Hub 2 USB-A, insira-a agora e, em seguida, pressione e libere o botão de energia.

2. O dispositivo será iniciado, você verá o branco 4 quadrado no meio da tela e verá um círculo girando abaixo do logotipo branco de quatro quadrados.

3. Se o dispositivo não inicializar automaticamente na unidade USB, desligue o dispositivo (desconecte o cabo de alimentação e conecte-o novamente). Após conectar o cabo de alimentação novamente, o dispositivo deve ser inicializado após alguns segundos para o logotipo branco de 4 quadrados no meio da tela, ou você pode pressionar e liberar o botão de energia para ligar o dispositivo novamente. Logo após ver o logotipo de quatro quadrados no meio da tela, pressione e mantenha pressionado o botão para baixo volume até ver o círculo girando abaixo do logotipo branco de quatro quadrados.
 
   ![Inicializar no Windows 10 a partir do USB](images/shm-fig26.png)
   
4. Quando a instalação do OOBE (configuração inicial da caixa) for iniciada, siga as instruções para instalar o Windows 10 pro ou Enterprise (versão 1903 ou posterior).

### Instalar drivers e firmware do Surface Hub 2

 - Para garantir que seu dispositivo tenha todas as atualizações e drivers mais recentes, instale [drivers e firmware para Windows 10 pro e Enterprise no Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
### Próximas etapas

Para configurar completamente o Surface Hub 2S como um dispositivo de produtividade pessoal, consulte [Configurar o Windows 10 pro ou Enterprise no Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Se seguir as etapas descritas neste documento não tiver êxito em migrar seu dispositivo para o Windows 10 pro ou Enterprise para Surface Hub 2, entre em contato com o [suporte do Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

### Retornando à equipe do Windows 10

Se você quiser restaurar seu dispositivo para a equipe do Windows 10, consulte [redefinir e recuperar para Surface Hub 2s](surface-hub-2s-recover-reset.md)

## Histórico de versões

| Versão | Data               | Descrição                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| m. 1,2  | 29 de setembro de 2020 | Atualizações diversas por feedback de usabilidade.                                                        |
| m. 1,1  | 15 de setembro de 2020 | Anotação adicional inserida nos requisitos de licenciamento da introdução para instalar um novo sistema operacional. |
| m. 1.0  | 1 de setembro de 2020  | Novo artigo.                                                                                           |
