---
title: SQLTables (Driver de acesso) | Microsoft Docs
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
- SQLTables function [ODBC], Access Driver
- Access driver [ODBC], SQLTables
ms.assetid: 94423cf9-341a-4db6-bb10-8f5448df7fc3
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d0a78f59ef54c3c157525a028b7323c5dcc39fe7
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32903381"
---
# <a name="sqltables-access-driver"></a>SQLTables (Driver de acesso)
> [!NOTE]  
>  Este tópico fornece informações específicas de Driver de acesso. Para obter informações gerais sobre esta função, consulte o tópico apropriado em [referência da API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
|Argumento|Comentários|  
|--------------|--------------|  
|*szTableOwner*|O argumento só é válido para *szTableOwner* é NULL porque nenhum dos drivers de suporte a nomes de proprietário. Com *szTableOwner* definido como NULL, todas as tabelas são retornadas. NULL é retornado na coluna TABLE_OWNER.|  
|*szTableQualifier*|Na coluna TABLE_QUALIFIER, **SQLTables** retorna o caminho para um arquivo de banco de dados.|  
|*SzTableType*|Quando o driver do Microsoft Access for usado, "Tabela de sistema" há suporte para *szTableType* para tabelas do sistema, "Sinônimo" suporte para tabelas anexadas e "VIEW" é suportado para retornar a linha consultas.|  
  
## <a name="see-also"></a>Consulte também  
 [Função SQLTables](../../odbc/reference/syntax/sqltables-function.md)
