---
title: Programa de administração | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- administration program [ODBC]
- ODBC administrator [ODBC]
ms.assetid: a6c8248a-7a01-42e7-aaed-99dc94d50028
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8d4fec680351c4b3abdc91defe726a498dd23a3f
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32915851"
---
# <a name="administration-program"></a>Programa de administração
> [!NOTE]  
>  Começando com o Windows XP e Windows Server 2003, o ODBC está incluído no sistema operacional Windows. Instale somente explicitamente ODBC em versões anteriores do Windows.  
  
 Um programa de administração, o administrador de ODBC é incluído com o SDK do Windows SDK/MDAC. Esse programa e pode ser redistribuído por usuários do SDK. Além disso, os desenvolvedores podem gravar seus próprios programas de administração. Em geral, os desenvolvedores escrevem seus próprios programas administração somente se eles desejam manter controle completo sobre a configuração da fonte de dados, ou se eles são configurar fontes de dados diretamente de um aplicativo que está atuando como um programa de administração. Por exemplo, um programa de planilha pode permitir aos usuários adicionar e, em seguida, usar fontes de dados em tempo de execução.  
  
 O programa de administração para o instalador DLL carregado pela primeira vez. Depois, ele chama funções no instalador do DLL para executar as seguintes tarefas:  
  
-   **Adicionar, modificar ou excluir fontes de dados interativamente.** O programa de administração pode chamar **SQLManageDataSources**, **SQLCreateDataSource**, ou **SQLConfigDataSource**.  
  
     **SQLManageDataSources** exibe uma caixa de diálogo com a qual o usuário pode adicionar, modificar ou excluir fontes de dados e especificar opções de rastreamento; essa função é chamada quando o instalador DLL é invocado diretamente no painel de controle. **SQLCreateDataSource** exibe uma caixa de diálogo com a qual o usuário só pode adicionar fontes de dados. **SQLConfigDataSource** passará a chamada diretamente para a DLL de instalação do driver.  
  
     Em todos os casos, o instalador DLL chama **ConfigDSN** na configuração do driver DLL, na verdade, adicionar, modificar ou excluir a fonte de dados. A DLL de instalação do driver pode solicitar ao usuário para obter informações adicionais.  
  
-   **Adicionar, modificar ou excluir fontes de dados silenciosamente.** O programa chamar administração **SQLConfigDataSource** na DLL do instalador e passa-uma janela nula manipular, o nome de uma fonte de dados para adicionar, modificar ou excluir e uma lista de valores para o registro. As chamadas DLL do instalador **ConfigDSN** na configuração do driver DLL, na verdade, adicionar, modificar ou excluir a fonte de dados.  
  
-   **Adicionar, modificar ou excluir uma fonte de dados padrão.** A fonte de dados padrão é o mesmo que qualquer outra fonte de dados, exceto que o seu nome é o padrão. Ele é adicionado, modificado ou excluído da mesma maneira como qualquer outra fonte de dados.
