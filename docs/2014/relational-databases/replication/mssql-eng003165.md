---
title: MSSQL_ENG003165 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003165 error
ms.assetid: 707d33dd-644e-4cc9-ac51-dddd49031530
caps.latest.revision: 14
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 17a48673988d6bea871ce89770fd5776311b9b70
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37230706"
---
# <a name="mssqleng003165"></a>MSSQL_ENG003165
    
## <a name="message-details"></a>Detalhes da mensagem  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|3165|  
|Origem do evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbólico||  
|Texto da mensagem|O banco de dados '%ls' foi restaurado; entretanto, houve um erro durante a restauração/remoção da replicação. O banco de dados foi deixado offline. Consulte o tópico MSSQL_ENG003165 dos Manuais Online do SQL Server.|  
  
## <a name="explanation"></a>Explicação  
 O erro será gerado se ocorrer um problema durante a restauração de um backup de um banco de dados replicado:  
  
-   Se o backup estiver sendo restaurado para o mesmo banco de dados e servidor nos quais foi obtido, o erro indica que não foi possível restaurar as configurações de replicação corretamente.  
  
-   Se o backup estiver sendo restaurado para um banco de dados ou servidor diferente, o erro indica que não foi possível remover as configurações de replicação corretamente (por padrão, as configurações de replicação são removidas se o banco de dados ou servidor for diferente).  
  
 É provável que o erro seja resultado de uma não correspondência entre o estado de um banco de dados restaurado e um ou mais bancos de dados do sistema com metadados de replicação: banco de dados **msdb**, **mestre**ou de distribuição.  
  
## <a name="user-action"></a>Ação do usuário  
 Para resolver o problema:  
  
1.  Execute ALTER DATABASE para que o banco de dados fique online; por exemplo: `ALTER DATABASE AdventureWorks SET ONLINE`. Para obter mais informações, veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql). Se desejar preservar as configurações de replicação, vá para a etapa 2. Caso contrário, vá para a etapa 3.  
  
2.  Execute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql). Se esse procedimento armazenado for executado com êxito, a restauração será concluída. Se não for executado com êxito, vá para a etapa 3.  
  
3.  Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para remover todas as configurações de replicação.  
  
     Se necessário, reconfigure a replicação. Se a topologia de replicação tiver sido inserida no script conforme recomendado, você deverá usar scripts para reconfigurar a topologia.  
  
## <a name="see-also"></a>Consulte também  
 [Backup e Restauração de bancos de dados do SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md)   
 [Fazer backup e restaurar bancos de dados replicados](administration/back-up-and-restore-replicated-databases.md)   
 [Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md)  
  
  
