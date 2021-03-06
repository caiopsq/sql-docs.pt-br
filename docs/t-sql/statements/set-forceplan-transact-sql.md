---
title: SET FORCEPLAN (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/26/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- SET_FORCEPLAN_TSQL
- SET FORCEPLAN
- FORCEPLAN
- FORCEPLAN_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- joins [SQL Server], overriding query optimizer process
- FORCEPLAN option
- SET FORCEPLAN statement
- query optimizer [SQL Server], optimizing process
- overriding query optimizer process
ms.assetid: b6c0b08f-2060-4696-9e12-50cb7e674321
caps.latest.revision: 40
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 2b52ce303c0d4fe2cb1fdd9338426400656e5e5d
ms.sourcegitcommit: 05e18a1e80e61d9ffe28b14fb070728b67b98c7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/04/2018
ms.locfileid: "37781137"
---
# <a name="set-forceplan-transact-sql"></a>SET FORCEPLAN (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Quando FORCEPLAN está definido como ON, o otimizador de consulta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processa uma ligação na mesma ordem conforme as tabelas são exibidas na cláusula FROM de uma consulta. Além disso, configurar FORCEPLAN como ON força o uso de uma junção de loop aninhado, a não ser que outros tipos de junção sejam necessários ao construir um plano para a consulta ou eles sejam solicitados com dicas de junção ou dicas de consulta.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
SET FORCEPLAN { ON | OFF }  
```  
  
## <a name="remarks"></a>Remarks  
 SET FORCEPLAN basicamente substitui a lógica usada pelo otimizador de consulta para processar uma instrução SELECT [!INCLUDE[tsql](../../includes/tsql-md.md)]. Os dados retornados pela instrução SELECT são os mesmos independentemente dessa configuração. A única diferença é o modo pelo qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processa as tabelas para satisfazer a consulta.  
  
 Também podem ser usadas dicas do otimizador de consulta em consultas para afetar a forma como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processa a instrução SELECT.  
  
 SET FORCEPLAN é aplicado na execução ou em tempo de execução e não no momento da análise.  
  
## <a name="permissions"></a>Permissões  
 Permissões de SET FORCEPLAN assumem como padrão todos os usuários.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir executa uma junção de quatro tabelas. A configuração `SHOWPLAN_TEXT` está habilitada, portanto o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna as informações sobre como o processamento da consulta é diferente depois de habilitar a configuração `SET FORCE_PLAN`.  
  
```  
USE AdventureWorks2012;  
GO  
-- Make sure FORCEPLAN is set to OFF.  
SET SHOWPLAN_TEXT OFF;  
GO  
SET FORCEPLAN OFF;  
GO  
SET SHOWPLAN_TEXT ON;  
GO  
-- Example where the query plan is not forced.  
SELECT p.LastName, p.FirstName, v.Name  
FROM Person.Person AS p  
   INNER JOIN HumanResources.Employee AS e  
   ON e.BusinessEntityID = p.BusinessEntityID  
   INNER JOIN Purchasing.PurchaseOrderHeader AS poh  
   ON e.BusinessEntityID = poh.EmployeeID  
   INNER JOIN Purchasing.Vendor AS v  
   ON poh.VendorID = v.BusinessEntityID;  
GO  
-- SET FORCEPLAN to ON.  
SET SHOWPLAN_TEXT OFF;  
GO  
SET FORCEPLAN ON;  
GO  
SET SHOWPLAN_TEXT ON;  
GO  
-- Reexecute inner join to see the effect of SET FORCEPLAN ON.  
SELECT p.LastName, p.FirstName, v.Name  
FROM Person.Person AS p  
   INNER JOIN HumanResources.Employee AS e   
   ON e.BusinessEntityID = p.BusinessEntityID  
   INNER JOIN Purchasing.PurchaseOrderHeader AS poh  
   ON e.BusinessEntityID = poh.EmployeeID  
   INNER JOIN Purchasing.Vendor AS v  
   ON poh.VendorID = v.BusinessEntityID;  
GO  
SET SHOWPLAN_TEXT OFF;  
GO  
SET FORCEPLAN OFF;  
GO  
```  
  
## <a name="see-also"></a>Consulte Também  
 [SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [Instruções SET &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)   
 [SET SHOWPLAN_ALL &#40;Transact-SQL&#41;](../../t-sql/statements/set-showplan-all-transact-sql.md)   
 [SET SHOWPLAN_TEXT &#40;Transact-SQL&#41;](../../t-sql/statements/set-showplan-text-transact-sql.md)  
  
  
