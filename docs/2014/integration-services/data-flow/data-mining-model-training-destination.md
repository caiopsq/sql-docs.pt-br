---
title: Destino de treinamento do modelo de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
caps.latest.revision: 45
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2bb23745ab0858cb598fd668d5f066f0e247d817
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37171007"
---
# <a name="data-mining-model-training-destination"></a>Destino de treinamento do modelo de mineração de dados
  Um destino de treinamento de modelos de mineração de dados treina modelos de mineração de dados ao passar os dados que o destino recebe pelos algoritmos de modelo de mineração de dados. Vários modelos de mineração de dados poderão ser treinados por um destino se os modelos forem criados na mesma estrutura de mineração de dados. Para obter mais informações, consulte [Mining Structure Columns](../../analysis-services/data-mining/mining-structure-columns.md) e [Mining Model Columns](../../analysis-services/data-mining/mining-model-columns.md).  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a>Configuração do destino Treinamento de Modelo de Mineração de Dados  
 Se uma coluna de nível de caso da estrutura de destino e os modelos criados na estrutura tiverem o tipo de conteúdo KEY TIME ou KEY SEQUENCE, os dados de entrada deverão ser classificados nessa coluna. Por exemplo, os modelos criados pelo algoritmo do Microsoft Time Series utilizam o tipo de conteúdo KEY TIME. Se os dados de entrada não forem classificados, o processamento do modelo poderá falhar. Se os dados exigirem a classificação, você poderá usar uma transformação do tipo Classificação antecipadamente no fluxo de dados para classificá-los. Esse requisito não se aplica a colunas com o tipo de conteúdo KEY. Para obter mais informações, consulte [Tipos de Conteúdo &#40; mineração de dados&#41;](../../analysis-services/data-mining/content-types-data-mining.md) e [Transformação Sort](transformations/sort-transformation.md).  
  
> [!NOTE]  
>  A entrada para o destino Treinamento de Modelo de Mineração de Dados deve ser classificada. Para classificar os dados, você pode incluir um upstream de destino do tipo Classificação a partir do destino Treinamento de Modelo de Mineração de Dados no fluxo de dados. Para obter mais informações, consulte [Sort Transformation](transformations/sort-transformation.md).  
  
 Este destino tem uma entrada e nenhuma saída.  
  
 O destino Treinamento de Modelo de Mineração de Dados utiliza um gerenciador de conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se conecta ao projeto ou à instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém a estrutura de mineração e os modelos de mineração treinados pelo destino. Para obter mais informações, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).  
  
 Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.  
  
 Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Treinamento de Modelo de Mineração de Dados** , clique em um dos seguintes tópicos:  
  
-   [Editor de treinamento do modelo de mineração de dados &#40;guia de Conexão&#41;](../data-mining-model-training-editor-connection-tab.md)  
  
-   [Editor de treinamento do modelo de mineração de dados &#40;guia colunas&#41;](../data-mining-model-training-editor-columns-tab.md)  
  
 A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente. Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:  
  
-   [Propriedades comuns](../common-properties.md)  
  
-   [Propriedades personalizadas do destino treinamento do modelo de mineração de dados](data-mining-model-training-destination-custom-properties.md)  
  
 Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).  
  
  
