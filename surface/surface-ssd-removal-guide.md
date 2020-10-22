---
title: Remoção de SSD em dispositivos de superfície compatíveis
description: Este artigo, destinado a técnicos de ti qualificados, descreve as práticas recomendadas para a remoção e substituição do SSDs no laptop Surface 3, Surface Pro X e Surface laptop go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133166"
---
# Práticas recomendadas para remoção de SSD de dispositivos de superfície compatíveis

> [!IMPORTANT]
> Este artigo destina-se a usar técnicos de ti qualificados apenas em uma organização corporativa. Ele descreve as práticas recomendadas recomendadas para uso por técnicos de ti qualificados na remoção e substituição de SSDs nos seguintes dispositivos da superfície compatível: 

- Laptop Surface 3 
- Surface Pro X 
- Usar o laptop Surface

> [!WARNING]
> Abrir dispositivos e substituir componentes de dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndios e riscos de ferimentos pessoais e outros riscos.  Use sempre um cuidado ao realizar tais atividades. Siga as precauções e os procedimentos de segurança identificados no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440). Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "guia de remoção do rSSD para empresas".

## Pré-requisitos

> [!IMPORTANT]
> Este artigo pressupõe que você compreenda as precauções gerais de segurança e as políticas de segurança e os procedimentos descritos no guia de remoção do rSSD para empresas.

## Preparar a remoção do SSD 

### Instalar as atualizações mais recentes 

Antes de começar, verifique se a sua versão do Windows tem as atualizações mais recentes instaladas:

1.  Vá para **Iniciar**  >  **configurações**  >  **Atualizar & segurança**e selecione **verificar se há atualizações**.
2. Instale todas as atualizações disponíveis.
3. Verifique as senhas necessárias para acessar o dispositivo.  
 
## Gerenciar o BitLocker 

> [!NOTE]
> Esta seção inclui recomendações para organizações que ativaram a criptografia BitLocker para discos rígidos. Para obter mais informações, consulte  [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### Se a criptografia do BitLocker estiver desabilitada durante a remoção e a substituição do SSD

Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:

1.  Em **configurações**, digite **BitLocker** e, em seguida, selecione **gerenciar o BitLocker**. 
2.  Selecione desativar **BitLocker**. 
3.  Desligue o dispositivo. 

### Se a criptografia do BitLocker estiver habilitada durante a remoção e a substituição do SSD

Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:

1.  Em **configurações**, digite **BitLocker**.
2. Selecione **gerenciar o BitLocker**  > **gerar a chave de recuperação do BitLocker**.
2.  Insira uma unidade USB. 
4.  Salve a chave de recuperação em armazenamento USB.  
5.  Remova a unidade USB.  
6.  Desligue o dispositivo. 

## Remover e substituir SSD 

1.  Remova a SSD usando as instruções no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440). 
2.  Coloque a SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão com a Internet com fio.
3.  Ligue o novo dispositivo. O dispositivo pode passar por uma atualização de firmware durante a inicialização.  
 
## Após remoção e substituição do SSD

### Gerenciar SSDs não criptografados 

Se a SSD não for criptografada durante a transferência, siga estas etapas: 

1.  Acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).  
2.  Digite a senha e entre na conclusão pendente de autenticação de dois fatores (se aplicável).
3.  Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.  
4.  Conecte-se novamente usando a senha e configure o Windows Hello e um PIN quando solicitado. 
    - Se o dispositivo tiver o BitLocker desabilitado para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, vá para **BitLocker**  >  **gerenciar BitLocker**  >  **retomar BitLocker**.  
6.  Execute o [Kit de ferramentas de diagnóstico do Surface da Microsoft para empresas](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para verificar a funcionalidade completa do dispositivo.  
7.  Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.  Se você vir mensagens de erro, selecione **solucionar problemas**. 
8.  Verifique a conta do Office abrindo o **aplicativo do Office**, navegue até **arquivo**  >  **conta** e verifique se há mensagens de erro.  

### Gerenciando o SSDs criptografado 

> [!NOTE]
> Será necessário ter um segundo dispositivo para ler a chave de recuperação do BitLocker que foi salva na unidade USB. 

Se a SSD for criptografada durante a transferência, siga estas etapas:

1.  Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo. 
2.  Abra o arquivo. txt que contém a chave de recuperação do BitLocker. 
3.  Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.  
4.  Depois de inserir a chave de recuperação do BitLocker com êxito, acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).  
5.  Digite a senha e conecte-se à conclusão pendente da autenticação de dois fatores (se aplicável).
6.  Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.  
7.  Entre novamente usando a senha e, em seguida, configure o Windows Hello e adicione um PIN. 
8.  Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para **configurações**  >  **BitLocker**  >  **gerenciar**BitLocker  >  **retomar BitLocker**.  
9.  Execute o **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** para verificar a funcionalidade completa do dispositivo.  
10. Para verificar a ativação do Windows, selecione ativação de **configurações**  >  **Activation**.  Se você vir mensagens de erro, selecione **solucionar problemas**.
11. Para verificar o status da conta do Office, abra o **aplicativo do Office**e, em seguida, vá para a **File**  >  **conta** arquivo para verificar se há mensagens de erro.

## Saiba mais

- [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440)
- [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Ainda precisa de ajuda? Vá para [comunidade da Microsoft](https://answers.microsoft.com/).