---
title: SQLProcedureColumns (Driver de acesso) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Access driver [ODBC], SQLProcedureColumns
- SQLProcedureColumns function [ODBC], Access Driver
ms.assetid: 34fee995-5848-4ecb-bda0-fc362a77b2d9
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c8a2f1fc2a37dcdce65a145eec966d3b118bf734
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32902141"
---
# <a name="sqlprocedurecolumns-access-driver"></a>SQLProcedureColumns (Driver de acesso)
> [!NOTE]  
>  Este tópico fornece informações específicas de Driver de acesso. Para obter informações gerais sobre esta função, consulte o tópico apropriado em [referência da API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Os desenvolvedores de aplicativos devem procurar colunas definidos pelo driver a partir do final do conjunto de resultados e continuar para trás.  
  
|Coluna|Comentários|  
|------------|--------------|  
|COLUMN_TYPE|SQL_PARAM_INPUT ou SQL_RESULT_COL|  
|ORDINAL|Esta é uma coluna de driver específico que é retornada no final do conjunto de resultados. O tipo SQL da coluna é um inteiro.|
