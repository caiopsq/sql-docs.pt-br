---
title: sp_revokelogin (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_revokelogin_TSQL
- sp_revokelogin
dev_langs:
- TSQL
helpviewer_keywords:
- sp_revokelogin
ms.assetid: cb1ab102-1ae0-4811-9144-9a8121ef2d7e
caps.latest.revision: 28
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 0d59e993563b340b7016887720fb8f3638dca247
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38005459"
---
# <a name="sprevokelogin-transact-sql"></a>sp_revokelogin (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Remove as entradas de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um usuário do Windows ou o grupo criado pelo uso de CREATE LOGIN **sp_grantlogin**, ou **sp_denylogin**.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Use [DROP LOGIN](../../t-sql/statements/drop-login-transact-sql.md) em vez disso.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_revokelogin [ @loginame= ] 'login'  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@loginame=**] **'***logon***'**  
 É o nome do usuário ou grupo do Windows. *login* está **sysname**, sem padrão. *login* pode ser qualquer nome de usuário do Windows existente ou um grupo no formulário *nome do computador*\\*usuário ou domínio*\\*usuário*.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou 1 (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_revokelogin** desabilita conexões que usam a conta especificada o *login* parâmetro. No entanto, os usuários do Windows que têm acesso a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] através da associação em um grupo do Windows ainda podem se conectar como o grupo após o acesso individual ter sido revogado. Da mesma forma, se o *login* parâmetro especifica o nome de um grupo do Windows, os membros desse grupo têm sido separadamente receber acesso à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ainda poderão se conectar.  
  
 Por exemplo, se o usuário de Windows **ADVWORKS\john** é um membro do grupo Windows **ADVWORKS\Admins**, e **sp_revokelogin** revogar o acesso de `ADVWORKS\john`:  
  
```  
sp_revokelogin [ADVWORKS\john]  
```  
  
 Usuário **ADVWORKS\john** ainda pode se conectar se **ADVWORKS\Admins** concedeu acesso a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Da mesma forma, se o grupo de Windows **ADVWORKS\Admins** tiver seu acesso revogado, mas **ADVWORKS\john** acesso é concedido, **ADVWORKS\john** ainda pode se conectar.  
  
 Use **sp_denylogin** explicitamente impedir que os usuários se conectem a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], independentemente de suas associações de grupo do Windows.  
  
 **sp_revokelogin** não pode ser executado em uma transação definida pelo usuário.  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão ALTER ANY LOGIN no servidor.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir remove as entradas de logon para o usuário do Windows `Corporate\MollyA`.  
  
```  
EXEC sp_revokelogin 'Corporate\MollyA';  
```  
  
 Ou  
  
```  
EXEC sp_revokelogin [Corporate\MollyA];  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos de segurança armazenados &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [DROP LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/drop-login-transact-sql.md)   
 [sp_denylogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-denylogin-transact-sql.md)   
 [sp_droplogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-droplogin-transact-sql.md)   
 [sp_grantlogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-grantlogin-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
