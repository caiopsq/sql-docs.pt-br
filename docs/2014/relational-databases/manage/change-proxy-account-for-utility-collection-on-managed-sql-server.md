---
title: Alterar a conta Proxy para a coleta do utilitário definida em uma instância gerenciada do SQL Server (utilitário do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ff37ba8b-a08c-4109-b6e2-5748c995a52c
caps.latest.revision: 7
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: d41abfdc155288e8140f0a69911829d33a891223
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37248396"
---
# <a name="change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server-sql-server-utility"></a>Alterar a conta proxy para o conjunto de coleta do utilitário em uma instância gerenciada do SQL Server (Utilitário do SQL Server)
  Este tópico descreve como alterar a conta proxy para o Conjunto de Coleta do Utilitário em uma instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server"></a>Para alterar a conta proxy do conjunto de coleta do utilitário em uma instância gerenciada do SQL Server  
  
1.  Remova a instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.  
  
    -   No **Gerenciador do Utilitário** no SSMS, clique no nó **Instâncias Gerenciadas** .  
  
    -   Na exibição de lista do **Gerenciador do Utilitário** , clique com o botão direito do mouse no nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e selecione **Remover Instância Gerenciada...**. Para obter mais informações, veja [Remover uma instância do SQL Server do Utilitário do SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).  
  
2.  Inscreva a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] novamente.  
  
    -   No **Gerenciador do Utilitário** no SSMS, clique com o botão direito do mouse no nó **Instâncias Gerenciadas** e selecione **Adicionar Instância Gerenciada...**.  
  
    -   Siga os prompts para concluir o assistente, especificando a nova conta proxy.  
  
## <a name="see-also"></a>Consulte também  
 [Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md)   
 [Solucionar problemas do Utilitário do SQL Server](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
