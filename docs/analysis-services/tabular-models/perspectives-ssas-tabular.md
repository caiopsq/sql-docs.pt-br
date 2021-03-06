---
title: Perspectivas | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 3e687116fa1f388da3b59884c29526cb9e7dd629
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34040514"
---
# <a name="perspectives"></a>Perspectivas
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  As perspectivas, em modelos tabulares, definem subconjuntos visíveis de um modelo que fornece pontos de vista concentrados, específicos à empresa ou específicos ao aplicativo.  
  
##  <a name="bkmk_understanding"></a> Benefícios  
 Os modelos tabulares podem ser muito complexos para usuários explorarem. Um único modelo pode representar o conteúdo de um data warehouse completo com muitas tabelas, medidas e dimensões. Essa complexidade pode ser difícil para usuários que precisam apenas interagir com uma pequena parte do modelo para satisfazer seus requisitos de Business Intelligence e geração de relatórios.  
  
 Em uma perspectiva, tabelas, colunas e medidas (inclusive KPIs) são definidas como objetos de campo. Você pode selecionar os campos exibíveis para cada perspectiva. Por exemplo, um único modelo pode conter dados de produto, de vendas, financeiros, de funcionários e geográficos. Enquanto um departamento de vendas precisa de dados de produto, vendas, promoções e geografia, não precisa de dados de funcionário e financeiros. De maneira semelhante, um departamento de recursos humanos não precisa de dados sobre promoções de vendas e geografia.  
  
 Quando um usuário se conectar a um modelo (como uma fonte de dados) com perspectivas definidas, o usuário poderá selecionar a perspectiva que deseja usar. Por exemplo, ao conectar-se a uma fonte de dados de modelo no Excel, os usuários de Recursos Humanos podem selecionar a perspectiva de Recursos Humanos na página Selecionar Tabelas e Exibições do Assistente de Conexão de dados. Somente campos (tabelas, colunas e medidas) definidos para a perspectiva de Recursos Humanos serão visíveis na Lista de Campos de Tabela Dinâmica.  
  
 As perspectivas não se destinam a serem usadas como um mecanismo de segurança, mas como uma ferramenta para fornecer uma melhor experiência. Toda a segurança de uma determinada perspectiva é herdada do modelo subjacente. As perspectivas não podem fornecer acesso a objetos de modelo aos quais o usuário ainda não tem acesso. A segurança para o banco de dados modelo deve ser resolvida antes que o acesso a objetos no modelo possa ser fornecido por meio de uma perspectiva. As funções de segurança podem ser usadas para proteger metadados e dados do modelo. Para obter mais informações, consulte [funções](../../analysis-services/tabular-models/roles-ssas-tabular.md).  
  
##  <a name="bkmk_testpersp"></a> Testing perspectives  
 Ao criar um modelo, você pode usar o recurso Analisar no Excel no designer de modelo para testar a eficácia das perspectivas que você definiu. No menu **Modelo** no designer de modelo, quando você clica em **Analisar no Excel**, antes de o Excel abrir, a caixa de diálogo **Escolher Credenciais e Perspectiva** é aberta. Nesta caixa de diálogo, você pode especificar o usuário atual, um nome de usuário diferente, uma função e uma perspectiva que você usará para se conectar ao banco de dados do espaço de trabalho modelo como uma fonte de dados e exibir os dados.  
  
##  <a name="bkmk_related_tasks"></a> Related tasks  
  
|Tópico|Description|  
|-----------|-----------------|  
|[Criar e gerenciar perspectivas](../../analysis-services/tabular-models/create-and-manage-perspectives-ssas-tabular.md)|Descreve como criar e gerenciar perspectivas usando a caixa de diálogo Perspectivas no designer de modelo.|  
  
## <a name="see-also"></a>Consulte também  
 [Funções](../../analysis-services/tabular-models/roles-ssas-tabular.md)   
 [Hierarquias](../../analysis-services/tabular-models/hierarchies-ssas-tabular.md)  
  
  
