---
title: Mensagens de erro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
caps.latest.revision: 33
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f3012d1e13de482dbcf173191bfd75dae9599b7c
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37421815"
---
# <a name="error-messages"></a>Mensagens de erro
  O texto das mensagens retornadas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client é colocado na *MessageText* parâmetro **SQLGetDiagRec**. A origem de um erro é indicada pelo cabeçalho da mensagem:  
  
 [Microsoft][ODBC Driver Manager]  
 São erros gerados pelo Gerenciador de Driver ODBC.  
  
 [Microsoft][ODBC Cursor Library]  
 São erros gerados pela biblioteca de cursores ODBC.  
  
 [Microsoft][SQL Server Native Client]  
 Esses erros são gerados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client. Se não houver outros nós com o nome de uma Net-Library nem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é sinal de que o erro foi encontrado no driver.  
  
 [Microsoft] [SQL Server Native Client] [*Net-Transportname*]  
 Esses erros são gerados pela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, onde *Net-Transportname* é o nome de exibição de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transporte de rede do cliente (por exemplo, Pipes nomeados, memória compartilhada, TCP/IP Sockets ou VIA). O restante da mensagem de erro contém a função Net-Library chamada e a função chamada na API de rede subjacente pela função TDS. O *pfNative* código de erro retornado com esses erros é o código de erro da pilha de protocolo de rede subjacente.  
  
 [Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]  
 São erros gerados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. O restante da mensagem de erro é o texto da mensagem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. O *pfNative* código retornado com esses erros é o número do erro [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para obter mais informações sobre uma lista de mensagens de erro (e seus números) que pode ser retornada por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte as colunas de descrição e o erro a **sysmessages** tabela do sistema a **mestre** banco de dados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Consulte também  
 [Tratando de erros e mensagens](handling-errors-and-messages.md)  
  
  
