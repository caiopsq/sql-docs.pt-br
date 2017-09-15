---
title: "Referência da API do JDBC Driver | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b55da26-ddeb-4e89-872a-91e0aba57103
caps.latest.revision: 42
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 2bd1cf731f49119e54fb9e5a548a8988af1ef9fc
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="sqlsrv-driver-api-reference"></a>Referência da API do driver JDBC
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

O nome da API para o driver SQLSRV nos [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] é **sqlsrv**. Todos os **sqlsrv** funções começam com **sqlsrv _** e são seguidas por um verbo ou um substantivo. As que são seguidas por um verbo executam alguma ação, e as que são seguidas por um substantivo retornam alguma forma de metadados.  
  
## <a name="in-this-section"></a>Nesta seção  
O driver SQLSRV contém as seguintes funções:  
  
|Função|Description|  
|------------|---------------|  
|[sqlsrv_begin_transaction](../../connect/php/sqlsrv-begin-transaction.md)|Começa uma transação.|  
|[sqlsrv_cancel](../../connect/php/sqlsrv-cancel.md)|Cancela uma instrução; descarta qualquer resultado pendente para a instrução.|  
|[sqlsrv_client_info](../../connect/php/sqlsrv-client-info.md)|Fornece informações sobre o cliente.|  
|[sqlsrv_close](../../connect/php/sqlsrv-close.md)|Fecha uma conexão. Libera todos os recursos associados à conexão.|  
|[sqlsrv_commit](../../connect/php/sqlsrv-commit.md)|Confirma uma transação.|  
|[sqlsrv_configure](../../connect/php/sqlsrv-configure.md)|Altera as configurações de log e tratamento de erros.|  
|[sqlsrv_connect](../../connect/php/sqlsrv-connect.md)|Cria e abre uma conexão.|  
|[sqlsrv_errors](../../connect/php/sqlsrv-errors.md)|Retorna informações de erro e/ou avisos sobre a última operação.|  
|[sqlsrv_execute](../../connect/php/sqlsrv-execute.md)|Executa uma instrução preparada.|  
|[sqlsrv_fetch](../../connect/php/sqlsrv-fetch.md)|Disponibiliza a próxima linha de dados para leitura.|  
|[sqlsrv_fetch_array](../../connect/php/sqlsrv-fetch-array.md)|Recupera a próxima linha de dados como uma matriz indexada numericamente, matriz associativa ou ambas.|  
|[sqlsrv_fetch_object](../../connect/php/sqlsrv-fetch-object.md)|Recupera a próxima linha de dados como um objeto.|  
|[sqlsrv_field_metadata](../../connect/php/sqlsrv-field-metadata.md)|Retorna metadados do campo.|  
|[sqlsrv_free_stmt](../../connect/php/sqlsrv-free-stmt.md)|Fecha uma instrução. Libera todos os recursos associados à instrução.|  
|[sqlsrv_get_config](../../connect/php/sqlsrv-get-config.md)|Retorna o valor da configuração especificada.|  
|[sqlsrv_get_field](../../connect/php/sqlsrv-get-field.md)|Recupera um campo na linha atual por índice. O tipo de retorno PHP pode ser especificado.|  
|[sqlsrv_has_rows](../../connect/php/sqlsrv-has-rows.md)|Detecta se um conjunto de resultados tem uma ou mais linhas.|  
|[sqlsrv_next_result](../../connect/php/sqlsrv-next-result.md)|Torna o próximo resultado disponível para processamento.|  
|[sqlsrv_num_rows](../../connect/php/sqlsrv-num-rows.md)|Informa o número de linhas em um conjunto de resultados.|  
|[sqlsrv_num_fields](../../connect/php/sqlsrv-num-fields.md)|Recupera o número de campos em um conjunto de resultados ativo.|  
|[sqlsrv_prepare](../../connect/php/sqlsrv-prepare.md)|Prepara uma consulta Transact-SQL sem executá-la. Associa parâmetros implicitamente.|  
|[sqlsrv_query](../../connect/php/sqlsrv-query.md)|Prepara e executa uma consulta Transact-SQL.|  
|[sqlsrv_rollback](../../connect/php/sqlsrv-rollback.md)|Reverte uma transação.|  
|[sqlsrv_rows_affected](../../connect/php/sqlsrv-rows-affected.md)|Retorna o número de linhas modificadas.|  
|[sqlsrv_send_stream_data](../../connect/php/sqlsrv-send-stream-data.md)|Envia até oito quilobytes (8 KB) de dados para o servidor com cada chamada para a função.|  
|[sqlsrv_server_info](../../connect/php/sqlsrv-server-info.md)|Fornece informações sobre o servidor.|  
  
## <a name="reference"></a>Referência  
[Manual do PHP](http://go.microsoft.com/fwlink/?LinkId=105500)  
  
## <a name="see-also"></a>Consulte também  
[Visão geral do Driver SQL de PHP](../../connect/php/overview-of-the-php-sql-driver.md)
[constantes &#40; Drivers da Microsoft para PHP para SQL Server &#41;](../../connect/php/constants-microsoft-drivers-for-php-for-sql-server.md)  
[Guia de programação para o driver SQL de PHP](../../connect/php/programming-guide-for-php-sql-driver.md)
[Introdução ao driver SQL de PHP](../../connect/php/getting-started-with-the-php-sql-driver.md)
  
