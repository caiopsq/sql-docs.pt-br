---
title: Elemento AlgorithmParameter (ASSL) | Microsoft Docs
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
- AlgorithmParameter Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- AlgorithmParameter
helpviewer_keywords:
- AlgorithmParameter element
ms.assetid: 73211495-065c-43c6-a486-be6044617263
caps.latest.revision: 35
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: fd5ee9ceb1c8d2455d7e9c087e12e2f59625b5ab
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37178853"
---
# <a name="algorithmparameter-element-assl"></a>Elemento AlgorithmParameter (ASSL)
  Define um parâmetro para o algoritmo usado por um [MiningModel](miningmodel-element-assl.md) elemento.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<AlgorithmParameters>  
   <AlgorithmParameter>  
      <Name>...</Name>  
      <Value>...</Value>  
   </AlgorithmParameter>  
</AlgorithmParameters>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-n: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[AlgorithmParameters](../collections/algorithmparameters-element-assl.md)|  
|Elementos filho|[Nome](../properties/name-element-assl.md), [Value](../properties/value-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 Um `AlgorithmParameter` é um parâmetro para um algoritmo de modelo de mineração. O `AlgorithmParameter` representa este parâmetro como um par de nome/valor. O conjunto de parâmetros aplicáveis que um `AlgorithmParameter` pode representar é dependente de algoritmo. Para obter mais informações sobre parâmetros de algoritmo para um determinado algoritmo, consulte a documentação apropriada para aquele algoritmo.  
  
 Parâmetros de algoritmo disponíveis, inclusive validação e informações de exibição, podem ser recuperados do [DMSCHEMA_MINING_SERVICE_PARAMETERS](../../schema-rowsets/data-mining/dmschema-mining-service-parameters-rowset.md) linhas de esquema.  
  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.AlgorithmParameter>.  
  
## <a name="see-also"></a>Consulte também  
 [Elemento MiningModel &#40;ASSL&#41;](miningmodel-element-assl.md)   
 [Elemento Algorithm &#40;ASSL&#41;](../properties/algorithm-element-assl.md)   
 [Objetos &#40;ASSL&#41;](objects-assl.md)  
  
  
