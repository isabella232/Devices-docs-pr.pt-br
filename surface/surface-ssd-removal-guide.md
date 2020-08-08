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
ms.date: 8/7/2020
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
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918942"
---
# Práticas recomendadas para remoção do SSD em dispositivos de superfície compatíveis

> [!IMPORTANT]
> Este artigo destina-se a usar técnicos de ti qualificados apenas em uma organização corporativa. Ele descreve as práticas recomendadas a serem usadas por técnicos de ti qualificados ao remover e substituir o SSDs em dispositivos de superfície com SSDs removível. 

> [!WARNING]
> Abrir dispositivos e substituir componentes de dispositivo pode apresentar choque elétrico, danos ao dispositivo, incêndios e riscos de ferimentos pessoais e outros riscos.  Sempre use cuidado ao realizar tais atividades. Siga as precauções de segurança e os procedimentos identificados no guia de remoção do rSSD para empresas. A Microsoft recomenda que você busque assistência profissional se não conseguir seguir as precauções e os procedimentos de segurança especificados no guia de remoção do rSSD para empresas. 

## Pré-requisitos

> [!IMPORTANT]
> Este artigo pressupõe que você compreenda as precauções gerais de segurança e os procedimentos e políticas de segurança descritos no [Guia de remoção rSSD para empresas](https://www.microsoft.com/download/100440).

## Preparar a remoção do SSD 

### Instalar as atualizações mais recentes 

Antes de começar, verifique se a sua versão do Windows tem as atualizações mais recentes.

1.  Vá para **Iniciar**  >  **configurações**  >  **Atualizar & segurança** e selecione **verificar se há atualizações**. Instale todas as atualizações disponíveis.  

2.  Confirme se você tem qualquer senha necessária para acessar o dispositivo.  
 
## Gerenciar o BitLocker 

> [!NOTE]
> Esta seção inclui recomendações para organizações que ativaram a criptografia BitLocker para discos rígidos. Para obter mais informações, consulte o [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### Se a criptografia do BitLocker estiver desabilitada durante a remoção e a substituição do SSD

Se o dispositivo pode ser descriptografado antes da remoção e substituição do SSD, siga estas etapas para desativar o BitLocker:

1.  Em **configurações**, digite **BitLocker** e selecione **gerenciar o BitLocker**. 
2.  Selecione desativar **BitLocker**. 
3.  Desligue o dispositivo. 

### Se a criptografia do BitLocker estiver habilitada durante a remoção e a substituição do SSD

Se o dispositivo for criptografado antes da remoção e substituição do SSD, siga estas etapas para gerar uma chave de recuperação do BitLocker e salvá-la no armazenamento USB:

1.  Vá para **configurações** e digite **BitLocker**.
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

Se a SSD permanecer sem criptografia durante a transferência, conclua o seguinte: 

1.  Acesse a senha de **Opções de entrada**  >  **Password** (representada como o ícone de chave no lado esquerdo).  
2.  Digite a senha e entre na conclusão pendente de autenticação de dois fatores (se aplicável).
3.  Uma vez conectado completamente, acesse **Iniciar**  >  **conta**  >  **sair**.  
4.  Conecte-se novamente com a senha e configure o Windows Hello e um PIN quando solicitado. 
    - Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, vá para **BitLocker**  >  **gerenciar BitLocker**  >  **retomar BitLocker**.  
6.  Execute **SDT** para confirmar a funcionalidade completa do dispositivo.  
7.  Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.  Se houver mensagens de erro, selecione **solucionar problemas**. 
8.  Verifique a conta do Office abrindo o **aplicativo do Office**e, em seguida, navegue até **arquivo**  >  **conta** e verifique se há mensagens de erro.  

### Gerenciando o SSDs criptografado 

> [!NOTE]
> Será necessário um segundo dispositivo para ler a chave de recuperação do BitLocker que foi salva na unidade USB. 

Se a SSD permanecia criptografada durante a transferência, conclua o seguinte:

1.  Insira a unidade USB que contém a chave de recuperação do BitLocker no segundo dispositivo. 
2.  Abra o arquivo. txt que contém a chave de recuperação do BitLocker. 
3.  Insira manualmente a chave de recuperação do BitLocker no novo dispositivo que contém o SSD original.  
4.  Depois de inserir a chave de recuperação do BitLocker com êxito, acesse a senha de **Opções de entrada**  >  **Password** (representada pelo ícone de chave no lado esquerdo).  
5.  Digite a senha e conecte-se à conclusão pendente da autenticação de dois fatores (se aplicável) 
6.  Uma vez conectado completamente, acesse **Iniciar**  >  **conta**  >  **sair**.  
7.  Entre novamente com a senha e configure o Windows Hello e adicione um PIN. 
8.  Se o dispositivo tiver sido desabilitado pelo BitLocker para facilitar a remoção e a substituição do SSD e você quiser habilitar o BitLocker após a substituição, acesse **configurações**  >  **BitLocker**  >  **gerenciar**BitLocker  >  **retomar BitLocker**.  
9.  Execute **SDT** para confirmar a funcionalidade completa do dispositivo.  
10. Verifique a ativação do Windows navegando para a ativação de **configurações**  >  **Activation**.  Se houver mensagens de erro, selecione **solucionar problemas**.
11. Para verificar a conta do Office, abra o **aplicativo do Office**e, em seguida, vá para a conta de **arquivo**  >  **Account** e verifique se há mensagens de erro.

## Mais informações 

Para obter mais informações, consulte os seguintes artigos:

- [Guia de remoção do rSSD para empresas](https://www.microsoft.com/download/100440)
- [Guia de recuperação do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Ainda precisa de ajuda? Vá para [comunidade da Microsoft](https://answers.microsoft.com/).