---
title: Coleções (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services]
- collections [Master Data Services], about collections
ms.assetid: 5aa1d1e0-b4e5-4897-8e74-01dcf418df73
caps.latest.revision: 9
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 09f40b94ef25384fb36223964d77afacf98ea9ed
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37184683"
---
# <a name="collections-master-data-services"></a>Coleções (Master Data Services)
  Uma coleção é um grupo de membros folha e consolidados de uma única entidade. Use coleções quando não precisar de uma hierarquia completa e desejar exibir agrupamentos diferentes de membros para relatório ou análise, ou quando precisar criar uma taxonomia.  
  
## <a name="what-collections-contain"></a>O que as coleções contêm  
 Coleções não limitam o número ou o tipo de membros que podem ser incluídos, desde que os membros estejam dentro da mesma entidade. Uma coleção pode conter membros folha e consolidados de várias hierarquias explícitas obrigatórias e não obrigatórias.  
  
 Quando você cria uma coleção, não está criando uma estrutura hierárquica; você está criando uma lista simples de membros. Quando você seleciona um nó de uma hierarquia e adiciona-o à coleção, o membro consolidado selecionado é o único membro acrescentado à coleção.  
  
 Uma coleção também pode conter outras coleções. É possível usar coleções de coleções para criar taxonomias.  
  
 Quando cria uma coleção, você é listado automaticamente como o proprietário. Se você for um administrador, poderá criar outros atributos para a coleção conforme necessário.  
  
> [!NOTE]  
>  Para poder criar uma coleção, a entidade deve estar habilitada para hierarquias explícitas. Para obter mais informações, consulte [habilitar uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).  
  
## <a name="subscription-views-for-collections"></a>Exibições de assinatura para coleções  
 Há dois tipos de exibições de assinatura que mostram coleções. O formato **Atributos da coleção** mostra uma lista de coleções e todos os atributos relacionados às coleções (como descrição ou proprietário). O formato **Coleções** mostra todos os membros em todas as coleções, bem como cada peso de membros e a ordem de classificação. Para obter mais informações, consulte [exportação de dados &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).  
  
 Se você definir valores de peso para membros específicos em uma coleção, estes valores estarão disponíveis em exibições de assinatura relacionadas.  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Descrição da tarefa|Tópico|  
|----------------------|-----------|  
|Habilitar uma entidade para hierarquias explícitas e coleções.|[Habilitar uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|  
|Criar uma nova coleção.|[Criar uma coleção &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-collection-master-data-services.md)|  
|Adicionar membros a uma coleção existente.|[Adicionar membros a uma coleção &#40;Master Data Services&#41;](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)|  
  
## <a name="related-content"></a>Conteúdo relacionado  
  
-   [Hierarquias explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
-   [Exportação de dados &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md)  
  
  
