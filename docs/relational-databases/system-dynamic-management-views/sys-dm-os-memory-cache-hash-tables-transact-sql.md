---
title: sys.dm_os_memory_cache_hash_tables (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_os_memory_cache_hash_tables_TSQL
- sys.dm_os_memory_cache_hash_tables
- dm_os_memory_cache_hash_tables
- dm_os_memory_cache_hash_tables_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_memory_cache_hash_tables dynamic management view
ms.assetid: 68b94f35-8f80-4d2b-bcde-7a21934219af
caps.latest.revision: 25
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: d1b533613840f34356858547d273965dcfd9361e
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39555486"
---
# <a name="sysdmosmemorycachehashtables-transact-sql"></a>sys.dm_os_memory_cache_hash_tables (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retorna uma linha para cada cache ativo na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!NOTE]  
>  Chamá-lo partir [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], use o nome **sys.dm_pdw_nodes_os_memory_cache_hash_tables**.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**cache_address**|**varbinary(8)**|Endereço (chave primária) da entrada de cache. Não permite valor nulo.|  
|**name**|**nvarchar(256)**|Nome do cache. Não permite valor nulo.|  
|**type**|**nvarchar(60)**|Tipo de cache. Não permite valor nulo.|  
|**table_level**|**int**|Número da tabela hash. Um cache específico pode ter várias tabelas hash que correspondem a funções hash diferentes. Não permite valor nulo.|  
|**buckets_count**|**int**|Número de partições de memória na tabela hash. Não permite valor nulo.|  
|**buckets_in_use_count**|**int**|Número de partições de memória que estão sendo usadas atualmente. Não permite valor nulo.|  
|**buckets_min_length**|**int**|Número mínimo de entradas de cache em uma partição de memória. Não permite valor nulo.|  
|**buckets_max_length**|**int**|Número máximo de entradas de cache em uma partição de memória. Não permite valor nulo.|  
|**buckets_avg_length**|**int**|Número médio de entradas de cache em cada partição de memória. Não permite valor nulo.|  
|**buckets_max_length_ever**|**int**|Número máximo de entradas em cache em uma partição de memória hash para esta tabela hash, desde que o servidor foi iniciado. Não permite valor nulo.|  
|**hits_count**|**bigint**|Número de acertos do cache. Não permite valor nulo.|  
|**misses_count**|**bigint**|Número de ausências de cache. Não permite valor nulo.|  
|**buckets_avg_scan_hit_length**|**int**|Número médio de entradas examinadas em uma partição de memória antes de um item pesquisado ser localizado. Não permite valor nulo.|  
|**buckets_avg_scan_miss_length**|**int**|Número médio de entradas examinadas em uma partição de memória antes do encerramento sem-êxito da pesquisa. Não permite valor nulo.|  
|**pdw_node_id**|**int**|O identificador para o nó que essa distribuição é no.<br /><br /> **Aplica-se ao**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)], [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]|  
  
## <a name="permissions"></a>Permissões 

Na [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], requer `VIEW SERVER STATE` permissão.   
Na [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)], requer o `VIEW DATABASE STATE` permissão no banco de dados.   

## <a name="see-also"></a>Consulte também  
 
  [Sistema operacional SQL Server relacionados exibições de gerenciamento dinâmico &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  


