---
title: Selecionar tabelas de origem e exibições (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.selectsourcetablesandviews.f1
ms.assetid: f60e1a19-2ea6-403c-89ab-3e60ac533ea0
caps.latest.revision: 47
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 863ec1ff07440dcab80cd46b5179e3f042d9dadd
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37149897"
---
# <a name="select-source-tables-and-views-sql-server-import-and-export-wizard"></a>Selecionar tabelas de origem e exibições (Assistente de Importação e Exportação do SQL Server)
  Use o **selecionar tabelas de origem e exibições** página para especificar as tabelas e exibições a serem copiados da fonte de dados para o destino.  
  
> [!NOTE]  
>  Não é necessário copiar todas as colunas em uma tabela ao selecionar a opção Cópia de Tabela. Depois de selecionar uma tabela de destino, clique em Editar mapeamentos para exibir o **mapeamentos de coluna** caixa de diálogo. Selecione  **\<ignorar >** no **destino** coluna do **mapeamentos de coluna** caixa de diálogo para colunas que você deseja ignorar.  
  
 Para saber mais sobre este assistente, consulte [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md). Para saber mais sobre as opções para iniciar o assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o Assistente de exportação e importação do SQL Server](start-the-sql-server-import-and-export-wizard.md).  
  
 O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino. O assistente também pode criar um banco de dados de destino e tabelas de destino para você. No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados. Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).  
  
## <a name="options"></a>Opções  
  
### <a name="tables-and-views-list"></a>Lista de tabelas e exibições  
 **Origem**  
 Usando as caixas de seleção, selecione da lista de tabelas e exibições disponíveis para copiar para o destino. Se uma tabela ou exibição de origem foi selecionada e nenhuma outra ação foi efetuada, o esquema e os dados da origem serão copiados sem qualquer alteração.  
  
 **Destino**  
 Selecione uma tabela de destino da lista para cada tabela de origem.  
  
> [!NOTE]  
>  Se você pausar neste ponto do Assistente para criar uma tabela de destino no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou outra ferramenta, a nova tabela não está imediatamente visível na lista de tabelas de destino disponíveis. Para atualizar a lista de tabelas de destino, volte duas páginas para o **escolher um destino** página, selecione novamente o banco de dados de destino e, em seguida, passo à frente novamente até a **selecionar tabelas de origem e exibições**.  
  
### <a name="other-options"></a>Outras opções  
 **Editar mapeamentos**  
 Use o **mapeamentos de coluna** caixa de diálogo para especificar colunas de destino para receber os dados de origem. Você pode copiar apenas um subconjunto de colunas selecionando \<ignorar > na **destino** coluna do **mapeamentos de coluna** caixa de diálogo para colunas que você deseja ignorar.  
  
 **Visualização**  
 Visualizar dados de origem na **visualizar dados** caixa de diálogo para verificá-lo antes de executar a importação ou exportação. O **visualizar dados** caixa de diálogo exibe até 200 linhas de dados.  
  
 Após visualizar os dados, é possível alterar as opções selecionadas para a origem e destino de dados. Para fazer essas alterações, na página **Selecionar Tabelas e Exibições de Origem**, clique em **Voltar** para retornar às páginas anteriores nas quais é possível alterar as seleções.  
  
  
