---
title: Caixa de diálogo Adicionar Tabela (Designer de Banco de Dados) (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-visual-db
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65555
- vdt.dlgbox.schema.addtable
ms.assetid: 3c0b1b30-795c-4240-91d6-890b8348014a
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: b107ae77626980258c4802f0c036f364845bc705
ms.sourcegitcommit: c7a98ef59b3bc46245b8c3f5643fad85a082debe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2018
ms.locfileid: "38985628"
---
# <a name="add-table-dialog-box-database-designer-visual-database-tools"></a>Caixa de diálogo Adicionar Tabela (Designer de Banco de Dados) (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Permite adicionar tabelas no Designer de Banco de Dados.  
  
> [!NOTE]  
> Se a tabela for publicada para replicação, você precisará fazer alterações no esquema usando a instrução Transact-SQL [ALTER TABLE](http://msdn.microsoft.com/f1745145-182d-4301-a334-18f799d361d1) ou o SMO (SQL Server Management Objects). Ao fazer alterações no esquema com o Criador de Tabelas ou com o Criador do Diagrama de Banco de Dados, ele tenta descartar e recriar a tabela. Não é possível descartar objetos publicados, portanto, haverá falha na alteração de esquema.  
  
## <a name="uielement-list"></a>Lista de elementos de interface do usuário  
**Atualizar**  
Atualizou a lista de tabelas para que correspondesse ao estado atual do banco de dados.  
  
**Adicionar**  
Adiciona a tabela ou tabelas selecionadas.  
  
> [!NOTE]  
> Para adicionar várias tabelas ao diagrama, você pode selecionar todas elas antes de clicar em **Adicionar**. Se preferir, clique duas vezes em cada tabela que desejar adicionar e clicar em **Fechar** ao final.  
  
**Fechar**  
Fecha a caixa de diálogo sem adicionar mais tabelas.  
  
## <a name="see-also"></a>Consulte Também  
[Adicionar tabelas a diagramas &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/add-tables-to-diagrams-visual-database-tools.md)  
  
