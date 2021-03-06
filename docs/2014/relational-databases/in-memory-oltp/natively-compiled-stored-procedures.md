---
title: Procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: in-memory-oltp
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- natively compiled stored procedures
ms.assetid: d5ed432c-10c5-4e4f-883c-ef4d1fa32366
caps.latest.revision: 54
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 79dbaba00d9eb8ff0b344fb713ee6599344ec317
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2018
ms.locfileid: "40392238"
---
# <a name="natively-compiled-stored-procedures"></a>procedimentos armazenados compilados nativamente
  Os procedimentos armazenados compilados nativamente são procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] compilados no código nativo que acessam tabelas com otimização de memória. Procedimentos armazenados compilados nativamente permitem a execução eficiente de consultas e lógica de negócios no procedimento armazenado. Para obter mais detalhes sobre o processo de compilação nativo, consulte [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md). Para obter mais informações sobre como migrar procedimentos armazenados baseados em disco para os procedimentos armazenados compilados nativamente, consulte [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).  
  
> [!NOTE]  
>  Uma diferença entre procedimentos armazenados interpretados (com base em disco) e procedimentos armazenados compilados nativamente é que o procedimento armazenado interpretado é criado na primeira execução enquanto que um procedimento armazenado compilado nativamente é compilado quando é criado. Com os procedimentos armazenados compilados nativamente, muitas condições de erro (estouro aritmético, conversão de tipo e algumas condições de divisão por zero) podem ser detectadas no momento da criação e causarão a falha na geração do procedimento armazenado compilado nativamente. Com os procedimentos armazenados interpretados, essas condições de erro geralmente não causarão uma falha quando o procedimento armazenado for criado, mas todas as execuções falharão.  
  
 Tópicos desta seção:  
  
-   [Criando procedimentos armazenados compilados nativamente](creating-natively-compiled-stored-procedures.md)  
  
-   [Blocos atômicos](atomic-blocks-in-native-procedures.md)  
  
-   [Construções com suporte nos procedimentos armazenados compilados de modo nativo](supported-features-for-natively-compiled-t-sql-modules.md)  
  
-   [Usando Try...Catch em procedimentos armazenados compilados nativamente](../../database-engine/using-try-catch-in-natively-compiled-stored-procedures.md)  
  
-   [Construções com suporte em procedimentos armazenados compilados de modo nativo](supported-ddl-for-natively-compiled-t-sql-modules.md)  
  
-   [Procedimentos armazenados compilados nativamente e opções de execução Set](natively-compiled-stored-procedures-and-execution-set-options.md)  
  
-   [Práticas recomendadas para chamar procedimentos armazenados compilados nativamente](best-practices-for-calling-natively-compiled-stored-procedures.md)  
  
-   [Monitorando o desempenho de procedimentos armazenados compilados nativamente](monitoring-performance-of-natively-compiled-stored-procedures.md)  
  
-   [Chamando procedimentos armazenados compilados nativamente em aplicativos de acesso a dados](calling-natively-compiled-stored-procedures-from-data-access-applications.md)  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas com otimização de memória](memory-optimized-tables.md)  
  
  
