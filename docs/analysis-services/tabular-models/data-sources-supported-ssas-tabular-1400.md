---
title: Fontes de dados com suporte em modelos de tabela 1400 do Analysis Services do SQL Server | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 856e15e7365128bc79d119afe267334fb8470832
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38041654"
---
# <a name="data-sources-supported-in-sql-server-analysis-services-tabular-1400-models"></a>Fontes de dados com suporte no SQL Server Analysis Services, modelos de tabela 1400

[!INCLUDE[ssas-appliesto-sql2017](../../includes/ssas-appliesto-sql2017.md)]

Este artigo descreve os tipos de fontes de dados que podem ser usados com modelos de tabela do SQL Server Analysis Services (SSAS) no nível de compatibilidade 1400. 

Para modelos de tabela do SSAS nos níveis de compatibilidade 1200 e inferior, consulte [fontes de dados com suporte em modelos do SQL Server Analysis Services tabulares 1200](data-sources-supported-ssas-tabular.md).

Para o Azure Analysis Services, consulte [fontes de dados com suporte no Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-datasource).


## <a name="cloud-data-sources"></a>Fontes de dados de nuvem

|Fonte de dados do Azure  |Na memória  |DirectQuery  |
|---------|---------|---------|
|Banco de dados SQL do Azure     |   Sim      |    Sim      |
|Azure SQL Data Warehouse     |   Sim      |   Sim       |
|Armazenamento de blobs do Azure     |   Sim       |    não      |
|Armazenamento de tabelas do Azure    |   Sim       |    não      |
|Azure Cosmos DB      |  Sim        |  não        |
|Azure Data Lake Store     |   Sim       |    não      |
|HDFS do HDInsight do Azure     |     Sim     |   não       |
|Azure HDInsight Spark (Beta)     |   Sim       |   não       |
||||

**Provedor**   
Na memória e os modelos DirectQuery se conectar a fontes de dados do Azure usam o .NET Framework Data Provider para SQL Server.

## <a name="on-premises-data-sources"></a>Fontes de dados locais

### <a name="supported-by-in-memory-and-directquery-models"></a>Compatível com modelos na memória e DirectQuery

|Fonte de dados | Provedor na memória | Provedor do DirectQuery |
|  --- | --- | --- |
| SQL Server |SQL Server Native Client 11.0, provedor Microsoft OLE DB para SQL Server, o .NET Framework Data Provider para SQL Server | Provedor de dados do .NET Framework para SQL Server |
| SQL Server Data Warehouse |SQL Server Native Client 11.0, provedor Microsoft OLE DB para SQL Server, o .NET Framework Data Provider para SQL Server | Provedor de dados do .NET Framework para SQL Server |
| Oracle |Provedor Microsoft OLE DB para Oracle, o provedor de dados Oracle para .NET |Provedor de dados Oracle para .NET | |
| Teradata |Provedor OLE DB para Teradata, provedor de dados Teradata para .NET |Provedor de dados Teradata para .NET | |
| | | |

> [!NOTE]
> Para modelos na memória, provedores OLE DB podem fornecer um melhor desempenho para dados em larga escala. Ao escolher entre diferentes provedores para a mesma fonte de dados, tente primeiro o provedor OLE DB.  

### <a name="supported-by-in-memory-models-only"></a>Com suporte apenas a modelos na memória

|banco de dados  |
|---------|---------|---------|
|Banco de dados do Access     | 
|SQL Server Analysis Services     | 
|IBM Informix (beta) | 
|Documento JSON     | 
|Linhas de binário     | 
|Banco de dados MySQL     | 
|Banco de dados PostgreSQL    | Sim | não
|SAP HANA   | Sim | não
|SAP Business Warehouse    | Sim | não
|Banco de dados Sybase     | Sim | não
|||

|Arquivo  |  
|---------|---------|
|Pasta de trabalho do Excel     |
|Pasta     | 
|JSON | 
|Texto/CSV    | 
|Tabela XML    | 
|||

|Serviços online  |  
|---------|---------|
|Dynamics 365      |
|Exhange Online     |
|Objetos de Saleforce    | 
|Relatórios do Salesforce     |
|Lista do SharePoint Online     |
|||

|Outro  |  
|---------|---------|
|Active Directory      | 
|Exhange     |  
|Feed OData     | 
|Consulta ODBC     | 
|OLE DB  | 
|Lista do SharePoint | 
|||

## <a name="see-also"></a>Confira também

[Fontes de dados com suporte no SQL Server Analysis Services, modelos de tabela 1200](data-sources-supported-ssas-tabular.md)

[Fontes de dados com suporte no Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-datasource)   
