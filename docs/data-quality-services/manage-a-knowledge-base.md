---
title: Gerenciar uma base de dados de conhecimento | Microsoft Docs
ms.custom: ''
ms.date: 06/04/2013
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.suite: sql
ms.technology:
- data-quality-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 27f306f4-d67c-47f5-b35c-4260cc5d36e3
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: a5f58d9c6192329e6cd3d6858cfd6cb2135acf3f
ms.sourcegitcommit: f16003fd1ca28b5e06d5700e730f681720006816
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35310855"
---
# <a name="manage-a-knowledge-base"></a>Gerenciar uma base de dados de conhecimento

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  Este tópico descreve como executar funções de gerenciamento em uma base de dados de conhecimento no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Você pode excluir uma base de dados de conhecimento, desbloqueá-la, descartar seu trabalho nela, renomeá-la e exibir suas propriedades.  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Prerequisites"></a> Pré-requisitos  
 Para gerenciar uma base de dados de conhecimento, ela já deve ter sido criada e publicada (caso outra pessoa a tenha criado) ou fechada (se você a criou).  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para abrir uma base de dados de conhecimento.  
  
##  <a name="Manage"></a> Gerenciar uma base de dados de conhecimento  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Executar o aplicativo Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir base de dados de conhecimento**.  
  
3.  Clique com o botão direito do mouse em uma base de dados de conhecimento na tabela de bases de dados de conhecimento.  
  
4.  No menu de contexto, você pode fazer o seguinte:  
  
    1.  **Abrir**: clique para abrir a base de dados de conhecimento na atividade selecionada do painel **Selecionar Atividade** .  
  
    2.  **Desbloquear**: você pode desbloquear a base de dados de conhecimento se você for o usuário que estava trabalhando nela em uma das etapas do gerenciamento de domínio, da descoberta de conhecimento e da atividade de política de correspondência, e a fechou. Se você descarregar a base de dados de conhecimento, outra pessoa poderá abri-la e trabalhar nela. Este comando não estará disponível se a base de dados de conhecimento não estiver no estado de uma atividade. Para obter mais informações, consulte [Open a Knowledge Base](../data-quality-services/open-a-knowledge-base.md).  
  
    3.  **Descartar trabalho**: clique quando a base de dados de conhecimento estiver em um estado que indique que ela está sendo usado no momento, conforme mostrado no campo Estado da tabela. Este comando não estará disponível se a base de dados de conhecimento não estiver no estado de uma atividade e se a base de dados de conhecimento estiver bloqueada. Para obter mais informações, consulte [Open a Knowledge Base](../data-quality-services/open-a-knowledge-base.md).  
  
    4.  **Renomear**: clique para tornar o campo Base de Dados de Conhecimento da tabela editável para a base de dados de conhecimento na qual você clicou o botão direito do mouse. Altere o nome e clique nessa base de dados de conhecimento e em outra no campo p0ara aceitar a alteração do nome.  
  
    5.  **Excluir**: clique para remover a base de dados de conhecimento do banco de dados DQS_MAIN no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].  
  
    6.  **Propriedades**: clique para exibir as propriedades do banco de dados em uma exibição somente leitura.  
  
        1.  **Base de Dados de Conhecimento de Origem**: a base de dados de conhecimento na qual este banco de dados se baseia. Isso é opcional.  
  
        2.  **Estado**: indicará se a base de dados de conhecimento está **Em Serviço** e se está em uma atividade de gerenciamento de conhecimento específica, conforme determinado quando ela foi fechada pela última vez. O estado pode ser **Em Serviço**, no qual a base de dados de conhecimento é aberta em uma sessão de gerenciamento de conhecimento, mas não em uma atividade específica, ou **Em Serviço** mais uma atividade de gerenciamento de conhecimento, na qual a base de dados de conhecimento é aberta em uma sessão de gerenciamento de conhecimento, e em uma atividade específica.  
  
        3.  **Está Bloqueado**: **Verdadeiro** se a base de dados de conhecimento foi bloqueada; **Falso** se a base de dados de conhecimento não foi bloqueada.  
  
        4.  **Contém conteúdo não publicado**: Verdadeiro se a base de dados de conhecimento contiver algum conteúdo que não foi salvo durante a publicação; caso contrário, será Falso.  
  
        5.  **Bloqueado por**: o nome do usuário que fechou a base de dados de conhecimento, bloqueando-a  
  
        6.  **Data do Bloqueio**: data em que o bloqueio foi feito  
  
        7.  **Criado por**: o nome do usuário que criou a base de dados de conhecimento, com a rede à qual ele pertence  
  
        8.  **Data de Criação**: data em que a criação foi realizada  
  
##  <a name="FollowUp"></a> Acompanhamento: após gerenciar uma base de dados de conhecimento  
 Depois que você gerenciar uma base de dados de conhecimento, a próxima etapa dependerá da ação executada na base de dados de conhecimento:  
  
-   Se você abriu a base de dados de conhecimento, continuará na atividade que selecionou.  
  
-   Se você a desbloqueou, ela estará disponível para outra pessoa abrir e trabalhar nela, no estado indicado.  
  
-   Se você descartou o trabalho nela, a base de dados de conhecimento estará disponível em seu último estado publicado.  
  
-   Se você a renomeou, precisará abrir a base de dados de conhecimento renomeada para trabalhar nela.  
  
-   Se você a excluiu, precisará selecionar outra base de dados de conhecimento para trabalhar ou criar uma nova.  
  
  
