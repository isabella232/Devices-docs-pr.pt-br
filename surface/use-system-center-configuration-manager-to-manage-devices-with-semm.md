---
title: Usar o Microsoft Endpoint Configuration Manager para gerenciar dispositivos com SEMM
description: Saiba como gerenciar o Microsoft Surface Enterprise Modo de Gerenciamento (SEMM) com o Endpoint Configuration Manager.
keywords: registrar, atualizar, scripts, configurações
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 9f3db9428e188aa20399d26c066507d76c90ba57
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708782"
---
# <a name="use-microsoft-endpoint-configuration-manager-to-manage-devices-with-semm"></a>Usar o Microsoft Endpoint Configuration Manager para gerenciar dispositivos com SEMM

O recurso SEMM (Modo de Gerenciamento do Microsoft Surface Enterprise) de dispositivos UEFI surface permite que os administradores gerenciem e ajudem a proteger a configuração das configurações do Surface UEFI. Para a maioria das organizações, esse processo é realizado criando Windows pacotes do Instalador (.msi) com a ferramenta Configurador uefi do Microsoft Surface. Esses pacotes são executados ou implantados nos dispositivos Surface cliente para registrar os dispositivos no SEMM e para atualizar a configuração de configurações uefi do Surface.

Para organizações com Microsoft Endpoint Configuration Manager há uma alternativa ao uso do processo configurador UEFI do Microsoft Surface .msi para implantar e administrar o SEMM. O Microsoft Surface UEFI Manager é um instalador leve que disponibiliza os assemblies necessários para o gerenciamento de SEMM em um dispositivo. Ao instalar esses assemblies com o Microsoft Surface UEFI Manager em um cliente gerenciado, o SEMM pode ser administrado pelo Configuration Manager com scripts do PowerShell, implantados como aplicativos. Com esse processo, o gerenciamento de SEMM é realizado no Configuration Manager, o que elimina a necessidade da ferramenta configuradora uefi uefi externa do Microsoft Surface.

> [!Note]
> Embora o processo descrito neste artigo possa funcionar com versões anteriores do Endpoint Configuration Manager ou com outras soluções de gerenciamento de terceiros, o gerenciamento do SEMM com o Microsoft Surface UEFI Manager e o PowerShell é suportado apenas com o Branch Atual do Endpoint Configuration Manager.

#### <a name="prerequisites"></a>Pré-requisitos

Antes de começar o processo descrito neste artigo, familiarize-se com as seguintes tecnologias e ferramentas:

* [Surface UEFI](manage-surface-uefi-settings.md)
* [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md)
* [Scripts do PowerShell](/powershell)
* [Implantar aplicativos com o Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)


> [!Note]
> Você também precisará de acesso ao certificado que pretende usar para proteger o SEMM. Para obter detalhes sobre os requisitos para este certificado, consulte Surface Enterprise Requisitos de [certificado do Modo de Gerenciamento.](surface-enterprise-management-mode.md#surface-enterprise-management-mode-certificate-requirements)
> 
> É muito importante que esse certificado seja mantido em um local seguro e feito backup corretamente. Se esse certificado se tornar perdido ou inutilizável, não é possível redefinir a UEFI do Surface, alterar as configurações gerenciadas da UEFI do Surface ou remover o SEMM de um dispositivo Surface inscrito.

#### <a name="download-microsoft-surface-uefi-manager"></a>Baixar o Microsoft Surface UEFI Manager

O gerenciamento do SEMM com o Configuration Manager requer a instalação do Microsoft Surface UEFI Manager em cada dispositivo Surface cliente. Você pode baixar o Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) na página [Ferramentas do Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) no Centro de Download da Microsoft.

#### <a name="download-semm-scripts-for-configuration-manager"></a>Baixar scripts SEMM para o Configuration Manager

Depois que o Microsoft Surface UEFI Manager é instalado no dispositivo Surface cliente, o SEMM pode ser implantado e gerenciado com scripts do PowerShell. Obter exemplos de scripts de [gerenciamento de SEMM](https://www.microsoft.com/download/details.aspx?id=46703) baixando SEMM_PowerShell.zip do Surface Tools para IT.

## <a name="deploy-microsoft-surface-uefi-manager"></a>Implantar o Microsoft Surface UEFI Manager

A implantação do Microsoft Surface UEFI Manager é uma implantação de aplicativo típica. O arquivo do instalador do Microsoft Surface UEFI Manager é um arquivo Windows Instalador padrão que você pode instalar com a [opção de silencioso padrão](https://msdn.microsoft.com/library/windows/desktop/aa367988).

O comando para instalar o Microsoft Surface UEFI Manager é o seguinte.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

O comando para desinstalar o Microsoft Surface UEFI Manager é o seguinte.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

Para criar um novo aplicativo e implantá-lo em uma coleção que contém seus dispositivos Surface, execute as seguintes etapas:

1. Abra o Console do Gerenciador de Configurações na **tela inicial** ou **no** menu Iniciar.
2. Selecione **Biblioteca de** Software no canto inferior esquerdo da janela.
3. Expanda **o nó Gerenciamento de** Aplicativos da Biblioteca de Software e selecione **Aplicativos**.
4. Selecione o **botão Criar Aplicativo** na guia **Página** Inicial, na parte superior da janela. Isso inicia o Assistente para Criar Aplicativos.
5. O Assistente para Criar Aplicativo apresenta uma série de etapas:

   * **Geral** – A **opção Detectar automaticamente informações sobre esse aplicativo** a partir de arquivos de instalação é selecionada por padrão. No campo **Tipo,** **o Windows (arquivo .msi)** também é selecionado por padrão. Selecione **Procurar** para navegar até e ** selecioneSurfaceUEFIManagerSetup.msi**e, em seguida, selecione **Próximo**.
   
      > [!Note]
      > O local do SurfaceUEFIManagerSetup.msi deve estar em um compartilhamento de rede e localizado em uma pasta que não contém outros arquivos. Não é possível usar um local de arquivo local.

   * **Importar Informações** – o Assistente para Criar Aplicativo analisará o arquivo .msi e lerá o **Nome** do Aplicativo e o Código **do Produto.** SurfaceUEFIManagerSetup.msi deve ser listado como o único arquivo na linha **Arquivos de**Conteúdo , conforme mostrado na Figura 1. Selecione **Avançar** para continuar.

      ![As informações da instalação do Surface UEFI Manager são automaticamente analisados](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Figura 1. As informações da instalação do Microsoft Surface UEFI Manager são automaticamente analisados*

   * **Informações Gerais** – Você pode modificar o nome do aplicativo e informações sobre o editor e a versão ou adicionar comentários nesta página. O comando de instalação do Microsoft Surface UEFI Manager é exibido no campo Programa de Instalação. O comportamento de instalação padrão de Install for system permitirá que o Microsoft Surface UEFI Manager instale os assemblies necessários para SEMM, mesmo se um usuário não estiver conectado ao dispositivo Surface. Selecione **Avançar** para continuar.
   * **Resumo** – As informações que foram **** analisados na etapa Importar Informações e suas seleções da etapa **Informações** Gerais são exibidas nesta página. Selecione **Próximo** para confirmar suas seleções e crie o aplicativo.
   * **Progresso** – Exibe uma barra de progresso e status à medida que o aplicativo é importado e adicionado à Biblioteca de Software.
   * **Conclusão** – A confirmação da criação bem-sucedida do aplicativo é exibida quando o processo de criação do aplicativo é concluído. Selecione **Fechar** para concluir o Assistente para Criar Aplicativos.

Depois que o aplicativo for criado no Configuration Manager, você poderá distribuí-lo para seus pontos de distribuição e implantá-lo nas coleções, incluindo seus dispositivos Surface. Este aplicativo não instalará ou habilitará o SEMM no dispositivo Surface. Ele fornece apenas os assemblies necessários para que o SEMM seja habilitado usando o script do PowerShell.

Se você não quiser instalar os assemblies do Microsoft Surface UEFI Manager em dispositivos que não serão gerenciados com o SEMM, você pode configurar o Microsoft Surface UEFI Manager como uma dependência dos scripts do SEMM Configuration Manager. Este cenário é abordado na seção [Implantar Scripts](#deploy-semm-configuration-manager-scripts) do Gerenciador de Configuração SEMM posteriormente neste artigo.

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a>Criar ou modificar os scripts do Semm Configuration Manager

Depois que os assemblies necessários foram instalados nos dispositivos, o processo de registrar os dispositivos no SEMM e configurar o Surface UEFI é feito com scripts do PowerShell e implantado como um aplicativo de script com o Configuration Manager. Esses scripts podem ser modificados para se ajustar às necessidades de sua organização e ambiente. Por exemplo, você pode criar várias configurações para dispositivos Surface gerenciados em diferentes departamentos ou funções. Você pode baixar amostras dos scripts do SEMM e do Configuration Manager no link na seção [Pré-requisitos](#prerequisites) no início deste artigo.

Há dois scripts principais que você precisará para executar uma implantação semm com o Configuration Manager:

* **ConfigureSEMM.ps1** – Use esse script para criar pacotes de configuração para seus dispositivos Surface com as configurações uefi do Surface desejadas para aplicar as configurações especificadas a um dispositivo Surface, para registrar o dispositivo no SEMM e para definir uma chave do Registro usada para identificar o registro do dispositivo no SEMM.
* **ResetSEMM.ps1** – Use esse script para redefinir o SEMM em um dispositivo Surface, que o desempacora do SEMM e remove o controle sobre as configurações da UEFI do Surface.

Os scripts de exemplo incluem exemplos de como definir configurações uefi do Surface e como controlar permissões para essas configurações. Essas configurações podem ser modificadas para proteger a UEFI do Surface e definir as configurações uefi do Surface de acordo com as necessidades do seu ambiente. As seções a seguir deste artigo explicam o script ConfigureSEMM.ps1 e explorem as modificações que você precisa fazer no script para se ajustar aos seus requisitos.

> [!NOTE]
> Os scripts do SEMM Configuration Manager e o arquivo de certificado SEMM exportado (.pfx) devem ser colocados na mesma pasta sem outros arquivos antes de serem adicionados ao Configuration Manager.

### <a name="specify-certificate-and-package-names"></a>Especificar nomes de certificados e pacotes

A primeira região do script que você precisa modificar é a parte que especifica e carrega o certificado SEMM e também indica a versão SurfaceUEFIManager e os nomes do pacote de configuração SEMM e do pacote de redefinição do SEMM. O nome do certificado e a versão SurfaceUEFIManager são especificados nas linhas 56 a 73 no ConfigureSEMM.ps1 script.

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

Substitua o **valor FabrikamSEMMSample.pfx** pela variável **$certName** pelo nome do seu arquivo de Certificado SEMM na linha 58. O script criará um diretório de trabalho (chamado Config) na pasta onde seus scripts estão localizados e, em seguida, copia o arquivo de certificado para esse diretório de trabalho.

O pacote de proprietário e o pacote de redefinição também serão criados no diretório Config e manterão a configuração para as configurações e permissões uefi do Surface geradas pelo script.

Na linha 73, substitua o valor da variável **$password,** de **1234** para a senha do arquivo de certificado. Se uma senha não for necessária, exclua o **texto 1234.**

> [!Note]
> Os dois últimos caracteres da impressão digital do certificado são necessários para registrar um dispositivo no SEMM. Esse script exibirá esses dígitos para o usuário, o que permite que o usuário ou o técnico grave esses dígitos antes que o sistema seja reiniciado para registrar o dispositivo no SEMM. O script usa o código a seguir, encontrado nas linhas 150-155, para fazer isso.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Os administradores com acesso ao arquivo de certificado (.pfx) podem ler a impressão digital a qualquer momento abrindo o arquivo .pfx no CertMgr. Para exibir a impressão digital com CertMgr, siga este processo:

1. Clique com o botão direito do mouse no arquivo .pfx e selecione **Abrir**.
2. Expanda a pasta no painel de navegação.
3. Selecione **Certificados**.
4. Clique com o botão direito do mouse no certificado no painel principal e selecione **Abrir**.
5. Selecione a **guia Detalhes.**
6. **Todas** ou **Propriedades Somente** devem ser selecionadas **no** menu suspenso Mostrar.
7. Selecione o campo **Impressão Digital**.

> [!NOTE]
> O nome e a senha do certificado SEMM também devem ser inseridos nesta seção do script ResetSEMM.ps1 para habilitar o Configuration Manager a remover o SEMM do dispositivo com a ação de desinstalação.

### <a name="configure-permissions"></a>Configurar permissões

A primeira região do script em que você especificará a configuração do Surface UEFI é a **região Configurar Permissões.** Essa região começa na linha 210 no script de exemplo com o comentário **# Configurar Permissões** e continua até a linha 247. O fragmento de código a seguir primeiro define permissões para todas as configurações uefi do Surface para que elas possam ser modificadas apenas pelo SEMM e, em seguida, adiciona permissões explícitas para permitir que o usuário local modifique a senha uefi do Surface, o TPM e as câmeras frontal e traseira.

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

Cada **$uefiV 2** identifica uma configuração uefi do Surface por nome de configuração ou ID e configura as permissões para um dos seguintes valores:

* **$ownerOnly** – A permissão para modificar essa configuração é concedida somente ao SEMM.
* **$ownerAndLocalUser** – A permissão para modificar essa configuração é concedida a um usuário local que está inicializando no Surface UEFI, bem como ao SEMM.

Você pode encontrar informações sobre os nomes e as IDs de configurações disponíveis para a UEFI do Surface na seção Configurações Nomes e [IDs](#settings-names-and-ids) deste artigo.

### <a name="configure-settings"></a>Definir configurações

**A segunda** região do script onde você especificará a configuração do Surface UEFI é a região Configurar Configurações do script ConfigureSEMM.ps1, que configura se cada configuração está habilitada ou desabilitada. O script de exemplo inclui instruções para definir todas as configurações para seus valores padrão. Em seguida, o script fornece instruções explícitas para desabilitar iPv6 para Inicialização PXE e para deixar a senha do Administrador uefi do Surface inalterada. Você pode encontrar essa região começando com **o comentário # Configurar Configurações** linha 291 até a linha 335 no script de exemplo. A região aparece da seguinte forma.

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

Como as permissões definidas na seção **Configurar Permissões** do script, a configuração de cada configuração uefi do Surface é executada definindo a variável **$uefiV 2.** Para cada linha que define a **variável $uefiV 2,** uma configuração uefi do Surface é identificada por nome de configuração ou ID e o valor configurado é definido como **Habilitado** ou **Desabilitado.**

Se você não quiser alterar a configuração de uma configuração uefi do Surface, por exemplo, para garantir que a senha do administrador uefi do Surface não seja desfeita pela ação de redefinir todas as configurações uefi do Surface como padrão, você pode usar **ClearConfiguredValue()** para impor que essa configuração não será alterada. No script de exemplo, isso é usado na linha 323 para impedir a limpeza da senha do Administrador uefi do Surface, identificada no script de exemplo por sua ID de configuração, **501**.

Você pode encontrar informações sobre os nomes e as IDs de configurações disponíveis para a UEFI do Surface na seção Configurações Nomes e [IDs](#settings-names-and-ids) posteriormente neste artigo.

### <a name="settings-registry-key"></a>Configurações chave do Registro

Para identificar sistemas inscritos para o Configuration Manager, o script ConfigureSEMM.ps1 grava chaves do Registro que podem ser usadas para identificar sistemas inscritos como tendo sido instalados com o script de configuração semm. Essas chaves podem ser encontradas no local a seguir.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

O fragmento de código a seguir, encontrado nas linhas 380-477, é usado para gravar essas chaves do Registro.

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <a name="settings-names-and-ids"></a>Configurações nomes e IDs

Para configurar as configurações ou permissões uefi do Surface para configurações uefi do Surface, você deve consultar cada configuração por seu nome de configuração ou ID de configuração. A cada nova atualização do Surface UEFI, novas configurações podem ser adicionadas. Executar ShowSettingsOptions.ps1 script (SEMM_Powershell.zip no Surface [Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703))fornece detalhes das configurações disponíveis. O computador onde ShowSettingsOptions.ps1 é executado deve ter o Microsoft Surface UEFI Manager instalado, mas o script não exige um dispositivo Surface.


## <a name="deploy-semm-configuration-manager-scripts"></a>Implantar scripts do SEMM Configuration Manager

Depois que seus scripts estão preparados para configurar e habilitar o SEMM no dispositivo cliente, a próxima etapa é adicionar esses scripts como um aplicativo no Configuration Manager. Antes de abrir o Configuration Manager, verifique se os seguintes arquivos estão em uma pasta compartilhada que não inclui outros arquivos:

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* Seu certificado SEMM (por exemplo, SEMMCertificate.pfx)

Os scripts do SEMM Configuration Manager serão adicionados ao Configuration Manager como um aplicativo de script. O comando para instalar o SEMM com ConfigureSEMM.ps1 é o seguinte.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

O comando para desinstalar o SEMM com ResetSEMM.ps1 é o seguinte.

`Powershell.exe -file ".\ResetSEMM.ps1"`

Para adicionar os scripts do Semm Configuration Manager ao Configuration Manager como um aplicativo, use o seguinte processo:

1. Inicie o Assistente para Criar Aplicativos usando a Etapa 1 até a Etapa 5 da seção [Implantar o Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) anteriormente neste artigo.

2. Prossiga através do Assistente para Criar Aplicativos da seguinte forma:

   - **Geral** – Selecione **Especificar manualmente as informações do**aplicativo e selecione **Próximo**.

   - **Informações Gerais** – Insira um nome para o aplicativo (por exemplo, SEMM) e qualquer outra informação que você deseja, como editor, versão ou comentários nesta página. Selecione **Avançar** para continuar.

   - **Catálogo de** Aplicativos – Os campos nesta página podem ser deixados com seus valores padrão. Selecione **Avançar**.

   - **Tipos de** implantação – Selecione **Adicionar** para iniciar o Assistente criar tipo de implantação.

   - Prossiga pelas etapas do Assistente criar tipo de implantação, da seguinte forma:

     * **Geral** – Selecione **Instalador de Script** **no** menu suspenso Tipo. A **opção Especificar manualmente as informações do tipo de** implantação será selecionada automaticamente. Selecione **Avançar** para continuar.
     * **Informações Gerais** – insira um nome para o tipo de implantação (por exemplo, Scripts de Configuração SEMM) e selecione **Próximo** para continuar.
     * **Conteúdo** – Selecione **Procurar** ao lado do campo **Local** do Conteúdo e selecione a pasta onde os scripts do Gerenciador de Configurações do SEMM estão localizados. No campo **Programa de Instalação,** digite o comando [de instalação](#deploy-semm-configuration-manager-scripts) encontrado anteriormente neste artigo. No campo Programa de Desinstalação, insira o comando [de desinstalação](#deploy-semm-configuration-manager-scripts) encontrado anteriormente neste artigo (mostrado na Figura 2). **** Selecione **Avançar** para mover para a próxima página.
    
     ![Definir os scripts do SEMM Configuration Manager como os comandos de instalação e desinstalação](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Figura 2. Definir os scripts do SEMM Configuration Manager como os comandos de instalação e desinstalação*

     * **Método Detecção** – Selecione **Adicionar Cláusula** para adicionar a regra de detecção de chave de chave de registro do Gerenciador de Configuração do SEMM. A **janela Regra de** Detecção é exibida, conforme mostrado na Figura 3. Use as seguintes configurações:

       - Selecione **Registro no** menu suspenso **Tipo** de Configuração.
       - Selecione **HKEY_LOCAL_MACHINE** no menu suspenso **Hive.**
       - Insira **SOFTWARE\Microsoft\Surface\SEMM** no **campo** Chave.
       - Insira **CertName** no **campo** Valor.
       - Selecione **Cadeia de** caracteres no menu suspenso Tipo de Dados. ****
       - Selecione a **configuração Esta configuração do Registro deve atender à seguinte regra para indicar a presença deste botão de** aplicativo.
       - Insira o nome do certificado inserido na linha 58 do script no **campo Valor.**
       - Selecione **OK** para fechar a janela **Regra de** Detecção.

     ![Usar uma chave do Registro para identificar dispositivos inscritos no SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *Figura 3. Usar uma chave do Registro para identificar dispositivos inscritos no SEMM*

     * Selecione **Avançar** para prosseguir para a próxima página.
     
     * **Experiência do Usuário** – Selecione **Instalar para o sistema** no menu suspenso Comportamento **de** Instalação. Se você quiser que seus usuários gravem e insiram a impressão digital do certificado por conta própria, deixe o requisito de logon definido como **Somente quando**um usuário estiver conectado . Se você quiser que os administradores insiram a impressão digital para os usuários e os usuários não precisam ver **a** impressão digital, selecione Se um usuário está conectado ou não no menu suspenso Requisito de **Logon.**

     * **Requisitos** – o ConfigureSEMM.ps1 script verifica automaticamente se o dispositivo é um dispositivo Surface antes de tentar habilitar o SEMM. No entanto, se você pretende implantar esse aplicativo de script em uma coleção com dispositivos que não sejam gerenciados com SEMM, você pode adicionar requisitos aqui para garantir que esse aplicativo seja executado somente em dispositivos Surface ou dispositivos que você pretende gerenciar com o SEMM. Selecione **Próximo** para continuar.
     
     * **Dependências** – Selecione **Adicionar** para abrir a janela **Adicionar Dependência.**

       * Selecione **Adicionar** para abrir a **janela Especificar Aplicativo** Necessário.

          - Insira um nome para as dependências do SEMM no campo **Nome** do Grupo de Dependência (por exemplo, *Assemblies SEMM*).

          - Selecione **o Microsoft Surface UEFI Manager** na lista de Aplicativos Disponíveis e o tipo de implantação MSI e selecione **OK** para fechar **a** janela **Especificar Aplicativo** Necessário.
          
         *   Mantenha a **caixa** de seleção Instalação Automática selecionada se quiser que o Microsoft Surface UEFI Manager seja instalado automaticamente em dispositivos quando tentar habilitar o SEMM com os scripts do Configuration Manager. Selecione **OK** para fechar a **janela Adicionar Dependência.**

     * Selecione **Avançar** para continuar.
     
     * **Resumo** – As informações inseridas em todo o assistente Criar Tipo de Implantação são exibidas nesta página. Selecione **Próximo** para confirmar suas seleções.
     
     * **Progresso** – Uma barra de progresso e status à medida que o tipo de implantação é adicionado para o aplicativo de script SEMM é exibido nesta página.
     
     * **Conclusão** – A confirmação da criação do tipo de implantação é exibida quando o processo é concluído. Selecione **Fechar para** concluir o Assistente criar tipo de implantação.

   - **Resumo** – As informações inseridas em todo o Assistente para Criar Aplicativos são exibidas. Selecione **Próximo** para criar o aplicativo.

   - **Progresso** – Uma barra de progresso e status à medida que o aplicativo é adicionado à Biblioteca de Software é exibido nesta página.

   - **Conclusão** – A confirmação da criação bem-sucedida do aplicativo é exibida quando o processo de criação do aplicativo é concluído. Selecione **Fechar** para concluir o Assistente para Criar Aplicativos.

Depois que o aplicativo de script está disponível na Biblioteca de Software do Gerenciador de Configurações, você pode distribuir e implantar o SEMM usando os scripts que você preparou para dispositivos ou coleções. Se você configurou os assemblies do Microsoft Surface UEFI Manager como uma dependência que será instalada automaticamente, você pode implantar o SEMM em uma única etapa. Se você não configurou os assemblies como uma dependência, eles devem ser instalados nos dispositivos que você pretende gerenciar antes de habilitar o SEMM.

Quando você implanta o SEMM usando esse aplicativo de script e com uma configuração visível para o usuário final, o script do PowerShell será acionada e a impressão digital do certificado será exibida pela janela do PowerShell. Você pode fazer com que os usuários gravem essa impressão digital e insiram-na quando solicitados pela UEFI do Surface após a reinicialização do dispositivo.

Como alternativa, você pode configurar a instalação do aplicativo para reiniciar automaticamente e instalar invisivelmente para o usuário. Nesse cenário, um técnico será necessário para inserir a impressão digital em cada dispositivo à medida que ele for reiniciado. Qualquer técnico com acesso ao arquivo de certificado pode ler a impressão digital exibindo o certificado com CertMgr. As instruções para exibir a impressão digital com CertMgr estão na seção Criar ou modificar os scripts do [Semm Configuration Manager](#create-or-modify-the-semm-configuration-manager-scripts) deste artigo.

A remoção do SEMM de um dispositivo implantado com o Configuration Manager usando esses scripts é tão fácil quanto desinstalar o aplicativo com o Configuration Manager. Essa ação inicia o script ResetSEMM.ps1 e desemrolla corretamente o dispositivo com o mesmo arquivo de certificado que foi usado durante a implantação do SEMM.

> [!NOTE]
> O Microsoft Surface recomenda que você crie pacotes de redefinição somente quando precisar desemrollar um dispositivo. Esses pacotes de redefinição geralmente são válidos para apenas um dispositivo, identificado por seu número de série. No entanto, você pode criar um pacote de redefinição universal que funcionaria para qualquer dispositivo inscrito no SEMM com esse certificado.
> 
> É recomendável proteger seu pacote de redefinição universal com cuidado como o certificado usado para registrar dispositivos no SEMM. Lembre-se de que, assim como o certificado em si, esse pacote de redefinição universal pode ser usado para desembrear qualquer um dos dispositivos Surface da sua organização a partir do SEMM.
> 
> Quando você instala um pacote de redefinição, o valor mais baixo com suporte (LSV) é redefinido para um valor 1. Você pode reenvar um dispositivo usando um pacote de configuração existente. O dispositivo solicitará a impressão digital do certificado antes que a propriedade seja tomada.
> 
> Por esse motivo, o reenrollamento de um dispositivo no SEMM exigiria que um novo pacote fosse criado e instalado nesse dispositivo. Como essa ação é um novo registro e não uma alteração na configuração em um dispositivo já inscrito no SEMM, o dispositivo solicitará a impressão digital do certificado antes que a propriedade seja tomada.
