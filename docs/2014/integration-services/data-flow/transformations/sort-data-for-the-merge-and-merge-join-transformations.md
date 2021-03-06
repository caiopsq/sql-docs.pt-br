---
title: Classificar dados para as transformações Mesclagem e Junção de Mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- sort attributes [Integration Services]
- output columns [Integration Services]
ms.assetid: 22ce3f5d-8a88-4423-92c2-60a8f82cd4fd
caps.latest.revision: 30
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 21b60f8b5007ae574ab48bdd46e2e8f430b299cd
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37316056"
---
# <a name="sort-data-for-the-merge-and-merge-join-transformations"></a>Classificar dados para as transformações Mesclagem e Junção de Mesclagem
  No [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], as transformações Mesclagem e Junção de Mesclagem exigem dados classificados para suas entradas. Os dados de entrada devem ser classificados fisicamente e as opções de classificação devem ser definidas nas saídas e nas colunas de saída na origem ou na transformação upstream. Se as opções de classificação indicarem que os dados estão classificados, mas os dados não estiverem efetivamente classificados, os resultados da operação de mesclagem ou junção de mesclagem são imprevisíveis.  
  
## <a name="sorting-the-data"></a>Classificando os dados  
 Você pode classificar os dados usando um dos seguintes métodos:  
  
-   Na origem, use uma cláusula de ORDER BY na instrução utilizada para carregar os dados.  
  
-   No fluxo de dados, insira uma transformação Classificação antes da transformação Mesclagem ou Junção de Mesclagem.  
  
 Se os dados forem dados de cadeia de caracteres, as transformações Mesclagem e Junção de Mesclagem esperarão que os valores da cadeia de caracteres tenham sido classificados com o uso do agrupamento do Windows. Para fornecer valores de cadeia de caracteres às transformações Mesclagem e Junção de Mesclagem classificadas com o uso do agrupamento do Windows, use o procedimento a seguir.  
  
#### <a name="to-provide-string-values-that-are-sorted-by-using-windows-collation"></a>Para fornecer valores da cadeia de caracteres que são classificados usando agrupamento de Windows  
  
-   Use uma transformação Classificação para classificar os dados.  
  
     A transformação Classificação usa o agrupamento do Windows para classificar valores de cadeia de caracteres.  
  
     — ou —  
  
-   Primeiro use o operador CAST Transact-SQL para converter os valores `varchar` em valores `nvarchar` e, em seguida, use a cláusula ORDER BY Transact-SQL para classificar os dados.  
  
    > [!IMPORTANT]  
    >  Não é possível usar a cláusula ORDER BY sozinha porque ela utiliza um agrupamento do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para classificar valores de cadeia de caracteres. O uso do agrupamento do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pode resultar em uma ordem de classificação diferente do agrupamento do Windows, o que pode fazer com que a transformação Mesclar ou Junção de Mesclagem produza resultados inesperados.  
  
## <a name="setting-sort-options-on-the-data"></a>Definindo opções de classificação nos dados  
 Há duas propriedades de classificação importantes que devem ser definidas para a transformação de origem ou upstream que fornece dados às transformações Mesclar e Junção de Mesclagem:  
  
-   A propriedade `IsSorted` da saída que indica se os dados foram classificados. Essa propriedade deve ser definida como `True`.  
  
    > [!IMPORTANT]  
    >  Definindo o valor da `IsSorted` propriedade para `True` não classifica os dados. Esta propriedade apenas fornece uma dica aos componentes downstream de que os dados foram classificados previamente.  
  
-   O `SortKeyPosition` propriedade de colunas de saída que indica se uma coluna é classificada, ordem de classificação da coluna e a sequência na qual várias colunas são classificadas. Esta propriedade deve ser definida para cada coluna de dados classificados.  
  
 Se você usar a transformação Classificação para classificar os dados, essa transformação define ambas as propriedades como necessárias para a transformação Mesclar ou Junção de Mesclagem. Ou seja, a transformação classificação define a `IsSorted` propriedade de sua saída para `True`e define o `SortKeyPosition` propriedades de suas colunas de saída.  
  
 No entanto, se você não usar uma transformação Classificação para classificar os dados, defina essas propriedades de classificação manualmente na transformação de origem ou upstream. Para definir as propriedades de classificação manualmente na transformação de origem ou upstream, siga o procedimento a seguir.  
  
#### <a name="to-manually-set-sort-attributes-on-a-source-or-transformation-component"></a>Para definir atributos de classificação manualmente em um componente de origem ou transformação  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.  
  
2.  No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.  
  
3.  Na guia **Fluxo de Dados** , localize a transformação apropriada de origem ou upstream ou arraste-a da **Caixa de Ferramentas** para a superfície de design.  
  
4.  Clique com o botão direito do mouse no componente e clique em **Mostrar Editor Avançado**.  
  
5.  Clique na guia **Propriedades de Entrada e Saída** .  
  
6.  Clique em  **\<nome do componente > saída**e defina as `IsSorted` propriedade `True`.  
  
    > [!NOTE]  
    >  Se você definir manualmente as `IsSorted` propriedade da saída para `True` e os dados não forem classificados, ausências de dados ou comparações de dados inválidas na transformação downstream ou junção de mesclagem quando você executa o pacote.  
  
7.  Expanda **Colunas de Saída**.  
  
8.  Clique na coluna que você deseja indicar é classificada e defina seu `SortKeyPosition` propriedade para um valor inteiro diferente de zero, seguindo estas diretrizes:  
  
    -   O valor do número inteiro deve representar uma sequência numérica, começando com 1 e incrementado em 1.  
  
    -   Um valor inteiro positivo indica uma ordem de classificação crescente.  
  
    -   Um valor inteiro negativo indica uma ordem de classificação decrescente. (Se definido com um número negativo, o valor absoluto do número determinará a posição da coluna na sequência de classificação.)  
  
    -   O valor padrão de 0 indica que a coluna não está classificada. Deixe o valor de 0 para colunas de saída que não participam da classificação.  
  
     Como exemplo de como definir a propriedade `SortKeyPosition`, considere a seguinte instrução Transact-SQL que carrega os dados em uma origem:  
  
     `SELECT * FROM MyTable ORDER BY ColumnA, ColumnB DESC, ColumnC`  
  
     Para esta instrução, você definiria o `SortKeyPosition` propriedade para cada coluna da seguinte maneira:  
  
    -   Defina a propriedade `SortKeyPosition` da Coluna A como 1. Isso indica que a Coluna A é a primeira a ser classificada e é classificada em ordem crescente.  
  
    -   Defina a propriedade `SortKeyPosition` da Coluna B como -2. Isso indica que a Coluna B é a segunda a ser classificada e é classificada em ordem decrescente.  
  
    -   Defina o `SortKeyPosition` propriedade da coluna c como 3. Isso indica que a Coluna C é a terceira a ser classificada e é classificada em ordem crescente.  
  
9. Repita a etapa 8 para cada coluna classificada.  
  
10. Clique em **OK**.  
  
11. Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .  
  
## <a name="see-also"></a>Consulte também  
 [Transformação mesclar](merge-transformation.md)   
 [Transformação junção de mesclagem](merge-join-transformation.md)   
 [Transformações do Integration Services](integration-services-transformations.md)   
 [Caminhos do Integration Services](../integration-services-paths.md)   
 [Tarefa de fluxo de dados] ((.. /.. /Control-Flow/Data-Flow-Task.MD)  
  
  
