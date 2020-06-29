---
title: Habilitar autenticação com fio 802.1x
description: As políticas do MDM de Autenticação com Fio 802.1x têm sido habilitadas em dispositivos Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830665"
---
# <span data-ttu-id="8e0d3-103">Habilitar autenticação com fio 802.1x</span><span class="sxs-lookup"><span data-stu-id="8e0d3-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="8e0d3-104">A [atualização de 14 de novembro de 2017 para o Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) habilita políticas de MDM de autenticação 802.1x com fio em dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="8e0d3-105">O recurso permite que as organizações forcem a autenticação de rede com fio padronizada usando o [protocolo de autenticação IEEE 802.1x](http://www.ieee802.org/1/pages/802.1x-2010.html).</span><span class="sxs-lookup"><span data-stu-id="8e0d3-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="8e0d3-106">Isso já está disponível para autenticação sem fio usando perfis WLAN via MDM.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="8e0d3-107">Este tópico explica como configurar um Surface Hub para uso com autenticação com fio.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="8e0d3-108">A imposição e a habilitação de autenticação 802.1x com fio no Surface Hub podem ser feitas por meio de MDM [definição OMA-URI](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span><span class="sxs-lookup"><span data-stu-id="8e0d3-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="8e0d3-109">A configuração principal a ser definida é a política **LanProfile**.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="8e0d3-110">Dependendo do método de autenticação selecionado, outras políticas talvez seja necessárias, ou a política **EapUserData** ou por meio de políticas de MDM para adicionar certificados de usuário ou de computador (como [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) para certificados de usuário/dispositivo ou [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) para certificados de dispositivo).</span><span class="sxs-lookup"><span data-stu-id="8e0d3-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="8e0d3-111">Elemento de política LanProfile</span><span class="sxs-lookup"><span data-stu-id="8e0d3-111">LanProfile policy element</span></span>

<span data-ttu-id="8e0d3-112">Para configurar o Surface Hub para usar um dos métodos de autenticação 802.1 com suporte, utilize o OMA-URI a seguir.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="8e0d3-113">Esse nó OMA-URI aceita uma cadeia de caracteres de texto de XML como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="8e0d3-114">O XML fornecido como um parâmetro deve estar em conformidade com o [Esquema de perfil de LAN com fio](https://msdn.microsoft.com/library/cc233002.aspx), incluindo elementos do [esquema 802.1X](https://msdn.microsoft.com/library/cc233003.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e0d3-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="8e0d3-115">Na maioria dos casos, um administrador ou um usuário pode exportar o XML de LanProfile de um computador existente que já esteja configurado na rede para 802.1X usando este comando NETSH a seguir.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="8e0d3-116">Executar esse comando oferecerá a seguinte saída e posicionará um arquivo chamado **Ethernet.xml** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="8e0d3-117">Elemento de política EapUserData</span><span class="sxs-lookup"><span data-stu-id="8e0d3-117">EapUserData policy element</span></span>

<span data-ttu-id="8e0d3-118">Se seu método de autenticação selecionado exigir um nome de usuário e uma senha em oposição a um certificado, você poderá usar o elemento **EapUserData** para especificar as credenciais para o dispositivo a ser usado para autenticação na rede.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="8e0d3-119">Esse nó OMA-URI aceita uma cadeia de caracteres de texto de XML como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="8e0d3-120">O XML fornecido como um parâmetro deve estar em conformidade com o [exemplo de Propriedades de Usuário de MS-CHAPv2 PEAP](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span><span class="sxs-lookup"><span data-stu-id="8e0d3-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="8e0d3-121">No exemplo, você precisará substituir todas as instâncias de *test* e *ias-domain* com suas informações.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="8e0d3-122">Adição de certificados</span><span class="sxs-lookup"><span data-stu-id="8e0d3-122">Adding certificates</span></span>

<span data-ttu-id="8e0d3-123">Se o seu método de autenticação selecionado for baseado em certificado, você precisará [criar um pacote de provisionamento](provisioning-packages-for-surface-hub.md), [usar o MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)ou importar um certificado de configurações (atualização de**configurações**  >  **e**  >  **certificados**de segurança) para implantar esses certificados em seu dispositivo do Surface Hub no repositório de certificados apropriado.</span><span class="sxs-lookup"><span data-stu-id="8e0d3-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="8e0d3-124">Ao adicionar certificados, cada PFX deve conter apenas um certificado (um PFX não pode ter vários certificados).</span><span class="sxs-lookup"><span data-stu-id="8e0d3-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>

