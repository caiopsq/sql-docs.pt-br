---
title: sys. security_predicates (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- Azure SQL Database
- SQL Server 2016 Preview
f1_keywords:
- SYS.SECURITY_PREDICATES
- SECURITY_PREDICATES
- SECURITY_PREDICATES_TSQL
- SYS.SECURITY_PREDICATES_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.security_predicates catalog view
- security_predicates catalog view
ms.assetid: c7a2f28c-98da-463d-8b8a-8e5619e2c6a6
caps.latest.revision: 9
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 1576ed5332f0cae14b3c263e3bfd72eacc26a956
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39559406"
---
# <a name="syssecuritypredicates-transact-sql"></a>sys. security_predicates (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Retorna uma linha para cada predicado de segurança no banco de dados.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|object_id|**int**|ID da política de segurança que contém esse predicado.|  
|security_predicate_id|**int**|ID do predicado nesta política de segurança.|  
|target_object_id|**int**|ID do objeto no qual o predicado de segurança está associado.|  
|predicate_definition|**nvarchar(max)**|Nome totalmente qualificado da função que será usada como um predicado de segurança, incluindo os argumentos. Observe que o `schema.function` nome pode ser normalizado (ou seja, com escape), bem como qualquer outro elemento em texto para manter a consistência. Por exemplo:<br /><br /> `[dbo].[fn_securitypredicate]([wing], [startTime], [endTime])`|  
|predicate_type|**int**|O tipo de predicado usado pela política de segurança:<br /><br /> 0 = O PREDICADO DE FILTRO<br /><br /> 1 = O PREDICADO DE BLOQUEIO|  
|predicate_type_desc|**nvarchar(60)**|O tipo de predicado usado pela política de segurança:<br /><br /> FILTER<br /><br /> BLOCO|  
|operação|**int**|O tipo de operação especificado para o predicado:<br /><br /> NULL = todas as operações aplicáveis<br /><br /> 1 = APÓS INSERÇÃO<br /><br /> 2 = APÓS A ATUALIZAÇÃO<br /><br /> 3 = ANTES DA ATUALIZAÇÃO<br /><br /> 4 = ANTES DA EXCLUSÃO|  
|operation_desc|**nvarchar(60)**|O tipo de operação especificado para o predicado:<br /><br /> NULL<br /><br /> APÓS INSERÇÃO<br /><br /> AFTER UPDATE<br /><br /> ANTES DA ATUALIZAÇÃO<br /><br /> ANTES DA EXCLUSÃO|  
  
## <a name="permissions"></a>Permissões  
 Entidades de segurança com o **ALTER ANY SECURITY POLICY** permissão têm acesso a todos os objetos nesta exibição do catálogo, bem como qualquer pessoa com **VIEW DEFINITION** no objeto.  
  
## <a name="see-also"></a>Consulte também  
 [Segurança em nível de linha](../../relational-databases/security/row-level-security.md)   
 [sys.security_policies &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-security-policies-transact-sql.md)   
 [CREATE SECURITY POLICY &#40;Transact-SQL&#41;](../../t-sql/statements/create-security-policy-transact-sql.md)   
 [Exibições de catálogo de segurança &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [Exibições de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Entidades &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  
