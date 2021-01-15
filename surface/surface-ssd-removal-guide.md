---
title: Remoção de SSD em dispositivos Surface compatíveis
description: Este artigo, destinado a técnicos de IT qualificados, descreve as práticas recomendadas para a remoção e substituição de SSDs no Surface Laptop 3, Surface Pro X e Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270626"
---
# Práticas recomendadas para remoção de SSD de dispositivos Surface compatíveis

> [!IMPORTANT]
> Este artigo destina-se somente ao uso de técnicos de IT qualificados em uma organização corporativa. Ele descreve as práticas recomendadas para uso por técnicos de IT qualificados na remoção e substituição de SSDs nos seguintes dispositivos Surface compatíveis: 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3

> [!WARNING]
> Abrir dispositivos e substituir componentes do dispositivo pode causar danos elétricos, danos ao dispositivo, incêndio e riscos de danos pessoais e outros riscos.  Sempre seja cuidadoso ao realizar essas atividades. Siga as precauções e os procedimentos de segurança identificados no Guia de Remoção [do rSSD para Empresas.](https://www.microsoft.com/download/100440) Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "Guia de Remoção de RSSD para Empresas".

## Pré-requisitos

> [!IMPORTANT]
> Este artigo supõe que você compreende as políticas e procedimentos gerais de segurança e precauções de segurança descritas no "Guia de Remoção de RSSD para Empresas".

## Preparar para remoção do SSD 

### Instalar as atualizações mais recentes 

Antes de começar, certifique-se de que sua versão do Windows tenha as atualizações mais recentes instaladas:

1.  Vá para **Iniciar**  >  **Configurações Atualização**&  >  **Segurança**e selecione Verificar se há **atualizações.**
2. Instale todas as atualizações disponíveis.
3. Verifique as senhas necessárias para acessar o dispositivo.  
 
## Gerenciar o BitLocker 

> [!NOTE]
> Esta seção inclui recomendações para organizações que habilitaram a criptografia BitLocker para discos rígidos. Para obter mais informações, consulte [o Guia de Recuperação do BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan) 

### Se a criptografia BitLocker estiver desabilitada durante a remoção e substituição do SSD

Se o dispositivo puder ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:

1.  Em **Configurações,** digite **BitLocker** e selecione **Gerenciar BitLocker**. 
2.  Selecione **Desativar BitLocker.** 
3.  Alimente o dispositivo. 

### Se a criptografia BitLocker estiver habilitada durante a remoção e substituição do SSD

Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:

1.  Em **Configurações,** digite **BitLocker**.
2. Selecione **Gerenciar BitLocker**  > **Gerar Chave de Recuperação do BitLocker.**
2.  Insira uma unidade USB. 
4.  Salve a chave de recuperação no armazenamento USB.  
5.  Remova a unidade USB.  
6.  Alimente o dispositivo. 

## Remover e substituir o SSD 

1.  Remova o SSD usando as instruções apropriadas para seu dispositivo incluído no Guia de Remoção [rSSD para Empresas.](https://www.microsoft.com/download/100440) 
2.  Coloque o SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão com a Internet com fio.
3.  A energia do novo dispositivo. O dispositivo pode passar por uma atualização de firmware durante a inicialização.  
 
## Após a remoção e substituição do SSD

### Gerenciar SSDs não criptografados 

Se o SSD não for criptografado durante a transferência, siga estas etapas: 

1.  Vá para **Senha de Opções de**  >  **Login** (representado pelo ícone de tecla no lado esquerdo).  
2.  Insira a senha e entre com a conclusão pendente da autenticação de dois fatores (se aplicável).
3.  Depois de entrar totalmente, vá para **Iniciar**Saída  >  ****  >  **da Conta.**  
4.  Entre novamente usando a senha e configurar o Windows Hello e um PIN quando for solicitado. 
    - Se o dispositivo foi desabilitado pelo BitLocker para facilitar a remoção e substituição do SSD e você deseja habilitar o BitLocker após a substituição, vá para **o BitLocker**Gerenciar o  >  **BitLocker**Retomar  >  **o BitLocker.**  
6.  Execute o [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para verificar a funcionalidade completa do dispositivo.  
7.  Verifique se há ativação do Windows navegando até **a ativação de**  >  **configurações.**  Se você vir alguma mensagem de erro, selecione **Solucionar problemas.** 
8.  Verifique a conta do Office abrindo **** o **Aplicativo do Office,** navegue até Conta de Arquivo e verifique se há mensagens  >  **** de erro.  

### Gerenciando SSDs criptografados 

> [!NOTE]
> Você terá que ter um segundo dispositivo para ler a chave de Recuperação do BitLocker que foi salva na unidade USB. 

Se o SSD for criptografado durante a transferência, siga estas etapas:

1.  Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo. 
2.  Abra o arquivo .txt que contém a chave de recuperação do Bitlocker. 
3.  Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.  
4.  Depois de ter inserido com êxito a chave **** de recuperação do BitLocker, vá para Senha de Opções de Entrada (representada pelo ícone de chave  >  **** no lado esquerdo).  
5.  Insira a senha e entre, conclusão pendente da autenticação de dois fatores (se aplicável).
6.  Depois de entrar totalmente, vá para **Iniciar**Saída  >  ****  >  **da Conta.**  
7.  Entre novamente usando a senha e, em seguida, configurar o Windows Hello e adicionar um PIN. 
8.  Se o dispositivo foi desabilitado pelo BitLocker para facilitar a remoção e substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para Configurações **do**  >  **BitLocker**Gerenciar o  >  **BitLocker**Retomar  >  **o BitLocker.**  
9.  Execute **[o SDT](surface-diagnostic-toolkit-for-business-intro.md)** para verificar a funcionalidade completa do dispositivo.  
10. Para verificar a ativação do Windows, selecione **Ativação de**  >  **Configurações.**  Se você vir alguma mensagem de erro, selecione **Solucionar problemas.**
11. Para verificar o status da conta do Office, **** abra o Aplicativo do **Office**e vá para a Conta de Arquivo  >  **** para verificar se há mensagens de erro.

## Saiba mais

- [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440)
- [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Ainda precisa de ajuda? Vá para [a Comunidade da Microsoft.](https://answers.microsoft.com/)