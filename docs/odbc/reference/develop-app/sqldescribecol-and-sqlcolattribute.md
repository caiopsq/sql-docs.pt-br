---
title: SQLDescribeCol e SQLColAttribute | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQLColAttribute function [ODBC], and SQLDescribeCol
- SQLDescribeCol function [ODBC], and SQLColAttribute
- result sets [ODBC], metadata
- retrieving result set meta data [ODBC]
- metadata [ODBC], result set
ms.assetid: c2ca442c-03a8-4e0f-9e67-b300bb15962f
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a99551fd76b68af9d48b5d97f8ef696259c8661e
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32914011"
---
# <a name="sqldescribecol-and-sqlcolattribute"></a>SQLDescribeCol e SQLColAttribute
**SQLDescribeCol** e **SQLColAttribute** são usados para recuperar metadados de conjunto de resultados. A diferença entre essas duas funções é que **SQLDescribeCol** sempre retorna as mesmo cinco peças de informação (uma coluna Nome, tipo de dados, precisão, escala e nulidade), enquanto **SQLColAttribute** retorna uma única informação solicitada pelo aplicativo. No entanto, **SQLColAttribute** pode retornar uma seleção muito mais rica de metadados, incluindo diferenciação de uma coluna, exibir o tamanho, a atualização e a capacidade de pesquisa.  
  
 Muitos aplicativos, especialmente aqueles que só exibem dados, exigem apenas os metadados retornados por **SQLDescribeCol**. Para esses aplicativos, é mais rápido usar **SQLDescribeCol** que **SQLColAttribute** porque as informações são retornadas em uma única chamada. Outros aplicativos, especialmente aqueles que atualizam dados, exigem os metadados adicionais retornados por **SQLColAttribute** e, portanto, usar ambas as funções. Além disso, **SQLColAttribute** dá suporte a metadados específicos do driver; para obter mais informações, consulte [tipos de dados específicos do Driver, tipos de descritor, tipos de informações, tipos de diagnóstico e atributos](../../../odbc/reference/develop-app/driver-specific-data-types-descriptor-information-diagnostic.md).  
  
 Um aplicativo pode recuperar metadados de conjunto de resultados a qualquer momento depois que uma instrução foi preparada ou executada e antes do cursor sobre o resultado do conjunto é fechado. Muito poucos aplicativos exigem metadados de conjunto de resultados após a instrução é preparada e antes de ser executado. Se possível, os aplicativos devem esperar para recuperar metadados até depois que a instrução é executada, pois algumas fontes de dados não é possível retornar metadados para instruções preparadas e geralmente é um processo lento emular esse recurso no driver. Por exemplo, o driver pode gerar um resultado de linha de zero definido, substituindo o **onde** cláusula de um **selecione** instrução com a cláusula **WHERE 1 = 2** e executar o instrução resultante.  
  
 Metadados geralmente são caro para recuperar da fonte de dados. Por isso, drivers devem armazenar em cache todos os metadados que recuperar do servidor e mantenha para enquanto o cursor sobre o resultado do conjunto estiver aberto. Além disso, os aplicativos devem solicitar apenas os metadados que absolutamente necessitam.
