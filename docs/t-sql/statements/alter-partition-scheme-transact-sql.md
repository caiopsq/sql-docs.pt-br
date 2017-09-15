---
title: "ALTERAR o esquema de partição (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER PARTITION SCHEME
- ALTER_PARTITION_SCHEME_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ALTER PARTITION SCHEME statement
- partition schemes [SQL Server], modifying
- modifying partition schemes
- adding filegroups
- NEXT USED filegroups
ms.assetid: f01d6880-9800-4cfb-8d11-d4be21efc8ca
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 545fe3da48f0d0c98d72b32e5a82d9fd55579d00
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="alter-partition-scheme-transact-sql"></a>ALTER PARTITION SCHEME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Adiciona um grupo de arquivos a um esquema de partição ou altera a designação do grupo de arquivos NEXT USED para o esquema de partição.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
ALTER PARTITION SCHEME partition_scheme_name   
NEXT USED [ filegroup_name ] [ ; ]  
```  
  
## <a name="arguments"></a>Argumentos  
 *partition_scheme_name*  
 É o nome do esquema de partição a ser alterado.  
  
 *filegroup_name*  
 Especifica o grupo de arquivos a ser marcado pelo esquema de partição como NEXT USED. Isso significa que o grupo de arquivos aceitará uma nova partição é criada usando um [ALTER PARTITION FUNCTION](../../t-sql/statements/alter-partition-function-transact-sql.md) instrução.  
  
 Em um esquema de partição, somente um grupo de arquivos pode ser designado como NEXT USED. Um grupo de arquivos que não está vazio pode ser especificado. Se *filegroup_name* for especificado e atualmente não há nenhum grupo de arquivos marcado como NEXT USED *filegroup_name* é marcado como NEXT USED. Se *filegroup_name* for especificado e um grupo de arquivos com a propriedade NEXT USED já existe, a propriedade NEXT USED transfere do grupo de arquivos existente para *filegroup_name*.  
  
 Se *filegroup_name* não for especificado e um grupo de arquivos com a propriedade NEXT USED já existe, o grupo de arquivos perderá seu estado NEXT USED para que não haja nenhum grupo de arquivos NEXT USED em *partition_scheme_name*.  
  
 Se *filegroup_name* não for especificado e não há nenhum grupo de arquivos marcado como NEXT USED, ALTER PARTITION SCHEME retornará um aviso.  
  
## <a name="remarks"></a>Comentários  
 Qualquer grupo de arquivos afetado por ALTER PARTITION SCHEME deve estar online.  
  
## <a name="permissions"></a>Permissões  
 Seção permissões a seguir podem ser usadas para executar ALTER PARTITION SCHEME:  
  
-   Permissão ALTER ANY DATASPACE. Essa permissão tem como padrão os membros da função de servidor fixa **sysadmin** e das funções de banco de dados fixas **db_owner** e **db_ddladmin** .  
  
-   Permissão CONTROL ou ALTER no banco de dados no qual o esquema de partição foi criado.  
  
-   Permissão CONTROL SERVER ou ALTER ANY DATABASE no servidor do banco de dados no qual o esquema de partição foi criado.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir assume o esquema de partição `MyRangePS1` e o grupo de arquivos `test5fg` existe no banco de dados atual.  
  
```  
ALTER PARTITION SCHEME MyRangePS1  
NEXT USED test5fg;  
```  
  
 O grupo de arquivos `test5fg` receberá qualquer partição adicional de uma tabela ou índice particionado como resultado de uma instrução ALTER PARTITION FUNCTION.  
  
## <a name="see-also"></a>Consulte também  
 [CREATE PARTITION SCHEME &#40;Transact-SQL&#41;](../../t-sql/statements/create-partition-scheme-transact-sql.md)   
 [REMOVER o esquema de partição &#40; Transact-SQL &#41;](../../t-sql/statements/drop-partition-scheme-transact-sql.md)   
 [CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;](../../t-sql/statements/create-partition-function-transact-sql.md)   
 [ALTER PARTITION FUNCTION &#40; Transact-SQL &#41;](../../t-sql/statements/alter-partition-function-transact-sql.md)   
 [DROP PARTITION FUNCTION &#40; Transact-SQL &#41;](../../t-sql/statements/drop-partition-function-transact-sql.md)   
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [sys. partition_schemes &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-partition-schemes-transact-sql.md)   
 [data_spaces &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-data-spaces-transact-sql.md)   
 [sys.destination_data_spaces &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-destination-data-spaces-transact-sql.md)   
 [sys. Partitions &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-partitions-transact-sql.md)   
 [sys.tables &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-tables-transact-sql.md)   
 [sys.indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)   
 [sys.index_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-index-columns-transact-sql.md)  
  
  