---
title: Portas seguras do Surface Dock 2 com o Surface Enterprise Modo de Gerenciamento (SEMM)
description: Este documento fornece orientações para configurar configurações de porta UEFI para o Surface Dock 2 quando conectado a dispositivos Surface compatíveis, incluindo Surface Book 3, Surface Laptop 3 e Surface Pro 7.
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: Solução de problemas comuns, problemas de instalação
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 08/02/2021
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 3eae976b1559c59bf44a94a62eb98dd3a3687424
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448484"
---
# <a name="secure-surface-dock-2-ports-with-surface-enterprise-management-mode-semm"></a>Portas seguras do Surface Dock 2 com o Surface Enterprise Modo de Gerenciamento (SEMM)

## <a name="introduction"></a>Introdução

O Modo de Gerenciamento do Surface Enterprise (SEMM) permite que os administradores de IT protejam e gerenciem portas do Surface Dock 2 configurando as configurações uefi em um pacote de configuração do Windows Installer (arquivo .msi) implantado em dispositivos Surface compatíveis em um ambiente corporativo.

### <a name="supported-devices"></a>Dispositivos com suporte

Gerenciar o Surface Dock 2 com SEMM está disponível para docas conectadas ao Surface Book 3, Surface Laptop Studio, Surface Laptop 4, Surface Laptop 3, Surface Laptop Go, Surface Pro 8, Surface Pro 7+, Surface Pro 7 e Surface Pro X. Esses dispositivos Surface compatíveis são comumente chamados de **dispositivos host**. Um pacote é aplicado a dispositivos host com base em se um dispositivo host for **autenticado** ou **não autenticado**. As configurações residem na camada UEFI em dispositivos host que permitem que você , o administrador de TI, gerencie o Surface Dock 2 como qualquer outro periférico integrado, como a câmera.

>[!NOTE]
>Você pode gerenciar as portas do Surface Dock 2 somente quando o dock estiver conectado a um dos seguintes dispositivos compatíveis: Surface Pro 8, Surface Laptop Studio, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, e Surface Pro 7. Qualquer dispositivo que não receba as configurações de política autenticada UEFI é inerentemente um dispositivo não autenticado.

### <a name="scenarios"></a>Cenários

Restringir o Surface Dock 2 a pessoas autorizadas conectados a um dispositivo host corporativo fornece outra camada de proteção de dados. Essa capacidade de bloquear o Surface Dock 2 é fundamental para clientes específicos em ambientes altamente seguros que querem a funcionalidade e os benefícios de produtividade do dock, mantendo a conformidade com protocolos de segurança estritos. Prevemos que o SEMM usado com o Surface Dock 2 seja particularmente útil em escritórios abertos e espaços compartilhados, especialmente para clientes que querem bloquear portas USB por motivos de segurança. Para uma demonstração de vídeo, confira [SEMM para Surface Dock 2](https://youtu.be/VLV19ISvq_s).

## <a name="configuring-and-deploying-uefi-settings-for-surface-dock-2"></a>Configurando e implantando configurações uefi para o Surface Dock 2

Esta seção fornece orientações passo a passo para as seguintes tarefas:

1. Instale **o Surface UEFI Configurator** a partir [das Ferramentas do Surface para IT](https://www.microsoft.com/download/details.aspx?id=46703).
1. Criar ou obter certificados de chave pública.
1. Crie um pacote .msi configuração.
   1. Adicione seus certificados.
   1. Insira o número RN de 16 dígitos para seus dispositivos Surface Dock 2.
   1. Configure as configurações UEFI.
1. Criar e aplicar o pacote de configuração a dispositivos Surface direcionados (Surface Book 3, Surface Laptop 3 ou Surface Pro 7.)

>[!NOTE]
>O **Número Aleatório (RN)** é um identificador de código hexaxa de 16 dígitos exclusivo que é provisionado na fábrica e impresso em um tipo pequeno na parte inferior do encaixe. O RN difere da maioria dos números de série, já que não pode ser lido eletronicamente. Isso garante que a prova de propriedade seja estabelecida principalmente lendo o RN ao acessar fisicamente o dispositivo. O RN também pode ser obtido durante a transação de compra e é registrado em sistemas de inventário da Microsoft.

### <a name="install-semm-and-surface-uefi-configurator"></a>Instalar o SEMM e o Surface UEFI Configurator

Instale o SEMM executando **SurfaceUEFI_Configurator_v2.83.139.0.msi.** Este é um instalador autônomo e contém tudo o que você precisa para criar e distribuir pacotes de configuração para o Surface Dock 2.

- Baixe **o Configurador UEFI do Surface** [Tools para IT](https://www.microsoft.com/download/details.aspx?id=46703).

## <a name="create-public-key-certificates"></a>Criar certificados de chave pública

Esta seção fornece especificações para a criação dos certificados necessários para gerenciar portas para o Surface Dock 2.

### <a name="prerequisites"></a>Pré-requisitos

Este artigo pressupo que você obtenha certificados de um provedor de terceiros ou já tenha experiência em serviços de certificado PKI e saiba como criar seus próprios.  Você deve estar familiarizado e seguir as recomendações gerais para a criação de certificados, conforme descrito na documentação do [Surface Enterprise Management Mode (SEMM),](surface-enterprise-management-mode.md) com uma exceção. Os certificados documentados nesta página exigem termos de expiração de 30 anos para **** a Autoridade de Certificação do Dock e 20 anos para o **Certificado de Autenticação de Host**.

Para obter mais informações, consulte Certificate [Services Architecture](/windows/win32/seccrypto/certificate-services-architecture) documentation and review the appropriate chapters [in Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277), or [Windows Server 2008 PKI and Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) available from Microsoft Press.

### <a name="root-and-host-certificate-requirements"></a>Requisitos de certificado raiz e host

Antes de criar o pacote de configuração, você precisa preparar certificados de chave pública que autenticam a propriedade do Surface Dock 2 e facilitam as alterações subsequentes na propriedade durante o ciclo de vida do dispositivo. Os certificados de host e provisionamento exigem a inserção de IDs de EKU também conhecidas como identificadores de objeto **EKU (Client Authentication Enhanced Key Usage) (OIDs)**.

Os valores EKU necessários estão listados na Tabela 1 e na Tabela 2.

#### <a name="table-1-root-and-dock-certificate-requirements"></a>Tabela 1. Requisitos de Certificado raiz e encaixado

|Certificado|Algoritmo|Descrição|Expiração|EKU OID|
|---|---|---|---|---|
|Autoridade de Certificação Raiz|ECDSA_P384|- Certificado raiz com algoritmo de assinatura digital de curva elíptica principal de 384 bits (ECDSA)<br>- Uso da chave SHA 256:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>- CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 anos|N/D
|Autoridade de Certificação do Dock|Curva ECC P256|- Certificado host com criptografia de curva elíptica de 256 bits (ECC)<br>- Uso da chave SHA 256:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>- Restrição de Comprimento do Caminho = 0|20 anos|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >A CA do dock deve ser exportada como um arquivo .p7b.

### <a name="provisioning-administration-certificate-requirements"></a>Requisitos de Certificado de Administração de Provisionamento

Cada dispositivo host deve ter a CA doc e dois certificados, conforme mostrado na Tabela 2.

#### <a name="table-2-provisioning-administration-certificate-requirements"></a>Tabela 2. Requisitos de certificado de administração de provisionamento

|Certificado|Algoritmo|Descrição|EKU OID|
|---|---|---|---|
|Certificado de autenticação de host|ECC P256<br>SHA 256|Prova a identidade do dispositivo host.|1.3.6.1.4.1.311.76.9.21.2|
|Certificado de administração de provisionamento|ECC P256<br>SHA256|Permite que você altere as configurações de propriedade e/ou política do dock, permitindo que você substitua a AC instalada no momento no dock.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >Os certificados de autenticação e provisionamento de host devem ser exportados como arquivos .pfx.

### <a name="create-configuration-package"></a>Criar pacote de configuração

Quando você tiver obtido ou criado os certificados, estará pronto para criar o pacote de configuração .msi que será aplicado aos dispositivos Surface de destino.

1. Execute o **Configurador UEFI do** Surface.

   ![Execute o Configurador UEFI do Surface.](images/secure-surface-dock-ports-semm-1.png)

1. Selecione **Surface Dock**.

   ![Selecione Surface Dock.](images/secure-surface-dock-ports-semm-2.png)

1. Insira os **certificados apropriados**  na página de certificados. Os certificados de demonstração estão disponíveis no [Surface Tools para IT](https://www.microsoft.com/download/details.aspx?id=46703): Baixe **SEMM_PowerShell.zip** e consulte **CreateSurfaceDock2Certificates.ps1**. Certifique-se de instalar **SurfaceDock2_WmiInstanceProvider** antes de executar os scripts de demonstração.

   ![insira os certificados apropriados.](images/secure-surface-dock-ports-semm-3.png)

1. Adicione RNs de encaixe apropriados à lista.

   >[!TIP]
   >Ao criar um pacote de configuração para vários dispositivos Surface Dock 2, em vez de inserir cada RN manualmente, você pode usar um arquivo .csv que contém uma lista de RNs.

1. Especifique suas configurações de política para dados USB, ethernet e portas de áudio. O Configurador UEFI permite configurar configurações de política para usuários autenticados (Política Autenticada) e usuários não autenticados (Política Não Autenticada). A figura a seguir mostra o acesso de porta ligado para usuários autenticados e desligados para usuários não autenticados.

   ![Escolha quais componentes você deseja ativar ou desativar.](images/secure-surface-dock-ports-semm-4.png)

   - O usuário autenticado refere-se a um Dispositivo Surface que tem os certificados apropriados instalados, conforme configurado no pacote de configuração .msi que você aplicou a dispositivos de destino. Aplica-se a qualquer usuário autenticado que entre no dispositivo.
   - O usuário não autenticado se refere a qualquer outro dispositivo.
   - Selecione **Redefinir** para criar um pacote especial de "Redefinição" que removerá qualquer pacote de configuração anterior aceito pelo dock.

1. Selecione **Criar** para criar o pacote conforme especificado.

### <a name="apply-the-configuration-package-to-a-surface-dock-2"></a>Aplicar o pacote de configuração a um Surface Dock 2

1. Pegue o .msi que o Configurador UEFI do Surface gerou e instale-o em um dispositivo host do Surface. Os dispositivos host compatíveis Surface Book 3, Surface Laptop Studio, Surface Laptop 3, Surface Laptop 4, Surface Pro 7+e Surface Pro 7.
1. Conexão o dispositivo host para o Surface Dock 2. Quando você conecta as configurações de política UEFI do dock são aplicadas.

## <a name="verify-managed-state-using-the-surface-app"></a>Verificar o estado gerenciado usando o Surface App

Depois de aplicar o pacote de configuração, você pode verificar rapidamente o estado de política resultante do dock diretamente do Surface App, instalado por padrão em todos os dispositivos Surface. Se o Surface App não estiver presente no dispositivo, você poderá baixá-lo e instalá-lo do Microsoft Store.

### <a name="test-scenario"></a>Cenário de teste

Objetivo: Configurar configurações de política para permitir o acesso de porta somente por usuários autenticados.

1. A turn on all ports for authenticated users and turn them off for unauthenticated users.

   ![Habilitando portas para usuários autenticados.](images/secure-surface-dock-ports-semm-4.png)

1. Aplique o pacote de configuração ao dispositivo de destino e conecte o Surface Dock 2.

1. Abra **o Surface App** e selecione **Surface Dock** para exibir o estado de política resultante do Surface Dock. Se as configurações de política são aplicadas, o Surface App indicará que as portas estão disponíveis.

   ![O aplicativo Surface mostra que todas as portas estão disponíveis para usuários autenticados.](images/secure-surface-dock-ports-semm-5.png)

1. Agora você precisa verificar se as configurações de política desligaram com êxito todas as portas para usuários não autenticados. Conexão Surface Dock 2 para um dispositivo não gerenciada, ou seja, qualquer dispositivo Surface fora do escopo de gerenciamento do pacote de configuração criado.

1. Abra **o Surface App** e selecione **Surface Dock**. O estado de política resultante indicará que as portas estão desligadas.

   ![Aplicativo surface mostrando portas desligadas para usuários não autenticados .](images/secure-surface-dock-ports-semm-6.png)

>[!TIP]
>Se você quiser manter a propriedade do dispositivo, mas permitir acesso total a todos os usuários, poderá fazer um novo pacote com tudo ligado. Se você quiser remover completamente as restrições e a propriedade do dispositivo (torná-lo nãomanageado), selecione **Redefinir** no Surface UEFI Configurator para criar um pacote para aplicar a dispositivos de destino.

Parabéns. Você gerencia com êxito as portas do Surface Dock 2 em dispositivos host direcionados.

## <a name="learn-more"></a>Saiba mais

- [Documentação do Modo de Gerenciamento do Surface Enterprise (SEMM)](surface-enterprise-management-mode.md)
- [Arquitetura de Serviços de Certificado](/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 de dentro para fora](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows Server 2008 PKI e Segurança de Certificado](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
