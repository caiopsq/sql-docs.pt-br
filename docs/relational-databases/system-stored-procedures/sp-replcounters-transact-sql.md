---
title: sp_replcounters (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_replcounters
- sp_replcounters_TSQL
helpviewer_keywords:
- sp_replcounters
ms.assetid: fe585b1f-edda-421f-81d6-8a03a3a535d2
caps.latest.revision: 24
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 5cc67b000b231146c9544ea7ef1bc1e2a3b6b667
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32997083"
---
# <a name="spreplcounters-transact-sql"></a>sp_replcounters (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna estatísticas de replicação sobre contagem de latência, transferência e transação para cada banco de dados publicado. Esse procedimento armazenado é executado no Publicador, em qualquer banco de dados.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_replcounters  
  
```  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**Banco de dados**|**sysname**|Nome do banco de dados.|  
|**Transações replicadas**|**Int**|Número de transações no log esperando serem entregues ao banco de dados de distribuição.|  
|**Taxa de replicação trans/s**|**float**|Número médio de transações por segundo entregue ao banco de dados de distribuição.|  
|**Latência de replicação**|**float**|Tempo médio, em segundos, de permanência das transações no log antes de serem distribuídas.|  
|**Replbeginlsn**|**binary(10)**|LSN (número de sequência de log) do ponto atual de truncamento no log.|  
|**Replnextlsn**|**binary(10)**|LSN do próximo registro de confirmação que aguarda entrega ao banco de dados de distribuição.|  
  
## <a name="remarks"></a>Remarks  
 **sp_replcounters** é usado em replicação transacional.  
  
## <a name="permissions"></a>Permissões  
 Requer a participação no **db_owner** função de banco de dados fixa ou **sysadmin** função de servidor fixa.  
  
## <a name="see-also"></a>Consulte também  
 [sp_replcmds &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md)   
 [sp_repldone &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-repldone-transact-sql.md)   
 [sp_replflush &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replflush-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
