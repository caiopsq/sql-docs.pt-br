---
title: Lição 9 criar perspectivas | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 4e917e817768571e1959ae6163743ecdad0409af
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38031614"
---
# <a name="lesson-8-create-perspectives"></a>Lição 8: Criar perspectivas
[!INCLUDE[ssas-appliesto-sql2016-later-aas](../includes/ssas-appliesto-sql2016-later-aas.md)]

Nesta lição, você criará uma perspectiva de Vendas pela Internet. Uma perspectiva define um subconjunto exibível de um modelo que fornece pontos de vista concentrados, específicos à empresa ou específicos ao aplicativo. Quando um usuário se conecta a um modelo usando uma perspectiva, eles veem apenas os objetos de modelo (tabelas, colunas, medidas, hierarquias e KPIs) como campos definidos nessa perspectiva.  
  
A perspectiva de vendas pela Internet que você criou nesta lição excluirá o objeto de tabela DimCustomer. Quando você cria uma perspectiva que exclui determinados objetos da exibição, esse objeto ainda existe no modelo; porém, não está visível em uma lista de campo de cliente de relatório. Colunas calculadas e medidas incluídas ou não em uma perspectiva ainda podem ser calculadas de dados de objeto que são excluídos.  
  
A finalidade desta lição é descrever como criar perspectivas e se familiarizar com as ferramentas de criação de modelo de tabela. Se você expandir este modelo para incluir tabelas adicionais posteriormente, você pode criar perspectivas adicionais para definir diferentes pontos de vista do modelo, por exemplo, vendas e inventário. Para saber mais, consulte [Perspectivas](../analysis-services/tabular-models/perspectives-ssas-tabular.md).  
  
Tempo estimado para concluir esta lição: **5 minutos**  
  
## <a name="prerequisites"></a>Prerequisites  
Este tópico faz parte de um tutorial de modelo de tabela, que deve ser concluído na ordem. Antes de executar as tarefas nesta lição, você deve ter concluído a lição anterior: [lição 7: criar indicadores chave de desempenho](../analysis-services/lesson-7-create-key-performance-indicators.md).  
  
## <a name="create-perspectives"></a>Criar perspectivas  
  
#### <a name="to-create-an-internet-sales-perspective"></a>Para criar uma perspectiva Vendas pela Internet  
  
1.  Clique o **modelo** menu > **perspectivas** > **criar e gerenciar**.  
  
2.  Na caixa de diálogo **Perspectivas** , clique em **Nova Perspectiva**.  
  
3.  Clique duas vezes o **nova perspectiva** título de coluna e renomeie **vendas pela Internet**.  
  
4.  Selecione todas as tabelas *exceto* **DimCustomer**.  
  
    ![como-tabela-lesson8-perspectivas](../analysis-services/media/as-tabular-lesson8-perspectives.png)
  
    Em uma lição posterior, você usará o analisar no recurso do Excel para testar essa perspectiva. A lista de campos de tabela dinâmica do Excel incluirá cada tabela, com exceção da tabela DimCustomer.  

## <a name="whats-next"></a>O que vem a seguir?
Vá para a próxima lição: [lição 9: criar hierarquias](../analysis-services/lesson-9-create-hierarchies.md).
  
  
  
  
