---
title: server_assembly_modules (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- server_assembly_modules_TSQL
- sys.server_assembly_modules
- server_assembly_modules
- sys.server_assembly_modules_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.server_assembly_modules catalog view
ms.assetid: af799e38-2d16-49b2-bcf5-6f9199af899e
caps.latest.revision: "26"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: eeb90ab264d2ba8fd9ca2213faca6fd4a872e3d9
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sysserverassemblymodules-transact-sql"></a>sys.server_assembly_modules (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contém uma linha para cada módulo de assembly para os gatilhos do nível de servidor de tipo TA. Essa exibição mapeia gatilhos de assembly para a implementação de CLR subjacente. Você pode associar essa relação para **server_triggers**. O assembly deve ser carregado para o **mestre** banco de dados. A tupla (object_id) é a chave para a relação.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|Essa é uma referência FOREIGN KEY para o objeto no qual esse módulo de assembly foi definido.|  
|**assembly_id**|**int**|ID do assembly a partir do qual o módulo foi criado. O assembly deve ser carregado no banco de dados mestre.|  
|**assembly_class**|**sysname**|Nome da classe no assembly que define esse módulo.|  
|**assembly_method**|**sysname**|Nome do método na classe que o define. É NULL para funções de agregação (AF).|  
|**execute_as_principal_id**|**int**|A identificação do servidor principal EXECUTE AS.<br /><br /> NULL por padrão ou se EXECUTE AS CALLER.<br /><br /> ID da entidade especificada se EXECUTE AS SELF EXECUTE AS \<principal >.<br /><br /> -2 = EXECUTE AS OWNER.|  
  
## <a name="permissions"></a>Permissões  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obter mais informações, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte também  
 [Exibições de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Exibições de catálogo de objeto &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)  
  
  