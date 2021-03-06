---
title: Conjunto de linhas DMSCHEMA_MINING_SERVICES | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- DMSCHEMA_MINING_SERVICES
topic_type:
- apiref
helpviewer_keywords:
- DMSCHEMA_MINING_SERVICES rowset
ms.assetid: 4a672f2f-d637-4def-a572-c18556f83d34
caps.latest.revision: 34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e6ccfdba24d7bc23b97eb15e61321f82e5ab1d9b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37278205"
---
# <a name="dmschemaminingservices-rowset"></a>Conjunto de linhas DMSCHEMA_MINING_SERVICES
  Oferece uma descrição de cada algoritmo de mineração de dados suportado pelo provedor.  
  
## <a name="rowset-columns"></a>Colunas do conjunto de linhas  
 O `DMSCHEMA_MINING_SERVICES` linhas contém as colunas a seguir.  
  
|Nome da coluna|Indicador de tipo|Comprimento|Description|  
|-----------------|--------------------|------------|-----------------|  
|`SERVICE_NAME`|`DBTYPE_WSTR`||O nome do algoritmo. Esta coluna é específica do provedor.|  
|`SERVICE_TYPE_ID`|`DBTYPE_UI4`||Essa coluna contém um bitmap que descreve o serviço de mineração. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] preenche esta coluna com um dos seguintes valores:<br /><br /> -   `DM_SERVICETYPE_CLASSIFICATION` (`1`)<br />-   `DM_SERVICETYPE_CLUSTERING` (`2`)|  
|`SERVICE_DISPLAY_NAME`|`DBTYPE_WSTR`||Um nome para exibição localizável para o algoritmo.|  
|`SERVICE_GUID`|`DBTYPE_GUID`||O GUID para o algoritmo.|  
|`DESCRIPTION`|`DBTYPE_WSTR`||Uma descrição amigável do algoritmo.|  
|`PREDICTION_LIMIT`|`DBTYPE_UI4`||O número máximo de previsões que o modelo e o algoritmo podem oferecer.|  
|`SUPPORTED_DISTRIBUTION_FLAGS`|`DBTYPE_WSTR`||Uma lista de sinalizadores delimitada por vírgulas que descreve as distribuições estatísticas suportadas pelo algoritmo. Esta coluna contém um ou mais dos valores a seguir:<br /><br /> -   "`NORMAL`"<br />-   "`LOG NORMAL`"<br />-   "`UNIFORM`"|  
|`SUPPORTED_INPUT_CONTENT_TYPES`|`DBTYPE_WSTR`||Uma lista de sinalizadores delimitada por vírgulas que descreve os tipos de conteúdo de entrada suportados pelo algoritmo. Esta coluna contém um ou mais dos valores a seguir:<br /><br /> -   "`KEY`"<br />-   "`DISCRETE`"<br />-   "`CONTINUOUS`"<br />-   "`DISCRETIZED`"<br />-   "`ORDERED`"<br />-"CHAVE `SEQUENCE`"<br />-   "`CYCLICAL`"<br />-   "`PROBABILITY`"<br />-   "`VARIANCE`"<br />-   "`STDEV`"<br />-   "`SUPPORT`"<br />-   "`PROBABILITY VARIANCE`"<br />-   "`PROBABILITY STDEV`"<br />-   "`KEY TIME`"|  
|`SUPPORTED_PREDICTION_CONTENT_TYPES`|`DBTYPE_WSTR`||Uma lista de sinalizadores delimitada por vírgulas que descreve os tipos de conteúdo de previsão suportados pelo algoritmo. Esta coluna contém um ou mais dos valores a seguir:<br /><br /> -   "`KEY`"<br />-   "`DISCRETE`"<br />-   "`CONTINUOUS`"<br />-   "`DISCRETIZED`"<br />-   "`ORDERED`"<br />-"CHAVE `SEQUENCE` "<br />-   "`CYCLICAL`"<br />-   "`PROBABILITY`"<br />-   "`VARIANCE`"<br />-   "`STDEV`"<br />-   "`SUPPORT`"<br />-   "`PROBABILITY VARIANCE`"<br />-   "`PROBABILITY STDEV`"<br />-"TEMPO-CHAVE"|  
|`SUPPORTED_MODELING_FLAGS`|`DBTYPE_WSTR`||Uma lista delimitada por vírgulas dos sinalizadores de modelagem suportados pelo algoritmo. Esta coluna contém um ou mais dos valores a seguir:<br /><br /> -   "`MODEL_EXISTENCE_ONLY`"<br />-   "`REGRESSOR`"<br /><br /> Os sinalizadores específicos do provedor também podem ser definidos.|  
|`SUPPORTED_SOURCE_QUERY`|`DBTYPE_WSTR`||-Esta coluna é suportada para compatibilidade com versões anteriores.|  
|`TRAINING_COMPLEXITY`|`DBTYPE_I4`||O período do tempo esperado para o treinamento:<br /><br /> -   `DM_TRAINING_COMPLEXITY_LOW` indica que o tempo de execução é relativamente curto e é proporcional à entrada.<br />-   **DM_TRAINING_COMPLEXITY_MEDIUM** indica que o tempo de execução pode ser longo, mas é geralmente proporcional à entrada.<br />-   **DM_TRAINING_COMPLEXITY_HIGH** indica que o tempo de execução é longo e pode crescer exponencialmente em relação ao número de casos de treinamento.|  
|`PREDICTION_COMPLEXITY`|`DBTYPE_I4`||O período de tempo esperado para a previsão:<br /><br /> -   **DM_PREDICTION_COMPLEXITY_LOW** indica que o tempo de execução é relativamente curto e é proporcional à entrada.<br />-   **DM_PREDICTION_COMPLEXITY_MEDIUM** indica que o tempo de execução pode ser longo, mas é geralmente proporcional à entrada.<br />-   **DM_PREDICTION_COMPLEXITY_HIGH** indica que o tempo de execução é longo e pode crescer exponencialmente em relação ao número de casos de treinamento.|  
|`EXPECTED_QUALITY`|`DBTYPE_I4`||A qualidade esperada do modelo gerado com este algoritmo:<br /><br /> -   `DM_EXPECTED_QUALITY_LOW`<br />-   `DM_EXPECTED_QUALITY_MEDIUM`<br />-   **DM_EXPECTED_QUALITY_HIGH**|  
|`SCALING`|`DBTYPE_I4`||A escalabilidade do algoritmo:<br /><br /> -   **DM_SCALING_LOW**<br />-   `DM_SCALING_MEDIUM`<br />-   **DM_SCALING_HIGH**|  
|`ALLOW_INCREMENTAL_INSERT`|`DBTYPE_BOOL`||Um Booliano que indica se o algoritmo suporta treinamento incremental, ou seja, a atualização dos padrões descobertos com base em novos dados reais, em vez da redescoberta total dos padrões.|  
|`ALLOW_PMML_INITIALIZATION`|`DBTYPE_BOOL`||Um Booliano que indica se os modelos de mineração podem ser criados com base em uma cadeia de caracteres PMML 2.1.<br /><br /> Se for `TRUE`, o algoritmo de mineração suporta a inicialização a partir de conteúdo PMML 2.1.|  
|`CONTROL`|`DBTYPE_I4`||O suporte dado pelo serviço caso o treinamento seja interrompido:<br /><br /> -   `DM_CONTROL_NONE` indica que o algoritmo não pode ser cancelado após ele ser iniciado treinar o modelo.<br />-   `DM_CONTROL_CANCEL` indica que o algoritmo pode ser cancelado após ele começa a treinar o modelo, mas deve ser reiniciado para retomar o treinamento.<br />-   `DM_CONTROL_SUSPENDRESUME` indica que o algoritmo pode ser cancelado e reiniciado a qualquer momento, mas os resultados não estão disponíveis até que o treinamento estiver concluído.<br />-   `DM_CONTROL_SUSPENDWITHRESULT` indica que o algoritmo pode ser cancelado e reiniciado a qualquer momento, e qualquer resultado incremental pode ser obtido.|  
|`ALLOW_DUPLICATE_KEY`|`DBTYPE_BOOL`||Um Booliano que indica se as ocorrências podem conter chaves duplicadas.<br /><br /> Se for `VARIANT_TRUE`, as ocorrências poderão conter chaves duplicadas.|  
|`VIEWER_TYPE`|`DBTYPE_WSTR`||O visualizador recomendado para este modelo.|  
|`HELP_FILE`|`DBTYPE_WSTR`||(Opcional) O nome do arquivo que contém a documentação para este serviço.|  
|`HELP_CONTEXT`|`DBTYPE_I4`||(Opcional) A ID de contexto da Ajuda para este serviço.|  
|`MSOLAP_SUPPORTS_ANALYSIS_SERVICES_DDL`|`DBTYPE_WSTR`||A versão do DDL suportada. 0 indica nenhum suporte a DDL.|  
|`MSOLAP_SUPPORTS_OLAP_MINING_MODELS`|`DBTYPE_BOOL`||Um Booliano que indica se modelos de mineração OLAP podem ser criados.<br /><br /> Se for `TRUE`, modelos de mineração OLAP poderão ser criados. Exige que `MSOLAP_SUPPORTS_ANALYSIS_SERVICES_DDL` seja diferente de zero.|  
|`MSOLAP_SUPPORTS_DATA_MINING_DIMENSIONS`|`DBTYPE_BOOL`||Um Booliano que indica se dimensões de mineração de dados podem ser criadas.<br /><br /> Se for `TRUE`, dimensões de mineração de dados poderão ser criadas.|  
|`MSOLAP_SUPPORTS_DRILLTHROUGH`|`DBTYPE_BOOL`||Um Booliano que indica se o serviço oferece suporte a recursos de detalhamento.<br /><br /> Se for `TRUE`, o serviço oferecerá suporte a recursos de detalhamento.|  
  
## <a name="restriction-columns"></a>Colunas de restrição  
 O conjunto de linhas `DMSCHEMA_MINING_SERVICES` pode ser restringido nas colunas listadas na tabela a seguir.  
  
|Nome da coluna|Indicador de tipo|Estado de restrição|  
|-----------------|--------------------|-----------------------|  
|`SERVICE_NAME`|`DBTYPE_WSTR`|Opcional.|  
|`SERVICE_TYPE_ID`|`DBTYPE_UI4`|Opcional.|  
  
## <a name="see-also"></a>Consulte também  
 [Conjuntos de linhas de esquema de mineração de dados](../../schema-rowsets/data-mining/data-mining-schema-rowsets.md) 
  
  
