---
title: Agente de Leitor de Fila de Replicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], Queue Reader Agent
- command prompt [SQL Server replication]
- Queue Reader Agent, parameter reference
- Queue Reader Agent, executables
ms.assetid: 8e227793-11f6-47c6-99dc-ffc282f5d4bf
caps.latest.revision: 35
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: e4d77806809ce3b7306d9f7560b126ff32980ca2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37309546"
---
# <a name="replication-queue-reader-agent"></a>Agente de Leitor de Fila de Replicação
  O Replication Queue Reader Agent é um executável que lê mensagens armazenadas em uma fila do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue e aplica essas mensagens no Publicador. O Queue Reader Agent é usado com publicações de instantâneo e transacionais que permitem atualização em fila.  
  
> [!NOTE]  
>  Os parâmetros podem ser especificados em qualquer ordem. Quando não são especificados parâmetros opcionais, são usados valores predefinidos com base no perfil de agente padrão.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
      qrdrsvc [-?]  
[-Continuous]  
[-DefinitionFiledefinition_file]  
[-Distributorserver_name[\instance_name]]  
[-DistributionDBdistribution_database]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-HistoryVerboseLevel [0|1|2|3]]  
[-LoginTimeOutlogin_time_out_seconds]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2]]  
[-PollingIntervalpolling_interval]  
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-ProfileNameagent_profile_name]  
[-QueryTimeOutquery_time_out_seconds]  
[-ResolverState [1|2|3]]  
```  
  
## <a name="arguments"></a>Argumentos  
 **-?**  
 Exibe informações de uso.  
  
 **-Continuous**  
 Especifica se o agente tenta processar transações em fila continuamente. Se especificado, o agente continua a execução, mesmo que não haja transações na fila pendentes de nenhum dos assinantes.  
  
 **-DefinitionFile** *def_path_and_file_name*  
 É o caminho do arquivo de definição de agente. Um arquivo de definição de agente contém argumentos de linha de comando para o agente. O conteúdo do arquivo é analisado como um arquivo executável. Use aspas duplas (") para especificar valores de argumentos que contêm caracteres arbitrários.  
  
 **-Distributor** *server_name*[**\\***instance_name*]  
 É o nome do Distribuidor. Especifique *server_name* para a instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] naquele servidor. Especifique *server_name*\\*instance_name* para uma instância nomeada do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] naquele servidor. Se não for especificado, o nome assumirá o padrão do nome da instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no computador local.  
  
 **-DistributionDB** *distribution_database*  
 É o banco de dados de distribuição.  
  
 **-DistributorLogin** *distributor_login*  
 É o nome de logon do Distribuidor.  
  
 **-DistributorPassword** *distributor_password*  
 É a senha do Distribuidor.  
  
 **-DistributorSecurityMode** [ **0**| **1**]  
 Especifica o modo de segurança do Distribuidor. Um valor de **0** indica Modo (padrão) de Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e um valor de **1** indica Modo de Autenticação do Windows.  
  
 **-EncryptionLevel** [ **0** | **1** | **2** ]  
 É o nível da criptografia SSL (Secure Sockets Layer) usada pelo Queue Reader Agent ao fazer conexões.  
  
|Valor EncryptionLevel|Description|  
|---------------------------|-----------------|  
|**0**|Especifica que o SSL não é usado.|  
|**1**|Especifica que o SSL é usado, mas que +o agente não verifica se o certificado de servidor SSL é assinado por um emissor confiável.|  
|**2**|Especifica que o SSL é usado, e que o certificado é verificado.|  
  
 Para obter mais informações, consulte [Visão geral da segurança &#40;Replicação&#41;](../security/security-overview-replication.md).  
  
 **-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]  
 Especifica a quantidade de histórico registrada durante uma operação de leitura de fila. Você pode minimizar o efeito de registro de histórico no desempenho selecionando **1**.  
  
|Valor HistoryVerboseLevel|Description|  
|-------------------------------|-----------------|  
|**0**|Nenhum log de histórico (não recomendado).|  
|**1**|Padrão. Sempre atualiza uma mensagem de histórico anterior do mesmo status (inicialização, andamento, êxito, etc.). Se nenhum registro anterior com o mesmo status existir, insira um registro novo.|  
|**2**|Insira novos registros de histórico, incluindo mensagens ociosas ou mensagens de trabalho de execução longa.|  
|**3**|Insira novos registros de histórico que incluam detalhes adicionais que podem ser úteis na solução de problemas.|  
  
 **-LoginTimeOut** *segundos_de_tempo_limite_de_logon*  
 É o número de segundos antes que o logon expire. O padrão é 15 segundos.  
  
 **-Output** *caminho_de_saída_e_nome_do_arquivo*  
 É o caminho do arquivo de saída do agente. Se o nome de arquivo não for fornecido, a saída será enviada ao console. Se o nome do arquivo especificado existir, a saída será anexada ao arquivo.  
  
 **-OutputVerboseLevel** [ **0**| **1**| **2**]  
 Especifica se a saída deve ser detalhada. Se o nível detalhado for **0**, só mensagens de erro serão impressas. Se o nível detalhado for **1**, todas as mensagens de relatório de progresso serão impressas. Se o nível detalhado for **2** (padrão), todas as mensagens de erro e de relatório de progresso serão impressas, o que é útil na depuração.  
  
 **-PollingInterval** *intervalo_de_sondagem*  
 É relevante apenas para assinaturas de atualização que usam filas com base no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Especifica com que frequência, em segundos, a fila do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é sondada para transações em fila pendentes. O valor pode ser entre 0 e 240 segundos. O padrão é 5 segundos.  
  
 **-PublisherFailoverPartner** *server_name*[**\\***instance_name*]  
 Especifica a instância de parceiro de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que participa de uma sessão de espelhamento de banco de dados com o banco de dados de publicação. Para obter mais informações, consulte [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).  
  
 **-ProfileName** *nome_do_perfil_do_agente*  
 É o nome de um perfil de agente usado para fornecer um conjunto de valores padrão ao agente. Para obter mais informações, consulte [Perfis do agente de replicação](replication-agent-profiles.md).  
  
 **-QueryTimeOut** *tempo_limite_da_consulta_em_segundos*  
 É o número de segundos antes que a consulta expire. O padrão é 1800 segundos.  
  
 **-ResolverState** [ **1**| **2**| **3**]  
 Especifica como conflitos de atualização na fila são resolvidos. Um valor **1** indica que o Publicador ganha o conflito, a transação na fila conflitante será revertida no Publicador e no Assinante de atualização de origem e o processo de transações subsequentes em fila continuará. Um valor **2** indica que o Assinante ganha o conflito e a transação na fila substituirá os valores no Publicador. Um valor **3** indica que qualquer conflito resultará na reinicialização do Assinante; o Publicador ganha o conflito, o processamento de transações subsequentes na fila será interrompido e a assinatura será reiniciada. A configuração padrão é **1** para publicações transacionais e **3** para publicações de instantâneo.  
  
## <a name="remarks"></a>Remarks  
 Para iniciar o Queue Reader Agent, execute **qrdrsvc.exe** no prompt de comando. Para obter informações, consulte [Executáveis do agente de replicação](../concepts/replication-agent-executables-concepts.md).  
  
## <a name="see-also"></a>Consulte também  
 [Administração do agente de replicação](replication-agent-administration.md)  
  
  
