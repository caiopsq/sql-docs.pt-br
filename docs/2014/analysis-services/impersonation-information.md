---
title: Informações sobre representação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 42319d60-ccd0-46b8-af0b-f0968c390d8a
caps.latest.revision: 9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 1a0f2b5914c31c3cacce4bfb8887ebde73e0d932
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37180997"
---
# <a name="impersonation-information"></a>Informações sobre representação
  Use a página **Informações sobre Representação** para especificar as credenciais que o Analysis Services usará para se conectar à fonte de dados.  
  
## <a name="options"></a>Opções  
 **Usar um nome de usuário específicos do Windows e senha**  
 Selecione esta opção para fazer com que o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use as credenciais de segurança de uma conta de usuário do Windows especificada. As credenciais especificadas são usadas para processamento, consultas ROLAP, associações fora de linha, cubos locais, modelos de mineração, partições remotas, objetos vinculados e sincronização do destino para a origem. No entanto, para instruções OPENQUERY de extensões DMX, essa opção é ignorada e as credenciais do usuário atual serão usadas.  
  
 **Nome de usuário**  
 Digite o domínio e o nome da conta de usuário a serem usados pelo objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selecionado. Use o seguinte formato:  
  
 *\<Nome de domínio >* **\\**  *\<nome da conta de usuário >*  
  
 Essa opção estará habilitada apenas se a opção **Usar um nome e uma senha específicos** estiver selecionada.  
  
 **Senha**  
 Digite a senha da conta de usuário a ser usada pelo objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selecionado.  
  
 Essa opção estará habilitada apenas se a opção **Usar um nome e uma senha específicos** estiver selecionada.  
  
 **Usar a conta de serviço**  
 Selecione esta opção para fazer o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usar as credenciais de segurança associadas ao serviço do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que gerencia o objeto. As credenciais da conta de serviço são usadas para processamento, consultas ROLAP, partições remotas, objetos vinculados e sincronização do destino para a origem. No entanto, para instruções OPENQUERY do Data Mining Extensions (DMX), cubos locais e modelos de mineração, as credenciais do usuário atual são usadas. Essa opção não tem suporte para associações fora de linha.  
  
 **Usar as credenciais do usuário atual**  
 Selecione esta opção para fazer com que o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use as credenciais de segurança do usuário atual para associações fora de linha, OPENQUERY DMX, cubos locais e modelos de mineração. A opção não tem suporte para processamento, consultas ROLAP, partições remotas, objetos vinculados e sincronização do destino para a origem.  
  
 **Herdar**  
 Selecione esta opção para usar o comportamento de representação, definido no nível de banco de dados que foi definido pelo administrador do servidor usando a propriedade `DataSourceImpersonation` do banco de dados.  
  
## <a name="see-also"></a>Consulte também  
 [Fontes de dados em modelos multidimensionais](multidimensional-models/data-sources-in-multidimensional-models.md)   
 [Fontes de dados com suporte no &#40;Multidimensional do SSAS&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
