---
title: Estado de propriedade (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- State
- Cellset::State
helpviewer_keywords:
- State property [ADO MD]
ms.assetid: 06d480ca-9eb6-4570-a45d-a73539bddd32
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 975a9354734e0f6e5d0a2502b89b43c886be5fa3
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35284555"
---
# <a name="state-property-ado-md"></a>Propriedade State (ADO MD)
Indica o estado atual do conjunto de células.  
  
## <a name="return-values"></a>Valores de retorno  
 Retorna um **longo** inteiro que indica a condição atual do [conjunto de células](../../../ado/reference/ado-md-api/cellset-object-ado-md.md) do objeto e é somente leitura. Os seguintes valores são válidos: **adStateClosed** (0) e **adStateOpen** (1).  
  
## <a name="remarks"></a>Remarks  
 Para usar o [ObjectStateEnum](../../../ado/reference/ado-api/objectstateenum.md) nomes de constantes, você deve ter a biblioteca de tipos do ADO referenciada em seu projeto. Consulte [usando o ADO com ADO MD](../../../ado/guide/multidimensional/using-ado-with-ado-md.md) para obter mais informações.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Cellset (ADO MD)](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)  
  
## <a name="see-also"></a>Consulte também  
 [Feche o método (ADO MD)](../../../ado/reference/ado-md-api/close-method-ado-md.md)   
 [Método Open (ADO MD)](../../../ado/reference/ado-md-api/open-method-ado-md.md)
