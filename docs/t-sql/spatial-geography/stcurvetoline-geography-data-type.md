---
title: STCurveToLine (tipo de dados geography) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- STCurveToLine_TSQL
- STCurveToLine
dev_langs:
- TSQL
helpviewer_keywords:
- STCurveToLine method (geography)
ms.assetid: 2f863a85-6168-465a-b32f-bb5e3de58dee
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 15b4fc42fcf206fe0de967f1c4329dd4ff07e2a0
ms.sourcegitcommit: a6596c62f607041c4402f7d5b41a232fca257c14
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36257108"
---
# <a name="stcurvetoline-geography-data-type"></a>STCurveToLine (tipo de dados geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna uma aproximação poligonal de uma instância de **geography** que contém segmentos de arco circulares.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
.STCurveToLine()  
```  
  
## <a name="return-types"></a>Tipos de retorno  
 Tipo de retorno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geography**  
  
 Tipo de retorno do CLR: **SqlGeography**  
  
## <a name="remarks"></a>Remarks  
 Retorna uma instância de **LineString** para uma instância de **CircularString** ou de **CompoundCurve**.  
  
 Retorna uma instância de **Polygon** para uma instância de **CurvePolygon**.  
  
 Retornar uma cópia das instâncias de **geografia** que não contêm instâncias de **CircularString**, **CompoundCurve** ou **CurvePolygon**.  
  
 Ao contrário da especificação SQL MM, esse método não usa valores de coordenada z para calcular a aproximação poligonal. Os valores de coordenada z que estiverem presentes na chamada da instância de **geography** serão ignorados.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir retorna uma instância de `LineString` que é uma aproximação poligonal de uma instância de `CircularString`:  
  
```
 DECLARE @g1 geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';  
 DECLARE @g2 geography;  
 SET @g2 = @g1.STCurveToLine();  
 SELECT @g1.STNumPoints() AS G1, @g2.STNumPoints() AS G2;
 ```  
  
## <a name="see-also"></a>Consulte Também  
 [STLength &#40;tipo de dados geography&#41;](../../t-sql/spatial-geography/stlength-geography-data-type.md)   
 [STNumPoints &#40;tipo de dados geography&#41;](../../t-sql/spatial-geography/stnumpoints-geography-data-type.md)   
 [Visão geral de tipos de dados espaciais](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
