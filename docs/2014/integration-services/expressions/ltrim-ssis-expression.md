---
title: LTRIM (Expressão SSIS) | Microsoft Docs
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
- leading blanks
- LTRIM function
ms.assetid: d082f42a-d7e7-49f5-a503-ac44ba630832
caps.latest.revision: 33
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 57270915299162ce45558dda7f8c44d56520082e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205726"
---
# <a name="ltrim-ssis-expression"></a>LTRIM (Expressão SSIS)
  Retorna uma expressão de caractere depois de remover espaços em branco à esquerda.  
  
> [!NOTE]  
>  LTRIM não remove caracteres do espaço em branco como os caracteres de guia ou de alimentação de linha. Unicode fornece pontos de código para muitos tipos diferentes de espaços, mas essa função reconhece somente o ponto de código Unicode 0x0020. Quando as cadeias de caracteres de DBCS (Conjunto de caracteres de byte duplo) são convertidas para Unicode, elas podem incluir caracteres de espaço diferentes de 0x0020, e a função não pode remover esses espaços. Para remover todos os tipos de espaços, você poderá usar o método LTrim do Microsoft Visual Basic .NET em uma execução de script a partir do componente Script.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
LTRIM(character expression)  
```  
  
## <a name="arguments"></a>Argumentos  
 *character_expression*  
 É uma expressão de caractere da qual remover espaços.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_WSTR  
  
## <a name="remarks"></a>Remarks  
 LTRIM só funciona com o tipo de dados DT_WSTR. Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes de LTRIM executar sua operação. Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR. Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).  
  
 LTRIM retornará um resultado nulo se o argumento for nulo.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Este exemplo remove espaços à esquerda de um literal de cadeia de caracteres. O resultado de retorno é "Hello".  
  
```  
LTRIM("    Hello")  
```  
  
 Este exemplo remove espaços à esquerda da coluna **FirstName** .  
  
```  
LTRIM(FirstName)  
```  
  
 Este exemplo remove os espaços à esquerda da variável **FirstName** .  
  
```  
LTRIM(@FirstName)  
```  
  
## <a name="see-also"></a>Consulte também  
 [RTRIM &#40;expressão do SSIS&#41;](trim-ssis-expression.md)   
 [TRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md)   
 [Funções &#40;expressão do SSIS&#41;](functions-ssis-expression.md)  
  
  
