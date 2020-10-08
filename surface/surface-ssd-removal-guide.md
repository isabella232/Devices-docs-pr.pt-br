---
title: Remoção de SSD em dispositivos de superfície compatíveis
description: Como transferir uma SSD de um dispositivo de superfície para outro.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 00109e4e1bb3873fc2914b2044f58e6fa3b6c211
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104803"
---
# Práticas recomendadas para remoção de SSD de dispositivos de superfície compatíveis

> [!IMPORTANT]
> Este artigo destina-se a usar técnicos de ti qualificados apenas em uma organização corporativa. Ele descreve as práticas recomendadas recomendadas para uso por técnicos de ti qualificados na remoção e substituição de SSDs no laptop de Surface 3 ou Surface Pro X. 

> [!WARNING]
> Abrir dispositivos e substituir componentes de dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndios e riscos de ferimentos pessoais e outros riscos.  Use sempre um cuidado ao realizar tais atividades. Siga as precauções e os procedimentos de segurança identificados no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440). Recomendamos que você receba assistência profissional se não puder seguir as precauções e os procedimentos de segurança especificados no "guia de remoção do rSSD para empresas".

## Pré-requisitos

> [!IMPORTANT]
> Este artigo pressupõe que você compreenda as precauções gerais de segurança e as políticas de segurança e os procedimentos descritos no guia de remoção do rSSD para empresas.

## Preparar a remoção do SSD 

### Instalar as atualizações mais recentes 

Antes de começar, verifique se a sua versão do Windows tem as atualizações mais recentes em atualização:

1.  Vá para **Iniciar**  >  **configurações**  >  **Atualizar & segurança**e selecione **verificar se há atualizações**. Instale todas as atualizações disponíveis. 
2. Instale todas as atualizações disponíveis.
3. Verifique se você tem senhas necessárias para acessar o dispositivo.  
 
## Gerenciar o BitLocker 

> [!NOTE]
> Esta seção inclui recomendações para organizações que ativaram a criptografia BitLocker para discos rígidos. Para obter mais informações, consulte o [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### Se a criptografia do BitLocker estiver desabilitada durante a remoção e a substituição do SSD

Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:

1.  Em **configurações**, digite **BitLocker**e, em seguida, selecione **gerenciar o BitLocker**. 
2.  Selecione desativar **BitLocker**. 
3.  Desligue o dispositivo. 

### Se a criptografia do BitLocker estiver habilitada durante a remoção e a substituição do SSD

Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:

1.  Em **configurações**, digite **BitLocker**.
2. Selecione **gerenciar o BitLocker**  > **gerar a chave de recuperação do BitLocker**.
2.  Insira uma unidade USB. 
3.  Salve a chave de recuperação em armazenamento USB.  
4.  Remova a unidade USB.  
5.  Desligue o dispositivo. 

## Remover e substituir a SSD 

1.  Remova a SSD usando as instruções no [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440). 
2. Coloque a SSD original em um novo dispositivo e conecte o novo dispositivo a uma conexão com a Internet com fio.
2.  Ligue o novo dispositivo. O dispositivo pode passar por uma atualização de firmware durante a inicialização.  
 
## Após remoção e substituição do SSD

### Gerenciar SSDs não criptografados 

Se a SSD permanecer sem criptografia durante a transferência, siga estas etapas: 

1.  Acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).  
2.  Digite a senha e entre na conclusão pendente da autenticação de dois fatores (se aplicável).
3.  Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.  
4.  Entre novamente usando a senha e configure o Windows Hello e um PIN quando solicitado. 
    - Se o dispositivo tiver o BitLocker desabilitado para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, vá para **BitLocker**  >  **gerenciar BitLocker**  >  **retomar BitLocker**.  
6.  Execute o kit de ferramentas de diagnóstico do Surface da Microsoft para empresas (SDT) para verificar a funcionalidade completa do dispositivo.  
7.  Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.  Se você vir mensagens de erro, selecione **solucionar problemas**. 
8.  Verifique a conta do Office abrindo o **aplicativo do Office**, navegue até **arquivo**  >  **conta** e verifique se há mensagens de erro.  

### Gerenciando o SSDs criptografado 

> [!NOTE]
> Será necessário ter um segundo dispositivo para ler a chave de recuperação do BitLocker que foi salva na unidade USB. 

Se a SSD permanecia criptografada durante a transferência, siga estas etapas:

1.  Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo. 
2.  Abra o arquivo. txt que contém a chave de recuperação do BitLocker. 
3.  Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.  
4.  Depois de inserir a chave de recuperação do BitLocker com êxito, acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).  
5.  Digite a senha e conecte-se à conclusão pendente da autenticação de dois fatores (se aplicável).
6.  Depois de conectar-se completamente, acesse **Iniciar**  >  **conta**sair  >  **Sign out**.  
7.  Entre novamente usando a senha e, em seguida, configure o Windows Hello e adicione um PIN. 
8.  Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e se você quiser habilitar o BitLocker após a substituição, vá para **configurações**  >  **BitLocker**  >  **gerenciar**BitLocker  >  **retomar BitLocker**.  
9.  Execute o **SDT** para verificar a funcionalidade completa do dispositivo.  
10. Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.  Se você vir mensagens de erro, selecione **solucionar problemas**.
11. Para verificar o status da conta do Office, abra o **aplicativo do Office**e, em seguida, vá para a **File**  >  **conta** arquivo para verificar se há mensagens de erro.

## Mais informações 

Para obter mais informações, consulte os seguintes artigos:

- [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440)
- [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Ainda precisa de ajuda? Vá para [comunidade da Microsoft](https://answers.microsoft.com/).