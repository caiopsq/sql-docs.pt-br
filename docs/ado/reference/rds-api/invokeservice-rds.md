---
title: InvokeService (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- InvokeService [RDS]
ms.assetid: ad45c676-ec7e-4a3a-9a6b-a54f75eb3012
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 92927a240c0501196c1b9bf0c1643f6cb0f708d4
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35288285"
---
# <a name="invokeservice-rds"></a>InvokeService (RDS)
Retorna um ponteiro para a interface solicitada em uma versão maior capacidade do objeto.  
  
> [!IMPORTANT]
>  Começando com o Windows 8 e Windows Server 2012, os componentes de servidor RDS não estão mais incluídos no sistema operacional Windows (veja o Windows 8 e [manual de compatibilidade do Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) para obter mais detalhes). Componentes de cliente RDS serão removidos em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Aplicativos que usam o RDS devem migrar para [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
object.InvokeService(REFID riid, IUknown* punkNotSoFunctionalInterface, IUknown** ppunkMoreFunctionalInterface) As HRESULT  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *riid*  
  
 [in] O identificador da interface que está sendo solicitado.  
  
 *punkNotSoFunctionalInterface*  
  
 [in] O objeto de origem com menos recursos.  
  
 *ppunkMoreFunctionalInterface*  
  
 [out] O endereço da variável de ponteiro que recebe o ponteiro de interface solicitado na *riid*. No retorno bem-sucedido, o *ppunkMoreFunctionalInterface* parâmetro contém o ponteiro de interface solicitada para o objeto. Se o objeto não oferece suporte para a interface especificada em *riid*, *ppunkMoreFunctionalInterface* é definido como NULL.  
  
## <a name="return-value"></a>Valor retornado  
 Um valor HRESULT que indica se a chamada para o **InvokeService** método foi bem-sucedida.  
  
## <a name="remarks"></a>Remarks  
 A implementação do mecanismo de cursor RDS do **InvokeService** usa o conjunto de linhas de entrada (ou objeto de vários resultados), preenche o mecanismo de cursor do conjunto de linhas de entrada e, em seguida, retorna um ponteiro de si mesma.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Interface IRDSService (RDS)](../../../ado/reference/rds-api/irdsservice-interface-rds.md)  
  
## <a name="see-also"></a>Consulte também  
 [Métodos RDS](../../../ado/reference/rds-api/rds-methods.md)


