---
title: 'Problemas conhecidos: Surface Hub'
description: Esta página fornece uma lista de problemas conhecidos para Surface Hubs
keywords: separar os valores com vírgulas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/09/2021
ms.localizationpriority: Medium
ms.openlocfilehash: a9435db1de48b33d062d5e79d0d622f1d17815f0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497481"
---
# <a name="known-issues-surface-hub"></a>Problemas conhecidos: Surface Hub

Este artigo lista os problemas conhecidos dos Surface Hubs que executam o sistema operacional atual, Windows 10 Team Atualização 2020.

Para garantir Surface Hub receba as atualizações mais recentes, **** >  entre com uma conta de administrador e selecione Todos os aplicativos **Configurações** >  **Atualizar** >  e Segurança **Windows Update** e, em seguida, instale todas as atualizações.

| Problema               | Descrição           | Solução                 |
|---------------------|-----------------------|------------------------|
| Ao usar o aplicativo Whiteboard em Surface Hub, o conteúdo não pode ser compartilhado por email. | O recurso "Compartilhamento Fácil" foi removido da nova versão do aplicativo Whiteboard. | A maneira recomendada de salvar o conteúdo do Whiteboard é entrar no aplicativo. Se a entrada não for possível, um arquivo de imagem poderá ser salvo no armazenamento local e compartilhado por meio de um serviço preferencial do usuário por meio do navegador Edge. O recurso "Compartilhamento Fácil" retornará em uma versão futura do Whiteboard. [Saiba mais sobre cenários de compartilhamento do Whiteboard.](https://support.microsoft.com/office/enable-microsoft-whiteboard-for-your-organization-1caaa2e2-5c18-4bdf-b878-2d98f1da4b24) |
| Alguns Surface Hubs estão reiniciando quando um usuário seleciona 'Encerrar Sessão'.  | Quando Surface Hub dispositivos selecionam a funcionalidade 'Encerrar Sessão' para limpar os dados do usuário, o dispositivo Surface Hub pode detectar erroneamente uma falha de limpeza, forçando uma reinicialização do Windows para garantir que a limpeza ocorra com êxito.  | A Microsoft está ciente e está investigando ativamente esse problema.  A Microsoft fornecerá informações adicionais sobre uma resolução o mais rápido possível.|
| Ao usar Os Surface Hubs GCC ambientes altos, o ingresso na reunião com um clique no calendário da tela de boas-vindas não funciona. | Clicar em "Ingressar" no calendário Surface Hub para uma reunião Teams em um ambiente GCC High não inicia automaticamente a reunião. | Para ingressar na reunião, inicie Teams e, em seguida, ingresse-a de dentro Teams agenda exibida pelo cliente. <br></br>A Microsoft também está investigando ativamente esse problema e fornecerá informações adicionais sobre uma resolução o mais rápido possível. |
| As configurações de QoS (Qualidade de Serviço) não funcionam conforme o esperado | Depois de definir as configurações de QoS por meio da política de MDM ou do pacote de provisionamento, as marcações DSCP não serão aplicadas ao tráfego de mídia Teams ou Skype for Business (SfB). | A Microsoft está ciente e está investigando ativamente esse problema.  A Microsoft fornecerá informações adicionais sobre uma resolução o mais rápido possível. |
| Falha na sincronização de calendário de contas de dispositivo híbrido com caixas de correio locais. | Surface Hub dispositivos usam a Autenticação Moderna para contas que existem no Azure AD, mesmo que tenham caixas de correio em ambientes locais que não têm a Autenticação Moderna Híbrida habilitada.[](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) Nesse cenário, o Exchange interrompe a sincronização de reuniões com o dispositivo. Como resultado, o dispositivo não recebe ou exibe novas reuniões. | Depois [que o KB4598291](https://support.microsoft.com/help/4598291) (ou uma CU de Windows subsequente) for instalado, o [CSP do SurfaceHub](/windows/client-management/mdm/surfacehub-csp) terá um novo parâmetro ExchangeModernAuthEnabled disponível para alternar o uso da Autenticação Moderna. Isso pode ser definido como false por meio da política de MDM ou [do pacote de provisionamento](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg) para impedir que o Hub use a Autenticação Moderna. |
| Um pequeno subconjunto de dispositivos Surface Hub v1 não é capaz de atualizar automaticamente para a atualização Windows 10 Team 2020. | Esse pequeno subconjunto de dispositivos Surface Hub v1 está em um estado que está impedindo a compatibilidade com a atualização direta por meio Windows Update. | Redimensione manualmente o dispositivo para a atualização Windows 10 Team 2020 usando a [ferramenta Surface Hub recuperação.](surface-hub-recovery-tool.md) |
| Surface Hub exibe a mensagem "Nenhum dispositivo inicializável" depois de tentar instalar a atualização Windows 10 Team 2020. | Durante o Windows Update para Windows 10 Team 2020, alguns dispositivos Hub v1 entrarão em um estado não inbooável. | Redimensione manualmente o dispositivo para a atualização Windows 10 Team 2020 usando a [ferramenta Surface Hub recuperação.](surface-hub-recovery-tool.md) |
| Os dispositivos hub 2S não podem receber atualizações de driver usando o WSUS. | Surface Hub 2S dá suporte Windows Update e Windows Update business para distribuir drivers; não há suporte para a distribuição por meio do Windows Server Update Services (WSUS). | Se estiver usando o WSUS, migre para o Windows Update for Business.<br> <br>**Saiba mais**: [O que é Windows atualização para empresas?](/windows/deployment/update/waas-manage-updates-wufb) |
| A Central de Ações tem um link não Configurações clique. | Esse link não deve aparecer no Windows 10 Team e pode causar confusão. | A funcionalidade é a mesma que antes da atualização de 2020; a seção Aplicativos do menu Iniciar deve ser usada para iniciar o Configurações aplicativo.  |
| Algumas configurações de facilidade de acesso persistem após o término de uma sessão| Quando os usuários ativam a alternância alto contraste no menu Ações rápidas ou no aplicativo Configurações, essa alternância persiste após o término da sessão do usuário. Da mesma forma, se os usuários alterarem a exibição das notificações para indicar 7 segundos versus 5 segundos definidos pelo administrador, ele permanecerá 7 segundos, mesmo que outras configurações sejam redefinidas para os valores definidos pelo administrador. | Os usuários podem desativar a alternância de Alto Contraste do menu ações rápidas (cursor) acessível na Barra de Tarefas logo após iniciar uma sessão no Hub. A duração de exibição das notificações pode ser definida como um valor diferente por meio do aplicativo Configurações pelo próximo usuário – essa configuração é acessível a todos os usuários. A Microsoft está procurando ativamente encontrar uma solução para esse problema.| 
