---
title: dm_execution_performance_counters (banco de dados SSISDB) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 1b38e8e3-c560-4b6e-b60e-bfd7cfcd4fdf
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 67d5ece89f5b964acb2bb55a8cc69ff2fb77b93b
ms.contentlocale: pt-br
ms.lasthandoff: 09/26/2017

---
# <a name="functions---dmexecutionperformancecounters"></a>Funções - dm_execution_performance_counters
[!INCLUDE[tsql-appliesto-ss2014-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2014-xxxx-xxxx-xxx-md.md)]

  Retorna a estatística de desempenho para uma execução que está em execução no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
## <a name="syntax"></a>Sintaxe  
  
```sql  
dm_execution_performance_counters [ @execution_id = ] execution_id  
  
```  
  
## <a name="arguments"></a>Argumentos  
 [ @execution_id =] *execution_id*  
 O identificador exclusivo da execução que contém um ou mais pacotes. Pacotes que são executados com a tarefa Executar Pacote, executados na mesma execução que o pacote pai.  
  
 Se uma ID de execução não for especificada, a estatística de desempenho para várias execuções será retornada. Se você for membro da função de banco de dados **ssis_admin** , as estatísticas de desempenho de todas as execuções em andamento serão retornadas.  Se você não for membro da função de banco de dados **ssis_admin** , as estatísticas de desempenho das execuções em andamento para as quais você tem permissões de leitura serão retornadas. O *execution_id* é um **BigInt**.  
  
## <a name="remarks"></a>Comentários  
 A tabela a seguir lista os valores de nomes de contadores retornados pela função dm_execution_performance_counter.  
  
|Nome do contador|Description|  
|------------------|-----------------|  
|Bytes de BLOB lidos|Número de bytes de dados BLOB (objetos binários grandes) que o mecanismo de fluxo de dados lê em todas as origens.|  
|Bytes de BLOB gravados|Número de bytes de dados BLOB, mecanismo de fluxo de dados grava todos os destinos.|  
|Arquivos de BLOB em uso|Número de arquivos de BLOB que o mecanismo de fluxo de dados está usando para o spool.|  
|Memória de buffer|Quantidade de memória usada pelos buffers do Integration Services, inclusive memória física e virtual.|  
|Buffers em uso|Número de objetos de buffer, de todos os tipos, que todos os componentes de fluxo de dados e o mecanismo de fluxo de dados estão usando.|  
|Buffers em spool|Número de buffers gravados em disco.|  
|Memória de buffer simples|Quantidade de memória, em bytes, usada por todos os buffers simples. Buffers simples são blocos de memória que um componente usa para armazenar dados.|  
|Buffers simples em uso|Número de buffers simples usados pelo mecanismo de fluxo de dados. Todos os buffers simples são buffers privados.|  
|Memória de buffer privada|Quantidade de memória em uso por todos os buffers privados. Um buffer privado é um buffer usado por uma transformação para trabalho temporário.<br /><br /> Um buffer não será privado se o mecanismo de fluxo de dados o criar para dar suporte ao fluxo de dados.|  
|Buffers privados em uso|Número de buffers usados pelas transformações para trabalho temporário.|  
|Linhas lidas|Número total de linhas prontas para execução.|  
|Linhas gravadas|Número total de linhas gravadas pela execução.|  
  
## <a name="return"></a>Retorno  
 A função dm_execution_performance_counters retorna uma tabela com as colunas a seguir, para uma execução em execução. As informações retornadas são de todos os pacotes contidos na execução. Se não houver nenhuma execução em execução, uma tabela vazia será retornada.  
  
|Nome da coluna|Tipo de coluna|Description|Comentários|  
|-----------------|-----------------|-----------------|-------------|  
|execution_id|**BigInt**<br /><br /> **NULO** não é um valor válido.|Identificador exclusivo da execução que contém o pacote.||  
|counter_name|**nvarchar (128)**|O nome do contador.|Consulte o **comentários** seção de valores.|  
|counter_value|**BigInt**|Valor retornado pelo contador.||  
  
## <a name="example"></a>Exemplo  
 No exemplo a seguir, a função retorna a estatística para uma execução com ID 34.  
  
```sql
select * from [catalog].[dm_execution_performance_counters] (34)  
```  
  
## <a name="example"></a>Exemplo  
 No exemplo a seguir, a função retorna a estatística de todas as execuções realizadas no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], dependendo das suas permissões.  
  
```sql
select * from [catalog].[dm_execution_performance_counters] (NULL)  
  
```  
  
## <a name="permissions"></a>Permissões  
 Essa função exige uma das seguintes permissões:  
  
-   Permissões READ e MODIFY na instância de execução  
  
-   Associação de **ssis_admin** função de banco de dados  
  
-   Associação de **sysadmin** função de servidor  
  
## <a name="errors-and-warnings"></a>Erros e avisos  
 A lista a seguir descreve as condições que podem provocar falha na função.  
  
-   O usuário não tem permissões MODIFY para a execução especificada.  
  
-   A ID da execução especificada não é válida.  
  
  