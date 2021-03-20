---
title: Surface Enterprise Management Mode (Surface)
description: Veja como esse recurso de dispositivos Surface com UEFI do Surface ajuda você a proteger e gerenciar configurações de firmware em sua organização.
keywords: uefi, configure, firmware, secure, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 03/18/2021
ms.openlocfilehash: 011f4d0270c47b976e10dbece2adb70559222b79
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442179"
---
# <a name="microsoft-surface-enterprise-management-mode"></a>Modo de Gerenciamento do Microsoft Surface Enterprise

O Microsoft Surface Enterprise Management Mode (SEMM) é um recurso de dispositivos Surface com UEFI surface que permite proteger e gerenciar configurações de firmware em sua organização. Com o SEMM, os profissionais de TI podem preparar as configurações das configurações da UEFI e instalá-las em um dispositivo Surface. Além da capacidade de configurar configurações uefi, o SEMM também usa um certificado para proteger a configuração contra violações ou remoção não autorizadas. O SEMM é um requisito para poder migrar um Surface Hub 2S para o Windows 10 Pro e Enterprise.

>[!NOTE]
>O SEMM só está disponível em dispositivos com firmware UEFI surface. Isso inclui a maioria dos dispositivos Surface, incluindo Surface Pro 7+, Surface Pro 7, Surface Pro X, Surface Hub 2S, SKUs comerciais do Surface Laptop 3 com um processador Intel e Surface Laptop Go. SEMM não tem suporte no SKU do Surface Laptop 3 de 15" com processador AMD (disponível apenas como SKU de varejo). 

Quando os dispositivos Surface são configurados pelo SEMM e protegidos com o certificado SEMM, eles são *considerados inscritos* no SEMM. Quando o certificado SEMM é removido e o controle das configurações UEFI é retornado para o usuário do dispositivo, o dispositivo Surface é considerado *não-rollado* no SEMM.

Há duas opções administrativas que você pode usar para gerenciar o SEMM e registrar dispositivos Surface – uma ferramenta autônoma ou integração com o Microsoft Endpoint Configuration Manager. A ferramenta autônoma SEMM, chamada de Configurador UEFI do Microsoft Surface, é descrita neste artigo. Para obter mais informações sobre como gerenciar o SEMM com o Microsoft Endpoint Configuration Manager, consulte [Use Microsoft Endpoint Configuration Manager para gerenciar](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)dispositivos com SEMM .

> [!NOTE]
> O SEMM tem suporte apenas no Surface Pro X por meio do GERENCIADOR UEFI. Você pode baixar o GERENCIADOR UEFI do [Surface Tools para TI.](https://www.microsoft.com/download/details.aspx?id=46703) Para obter mais informações, consulte [Deploying, managing, and sering Surface Pro X](surface-pro-arm-app-management.md).


## <a name="microsoft-surface-uefi-configurator"></a>Configurador UEFI do Microsoft Surface

O espaço de trabalho principal do SEMM é o Configurador UEFI do Microsoft Surface, conforme mostrado na Figura 1. O Microsoft Surface UEFI Configurator é uma ferramenta usada para criar pacotes do Windows Installer (.msi) ou imagens winpe usadas para registrar, configurar e desempacodar o SEMM em um dispositivo Surface. Esses pacotes contêm um arquivo de configuração onde as configurações para UEFI são especificadas. Os pacotes SEMM também contêm um certificado, que é instalado e armazenado no firmware e usado para verificar a assinatura de arquivos de configuração antes que as configurações da UEFI sejam aplicadas.

>[!TIP]
>Agora você pode usar o Surface UEFI Configurator e o SEMM para gerenciar portas no Surface Dock 2. Para saber mais, confira [Portas seguras do Surface Dock 2 com SEMM](secure-surface-dock-ports-semm.md).

![Configurador UEFI do Microsoft Surface](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Figura 1. Configurador UEFI do Microsoft Surface*


Você pode usar a ferramenta Configurador UEFI do Microsoft Surface em três modos:

* [Pacote de Configuração UEFI do Surface](#configuration-package). Use esse modo para criar um pacote de configuração uefi do Surface para registrar um dispositivo Surface no SEMM e para configurar as configurações uefi em dispositivos inscritos.
* [Pacote de redefinição uefi surface](#reset-package). Use esse modo para desemrollar um dispositivo Surface do SEMM.
* [Solicitação de Recuperação UEFI do Surface](#recovery-request). Use esse modo para responder a uma solicitação de recuperação para desemrollar um dispositivo Surface do SEMM em que uma operação do Pacote de Redefinição não é bem-sucedida.


#### <a name="download-microsoft-surface-uefi-configurator"></a>Baixar o Configurador UEFI do Microsoft Surface

Você pode baixar o Configurador UEFI do Microsoft Surface na página [Ferramentas do Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) no Centro de Download da Microsoft.

### <a name="configuration-package"></a>Pacote de configuração

Os pacotes de configuração uefi do Surface são o mecanismo principal para implementar e gerenciar o SEMM em dispositivos Surface. Esses pacotes contêm um arquivo de configuração de configurações UEFI especificado durante a criação do pacote no Microsoft Surface UEFI Configurator e um arquivo de certificado, conforme mostrado na Figura 2. Quando um pacote de configuração é executado pela primeira vez em um dispositivo Surface que ainda não está inscrito no SEMM, ele provisiona o arquivo de certificado no firmware do dispositivo e registra o dispositivo no SEMM. Ao registrar um dispositivo no SEMM, você será solicitado a confirmar a operação fornecendo os dois últimos dígitos da impressão digital do certificado SEMM antes que o arquivo de certificado seja armazenado e o registro possa ser concluído. Essa confirmação exige que um usuário seja fisicamente presente no dispositivo no momento do registro para executar a confirmação.

![Proteger um pacote de configuração do SEMM com um certificado](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Figura 2. Proteger um pacote de configuração do SEMM com um certificado*

Consulte a [seção Requisitos de](#surface-enterprise-management-mode-certificate-requirements) certificado do Modo de Gerenciamento do Surface Enterprise deste artigo para obter mais informações sobre os requisitos para o certificado SEMM.

>[!TIP]
>Você também pode especificar uma senha UEFI com SEMM necessária **** para exibir as páginas **Segurança,** Dispositivos, **** Configuração de Inicialização ou Gerenciamento **empresarial** do Surface UEFI.

Depois que um dispositivo é inscrito no SEMM, o arquivo de configuração é lido e as configurações especificadas no arquivo são aplicadas à UEFI. Quando você executar um pacote de configuração em um dispositivo que já está inscrito no SEMM, a assinatura do arquivo de configuração é verificada em relação ao certificado armazenado no firmware do dispositivo. Se a assinatura não corresponder, nenhuma alteração será aplicada ao dispositivo.

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>Habilitar ou desabilitar dispositivos no Surface UEFI com SEMM

A lista a seguir mostra todos os dispositivos disponíveis que você pode gerenciar no SEMM:

* Porta USB de encaixe
* Áudio a bordo
* DGPU
* Capa Teclado
* Cartão Micro SD
* Câmera Frontal
* Câmera Traseira
* Câmera infravermelha, para Windows Hello
* Bluetooth Somente
* Wi-Fi e Bluetooth
*              LTE           

 >[!NOTE]
>Os dispositivos integrados que aparecem na página Dispositivos UEFI podem variar dependendo do seu dispositivo ou ambiente corporativo. Por exemplo, a página Dispositivos UEFI não tem suporte no Surface Pro X; O LTE só aparece em dispositivos equipados com LTE. 
### <a name="configure-advanced-settings-with-semm"></a>Configurar configurações avançadas com SEMM
**Tabela 1. Configurações avançadas**

| Configuração                            | Descrição                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Inicialização de IPv6 para PXE                  | Permite gerenciar o suporte IPv6 para inicialização PXE. Se você não configurar essa configuração, o suporte IPv6 para inicialização PXE será desabilitado.                                                                               |
| Inicialização alternativa                     | Permite gerenciar o uso de uma ordem de inicialização alternativa para inicializar diretamente em um dispositivo USB ou Ethernet pressionando o botão Volume Para Baixo e o botão Desligar durante a inicialização. Se você não configurar essa configuração, a inicialização alternativa será habilitada. |
| Bloqueio da ordem de inicialização                    | Permite bloquear a ordem de inicialização para evitar alterações. Se você não configurar essa configuração, o Bloqueio de Ordem de Inicialização será desabilitado.                                                                                                        |
| Inicialização USB                           | Permite gerenciar a inicialização em dispositivos USB. Se você não configurar essa configuração, a Inicialização USB será habilitada.                                                                                                                 |
| Pilha de rede                      | Permite que você gerencie as configurações de inicialização de Pilha de Rede. Se você não definir essa configuração, a capacidade de gerenciar as configurações de inicialização de Pilha de Rede será desabilitada.                                                                                                           |
| Energia automática                      | Permite que você gerencie as configurações de inicialização do Auto Power On. Se você não configurar essa configuração, o Auto Power on será habilitado.                                                                                                        |
| SMT (Multi-Threading Simultâneo) | Permite gerenciar o SMT (Multi-Threading Simultâneo) para habilitar ou desabilitar o hiperthreading. Se você não configurar essa configuração, a SMT será habilitada.                                                  |
|Habilitar limite de bateria| Permite gerenciar a funcionalidade de limite de bateria. Se você não configurar essa configuração, o limite de bateria será habilitado |
| Security                           | Exibe a página Segurança uefi **do** Surface. Se você não configurar essa configuração, a página Segurança será exibida.                                                                                                                 |
| Dispositivos                            | Exibe a página Dispositivos UEFI **surface.** Se você não configurar essa configuração, a página Dispositivos será exibida.                                                                                                                     |
| Iniciar                               | Exibe a página Inicialização uefi **do** Surface. Se você não configurar essa configuração, a página Inicialização será exibida.                                                                                                                                                            |
| DateTime                           | Exibe a página Surface UEFI **DateTime.** Se você não configurar essa configuração, a página DateTime será exibida.                                                                                                                |
| EnableOSMigration                          | Permite migrar o Surface Hub 2 da Equipe do Windows 10 para o Windows 10 Pro ou Enterprise. Se você não configurar essa configuração, os dispositivos do Surface Hub 2 só poderão executar o sistema operacional de equipe do Windows 10.   Observação: a inicialização dupla entre a Equipe do Windows 10 e o Windows 10 Pro/Enterprise não está disponível no Surface Hub 2.                                                                                                           |


>[!NOTE]
>Quando você cria um pacote de configuração **** SEMM, dois caracteres são mostrados na página Bem-sucedido, conforme mostrado na Figura 3.

![Exibição de impressão digital de certificado](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Figura 3. Exibição dos dois últimos caracteres da impressão digital do certificado na página Bem-sucedida*

Esses caracteres são os dois últimos caracteres da impressão digital do certificado e devem ser gravados ou gravados. Os caracteres são necessários para confirmar o registro no SEMM em um dispositivo Surface, conforme mostrado na Figura 4.

![Confirmação de registro no SEMM](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Figura 4. Confirmação de registro no SEMM com a impressão digital do certificado SEMM*

>[!NOTE]
>Os administradores com acesso ao arquivo de certificado (.pfx) podem ler a impressão digital a qualquer momento abrindo o arquivo .pfx no CertMgr. Para exibir a impressão digital com CertMgr: 
>1. Clique com o botão direito do mouse no arquivo .pfx e clique em **Abrir**.
>2. Expanda a pasta no painel de navegação.
>3. Clique em **Certificados**.
>4. Clique com o botão direito do mouse no certificado no painel principal e clique em **Abrir**.
>5. Clique na **guia Detalhes.**
>6. **Todas** ou **Propriedades Somente** devem ser selecionadas **no** menu suspenso Mostrar.
>7. Selecione o campo **Impressão Digital**.

Para registrar um dispositivo Surface no SEMM ou para aplicar a configuração UEFI de um pacote de configuração, basta executar o arquivo .msi com privilégios administrativos no dispositivo Surface pretendido. Você pode usar tecnologias de implantação de aplicativos ou implantação do sistema operacional, como [o Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) ou o Microsoft Deployment [Toolkit](https://technet.microsoft.com/windows/dn475741). Ao registrar um dispositivo no SEMM, você deve estar fisicamente presente para confirmar o registro no dispositivo. A interação do usuário não é necessária quando você aplica uma configuração a dispositivos que já estão inscritos no SEMM.

Para um passo a passo sobre como registrar um dispositivo Surface no SEMM ou aplicar uma configuração uefi surface com SEMM, consulte Registrar e configurar dispositivos Surface com [SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).

### <a name="reset-package"></a>Redefinir o pacote

Um pacote de redefinição uefi do Surface é usado para executar apenas uma tarefa — para desempacotar um dispositivo Surface do SEMM. O pacote de redefinição contém instruções assinadas para remover o certificado SEMM do firmware do dispositivo e redefinir as configurações uefi como padrão de fábrica. Como um pacote de configuração UEFI do Surface, um pacote de redefinição deve ser assinado com o mesmo certificado SEMM provisionado no dispositivo Surface. Quando você cria um pacote de redefinição do SEMM, é necessário fornecer o número de série do dispositivo Surface que você pretende redefinir. Os pacotes de redefinição do SEMM não são universais e são específicos de um dispositivo.

### <a name="recovery-request"></a>Solicitação de recuperação

Em alguns cenários, pode ser impossível usar um pacote de redefinição uefi do Surface. (Por exemplo, se o Windows se tornar inutilizável no dispositivo Surface.) Nesses cenários, você pode desempacodar **** o dispositivo Surface do SEMM por meio da página Gerenciamento Empresarial do Surface UEFI (mostrado na Figura 5) com uma operação de Solicitação de Recuperação.

> [!div class="mx-imgBorder"]
> ![Iniciar uma solicitação de recuperação semm](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Figura 5. Iniciar uma solicitação de recuperação semm na página Gerenciamento empresarial*

Quando você usa o processo na página **Gerenciamento empresarial** para redefinir o SEMM em um dispositivo Surface, você é fornecido com uma Solicitação de Redefinição. Essa Solicitação de Redefinição pode ser salva como um arquivo em uma unidade USB, copiada como texto ou lida como um código QR com um dispositivo móvel para ser facilmente enviada por email ou mensagem. Use a opção Solicitação de Redefinição do Configurador UEFI do Microsoft Surface para carregar um arquivo de Solicitação de Redefinição ou inserir o texto de Solicitação de Redefinição ou Código QR. O Microsoft Surface UEFI Configurator gerará um código de verificação que pode ser inserido no dispositivo Surface. Se você inserir o código no dispositivo Surface e clicar em **Reiniciar**, o dispositivo será desemrollado do SEMM. 

>[!NOTE]
>Uma Solicitação de Redefinição expira duas horas após a criação.

Para um passo a passo passo sobre como desemincar dispositivos Surface do [SEMM, consulte Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Requisitos de certificado do Modo de Gerenciamento do Surface Enterprise
O uso do SEMM com o Configurador UEFI do Microsoft Surface requer um certificado para verificar a assinatura de arquivos de configuração antes que as configurações da UEFI possam ser aplicadas. Esse certificado garante que, depois que um dispositivo é inscrito no SEMM, somente pacotes criados com o certificado aprovado podem ser usados para modificar as configurações da UEFI.

>[!NOTE]
>O certificado SEMM é necessário para executar qualquer modificação nas configurações de SEMM ou UEFI do Surface em dispositivos Surface inscritos. Se o certificado SEMM estiver corrompido ou perdido, o SEMM não poderá ser removido ou redefinido. Gerencie seu certificado SEMM adequadamente com uma solução apropriada para backup e recuperação.

Os pacotes criados com a ferramenta Configurador UEFI do Microsoft Surface são assinados com um certificado. Esse certificado garante que, depois que um dispositivo é inscrito no SEMM, somente pacotes criados com o certificado aprovado podem ser usados para modificar as configurações da UEFI. 
### <a name="recommended-certificate-settings"></a>Configurações de certificado recomendadas
As configurações a seguir são recomendadas para o certificado SEMM:

* **Algoritmo chave** – RSA 
* **Comprimento da chave** – 2048
* **Algoritmo de hash** – SHA-256
* **Tipo** – Autenticação do servidor SSL
* **Uso de Chave** – Assinatura digital, Chave Encipherment
* **Provedor** – Provedor criptográfico rsa aprimorado da Microsoft e do AES
* **Data de expiração** – 15 meses após a criação do certificado
* **Política de Exportação de Chave** – Exportável

Também é recomendável que o certificado SEMM seja autenticado em uma arquitetura PKI (infraestrutura de chave pública de duas camadas) na qual a autoridade de certificação intermediária (CA) é dedicada ao SEMM, habilitando a revogação do certificado. Para obter mais informações sobre uma configuração PKI de duas camadas, consulte [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).

### <a name="self-signed-certificate"></a>Certificado auto-assinado 
Você pode usar o seguinte exemplo de script do PowerShell para criar um certificado auto-assinado para uso em cenários de prova de conceito.
Para usar esse script, copie o texto a seguir no Bloco de Notas e salve o arquivo como um script do PowerShell (.ps1). 

> [!NOTE]
> Este script cria um certificado com uma senha de `12345678` . O certificado gerado por esse script não é recomendado para ambientes de produção.
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
>Para uso com o SEMM e o Microsoft Surface UEFI Configurator, o certificado deve ser exportado com a chave privada e com a proteção de senha. O Microsoft Surface UEFI Configurator solicitará que você selecione o arquivo de certificado SEMM (.pfx) e a senha do certificado quando necessário.

1.  Crie uma pasta em sua unidade C: onde você salvará o script; por exemplo, C:\SEMM.
2.  Copie o script de exemplo no Bloco de Notas ou editor de texto equivalente e salve o arquivo como um script do PowerShell (.ps1).
3.  Entre no computador com credenciais de administrador e abra uma sessão do PowerShell com privilégios elevados.
4.  Verifique se suas permissões estão definidas para permitir que scripts sejam executados. Por padrão, os scripts são bloqueados de execução, a menos que você modifique a política de execução. Para saber mais, confira [Sobre Políticas de Execução.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)
5.  No prompt de comando, insira o caminho completo do script e pressione Enter. O script cria um Certificado de Demonstração chamado TempOwner.pfx.

Como alternativa, você pode criar seu próprio certificado auto-assinado usando o PowerShell. Para obter mais informações, consulte a seguinte documentação do PowerShell: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).




>[!NOTE]
>Para organizações que usam uma raiz offline em sua infraestrutura PKI, o Microsoft Surface UEFI Configurator deve ser executado em um ambiente conectado à CA raiz para autenticar o certificado SEMM. Os pacotes gerados pelo Configurador UEFI do Microsoft Surface podem ser transferidos como arquivos e, portanto, podem ser transferidos para fora do ambiente de rede offline com armazenamento removível, como um pen drive.

### <a name="managing-certificates-faq"></a>Gerenciar perguntas frequentes sobre certificados

O comprimento *mínimo recomendado* é de 15 meses. Você pode usar um certificado que expire em menos de 15 meses ou usar um certificado que expire em mais de 15 meses.

>[!NOTE] 
>Quando um certificado expira, ele não é renovado automaticamente. 


**Um certificado expirado afetará a funcionalidade dos dispositivos inscritos no SEMM?**<br><br>
Não, um certificado afeta apenas tarefas de gerenciamento de administradores de IT no SEMM e não afeta a funcionalidade do dispositivo quando expira.


**O pacote e o certificado SEMM precisarão ser atualizados em todos os máquinas que o possuem?**

Se você quiser que a redefinição ou a recuperação do SEMM funcionem, o certificado precisa ser válido e não expirado. 

**Os pacotes de redefinição em massa podem ser criados para cada superfície que encomendamos? Pode-se construir um que redefine todos os máquinas em nosso ambiente?**

Os exemplos do PowerShell que criam um pacote de configuração para um tipo de dispositivo específico também podem ser usados para criar um pacote de redefinição independente do número de série. Se o certificado ainda for válido, você poderá criar um pacote de redefinição usando o PowerShell para redefinir o SEMM.

## <a name="version-history"></a>Histórico de versão

### <a name="version-2791390"></a>Versão 2.79.139.0

Esta versão do SEMM inclui:
- Suporte para o Surface Pro 7+
- Melhorias na experiência do usuário


### <a name="version-2781390"></a>Versão 2.78.139.0

Esta versão do SEMM inclui:

- Suporte para Surface Laptop Go e Surface Pro X
- Notificações para a nova versão de versão
- Capacidade de criar pacotes personalizados para alterar a propriedade
- Correções de bugs

### <a name="version-2731360"></a>Versão 2.73.136.0

Esta versão do SEMM inclui:

- O áudio agora pode ser desabilitado no Surface Hub2S usando o SEMM
- Suporte ao Surface Pro X para Dock 2
- Suporte ao GERENTE UEFI para operações relacionadas ao Dock 2
- Correção de bugs do pacote de redefinição do Surface Go
- Suporte para migrar dispositivos Surface Hub 2 do Sistema Operacional de Equipe do Windows 10 para o Windows 10 Pro ou Enterprise.

### <a name="version-2711390"></a>Versão 2.71.139.0

Esta versão do SEMM adiciona suporte para recursos de gerenciamento do Surface Dock 2 para Surface Book 3, Surface Laptop 3 e Surface Pro 7, incluindo:

- Habilitando áudio (bloqueio/desbloqueio), portas Ethernet e USB
- Capacidade de criar pacotes de encaixe para hosts autenticados e não autenticados

### <a name="version-2701300"></a>Versão 2.70.130.0

Esta versão do SEMM inclui:

- Suporte para o Surface Go 2
- Suporte para o Surface Book 3
- Correções de bugs


### <a name="version-2591390"></a>Versão 2.59.139.0

* Suporte para modelos do Surface Pro 7, Surface Pro X e Surface Laptop 3 de 13,5" e 15" com processador Intel.

  > [!NOTE]
  > O processador AMD do Surface Laptop 3 15" não é suportado.

- Suporte para o recurso Wake on Power

### <a name="version-2541390"></a>Versão 2.54.139.0
* Suporte ao Surface Hub 2S
* Correções de bugs

### <a name="version-2431360"></a>Versão 2.43.136.0
* Suporte para habilitar/desabilitar multithreating simulado 
* Opções separadas para WiFi e Bluetooth para alguns dispositivos 
* Limite de bateria removido para o Surface Studio 

### <a name="version-2261360"></a>Versão 2.26.136.0
* Adicionar suporte ao Surface Studio 2
* Recurso Limite de Bateria

### <a name="version-2211360"></a>Versão 2.21.136.0
* Adicionar suporte ao Surface Pro 6
* Adicionar suporte ao Surface Laptop 2

### <a name="version-2141360"></a>Versão 2.14.136.0
* Adicionar suporte ao Surface Go

### <a name="version-291360"></a>Versão2.9.136.0
* Adicionar suporte ao Surface Book 2
* Adicionar suporte ao Surface Pro LTE
* Melhorias de acessibilidade

### <a name="version-10740"></a>Versão 1.0.74.0
* Adicionar suporte ao Surface Laptop
* Adicionar suporte ao Surface Pro
* Correções de bugs e melhoria geral

## <a name="related-topics"></a>Tópicos relacionados

- [Registrar e configurar dispositivos Surface com o SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Cancelar o registro de dispositivos Surface no SEMM](unenroll-surface-devices-from-semm.md)
- [Portas do Secure Surface Dock 2 com SEMM](secure-surface-dock-ports-semm.md)
