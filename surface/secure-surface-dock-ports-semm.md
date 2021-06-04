---
title: Proteger portas do Dock Surface 2 com o modo de gerenciamento do Surface Enterprise (SEMM)
description: Este documento fornece orientação para definir as configurações de porta UEFI para o Surface Dock 2 quando conectado a dispositivos de superfície compatíveis, incluindo o catálogo de superfície 3, Surface laptop 3 e Surface Pro 7.
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
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 641d023b59426582130dcfb7e0d86c6f3af456e8
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114689"
---
# Proteger portas do Dock Surface 2 com o modo de gerenciamento do Surface Enterprise (SEMM)

##  <a name="introduction"></a>Introdução

O SEMM (Surface Enterprise Management Mode) permite que os administradores de ti protejam e gerenciem portas do Dock 2, definindo as configurações de UEFI em um pacote de configuração do Windows Installer (. Arquivo MSI) implantado para dispositivos de superfície compatíveis em um ambiente corporativo.

###  <a name="supported-devices"></a>Dispositivos com suporte

O gerenciamento do Surface Dock 2 com o SEMM está disponível para cais conectados ao livro Surface 3, Surface laptop 3, Surface laptop Go, Surface Pro 7 e Surface Pro X. Esses dispositivos de superfície compatíveis são comumente chamados de **dispositivos de host**. Um pacote é aplicado a dispositivos host baseados em se um dispositivo de host é **autenticado** ou não **autenticado**. As configurações definidas residem na camada UEFI em dispositivos host que permitem que você, o administrador de ti, gerencie o Surface Dock 2 como qualquer outro periférico embutido, como a câmera.

>[!NOTE]
>Você só pode gerenciar portas do Dock Surface 2 quando o Dock estiver conectado a um dos seguintes dispositivos compatíveis: livro Surface 3, Surface laptop 3 e Surface Pro 7. Qualquer dispositivo que não recebe as configurações de política UEFI autenticado é inerentemente um dispositivo não autenticado.

###  <a name="scenarios"></a>Cenários

A restrição do Dock Surface 2 para pessoas autorizadas conectadas a um dispositivo host corporativo oferece outra camada de proteção de dados. Essa capacidade de bloquear o Surface Dock 2 é essencial para clientes específicos em ambientes altamente seguros que desejam os benefícios da funcionalidade e da produtividade do Dock, mantendo a conformidade com protocolos de segurança estritos. Prevêmos que o SEMM usado com o Surface Dock 2 será particularmente útil em escritórios abertos e espaços compartilhados, especialmente para clientes que desejam bloquear portas USB por motivos de segurança. Para ver uma demonstração em vídeo, confira [Semm para Surface Dock 2](https://youtu.be/VLV19ISvq_s).

##  <a name="configuring-and-deploying-uefi-settings-for-surface-dock-2"></a>Configurar e implantar as configurações de UEFI para o Surface Dock 2

Esta seção fornece uma orientação passo a passo para as seguintes tarefas:

1. Instale o [**configurador UEFI da Surface**](https://www.microsoft.com/download/details.aspx?id=46703).
1. Criar ou obter certificados de chave pública.
1. Criar um. Pacote de configuração MSI.
   1. Adicione seus certificados.
   1. Digite o número de 16 dígitos RN para seus dispositivos de Surface Dock 2.
   1. Definir configurações de UEFI.
1. Crie e aplique o pacote de configuração a dispositivos de superfície direcionada (livro de superfície 3, Surface laptop 3 ou Surface Pro 7.)

>[!NOTE]
>O **número aleatório (RN)** é um identificador de código hexadecimal de 16 dígitos exclusivo que é provisionado na fábrica e impresso em pequeno tipo na parte inferior do Dock. O RN é diferente da maioria dos números de série, pois ele não pode ser lido eletronicamente. Isso garante que o comprovante de propriedade seja basicamente estabelecido apenas lendo o RN ao acessar fisicamente o dispositivo. O RN também pode ser obtido durante a transação de compra e é registrado em sistemas de inventário da Microsoft.

###  <a name="install-semm-and-surface-uefi-configurator"></a>Instale o configurador UEFI SEMM e Surface

Instale o SEMM executando **SurfaceUEFI_Configurator_v2.71.139.0.msi**. Este é um instalador autônomo e contém tudo o que você precisa para criar e distribuir pacotes de configuração para o Surface Dock 2.

- Baixe o recurso **configurador UEFI da Surface** nas [ferramentas Surface para ele](https://www.microsoft.com/en-us/download/details.aspx?id=46703).

##  <a name="create-public-key-certificates"></a>Criar certificados de chave pública

Esta seção fornece especificações para a criação dos certificados necessários para gerenciar portas para o Surface Dock 2.

###  <a name="prerequisites"></a>Pré-requisitos

Este artigo pressupõe que você pode obter certificados de um provedor de terceiros ou já tem experiência em serviços de certificado PKI e sabe como criar seus próprios.  Você deve estar familiarizado com e seguir as recomendações gerais para a criação de certificados, conforme descrito em documentação do [modo de gerenciamento do Surface Enterprise (Semm)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) , com uma exceção. Os certificados documentados nesta página exigem os termos de expiração de 30 anos para a **autoridade de certificação Dock**e 20 anos para o **certificado de autenticação de host**.

Para obter mais informações, consulte documentação da [arquitetura dos serviços de certificado](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) e revise os capítulos apropriados no [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)ou no [Windows Server 2008 PKI e segurança de certificado](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) disponíveis na Microsoft Press.

###  <a name="root-and-host-certificate-requirements"></a>Requisitos de certificado raiz e de host

Antes de criar o pacote de configuração, você precisa preparar certificados de chave pública que autenticam a propriedade do Surface Dock 2 e facilitar alterações subsequentes na propriedade durante o ciclo de vida do dispositivo. Os certificados de host e provisionamento exigem a inserção de IDs EKU, de outra forma, conhecidas como **identificadores de objetos (EKU) de autenticação avançada do cliente**.

Os valores de EKU necessários estão listados na tabela 1 e tabela 2.

####  <a name="surface-hub-2-fingerprint-reader-tech-specs"></a>Tabela 1. Requisitos de certificado raiz e Dock

|Certificado|Algoritmo|Descrição|Expiração|OID EKU|
|---|---|---|---|---|
|Autoridade de certificação raiz|ECDSA_P384|-Certificado raiz com o algoritmo de assinatura digital de curva elíptica de 384 bits (ECDSA)<br>-Uso da chave do SHA 256:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>-CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 anos|N/D
|Encaixar autoridade de certificação|Curva de P256 ECC|-Certificado de host com ECC (criptografia elíptica de curva de 256 bits)<br>-Uso da chave do SHA 256:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>-Restrição de comprimento de caminho = 0|20 anos|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >A CA Dock deve ser exportada como um arquivo. p7b.

###  <a name="provisioning-administration-certificate-requirements"></a>Requisitos de certificado de administração de provisionamento

Cada dispositivo de host deve ter a CA do doc e dois certificados, conforme mostrado na tabela 2.

#### Tabela 2. Requisitos de certificado de administração de provisionamento

|Certificado|Algoritmo|Descrição|OID EKU|
|---|---|---|---|
|Certificado de autenticação de host|P256 ECC<br>SHA 256|Prova a identidade do dispositivo host.|1.3.6.1.4.1.311.76.9.21.2|
|Provisionando certificado de administração|P256 ECC<br>SHA256|Permite que você altere a propriedade Dock e/ou configurações de política, permitindo que você substitua a autoridade de certificação que está instalada atualmente no Dock.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >Os certificados de autenticação de host e provisionamento devem ser exportados como arquivos. pfx.

###  <a name="create-configuration-package"></a>Criar pacote de configuração

Depois de obter ou criar os certificados, você estará pronto para criar o pacote de configuração MSI que será aplicado aos dispositivos de superfície de destino.

1. Executar **configurador UEFI**de Surface.

   ![Executar configurador UEFI de Surface](images/secure-surface-dock-ports-semm-1.png)

1. Selecione **encaixe de superfície**.

   ![Selecionar encaixe de superfície](images/secure-surface-dock-ports-semm-2.png)

1. Na página certificado, insira os **certificados**apropriados.

   ![Insira os certificados apropriados](images/secure-surface-dock-ports-semm-3.png)

1. Adicione o encaixe adequado RNs à lista.

   >[!NOTE]
   >Ao criar um pacote de configuração para vários dispositivos do Dock Surface 2, em vez de digitar cada RN manualmente, você pode usar um arquivo. csv que contém uma lista de RNs.

1. Especifique as configurações de política para dados USB, Ethernet e portas de áudio. O UEFI configurador permite que você defina as configurações de política para usuários autenticados (política autenticada) e usuários não autenticados (política não autenticada). A figura a seguir mostra o acesso às portas ativada para usuários autenticados e desativada para usuários não autenticados.

   ![Escolha quais componentes você deseja ativar ou desativar.](images/secure-surface-dock-ports-semm-4.png)

   - O usuário autenticado refere-se a um dispositivo de superfície que tem os certificados apropriados instalados, conforme configurado em. Pacote de configuração MSI que você aplicou aos dispositivos de destino. Ele se aplica a qualquer usuário autenticado do usuário que assine o dispositivo. 
   - Um usuário não autenticado refere-se a qualquer outro dispositivo.
   - Selecione **Redefinir** para criar um pacote "Reset" especial que removerá qualquer pacote de configuração anterior que o Dock tivesse aceitado.

1. Selecione **Compilar** para criar o pacote conforme especificado.

###  <a name="apply-the-configuration-package-to-a-surface-dock-2"></a>Aplicar o pacote de configuração a um Dock Surface 2

1. Pegue o arquivo MSI gerado pelo Configurador da Surface do Surface e instale-o em um dispositivo de host Surface. Os dispositivos de host compatíveis são o livro Surface 3, Surface laptop 3 ou Surface Pro 7.
1. Conecte o dispositivo de host ao Dock Surface 2. Quando você conecta as configurações de política de UEFI de encaixe são aplicadas.

##  <a name="verify-managed-state-using-the-surface-app"></a>Verificar o estado gerenciado usando o aplicativo Surface

Depois de aplicar o pacote de configuração, você pode verificar rapidamente o estado da política resultante do Dock diretamente do aplicativo Surface, instalado por padrão em todos os dispositivos Surface. Se o aplicativo Surface não estiver presente no dispositivo, você poderá baixá-lo e instalá-lo na Microsoft Store.

###  <a name="test-scenario"></a>Cenário de teste

Objetivo: definir configurações de política para permitir o acesso às portas somente pelos usuários autenticados.

1. Ative todas as portas para usuários autenticados e desative-as para usuários não autenticados.

   ![Habilitando portas para usuários autenticados](images/secure-surface-dock-ports-semm-4.png)

1. Aplique o pacote de configuração ao seu dispositivo de destino e conecte o Surface Dock 2.

1. Abra o **aplicativo Surface** e selecione **Surface Dock** para ver o estado da política resultante do seu encaixe Surface. Se as configurações de política forem aplicadas, o aplicativo Surface indicará que as portas estão disponíveis.

   ![Aplicativo Surface mostra que todas as portas estão disponíveis para usuários autenticados](images/secure-surface-dock-ports-semm-5.png)

1. Agora, você precisa verificar se as configurações de política desativaram com êxito todas as portas de usuários não autenticados. Conecte o Dock Surface 2 a um dispositivo não gerenciado, ou seja, qualquer dispositivo Surface fora do escopo de gerenciamento do pacote de configuração que você criou.

1. Abra o **aplicativo Surface** e selecione **Surface Dock**. O estado da política resultante indicará que as portas estão desativadas.

   ![Aplicativo Surface mostrando portas desativadas para usuários não autenticados ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
>Se você quiser manter a propriedade do dispositivo, mas permitir que todos os usuários tenham acesso total, poderá criar um novo pacote com tudo ativado. Se quiser remover completamente as restrições e a propriedade do dispositivo (torná-lo não gerenciado), selecione **Redefinir** no configurador UEFI de Surface para criar um pacote para aplicar aos dispositivos de destino.

Parabéns. Você gerenciou com êxito as portas do Dock 2 em dispositivos host de destino.

##  <a name="learn-more"></a>Saiba mais

- [Documentação do modo de gerenciamento do Surface Enterprise (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [Arquitetura de serviços de certificado](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Segurança da PKI e do certificado do Windows Server 2008](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
