---
title: sp_dropextendedproc (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 10/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_dropextendedproc
- sp_dropextendedproc_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_dropextendedproc
ms.assetid: dd93af2c-1b7d-4e39-af23-2d21d270a381
caps.latest.revision: 36
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 23361e6f28bdb87ab35a39ec68b448a60ad677d0
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38049384"
---
# <a name="spdropextendedproc-transact-sql"></a>sp_dropextendedproc (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Descarta um procedimento armazenado estendido.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Em vez disso, use a [Integração CLR](../../relational-databases/clr-integration/common-language-runtime-integration-overview.md) .  
  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
sp_dropextendedproc [ @functname = ] 'procedure'   
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@functname =**] **'***procedimento***'**  
 É o nome do procedimento armazenado estendido a ser descartado. *procedimento* está **nvarchar(517)**, sem padrão.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou 1 (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Nenhum  
  
## <a name="remarks"></a>Remarks  
 Executando **sp_dropextendedproc** descarta o nome do procedimento armazenado estendido definido pelo usuário da [sys. Objects](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md) exibição do catálogo e remove a entrada do [extended_procedures ](../../relational-databases/system-catalog-views/sys-extended-procedures-transact-sql.md) exibição do catálogo. Esse procedimento armazenado pode ser executado somente na **mestre** banco de dados.  
  
**sp_dropextendedproc** não descarta procedimentos armazenados estendido de sistema. Em vez disso, o administrador do sistema deve negar a permissão EXECUTE no procedimento armazenado estendido para o **pública** função.  
  
 **sp_dropextendedproc** não pode ser executado dentro de uma transação.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros dos **sysadmin** pode executar a função de servidor fixa **sp_dropextendedproc**.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir descarta o procedimento armazenado estendido `xp_hello`.  
  
> [!NOTE]  
>  Esse procedimento armazenado estendido já deve existir, caso contrário, o exemplo retornará uma mensagem de erro.  
  
```  
USE master;  
GO  
EXEC sp_dropextendedproc 'xp_hello';  
```  
  
## <a name="see-also"></a>Consulte também  
 [sp_addextendedproc &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql.md)   
 [sp_helpextendedproc &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
