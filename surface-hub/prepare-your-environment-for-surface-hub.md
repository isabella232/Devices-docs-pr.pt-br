---
title: Preparar seu ambiente para o Microsoft Surface Hub (v1)
description: Esta seção contém uma visão geral das etapas necessárias para preparar o ambiente para que você possa usar todos os recursos do Microsoft Surface Hub.
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: preparar o ambiente, recursos do Surface Hub, criar e testar conta de dispositivo, verificar a disponibilidade da rede
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/04/2017
ms.localizationpriority: medium
appliesto:
- Surface Hub
ms.openlocfilehash: 95b575e5213e3e11685b342cb2a7b77eb3e868a0
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314394"
---
# Preparar seu ambiente para o Microsoft Surface Hub (v1)


Esta seção contém uma visão geral das dependências e do processo de configuração. Examine as informações nesta seção para ajudar a preparar o ambiente e coletar informações necessárias para configurar o Surface Hub.


## Examinar dependências de infraestrutura
Examine essas dependências para verificar se recursos do Surface Hub funcionarão na infraestrutura de TI.

| Dependência        | Finalidade           |
|-------------|------------------|
| Active Directory ou Azure Active Directory (Azure AD) | <p>O Surface Hub usa uma conta do Active Directory ou do Azure AD (chamada de **conta de dispositivo**) para acessar os serviços Exchange e Skype for Business. O Surface Hub deve ser capaz de se conectar ao controlador de domínio do Active Directory ou ao locatário do Azure AD para validar as credenciais da conta de dispositivo, bem como acessar informações, como o nome de exibição da conta de dispositivo, alias, Exchange Server e endereço com protocolo SIP.</p>Você também pode adicionar o domínio ou o Azure AD ao Surface Hub para permitir que um grupo de usuários autorizados definam configurações no Surface Hub. |
| Exchange (Exchange 2013 ou posteriores ou Exchange Online) e Exchange ActiveSync | <p>O Exchange é usado para habilitar os recursos de email e calendário e também permite que as pessoas que usam o dispositivo enviem solicitações de reunião para o Surface Hub, permitindo participar da reunião com um toque.</p>O ActiveSync é usado para sincronizar calendário e email da conta de dispositivo com o Surface Hub. Se o dispositivo não puder usar o ActiveSync, as reuniões não serão exibidas na tela de boas-vindas, e não será possível ingressar em reuniões e enviar quadros de comunicações por email. |
| Skype for Business (Lync Server 2013 ou posteriores, ou Skype for Business Online)  | O Skype for Business é usado por vários recursos de conferência, como chamadas de vídeo, mensagens instantâneas e compartilhamento de tela.|
| Solução de gerenciamento de dispositivo móvel (MDM) (Microsoft Intune, Microsoft Endpoint Configuration Manager ou provedor de MDM de terceiros com suporte) | Se você deseja aplicar configurações e instalar aplicativos remotamente, e a vários dispositivos de cada vez, instale uma solução MDM e registre o dispositivo nessa solução. Consulte [Gerenciar configurações usando um provedor MDM](manage-settings-with-mdm-for-surface-hub.md) para saber mais detalhes. |
| Microsoft Operations Management Suite (OMS)   | O OMS é usado para monitorar a integridade dos dispositivos do Surface Hub. Consulte [Monitorar o Surface Hub](monitor-surface-hub.md) para saber mais detalhes. |
| Acesso à rede e à Internet   | Para funcionar corretamente, o Surface Hub deve ter acesso a uma rede com ou sem fio. No geral, uma conexão com fio é preferencial. A autenticação 802.1X tem suporte para conexões com e sem fio.</br></br></br>**Autenticação 802.1X:** no Windows 10, versão 1703, a autenticação 802.1X para conexões com e sem fio está habilitada por padrão no Surface Hub. Se sua organização não usar autenticação 802.1 X, não há nenhuma configuração necessária e o Surface Hub continuará a funcionar normalmente. Se você usar autenticação 802.1 X, você deve garantir que a certificação de autenticação esteja instalada no Surface Hub. Você pode fornecer o certificado para o Surface Hub usando o [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) no MDM, ou você pode [criar um pacote de provisionamento](provisioning-packages-for-surface-hub.md) e instalá-lo durante a primeira execução ou por meio do aplicativo Configurações. Depois que o certificado for aplicado ao Surface Hub, autenticação 802.1 X começará a funcionar automaticamente.</br>**Observação:** para obter mais informações sobre como habilitar a autenticação 802.1X com fio no Surface Hub, consulte [Habilitar a autenticação 802.1x com fio](enable-8021x-wired-authentication.md).</br></br>**IP dinâmico:** O Surface Hub não pode ser configurado para usar um IP estático. Ele deve usar DHCP para atribuir um endereço IP.</br></br>**Servidores proxy:** Se a topologia exigir uma conexão com um servidor proxy para alcançar os serviços de Internet, você pode configurá-la durante a primeira execução, ou em Configurações. As credenciais do proxy são armazenadas em sessões do Surface Hub e só precisam ser definidas uma vez. |

Além disso, o Surface Hub requer que as seguintes portas estejam abertas:
- HTTPS: 443
- HTTP: 80
- NTP: 123

Se você estiver usando o Surface Hub com o Skype for Business, precisará abrir portas adicionais. Siga as orientações abaixo:
- Se você usa o Skype for Business Online, confira URLs IP e intervalos de [endereços IP do Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)
- Se você usar o Skype for Business Server, consulte Skype for Business Server: portas e [protocolos para servidores internos.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols) 
- Se você usar um híbrido do Skype for Business Online e do Skype for Business Server, precisará abrir todas as portas documentadas de URLs IP e intervalos de endereços IP do [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) e do [Skype for Business Server:](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)portas e protocolos para servidores internos.

A Microsoft coleta dados de diagnóstico para ajudar a melhorar a experiência do Surface Hub. Adicione esses sites à lista de permissões:
- Ponto de extremidade de cliente de dados de diagnóstico: `https://vortex.data.microsoft.com/`
- Ponto de extremidade de configurações de dados de diagnóstico: `https://settings.data.microsoft.com/`

### Configuração proxy

Caso a organização restrinja a conexão de computadores na rede com a Internet, há um conjunto de URLs que precisam estar disponíveis para dispositivos usarem a Microsoft Store para Empresas. Alguns dos recursos da Microsoft Store para Empresas usam o aplicativo da Microsoft Store e os serviços da Microsoft Store. Dispositivos que usam a Microsoft Store para Empresas – para adquirir, instalar, ou atualizar aplicativos – terão acesso a essas URLs. Se você usar um servidor proxy para bloquear o tráfego, a configuração precisará permitir estas URLs:

- login.live.com
- login.windows.net
- account.live.com
- clientconfig.passport.net
- windowsphone.com
- *.wns.windows.com
- *.microsoft.com
- www.msftncsi.com (antes do Windows 10, versão 1607)
- www.msftconnecttest.com/connecttest.txt (substitui www.msftncsi.com a partir do Windows 10, versão 1607)


## Trabalhar com outros administradores

O Surface Hub interage com alguns produtos e serviços diferentes. Dependendo do tamanho da organização, é possível que haja várias pessoas dando suporte a produtos diferentes no ambiente. Você desejará incluir pessoas que gerenciam o Exchange, o Active Directory (ou o Azure Active Directory), gerenciamento de dispositivo móvel (MDM) e recursos de rede no planejamento e na preparação para implantações do Surface Hub. 


## Criar e verificar conta de dispositivo

Uma conta de dispositivo é uma conta de recurso do Exchange que o Surface Hub usa para exibir o calendário de reuniões, participar de chamadas do Skype for Business, enviar e-mail e, como opção, autenticar para o Exchange. Veja [Criar e testar uma conta de dispositivo](create-and-test-a-device-account-surface-hub.md) para obter detalhes.

Depois que tiver criado sua conta de dispositivo, para verificar se ela está configurada corretamente, execute os scripts do PowerShell de validação de conta de dispositivo do Surface Hub. Para obter mais informações, consulte [scripts do PowerShell para o Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md) mais adiante neste guia. 

 

## Preparar-se para o programa de apresentação 
Existem mais alguns itens a serem considerados antes de você iniciar o [programa de apresentação](first-run-program-surface-hub.md).  

### Criar pacotes de provisionamento (opcional)
Você pode usar pacotes de provisionamento para adicionar certificados, personalizar configurações e instalar aplicativos. Veja [Criar pacotes de provisionamento](provisioning-packages-for-certificates-surface-hub.md) para obter detalhes. Você pode [instalar pacotes de provisionamento na apresentação](first-run-program-surface-hub.md#first-page).

### Configurar grupos de administradores
Cada Surface Hub pode ser configurado localmente usando-se o aplicativo Configurações no dispositivo. Para evitar que usuários não autorizados alterem configurações, o aplicativo Configurações requer credenciais de administrador para abrir o aplicativo. Veja [Gerenciamento de grupo de administração](admin-group-management-for-surface-hub.md) para obter detalhes sobre como os grupos de administração são configurados e gerenciados. Você irá [configurar administradores para o dispositivo na apresentação](first-run-program-surface-hub.md#setup-admins).

### Examinar e preencher planilha de configuração do Surface Hub (opcional)
Ao passar pelo programa de apresentação do Surface Hub, existem algumas informações que você precisará fornecer. A planilha de configuração resume essas informações e fornece listas de informações específicas do ambiente das quais você precisará ao passar pelo programa de apresentação. Para obter mais informações, consulte [Planilha de configuração](setup-worksheet-surface-hub.md).


## Nesta seção

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Tópico</th>
<th align="left">Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)">Criar e testar uma conta de dispositivo</a></p></td>
<td align="left"><p>Este tópico discute como criar e testar a conta de dispositivo que o Surface Hub usa para se comunicar com o Exchange e o Skype.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)">Criar pacotes de provisionamento</a></p></td>
<td align="left"><p>No Windows 10, os ajustes que usam o Registro ou uma plataforma de serviços de conteúdo (CSP) podem ser definidos por pacotes de provisionamento. Você também pode adicionar certificados durante a primeira execução usando o provisionamento.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)">Gerenciamento de grupo de administração</a></p></td>
<td align="left"><p>Cada Surface Hub pode ser configurado individualmente, abrindo o aplicativo Configurações no dispositivo. No entanto, para evitar que pessoas que não são administradores alterem as configurações, o aplicativo Configurações requer credenciais de administrador para abrir o aplicativo e alterar configurações.</p>
<p>O aplicativo Configurações requer credenciais de administrador local para abrir o aplicativo.</p></td>
</tr>
</tbody>
</table>

## Mais informações

- [Postagem do blog: Surface Hub e a lista de domínios confiáveis do Skype for Business](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [Postagem do blog: Surface Hub em um ambiente de vários domínios](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [Postagem do blog: Configuração de um proxy para o Surface Hub](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 





