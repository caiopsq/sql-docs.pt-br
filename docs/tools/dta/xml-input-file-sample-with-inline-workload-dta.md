---
title: Exemplo do arquivo de entrada XML com carga de trabalho embutida (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: dta
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0f27f7a05aeb74baff4e806aaece83223996b701
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37990148"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a>Amostra do arquivo de entrada XML com carga de trabalho embutida (DTA)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Copie e cole esta amostra em um arquivo de entrada XML que especifica uma carga de trabalho com o elemento **EventString** em seu editor de XML ou editor de texto favorito. Você pode usar o elemento **EventString** para especificar uma carga de trabalho de script [!INCLUDE[tsql](../../includes/tsql-md.md)] no arquivo de entrada XML em vez de usar um arquivo de carga de trabalho separado. Depois de copiar esta amostra na ferramenta de edição, substitua os valores especificados dos elementos **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**e **TuningOptions** pelos valores de sua sessão de ajuste específica. Para obter mais informações sobre todos os atributos e elementos filho que podem ser usados com esses elementos, veja a [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md). O exemplo a segui usa um subconjunto de atributo único disponível e opções de elemento filho.  
  
## <a name="code"></a>Código  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../tools/dta/codesnippet/xml/xml-input-file-sample-wi_1.xml)]  
  
## <a name="comments"></a>Comentários  
 `USE database_name` As instruções podem ser especificadas na carga de trabalho embutida, contida no elemento **EventString** .  
  
## <a name="see-also"></a>Consulte Também  
 [Iniciar e usar o Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)   
 [Exibir e trabalhar com a saída do Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md)   
 [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
