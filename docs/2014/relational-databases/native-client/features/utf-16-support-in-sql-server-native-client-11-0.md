---
title: Suporte a UTF-16 no SQL Server Native Client 11.0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f2520424-8ef4-409f-8147-d83da5076e96
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: edfcd65c62e8d8d86f55fb48f23df3831383e9d8
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2018
ms.locfileid: "40394813"
---
# <a name="utf-16-support-in-sql-server-native-client-110"></a>Suporte a UTF-16 no SQL Server Native Client 11.0
  A partir [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], se você fornecer um buffer de comprimento fixo ao associar um parâmetro de saída ou de resultado de coluna e se o `wchar` caractere gravado no buffer antes que o caractere de terminação é um ponto de código alternativo alto de um par substituto e se a próxima `wchar` caractere é um ponto de código alternativo baixo, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client não adicionará o ponto de código alternativo alto ao buffer.  
  
## <a name="see-also"></a>Consulte também  
 [Recursos do SQL Server Native Client](sql-server-native-client-features.md)  
  
  
