---
title: Como usar a Ferramenta de Diagnóstico de Hardware do Surface Hub para testar uma conta de dispositivo
description: Como usar a Ferramenta de Diagnóstico de Hardware do Surface Hub para testar uma conta de dispositivo
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: Ajustes de acessibilidade, aplicativo Configurações, Facilidade de Acesso
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 0a9914f5c07a33306cc8a3ef87de85df47a05a20
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911426"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a>Como usar a Ferramenta de Diagnóstico de Hardware do Surface Hub para testar uma conta de dispositivo

## <a name="introduction"></a>Introdução

> [!NOTE]
> A seção "Conta Configurações" da ferramenta Surface Hub Hardware Diagnostic não coleta informações. O email e a senha inseridos como entrada são usados diretamente em seu ambiente e não coletados ou transferidos para qualquer pessoa. As informações de logon persistem apenas até que o aplicativo seja fechado ou você termine a sessão atual no Surface Hub.

> [!IMPORTANT]
> * Os privilégios de administrador não são necessários para executar esse aplicativo.
> * Os resultados do diagnóstico devem ser discutidos com o administrador local antes de abrir uma chamada de serviço com a Microsoft.

### <a name="surface-hub-hardware-diagnostic"></a>Surface Hub Diagnóstico de Hardware

Por padrão, o [Surface Hub de Diagnóstico](https://www.microsoft.com/store/apps/9nblggh51f2g) de Hardware não está instalado em versões anteriores do Surface Hub sistema. O aplicativo está disponível gratuitamente no Microsoft Store. Os privilégios de administrador são necessários para instalar o aplicativo.

   ![Captura de tela do Diagnóstico de Hardware.](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a>Sobre a Surface Hub de Diagnóstico de Hardware

A Surface Hub de Diagnóstico de Hardware é uma ferramenta fácil de navegar que permite ao usuário testar muitos dos componentes de hardware dentro do dispositivo Surface Hub. Essa ferramenta também pode testar e verificar uma conta Surface Hub dispositivo. Este artigo descreve como usar o teste account Configurações na ferramenta Surface Hub Hardware Diagnostic.

> [!NOTE]
> A conta do dispositivo para o Surface Hub deve ser criada antes que qualquer teste seja feito. O Surface Hub Guia de Administradores fornece instruções e scripts do PowerShell para ajudá-lo a criar contas de dispositivo local, online (Office365) ou híbridas. Para obter mais informações, acesse o tópico Criar e testar uma conta de dispositivo [(Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) no guia.

### <a name="device-account-testing-process"></a>Processo de teste de conta de dispositivo

1. Navegue **até Todos os Aplicativos**e localize o Surface Hub de Diagnóstico de Hardware.

    ![Captura de tela de Todos os Aplicativos.](images/02-all-apps.png)

1. Quando o aplicativo é iniciado, a página **De** boas-vindas fornece uma janela de texto para documentar o motivo pelo qual você está testando o Hub. Essa observação pode ser salva em USB juntamente com os resultados de diagnóstico na conclusão do teste. Depois de concluir a inserção de uma nota, selecione o **botão Continuar.**

    >[!NOTE]
    >Ao salvar resultados de diagnóstico, não altere o caminho padrão ou selecione um subdiretório. Os arquivos podem ser copiados posteriormente por meio do aplicativo Explorador de Arquivos.

    ![Captura de tela de Boas-vindas.](images/03-welcome.png)

1. A próxima tela oferece a opção de testar todos ou alguns dos componentes Surface Hub. Para começar a testar a conta do dispositivo, selecione o **ícone Resultados de** Teste.

    ![Captura de tela das opções de teste.](images/04-test-results-1.png)

    ![Captura de tela dos resultados do teste.](images/05-test-results-2.png)

1. Selecione **Conta Configurações**.  

    ![Captura de tela do account Configurações.](images/06-account-settings.png)

    A tela Configurações conta é usada para testar sua conta de dispositivo.

    ![Captura de tela de Detalhes Configurações Conta.](images/07-account-settings-details.png)

1. Insira o endereço de email da sua conta de dispositivo. A senha é opcional, mas recomendada. Selecione o **botão Testar Conta** quando estiver pronto para continuar.

    ![Captura de tela da Conta de Teste.](images/08-test-account.png)

1. Depois que o teste for concluído, revise os resultados das quatro áreas de teste. Cada seção pode ser expandida ou colapsada selecionando o sinal Mais ou Menos ao lado de cada tópico.

    **Rede**

    ![Captura de tela de Rede.](images/09-network.png)

    **Ambiente**

    ![Captura de tela do Ambiente.](images/10-environment.png)

    **Certificates**

    ![Captura de tela de certificados.](images/11-certificates.png)

    **Modelo de confiança**

    ![Captura de tela do Modelo de Confiança.](images/12-trust-model.png)

## <a name="appendix"></a>Apêndice

### <a name="field-messages-and-resolution"></a>Mensagens de campo e resolução

#### <a name="network"></a>Rede

Campo |Êxito |Falha |Comentário |Referência
|------|------|------|------|------|
Conectividade com a Internet |O dispositivo tem conectividade com a Internet |O dispositivo não tem conectividade com a Internet |Verifica a conectividade com a Internet, incluindo a conexão de proxy |
Versão HTTP |1.1 |1.0 |Se HTTP 1.0 encontrado, ele causará problemas com WU e Store |
Conectividade direta com a Internet |O dispositivo tem um Dispositivo configurado por Proxy que não tem Proxy configurado |N/D |Informações. Seu dispositivo está atrás de um proxy? |
Endereço proxy | | |Se configurado, retorna o endereço proxy. |
Autenticação proxy |Proxy não exige Autenticação |Proxy requer Proxy Auth |O resultado pode ser um falso positivo se um usuário já tiver uma sessão aberta no Edge e tiver autenticado por meio do proxy. |
Tipos de Proxy Auth | | |Se a autenticação de proxy for usada, retorne os métodos de autenticação anunciados pelo proxy.  |

#### <a name="environment"></a>Ambiente

Campo |Êxito |Falha |Comentário |Referência
|------|------|------|------|------|
Domínio SIP | | |Informações.  |
Skype Ambiente |Skype for Business Online, Skype for Business OnPrem, Skype for Business Híbrido |Informações. |Que tipo de ambiente foi detectado. Observação: híbrida só poderá ser detectada se a senha for inserida.
LyncDiscover FQDN | | |Informações. Exibe o resultado dns do LyncDiscover |
LyncDiscover URI | | |Informações. Exibe a URL usada para executar um LyncDiscover em seu ambiente.|
LyncDiscover |Conexão bem-sucedida |Falha na conexão |Resposta do serviço Web do LyncDiscover. |
SIP Pool Hostname | | |Informações. Exibir o nome do pool SIP descoberto a partir do LyncDiscover |

#### <a name="certificates-in-premises-hybrid-only"></a>Certificados (somente híbridos locais)

Certificado LyncDiscover

Campo |Êxito |Falha |Comentário |Referência
|------|------|------|------|------|
LyncDiscover Cert CN | | |Informações. Exibe o nome comum do certificado LD |
LyncDiscover Cert CA | | |Informações. Exibe a LD Cert CA |
CA raiz do Certificado de Descoberta do LyncDiscover | | |Informações. Exibe a CA raiz do Certificado LD, se disponível. |
Status de confiança LD |O certificado é Confiável. |O certificado não é confiável, adicione a AC Raiz. |Verifique o certificado no armazenamento de certificados local. Retorna positivo se o computador confiar no certificado.|[Baixar e implantar Skype for Business certificados usando o PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Itens com suporte para Surface Hub de provisionamento](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

Certificação sip pool

Campo |Êxito |Falha |Comentário |Referência
|------|------|------|------|------|
SIP Pool Cert CN | | |(CONTENTS) |
SIP Pool Cert CA | | |(CONTENTS) |
Status de confiança do pool SIP |O certificado é Confiável. |O certificado não é confiável, adicione a AC Raiz. |Verifique o certificado no armazenamento de certificados local e retorne um positivo se os dispositivos confiarem no certificado. |
SIP Pool Cert Root CA | | |Informações. Exibe a CA Raiz do Certificado do Pool SIP, se disponível. |

#### <a name="trust-model-on-premises-hybrid-only"></a>Modelo de confiança (somente híbrida local)

Campo |Êxito |Falha |Comentário |Referência
|------|------|------|------|------|
Status do modelo de confiança |Nenhum problema de modelo de confiança detectado. |Domínio SIP e domínio de servidor são diferentes, adicione os seguintes domínios. |Verifique o nome do servidor LD FQDN/LD Server Name/Pool para problemas de modelo de confiança. 
Nome(s) de domínio | | |Retorne a lista de domínios que devem ser adicionados para que o SFB se conecte. |
