---
title: Considerações administrativas sobre Publicadores Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], administrative considerations
- administering replication, Oracle publishing
ms.assetid: cfd81fb5-419b-4a1b-97c4-be7c9d4ee289
caps.latest.revision: 28
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7a58cbba3de8fa4ddab30180b644147f7ad33fd5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37177705"
---
# <a name="administrative-considerations-for-oracle-publishers"></a>Considerações administrativas sobre Oracle Publishers
  Após configurar um Editor Oracle e ativar os mecanismos de rastreamento de alterações de replicação, os administradores do sistema de banco de dados Oracle ainda podem usar os utilitários de banco de dados padrão Oracle e realizar tarefas típicas de administração de sistemas. Porém, você deve estar ciente quanto aos efeitos que a execução de certas tarefas administrativas pode ter nos dados publicados.  
  
 Com exceção de descartar ou modificar uma coluna publicada para replicação e descartar ou modificar qualquer objeto de replicação, essas considerações não se aplicam à publicação de instantâneos.  
  
## <a name="importing-and-loading-data"></a>Importando e carregando dados  
 Gatilhos são usados para rastrear alterações em publicações transacionais no Oracle. As alterações em tabelas publicadas podem ser replicadas para os Assinantes apenas se os gatilhos de replicação forem acionados quando ocorrer uma atualização, uma inserção ou uma exclusão. Os utilitários Oracle Import e SQL*Loader, da Oracle, têm opções que afetam o acionamento dos gatilhos quando linhas são inseridas em tabelas replicadas com esses utilitários.  
  
### <a name="oracle-import"></a>Oracle Import  
 Com o Oracle Import, é possível definir a opção **ignorar** para 's' ou 'n' (o padrão é 'n'). Se **ignorar** for definido como 'n', a tabela será descartada e recriada durante a importação. Isso remove os gatilhos de replicação e desabilita a replicação. Se **ignorar** for definido como 's', a importação tentará carregar as linhas na tabela existente, o que aciona os gatilhos de replicação. Portanto, certifique-se de que **ignorar** esteja definido como 's' ao importar para uma tabela replicada com a ferramenta de importação.  
  
### <a name="sqlloader"></a>SQL*Loader  
 Com o SQL\*Loader, você pode definir a opção **direto** como 'true' ou 'false' (o padrão é 'false'). Se **direcionar** estiver definido como 'falso', serão inseridas linhas usando instruções convencionais INSERT que acionam gatilhos de replicação. Se **direcionar** estiver definido como 'verdadeiro', a carga será otimizada e os gatilhos não serão acionados. Portanto, certifique-se de que **direcionar** esteja definido como 'falso' ao importar para uma tabela replicada com a ferramenta SQL*Loader.  
  
## <a name="making-changes-to-published-objects"></a>Fazendo alterações em objetos publicados  
 As seguintes ações não requerem nenhuma consideração especial:  
  
-   Reconstruir índices em tabelas publicadas.  
  
-   Adicionar gatilhos de usuário a uma tabela publicada.  
  
 A ação a seguir exige que você interrompa toda a atividade nas tabelas publicadas:  
  
-   Mover uma tabela publicada.  
  
 As ações a seguir exigem que você descarte a publicação, execute a operação e então recrie a publicação:  
  
-   Truncar uma tabela publicada.  
  
-   Renomear uma tabela publicada.  
  
-   Adicionar uma coluna a uma tabela publicada.  
  
-   Descartar ou modificar uma coluna que é publicada para replicação.  
  
-   Executar operações não registradas.  
  
## <a name="dropping-or-modifying-replication-objects"></a>Descartar ou modificar objetos de replicação  
 Você deve descartar e reconfigurar o Publicador se descartar ou modificar qualquer tabela de rastreamento de nível, sequência ou procedimento armazenado do Editor. Para obter uma lista parcial desses objetos, consulte [Objetos criados no Publicador Oracle](objects-created-on-the-oracle-publisher.md).  
  
 Para obter mais informações sobre como descartar e reconfigurar o Publicador, consulte a seção "Alterações que exigem reconfiguração do Publicador" no tópico [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).  
  
## <a name="see-also"></a>Consulte também  
 [Configurar um Publicador Oracle](configure-an-oracle-publisher.md)   
 [Considerações de design e limitações para Publicadores Oracle](design-considerations-and-limitations-for-oracle-publishers.md)   
 [Visão geral da publicação do Oracle](oracle-publishing-overview.md)  
  
  
