---
title: sys. foreign_keys (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- foreign_keys
- sys.foreign_keys
- sys.foreign_keys_TSQL
- foreign_keys_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.foreign_keys catalog view
ms.assetid: e960df1a-13fc-43ee-ba91-34c1b719ac2c
caps.latest.revision: 37
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 58dcea9a85120f412aaba42786b6c95bbed8850e
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39557676"
---
# <a name="sysforeignkeys-transact-sql"></a>sys.foreign_keys (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Contém uma linha para cada objeto que é uma restrição FOREIGN KEY, com **sys.object.type** = F.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**\<Colunas herdadas de sys. Objects >**||Para obter uma lista de colunas que essa exibição herda valores, consulte [sys. Objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).|  
|**referenced_object_id**|**int**|ID do objeto referenciado.|  
|**key_index_id**|**int**|ID do índice de chave no objeto referenciado.|  
|**is_disabled**|**bit**|A restrição FOREIGN KEY foi desabilitada.|  
|**is_not_for_replication**|**bit**|A restrição FOREIGN KEY foi criada com o uso da opção NOT FOR REPLICATION.|  
|**is_not_trusted**|**bit**|A restrição FOREIGN KEY não foi verificada pelo sistema.|  
|**delete_referential_action**|**tinyint**|A ação referencial declarada para esse FOREIGN KEY quando ocorre uma exclusão.<br /><br /> 0 = Nenhuma ação<br /><br /> 1 = Cascata<br /><br /> 2 = Definido como nulo<br /><br /> 3 = Definir como padrão|  
|**delete_referential_action_desc**|**nvarchar(60)**|Descrição da ação referencial declarada para esse FOREIGN KEY quando ocorre uma exclusão:<br /><br /> NO_ACTION<br /><br /> CASCADE<br /><br /> SET_NULL<br /><br /> SET_DEFAULT|  
|**update_referential_action**|**tinyint**|A ação referencial declarada para esse FOREIGN KEY quando ocorre uma atualização.<br /><br /> 0 = Nenhuma ação<br /><br /> 1 = Cascata<br /><br /> 2 = Definido como nulo<br /><br /> 3 = Definir como padrão|  
|**update_referential_action_desc**|**nvarchar(60)**|Descrição da ação referencial declarada para esse FOREIGN KEY quando ocorre uma atualização:<br /><br /> NO_ACTION<br /><br /> CASCADE<br /><br /> SET_NULL<br /><br /> SET_DEFAULT|  
|**is_system_named**|**bit**|1 = nome foi gerado pelo sistema.<br /><br /> 0 = O nome foi fornecido pelo usuário.|  
  
## <a name="permissions"></a>Permissões  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obter mais informações, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte também  
 [Exibições de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Exibições de catálogo de objeto&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Consultando as perguntas frequentes do catálogo do sistema do SQL Server](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
