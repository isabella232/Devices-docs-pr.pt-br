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
ms.openlocfilehash: dcb2799accfcbccb41e44e09f0df3fd1ac6eb57e
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154036"
---
# <a name="enable-8021x-wired-authentication"></a>Habilitar autenticação com fio 802.1x

A atualização de 14 de novembro de [2017](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) para o Windows 10 (build 15063.726) habilitada para políticas MDM de autenticação com fio 802,1x em dispositivos Surface Hub. O recurso permite que as organizações forcem a autenticação de rede com fio padronizada usando o [protocolo de autenticação IEEE 802.1x](http://www.ieee802.org/1/pages/802.1x-2010.html). Isso já estava disponível para autenticação sem fio usando [perfis WLAN](/mem/intune/configuration/wi-fi-settings-import-windows-8-1) via MDM. Este tópico explica como configurar um Surface Hub para uso com autenticação com fio. 

A imposição e a habilitação de autenticação 802.1x com fio no Surface Hub podem ser feitas por meio de MDM [definição OMA-URI](/mem/intune/configuration/custom-settings-windows-10). 

A configuração principal a ser definida é a política **LanProfile**. Dependendo do método de autenticação selecionado, outras políticas talvez seja necessárias, ou a política **EapUserData** ou por meio de políticas de MDM para adicionar certificados de usuário ou de computador (como [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) para certificados de usuário/dispositivo ou [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) para certificados de dispositivo). 

## <a name="lanprofile-policy-element"></a>Elemento de política LanProfile

Para configurar o Surface Hub para usar um dos métodos de autenticação 802.1 com suporte, utilize o OMA-URI a seguir. 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

Esse nó OMA-URI aceita uma cadeia de caracteres de texto de XML como um parâmetro. O XML fornecido como um parâmetro deve estar em conformidade com o [Esquema de perfil de LAN com fio](/openspecs/windows_protocols/ms-gpwl/c88a926a-087b-405f-9a76-effaf7277bf3), incluindo elementos do [esquema 802.1X](/openspecs/windows_protocols/ms-gpwl/71f2eda6-d018-4ba3-ad37-32c98b926ebb). 

Na maioria dos casos, um administrador ou um usuário pode exportar o XML de LanProfile de um computador existente que já esteja configurado na rede para 802.1X usando este comando NETSH a seguir. 

```
netsh lan export profile folder=.
```

Executar esse comando oferecerá a seguinte saída e posicionará um arquivo chamado **Ethernet.xml** no diretório atual. 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <a name="eapuserdata-policy-element"></a>Elemento de política EapUserData

Se seu método de autenticação selecionado exigir um nome de usuário e uma senha em oposição a um certificado, você poderá usar o elemento **EapUserData** para especificar as credenciais para o dispositivo a ser usado para autenticação na rede. 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

Esse nó OMA-URI aceita uma cadeia de caracteres de texto de XML como um parâmetro. O XML fornecido como um parâmetro deve estar em conformidade com o [exemplo de Propriedades de Usuário de MS-CHAPv2 PEAP](/windows/win32/eaphost/peap-ms-chapv2-user-properties). No exemplo, você precisará substituir todas as instâncias de *test* e *ias-domain* com suas informações.



## <a name="adding-certificates"></a>Adição de certificados

Se o método de autenticação selecionado for baseado em certificados, você precisará criar um pacote de [provisionamento,](provisioning-packages-for-surface-hub.md)utilizar [o MDM](/windows/client-management/mdm/clientcertificateinstall-csp)ou importar um certificado de configurações (**Configurações certificados**de atualização e segurança ) para implantar esses certificados em seu dispositivo Surface Hub no Armazenamento de  >  ****  >  **Certificados**apropriado. Ao adicionar certificados, cada PFX deve conter apenas um certificado (um PFX não pode ter vários certificados).

