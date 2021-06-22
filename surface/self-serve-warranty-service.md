---
title: Garantia e serviço do Surface Self Serve
description: Microsoft 365 Os clientes comerciais podem estar qualificados para usar o nó de Garantia e Serviço do Surface Self Serve beta no Centro de Administração da Microsoft para criar e gerenciar pedidos de serviço.
ms.prod: w10
ms.mktglfcycl: support
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/07/2021
ms.reviewer: louannh
manager: laurawi
audience: itpro
ms.openlocfilehash: a6021a58c85ac6ee4c039959dcde9bab632ea1bb
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614034"
---
# <a name="surface-self-serve-warranty-and-service"></a>Garantia e serviço de autoatendação do Surface

Microsoft 365 Os clientes comerciais podem estar qualificados para usar o nó Surface Self Serve Warranty and Service no centro de Administração Microsoft 365 para criar e gerenciar pedidos de serviço. Esse novo recurso, disponível como um programa beta, permite que os Administradores Globais designem permissões para indivíduos em sua empresa responsáveis por oferecer suporte a declarações de garantia e serviço, incluindo:

- Upload números de série para os dispositivos que exigem serviço.
- Adicione vários endereços de envio.
- Crie uma única ordem de serviço para um ou vários dispositivos e capas de tipo.
- Consulte o status da ordem de serviço em tempo real.
- Enviar e receber envios Exchange envios em massa se os dispositivos são cobertos por uma garantia estendida ou o Exchange avançado foi incluído como parte da compra do dispositivo.

## <a name="join-beta-program"></a>Ingressar no programa beta

Entre em contato com o Gerente de Conta de Sucesso do Cliente da Microsoft ou o Gerente de Sucesso do Cliente para saber mais sobre a experiência e como participar do programa beta.

## <a name="role-based-permissions"></a>Permissões baseadas em função

O Surface Self-Serve Garantia e Serviço permite que um administrador global Microsoft 365 a capacidade de conceder permissões diferentes para criar e gerenciar pedidos de serviço atribuindo funções aos usuários.

Quando um Microsoft 365 é adicionado ao programa beta, as seguintes funções de administrador são concedidas a permissões adicionais:

| Função                  | Permissões                                                                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Administrador Global          | Exibir Solicitações de Reparo<br>Criar/gerenciar solicitações de reparo<br>Add/Edit/Delete Ship to Address(es)<br>Criar/gerenciar usuários e suas funções |
| Administrador de Suporte ao Serviço | Exibir Solicitações de Reparo<br>Criar/gerenciar solicitações de reparo                                                                               |
| Administrador de Cobrança         | Exibir Solicitações de Reparo<br>Criar/gerenciar solicitações de reparo<br>Add/Edit/Delete Ship to address(es)                                        |

Para obter mais informações sobre usuários e permissões, consulte [Visão geral do Centro de Administração da Microsoft.](/microsoft-365/admin/admin-overview/about-the-admin-center)

## <a name="create-and-manage-a-service-order"></a>Criar e gerenciar uma ordem de serviço

1. Vá para a Administração Microsoft 365 central em [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) e entre com as permissões de administrador apropriadas. Para saber mais, confira [Who tem permissões de administrador na minha empresa?](/microsoft-365/business-video/admin-center-overview#who-has-admin-permissions-in-my-business)
2. Vá para **Suporte**  >  **a Reparos de Dispositivo Surface** e selecione Criar **solicitação de reparo**. (Se você não vir essa opção de reparo, não terá permissão para acessar esta página.)

    > [!div class="mx-imgBorder"]
    > ![Iniciar solicitação de reparo de autoatendito](images/self-serve-fig1.png)

3. Você pode criar uma solicitação de reparo para um ou vários dispositivos. Selecione Enviar **um dispositivo** de **** cada vez ou Enviar vários dispositivos para usar um arquivo .csv para carregar vários números de série e selecione **Próximo**.

    > [!NOTE]
    > **Para vários dispositivos:**
    >
    > - Na página Centro de Administração, baixe o modelo CSV de exemplo, adicione as informações necessárias e salve-as na unidade local.
    > - Selecione **Upload arquivo CSV**para entradas em massa, selecione o arquivo .csv que você salvou na unidade local e **selecione Abrir.**
    > - Os números de série do dispositivo serão carregados. Selecione **Próximo** para continuar a criação do reparo.

4. Em **Substituição de envio para**, selecione um endereço de envio. Ou selecione  **Adicionar novo endereço**.

    > [!NOTE]
    >
    > - As permissões permitem que determinados administradores adicionem nova nave a endereços. Se você tiver permissões, > poderá adicionar novos endereços. Insira as informações necessárias e selecione  **Salvar**.
    > - O formulário valida automaticamente as informações de endereço e você pode ser corrigido para fazer alterações se o endereço não for reconhecido pelo sistema postal local. O endereço de email é usado para enviar notificações e comunicações para a solicitação de reparo.

    > [!div class="mx-imgBorder"]
    > ![
      Adicionar novo endereço
    ](images/self-serve-fig2a.png)

5. Adicione o dispositivo inserindo o número de série do dispositivo no bloco de texto. Para saber mais, confira [números de série do dispositivo](https://support.microsoft.com/help/4036293/surface-find-the-serial-number-on-surface). Se o número de série for válido, uma imagem e informações do produto, incluindo a data da garantia e o número do modelo, serão exibidas. Selecione **Adicionar Dispositivo** se as informações estão corretas.

    > [!div class="mx-imgBorder"]
    > ![Adicionar dispositivos](images/self-serve-fig2.png)

6. Repita as etapas 1 a 2 para adicionar vários dispositivos (até 20 no total) à solicitação.
7. No menu suspenso, selecione o tipo de problema que melhor descreve o problema e selecione **Próximo.**

    > [!div class="mx-imgBorder"]
    > ![Selecionar categoria de problema](images/self-serve-fig3.png)

8. Revise seu pedido. Se alguma informação estiver incorreta, escolha **Voltar** para corrigir erros.
9. Aceite os termos de condições.
10. Se o resumo da solicitação estiver correto, selecione **Enviar sua solicitação**.

    > [!div class="mx-imgBorder"]
    > ![Enviar solicitação de reparo de autoatendito](images/self-serve-fig4.png)

Quando a home page é exibida, você pode exibir sua solicitação de serviço na lista de resumos e receber um email de confirmação.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="why-am-i-getting-error-code-400-generic-client-service-error-401-unauthorized-service-error-or-error-403-forbidden-service-error"></a>Por que estou recebendo o código de erro 400 "Erro de serviço de cliente genérico", 401 "Erro de serviço não autorizado" ou erro 403 "Erro de serviço proibido"?

Pode haver um problema com a conta Microsoft 365 ou o usuário não tem permissões para acessar o conteúdo. Entre em contato com seu Microsoft 365 Global Admin para assistência.

### <a name="when-i-enter-my-shipping-address-and-i-get-an-error-message-that-no-shipping-offers-are-available"></a>Quando eu insere meu endereço de envio e eu receber uma mensagem de erro de que nenhuma oferta de envio está disponível?

O Surface Self-Serve Garantia e Serviço Beta tem disponibilidade limitada no momento. As ofertas só estarão disponíveis se o endereço estiver localizado em um dos seguintes países:

Áustria, Bahrein, Bélgica, Bulgária, Croácia, Chipre, República Tcheca, Dinamarca, Estônia, Finlândia, França, Alemanha, Grécia, Hungria, Irlanda, Itália, Kuwait, Letônia, Lituânia, Luxemburgo, Malta, Países Baixos, Omã, Polônia, Portugal, Romênia, Eslováquia, Eslovênia, África do Sul, Espanha, Suécia e Reino Unido (excluindo a Irlanda do Norte).

### <a name="where-can-i-see-orders-that-i-have-placed-through-the-microsoft-365-portal"></a>Onde posso ver pedidos que eu tenho feito por meio do portal Microsoft 365?

Vá para [Centro de administração do Microsoft 365 - Solicitações de serviço](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/support/devicerepairs) e entre com suas Microsoft 365 credenciais.

Os pedidos criados por meio do Suporte ao Cliente da Microsoft não estarão visíveis no módulo Self-Serve Gerenciamento de Serviços e Garantia.

### <a name="why-am-i-unable-to-add-edit-or-delete-a-shipping-address"></a>Por que não consigo adicionar, editar ou excluir um endereço de envio?

A capacidade de adicionar, editar ou excluir um endereço de envio só pode ser feita por seu Microsoft 365 Global ou Administrador de Cobrança. Entre em contato com eles para saber mais.  

### <a name="how-can-i-contact-microsoft-support-for-the-surface-self-serve-warranty-and-service-beta"></a>Como entrar em contato com o Suporte da Microsoft para o Surface Self-Serve Garantia e Serviço beta?

Você pode entrar em contato com o suporte diretamente por meio do módulo de Suporte do Surface no Centro de Administração da Microsoft.

1. Entre no Centro de Administração da Microsoft usando suas Microsoft 365 credenciais.
2. Selecione **Suporte a**  >  **Reparos de Dispositivo Surface > Precisa de ajuda?** e descreva o problema.
3. Se os resultados não ajudarem, selecione **Contatar suporte**e insira uma descrição do seu problema. Confirme seu número de contato e endereço de email, selecione seu método de contato preferencial e selecione **Contact me**.
