---
title: SQL para obter exemplos de conversão de dados C | Microsoft Docs
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
- data conversions from SQL to C types [ODBC], examples
- converting data from SQL to C types [ODBC], examples
ms.assetid: 0190c76c-7f9b-42f4-be9d-cef7284840fd
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1c23e98067cafefbf44c39633aa8c11effa6594f
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32911781"
---
# <a name="sql-to-c-data-conversion-examples"></a>SQL para obter exemplos de conversão de dados C
Os exemplos mostrados na tabela a seguir ilustram como o driver converte os dados do SQL para dados de C:  
  
|Tipo SQL<br /><br /> identificador|Dados SQL<br /><br /> value|Tipo de C<br /><br /> identificador|Buffer<br /><br /> comprimento|**TargetValuePtr*|SQLSTATE|  
|-----------------------------|------------------------|---------------------------|-----------------------|------------------------|--------------|  
|SQL_CHAR|abcdef|SQL_C_CHAR|7|abcdef\0 [a]|n/d|  
|SQL_CHAR|abcdef|SQL_C_CHAR|6|abcde\0 [a]|01004|  
|SQL_DECIMAL|1234.56|SQL_C_CHAR|8|1234.56\0 [a]|n/d|  
|SQL_DECIMAL|1234.56|SQL_C_CHAR|5|1234\0 [a]|01004|  
|SQL_DECIMAL|1234.56|SQL_C_CHAR|4|----|22003|  
|SQL_DECIMAL|1234.56|SQL_C_FLOAT|ignorado|1234.56|n/d|  
|SQL_DECIMAL|1234.56|SQL_C_SSHORT|ignorado|1234|01S07|  
|SQL_DECIMAL|1234.56|SQL_C_STINYINT|ignorado|----|22003|  
SQL_DOUBLE|1.2345678|SQL_C_DOUBLE|ignorado|1.2345678|n/d|  
|SQL_DOUBLE|1.2345678|SQL_C_FLOAT|ignorado|1.234567|n/d|  
|SQL_DOUBLE|1.2345678|SQL_C_STINYINT|ignorado|1|n/d|  
|SQL_TYPE_DATE|1992-12-31|SQL_C_CHAR|11|1992-12-31\0 [a]|n/d|  
|SQL_TYPE_DATE|1992-12-31|SQL_C_CHAR|10|-----|22003|  
|SQL_TYPE_DATE|1992-12-31|SQL_C_TIMESTAMP|ignorado|1992,12,31, 0,0,0,0 [b]|n/d|  
|SQL_TYPE_TIMESTAMP|1992-12-31 23:45:55.12|SQL_C_CHAR|23|1992-12-31 23:45:55.12\0 [a]|n/d|  
SQL_TYPE_TIMESTAMP|1992-12-31 23:45:55.12|SQL_C_CHAR|22|1992-12-31 23:45:55.1\0 [a]|01004|  
|SQL_TYPE_TIMESTAMP|1992-12-31 23:45:55.12|SQL_C_CHAR|18|----|22003|  
  
 [a] "\0" representa um byte nulo de terminação. O driver sempre nulo-finaliza SQL_C_CHAR dados.  
  
 [b] o os números na lista são armazenados nos campos da estrutura de TIMESTAMP_STRUCT.
