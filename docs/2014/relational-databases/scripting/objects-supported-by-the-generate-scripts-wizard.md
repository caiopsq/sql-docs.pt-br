---
title: Objetos com suporte no Assistente para Gerar Scripts | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e2d0cc8bb86c84b9b4c9416f844eaff8251b3445
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37233076"
---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a>Objetos com suporte no Assistente para Gerar Scripts
  O Assistente para Gerar e Publicar Scripts oferece suporte a um subconjunto dos objetos com suporte no [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].  
  
## <a name="supported-objects"></a>Objetos com suporte  
 A seguinte tabela lista os objetos que podem ser publicados e as versões com suporte do Assistente para Gerar e Publicar Scripts.  
  
||||||  
|-|-|-|-|-|  
|Função de aplicativo|Função de banco de dados|esquema|Agregação definida pelo usuário|Modo de exibição<sup>1</sup>|  
|Assembly|Restrição DEFAULT|Procedimento armazenado<sup>1</sup>|Tipo de dados definido pelo usuário|Coleção de esquemas XML|  
|Restrição CHECK|Catálogo de texto completo|Sinônimo|Função definida pelo usuário||  
|Procedimento armazenado CLR (common language runtime)<sup>1</sup>|Índice|Table|Tabela definida pelo usuário||  
|Função CLR definida pelo usuário|Regra|Usuário<sup>2</sup>|Tipo definido pelo usuário||  
  
 <sup>1</sup> publicado sem criptografia.  
  
 <sup>2</sup> quaisquer usuários de fora do sistema que existem no banco de dados são publicados como funções.  
  
  
