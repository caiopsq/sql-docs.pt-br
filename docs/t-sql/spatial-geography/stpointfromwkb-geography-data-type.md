---
title: STPointFromWKB (tipo de dados geography) | Microsoft Docs
ms.custom: ''
ms.date: 07/30/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- STPointFromWKB_TSQL
- STPointFromWKB (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STPointFromWKB method
ms.assetid: b3b4e3bb-47bc-4621-99c4-c97aa60cdf8b
caps.latest.revision: 13
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 51e03cea630c442f896c61885c375c1ac48ef254
ms.sourcegitcommit: a6596c62f607041c4402f7d5b41a232fca257c14
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36239656"
---
# <a name="stpointfromwkb-geography-data-type"></a>STPointFromWKB (tipo de dados geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Retorna uma instância de **geographyPoint** de uma representação WKB (Well-Known Binary) do OGC (Open Geospatial Consortium).
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
STPointFromWKB ( 'WKB_point' , SRID )  
```  
  
## <a name="arguments"></a>Argumentos  
 *WKB_point*  
 É a representação WKB da instância de **geographyPoint** que você deseja retornar. *WKB_point* é uma expressão **varbinary(max)**.  
  
 *SRID*  
 É uma expressão **int** que representa a SRID (ID de referência espacial) da instância de **geographyPoint** que você deseja retornar.  
  
## <a name="return-types"></a>Tipos de retorno  
 Tipo de retorno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geography**  
  
 Tipo de retorno do CLR: **SqlGeography**  
  
 Tipo do OGC: **Point**  
  
## <a name="remarks"></a>Remarks  
 Esse método gera uma **FormatException** se a entrada não está bem formatada.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir usa `STPointFromWKB()` para criar uma instância `geography`.  
  
```  
DECLARE @g geography;  
SET @g = geography::STPointFromWKB(0x010100000017D9CEF753D347407593180456965EC0, 4326);  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>Consulte Também  
 [OGC Static Geography Methods](../../t-sql/spatial-geography/ogc-static-geography-methods.md)  
  
  
