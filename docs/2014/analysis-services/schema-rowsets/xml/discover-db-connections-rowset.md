---
title: Conjunto de linhas DISCOVER_DB_CONNECTIONS | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- DISCOVER_DB_CONNECTIONS rowset
ms.assetid: 12a51a4e-5f3d-4449-9d94-7836fea1bc8b
caps.latest.revision: 18
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f22c330fcc1deef1e86f4442ed8524235a3ba5c0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37295546"
---
# <a name="discoverdbconnections-rowset"></a>Conjunto de linhas DISCOVER_DB_CONNECTIONS
  Oferece uso de recursos e de informações de atividade sobre as conexões abertas no momento do servidor para um banco de dados.  
  
## <a name="rowset-columns"></a>Colunas do conjunto de linhas  
 O `DISCOVER_DB_CONNECTIONS` linhas contém as colunas a seguir.  
  
|Nome da coluna|Indicador de tipo|Comprimento|Description|  
|-----------------|--------------------|------------|-----------------|  
|`CONNECTION_CATALOG_NAME`|`DBTYPE_WSTR`||O nome do banco de dados conectado no momento.|  
|`CONNECTION_ID`|`DBTYPE_I4`||Um número exclusivo que identifica a conexão.|  
|`CONNECTION_IDLE_TIME_MS`|`DBTYPE_I8`||O tempo ocioso, em milissegundos, desde o início da conexão.|  
|`CONNECTION_IN_USE`|`DBTYPE_I4`||indica se a conexão está ativa (1) ou ociosa (0).|  
|`CONNECTION_LAST_COMMAND_END_TIME`|`DBTYPE_DBTIMESTAMP`||A data e a hora UTC do servidor quando a execução do último comando foi concluída.|  
|`CONNECTION_LAST_COMMAND_START_TIME`|`DBTYPE_DBTIMESTAMP`||A data e a hora UTC do servidor quando a execução do último comando foi iniciada.|  
|`CONNECTION_SERVER_NAME`|`DBTYPE_WSTR`||O nome do servidor conectado no momento.|  
|`CONNECTION_SPID`|`DBTYPE_I4`||A ID da sessão.|  
|`CONNECTION_START_TIME`|`DBTYPE_DBTIMESTAMP`||A data e a hora UTC do servidor quando a conexão foi iniciada.|  
|`CONNECTION_USAGE_TIME_MS`|`DBTYPE_I8`||O tempo de atividade da conexão, em milissegundos, desde o início da conexão.|  
  
 Este conjunto de linhas do esquema não é classificado.  
  
> [!IMPORTANT]  
>  O conjunto de linhas `DISCOVER_DB_CONNECTIONS` só exibirá informações quando o serviço estiver conectado às fontes de dados relacionais.  
  
## <a name="restriction-columns"></a>Colunas de restrição  
 O conjunto de linhas `DISCOVER_DB_CONNECTIONS` pode ser restringido nas colunas listadas na tabela a seguir.  
  
|Nome da coluna|Indicador de tipo|Estado de restrição|  
|-----------------|--------------------|-----------------------|  
|CONNECTION_ID|DBTYPE_I4|Opcional.|  
|CONNECTION_IN_USE|DBTYPE_I4|Opcional.|  
|CONNECTION_SERVER_NAME|DBTYPE_WSTR|Opcional.|  
|CONNECTION_CATALOG_NAME|DBTYPE_WSTR|Obrigatórios.|  
|CONNECTION_SPID|DBTYPE_I4|Opcional.|  
  
## <a name="see-also"></a>Consulte também  
 [Conjunto de linhas de esquema do XML](xml-for-analysis-schema-rowsets.md)  
  
  
