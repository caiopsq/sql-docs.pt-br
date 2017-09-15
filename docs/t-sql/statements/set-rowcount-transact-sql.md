---
title: SET ROWCOUNT (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SET_ROWCOUNT_TSQL
- ROWCOUNT_TSQL
- SET ROWCOUNT
- ROWCOUNT
dev_langs:
- TSQL
helpviewer_keywords:
- row return limitations [SQL Server]
- SET ROWCOUNT statement
- number of rows affected by statement
- ROWCOUNT option
- counting rows
- stopping queries
- limiting rows returned
- queries [SQL Server], stopping
ms.assetid: c6966fb7-6421-47ef-98f3-82351f2f6bdc
caps.latest.revision: 43
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: eda7f9faf2bb45b06cf1112dbe48cbdb281fdab3
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="set-rowcount-transact-sql"></a>SET ROWCOUNT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Faz o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parar o processamento de consulta depois que o número especificado de linhas for retornado.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
SET ROWCOUNT { number | @number_var }   
```  
  
## <a name="arguments"></a>Argumentos  
 *número* | @*number_var*  
 É o número inteiro de filas a serem processadas antes de finalizar a consulta específica.  
  
## <a name="remarks"></a>Comentários  
  
> [!IMPORTANT]  
>  O uso de SET ROWCOUNT não afetará as instruções DELETE, INSERT e UPDATE em uma futura versão do SQL Server. Evite usar SET ROWCOUNT com instruções DELETE, INSERT e UPDATE em um novo trabalho de desenvolvimento e planeje modificar os aplicativos que a utilizam atualmente. Para um comportamento semelhante, use a sintaxe de TOP. Para obter mais informações, consulte [TOP &#40; Transact-SQL &#41; ](../../t-sql/queries/top-transact-sql.md).  
  
 Para desligar esta opção de forma que todas as linhas sejam retornadas, especifique SET ROWCOUNT 0.  
  
 A configuração da opção SET ROWCOUNT faz com que a maioria das instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] parem de processar quando forem afetadas pelo número de linhas especificado. Isso inclui gatilhos. A opção ROWCOUNT não afeta cursores dinâmicos, mas limita o conjunto de linhas de conjunto de chaves e cursores sem distinção. Essa opção deve ser usada com cuidado.  
  
 SET ROWCOUNT substituirá a palavra-chave TOP da instrução SELECT TOP se o número de linhas for o menor valor.  
  
 A configuração de SET ROWCOUNT é definida no momento da execução ou em tempo de execução e não no momento da análise.  
  
## <a name="permissions"></a>Permissões  
 Requer associação à função public.  
  
## <a name="examples"></a>Exemplos  
 SET ROWCOUNT para de processar depois do número especificado de linhas. No exemplo a seguir, observe que mais de 500 linhas atendem aos critérios de `Quantity` menor que `300`. Porém, depois de aplicar SET ROWCOUNT, você pode ver que nem todas as linhas foram retornadas.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT count(*) AS Count  
FROM Production.ProductInventory  
WHERE Quantity < 300;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Count`  
  
 `-----------`  
  
 `537`  
  
 `(1 row(s) affected)`  
  
 Agora, defina `ROWCOUNT` como `4` e retorne todas as linhas para demonstrar que apenas quatro linhas são retornadas.  
  
```  
SET ROWCOUNT 4;  
SELECT *  
FROM Production.ProductInventory  
WHERE Quantity < 300;  
GO  
```  
  
 `(4 row(s) affected)`  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 SET ROWCOUNT para de processar depois do número especificado de linhas. No exemplo a seguir, observe que mais de 20 linhas atendem aos critérios de `AccountType = 'Assets'`. Porém, depois de aplicar SET ROWCOUNT, você pode ver que nem todas as linhas foram retornadas.  
  
```  
-- Uses AdventureWorks  
  
SET ROWCOUNT 5;  
SELECT * FROM [dbo].[DimAccount]  
WHERE AccountType = 'Assets';  
```  
  
 Para retornar todas as linhas, defina o número de linhas como 0.  
  
```  
-- Uses AdventureWorks  
  
SET ROWCOUNT 0;  
SELECT * FROM [dbo].[DimAccount]  
WHERE AccountType = 'Assets';  
```  
  
## <a name="see-also"></a>Consulte também  
 [Instruções SET &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
  
  

