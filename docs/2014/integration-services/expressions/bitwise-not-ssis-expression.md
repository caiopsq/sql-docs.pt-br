---
title: ~ (Não bit a bit) (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- bitwise NOT (~)
- ~ (bitwise NOT)
ms.assetid: e4413ddd-0d0e-40c3-9c76-b5ce323218ec
caps.latest.revision: 31
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f422eb2e9b75e7488cff9ceaa089954595d00313
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37231486"
---
# <a name="-bitwise-not-ssis-expression"></a>~ (Não de bit a bit) (Expressão SSIS)
  Executa uma negação bit a bit de um inteiro. Esse operador pode ser se aplicado a tipos de dados inteiro assinados e não assinados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
~integer_expression  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *integer_expression*  
 É qualquer expressão válida de um tipo de dados inteiro. *integer*_*expression* é um inteiro que é transformado em um número binário para a operação bit a bit. Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).  
  
## <a name="result-types"></a>Tipos de resultado  
 Retorna o tipo de dados de *integer_expression.*  
  
## <a name="remarks"></a>Remarks  
 Nenhum  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Esse exemplo executa uma operação ~ (NOT) bit a bit no número 170 (0000 0000 1010 1010). O número é um inteiro assinado.  
  
```  
  
~ 170  
```  
  
 A expressão é avaliada como -170 (1111111101010101).  
  
 0000000010101010  
  
 ---------------------\-  
  
 1111111101010101  
  
## <a name="see-also"></a>Consulte também  
 [Associatividade e precedência de operador](operator-precedence-and-associativity.md)   
 [Operadores &#40;expressão do SSIS&#41;](operators-ssis-expression.md)  
  
  
