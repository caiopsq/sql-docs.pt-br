---
title: Método Execute (Java, int[]) | Microsoft Docs
ms.custom: ''
ms.date: 02/07/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerStatement.execute (javal.lang.String.int[])
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: dc73d1c3-e756-43af-b1fc-ac438cbd0965
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: afe080df57157ae62e604ff8057027a45df39fc1
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32833321"
---
# <a name="execute-method-javalangstring-int"></a>Método execute (java.lang.String, int[])

  Executa a instrução SQL fornecida, que pode retornar diversos resultados, e sinaliza ao [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion-md.md)] que as chaves geradas automaticamente indicadas na matriz fornecida devem ser disponibilizadas para recuperação.

## <a name="syntax"></a>Sintaxe

```Java
public final boolean execute(
    java.lang.String sql,
    int[] columnIndexes)
```

#### <a name="parameters"></a>Parâmetros
*sql*

Um **cadeia de caracteres** que contém uma instrução SQL.

*columnIndexes*

Uma matriz de **int**s que indica os índices de coluna das chaves geradas automaticamente que devem ser disponibilizados.

## <a name="return-value"></a>Valor de retorno
**True** se o primeiro resultado é um conjunto de resultados. Caso contrário, **false**.
  
## <a name="exceptions"></a>Exceções
[SQLServerException](./sqlserverexception-class.md)

## <a name="remarks"></a>Remarks
Esse método execute é especificado pelo método execute na interface Java.SQL. Statement.

## <a name="see-also"></a>Consulte também

[Método Execute &#40;SQLServerStatement&#41;](./execute-method-sqlserverstatement.md)

[Membros SQLServerStatement](./sqlserverstatement-members.md)

[Classe SQLServerStatement](./sqlserverstatement-class.md)
