---
title: Resolvedores personalizados baseados em COM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- COM-based resolvers [SQL Server replication]
- custom resolvers [SQL Server replication]
ms.assetid: 94195797-ad7a-4962-a8e3-b259cd13aa38
caps.latest.revision: 35
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9809787b2a674b176bd7ef21a1091aecdd106d6d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37271162"
---
# <a name="com-based-custom-resolvers"></a>COM-Based Custom Resolvers
  Resolvedores personalizados fornecem maior flexibilidade do que o mecanismo de resolução padrão, e podem implementar a lógica comercial exigida por aplicativos usando dados replicados. Um resolvedor personalizado com base em COM é uma biblioteca de vínculo dinâmico (DLL) que implementa a interface COM **ICustomResolver** , seus métodos e propriedades e outras interfaces de suporte e definições de tipo criadas especificamente para resolução de conflito.  
  
> [!NOTE]  
>  Se possível, recomenda-se o uso de um manipulador de lógica de negócios em vez de um resolvedor personalizado com base em COM. Para obter mais informações sobre manipuladores de lógica de negócios, consulte [Executar lógica de negócios durante a sincronização de mesclagem](execute-business-logic-during-merge-synchronization.md).  
  
 Para criar um resolvedor COM personalizado, é possível usar a biblioteca de tipos fornecida em replrec.dll; por padrão, essa biblioteca é instalada em [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]COM.  
  
 Antes de gravar um resolvedor COM personalizado, é necessário decidir:  
  
-   Os tipos de alterações de linhas que você quer resolver, como atualizações, inserções e exclusões, e se o resolvedor deve ser chamado durante o carregamento de alterações de mesclagem, o download de alterações de mesclagem ou ambos. É possível especificar um tipo de alteração, todas as alterações ou qualquer combinação. O resolvedor de conflito padrão de mesclagem controla quaisquer conflitos não controlados por um resolvedor personalizado.  
  
-   Quando usar controle de coluna ao resolver o conflito. Quando rastreamento de nível de coluna estiver habilitado, somente dados naquelas colunas em que existir um conflito serão sinalizados como conflito, caso contrário os dados serão mesclados. No entanto, conflitos são resolvidos da mesma forma que rastreamento em nível de linha: o vencedor de prioridade substitui toda a coluna de dados (mas os dados podem ser uma mistura de valores do Publicador, Assinantes ou alguns valores alterados que não eram nem do Publicador e nem dos Assinantes). Para obter mais informações, consulte [Detect and Resolve Merge Replication Conflicts](advanced-merge-replication-resolve-merge-replication-conflicts.md).  
  
 Para implementar um resolvedor de conflito personalizado com base em COM, consulte [Implement a Custom Conflict Resolver for a Merge Article](../implement-a-custom-conflict-resolver-for-a-merge-article.md).  
  
 Um resolvedor personalizado é especificado para um artigo, não para uma publicação inteira. O mesmo resolvedor pode ser usado com mais de um artigo, mas a lógica em resolvedores personalizados é em geral específica para uma determinada tabela. Se a tabela usada no artigo for modificada depois que o resolvedor for criado (por exemplo, renomeando o nome da coluna que é usada em resolução de conflito), o resolvedor personalizado pode precisar ser modificado e recompilado.  
  
 Para especificar um resolvedor personalizado, consulte [Specify a Merge Article Resolver](../publish/specify-a-merge-article-resolver.md).  
  
## <a name="see-also"></a>Consulte também  
 [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md)   
 [Microsoft COM-Based Resolvers](advanced-merge-replication-conflict-com-based-resolvers.md)  
  
  
