---
title: MSrepl_identity_range (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSrepl_identity_range_TSQL
- MSrepl_identity_range
dev_langs:
- TSQL
helpviewer_keywords:
- MSrepl_identity_range system table
ms.assetid: 6e92a8e8-7667-4c98-b1c4-46735bac50d8
caps.latest.revision: 27
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 8cb090c20142a1e081b5af3401ba8e7a35a5a6c8
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39101664"
---
# <a name="msreplidentityrange-transact-sql"></a>MSrepl_identity_range (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O **MSrepl_identity_range** tabela oferece suporte ao gerenciamento de intervalo de identidade. Essa tabela é armazenada na publicação, nos bancos de dados de assinatura e distribuição.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**publisher**|**sysname**|O nome do publicador.|  
|**publisher_db**|**sysname**|O nome do banco de dados de publicação.|  
|**TableName**|**sysname**|O nome da tabela.|  
|**identity_support**|**int**|Especifica se o tratamento de intervalo de identidade automático está habilitado. 0 especifica que o tratamento de intervalo de identidade automático não está habilitado.|  
|**next_seed**|**bigint**|Se o intervalo de identidade automático estiver habilitado, indicará o ponto de início do próximo intervalo.|  
|**pub_range**|**bigint**|O tamanho do intervalo de identidade do publicador.|  
|**range**|**bigint**|O tamanho dos valores de identidade consecutivos que seria atribuído a assinantes em um ajuste.|  
|**max_identity**|**bigint**|O limite máximo do intervalo de identidade.|  
|**threshold**|**int**|A porcentagem de limite do intervalo de identidade.|  
|**current_max**|**bigint**|O máximo atual que pode ser atribuído, mas que não será necessariamente atribuído.|  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Exibições de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
