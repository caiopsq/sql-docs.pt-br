---
title: log_shipping_secondary_databases (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- log_shipping_secondary_databases_TSQL
- log_shipping_secondary_databases
dev_langs: TSQL
helpviewer_keywords: log_shipping_secondary_databases system table
ms.assetid: ba2374af-86b8-480c-a10c-51e7c4e3ae23
caps.latest.revision: "19"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 60237602284820c646513b0ff6d8c1fcc8002cce
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="logshippingsecondarydatabases-transact-sql"></a>log_shipping_secondary_databases (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Armazena um registro para o banco de dados secundário em uma configuração de envio de logs. Essa tabela é armazenada no **msdb** banco de dados.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**secondary_database**|**sysname**|Nome do banco de dados secundário na configuração de envio de logs.|  
|**secondary_id**|**uniqueidentifier**|ID de servidor secundário na configuração de envio de logs.|  
|**restore_delay**|**int**|Período, em minutos, em que o servidor secundário aguardará para restaurar um determinado arquivo de backup. O padrão é 0 minutos.|  
|**restore_all**|**bit**|Se definido como 1, o servidor secundário restaurará todos os backups de log de transações disponíveis quando o trabalho de restauração for executado. Caso contrário, ele será interrompido depois de um arquivo foi restaurado.|  
|**restore_mode**|**bit**|O modo de restauração do banco de dados secundário.<br /><br /> 0 = Log de restauração com NORECOVERY.<br /><br /> 1 = Log de restauração com STANDBY.|  
|**disconnect_users**|**bit**|Se definido como 1, os usuários serão desconectados do banco de dados secundário quando uma operação de restauração for executada. O padrão = 0.|  
|**block_size**|**int**|Tamanho, em bytes, usado como tamanho de bloco para o dispositivo de backup.|  
|**buffer_count**|**int**|Número total de buffers usado pela operação de backup ou restauração.|  
|**max_transfer_size**|**int**|O tamanho, em bytes, do máximo solicitação de entrada ou saída que é emitida por [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o dispositivo de backup.|  
|**last_restored_file**|**nvarchar (500)**|Nome do último arquivo de backup restaurado no banco de dados secundário.|  
|**last_restored_date**|**datetime**|Hora e data da última operação de restauração no banco de dados secundário.|  
  
## <a name="see-also"></a>Consulte também  
 [Sobre o envio de logs &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [sp_add_log_shipping_secondary_database &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql.md)   
 [sp_delete_log_shipping_secondary_database &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql.md)   
 [sp_help_log_shipping_secondary_database &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-log-shipping-secondary-database-transact-sql.md)   
 [log_shipping_secondary &#40; Transact-SQL &#41;](../../relational-databases/system-tables/log-shipping-secondary-transact-sql.md)   
 [Tabelas do sistema &#40; Transact-SQL &#41;](../../relational-databases/system-tables/system-tables-transact-sql.md)  
  
  