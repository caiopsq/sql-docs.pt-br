---
title: Adicionar pontos vazios a um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-design
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 2b056119-439f-494f-83cf-ee0c05dc6487
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dfa20f918ae7c5c932e298c371ee9253af7b8d6e
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33020583"
---
# <a name="add-empty-points-to-a-chart-report-builder-and-ssrs"></a>Adicionar pontos vazios a um gráfico (Construtor de Relatórios e SSRS)
Valores nulos são mostrados no gráfico como espaços vazios ou lacunas entre os pontos de dados em uma série. Nos relatórios paginados do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , pontos vazios são pontos de dados que podem ser inseridos em um espaço vazio criado por valores nulos.  
  
 Por padrão, pontos vazios são calculados pela média dos pontos de dados anteriores e seguintes que contêm um valor. Você pode alterar isso para que todos os pontos vazios sejam inseridos como zero.  
  
 Para obter mais informações, consulte [Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/empty-and-null-data-points-in-charts-report-builder-and-ssrs.md).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-specify-empty-points-on-a-chart"></a>Para especificar pontos vazios em um gráfico  
  
1.  Abra o painel Propriedades.  
  
2.  Na superfície de design, clique com o botão direito do mouse na série que contém valores nulos. As propriedades da série são exibidas no painel Propriedades.  
  
3.  Expanda o nó **EmptyPoint** .  
  
4.  Selecione um valor de cor para a propriedade Color.  
  
5.  No nó **EmptyPoint** , expanda o nó Marker.  
  
6.  Selecione um tipo de marcador para a propriedade MarkerType.  
  
    > [!NOTE]  
    >  Você deve selecionar um tipo de marcador para adicionar pontos vazios a um gráfico de barras, colunas ou de dispersão. No entanto, para gráficos de área, linha e radar, a seleção de um tipo de marcador é opcional porque o gráfico preenche o espaço vazio ou a lacuna sem precisar da especificação de um marcador.  
  
7.  Defina o valor do ponto vazio.  
  
    1.  No painel Propriedades, expanda o nó **CustomAttributes** .  
  
    2.  Defina a propriedade EmptyPointValue. Para inserir pontos vazios em uma média dos pontos de dados anteriores e seguintes, selecione **Média**. Para inserir pontos vazios em zero, selecione **Zero**.  
  
## <a name="see-also"></a>Consulte Também  
 [Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/chart-types-report-builder-and-ssrs.md)   
 [Adicionar quebras de escala a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/add-scale-breaks-to-a-chart-report-builder-and-ssrs.md)   
 [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  
