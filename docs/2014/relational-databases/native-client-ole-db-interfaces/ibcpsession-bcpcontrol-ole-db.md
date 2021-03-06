---
title: 'Ibcpsession:: Bcpcontrol (OLE DB) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- IBCPSession::BCPControl (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPControl method
ms.assetid: d58f3fe1-45e3-4e46-8e9c-000971829d99
caps.latest.revision: 49
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f1e1d13ff0d31dee51eacaaffe71e5b4a53e1b24
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37408435"
---
# <a name="ibcpsessionbcpcontrol-ole-db"></a>IBCPSession::BCPControl (OLE DB)
  Define as opções para uma operação de cópia em massa.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
HRESULT BCPControl(   
inteOption,  
void *iValue);  
```  
  
## <a name="remarks"></a>Remarks  
 O método **BCPControl** define vários parâmetros de controle para operações de cópia em massa, inclusive o número de erros permitidos antes de cancelar uma cópia em massa, os números da primeira e da última linha a serem copiadas de um arquivo de dados e o tamanho do lote.  
  
 Esse método também é usado para especificar a instrução SELECT a ser usada na cópia em massa de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Você pode definir as `eOption` argumento como BCP_OPTION_HINTS e `iValue` argumento para ter um ponteiro para uma cadeia de caracteres de caractere largo que contém a instrução SELECT.  
  
 Os valores possíveis para *eOption* são:  
  
|Opção|Description|  
|------------|-----------------|  
|BCP_OPTION_ABORT|Para uma operação de cópia em massa que já está em andamento. Você pode chamar o método **BCPControl** com um argumento *eOption* com valor BCP_OPTION_ABORT de outro thread para parar uma operação de cópia em massa em execução. O argumento *iValue* é ignorado.|  
|BCP_OPTION_BATCH|O número de linhas por lote. O padrão é 0, que indica que todas as linhas de uma tabela quando os dados estiverem sendo extraídos, ou todas as linhas no arquivo de dados do usuário quando os dados estiverem sendo copiados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Um valor menor que 1 reinicia BCP_OPTION_BATCH para o valor padrão.|  
|BCP_OPTION_DELAYREADFMT|Um booliano, se definido como true, fará com que [ibcpsession:: Bcpreadfmt](ibcpsession-bcpreadfmt-ole-db.md) Leia na execução. Se false (padrão), ibcpsession:: Bcpreadfmt será imediatamente ler o arquivo de formato. Ocorrerá um erro de sequência se `BCP_OPTION_DELAYREADFMT` é a verdadeira e você chamar ibcpsession:: BCPColumns ou ibcpsession:: BCPColFmt.<br /><br /> Um erro de sequência também ocorrerá se você chamar `IBCPSession::BCPControl(BCPDELAYREADFMT, (void *)FALSE))` depois de chamar `IBCPSession::BCPControl(BCPDELAYREADFMT, (void *)TRUE)` e ibcpsession:: Bcpwritefmt.<br /><br /> Para obter mais informações, consulte [descoberta de metadados](../native-client/features/metadata-discovery.md).|  
|BCP_OPTION_FILECP|O argumento *iValue* contém o número da página de código para o arquivo de dados. Você pode especificar o número da página de código, como 1252 ou 850, ou um dos seguintes valores:<br /><br /> -BCP_FILECP_ACP: os dados no arquivo estão na página de código Microsoft Windows® do cliente.<br />-BCP_FILECP_OEMCP: os dados no arquivo estão na página de código OEM do cliente (padrão).<br />-BCP_FILECP_RAW: os dados no arquivo estão na página de código do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|BCP_OPTION_FILEFMT|O número de versão do formato de arquivo de dados. Pode ser 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]) ou 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]. 120 é o padrão. Isso é útil para exportar e importar dados em formatos que tinham suporte em versões anteriores do servidor.  Por exemplo, para importar dados obtidos de uma coluna de texto em uma [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server em uma **varchar (max)** coluna em um [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] servidor ou posterior, você deve especificar 80. Da mesma forma, se você especificar 80 ao exportar dados de um **varchar (max)** coluna, ele será salvo como colunas de texto são salvos na [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Formatar e podem ser importados para uma coluna de texto de um [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server.|  
|BCP_OPTION_FIRST|A primeira linha de dados do arquivo ou da tabela a ser copiada. O padrão é 1; um valor menor que 1 redefine essa opção para seu valor padrão.|  
|BCP_OPTION_FIRSTEX|Para operações de saída BCP, especifica a primeira linha da tabela do banco de dados a ser copiada no arquivo de dados.<br /><br /> Para BCP em operações, especifica a primeira linha do arquivo de dados a ser copiada na tabela de banco de dados.<br /><br /> Espera-se que o parâmetro *iValue* seja o endereço de um inteiro de 64 bits assinado que contenha o valor. O valor máximo que pode ser passado para BCPFIRSTEX é 2^63-1.|  
|BCP_OPTION_FMTXML|Usado para especificar que o arquivo de formato gerado deve estar no formato XML. Por padrão, está desativado, o que implica que os arquivos formatados são salvos como arquivos de texto. O arquivo de formato XML fornece maior flexibilidade, mas com algumas restrições adicionais. Por exemplo, não é possível especificar o prefixo e terminador para um campo simultaneamente, o que é possível em arquivos de formatos mais antigos. **Observação:** arquivos de formato XML só são suportados quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ferramentas são instaladas junto com [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.|  
|BCP_OPTION_HINTS|O argumento *iValue* contém um ponteiro de cadeia de caracteres largo. A cadeia de caracteres endereçada especifica dicas de processamento da cópia em massa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] que retorna um conjunto de resultados. Se uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] especificada retornar mais de um conjunto de resultados, todos os conjuntos de resultados depois do primeiro serão ignorados.|  
|BCP_OPTION_KEEPIDENTITY|Quando o *iValue* argumento é definido como TRUE, esta opção especifica que os métodos de cópia em massa inserem valores de dados fornecidos para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colunas definidas com uma restrição de identidade. O arquivo de entrada deve fornecer valores para as colunas de identidade. Se essa opção não for definida, novos valores de identidade serão gerados para as linhas inseridas. Quaisquer dados contidos no arquivo para as colunas de identidade serão ignorados.|  
|BCP_OPTION_KEEPNULLS|Especifica se valores de dados vazios no arquivo serão convertidos em valores NULL na tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Quando o *iValue* argumento é definido como TRUE, valores vazios serão convertidos para NULL no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela. O padrão será converter valores vazios em um valor padrão para a coluna na tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se houver um padrão.|  
|BCP_OPTION_LAST|A última linha a ser copiada. O padrão é copiar todas as linhas. Um valor menor que 1 redefine esta opção para seu valor padrão.|  
|BCP_OPTION_LASTEX|Para operações de saída BCP, especifica a última linha da tabela do banco de dados a ser copiada no arquivo de dados.<br /><br /> Para BCP em operações, especifica a última linha do arquivo de dados a ser copiada na tabela do banco de dados.<br /><br /> Espera-se que o parâmetro *iValue* seja o endereço de um inteiro de 64 bits assinado que contenha o valor. O valor de máximo que pode ser passado para BCPLASTEX é 2^63-1.|  
|BCP_OPTION_MAXERRS|O número de erros permitido antes da falha da operação de cópia em massa. O padrão é 10. Um valor menor que 1 redefine esta opção para seu valor padrão. A cópia em massa impõe um máximo de 65.535 erros. Uma tentativa de definir esta opção como um valor maior que 65.535 resulta na definição da opção como 65.535.|  
|BCP_OPTION_ROWCOUNT|Retorna o número de linhas afetadas pela operação BCP atual (ou última).|  
|BCP_OPTION_TEXTFILE|O arquivo de dados não é um arquivo binário, mas um arquivo de texto. O BCP detecta se o arquivo de texto é Unicode ou não verificando o marcador do byte Unicode nos primeiros 2 bytes do arquivo de dados.|  
|BCP_OPTION_UNICODEFILE|Quando definida como TRUE, essa opção especifica que o arquivo de entrada está no formato de arquivo Unicode.|  
  
## <a name="arguments"></a>Argumentos  
 *eOption*[in]  
 Defina como uma das opções listadas na seção de comentários, acima.  
  
 *iValue*[in]  
 O valor para o *eOption*especificado. O argumento *iValue* é um valor inteiro convertido para um ponteiro void para permitir a expansão futura para valores de 64 bits.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 S_OK  
 O método foi bem-sucedido.  
  
 E_FAIL  
 Ocorreu um erro específico do provedor; Para obter informações detalhadas, use o [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.  
  
 E_UNEXPECTED  
 A chamada para o método era inesperada. Por exemplo, o [ibcpsession:: BCPInit](ibcpsession-bcpinit-ole-db.md) método não foi chamado antes de chamar essa função.  
  
 E_OUTOFMEMORY  
 Erro de memória insuficiente.  
  
## <a name="see-also"></a>Consulte também  
 [IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md)   
 [Executando operações de cópia em massa](../native-client/features/performing-bulk-copy-operations.md)  
  
  
