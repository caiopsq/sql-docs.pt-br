---
title: Elemento de tabela para esquema (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Table element [DTA]
ms.assetid: a59e8319-05d1-47f3-af39-7d970ab8e7dc
caps.latest.revision: 13
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: f58288d90c1a3158f4757856b51b7374ee07f167
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37187753"
---
# <a name="table-element-for-schema-dta"></a>Elemento de tabela para esquema (DTA)
  Especifica a tabela para ajuste.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
<Schema>  
...code removed here...  
    <Table>...</Table>  
```  
  
## <a name="element-attributes"></a>Atributos do elemento  
  
|attribute|Description|  
|---------------|-----------------|  
|`NumberOfRows`|Opcional. Inteiro que permite simular tabelas de tamanhos diferentes.|  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|**Comprimento e tipo de dados**|**string**, entre 1 e 255 caracteres.|  
|**Valor padrão**|Nenhum.|  
|**Ocorrência**|Opcional. Lista tantas tabelas quanto for apropriado para sua carga de trabalho.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elementos|  
|------------------|--------------|  
|**Elemento pai**|[Elemento de esquema para o banco de dados &#40;DTA&#41;](schema-element-for-database-dta.md)|  
|**Elementos filho**|[Nomeie o elemento para a tabela &#40;DTA&#41;](name-element-for-table-dta.md)|  
  
## <a name="remarks"></a>Remarks  
 Se você não especificar um elemento `Table`, o Orientador de Otimização do Mecanismo de Banco de Dados assumirá que todas as tabelas no banco de dados especificado podem ser ajustadas.  
  
## <a name="example"></a>Exemplo  
 Para obter um exemplo de uso, veja [Elemento Server&#40;DTA&#41;](server-element-dta.md).  
  
## <a name="see-also"></a>Consulte também  
 [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
