---
title: TRIM (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/20/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- TRIM
- TRIM_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- TRIM function
ms.assetid: a00245aa-32c7-4ad4-a0d1-64f3d6841153
caps.latest.revision: 4
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2017||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 82a4fcce1764cf8bdb07db18366847fbe8e1cd57
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39451140"
---
# <a name="trim-transact-sql"></a>TRIM (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2017-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-asdb-xxxx-xxx-md.md)]

Remove o caractere de espaço `char(32)` ou outros caracteres especificados do início ou final de uma cadeia de caracteres.  
 
## <a name="syntax"></a>Sintaxe   
```
TRIM ( [ characters FROM ] string ) 
```
[//]: # "[ BOTH | LEADING | TRAILING ] ainda não disponíveis."

## <a name="arguments"></a>Argumentos   

characters   
É um literal, uma variável ou uma chamada de função de qualquer tipo de caractere não LOB (`nvarchar`, `varchar`, `nchar` ou `char`) que contém caracteres que devem ser removidos. Os tipos `nvarchar(max)` e `varchar(max)` não são permitidos.

cadeia de caracteres   
É uma expressão de qualquer tipo de caractere (`nvarchar`, `varchar`, `nchar` ou `char`) na qual os caracteres devem ser removidos.

## <a name="return-types"></a>Tipos de retorno   
Retorna uma expressão de caractere com um tipo de argumento de cadeia de caracteres na qual o caractere de espaço `char(32)` ou outros caracteres especificados são removidos de ambos os lados. Retorna `NULL` se a cadeia de caracteres de entrada é `NULL`.

## <a name="remarks"></a>Remarks   
Por padrão, a função `TRIM` remove o caractere de espaço `char(32)` de ambos os lados. Isso é equivalente a `LTRIM(RTRIM(@string))`. O comportamento da função `TRIM ` com os caracteres especificados é idêntico ao comportamento da função `REPLACE`, em que os caracteres do início ou final são substituídos por cadeias de caracteres vazias.


## <a name="examples"></a>Exemplos
### <a name="a--removes-the-space-character-from-both-sides-of-string"></a>A.  Remove o caractere de espaço de ambos os lados da cadeia de caracteres   
O exemplo a seguir remove os espaços antes e depois da palavra `test`.   
```sql
SELECT TRIM( '     test    ') AS Result;
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]   

`test`


### <a name="b--removes-specified-characters-from-both-sides-of-string"></a>B.  Remove caracteres especificados de ambos os lados da cadeia de caracteres   
O exemplo a seguir remove um ponto à direita e espaços à direita.
```sql
SELECT TRIM( '.,! ' FROM  '#     test    .') AS Result;
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]   
`#     test`


## <a name="see-also"></a>Consulte Também
 [LEFT &#40;Transact-SQL&#41;](../../t-sql/functions/left-transact-sql.md)  
 [LTRIM &#40;Transact-SQL&#41;](../../t-sql/functions/ltrim-transact-sql.md)  
 [RIGHT &#40;Transact-SQL&#41;](../../t-sql/functions/right-transact-sql.md)  
 [RTRIM &#40;Transact-SQL&#41;](../../t-sql/functions/rtrim-transact-sql.md)  
 [STRING_SPLIT &#40;Transact-SQL&#41;](../../t-sql/functions/string-split-transact-sql.md)  
 [SUBSTRING &#40;Transact-SQL&#41;](../../t-sql/functions/substring-transact-sql.md)  
 [Funções de cadeia de caracteres &#40;Transact-SQL&#41;](../../t-sql/functions/string-functions-transact-sql.md)   
