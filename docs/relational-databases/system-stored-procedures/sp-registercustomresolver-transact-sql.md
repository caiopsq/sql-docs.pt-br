---
title: sp_registercustomresolver (Transact-SQL) | Microsoft Docs
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
applies_to:
- SQL Server
f1_keywords:
- sp_registercustomresolver
- sp_registercustomresolver_TSQL
helpviewer_keywords:
- sp_registercustomresolver
ms.assetid: 6d2b0472-0e1f-4005-833c-735d1940fe93
caps.latest.revision: 29
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 56bc885e9c149b736bee5f5662816fdb90a144eb
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32998953"
---
# <a name="spregistercustomresolver-transact-sql"></a>sp_registercustomresolver (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Registra um manipulador de lógica de negócios ou um resolvedor personalizado com base em COM que pode ser invocado durante o processo de sincronização de replicação de mesclagem. Esse procedimento armazenado é executado no Distribuidor.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_registercustomresolver [ @article_resolver = ] 'article_resolver'   
    [ , [ @resolver_clsid = ] 'resolver_clsid' ]  
    [ , [ @is_dotnet_assembly = ] 'is_dotnet_assembly' ]  
    [ , [ @dotnet_assembly_name = ] 'dotnet_assembly_name' ]  
    [ , [ @dotnet_class_name = ] 'dotnet_class_name' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@article_resolver =** ] **'***article_resolver***'**  
 Especifica o nome amigável da lógica comercial personalizada que está sendo registrada. *article_resolver* é **nvarchar (255)**, sem padrão.  
  
 [  **@resolver_clsid=** ] **'***resolver_clsid***'**  
 Especifica o valor CLSID do objeto COM que está sendo registrado. Lógica de negócios personalizada *resolver_clsid* é **nvarchar (50)**, com um padrão NULL. Esse parâmetro deve ser definido para um CLSID válido ou definido como NULL ao registrar um assembly de manipulador de lógica de negócios.  
  
 [  **@is_dotnet_assembly=** ] **'***is_dotnet_assembly***'**  
 Especifica o tipo da lógica comercial personalizada que está sendo registrada. *is_dotnet_assembly* é **nvarchar (50)**, com um padrão de FALSE. **True** indica que a lógica de negócios personalizada que está sendo registrada é um manipulador de lógica de negócios Assembly. **false** indica que é um componente COM.  
  
 [  **@dotnet_assembly_name=** ] **'***dotnet_assembly_name***'**  
 É o nome do assembly que implementa o manipulador de lógica de negócios. *dotnet_assembly_name* é **nvarchar (255)**, com um valor padrão de NULL. É necessário especificar o caminho completo para o assembly se ele não estiver implantado no mesmo diretório que o executável Agente de Mesclagem, no mesmo diretório que o aplicativo que é iniciado de forma síncrona o Agente de Mesclagem ou no GAC (cache de assembly global).  
  
 [  **@dotnet_class_name=** ] **'***dotnet_class_name***'**  
 É o nome da classe que substitui <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> para implementar o manipulador de lógica de negócios. O nome deve ser especificado no formato **NomeDaClasse**. *dotnet_class_name* é **nvarchar (255)**, com um valor padrão de NULL.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_registercustomresolver** é usado em replicação de mesclagem.  
  
## <a name="permissions"></a>Permissões  
 Somente membros do **sysadmin** função de servidor fixa ou **db_owner** pode executar a função de banco de dados fixa **sp_registercustomresolver**.  
  
## <a name="see-also"></a>Consulte também  
 [Implementar um manipulador de lógica de negócios para um artigo de mesclagem](../../relational-databases/replication/implement-a-business-logic-handler-for-a-merge-article.md)   
 [Implementar um resolvedor de conflitos personalizado para um artigo de mesclagem](../../relational-databases/replication/implement-a-custom-conflict-resolver-for-a-merge-article.md)   
 [sp_lookupcustomresolver &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-lookupcustomresolver-transact-sql.md)   
 [sp_unregistercustomresolver &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-unregistercustomresolver-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
