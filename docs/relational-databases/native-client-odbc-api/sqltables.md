---
title: SQLTables | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
caps.latest.revision: 38
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: e8d0d9983b49d235831699ef0d269a7415bb276e
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39536126"
---
# <a name="sqltables"></a>SQLTables
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  SQLTables pode ser executado em um cursor de servidor estático. Uma tentativa de executar SQLTables em um cursor atualizável (dinâmico ou conjunto de chaves) retornará SQL_SUCCESS_WITH_INFO, indicando que o tipo de cursor foi alterado.  
  
 SQLTables relatórios de tabelas de todos os bancos de dados quando o *CatalogName* parâmetro é SQL_ALL_CATALOGS e todos os outros parâmetros contêm valores padrão (ponteiros NULL).  
  
 Para relatar catálogos disponíveis, esquemas e tipos de tabela, SQLTables faz uso especial de cadeias de caracteres vazias (ponteiros de comprimento zero bytes). As cadeias de caracteres vazias não são os valores padrões (ponteiros NULL).  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client dá suporte a informações de relatórios para tabelas em servidores vinculados, aceitando um nome de duas partes para o *CatalogName* parâmetro: *linked_server_name*.  
  
 SQLTables retorna informações sobre quaisquer tabelas cujo nomes correspondem ao *TableName* e são de propriedade do usuário atual.  
  
## <a name="sqltables-and-table-valued-parameters"></a>SQLTables e parâmetros com valor de tabela  
 Quando o atributo de instrução SQL_SOPT_SS_NAME_SCOPE tem o valor SQL_SS_NAME_SCOPE_TABLE_TYPE, em vez de seu valor padrão sql_ss_name_scope_table, SQLTables retorna informações sobre tipos de tabela. O valor TABLE_TYPE retornado para um tipo de tabela na coluna 4 do conjunto de resultados retornado por SQLTables é o tipo de tabela. Para obter mais informações sobre SQL_SOPT_SS_NAME_SCOPE, consulte [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md).  
  
 Tabelas, exibições e sinônimos compartilham um namespace comum que é diferente do namespace usado por tipos de tabela. Apesar de não ser possível ter uma tabela e uma exibição com o mesmo nome, é possível ter uma tabela de um tipo de tabela com o mesmo nome, no mesmo catálogo e no mesmo esquema.  
  
 Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;ODBC&#41;](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="example"></a>Exemplo  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a>Consulte também  
 [Função SQLTables](http://go.microsoft.com/fwlink/?LinkId=59374)   
 [Detalhes da implementação da API do ODBC](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
