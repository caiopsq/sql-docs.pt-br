---
title: Indicadores (ODBC) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- result sets [ODBC], bookmarks
- bookmarks [ODBC]
ms.assetid: 1d7cccc5-f847-4321-b240-28570854ee5c
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 791350c93e2570ad8615e5b378e9979870e02acf
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="bookmarks-odbc"></a>Indicadores (ODBC)
Um indicador é um valor usado para identificar uma linha de dados. O significado do valor de indicador só é conhecido para o driver ou a fonte de dados. Por exemplo, ele poderá ser tão simples quanto um número de linha ou tão complexo quanto um endereço de disco. Indicadores em ODBC são um pouco diferentes de indicadores em livros reais. Em um livro real, o leitor coloca um indicador em uma página específica e, em seguida, procura esse indicador retornar à página. Em ODBC, o aplicativo solicita um indicador para uma linha específica, armazena-o e transmite-o novamente ao cursor para que retorne à linha. Assim, indicadores em ODBC são semelhantes a um leitor de anotar um número de página lembrá-la e, em seguida, procura novamente a página.  
  
 Para determinar o suporte do driver de indicadores, um aplicativo chama **SQLGetInfo** com a opção SQL_BOOKMARK_PERSISTENCE. Os bits nesse valor descrevem o que os indicadores de operações sobrevivem, como se marcadores ainda são válidas depois que o cursor é fechado.  
  
 Esta seção contém os tópicos a seguir.  
  
-   [Tipos de indicador](../../../odbc/reference/develop-app/bookmark-types.md)  
  
-   [Recuperando indicadores](../../../odbc/reference/develop-app/retrieving-bookmarks.md)  
  
-   [Rolando pelo indicador](../../../odbc/reference/develop-app/scrolling-by-bookmark.md)  
  
-   [Atualizar, excluir ou buscar por indicador](../../../odbc/reference/develop-app/updating-deleting-or-fetching-by-bookmark.md)  
  
-   [Comparando indicadores](../../../odbc/reference/develop-app/comparing-bookmarks.md)