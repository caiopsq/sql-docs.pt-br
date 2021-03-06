---
title: Exemplo de propriedades de precisão (VB) e NumericScale | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- Precision property [ADOX], Visual Basic example
- NumericScale property [ADOX], Visual Basic example
ms.assetid: ea2ec614-34c8-41b7-8ebd-063798bd56b4
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0776d768a8cbfa8d1ac252cdc90a07bc9fae8f07
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35284885"
---
# <a name="adox-code-example-numericscale-and-precision-properties-example-vb"></a>Exemplo de código ADOX: NumericScale e exemplo de propriedades de precisão (VB)
Este exemplo demonstra o [NumericScale](../../../ado/reference/adox-api/numericscale-property-adox.md) e [precisão](../../../ado/reference/adox-api/precision-property-adox.md) propriedades do [coluna](../../../ado/reference/adox-api/column-object-adox.md) objeto. Este código exibe o valor para o **Order Details** tabela do *Northwind* banco de dados.  
  
```  
' BeginNumericScalePrecVB  
Sub Main()  
    On Error GoTo NumericScalePrecXError  
  
    Dim cnn As New ADODB.Connection  
    Dim cat As New ADOX.Catalog  
    Dim tblOD As ADOX.Table  
    Dim colLoop As ADOX.Column  
  
    ' Connect the catalog.  
    cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _  
        "data source='Northwind.mdb';"  
    Set cat.ActiveConnection = cnn  
  
    ' Retrieve the Order Details table  
    Set tblOD = cat.Tables("Order Details")  
  
    ' Display numeric scale and precision of  
    ' small integer fields.  
    For Each colLoop In tblOD.Columns  
        If colLoop.Type = adSmallInt Then  
            MsgBox "Column: " & colLoop.Name & vbCr & _  
                "Numeric scale: " & _  
                colLoop.NumericScale & vbCr & _  
                "Precision: " & colLoop.Precision  
        End If  
    Next colLoop  
  
    'Clean up  
    cnn.Close  
    Set cat = Nothing  
    Set cnn = Nothing  
    Exit Sub  
  
NumericScalePrecXError:  
    Set cat = Nothing  
  
    If Not cnn Is Nothing Then  
        If cnn.State = adStateOpen Then cnn.Close  
    End If  
    Set cnn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
' EndNumericScalePrecVB  
```  
  
## <a name="see-also"></a>Consulte também  
 [Objeto de coluna (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)   
 [Propriedade NumericScale (ADOX)](../../../ado/reference/adox-api/numericscale-property-adox.md)   
 [Propriedade Precision (ADOX)](../../../ado/reference/adox-api/precision-property-adox.md)
