---
title: MSSQL_ENG014152 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014152 error
ms.assetid: 4215e2b1-cd30-441f-9671-9afc742adf6e
caps.latest.revision: 10
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 4b499d24a6cfa7c09f75d0d0150eb8f2f942d4b7
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205216"
---
# <a name="mssqleng014152"></a>MSSQL_ENG014152
    
## <a name="message-details"></a>Detalhes da mensagem  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|14152|  
|Origem do evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbólico||  
|Texto da mensagem|Replicação-%s: agente %s agendado para tentar novamente. %s|  
  
## <a name="explanation"></a>Explicação  
 O agente de replicação especificado foi programado para repetir a operação solicitada. O processo continua repetindo até alcançar o número máximo configurado de tentativas de repetição para a etapa de trabalho.  
  
 Normalmente, uma repetição ocorre devido a um dos seguintes motivos:  
  
-   O valor **QueryTimeout** é excedido.  
  
-   O valor **LoginTimeout** é excedido.  
  
-   O processo de replicação foi escolhido como uma vítima de deadlock.  
  
## <a name="user-action"></a>Ação do usuário  
 Se a mensagem de repetição não for frequente, nenhuma ação é exigida do usuário.  
  
 Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) para exibir a definição atual do número máximo de vezes que a etapa **Executar agente** do agente de replicação especificado será repetida. É possível usar o parâmetro **@retry_attempts** do procedimento armazenado [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) para ajustar o número de vezes que uma etapa de trabalho é repetida.  
  
 Se a mensagem de repetição ocorrer com frequência, você deverá solucionar o problema com base na mensagem que está causando a repetição. Verifique o histórico do agente para mensagens que indicam por que a nova tentativa teve que ser programada. Em alguns casos, talvez seja necessário habilitar o log mais detalhado do agente de replicação. Para obter mais informações sobre como configurar o log para replicação, consulte o artigo [312292](http://support.microsoft.com/kb/312292)na Base de Dados de Conhecimento Microsoft.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md)  
  
  
