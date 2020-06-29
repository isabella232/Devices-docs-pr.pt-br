---
title: Instalar aplicativos no Microsoft Surface Hub
description: Os administradores podem instalar aplicativos da Microsoft Store ou da Microsoft Store para Empresas.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: instalar aplicativos, Microsoft Store, Microsoft Store para Empresas
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 462b76451bd12547d1c1560054a51bb88c218f96
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830547"
---
# Instalar aplicativos no Microsoft Surface Hub

Você pode instalar aplicativos adicionais em seu Surface Hub para atender às necessidades de sua equipe ou organização. Há métodos diferentes para instalar aplicativos dependendo se você estiver desenvolvendo e testando um aplicativo ou implantando um aplicativo lançado. Este tópico descreve métodos de instalação de aplicativos para qualquer um desses cenários.

Alguns pontos a saber sobre aplicativos no Surface Hub:
- O Surface Hub executa apenas [aplicativos da Plataforma Universal do Windows (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp). Os aplicativos criados usando o [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) não serão executados no Surface Hub.
- Os aplicativos devem ser voltados para a [família de dispositivos universais](https://msdn.microsoft.com/library/windows/apps/dn894631) ou família de dispositivos da Equipe do Windows.
- O Surface hub só dá suporte [a aplicativos licenciados offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) da [Microsoft Store para empresas](https://businessstore.microsoft.com/store).
- Por padrão, os aplicativos devem ser assinados pela Microsoft Store para serem instalados. Durante o processo de teste e desenvolvimento, você também pode optar por executar os aplicativos UWP assinados pelo desenvolvedor colocando o dispositivo no modo de desenvolvedor.
- Ao enviar um aplicativo para a Microsoft Store, os desenvolvedores precisam definir a disponibilidade da família de dispositivos e as opções de licenciamento organizacional para garantir que um aplicativo estará disponível para ser executado no Surface Hub.
- Você precisa de credenciais de administrador para instalar aplicativos no Surface Hub. Como o dispositivo foi projetado para ser usado em espaços públicos, como salas de reunião, as pessoas não podem acessar a Microsoft Store para baixar e instalar aplicativos.


## Desenvolver e testar aplicativos
Enquanto você estiver desenvolvendo seu próprio aplicativo, há algumas opções para testar aplicativos no Surface Hub.

### Modo de Desenvolvedor
Por padrão, o Surface Hub só executa aplicativos UWP que foram publicados e assinados pela Microsoft Store. Os aplicativos enviados à Microsoft Store passam por testes de segurança e conformidade como parte do [processo de certificação de aplicativo](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process); portanto, isso ajuda a proteger o Surface Hub contra aplicativos mal-intencionados.
 
Habilitando o modo de desenvolvedor, você também pode instalar aplicativos UWP assinados pelo desenvolvedor.
 
> [!IMPORTANT]
> Após a habilitação do modo de desenvolvedor, você precisará redefinir o Surface Hub para desativá-lo. Redefinir o dispositivo remove todas as configurações e arquivos de usuário local e reinstala o Windows.

**Para ativar o modo de desenvolvedor** 
1. No Surface Hub, inicie **Configurações**.
2. Digite as credenciais de administrador de dispositivo quando solicitado.
3. Navegue até **Atualização e segurança** > **Para desenvolvedores**.
4. Selecione **Modo de desenvolvedor** e aceite o prompt de aviso.

### Visual Studio
Durante o desenvolvimento, a maneira mais fácil de testar seu aplicativo em um Surface Hub é usando o Visual Studio. Recurso de depuração remota do Visual Studio ajuda você a descobrir problemas em seu aplicativo antes de implantá-lo amplamente. Para obter mais informações, consulte [Testar aplicativos Surface Hub usando o Visual Studio](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).

### Pacote de provisionamento
Use o Visual Studio para [criar um pacote do aplicativo](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx) para seu aplicativo UWP, assinado com um certificado de teste. Use o ICD (Designer de Configuração e Imagens do Windows) para criar um pacote de provisionamento que contenha o pacote do aplicativo. Para obter mais informações, consulte [Criar pacotes de provisionamento](provisioning-packages-for-certificates-surface-hub.md).


## Enviar aplicativos para a Microsoft Store
Quando um aplicativo estiver pronto para ser lançado, os desenvolvedores precisarão enviá-lo e publicá-lo na Microsoft Store. Para obter mais informações, consulte [Publicar aplicativos do Windows](https://developer.microsoft.com/store/publish-apps).

Durante o envio do aplicativo, os desenvolvedores precisam definir as opções de **Disponibilidade da família de dispositivos** e **Licenciamento organizacional** para garantir que o aplicativo esteja disponível para execução no Surface Hub.

**Para definir a disponibilidade da família de dispositivos**  
1. No [Centro de Desenvolvimento do Windows](https://developer.microsoft.com), navegue até a página de envio de aplicativo.
2. Selecione **Pacotes**.
3. Em **Disponibilidade da família de dispositivos**, selecione estas opções:
    
    - **Windows 10 Team**
    - **Permitir que a Microsoft decida se deseja disponibilizar este aplicativo para futuras famílias de dispositivos**
  
![Imagem mostrando a página Disponibilidade da família de dispositivos – parte do processo de envio de aplicativo da Microsoft Store.](images/device-family.png)  
    
Para obter mais informações, consulte [Disponibilidade da família de dispositivos](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability).

**Para definir o licenciamento organizacional**
1. No [Centro de Desenvolvimento do Windows](https://developer.microsoft.com), navegue até a página de envio de aplicativo.
2. Selecione **Preço e disponibilidade**.
3. Em Licenciamento organizacional, selecione **Allow disconnected (offline) licensing for organizations**.

![Imagem mostrando a página Licenciamento organizacional – parte do processo de envio de aplicativo da Microsoft Store.](images/sh-org-licensing.png)

> [!NOTE]
> **Tornar meu aplicativo disponível para organizações com licenciamento por volume gerenciado pela Microsoft Store (online)** é selecionado por padrão.

> [!NOTE]
> Os desenvolvedores também podem publicar aplicativos de linha de negócios diretamente para empresas sem torná-los amplamente disponíveis na Microsoft Store. Para obter mais informações, consulte [Distribuir aplicativos LOB para empresas](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises).

Para obter mais informações, consulte [Opções de licenciamento organizacional](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing).


## Implantar aplicativos lançados

Há várias opções para instalar aplicativos que foram lançados na Microsoft Store, dependendo se você deseja avaliá-los em alguns dispositivos ou implantá-los amplamente em sua organização.

Para instalar aplicativos lançados:
- Baixe o aplicativo usando o aplicativo da Microsoft Store ou
- Baixe o pacote do aplicativo na Microsoft Store para Empresas e distribua-o usando um pacote de provisionamento ou um provedor MDM com suporte.

### Aplicativo da Microsoft Store
Para avaliar aplicativos lançados na Microsoft Store, use o aplicativo da Microsoft Store no Surface Hub para procurar e baixar aplicativos.

> [!NOTE]
> Usar o aplicativo da Microsoft Store não é o método recomendado de implantação de aplicativos em escala em sua organização:
> - Para baixar aplicativos, você deve entrar no aplicativo da Microsoft Store com uma conta da Microsoft ou organizacional. No entanto, você só pode conectar uma conta a no máximo 10 dispositivos por vez. Se você tiver mais de 10 Surface Hubs, precisará criar várias contas ou remover dispositivos de sua conta entre as instalações do aplicativo.
> - Para instalar aplicativos, você precisará entrar manualmente no aplicativo da Microsoft Store em cada Surface Hub de sua propriedade.

**Para procurar a Microsoft Store no Surface Hub** 
1. No Surface Hub, inicie **Configurações**.
2. Digite as credenciais de administrador de dispositivo quando solicitado.
3. Navegue até **Este dispositivo** > **Aplicativos e recursos**.
4. Selecione **Abrir Microsoft Store**.

### Baixar pacotes de aplicativos da Microsoft Store para Empresas
Para baixar o pacote de aplicativos que você precisa instalar no Surface Hub, acesse a [Microsoft Store para Empresas](https://www.microsoft.com/business-store). A Windows Store para Empresas é onde você pode encontrar, adquirir e gerenciar aplicativos para os dispositivos Windows 10 em sua organização, incluindo o Surface Hub.
 
> [!NOTE]
> Atualmente, o Surface Hub dá suporte apenas para aplicativos licenciados offline disponibilizados pela Windows Store para Empresas. Os desenvolvedores de aplicativos definem disponibilidade da licença offline quando enviam os aplicativos.

Encontre e adquira o aplicativo desejado e baixe:
- O pacote do aplicativo licenciado offline (.appx ou .appxbundle)
- O arquivo de licença *decodificado* (se você estiver usando pacotes de provisionamento para instalar o aplicativo)
- O arquivo de licença *codificado* (se você estiver usando o MDM para distribuir o aplicativo)
- Todos os arquivos de dependência necessários

Para obter mais informações, consulte [Baixar um aplicativo licenciado offline](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

### Pacote de provisionamento
Você pode instalar manualmente os aplicativos licenciados offline que você baixou da Windows Store para Empresas em alguns Surface Hubs usando pacotes de provisionamento. Use o ICD (Designer de Configuração e Imagens do Windows) para criar um pacote de provisionamento que contenha o pacote do aplicativo e o arquivo de licença *decodificado* que você baixou da Windows Store para Empresas. Para obter mais informações, consulte [Criar pacotes de provisionamento](provisioning-packages-for-certificates-surface-hub.md).

### Provedor de MDM com suporte
Para implantar aplicativos em um grande número de Surface Hubs em sua organização, use um provedor de MDM com suporte. A tabela a seguir mostra quais provedores de MDM dão suporte à implantação de pacotes de aplicativos licenciados offline.

| Provedor de MDM                | Dá suporte para pacotes de aplicativos licenciados offline |
|-----------------------------|----------------------------------------|
| MDM local com o Configuration Manager (início na versão 1602) | Sim |
|
| Provedor de MDM de terceiros    | Verifique se seu provedor de MDM dá suporte à implantação de pacotes de aplicativos licenciados offline. |

**Implantar aplicativos remotamente usando o Gerenciador de configuração do Microsoft Endpoint**

> [!NOTE]
> Essas instruções se baseiam na ramificação atual do Gerenciador de configuração do Microsoft Endpoint.

1. Registre seus hubs de Surface no Configuration Manager. Para obter mais informações, consulte [Registrar um Surface Hub em MDM](manage-settings-with-mdm-for-surface-hub.md#enroll-into-mdm).
2. Baixe o pacote de aplicativos licenciados offline, o arquivo de licença *codificado* e os arquivos de dependência necessários da Windows Store para Empresas. Para obter mais informações, consulte [Baixar um aplicativo licenciado offline](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app). Coloque os arquivos baixados na mesma pasta em um compartilhamento de rede.
3. No espaço de trabalho **Biblioteca de Software** do console do Configuration Manager, clique em **Visão Geral** > **Gerenciamento de Aplicativos** > **Aplicativos**.
4. Na guia **Página Inicial**, no grupo **Criar**, clique em **Criar Aplicativo**.
5. Na página **Geral** do **Assistente para Criar Aplicativo**, marque a caixa de seleção **Detectar automaticamente informações sobre este aplicativo em arquivos de instalação**.
6. Na lista suspensa **Tipo**, selecione **Pacote de aplicativo do Windows (*.appx, *.appxbundle)**.
7. No campo **Local**, especifique o caminho UNC no formato \\servidor\compartilhamento\\nome_do_arquivo do pacote do aplicativo licenciado offline que você baixou da Windows Store para Empresas. Você também pode clicar em **Procurar** para navegar até o pacote do aplicativo.
8. Na página **Importar Informações**, examine as informações que foram importadas e clique em **Avançar**. Se necessário, você pode clicar em **Anterior** para voltar e corrigir os erros.
9. Na página **Informações Gerais**, preencha os detalhes adicionais sobre o aplicativo. Algumas dessas informações já podem estar preenchidas se foram obtidas automaticamente do pacote do aplicativo.
10. Clique em **Avançar**, revise as informações do aplicativo na página Resumo e conclua o Assistente para Criar Aplicativo. 
11. Crie um tipo de implantação para o aplicativo. Para obter mais informações, consulte [Criar tipos de implantação para o aplicativo](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application).
12. Implante o aplicativo em seus Surface Hubs. Para obter mais informações, consulte [implantar aplicativos com o Gerenciador de configuração do Microsoft Endpoint](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications).
13. Conforme necessário, atualize o aplicativo baixando um novo pacote da Windows Store para Empresas e publicando uma revisão do aplicativo no Configuration Manager. Para obter mais informações, consulte [atualizar e remover aplicativos usando o Gerenciador de configuração do Microsoft Endpoint](https://technet.microsoft.com/library/mt595704.aspx). 

> [!NOTE] 
> Se você estiver usando o Gerenciador de configuração do Microsoft EndPoint (ramificação atual), poderá ignorar as etapas acima conectando a loja de negócios ao Configuration Manager. Fazendo isso, você pode sincronizar a lista de aplicativos que comprou com o Configuration Manager, exibi-los no console do Configuration Manager e implantá-los como faria com qualquer outro aplicativo. Para obter mais informações, consulte [gerenciar aplicativos da Microsoft Store para empresas com o Configuration Manager](https://technet.microsoft.com/library/mt740630.aspx).


## Resumo

Há algumas maneiras diferentes de instalar aplicativos no Surface Hub, dependendo se você estiver desenvolvendo aplicativos, avaliando aplicativos em um pequeno número de dispositivos ou implantando aplicativos amplamente em sua organização. Esta tabela resume os métodos com suporte:

| Método de instalação             | Desenvolver aplicativos | Avaliar aplicativos em <br> alguns dispositivos | Implantar aplicativos amplamente <br> em sua organização |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| Pacote de provisionamento       | X | X |   |
| Aplicativo da Microsoft Store          |   | X |   |
| Provedor de MDM com suporte     |   |   | X |

## Mais informações

- [Postagem do blog: Implantar aplicativos da Windows Store no Surface Hub usando o Intune](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## Tópicos relacionados

[Gerenciar o Microsoft Surface Hub](manage-surface-hub.md)

[Guia do administrador do Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





