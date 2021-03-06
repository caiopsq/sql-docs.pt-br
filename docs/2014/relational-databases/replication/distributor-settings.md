---
title: Configurações de distribuidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
caps.latest.revision: 9
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: bee6eb86ae33552b3ee15edd161aa948651a7d8f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37305466"
---
# <a name="distributor-settings"></a>Configurações de distribuidor
  A caixa de diálogo **Configurações do Distribuidor** permite alterar configurações para Distribuidores que foram adicionados ao painel esquerdo no Replication Monitor.  
  
## <a name="options"></a>Opções  
 **Conectar automaticamente quando o Replication Monitor for iniciado**  
 Selecione para permitir que o Monitor de Replicação conecte-se ao Distribuidor e recupere informações de status.  
  
 **Conexão**  
 Clique para exibir a caixa de diálogo **Conectar ao Servidor** . Isso permite que você visualize e altere as credenciais e propriedades de conexão que o Replication Monitor usa para se conectar ao Distribuidor.  
  
 **Atualizar automaticamente o status deste Distribuidor e de suas publicações**  
 Selecione para permitir que o Monitor de Replicação atualize automaticamente o status para o Distribuidor. Se essa opção for selecionada, o Replication Monitor pesquisará no Distribuidor informações de status com base no intervalo de sondagem pela opção **Taxa de atualização** . Para obter mais informações sobre atualização no Replication Monitor, consulte [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).  
  
 **Taxa de atualização**  
 Insira um valor (em segundos) para especificar a frequência de sondagem do Replication Monitor no Distribuidor, por status. Valores inferiores resultam em sondagem mais frequente. Isto poderá afetar o desempenho no Distribuidor se você estiver monitorando muitos Publicadores. Recomendamos que você teste seu sistema para determinar um valor apropriado. A configuração da **Taxa de Atualização** será também usada se você selecionar **Atualização Automática** em qualquer uma das janelas de detalhes no Replication Monitor.  
  
 **Mostre para todos os Publicadores deste Distribuidor no grupo a seguir**  
 Selecione um grupo de Publicadores na lista. O Publicador é exibido nesse grupo no painel esquerdo. Grupos fornecem uma forma de organizar Publicadores e não afetam a maneira como a replicação funciona.  
  
 **Novo grupo**  
 Clique para criar um novo grupo de Publicadores. Um grupo de Publicadores é um modo conveniente de organizar Publicadores no Replication Monitor. Grupos não afetam a replicação de dados ou a relação entre servidores em uma topologia de replicação.  
  
## <a name="see-also"></a>Consulte também  
 [Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md)   
 [Monitorando a Replicação](monitoring-replication.md)  
  
  
