---
title: RingN (tipo de dados geography) | Microsoft Docs
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
- RingN
- RingN_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- RingN method
ms.assetid: 30f47275-2727-4d22-bbec-c0c54bcb3ac2
caps.latest.revision: 14
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: c122e2c1a454dc4db149e68fcf591fee860f7ef4
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38029297"
---
# <a name="ringn-geography-data-type"></a>RingN (tipo de dados geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna o anel especificado da instância de **geography**: `1 ≤ n ≤ NumRings()`.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
.RingN (expression )  
```  
  
## <a name="arguments"></a>Argumentos  
 *expressão*  
 É uma expressão **int** entre 1 e o número de anéis em uma instância de **polygon**.  
  
## <a name="return-value"></a>Valor retornado  
 Tipo de retorno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geography**  
  
 Tipo de retorno do CLR: **SqlGeography**  
  
## <a name="remarks"></a>Remarks  
 Se o valor do índice de anéis **n** é menor que 1, esse método gera uma **ArgumentOutOfRangeException.** O valor do índice de anéis deve ser maior ou igual a 1 e deve ser menor ou igual ao número retornado por `NumRings()`.  
  
## <a name="examples"></a>Exemplos  
 Esse exemplo cria uma instância de `Polygon` com dois anéis e retorna o segundo anel.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653), (-122.357 47.654, -122.357 47.657, -122.349 47.657, -122.349 47.650, -122.357 47.654))', 4326);  
SELECT @g.RingN(2).ToString();  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Métodos estendidos em instâncias de geografia](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)   
 [NumRings &#40;tipo de dados geography&#41;](../../t-sql/spatial-geography/numrings-geography-data-type.md)  
  
  
