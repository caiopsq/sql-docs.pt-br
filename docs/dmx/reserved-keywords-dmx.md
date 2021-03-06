---
title: Palavras-chave (DMX) reservadas | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 7af060203d044435e364803ace67d35711eb63ea
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37985308"
---
# <a name="reserved-keywords-dmx"></a>Palavras-chave reservadas (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASversion2005](../includes/ssasversion2005-md.md)] reserva determinadas palavras-chave para seu uso exclusivo. Essas palavras-chave não podem ser usadas em nenhum lugar nas instruções DMX (Data Mining Extensions), exceto nas posições que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] define na referência de linguagem DMX. As palavras-chave restritas de DMX incluem os seguintes membros:  
  
-   Todas as instruções de definição de dados listados no tópico [instruções de definição de dados DMX](../dmx/dmx-statements-data-definition.md).  
  
-   Todos os dados listadas no tópico de funções de consulta de mineração [referência de função DMX](../dmx/data-mining-extensions-dmx-function-reference.md).  
  
-   Todos os operadores listados no tópico [referência de operador DMX](../dmx/data-mining-extensions-dmx-operator-reference.md).  
  
-   Palavras-chave definidas em linguagem de consulta MDX (Multidimensional Expressions) e que são incluídas como parte de uma instrução DMX.  
  
-   Palavras-chave definidas na especificação do OLE DB for Data Mining e que são incluídas como parte de uma instrução DMX.  
  
 Quando objetos são nomeados em um banco de dados, é recomendado usar uma convenção de nomeação que evite o uso de palavras-chave reservadas.  
  
 Caso o banco de dados não contenha nomes que correspondam às palavras-chave reservadas, será preciso usar identificadores delimitados para fazer referência a esses objetos. Para obter mais informações, consulte [identificadores &#40;DMX&#41;](../dmx/identifiers-dmx.md).  
  
## <a name="see-also"></a>Consulte também  
 [Extensões de mineração de dados &#40;DMX&#41; referência](../dmx/data-mining-extensions-dmx-reference.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de instrução](../dmx/data-mining-extensions-dmx-statements.md)   
 [Extensões de mineração de dados &#40;DMX&#41; convenções de sintaxe](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Extensões de mineração de dados &#40;DMX&#41; elementos de sintaxe](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Compreendendo a instrução DMX Select](../dmx/understanding-the-dmx-select-statement.md)  
  
  
