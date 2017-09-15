---
title: Elemento Return (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- return Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.return
- http://schemas.microsoft.com/analysisservices/2003/engine#return
- urn:schemas-microsoft-com:xml-analysis#return
helpviewer_keywords:
- return element
ms.assetid: 3cfe8b74-fec3-4987-a74a-5f731444e024
caps.latest.revision: 14
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 06b93a7d4c785f8e298a40d6b0accd2ad945b53e
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="return-element-xmla"></a>Elemento return (XMLA)
  Contém informações retornadas por uma [DiscoverResponse](../../../analysis-services/xmla/xml-elements-objects-discoverresponse.md) elemento em resposta a um [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) chamada de método ou um [ExecuteResponse](../../../analysis-services/xmla/xml-elements-objects-executeresponse.md) elemento em resposta a um [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) chamada de método.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<DiscoverResponse> <!-- or ExecuteResponse -->  
   <return>  
      <root>...</root>  
      <!-- or -->  
      <results>...</results> <!-- ExecuteResponse only -->  
   </return>  
</DiscoverResponse>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhuma|  
|Valor padrão|Nenhuma|  
|Cardinalidade|1-1: elemento obrigatório que ocorre apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[DiscoverResponse](../../../analysis-services/xmla/xml-elements-objects-discoverresponse.md), [ExecuteResponse](../../../analysis-services/xmla/xml-elements-objects-executeresponse.md)|  
|Elementos filho|Consulte a tabela a seguir.|  
  
|Ancestor|Elementos filho|  
|--------------|--------------------|  
|[DiscoverResponse](../../../analysis-services/xmla/xml-elements-objects-discoverresponse.md)|[raiz](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md)|  
|[ExecuteResponse](../../../analysis-services/xmla/xml-elements-objects-executeresponse.md)|[raiz](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md) ou [resultados](../../../analysis-services/xmla/xml-elements-properties/results-element-xmla.md)|  
  
## <a name="remarks"></a>Comentários  
 O **retornar** elemento contém os dados retornados pelo **Discover** e **Execute** métodos. Normalmente, o **retornar** elemento contém um único **raiz** elemento que contém os dados retornados por uma bem-sucedida **Discover** ou **Execute** um XML para exceção Analysis (XMLA) retornado por uma chamada de método malsucedida ou chamada de método. Se o **Execute** método contém um **lote** comando que executa várias operações, o **retornar** elemento contém um **resultados** elemento que, por sua vez, contém um **raiz** elemento para cada comando executado com êxito ou não pelo **lote** comando.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  