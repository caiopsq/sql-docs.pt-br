---
title: sys.dm_xe_database_session_object_columns (banco de dados SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: ''
ms.prod_service: sql-database
ms.reviewer: ''
ms.service: sql-database
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
ms.assetid: 0e6adc54-4d97-4ef0-bf4f-b4538d69f136
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: 863b6d2c274c76919455a4ea68ba0e944d64f16e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38029402"
---
# <a name="sysdmxedatabasesessionobjectcolumns-azure-sql-database"></a>sys.dm_xe_database_session_object_columns (banco de dados SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

  Mostra os valores de configuração de objetos associados a uma sessão.  
  
||  
|-|  
|**Aplica-se ao**: [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] V12 e versões posteriores.|  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|event_session_address|**varbinary(8)**|O endereço da memória da sessão de evento. Tem uma relação muitos-para-um com sys.dm_xe_database_sessions.address. Não permite valor nulo.|  
|column_name|**nvarchar(60)**|O nome do valor de configuração. Não permite valor nulo.|  
|column_id|**int**|A ID da coluna. É exclusiva no objeto. Não permite valor nulo.|  
|column_value|**nvarchar(2048)**|O valor configurado da coluna. Permite valor nulo.|  
|object_type|**nvarchar(60)**|O tipo do objeto.  Não é nullable.object_type é um dos:<br /><br /> event<br /><br /> target|  
|object_name|**nvarchar(60)**|O nome do objeto ao qual a coluna pertence. Não permite valor nulo.|  
|object_package_guid|**uniqueidentifier**|O GUID do pacote que contém o objeto. Não permite valor nulo.|  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão VIEW DATABASE STATE.  
  
### <a name="relationship-cardinalities"></a>Cardinalidades de relações  
  
|De|Para|Relação|  
|----------|--------|------------------|  
|dm_xe_database_session_object_columns.object_name<br /><br /> dm_xe_database_session_object_columns.object_package_guid|sys.dm_xe_objects.package_guid<br /><br /> sys.dm_xe_objects.name|Muitos para um|  
|dm_xe_database_session_object_columns.column_name<br /><br /> dm_xe_database_session_object_columns.column_id|sys.dm_xe_object_columns.name<br /><br /> sys.dm_xe_object_columns.column_id|Muitos para um|  
  
## <a name="see-also"></a>Consulte também  
 [Eventos estendidos](../../relational-databases/extended-events/extended-events.md)  
  
  
