---
title: sp_droparticle (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
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
- sp_droparticle_TSQL
- sp_droparticle
helpviewer_keywords:
- sp_droparticle
ms.assetid: 09fec594-53f4-48a5-8edb-c50731c7adb2
caps.latest.revision: 25
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: a05199bb255a3ae4050f2bca7a6d2f4352d5533a
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32990861"
---
# <a name="spdroparticle-transact-sql"></a>sp_droparticle (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Descarta um artigo de uma publicação de instantâneo ou transacional. Um artigo não poderá ser removido se tiver uma ou mais assinaturas associadas. Esse procedimento armazenado é executado no Publicador, no banco de dados publicador.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_droparticle [ @publication= ] 'publication'  
        , [ @article= ] 'article'  
    [ , [ @ignore_distributor = ] ignore_distributor ]  
    [ , [ @force_invalidate_snapshot= ] force_invalidate_snapshot ]  
    [ , [ @publisher = ] 'publisher' ]  
    [ , [ @from_drop_publication = ] from_drop_publication ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@publication=**] **'***publicação***'**  
 É o nome da publicação que contém o artigo a ser removido. *publicação* é **sysname**, sem padrão.  
  
 [  **@article=**] **'***artigo***'**  
 É o nome do artigo a ser removido. *artigo* é **sysname**, sem padrão.  
  
 [  **@ignore_distributor =**] *ignore_distributor*  
 [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
 [  **@force_invalidate_snapshot =** ] *force_invalidate_snapshot*  
 Confirma que a ação tomada por esse procedimento armazenado pode invalidar um instantâneo existente. *force_invalidate_snapshot* é um **bit**, com um padrão de **0**.  
  
 **0** Especifica que as alterações no artigo fazem com que o instantâneo seja inválido. Se o procedimento armazenado detectar que a alteração requer um novo instantâneo, ocorrerá um erro e nenhuma alteração será feita.  
  
 **1** Especifica que as alterações no artigo podem invalidar o instantâneo inválido e se houver assinaturas existentes que exigem um novo instantâneo, dará permissão para que o instantâneo existente seja marcado como obsoleto e um novo instantâneo seja gerado.  
  
 [ **@publisher**=] **'***publicador***'**  
 Especifica um não[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador. *publicador* é **sysname**, com um padrão NULL.  
  
> [!NOTE]  
>  *publicador* não deve ser usado ao alterar as propriedades de artigo em uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador.  
  
 [ **@from_drop_publication**=] *from_drop_publication*  
 [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_droparticle** é usado em replicação de instantâneo e transacional.  
  
 Para artigos filtrados horizontalmente, **sp_droparticle** verifica o **tipo** coluna do artigo no [sysarticles &#40;Transact-SQL&#41; ](../../relational-databases/system-tables/sysarticles-transact-sql.md) tabela Determine se uma exibição ou filtro também deve ser descartado. Se uma exibição ou filtro foram gerados automaticamente, serão descartados com o artigo. Se foram criados manualmente, não serão descartados.  
  
 Executar **sp_droparticle** descartar um artigo de uma publicação não remove o objeto do banco de dados de publicação ou o objeto correspondente do banco de dados de assinatura. Use `DROP <object>` para remover esses objetos manualmente, se necessário.  
  
## <a name="example"></a>Exemplo  
 [!code-sql[HowTo#sp_droparticle](../../relational-databases/replication/codesnippet/tsql/sp-droparticle-transact-_1.sql)]  
  
## <a name="permissions"></a>Permissões  
 Somente membros do **sysadmin** função de servidor fixa ou **db_owner** pode executar a função de banco de dados fixa **sp_droparticle**.  
  
## <a name="see-also"></a>Consulte também  
 [Excluir um artigo](../../relational-databases/replication/publish/delete-an-article.md)   
 [Adicionar e remover artigos de publicações existentes](../../relational-databases/replication/publish/add-articles-to-and-drop-articles-from-existing-publications.md)   
 [sp_addarticle &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addarticle-transact-sql.md)   
 [sp_changearticle &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-changearticle-transact-sql.md)   
 [sp_helparticle &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helparticle-transact-sql.md)   
 [sp_helparticlecolumns &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helparticlecolumns-transact-sql.md)   
 [Procedimentos armazenados de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
