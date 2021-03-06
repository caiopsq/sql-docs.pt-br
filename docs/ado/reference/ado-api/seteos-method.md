---
title: Método SetEOS | Microsoft Docs
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
- _Stream::raw_SetEOS
- _Stream::SetEOS
helpviewer_keywords:
- SetEOS method [ADO]
ms.assetid: 707c18ca-6a56-4970-bbd6-ae1fb86a0b8a
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8821b58e5e111ad879c34f0d3d8177404945a72f
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35281605"
---
# <a name="seteos-method"></a>Método SetEOS
Define a posição que é o final do fluxo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Stream.SetEOS  
```  
  
## <a name="remarks"></a>Remarks  
 **SetEOS** atualiza o valor da [EOS](../../../ado/reference/ado-api/eos-property.md) propriedade fazendo atual [posição](../../../ado/reference/ado-api/position-property-ado.md) o fim do fluxo. Todos os bytes ou caracteres da posição atual a seguir são truncados.  
  
 Porque [gravar](../../../ado/reference/ado-api/write-method.md), [WriteText](../../../ado/reference/ado-api/writetext-method.md), e [CopyTo](../../../ado/reference/ado-api/copyto-method-ado.md) não truncar valores extras existente **fluxo** objetos, você pode truncar esses bytes ou caracteres definindo a nova posição final de fluxo com **SetEOS**.  
  
> [!CAUTION]
>  Se você definir **EOS** para uma posição antes do final do fluxo real, você perderá todos os dados depois que o novo **EOS** posição.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Stream (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
