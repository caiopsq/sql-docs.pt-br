---
title: Parâmetros de comando | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- parameters [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, parameters
- SQL Server Native Client OLE DB provider, commands
- parameters [SQL Server Native Client], OLE DB
- commands [OLE DB]
ms.assetid: 072ead49-ebaf-41eb-9a0f-613e9d990f26
caps.latest.revision: 39
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e2ae43260105acca3d638749d197e4e0d95a0260
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37426825"
---
# <a name="command-parameters"></a>Parâmetros de comando
  Os parâmetros são marcados no texto do comando com o caractere de ponto de interrogação. Por exemplo, a seguinte instrução SQL é marcada para um único parâmetro de entrada:  
  
```  
{call SalesByCategory('Produce', ?)}  
```  
  
 Para melhorar o desempenho, reduzindo o tráfego de rede, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client não deriva automaticamente informações de parâmetro, a menos que **ICommandWithParameters:: Getparameterinfo** ou  **Icommandprepare:: Prepare** é chamado antes de executar um comando. Isso significa que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client não automaticamente:  
  
-   Verifique a exatidão do tipo de dados especificado com **ICommandWithParameters:: SetParameterInfo**.  
  
-   Mapeie do DBTYPE especificado nas informações de associação do acessador para o tipo de dados correto do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do parâmetro.  
  
 Os aplicativos receberão erros possíveis ou perda de precisão com um desses métodos, se especificarem tipos de dados não compatíveis com o tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do parâmetro.  
  
 Para garantir que isso não aconteça, o aplicativo deve:  
  
-   Certifique-se de que *pwszDataSourceType* corresponde a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de dados para o parâmetro de caso de hard-coding **ICommandWithParameters:: SetParameterInfo**.  
  
-   Garantir que o valor DBTYPE associado ao parâmetro seja do mesmo tipo do tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do parâmetro em caso de hard-coding de um acessador.  
  
-   Codificar o aplicativo chamar **ICommandWithParameters:: Getparameterinfo** para que o provedor possa obter o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados dos parâmetros dinamicamente. Observe que isso causa uma viagem de ida e volta na rede adicional até o servidor.  
  
> [!NOTE]  
>  O provedor não dá suporte a chamar **ICommandWithParameters:: Getparameterinfo** para qualquer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instrução UPDATE ou DELETE que contém uma cláusula FROM; para qualquer instrução SQL, dependendo de uma subconsulta que contenha parâmetros; para instruções SQL que contém os marcadores de parâmetro em ambas as expressões de comparação, como, ou predicado; quantificado ou consultas em que um dos parâmetros é um parâmetro para uma função. Ao processar um lote de instruções SQL, o provedor também não suporta chamada **ICommandWithParameters:: Getparameterinfo** para marcadores de parâmetro nas instruções após a primeira instrução no lote. Comentários (/ * \*/) não são permitidos no [!INCLUDE[tsql](../../includes/tsql-md.md)] comando.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client dá suporte a parâmetros de entrada em comandos de instrução SQL. Em comandos de chamada de procedimento, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client dá suporte a parâmetros de entrada/saída, de entrada e saída. Os valores de parâmetro de saída são retornados para o aplicativo na execução (apenas se não houver nenhum conjunto de linhas retornado) ou quando todos os conjuntos de linhas retornados são esgotados pelo aplicativo. Para garantir que os valores retornados são válidos, use **IMultipleResults** para forçar o consumo de conjunto de linhas.  
  
 Os nomes dos parâmetros de procedimento armazenado não precisam ser especificados em uma estrutura DBPARAMBINDINFO. Use NULL para o valor da *pwszName* membro para indicar que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client deve ignorar o nome do parâmetro e usar apenas o ordinal especificado no *rgParamOrdinals*membro de **ICommandWithParameters:: SetParameterInfo**. Caso o texto do comando contenha parâmetros nomeados e sem-nome, todos os parâmetros sem-nome devem ser especificados antes de qualquer parâmetro nomeado.  
  
 Se o nome de um parâmetro de procedimento armazenado for especificado, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client verifica o nome para garantir que ele é válido. O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client retornará um erro quando ele recebe um nome de parâmetro incorreto do consumidor.  
  
> [!NOTE]  
>  Para expor o suporte para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML e tipos definidos pelo usuário (UDT), o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB do Native Client implementa uma nova [ISSCommandWithParameters](../native-client-ole-db-interfaces/isscommandwithparameters-ole-db.md) interface.  
  
## <a name="see-also"></a>Consulte também  
 [Comandos](commands.md)  
  
  
