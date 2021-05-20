---
title: Remoção de SSD em dispositivos Surface compatíveis
description: Este artigo, destinado a técnicos de IT qualificados, descreve as práticas recomendadas para a remoção e substituição de SSDs no Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X e Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576901"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a>Práticas recomendadas para remoção de SSD de dispositivos Surface compatíveis

> [!IMPORTANT]
> Este artigo destina-se apenas a ser usado por técnicos de IT qualificados em uma organização corporativa. Ele descreve as práticas recomendadas recomendadas para uso por técnicos de IT qualificados na remoção e substituição de SSDs nos seguintes dispositivos Surface compatíveis: 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4

> [!WARNING]
> Abrir dispositivos e substituir componentes do dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndio e riscos de danos pessoais e outros riscos.  Sempre use cuidado ao realizar essas atividades. Siga as precauções e os procedimentos de segurança identificados no Guia de Remoção [do rSSD para Enterprise](https://www.microsoft.com/download/100440). Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "Guia de Remoção do rSSD para Enterprise".

## <a name="prerequisites"></a>Pré-requisitos

> [!IMPORTANT]
> Este artigo pressupôs que você compreende as políticas e procedimentos gerais de segurança e precauções de segurança descritos no "Guia de Remoção do rSSD para Enterprise".

## <a name="prepare-for-ssd-removal"></a>Preparar para remoção do SSD 

### <a name="install-the-latest-updates"></a>Instalar as atualizações mais recentes 

Antes de começar, certifique-se de que sua versão do Windows tenha as atualizações mais recentes instaladas:

1.  Vá para **Iniciar**  >  **Configurações**  >  **Atualização & Segurança**e selecione Verificar se há **atualizações**.
2. Instale todas as atualizações disponíveis.
3. Verifique as senhas necessárias para acessar o dispositivo.  
 
## <a name="manage-bitlocker"></a>Gerenciar o BitLocker 

> [!NOTE]
> Esta seção inclui recomendações para organizações que tenham habilitado BitLocker criptografia para discos rígidos. Para obter mais informações, [consulte BitLocker Guia de Recuperação.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan) 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a>Se BitLocker criptografia for desabilitada durante a remoção e substituição do SSD

Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar BitLocker:

1.  Em **Configurações**, digite **BitLocker** e selecione **Gerenciar BitLocker**. 
2.  Selecione **Desativar BitLocker**. 
3.  Alimente o dispositivo. 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a>Se BitLocker criptografia estiver habilitada durante a remoção e substituição do SSD

Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave BitLocker de recuperação e salvá-lo no armazenamento USB:

1.  Em **Configurações,** digite **BitLocker**.
2. Selecione **Gerenciar BitLocker**Gerar BitLocker Chave de  > **Recuperação**.
2.  Insira uma unidade USB. 
4.  Salve a chave de recuperação no armazenamento USB.  
5.  Remova a unidade USB.  
6.  Alimente o dispositivo. 

## <a name="remove-and-replace-ssd"></a>Remover e substituir SSD 

1.  Remova o SSD usando as instruções apropriadas para seu dispositivo incluído no Guia de Remoção [do rSSD para](https://www.microsoft.com/download/100440)Enterprise . 
2.  Coloque o SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão de internet com fio.
3.  Power on the new device. O dispositivo pode passar por uma atualização de firmware durante a inicialização.  
 
## <a name="after-ssd-removal-and-replacement"></a>Após a remoção e substituição do SSD

### <a name="manage-unencrypted-ssds"></a>Gerenciar SSDs não criptografados 

Se o SSD for descriptografado durante a transferência, siga estas etapas: 

1.  Vá para **Senha de Opções de**  >  **Login** (representado pelo ícone da chave no lado esquerdo).  
2.  Insira a senha e entre aguardando a conclusão da autenticação de dois fatores (se aplicável).
3.  Depois de entrar totalmente, vá para **Iniciar**a Saída  >  ****  >  **da Conta**.  
4.  Entre novamente usando a senha e configurar o Windows Hello e um PIN quando você for solicitado. 
    - Se o dispositivo foi BitLocker desabilitado para facilitar a remoção e a substituição do SSD e você deseja habilitar o BitLocker após a substituição, vá para **BitLocker Gerenciar**BitLocker  >  ****  >  **Retomar BitLocker**.  
6.  Execute o [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para verificar a funcionalidade completa do dispositivo.  
7.  Verifique se Windows ativação navegando para **Configurações**  >  **Ativação**.  Se você vir mensagens de erro, selecione **Solucionar problemas**. 
8.  Verifique a Office ao abrir o aplicativo **Office,** navegue até **Conta**de Arquivo e verifique se há mensagens  >  **** de erro.  

### <a name="managing-encrypted-ssds"></a>Gerenciando SSDs criptografados 

> [!NOTE]
> Você terá que ter um segundo dispositivo para ler a chave de recuperação BitLocker que foi salva na unidade USB. 

Se o SSD for criptografado durante a transferência, siga estas etapas:

1.  Insira a unidade USB que contém a chave BitLocker de recuperação no segundo dispositivo. 
2.  Abra o .txt que contém a chave de recuperação Bitlocker. 
3.  Insira manualmente a BitLocker chave de recuperação no novo dispositivo que contém o SSD original.  
4.  Depois de ter inserido com êxito a BitLocker de recuperação, vá para **Senha**de Opções de Entrada (representada pelo ícone de tecla  >  **** no lado esquerdo).  
5.  Insira a senha e entre, aguardando a conclusão da autenticação de dois fatores (se aplicável).
6.  Depois de entrar totalmente, vá para **Iniciar**a Saída  >  ****  >  **da Conta**.  
7.  Entre novamente usando a senha e, em seguida, configurar Windows Hello e adicionar um PIN. 
8.  Se o dispositivo foi BitLocker desabilitado para facilitar a remoção e a substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para **Configurações**  >  **BitLocker**  >  **Gerenciar**BitLocker  >  **Retomar BitLocker**.  
9.  Execute **[o SDT](surface-diagnostic-toolkit-for-business-intro.md)** para verificar a funcionalidade completa do dispositivo.  
10. Para verificar Windows ativação, selecione **Configurações**  >  **Ativação**.  Se você vir mensagens de erro, selecione **Solucionar problemas**.
11. Para verificar o status da conta Office, abra o aplicativo Office **,** em seguida, vá para **Conta**de Arquivo para verificar se há mensagens  >  **** de erro.

## <a name="learn-more"></a>Saiba mais

- [Guia de Remoção do rSSD para Enterprise](https://www.microsoft.com/download/100440)
- [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Ainda precisa de ajuda? Vá para [Microsoft Community](https://answers.microsoft.com/).