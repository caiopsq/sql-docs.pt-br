---
title: "NÃO nulo nas instruções CREATE TABLE | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- not null [ODBC]
- interoperability [ODBC], not null
ms.assetid: 3fb69943-f0c9-4ed2-aa42-20440e37e49d
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: dc96de9df9724e500709488054b3357b3c7e50aa
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="not-null-in-create-table-statements"></a>NOT NULL nas instruções de tabela de criação
Alguns bancos de dados e especialmente área de trabalho, não dão suporte a **não NULL** restrição de coluna no **CREATE TABLE** instruções. Para obter mais informações, consulte a opção SQL_NON_NULLABLE_COLUMNS o [SQLGetInfo](../../../odbc/reference/syntax/sqlgetinfo-function.md) descrição da função.