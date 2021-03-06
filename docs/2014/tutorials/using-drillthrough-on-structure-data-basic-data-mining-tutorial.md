---
title: Usando o detalhamento em dados de estrutura (Tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: a693979c-0564-4d6d-b35d-cbbc8f350469
caps.latest.revision: 19
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ec32e6f46f63c6de342b6b4cab63bb8e6556bfb8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37198346"
---
# <a name="using-drillthrough-on-structure-data-basic-data-mining-tutorial"></a>Usando o detalhamento em dados de estrutura (Tutorial de mineração de dados básico)
  Como parte da sua campanha de propaganda, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] está enviando uma mala direta aos clientes potenciais em 34 a 40 anos demográficas. O departamento de marketing decidiu que eles também gostariam de enviar a mala direta aos clientes que compraram Bicicletas da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] há mais de cinco anos. Nesta lição, você identificará clientes com bicicletas mais antigas e irá recuperar suas informações de contato. Essas informações não estão incluídas no modelo, mas na estrutura. Para recuperar as informações de contato, primeiro você terá de garantir que o detalhamento esteja habilitado para a estrutura para depois usá-lo para revelar os nomes e os endereços dos clientes-alvo.  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a>Como habilitar o detalhamento em um modelo de mineração  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]diante a **modelos de mineração** guia do Designer de mineração de dados, clique com botão direito a **TM_Decision_Tree** de modelo e, em seguida, selecione **propriedades**.  
  
2.  Nas janelas Propriedades, clique em **AllowDrillthrough**e selecione **True**.  
  
3.  Na guia modelos de mineração, o modelo com o botão direito e selecione **modelo de processo**.  
  
 Para obter mais informações, consulte [consultas de detalhamento &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a>Para exibir dados de detalhamento de um modelo de mineração  
  
1.  No Designer de Mineração de Dados, clique na guia **Visualizador do Modelo de Mineração** .  
  
2.  Selecione o **TM_Decision_Tree** modelo da **modelo de mineração** lista.  
  
3.  Alterar o **plano de fundo** valor `1`. Assim, você mostra apenas a parte do modelo que está relacionada ao cliente que comprou bicicletas.  
  
4.  Selecione o Visualizador de Árvores da Microsoft na lista **Visualizador** . Isso forçará o visualizador a atualizar com as novas condições de filtro. Em seguida, localize o **idade > = 34 e < 41** nó e o botão direito do mouse no nó.  
  
5.  Selecione **Detalhar**e selecione **Colunas do Modelo e da Estrutura** para abrir a janela **Detalhar** .  
  
6.  Navegue até a coluna **Estrutura.Data da Primeira Compra** para exibir as datas de compra das bicicletas mais antigas.  
  
7.  Para copiar os dados para a Área de Transferência, clique com o botão direito do mouse na tabela e selecione **Copiar Tudo**.  
  
 Parabéns, você concluiu o tutorial de mineração de dados básico. Agora que você já está se sentindo confortável em usar as ferramentas de mineração de dados, recomendamos que conclua também o Tutorial de mineração de dados intermediário, que demonstra como criar modelos para previsão, análise de cesta básica e clustering de sequências.  
  
## <a name="previous-task-in-lesson"></a>Tarefa anterior da lição  
 [Criando previsões &#40;Tutorial de mineração de dados básicos&#41;](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Consulte também  
 [Criar uma consulta de previsão usando o Construtor de Consultas de previsão](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
