---
title: sys.dm_io_pending_io_requests (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_io_pending_io_requests
- dm_io_pending_io_requests
- dm_io_pending_io_requests_TSQL
- sys.dm_io_pending_io_requests_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_io_pending_io_requests dynamic management view
ms.assetid: d1fb46dd-5c74-4c04-9ecf-8934b1bedb5b
caps.latest.revision: 26
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 6607db0d4907206936ab952a5b559ac9055a79aa
ms.sourcegitcommit: b70b99c2e412b4d697021f3bf1a92046aafcbe37
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2018
ms.locfileid: "40392228"
---
# <a name="sysdmiopendingiorequests-transact-sql"></a>sys.dm_io_pending_io_requests (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retorna uma linha para cada solicitação de E/S pendente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!NOTE]  
>  Chamá-lo partir [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], use o nome **sys.dm_pdw_nodes_io_pending_io_requests**.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**io_completion_request_address**|**varbinary(8)**|Endereço de memória da solicitação de E/S. Não permite valor nulo.|  
|**io_type**|**varchar(7)**|Tipo de solicitação de E/S pendente. Não permite valor nulo.|  
|**io_pending**|**int**|Indica se a solicitação de E/S está pendente ou foi concluída pelo Windows. Uma solicitação de E/S ainda pode ficar pendente mesmo que o Windows a conclua, caso o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não execute uma opção de contexto que processe a solicitação de E/S e a remova da lista. Não permite valor nulo.|  
|**io_completion_routine_address**|**varbinary(8)**|Função interna a ser chamada quando a solicitação de E/S é concluída. Permite valor nulo.|  
|**io_user_data_address**|**varbinary(8)**|Somente para uso interno. Permite valor nulo.|  
|**scheduler_address**|**varbinary(8)**|Agendador no qual esta solicitação de E/S foi emitida. A solicitação de E/S será exibida na lista de E/S pendente do agendador. Para obter mais informações, consulte [DM os_schedulers &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-schedulers-transact-sql.md). Não permite valor nulo.|  
|**io_handle**|**varbinary(8)**|Identificador de arquivo do arquivo usado na solicitação de E/S. Permite valor nulo.|  
|**io_offset**|**bigint**|Deslocamento da solicitação de E/S. Não permite valor nulo.|  
|**io_pending_ms_ticks**|**int**|Somente para uso interno. Não permite valor nulo.|  
|**pdw_node_id**|**int**|**Aplica-se ao**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)], [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> O identificador para o nó que essa distribuição é no.|  
  
## <a name="permissions"></a>Permissões  

Na [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], requer `VIEW SERVER STATE` permissão.   
Na [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)], requer o `VIEW DATABASE STATE` permissão no banco de dados.   
  
## <a name="see-also"></a>Consulte também  
 [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Eu O relacionadas a funções e exibições de gerenciamento dinâmico &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/i-o-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  


