---
title: Categoria de eventos de bloqueio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 06427f8e-89bb-4710-a0c1-dc5e42b7e95e
caps.latest.revision: 5
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 0a3fc63269fdaff254ef2dfd412ef3a706abb09d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37302766"
---
# <a name="lock-events-category"></a>Categoria de eventos de bloqueio
  A categoria de evento Eventos de Bloqueios tem as classes de evento descritas na tabela a seguir.  
  
|Event Class|ID do evento|Description|  
|-----------------|--------------|-----------------|  
|Deadlock|50|Coleta todos os eventos deadlock de bloqueios de metadados desde o início do rastreamento.|  
|Tempo limite de bloqueio|51|Coleta todos os eventos de tempo limite de bloqueio de metadados desde o início do rastreamento.|  
|Lock Acquired|52|Coleta informações sobre bloqueios adquiridos, desde que o rastreamento iniciou.|  
|Lock Released|53|Coleta informações sobre bloqueios liberados, desde que o rastreamento iniciou.|  
|Espera de bloqueio|54|Coleta informações sobre bloqueios no status aguardando, desde que o rastreamento iniciou.|  
  
 Para obter informações sobre as colunas associadas a cada classe de evento de bloqueio, consulte [Lock Events Data Columns](lock-events-data-columns.md).  
  
## <a name="see-also"></a>Consulte também  
 [Eventos de rastreamento do Analysis Services](analysis-services-trace-events.md)  
  
  
