---
title: Implementando uma classe Command para uma extensão de processamento de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: extensions
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- data processing extensions [Reporting Services], commands
- Command class
- commands [Reporting Services]
ms.assetid: 465ef8d1-c503-407c-8afd-58d620e344ee
caps.latest.revision: 35
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: cbd1bf5faa995f5ab249b8f96ad8700349a38a62
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33014973"
---
# <a name="implementing-a-command-class-for-a-data-processing-extension"></a>Implementando uma classe Command para uma extensão de processamento de dados
  O objeto **Command** formula uma solicitação e a passa para a fonte de dados. O texto do comando pode ter várias formas sintáticas diferentes, incluindo texto e XML. Se forem retornados resultados, o objeto **Command** retornará resultados como um objeto **DataReader**.  
  
 Para criar uma classe **Command**, implemente <xref:Microsoft.ReportingServices.DataProcessing.IDbCommand>. Implemente o método <xref:Microsoft.ReportingServices.DataProcessing.IDbCommand.ExecuteReader%2A> para retornar um conjunto de resultados como um objeto **DataReader**. O método <xref:Microsoft.ReportingServices.DataProcessing.IDbCommand.ExecuteReader%2A> da classe **Command** deve incluir uma implementação que usa uma enumeração <xref:Microsoft.ReportingServices.DataProcessing.CommandBehavior> como argumento. Se você implantar a sua extensão de processamento de dados no Designer de Relatórios, crie uma implementação que manipule um caso <xref:Microsoft.ReportingServices.DataProcessing.CommandBehavior.SchemaOnly> no método <xref:Microsoft.ReportingServices.DataProcessing.IDbCommand.ExecuteReader%2A>. Uma implementação somente esquema é usada para fornecer uma lista de campos ao Designer de Relatórios. O objeto **DataReader** retornado pelo método <xref:Microsoft.ReportingServices.DataProcessing.IDbCommand.ExecuteReader%2A> precisa conter informações de tipo e de nome para os campos ou colunas, do conjunto de resultados.  
  
 Opcionalmente, a classe **Command** pode implementar <xref:Microsoft.ReportingServices.DataProcessing.IDbCommandAnalysis>. Essa interface permite que uma classe de implementação analise uma consulta e retorne uma lista de parâmetros na consulta. A funcionalidade da interface <xref:Microsoft.ReportingServices.DataProcessing.IDbCommandAnalysis> só será usada no Designer de Relatórios. Quando você implementa <xref:Microsoft.ReportingServices.DataProcessing.IDbCommandAnalysis>, permite que sejam solicitados parâmetros dos usuários do Designer de Relatórios sempre que um relatório for executado em modo de visualização. Além disso, você pode exibir os parâmetros na guia **Parâmetros** da caixa de diálogo **Conjunto de Dados**.  
  
> [!NOTE]  
>  Você não deve implementar <xref:Microsoft.ReportingServices.DataProcessing.IDbCommandAnalysis> se a sua extensão de processamento de dados personalizada não der suporte a parâmetros.  
  
 Para obter uma implementação de exemplo da classe **Command**, consulte [Amostras de produto do SQL Server Reporting Services](http://go.microsoft.com/fwlink/?LinkId=177889).  
  
## <a name="see-also"></a>Consulte Também  
 [Extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [Implementando uma extensão de processamento de dados](../../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)   
 [Biblioteca de extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  
