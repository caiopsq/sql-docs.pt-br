---
title: SQLSetConnectOption (Driver de acesso) | Microsoft Docs
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
- Access driver [ODBC], SQLSetConnectOption
- SQLSetConnectOption function [ODBC], Access Driver
ms.assetid: 58399bc4-d0b1-4eaa-a474-c92b2d5855ea
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: b8f7497cb6b36602908443ab4fd9bdeb592ce8af
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="sqlsetconnectoption-access-driver"></a>SQLSetConnectOption (Driver de acesso)
> [!NOTE]  
>  Este tópico fornece informações específicas de Driver de acesso. Para obter informações gerais sobre esta função, consulte o tópico apropriado em [referência da API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
|fOption|Comentário|  
|-------------|-------------|  
|SQL_ACCESS_MODE|O fOption SQL_ACCESS_MODE pode ser definido como SQL_MODE_READ_ONLY ou SQL_MODE_READ_WRITE. No entanto, o driver não impede que atualizações se SQL_ACCESS_MODE for definido como SQL_MODE_READ_ONLY.|  
|SQL_AUTOCOMMIT|Quando o driver do Microsoft Access for usado, a opção SQL_AUTOCOMMIT pode ser definida como SQL_AUTOCOMMIT_ON ou SQL_AUTOCOMMIT_OFF, porque o driver do Microsoft Access dá suporte a transações [1].|  
|SQL_CURRENT_QUALIFIER|Tem suporte.|  
|SQL_LOGIN_TIMEOUT|Sem suporte.|  
|SQL_OPT_TRACE|Tem suporte.|  
|SQL_OPT_TRACEFILE|Tem suporte.|  
|SQL_PACKET_SIZE|Sem suporte.|  
|SQL_QUIET_MODE|Sem suporte.|  
|SQL_TRANSLATE_DLL|Sem suporte.|  
|SQL_TRANSLATION_OPTION|Sem suporte.|  
|SQL_TXN_ISOLATION|SQL_TXN_ISOLATION é sempre SQL_TXN_READ_COMMITTED.|  
  
 [1] não há suporte para transações atômicas pelo driver do Microsoft Access. Quando a confirmação de uma transação usando o driver do Microsoft Access, um atraso finito existe entre o momento em que a transação é confirmada e a hora em que os valores são gravados no disco. Esse atraso é determinado por um atraso inerente no mecanismo do Microsoft Jet. O tempo limite da página não pode ser menor que um valor mínimo, mesmo se a opção PageTimeout está definida abaixo do valor. Como resultado, não há nenhuma garantia de que foi confirmada dados estável, desde que as alterações podem ser feitas durante o intervalo.