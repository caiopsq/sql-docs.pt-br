---
title: Método Commit (SQLServerXAResource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerXAResource.commit
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 1d0f8612-fb4a-4eca-bc37-8342e1419fd4
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8c6bdb28d36a148cab744fe5d9b0dbe321998757
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32830861"
---
# <a name="commit-method-sqlserverxaresource"></a>Método commit (SQLServerXAResource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Confirma a transação global especificada pelo objeto Xid fornecido.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void commit(javax.transaction.xa.Xid xid,  
                   boolean onePhase)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *XID*  
  
 Um objeto Xid.  
  
 *onePhase*  
  
 Um valor **booliano**.  
  
## <a name="exceptions"></a>Exceções  
 javax.transaction.xa.XAException  
  
## <a name="remarks"></a>Remarks  
 Esse método commit é especificado pelo método commit na interface javax.transaction.xa.XAResource.  
  
## <a name="see-also"></a>Consulte também  
 [Métodos SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-methods.md)   
 [Membros SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-members.md)   
 [Classe SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md)  
  
  
