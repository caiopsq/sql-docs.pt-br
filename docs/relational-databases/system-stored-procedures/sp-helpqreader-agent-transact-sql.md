---
title: sp_helpqreader_agent (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_helpqreader_agent_TSQL
- sp_helpqreader_agent
helpviewer_keywords:
- sp_helpqreader_agent
ms.assetid: 8e74e1aa-e95b-4183-8017-bf123439b08d
caps.latest.revision: 21
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: be49f8a6303096487ef2c36593280fcc72e38a91
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32995943"
---
# <a name="sphelpqreaderagent-transact-sql"></a>sp_helpqreader_agent (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna propriedades do Queue Reader Agent. Esse procedimento armazenado é executado no Distribuidor, no banco de dados de distribuição, ou no Publicador, em qualquer banco de dados.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_helpqreader_agent [ [ @frompublisher = ] frompublisher ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@frompublisher=** ] *frompublisher*  
 Especifica se o procedimento armazenado é chamado no Publisher ou no Distribuidor. *frompublisher* é bit, com um valor padrão de 0. **1** significa que o procedimento armazenado é chamado do publicador, e **0** significa que o procedimento armazenado é chamado do distribuidor.  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**id**|**Int**|ID do agente.|  
|**name**|**nvarchar(100)**|O nome do agente.|  
|**job_id**|**uniqueidentifier**|ID exclusiva do trabalho de agente.|  
|**job_login**|**nvarchar(512)**|É a conta do Windows sob a qual o Distribution agent é executado, que é retornada no formato *domínio*\\*nome de usuário*.|  
|**job_password**|**sysname**|Por motivos de segurança, um valor de **\* \* \* \* \* \* \* \* \* \*** é sempre retornado.|  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_helpqreader_agent** é usado em replicação transacional.  
  
## <a name="permissions"></a>Permissões  
 Quando o valor de *frompublisher* é **1**, somente os membros do **sysadmin** a função de servidor fixa no publicador ou membros do **db_owner**função de banco de dados fixa no banco de dados de publicação pode executar **sp_helpqreader_agent**. Caso contrário, somente os membros do **sysadmin** a função de servidor fixa no distribuidor ou membros do **db_owner** função de banco de dados fixa no banco de dados de distribuição pode executar **sp_helpqreader_ agente**.  
  
## <a name="see-also"></a>Consulte também  
 [Habilitar atualização de assinaturas para publicações transacionais](../../relational-databases/replication/publish/enable-updating-subscriptions-for-transactional-publications.md)  
  
  
