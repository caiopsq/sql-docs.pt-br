---
title: Como usar um procedimento armazenado sem parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: e9470a6d-a758-4c56-96ec-7b37139e36a7
caps.latest.revision: 18
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6bd763d709238c6bd25fbe7a90acb7b617004925
ms.sourcegitcommit: 2f9cafc1d7a3773a121bdb78a095018c8b7c149f
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39661828"
---
# <a name="using-a-stored-procedure-with-no-parameters"></a>Usando um procedimento armazenado sem parâmetros

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

O tipo mais simples de procedimento armazenado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] que é possível chamar é aquele que não contém parâmetros e retorna um único conjunto de resultados. O [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] fornece a classe [SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md), que pode ser usada para chamar esse tipo de procedimento armazenado e processar os dados retornados.

Ao usar o driver JDBC para chamar um procedimento armazenado sem parâmetros, você deve usar a sequência de escape SQL `call`. A sintaxe da sequência de escape `call` sem parâmetros é a seguinte:

`{call procedure-name}`

> [!NOTE]  
> Para obter mais informações sobre as sequências de escape SQL, consulte [usando sequências de Escape SQL](../../connect/jdbc/using-sql-escape-sequences.md).

Como exemplo, crie o seguinte procedimento armazenado no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]:

```sql
CREATE PROCEDURE GetContactFormalNames
AS  
BEGIN  
   SELECT TOP 10 Title + ' ' + FirstName + ' ' + LastName AS FormalName
   FROM Person.Contact  
END  
```

Esse procedimento armazenado retorna um único conjunto de resultados que contém uma coluna de dados, uma combinação do título, do nome e do sobrenome dos 10 primeiros contatos presentes na tabela Person.Contact.

No exemplo a seguir, uma conexão aberta com o banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] é passada para a função, e o método [executeQuery](../../connect/jdbc/reference/executequery-method-sqlserverstatement.md) é usado para chamar o procedimento armazenado GetContactFormalNames.

```java
public static void executeSprocNoParams(Connection con) throws SQLException {  
    try(Statement stmt = con.createStatement();) {  

        ResultSet rs = stmt.executeQuery("{call dbo.GetContactFormalNames}");  
        while (rs.next()) {  
            System.out.println(rs.getString("FormalName"));  
        }  
    }  
}
```

## <a name="see-also"></a>Consulte Também

[Usando instruções com procedimentos armazenados](../../connect/jdbc/using-statements-with-stored-procedures.md)
