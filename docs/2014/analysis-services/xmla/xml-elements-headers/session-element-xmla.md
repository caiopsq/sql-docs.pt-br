---
title: Elemento Session (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- Session Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- microsoft.xml.analysis.session
- http://schemas.microsoft.com/analysisservices/2003/engine#Session
- urn:schemas-microsoft-com:xml-analysis#Session
helpviewer_keywords:
- Session element
ms.assetid: 884ed090-968e-41d3-97e5-6d12787467da
caps.latest.revision: 15
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 74ce499ba167c7c0d439fba4e4099638f4e98db6
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37310363"
---
# <a name="session-element-xmla"></a>Elemento Session (XMLA)
  Usa o cabeçalho SOAP em uma mensagem de solicitação SOAP para identificar uma sessão existente explícita em uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
   <soap:Header>  
      ...  
      <Session  
         xmlns="urn:schemas-microsoft-com:xml-analysis"  
         SessionId="string" />  
      ...  
   </soap:Header>  
   <soap:Body>  
      ...  
   </soap:Body>  
</soap:Envelope>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|Nenhum|  
|Elementos filho|Nenhum|  
  
## <a name="attributes"></a>Atributos  
  
|attribute|Description|  
|---------------|-----------------|  
|SessionId|Atributo obrigatório `String` que identifica a sessão a ser usada. O [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] usa um GUID (identificador global exclusivo) para identificar uma sessão.|  
  
## <a name="remarks"></a>Remarks  
 O elemento do cabeçalho `Session` identifica uma sessão existente explicitamente iniciada na instância [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]. O elemento `Session` faz parte do cabeçalho SOAP nos seguintes tipos de mensagens:  
  
-   Uma resposta SOAP que contém um [BeginSession](session-element-xmla.md) elemento de cabeçalho SOAP.  
  
-   Uma solicitação SOAP para identificar a sessão na qual executar o [Discover](../xml-elements-methods-discover.md) ou [Execute](../xml-elements-methods-execute.md) método.  
  
 Um identificador de sessão não garante que uma sessão permaneça válida. A sessão especificada no elemento `Session` pode expirar. Por exemplo, uma sessão pode expirar se o tempo da sessão atingir seu limite ou se a conexão associada à sessão for interrompida. Se a sessão expirar e não for mais válida, o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] finalizará a sessão e reverterá as transações que estiverem em andamento naquele momento. Qualquer mensagem SOAP que for enviada com um identificador de sessão inválido falhará, indicando que a sessão especificada não pode ser encontrada.  
  
 Se um elemento `Session` não for enviado como parte de uma solicitação SOAP, a instância [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] dará início a uma sessão, de maneira implícita, durante a chamada do método `Discover` ou `Execute` e finalizará essa sessão assim que a chamada do método for concluída.  
  
## <a name="see-also"></a>Consulte também  
 [Elemento EndSession &#40;XMLA&#41;](endsession-element-xmla.md)   
 [Gerenciando conexões e sessões &#40;XMLA&#41;](../../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md)   
 [Cabeçalhos &#40;XMLA&#41;](xml-elements-headers.md)  
  
  
