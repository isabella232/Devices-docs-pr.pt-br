---
title: Usar o Gerenciador de configuração do Microsoft Endpoint para gerenciar dispositivos com o SEMM (Surface)
description: Saiba como gerenciar o modo de gerenciamento do Microsoft Surface Enterprise (SEMM) com o Endpoint Configuration Manager.
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
ms.date: 10/13/2020
ms.openlocfilehash: bfd10df3bb7a7dd031c1719d4191ffc46418c4e3
ms.sourcegitcommit: 30c1eb469610dfd2ad9169c154ca07e565240fdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117847"
---
# Usar o Microsoft Endpoint Configuration Manager para gerenciar dispositivos com SEMM

O recurso SEMM (Microsoft Surface Enterprise Management Mode) de dispositivos da Surface UEFI permite que os administradores gerenciem e ajudem a proteger a configuração das configurações de controle de superfície. Para a maioria das organizações, esse processo é realizado criando pacotes do Windows Installer (. msi) com a ferramenta Microsoft Surface UEFI Configuration. Esses pacotes são, em seguida, executados ou implantados nos dispositivos de superfície do cliente para registrar os dispositivos no SEMM e atualizar a configuração de configurações de UEFI da superfície.

Para organizações com o Gerenciador de configuração do Microsoft EndPoint, há uma alternativa em usar o processo Microsoft Surface UEFI Configurator. msi para implantar e administrar o SEMM. O Microsoft Surface UEFI Manager é um instalador leve que torna assemblies necessários para o gerenciamento do SEMM disponível em um dispositivo. Ao instalar esses assemblies com o Microsoft Surface UEFI Manager em um cliente gerenciado, o SEMM pode ser administrado pelo Configuration Manager com scripts do PowerShell, implantados como aplicativos. Com esse processo, o gerenciamento de SEMM é executado no Configuration Manager, que elimina a necessidade da ferramenta Microsoft Surface UEFI configuradora externa.

> [!Note]
> Embora o processo descrito neste artigo possa funcionar com versões anteriores do Endpoint Configuration Manager ou com outras soluções de gerenciamento de terceiros, o gerenciamento de SEMM com o Microsoft Surface UEFI Manager e o PowerShell só tem suporte com o Branch atual do Endpoint Configuration Manager.

#### Pré-requisitos

Antes de começar o processo descrito neste artigo, familiarize-se com as seguintes tecnologias e ferramentas:

* [UEFI da superfície](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [Surface Enterprise Management Mode (SEMM)](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [Script do PowerShell](https://technet.microsoft.com/scriptcenter/dd742419)
* [Implantação de aplicativo do System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* Gerenciamento de certificados

> [!Note]
> Também será necessário acessar o certificado que você pretende usar para proteger o SEMM. Para obter detalhes sobre os requisitos para esse certificado, consulte [requisitos de certificado do modo de gerenciamento da empresa Surface](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).
> 
> É muito importante que esse certificado seja mantido em um local seguro e backup adequado. Se esse certificado ficar perdido ou não ser usado, não será possível redefinir o recurso de UEFI, alterar as configurações de UEFI de superfície gerenciada ou remover SEMM de um dispositivo de superfície inscrito.

#### Baixar o Microsoft Surface UEFI Manager

O gerenciamento de SEMM com o Configuration Manager requer a instalação do Microsoft Surface UEFI Manager em cada dispositivo de superfície de cliente. Você pode baixar o Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) na página [Surface Tools para it](https://www.microsoft.com/download/details.aspx?id=46703) no centro de download da Microsoft.

#### Baixar scripts SEMM para o Configuration Manager

Após o Microsoft Surface UEFI Manager ser instalado no dispositivo de superfície do cliente, o SEMM é implantado e gerenciado com scripts do PowerShell. Você pode baixar exemplos dos [scripts de gerenciamento do Semm](https://www.microsoft.com/download/details.aspx?id=46703) a partir do centro de download.

## Implantar o Microsoft Surface UEFI Manager

A implantação do Microsoft Surface UEFI Manager é uma implantação de aplicativo típica. O arquivo do instalador do Microsoft Surface UEFI Manager é um arquivo padrão do Windows Installer que você pode instalar com a [opção silencioso padrão](https://msdn.microsoft.com/library/windows/desktop/aa367988).

O comando para instalar o Microsoft Surface UEFI Manager é o seguinte.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

O comando para desinstalar o Microsoft Surface UEFI Manager é o seguinte.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

Para criar um novo aplicativo e implantá-lo em uma coleção que contenha seus dispositivos de superfície, execute as seguintes etapas:

1. Abra o console do Configuration Manager na tela **inicial** ou no menu **Iniciar** .
2. Selecione **biblioteca de software** no canto inferior esquerdo da janela.
3. Expanda o nó **Gerenciamento de aplicativos** da biblioteca de software e selecione **aplicativos**.
4. Selecione o botão **criar aplicativo** na guia **página inicial** , na parte superior da janela. Isso inicia o assistente para criação de aplicativos.
5. O assistente criar aplicativo apresenta uma série de etapas:

   * **Geral** – a opção **detectar automaticamente informações sobre este aplicativo a partir de arquivos de instalação** está marcada por padrão. No campo **tipo** , o **Windows Installer (arquivo. msi)** também é selecionado por padrão. Selecione **procurar** para navegar e selecionar **SurfaceUEFIManagerSetup.msi**e, em seguida, selecione **Avançar**.
   
      > [!Note]
      > O local do SurfaceUEFIManagerSetup.msi deve estar em um compartilhamento de rede e localizado em uma pasta que não contenha outros arquivos. Não é possível usar um local de arquivo local.

   * **Importar informações** – o assistente de criação de aplicativos analisará o arquivo. msi e lerá o **nome do aplicativo** e o **código do produto**. SurfaceUEFIManagerSetup.msi deve ser listado como o único arquivo sob os **arquivos de conteúdo**de linha, conforme mostrado na Figura 1. Selecione **Avançar** para continuar.

      ![As informações da configuração do Surface Manager do Surface são automaticamente analisadas](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Figura 1. As informações da configuração do Microsoft Surface UEFI Manager são automaticamente analisadas*

   * **Informações gerais** – você pode modificar o nome do aplicativo e informações sobre o Publisher e a versão ou adicionar comentários nesta página. O comando de instalação do Microsoft Surface UEFI Manager é exibido no campo programa de instalação. O comportamento de instalação padrão da instalação do sistema permitirá que o Microsoft Surface UEFI Manager instale os assemblies necessários para o SEMM mesmo se um usuário não estiver conectado ao dispositivo Surface. Selecione **Avançar** para continuar.
   * **Resumo** – as informações analisadas na etapa informações de **importação** e suas seleções da etapa **informações gerais** são exibidas nesta página. Selecione **Avançar** para confirmar suas seleções e criar o aplicativo.
   * **Progresso** – exibe uma barra de progresso e o status conforme o aplicativo é importado e adicionado à biblioteca de software.
   * **Conclusão** – a confirmação da criação bem-sucedida do aplicativo é exibida quando o processo de criação do aplicativo é concluído. Selecione **fechar** para concluir o assistente de criação de aplicativos.

Após a criação do aplicativo no Configuration Manager, você pode distribuí-lo aos seus pontos de distribuição e implantá-lo nas coleções, incluindo os dispositivos Surface. Este aplicativo não instalará ou habilitará o SEMM no dispositivo Surface. Ele somente fornece os assemblies necessários para que o SEMM seja habilitado usando o script do PowerShell.

Se você não quiser instalar os assemblies do Gerenciador de Microsoft Surface UEFI em dispositivos que não serão gerenciados com o SEMM, é possível configurar o Gerenciador da Microsoft Surface UEFI como uma dependência dos scripts do Gerenciador de configuração do SEMM. Esse cenário é abordado na seção [implantar scripts do Gerenciador de configuração Semm](#deploy-semm-configuration-manager-scripts) mais adiante neste artigo.

## Criar ou modificar os scripts do Gerenciador de configuração do SEMM

Depois que os assemblies necessários tiverem sido instalados nos dispositivos, o processo de registrar os dispositivos no SEMM e configurar o Surface UEFI será feito com os scripts do PowerShell e implantados como uma aplicação de script com o Configuration Manager. Esses scripts podem ser modificados de acordo com as necessidades da sua organização e do seu ambiente. Por exemplo, você pode criar várias configurações para dispositivos de superfície gerenciados em diferentes departamentos ou funções. Você pode baixar exemplos dos scripts do SEMM e do Configuration Manager no link na seção [pré-requisitos](#prerequisites) no início deste artigo.

Há dois scripts principais necessários para realizar uma implantação do SEMM com o Configuration Manager:

* **ConfigureSEMM.ps1** – Use este script para criar pacotes de configuração para seus dispositivos Surface com as configurações de configuração de superfície desejadas para aplicar as configurações especificadas a um dispositivo Surface, para registrar o dispositivo no Semm e para definir uma chave do Registro usada para identificar o registro do dispositivo no Semm.
* **ResetSEMM.ps1** – Use este script para redefinir o Semm em um dispositivo Surface, que o cadastra do Semm e remove o controle sobre as configurações de controle de superfície.

Os scripts de exemplo incluem exemplos de como definir as configurações da superfície UEFI e como controlar as permissões para essas configurações. Essas configurações podem ser modificadas para garantir a UEFI de segurança da superfície e definir configurações da superfície UEFI de acordo com as necessidades do seu ambiente. As seções a seguir deste artigo explicam o ConfigureSEMM.ps1 script e exploram as modificações que você precisa fazer ao script para atender às suas necessidades.

> [!NOTE]
> Os scripts do Gerenciador de configuração do SEMM e o arquivo de certificado SEMM exportado (. pfx) devem ser colocados na mesma pasta sem outros arquivos antes de serem adicionados ao Configuration Manager.

### Especificar nomes de certificado e pacote

A primeira região do script que você precisa modificar é a parte que especifica e carrega o certificado SEMM, e também indica a versão SurfaceUEFIManager e os nomes do pacote de configuração do SEMM e do pacote de redefinição do SEMM. O nome do certificado e a versão do SurfaceUEFIManager são especificados nas linhas de 56 a 73 no script ConfigureSEMM.ps1.

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

Substitua o valor **FabrikamSEMMSample. pfx** da variável **$certName** com o nome do seu arquivo de certificado Semm na linha 58. O script criará um diretório de trabalho (chamado config) na pasta em que os seus scripts estão localizados e, em seguida, copiará o arquivo de certificado para este diretório de trabalho.

O pacote de proprietário e o pacote de redefinição também serão criados no diretório de configuração e armazenarão a configuração para as permissões de controle de superfície e permissões geradas pelo script.

Na linha 73, substitua o valor da variável **$password** , do **1234** à senha do seu arquivo de certificado. Se não for necessária uma senha, exclua o texto do **1234** .

> [!Note]
> Os dois últimos caracteres da impressão digital do certificado são necessários para registrar um dispositivo no SEMM. Esse script exibirá esses dígitos para o usuário, o que permite que o usuário ou o técnico grave esses dígitos antes de o sistema ser reiniciado para registrar o dispositivo no SEMM. O script usa o código a seguir, encontrado nas linhas 150-155, para fazer isso.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Os administradores com acesso ao arquivo de certificado (. pfx) podem ler a impressão digital a qualquer momento abrindo o arquivo. pfx em CertMgr. Para exibir a impressão digital com o CertMgr, siga este processo:

1. Clique com o botão direito do mouse no arquivo. pfx e selecione **abrir**.
2. Expanda a pasta no painel de navegação.
3. Selecione **certificados**.
4. Clique com o botão direito do mouse no certificado no painel principal e selecione **abrir**.
5. Selecione a guia **detalhes** .
6. **Todas as** **Propriedades ou somente** devem ser selecionadas no menu suspenso **Mostrar** .
7. Selecione a **impressão digital**do campo.

> [!NOTE]
> O nome de certificado e a senha do SEMM também devem ser inseridos nesta seção do script ResetSEMM.ps1 para permitir que o Configuration Manager remova SEMM do dispositivo com a ação de desinstalação.

### Configurar permissões

A primeira região do script em que você especificará a configuração do Surface UEFI é a região **configurar permissões** . Esta região começa na linha 210 do script de exemplo com o comentário **# Configure permissões** e continua para a linha 247. O fragmento de código a seguir define permissões para todas as configurações de Surface UEFI para que elas possam ser modificadas apenas por SEMM e, em seguida, adicionam permissões explícitas para permitir que o usuário local modifique a senha UEFI da superfície, TPM e câmeras frontais e posteriores.

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

Cada variável **$uefiV 2** identifica uma configuração de Surface UEFI definindo o nome ou a ID e, em seguida, configura as permissões para um dos seguintes valores:

* **$ownerOnly** – a permissão para modificar essa configuração é concedida somente a Semm.
* **$ownerAndLocalUser** – a permissão para modificar essa configuração é concedida a uma inicialização de usuário local para a UEFI da superfície, bem como Semm.

Você pode encontrar informações sobre os nomes e IDs de configurações disponíveis para a identificação de superfície na seção [nomes e IDs de configurações](#settings-names-and-ids) deste artigo.

### Definir configurações

A segunda região do script em que você especificará a configuração de Surface UEFI é a região de **configurações** de configuração do script ConfigureSEMM.ps1, que define se cada configuração está habilitada ou desabilitada. O script de exemplo inclui instruções para definir todos os valores padrão de todas as configurações. Em seguida, o script fornece instruções explícitas para desabilitar o IPv6 para inicialização PXE e deixar a senha do administrador da superfície UEFI inalterada. Você pode encontrar essa região começando com o comentário de **# Configurar configurações** na linha 291 até a linha 335 no script de exemplo. A região aparece da seguinte maneira.

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

Assim como as permissões definidas na seção **configurar permissões** do script, a configuração de cada configuração de Surface UEFI é realizada definindo a variável **$uefiV 2** . Para cada linha que define a variável **$uefiV 2** , uma configuração de Surface UEFI é identificada pela configuração de Name ou ID e o valor configurado é definido como **Enabled** ou **Disabled**.

Se você não quiser alterar a configuração de uma configuração de superfície UEFI, por exemplo, para garantir que a senha do administrador do Surface não seja desmarcada pela ação de redefinir todas as configurações da superfície UEFI para o padrão, você pode usar **ClearConfiguredValue ()** para impor que essa configuração não será alterada. No script de exemplo, ele é usado na linha 323 para impedir a limpeza da senha de administrador da superfície UEFI, identificada no script de exemplo por sua ID de configuração, **501**.

Você pode encontrar informações sobre os nomes e IDs de configurações disponíveis para a identificação do Surface na seção [nomes e IDs de configurações](#settings-names-and-ids) mais adiante neste artigo.

### Chave do registro de configurações

Para identificar sistemas registrados para o Configuration Manager, o script ConfigureSEMM.ps1 grava as chaves do registro que podem ser usadas para identificar sistemas registrados como se tivessem sido instalados com o script de configuração SEMM. Essas chaves podem ser encontradas no local a seguir.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

O fragmento de código a seguir, encontrado nas linhas 380-477, é usado para gravar essas chaves do registro.

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

### Nomes e IDs de configurações

Para definir as configurações de Surface UEFI ou permissões para configurações de Surface UEFI, você deve se referir a cada configuração por meio do nome da configuração ou da ID de configuração. As novas configurações podem ser adicionadas a cada nova atualização para o Surface UEFI. A melhor maneira de obter uma lista completa das configurações disponíveis em um dispositivo de superfície, juntamente com as IDs de nomes e configurações, é usar o script ShowSettingsOptions.ps1 de SEMM_Powershell.zip em [ferramentas de superfície para downloads de ti](https://www.microsoft.com/download/details.aspx?id=46703) 

O computador em que o ShowSettingsOptions.ps1 é executado deve ter o Microsoft Surface UEFI Manager instalado, mas o script não requer um dispositivo Surface.

A melhor maneira de exibir os nomes e as IDs de configuração mais recentes de dispositivos é usar o ConfigureSEMM.ps1 script ou o ConfigureSEMM- <device name> . ps1 do SEMM_Powershell.zip em [ferramentas de superfície para downloads](https://www.microsoft.com/download/details.aspx?id=46703).

A configuração de nomes e IDs para todos os dispositivos pode ser vista no script ConfigureSEMM.ps1.

A configuração de nomes e IDs para dispositivos específicos pode ser vista nos scripts ConfigureSEMM- <device name> . ps1. 

## Implantar scripts do SEMM Configuration Manager

Depois que seus scripts estiverem preparados para configurar e habilitar o SEMM no dispositivo cliente, a próxima etapa será adicionar esses scripts como um aplicativo no Configuration Manager. Antes de abrir o Configuration Manager, verifique se os seguintes arquivos estão em uma pasta compartilhada que não inclui outros arquivos:

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* Seu certificado SEMM (por exemplo SEMMCertificate. pfx)

Os scripts do Gerenciador de configuração do SEMM serão adicionados ao Configuration Manager como um aplicativo de script. O comando para instalar o SEMM com ConfigureSEMM.ps1 é o seguinte.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

O comando para desinstalar o SEMM com ResetSEMM.ps1 é o seguinte.

`Powershell.exe -file ".\ResetSEMM.ps1"`

Para adicionar os scripts do Gerenciador de configuração SEMM ao Configuration Manager como um aplicativo, use o seguinte processo:

1. Inicie o assistente de criação de aplicativos usando a etapa 1 até a etapa 5 da seção [implantar o Gerenciador de Microsoft Surface UEFI](#deploy-microsoft-surface-uefi-manager) anteriormente neste artigo.

2. Prossiga pelo assistente de criação de aplicativos da seguinte maneira:

   - **Geral** – selecione **especificar manualmente as informações do aplicativo**e, em seguida, selecione **Avançar**.

   - **Informações gerais** – Insira um nome para o aplicativo (por exemplo, Semm) e qualquer outra informação que você queira, como o Publisher, versão ou comentários nesta página. Selecione **Avançar** para continuar.

   - **Catálogo de aplicativos** – os campos nessa página podem ser deixados com os valores padrão. Selecione **Avançar**.

   - **Tipos de implantação** – selecione **Adicionar** para iniciar o assistente criar tipo de implantação.

   - Siga as etapas do assistente para criação de tipo de implantação, da seguinte maneira:

     * **Geral** – selecione **instalador de script** no menu suspenso **tipo** . A opção **especificar manualmente a opção informações do tipo de implantação** será selecionada automaticamente. Selecione **Avançar** para continuar.
     * **Informações gerais** – Insira um nome para o tipo de implantação (por exemplo, scripts de configuração Semm) e, em seguida, selecione **Avançar** para continuar.
     * **Conteúdo** – selecione **procurar** ao lado do campo **local do conteúdo** e, em seguida, selecione a pasta onde os seus scripts do Semm Configuration Manager estão localizados. No campo **programa de instalação** , digite o [comando de instalação](#deploy-semm-configuration-manager-scripts) encontrado anteriormente neste artigo. No campo **desinstalar programa** , digite o [comando de desinstalação](#deploy-semm-configuration-manager-scripts) encontrado anteriormente neste artigo (mostrado na Figura 2). Selecione **Avançar** para ir para a próxima página.
    
     ![Definir os scripts do Gerenciador de configuração SEMM como os comandos instalar e desinstalar](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Figura 2. Definir os scripts do Gerenciador de configuração SEMM como os comandos instalar e desinstalar*

     * **Método de detecção** – selecione **Adicionar cláusula** para adicionar a regra de detecção de chave do registro de script do Configuration Manager do Semm. A janela **regra de detecção** é exibida, conforme mostrado na Figura 3. Use as seguintes configurações:

       - Selecione **registro** no menu suspenso **tipo de configuração** .
       - Selecione **HKEY_LOCAL_MACHINE** no menu suspenso **Hive** .
       - Digite **SOFTWARE\Microsoft\Surface\SEMM** no campo **chave** .
       - Insira **CertName** no campo **Value** .
       - Selecione **cadeia de caracteres** no menu suspenso **tipo de dados** .
       - Selecione a **seguinte configuração do registro deve satisfazer a seguinte regra para indicar o botão presença deste aplicativo** .
       - Digite o nome do certificado que você digitou na linha 58 do script no campo **valor** .
       - Selecione **OK** para fechar a janela de **regra de detecção** .

     ![Usar uma chave do registro para identificar os dispositivos registrados no SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *Figura 3. Usar uma chave do registro para identificar os dispositivos registrados no SEMM*

     * Selecione **Avançar** para ir para a próxima página.
     
     * **Experiência do usuário** – selecione **instalar para o sistema** no menu suspenso comportamento de **instalação** . Se você quiser que os usuários registrem e insiram a impressão digital do certificado, deixe o requisito de logon definido como **somente quando um usuário estiver conectado**. Se quiser que os administradores insiram a impressão digital para os usuários e os usuários não precisem ver a impressão digital, selecione **se o usuário está ou não conectado** do menu suspenso de **requisitos de logon** .

     * **Requisitos** – o script ConfigureSEMM.ps1 verifica automaticamente se o dispositivo é um dispositivo Surface antes de tentar habilitar o Semm. No entanto, se você pretende implantar esse aplicativo de script em uma coleção com dispositivos diferentes daqueles a serem gerenciados com o SEMM, você pode adicionar requisitos aqui para garantir que esse aplicativo seria executado apenas em dispositivos de superfície ou dispositivos que você pretende gerenciar com o SEMM. Selecione **Avançar** para continuar.
     
     * **Dependências** – selecione **Adicionar** para abrir a janela **Adicionar dependência** .

       * Selecione **Adicionar** para abrir a janela **especificar aplicativo necessário** .

          - Insira um nome para as dependências do SEMM no campo **nome do grupo de dependências** (por exemplo, *Semm assemblys*).

          - Selecione **Microsoft Surface UEFI Manager** na lista de **aplicativos disponíveis** e o tipo de implantação msi e, em seguida, selecione **OK** para fechar a janela **especificar aplicativo necessário** .
          
         *   Mantenha a caixa de seleção **instalação automática** marcada se desejar que o Microsoft Surface UEFI Manager seja instalado automaticamente em dispositivos quando você tentar habilitar o Semm com os scripts do Configuration Manager. Selecione **OK** para fechar a janela **Adicionar dependência** .

     * Selecione **Avançar** para continuar.
     
     * **Resumo** – as informações que você digitou em todo o assistente para criar tipo de implantação são exibidas nesta página. Selecione **Avançar** para confirmar suas seleções.
     
     * **Progresso** – uma barra de progresso e status como o tipo de implantação é adicionado para o aplicativo de script Semm é exibido nesta página.
     
     * **Conclusão** – a confirmação da criação do tipo de implantação é exibida quando o processo é concluído. Selecione **fechar** para concluir o assistente para criar tipo de implantação.

   - **Resumo** – as informações que você inseriu em todo o assistente para criar aplicativos são exibidas. Selecione **Avançar** para criar o aplicativo.

   - **Progresso** – uma barra de progresso e o status conforme o aplicativo é adicionado à biblioteca de software são exibidos nesta página.

   - **Conclusão** – a confirmação da criação bem-sucedida do aplicativo é exibida quando o processo de criação do aplicativo é concluído. Selecione **fechar** para concluir o assistente de criação de aplicativos.

Depois que o aplicativo de script estiver disponível na biblioteca de software do Configuration Manager, você poderá distribuir e implantar o SEMM usando os scripts preparados para dispositivos ou coleções. Se você configurou os assemblies do Gerenciador de Microsoft Surface UEFI como uma dependência que será instalada automaticamente, você pode implantar o SEMM em uma única etapa. Se você não configurou os assemblies como uma dependência, eles devem ser instalados nos dispositivos que você pretende gerenciar antes de habilitar o SEMM.

Ao implantar o SEMM usando esse aplicativo de script e uma configuração visível para o usuário final, o script do PowerShell será iniciado e a impressão digital do certificado será exibida pela janela do PowerShell. Você pode fazer seus usuários gravarem essa impressão digital e digitá-la quando solicitado pela UEFI de Surface após a reinicialização do dispositivo.

Você também pode configurar a instalação do aplicativo para reinicializar automaticamente e instalar invisivelmente para o usuário. Nesse cenário, um técnico será solicitado a inserir a impressão digital em cada dispositivo à medida que ele for reinicializado. Qualquer técnico com acesso ao arquivo de certificado pode ler a impressão digital exibindo o certificado com CertMgr. Instruções para exibir a impressão digital com CertMgr estão na seção [criar ou modificar os scripts do Gerenciador de configuração Semm](#create-or-modify-the-semm-configuration-manager-scripts) deste artigo.

A remoção de SEMM de um dispositivo implantado com o Configuration Manager usando esses scripts é tão fácil quanto desinstalar o aplicativo com o Configuration Manager. Essa ação inicia o script ResetSEMM.ps1 e corretamente cancelar o registro do dispositivo com o mesmo arquivo de certificado usado durante a implantação do SEMM.

> [!NOTE]
> A Microsoft Surface recomenda que você crie pacotes de redefinição somente quando precisar cancelar o registro de um dispositivo. Esses pacotes de redefinição geralmente são válidos para apenas um dispositivo, identificado pelo seu número de série. No entanto, você pode criar um pacote de redefinição universal que funcionaria para qualquer dispositivo registrado no SEMM com esse certificado.
> 
> É altamente recomendável que você proteja seu pacote de restauração universal com cuidado com o certificado que usou para inscrever dispositivos no SEMM. Lembre-se de que, assim como o próprio certificado, este pacote universal de restauração pode ser usado para cancelar a inscrição de todos os dispositivos de superfície da sua organização do SEMM.
> 
> Quando você instala um pacote de redefinição, o menor valor com suporte (LSV) é redefinido para um valor de 1. Você pode reinscrever um dispositivo usando um pacote de configuração existente. O dispositivo solicitará a impressão digital do certificado antes que a propriedade seja tirada.
> 
> Por esse motivo, a reinscrição de um dispositivo no SEMM exigiria um novo pacote a ser criado e instalado nesse dispositivo. Como essa ação é uma nova inscrição e não uma alteração na configuração em um dispositivo já registrado no SEMM, o dispositivo solicitará a impressão digital do certificado antes de a propriedade ser executada.
