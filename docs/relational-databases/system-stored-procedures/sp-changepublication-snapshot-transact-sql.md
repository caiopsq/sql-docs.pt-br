---
title: sp_changepublication_snapshot (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_changepublication_snapshot_TSQL
- sp_changepublication_snapshot
helpviewer_keywords:
- sp_changepublication_snapshot
ms.assetid: 518a4618-3592-4edc-8425-cbc33cdff891
caps.latest.revision: 23
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: d83772784d2d0c67d76087013c13621e5ca7c906
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32992833"
---
# <a name="spchangepublicationsnapshot-transact-sql"></a>sp_changepublication_snapshot (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Propriedades de alteração do Agente de Instantâneo para a publicação especificada. Esse procedimento armazenado é executado no Publicador, no banco de dados publicador.  
  
> [!IMPORTANT]  
>  Quando um Publicador é configurado com um Distribuidor remoto, os valores fornecidos para todos os parâmetros, inclusive *job_login* e *job_password*, são enviados ao Distribuidor como texto sem-formatação. Você deve criptografar a conexão entre o Publicador e seu Distribuidor remoto antes de executar esse procedimento armazenado. Para obter mais informações, veja [Habilitar conexões criptografadas no Mecanismo de Banco de Dados &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_changepublication_snapshot [ @publication= ] 'publication'  
    [ , [ @frequency_type= ] frequency_type ]  
    [ , [ @frequency_interval= ] frequency_interval ]  
    [ , [ @frequency_subday= ] frequency_subday ]  
    [ , [ @frequency_subday_interval= ] frequency_subday_interval ]  
    [ , [ @frequency_relative_interval= ] frequency_relative_interval ]  
    [ , [ @frequency_recurrence_factor= ] frequency_recurrence_factor ]  
    [ , [ @active_start_date= ] active_start_date ]  
    [ , [ @active_end_date= ] active_end_date ]  
    [ , [ @active_start_time_of_day= ] active_start_time_of_day ]  
    [ , [ @active_end_time_of_day= ] active_end_time_of_day ]  
    [ , [ @snapshot_job_name = ] 'snapshot_agent_name' ]  
    [ , [ @publisher_security_mode = ] publisher_security_mode ]  
    [ , [ @publisher_login = ] 'publisher_login' ]  
    [ , [ @publisher_password = ] 'publisher_password' ]   
    [ , [ @job_login = ] 'job_login' ]  
    [ , [ @job_password = ] 'job_password' ]  
    [ , [ @publisher = ] 'publisher' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@publication =**] **'***publicação***'**  
 É o nome da publicação. *publicação* é **sysname**, sem padrão.  
  
 [  **@frequency_type =**] *frequency_type*  
 É a frequência de agendamento do agente. *frequency_type* é **int**, e pode ser um dos valores a seguir.  
  
|Value|Descrição|  
|-----------|-----------------|  
|**1**|Uma vez|  
|**2**|Sob Demanda|  
|**4**|Diariamente|  
|**8**|Semanalmente|  
|**16**|Mensalmente|  
|**32**|Relativo ao mês|  
|**64**|Iniciar automaticamente|  
|**128**|Recorrente|  
|NULL (padrão)||  
  
 [  **@frequency_interval =**] *frequency_interval*  
 Especifica os dias em que o agente é executado. *frequency_interval* é **int**, e pode ser um dos valores a seguir.  
  
|Value|Descrição|  
|-----------|-----------------|  
|**1**|Domingo|  
|**2**|Segunda-feira|  
|**3**|Terça-feira|  
|**4**|Quarta-feira|  
|**5**|Quinta-feira|  
|**6**|Sexta-feira|  
|**7**|Sábado|  
|**8**|Day|  
|**9**|Dias da semana|  
|**10**|Dias de fim de semana|  
|NULL (padrão)||  
  
 [  **@frequency_subday =**] *frequency_subday*  
 É a unidade do *freq_subday_interval*. *frequency_subday* é **int**, e pode ser um destes valores.  
  
|Value|Descrição|  
|-----------|-----------------|  
|**1**|Uma vez|  
|**2**|Segundo|  
|**4**|Minuto|  
|**8**|Hora|  
|NULL (padrão)||  
  
 [  **@frequency_subday_interval =**] *frequency_subday_interval*  
 É o intervalo de *frequency_subday*. *frequency_subday_interval* é **int**, com um padrão NULL.  
  
 [  **@frequency_relative_interval =**] *frequency_relative_interval*  
 É a data de execução do Agente de Instantâneo. *frequency_relative_interval* é **int**, com um padrão NULL.  
  
 [  **@frequency_recurrence_factor =**] *frequency_recurrence_factor*  
 É o fator de recorrência usado por *frequency_type*. *frequency_recurrence_factor* é **int**, com um padrão NULL.  
  
 [  **@active_start_date =**] *active_start_date*  
 É a data do primeiro agendamento do Agente de Instantâneo, formatada como AAAAMMDD. *active_start_date* é **int**, com um padrão NULL.  
  
 [  **@active_end_date =**] *active_end_date*  
 É a data em que o Agente de Instantâneo para de ser agendado, formatada como AAAAMMDD. *active_end_date* é **int**, com um padrão NULL.  
  
 [  **@active_start_time_of_day =**] *active_start_time_of_day*  
 É a hora do dia do primeiro agendamento do Agente de Instantâneo, formatada como HHMMSS. *active_start_time_of_day* é **int**, com um padrão NULL.  
  
 [  **@active_end_time_of_day =**] *active_end_time_of_day*  
 É a hora do dia do último agendamento do Agente de Instantâneo, formatada como HHMMSS. *active_end_time_of_day* é **int**, com um padrão NULL.  
  
 [  **@snapshot_job_name =** ] **'***snapshot_agent_name***'**  
 É o nome de um trabalho existente do Agente de Instantâneo se um trabalho existente estiver sendo usado. *snapshot_agent_name* é **nvarchar (100)** com um valor padrão de NULL.  
  
 [  **@publisher_security_mode =** ] *publisher_security_mode*  
 É o modo de segurança usado pelo agente ao conectar-se ao Publicador. *publisher_security_mode* é **smallint**, com um padrão NULL. **0** especifica [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticação, e **1** Especifica autenticação do Windows. Um valor de **0** devem ser especificados para não -[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] editores.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
 [  **@publisher_login =** ] **'***publisher_login***'**  
 É o logon usado na conexão com o Publicador. *publisher_login* é **sysname**, com um padrão NULL. *publisher_login* deve ser especificado quando *publisher_security_mode* é **0**. Se *publisher_login* é NULL e *publisher_security_mode* é **1**, em seguida, a conta do Windows especificada na *job_login* é usado quando Conectando-se ao publicador.  
  
 [  **@publisher_password =** ] **'***publisher_password***'**  
 É a senha usada ao conectar-se ao Publicador. *publisher_password* é **sysname**, com um padrão NULL.  
  
> [!IMPORTANT]  
>  Não use uma senha em branco. Use uma senha forte. Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução. Se for necessário armazenar credenciais em um arquivo de script, você deverá proteger o arquivo para impedir acesso não autorizado.  
  
 [ **@job_login** =] **'***job_login***'**  
 É o logon da conta do Windows na qual o agente é executado. *job_login* é **nvarchar (257)**, com um padrão NULL. Essa conta do Windows sempre é usada para conexões de agente com o Distribuidor. Você deve fornecer esse parâmetro ao criar um novo trabalho do Agente de Instantâneo. Isso não pode ser alterado para um editor não [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 [  **@job_password =** ] **'***job_password***'**  
 É a senha da conta do Windows na qual o agente é executado. *job_password* é **sysname**, com um padrão NULL. Você deve fornecer esse parâmetro ao criar um novo trabalho do Agente de Instantâneo.  
  
> [!IMPORTANT]  
>  Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução. Se for necessário armazenar credenciais em um arquivo de script, você deverá proteger o arquivo para impedir acesso não autorizado.  
  
 [  **@publisher =** ] **'***publicador***'**  
 Especifica um publicador que não é do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. *publicador* é **sysname**, com um padrão NULL.  
  
> [!NOTE]  
>  *publicador* não deve ser usado durante a criação de um agente de instantâneo em um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_changepublication_snapshot** é usado em replicação de instantâneo, replicação transacional e replicação de mesclagem.  
  
## <a name="permissions"></a>Permissões  
 Somente membros do **sysadmin** função de servidor fixa ou **db_owner** pode executar a função de banco de dados fixa **sp_changepublication_snapshot**.  
  
## <a name="see-also"></a>Consulte também  
 [Exibir e modificar as propriedades da publicação](../../relational-databases/replication/publish/view-and-modify-publication-properties.md)   
 [Alterar propriedades da publicação e do artigo](../../relational-databases/replication/publish/change-publication-and-article-properties.md)   
 [sp_addpublication_snapshot &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
