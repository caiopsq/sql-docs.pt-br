---
title: Classificar colunas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.sortcolumns.f1
ms.assetid: 66b44b6c-10a5-4e3f-a97b-7568609c88ac
caps.latest.revision: 6
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: d0610b65013bce66f4ebcb6f446d63ecaf656463
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37234826"
---
# <a name="sort-columns"></a>Classificar Colunas
  A caixa de diálogo **Classificar Colunas** permite classificar grades no Replication Monitor com base em uma ou mais colunas. (Você também pode classificar uma única coluna clicando no cabeçalho de coluna na grade do Replication Monitor.) Por exemplo, para classificar assinaturas na guia **Todas as Assinaturas** com base no status e no tipo de conexão, siga estas etapas:  
  
1.  Na primeira linha da grade, selecione **Status** na coluna **Nome da Coluna** e um valor na coluna **Ordem de Classificação**  
  
2.  Na segunda linha da grade, selecione **Tipo de Conexão** na coluna **Nome da Coluna** e um valor na coluna **Ordem de Classificação**  
  
## <a name="options"></a>Opções  
 **Nome da Coluna**  
 O nome da coluna na qual você quer classificar. Você pode classificar em uma ou mais colunas. Você não pode classificar as colunas **Desempenho Médio Atual** ou **Pior Desempenho Atual** na guia **Publicações** por causa da forma pela qual essas colunas são calculadas.  
  
 **Ordem de Classificação**  
 Especifique um valor **Crescente** ou **Decrescente**.  
  
 **Limpar Tudo**  
 Remove todas as linhas da grade de classificação. Para remover uma única linha, selecione a linha e pressione a tecla Delete.  
  
## <a name="see-also"></a>Consulte também  
 [Monitorando a Replicação](monitoring-replication.md)  
  
  
