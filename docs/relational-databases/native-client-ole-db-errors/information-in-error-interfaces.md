---
title: Informações em Interfaces de erro | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: a017ce9414b3f83f76c5cc3d4c15cf0f626dad54
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39535786"
---
# <a name="information-in-error-interfaces"></a>Informações em interfaces de erro
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client reporta algumas informações de erro e de status nas interfaces de erro definidas pelo OLE DB **IErrorInfo**, **IErrorRecords**, e **ISQLErrorInfo** .  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dá suporte ao provedor de OLE DB do Native Client **IErrorInfo** funções de membro da seguinte maneira.  
  
|Função de membro|Description|  
|---------------------|-----------------|  
|**GetDescription**|Cadeia de caracteres de mensagem de erro descritiva.|  
|**GetGUID**|GUID da interface que definiu o erro.|  
|**GetHelpContext**|Sem suporte. Sempre retorna zero.|  
|**GetHelpFile**|Sem suporte. Sempre retorna NULL.|  
|**GetSource**|Cadeia de caracteres "Microsoft SQL Server Native Client".|  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client dá suporte ao consumidor disponível **IErrorRecords** funções de membro da seguinte maneira.  
  
|Função de membro|Description|  
|---------------------|-----------------|  
|**GetBasicErrorInfo**|Preenche uma estrutura ERRORINFO com informações básica sobre um erro. Uma estrutura ERRORINFO contém membros que identificam o valor de retorno HRESULT para o erro e o provedor e interface aos quais o erro se aplica.|  
|**GetCustomErrorObject**|Retorna uma referência em interfaces **ISQLErrorInfo** e [ISQLServerErrorInfo](http://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1).|  
|**GetErrorInfo**|Retorna uma referência em uma interface **IErrorInfo**.|  
|**GetErrorParameters**|O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client não retorna parâmetros para o consumidor por meio **GetErrorParameters**.|  
|**GetRecordCount**|Contagem de registros de erro disponível.|  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dá suporte ao provedor de OLE DB do Native Client **isqlerrorinfo:: Getsqlinfo** parâmetros da seguinte maneira.  
  
|Parâmetro|Description|  
|---------------|-----------------|  
|*pbstrSQLState*|Retorna um valor SQLSTATE para o erro. São definidos valores SQLSTATE nas especificações SQL-92, ODBC ISO SQL e de API. Nem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nem o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor Native Client OLE DB definidos valores SQLSTATE específicos de implementação.|  
|*plNativeError*|Retorna o número do erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de **master.dbo.sysmessages** quando disponível. Erros nativos estão disponíveis após uma tentativa bem-sucedida de inicializar um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonte de dados do provedor OLE DB do Native Client. Antes da tentativa, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client sempre retorna zero.|  
  
## <a name="see-also"></a>Consulte também  
 [Erros](../../relational-databases/native-client-ole-db-errors/errors.md)  
  
  
