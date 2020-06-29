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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830323"
---
# Como usar a Ferramenta de Diagnóstico de Hardware do Surface Hub para testar uma conta de dispositivo

## Introdução

> [!NOTE]
> A seção "configurações de conta" da ferramenta de diagnóstico de hardware do Surface Hub não coleta nenhuma informação. O email e a senha inseridos como entrada são usados apenas diretamente em seu ambiente e não são coletados ou transferidos para qualquer pessoa. As informações de logon persistem somente até que o aplicativo seja fechado ou que você encerre a sessão atual no Surface Hub.

> [!IMPORTANT]
> * Não é necessário ter privilégios de administrador para executar este aplicativo.
> * Os resultados do diagnóstico devem ser discutidos com o administrador local antes de você abrir uma chamada de serviço com a Microsoft.

### Diagnóstico de hardware do Surface Hub

Por padrão, o aplicativo de [diagnóstico de hardware do Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g) não está instalado em versões anteriores do sistema do Surface Hub. O aplicativo está disponível gratuitamente na Microsoft Store. É necessário ter privilégios de administrador para instalar o aplicativo.

   ![Captura de tela do diagnóstico de hardware](images/01-diagnostic.png)

## Sobre a ferramenta de diagnóstico de hardware do Surface Hub

A ferramenta de diagnóstico de hardware do Surface Hub é uma ferramenta fácil de navegar que permite que o usuário teste muitos dos componentes de hardware dentro do dispositivo do Surface Hub. Essa ferramenta também pode testar e verificar uma conta de dispositivo do Surface Hub. Este artigo descreve como usar o teste de configurações de conta dentro da ferramenta de diagnóstico de hardware do Surface Hub.

> [!NOTE]
> A conta de dispositivo do Surface hub deve ser criada antes de qualquer teste ser feito. O guia do administrador do Surface Hub fornece instruções e scripts do PowerShell para ajudá-lo a criar contas de dispositivos locais, online (Office365) ou híbridas. Para obter mais informações, vá para o tópico [criar e testar um tópico da conta do dispositivo (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) no guia.

### Processo de teste de conta do dispositivo

1. Navegue até **todos os aplicativos**e, em seguida, localize o aplicativo de diagnóstico de hardware do Surface Hub.

    ![Captura de tela de todos os aplicativos](images/02-all-apps.png)

1. Quando o aplicativo é iniciado, a página de **boas-vindas** fornece uma janela de texto para documentar o motivo pelo qual você está testando o Hub. Esta nota pode ser salva em USB em conjunto com os resultados do diagnóstico na conclusão do teste. Depois de terminar de inserir uma anotação, selecione o botão **continuar** .

    ![Captura de tela de boas-vindas](images/03-welcome.png)

1. A próxima tela fornece a opção para testar todos ou alguns dos componentes do Surface Hub. Para começar a testar a conta do dispositivo, selecione o ícone **resultados do teste** .

    ![Captura de tela dos resultados do teste](images/04-test-results-1.png)

    ![Captura de tela dos resultados do teste](images/05-test-results-2.png)

1. Selecione **configurações de conta**.  

    ![Captura de tela das configurações de conta](images/06-account-settings.png)

    A tela de configurações de conta é usada para testar sua conta de dispositivo.

    ![Captura de tela de detalhes das configurações de conta](images/07-account-settings-details.png)

1. Digite o endereço de email da sua conta de dispositivo. A senha é opcional, mas é recomendada. Selecione o botão **testar conta** quando estiver pronto para continuar.

    ![Captura de tela da conta de teste](images/08-test-account.png)

1. Depois de concluir o teste, examine os resultados das quatro áreas de teste. Cada seção pode ser expandida ou recolhida selecionando o sinal de mais ou de menos ao lado de cada tópico.

    **Rede**

    ![Captura de tela da rede](images/09-network.png)

    **Ambiente**

    ![Captura de tela do ambiente](images/10-environment.png)

    **Certificados**

    ![Captura de tela de certificados](images/11-certificates.png)

    **Modelo de confiança**

    ![Captura de tela do modelo de confiança](images/12-trust-model.png)

## Apêndice

### Mensagens de campo e resolução

#### Rede

Campo |Sucesso |Falha |Comentário |Referência
|------|------|------|------|------|
Conectividade com a Internet |O dispositivo tem conectividade com a Internet |O dispositivo não tem conexão à Internet |Verifica a conectividade com a Internet, incluindo conexão proxy |
Versão HTTP |1,1 |1.0 |Se HTTP 1,0 encontrado, isso causará problemas com o WU e a loja |
Conectividade à Internet direta |O dispositivo tem um dispositivo configurado por proxy não tem proxy configurado |N/A |Informativos. O seu dispositivo está atrás de um proxy? |
Endereço de proxy | | |Se configurado, retorna o endereço proxy. |
Autenticação de proxy |O proxy não requer autenticação |Proxy requer autenticação de proxy |O resultado pode ser um falso positivo se um usuário já tiver uma sessão aberta no Edge e autenticado por meio do proxy. |
Tipos de autenticação de proxy | | |Se a autenticação de proxy for usada, retorne os métodos de autenticação anunciados pelo proxy.  |

#### Ambiente

Campo |Sucesso |Falha |Comentário |Referência
|------|------|------|------|------|
Domínio SIP | | |Informativos.  |
Ambiente do Skype |Skype for Business Online, Skype for Business local, Skype for Business híbrido |Informativos. |Que tipo de ambiente foi detectado. Observação: híbrido só poderá ser detectado se a senha for inserida.
LyncDiscover FQDN | | |Informativos. Exibe o resultado do DNS LyncDiscover |
URI LyncDiscover | | |Informativos. Exibe a URL usada para executar um LyncDiscover no seu ambiente.|
LyncDiscover |Conexão bem-sucedida |Falha na conexão |Resposta do serviço Web LyncDiscover. |
Nome do host do pool SIP | | |Informativos. Exibir o nome do pool SIP descoberto em LyncDiscover |

#### Certificados (somente híbridas locais)

Certificado LyncDiscover

Campo |Sucesso |Falha |Comentário |Referência
|------|------|------|------|------|
CN do certificado LyncDiscover | | |Informativos. Exibe o nome comum do CERT de LD |
CA LyncDiscover CERT | | |Informativos. Exibe a CA de CERT de LD |
CA raiz do certificado LyncDiscover | | |Informativos. Exibe a CA raiz do CERT de LD, se disponível. |
LD status de confiança |Certificado é confiável. |O certificado não é confiável; adicione a CA raiz. |Verifique o certificado em relação ao repositório de certificados local. Retorna positivo se o computador confiar no certificado.|[Baixar e implantar certificados do Skype for Business usando o PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Itens com suporte para pacotes de provisionamento do Surface Hub](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

Certificação de pool SIP

Campo |Sucesso |Falha |Comentário |Referência
|------|------|------|------|------|
CN do certificado do pool SIP | | |CONTEÚDOS |
CA do certificado do pool SIP | | |CONTEÚDOS |
Status de confiança do pool SIP |Certificado é confiável. |O certificado não é confiável; adicione a CA raiz. |Verifique o certificado em relação ao repositório de certificados local e retorne um positivo se os dispositivos confiarem no certificado. |
CA raiz do certificado do pool SIP | | |Às. Exiba a CA raiz do certificado do pool SIP, se disponível. |

#### Modelo de confiança (somente híbrido local)

Campo |Sucesso |Falha |Comentário |Referência
|------|------|------|------|------|
Status do modelo de confiança |Nenhum problema de modelo de confiança detectado. |O domínio SIP e o domínio do servidor são diferentes, adicione os domínios a seguir. |Verifique o nome do servidor FQDN FQDN/LD nome do servidor/pool para o problema de modelo de confiança. 
Nome (s) de domínio | | |Retorne a lista de domínios que devem ser adicionados para que o SFB se conecte. |
