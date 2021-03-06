---
title: Elemento Database para configuração (DTA) | Microsoft Docs
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
- Database element
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
caps.latest.revision: 12
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: fa99c86b6e4cc6705a04f0b1eecd1695033f50de
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37263882"
---
# <a name="database-element-for-configuration-dta"></a>Elemento de banco de dados para configuração (DTA)
  Especifica o banco de dados em relação ao qual você deseja que o orientador de otimização do mecanismo de banco de dados para avaliar a configuração hipotética (especificada pelo `Configuration` elemento).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|**Comprimento e tipo de dados**|Nenhum.|  
|**Valor padrão**|Nenhum.|  
|**Ocorrência**|Exigido uma ou mais vezes por `Server` elemento.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elementos|  
|------------------|--------------|  
|**Elemento pai**|[Elemento Server para a configuração &#40;DTA&#41;](server-element-for-configuration-dta.md)|  
|**Elementos filho**|[Nome de elemento para o banco de dados &#40;DTA&#41;](name-element-for-database-dta.md)<br /><br /> [Elemento de esquema para o banco de dados &#40;DTA&#41;](schema-element-for-database-dta.md)<br /><br /> [Elemento de recomendação &#40;DTA&#41;](recommendation-element-dta.md)|  
  
## <a name="remarks"></a>Remarks  
 Esse elemento tem o nome **DatabaseTypecomplexType** no esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados. Não confunda esse elemento `Database` com o elemento cujo pai raiz é o elemento `Server` que ocorre no topo do arquivo de entrada XML. Para obter mais informações, veja [Elemento Database para servidor &#40;DTA&#41;](database-element-for-server-dta.md).  
  
## <a name="example"></a>Exemplo  
 Para obter um exemplo de uso deste `Database` elemento, consulte a [amostra do arquivo de entrada XML com configuração especificada pelo usuário &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).  
  
## <a name="see-also"></a>Consulte também  
 [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
