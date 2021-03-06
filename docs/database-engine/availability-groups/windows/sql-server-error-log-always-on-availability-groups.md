---
title: Log de erros do SQL Server (Grupos de Disponibilidade Always On) (SQL Server) | Microsoft Docs
ms.custom: ag-guide
ms.date: 06/13/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 39d0c98d-75af-4dd1-b908-30d31af56f2a
caps.latest.revision: 4
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 0c4c4e04ffa776d5799584800e65fb3f9d9b6d9e
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32862901"
---
# <a name="sql-server-error-log-always-on-availability-groups"></a>Log de erros do SQL Server (Grupos de Disponibilidade Always On)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  O log de erros do SQL Server relata eventos que afetam Grupos de Disponibilidade Always On, tais como:  
  
-   Comunicação com o cluster do WSFC (Cluster de Failover do Windows Server)  
  
-   Transições de estado de réplicas de disponibilidade  
  
-   Transições de estado de bancos de dados de disponibilidade  
  
-   Estado de conectividade de bancos de dados de disponibilidade entre réplicas primárias e secundárias  
  
-   Status dos pontos de extremidade de grupo de disponibilidade  
  
-   Status de ouvintes de grupo de disponibilidade  
  
-   Status da concessão entre a DLL de recurso do SQL Server (em execução no cluster WSFC) e a instância do SQL Server (para obter mais informações, veja [Como funciona o tempo limite de concessão do Always On do SQL Server](http://blogs.msdn.com/b/psssql/archive/2012/09/07/how-it-works-sql-server-alwayson-lease-timeout.aspx))  
  
-   Eventos de erro no grupo de disponibilidade  


Os seguintes sintomas devem levar à revisão do log de erros do SQL Server:  

-   Não é possível acessar bancos de dados de disponibilidade  
  
-   Failover inesperado do grupo de disponibilidade  
  
-   Grupo de disponibilidade no estado Resolving inesperadamente  
  
-   Grupo de disponibilidade em um estado indeterminado  
  
Para obter mais informações, veja [Exibir o log de erros do SQL Server &#40;SQL Server Management Studio&#41;](~/relational-databases/performance/view-the-sql-server-error-log-sql-server-management-studio.md).  
  
  