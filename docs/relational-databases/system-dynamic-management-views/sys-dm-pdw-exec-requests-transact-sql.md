---
title: sys.dm_pdw_exec_requests (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: ''
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.reviewer: ''
ms.suite: sql
ms.component: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 390225cc-23e8-4051-a5f6-221e33e4c0b4
author: ronortloff
ms.author: rortloff
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 966fbd2efde6934f8cfe1b59706dec27b92e301e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37980677"
---
# <a name="sysdmpdwexecrequests-transact-sql"></a>sys.dm_pdw_exec_requests (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Contém informações sobre todas as solicitações ativas no momento ou recentemente em [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]. Ele lista uma linha por solicitação/consulta.  
  
|Nome da coluna|Tipo de dados|Description|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|request_id|**nvarchar(32)**|A chave para este modo de exibição. Id numérico exclusivo associado com a solicitação.|Exclusivo entre todas as solicitações no sistema.|  
|session_id|**nvarchar(32)**|Id numérico exclusivo associado à sessão em que essa consulta foi executada. Ver [DM pdw_exec_sessions &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-sessions-transact-sql.md).||  
|status|**nvarchar(32)**|Status atual da solicitação.|'Running', 'Suspenso', 'Concluído', 'Cancelado', 'Falha'.|  
|submit_time|**datetime**|Hora em que a solicitação foi enviada para execução.|Válido **datetime** menor ou igual à hora atual e start_time.|  
|start_time|**datetime**|Hora em que a execução da solicitação foi iniciada.|NULL para solicitações em fila; Caso contrário, válido **datetime** menor ou igual à hora atual.|  
|end_compile_time|**datetime**|Hora em que o mecanismo concluiu a solicitação de compilação.|NULL para solicitações que não foram compilados ainda; Caso contrário, válido **datetime** menor do que start_time e menor ou igual à hora atual.|
|end_time|**datetime**|Hora em que a execução da solicitação concluído, falhou ou foi cancelada.|NULL para solicitações em fila ou do Active Directory; Caso contrário, válido **datetime** menor ou igual à hora atual.|  
|total_elapsed_time|**int**|Tempo decorrido na execução desde que a solicitação foi iniciada, em milissegundos.|Entre 0 e a diferença entre start_time e end_time.<br /><br /> Se total_elapsed_time exceder o valor máximo para um número inteiro, o total_elapsed_time continuará a ser o valor máximo. Essa condição gerará o aviso "o valor máximo foi excedido."<br /><br /> O valor máximo em milissegundos é equivalente a 24,8 dias.|  
|rótulo|**nvarchar(255)**|Cadeia de caracteres de rótulo opcional associada com algumas instruções de consulta SELECT.|Qualquer cadeia de caracteres que contém 'a-z', 'A-Z','0-9', '_'.|  
|error_id|**nvarchar(36)**|Id exclusiva do erro associado à solicitação, se houver.|Ver [sys.dm_pdw_errors &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-errors-transact-sql.md); definido como NULL se nenhum erro tiver ocorrido.|  
|database_id|**int**|Identificador do banco de dados usado pelo contexto explícito (por exemplo, USE DB_X).|Consulte a id na [sys. Databases &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md).|  
|command|**nvarchar(4000)**|Contém o texto completo da solicitação enviado pelo usuário.|Qualquer texto de consulta ou de solicitação válido. Consultas que têm mais de 4000 bytes são truncadas.|  
|resource_class|**nvarchar(20)**|A classe de recurso para esta solicitação. Consulte relacionados **concurrency_slots_used** na [sys.dm_pdw_resource_waits &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-resource-waits-transact-sql.md).|SmallRC<br /><br /> MediumRC<br /><br /> LargeRC<br /><br /> XLargeRC|  
  
 Para obter informações sobre o máximo de linhas mantido por esta exibição, consulte "Mínimo e máximo valores" no [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão VIEW SERVER STAT.  
  
## <a name="security"></a>Segurança  
 DM pdw_exec_requests não filtra os resultados de consulta de acordo com as permissões específicas do banco de dados. Logons com permissão VIEW SERVER STATE podem obter resultados resultados da consulta para todos os bancos de dados  
  
> [!WARNING]  
>  Um invasor pode usar DM pdw_exec_requests para recuperar informações sobre objetos de banco de dados específico, basta ter a permissão VIEW SERVER STATE e por não ter uma permissão de banco de dados específico.  
  
## <a name="see-also"></a>Consulte também  
 [SQL Data Warehouse e Parallel Data Warehouse exibições de gerenciamento dinâmico &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
