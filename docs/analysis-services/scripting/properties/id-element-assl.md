---
title: Elemento ID (ASSL) | Microsoft Docs
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a9b0d85a5d5e5ae369048c64197122d45cb4c044
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34036377"
---
# <a name="id-element-assl"></a>Elemento ID (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contém o ID (Identificador exclusivo) do elemento pai.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Action> <!-- or one of the elements listed in the Element Relationships table -->  
   ...  
   <ID>...</ID>  
   ...  
</Action>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres (até 100 caracteres)|  
|Valor padrão|Nenhuma|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Ação](../../../analysis-services/scripting/objects/action-element-assl.md), [agregação](../../../analysis-services/scripting/objects/aggregation-element-assl.md), [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md), [Assembly](../../../analysis-services/scripting/objects/assembly-element-assl.md), [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md), [CubeBinding](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md), [CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md), [banco de dados](../../../analysis-services/scripting/objects/database-element-assl.md), [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md), [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md), [dimensão ](../../../analysis-services/scripting/objects/dimension-element-assl.md), [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md), [hierarquia](../../../analysis-services/scripting/objects/hierarchy-element-assl.md), [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md), [nível](../../../analysis-services/scripting/objects/level-element-assl.md), [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md), [Medidas](../../../analysis-services/scripting/objects/measure-element-assl.md), [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md), [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md), [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md), [ MiningModelColumn](../../../analysis-services/scripting/data-type/miningmodelcolumn-data-type-assl.md), [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md), [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md), [partição](../../../analysis-services/scripting/objects/partition-element-assl.md), [permissão](../../../analysis-services/scripting/data-type/permission-data-type-assl.md), [Perspectiva](../../../analysis-services/scripting/objects/perspective-element-assl.md), [função](../../../analysis-services/scripting/objects/role-element-assl.md), [servidor](../../../analysis-services/scripting/objects/server-element-assl.md), [rastreamento](../../../analysis-services/scripting/objects/trace-element-assl.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Remarks  
 Todo objeto principal em [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] tem um **ID** elemento como uma propriedade. O valor de um **ID** elemento tem as seguintes restrições:  
  
-   O valor não pode conter espaços à esquerda ou direita. [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implicitamente removerá espaços à esquerda ou à direita do valor de um **ID** elemento.  
  
-   O valor não pode conter caracteres de controle. [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implicitamente removerá os caracteres de controle do valor de um **ID** elemento.  
  
-   Os valores reservados a seguir não podem ser usados:  
  
    -   AUX  
  
    -   CLOCK$  
  
    -   COM1 a COM9 (COM1, COM2, COM3 e assim por diante)  
  
    -   CON  
  
    -   LPT1 a LPT9 (LPT1, LPT2, LPT3 e assim por diante)  
  
    -   NUL  
  
    -   PRN  
  
 A tabela a seguir lista os caracteres adicionais que não podem ser usados dentro do valor de um **ID** elemento, dependendo do elemento pai.  
  
|Elemento pai|Caracteres|  
|--------------------|----------------|  
|[Servidor](../../../analysis-services/scripting/objects/server-element-assl.md)|O valor deve seguir as regras para nomes do computador Windows [!INCLUDE[msCoName](../../../includes/msconame-md.md)]. (Endereços IP não são válidos)|  
|[Fonte de dados](../../../analysis-services/scripting/objects/datasource-element-assl.md)|:/\\*&#124;?" [()]{}<>|  
|[Nível de](../../../analysis-services/scripting/objects/level-element-assl.md), [atributo do elemento](../../../analysis-services/scripting/objects/attribute-element-assl.md)|.,;' `:/\\*&#124;?" & % $! [] de + ={}<>|  
|Todos os outros elementos pai|.,;' `:/\\*&#124;?" & % $! [] () de + ={}<>|  
  
## <a name="see-also"></a>Consulte também  
 [Nome de elemento &#40;ASSL&#41;](../../../analysis-services/scripting/properties/name-element-assl.md)   
 [Propriedades & #40; ASSL & #41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
