---
title: Preparando procedimento armazenado (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 6a613106-9f87-4caf-a23a-a726fc6561c5
caps.latest.revision: 10
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 99c28e2346494f737a6ee73b37cb458d7448e40b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37160597"
---
# <a name="staging-stored-procedure-master-data-services"></a>Preparando procedimento armazenado (Master Data Services)
  Ao iniciar o processo de preparo no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], você usa um entre três procedimentos armazenados.  
  
-   stg.udp_name_Leaf  
  
-   stg.udp_name_Consolidated  
  
-   stg.udp_name_Relationship  
  
 Onde nome é o nome da tabela de preparo que foi especificada quando a entidade foi criada.  
  
## <a name="staging-process-stored-procedure-parameters"></a>Parâmetros do procedimento armazenado do processo de preparo  
 A tabela a seguir lista os parâmetros desses procedimentos armazenados.  
  
|Parâmetro|Description|  
|---------------|-----------------|  
|**VersionName**<br /><br /> Obrigatório|O nome da versão. Pode ou não diferenciar maiúsculas de minúsculas, dependendo de sua configuração de agrupamento do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .|  
|**LogFlag**<br /><br /> Obrigatório|Determina se as transações são registradas em log durante o processo de preparo. Os valores possíveis são:<br /><br /> **0**: não registrar transações em log.<br />**1**: registrar transações em log.<br /><br /> <br /><br /> Para obter mais informações sobre transações, consulte [Transações &#40;Master Data Services&#41;](transactions-master-data-services.md).|  
|**BatchTag**<br /><br /> Necessário, exceto pelo serviço Web|O valor **BatchTag** conforme especificado na tabela de preparo.|  
|**Batch_ID**<br /><br /> Necessário apenas pelo serviço Web|O valor **Batch_ID** , conforme especificado na tabela de preparo.|  
  
### <a name="staging-process-stored-procedure-example"></a>Exemplo de procedimento armazenado do processo de preparo  
 O exemplo a seguir mostra como iniciar o processo de preparo por meio do procedimento armazenado de preparo.  
  
```  
USE [DATABASE_NAME]  
GO  
  
EXEC[stg].[udp_name_Leaf]  
      @VersionName = N'VERSION_1',  
@LogFlag = 1,  
@BatchTag = N'batch1'  
  
GO  
  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimento armazenado de validação &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md)   
 [Carregar ou atualizar membros no Master Data Services por meio do processo de preparo](/sql/2014/master-data-services/add-update-and-delete-data-master-data-services)   
 [Exibir erros que ocorrem durante o processo de preparo &#40;Master Data Services&#41;](view-errors-that-occur-during-staging-master-data-services.md)  
  
  
