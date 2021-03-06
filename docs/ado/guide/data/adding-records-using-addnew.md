---
title: Adicionando registros usando AddNew | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- AddNew method [ADO]
- ADO, adding data
- editing data [ADO], AddNew method
ms.assetid: cab4adff-f22f-4fb1-9217-f8138c795268
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 36827d102d7e6ef0850c557eb6555135343fbec0
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35270085"
---
# <a name="adding-records-using-addnew-method"></a>Adicionando registros usando o método AddNew
Esta é a sintaxe básica do **AddNew** método:

 *conjunto de registros*. AddNew *FieldList*, *valores*

 O *FieldList* e *valores* argumentos são opcionais. *Lista de campos* é um nome único ou uma matriz de nomes ou posições ordinais dos campos no novo registro.

 O *valores* argumento for um único valor ou uma matriz de valores para os campos no novo registro.

 Normalmente, quando você pretende adicionar um registro único, você chamará o **AddNew** método sem argumentos. Especificamente, você chamará **AddNew**; defina a **valor** de cada campo no novo registro; e, em seguida, chame **atualização** ou **UpdateBatch**, ou ambos. Você pode garantir que seu **registros** dá suporte à adição de novos registros usando o **dá suporte a** propriedade com o **adAddNew** constante enumerada.

 O código a seguir usa essa técnica para adicionar uma novo transportadora ao exemplo **registros**. SQL Server fornece o valor do campo CódigoDaTransportadora automaticamente. Portanto, o código não tenta fornecer um valor de campo para os novos registros.

```
'BeginAddNew1.1
If objRs.Supports(adAddNew) Then
    With objRs
        .AddNew
        .Fields("CompanyName") = "Sample Shipper"
        .Fields("Phone") = "(931) 555-6334"
        .Update
    End With
End If
'EndAddNew1.1
```

## <a name="remarks"></a>Remarks
 Porque esse código usa um desconectada **registros** com um cursor do lado do cliente no modo de lote, você deve reconectar o **registros** à fonte de dados com um novo **Conexão** objeto antes de chamar o **UpdateBatch** método para postar as alterações no banco de dados. Isso é feito facilmente usando a nova função **GetNewConnection**.
