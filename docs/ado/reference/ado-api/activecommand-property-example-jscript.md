---
title: Exemplo de propriedade ActiveCommand (JScript) | Microsoft Docs
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
- JScript
helpviewer_keywords:
- ActiveCommand property [ADO], JScript example
ms.assetid: be09e2af-ba31-4168-8ccd-2461bb24e49a
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4272cda6ce23406661c216944a155b2de6d61349
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35275005"
---
# <a name="activecommand-property-example-jscript"></a>Exemplo de propriedade ActiveCommand (JScript)
Este exemplo demonstra o [ActiveCommand](../../../ado/reference/ado-api/activecommand-property-ado.md) propriedade. Recorte e cole o seguinte código ao bloco de notas ou outro editor de texto e salve-o como **ActiveCommandJS.asp**.  
  
```  
<!-- BeginActiveCommandJS -->  
<%@LANGUAGE="JScript" %>  
<%// use this meta tag instead of adojavas.inc%>  
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" -->  
  
<%  
    // user input  
    strName = new String(Request.Form("ContactName"))  
%>  
  
<html>  
  
<head>  
<title>ActiveCommand Property Example (JScript)</title>  
<style>  
<!--  
BODY {  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;  
   BACKGROUND-COLOR:white;  
   COLOR:black;  
    }  
-->  
</style>  
</head>  
  
<body bgcolor="White">  
  
<h1>ActiveCommand Property Example (JScript)</h1>  
  
<%  
if (strName.length > 0)  
    {  
        // connection and recordset variables  
        var Cnxn = Server.CreateObject("ADODB.Connection")  
        var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" +  
            "Initial Catalog='Northwind';Integrated Security='SSPI';";  
        var cmdContact = Server.CreateObject("ADODB.Command");  
        var rsContact = Server.CreateObject("ADODB.Recordset");  
        // display variables  
        var strMessage;  
  
        try  
        {  
            // open connection  
            Cnxn.Open(strCnxn);  
  
            // Open a recordset using a command object  
            cmdContact.CommandText = "SELECT ContactName FROM Customers WHERE City = ?";  
            cmdContact.ActiveConnection = Cnxn;  
            // create parameter and insert variable value  
            cmdContact.Parameters.Append(cmdContact.CreateParameter("ContactName", adChar, adParamInput, 30, strName));  
  
            rsContact = cmdContact.Execute();  
  
            while(!rsContact.EOF){  
                // start new line  
                strMessage = "<P>";  
  
                // get data  
                strMessage += rsContact("ContactName")  
  
                // end the line  
                strMessage += "</P>";  
  
                // show data  
                Response.Write(strMessage);  
  
                // get next record  
                rsContact.MoveNext;  
            }  
        }  
        catch (e)  
        {  
            Response.Write(e.message);  
        }  
        finally  
        {  
            // 'clean up  
            if (rsContact.State == adStateOpen)  
                rsContact.Close;  
            if (Cnxn.State == adStateOpen)  
                Cnxn.Close;  
            rsContact = null;  
            Cnxn = null;  
        }  
    }  
%>  
  
<hr>  
  
<form method="POST" action="ActiveCommandJS.asp">  
  <p align="left">Enter city of customer to find (e.g., Paris): <input type="text" name="ContactName" size="40" value=""></p>  
  <p align="left"><input type="submit" value="Submit" name="B1"><input type="reset" value="Reset" name="B2"></p>  
</form>  
</body>  
  
</html>  
<!-- EndActiveCommandJS -->  
```  
  
## <a name="see-also"></a>Consulte também  
 [Propriedade ActiveCommand (ADO)](../../../ado/reference/ado-api/activecommand-property-ado.md)   
 [Objeto de comando (ADO)](../../../ado/reference/ado-api/command-object-ado.md)   
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
