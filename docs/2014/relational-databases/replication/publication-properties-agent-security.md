---
title: Propriedades da publicação, segurança do agente | Microsoft Docs
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
- sql12.rep.newpubwizard.pubproperties.agentsecurity.f1
ms.assetid: 03945aac-66f2-4370-b5d1-c1de694bc4c1
caps.latest.revision: 20
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 6ffabfe5bdf652e5dec468b06c85591da555a2a7
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37186473"
---
# <a name="publication-properties-agent-security"></a>Propriedades de Publicação, Segurança do Agente
  A página **Segurança do Agente** da caixa de diálogo **Propriedades de Publicação** permite acessar as configurações das contas nas quais os seguintes agentes executam e fazem conexões com computadores em uma topologia de replicação:  
  
-   O Agente de Instantâneo para todas as publicações.  
  
-   O Agente de Leitor de Log para todas as publicações transacionais. Há um Agente de Leitor de Log para cada banco de dados publicado para replicação transacional. A alteração das configurações do Agente de Leitor de Log afeta todas as publicações transacionais em um banco de dados.  
  
-   O Agente de Leitor de Fila para publicações transacionais, que permite assinaturas de atualização enfileiradas. Há um Agente de Leitor de Fila para cada banco de dados de distribuição. A alteração das configurações do Agente de Leitor de Fila afeta todas as publicações transacionais com assinaturas de atualização em fila que usam o mesmo banco de dados de distribuição. Para obter mais informações sobre as configurações de segurança do Queue Reader Agent, consulte [Exibir e modificar configurações de segurança de replicação](security/view-and-modify-replication-security-settings.md).  
  
 Para obter mais informações sobre configurações de segurança e permissões exigidas para cada agente, consulte [Replication Agent Security Model](security/replication-agent-security-model.md).  
  
## <a name="options"></a>Opções  
 **Configurações de segurança** ou **Criar Agente**  
 Se um trabalho de agente tiver sido criado, clique em **Configurações de segurança** para acessar a caixa de diálogo que permite alterar as configurações de segurança de um agente. Se um trabalho de agente não tiver sido criado, clique em **Criar Agente** para criar um e especificar as configurações de segurança.  
  
## <a name="see-also"></a>Consulte também  
 [Create a Publication](publish/create-a-publication.md)   
 [Exibir e modificar as propriedades da publicação](publish/view-and-modify-publication-properties.md)   
 [Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md)   
 [Replication Security Best Practices](security/replication-security-best-practices.md)   
 [Segurança e proteção &#40;Replicação&#41;](security/security-and-protection-replication.md)  
  
  
