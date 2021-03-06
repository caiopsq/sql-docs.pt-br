---
title: Elemento PropertyList (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- PropertyList Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#PropertyList
- microsoft.xml.analysis.propertylist
- urn:schemas-microsoft-com:xml-analysis#PropertyList
helpviewer_keywords:
- PropertyList element
ms.assetid: 58e63bd9-8aac-438d-adba-1868b4d123f5
caps.latest.revision: 13
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 6b3fdd7f6d59ef6a2523bada292dfb2b8f17a4a8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37323036"
---
# <a name="propertylist-element-xmla"></a>Elemento PropertyList (XMLA)
  Contém uma coleção de XML para as propriedades do Analysis (XMLA) usada pelo [Discover](../xml-elements-methods-discover.md) e [Execute](../xml-elements-methods-execute.md) métodos.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
<Properties>  
   <PropertyList>  
      <!-- Zero or more XMLA properties -->  
   </PropertyList>  
</Properties>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Propriedades](properties-element-xmla.md)|  
|Elementos filho|Propriedades XMLA (consulte Comentários)|  
  
## <a name="remarks"></a>Remarks  
 O `PropertyList` elemento contém uma coleção de propriedades XMLA. Cada propriedade permite ao usuário controlar alguns aspectos do método `Discover` ou `Execute`, como a definição de informações obrigatórias para estabelecer conexão com a fonte de dados, a especificação do formato de retorno do conjunto de resultados ou a especificação da localidade na qual os dados devem ser formatados. Cada propriedade XMLA no `PropertyList` elemento é definido por um elemento XML separado. O valor da propriedade XMLA são os dados contidos pelo elemento XML e o nome da propriedade XMLA que corresponde ao nome do elemento XML.  
  
 As propriedades disponíveis e seus valores podem ser obtidos usando o tipo de solicitação DISCOVER_PROPERTIES com o `Discover` método. Não há nenhum pedido obrigatório para as propriedades listadas no elemento `PropertyList`.  
  
 Para obter mais informações sobre as propriedades XMLA com suporte [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], consulte [propriedades XMLA com suporte &#40;XMLA&#41;](propertylist-element-supported-xmla-properties.md).  
  
## <a name="example"></a>Exemplo  
  
```  
<Properties>  
   <PropertyList>  
      <DataSourceInfo>  
         Provider=MSOLAP;Data Source=local;  
      </DataSourceInfo>  
      <Catalog>  
         Foodmart 2000  
      </Catalog>  
      <Format>  
         Multidimensional  
      </Format>  
   </PropertyList>  
</Properties>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
