---
title: Classe SqlErrorLogEvent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SqlErrorLogEvent class
- SqlErrorLogFile class
ms.assetid: bde6c467-38d0-4766-a7af-d6c9d6302b07
caps.latest.revision: 12
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 65c2eb3758524788d0c65645d3b5736c930d58ac
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37204886"
---
# <a name="sqlerrorlogevent-class"></a>Classe SqlErrorLogEvent
  Fornece propriedades para exibir eventos em um arquivo de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
class SQLErrorLogEvent   
{  
   stringFileName;  
   stringInstanceName;  
   datetimeLogDate;  
   stringMessage;  
   stringProcessInfo;  
};  
```  
  
## <a name="properties"></a>Propriedades  
 A classe SQLErrorLogEvent define as propriedades a seguir.  
  
|||  
|-|-|  
|FileName|Tipo de dados: `string`<br /><br /> Tipo de acesso: Somente leitura<br /><br /> <br /><br /> O nome do arquivo do log de erros.|  
|InstanceName|Tipo de dados: `string`<br /><br /> Tipo de acesso: Somente leitura<br /><br /> Qualificadores: Chave<br /><br /> O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] onde o arquivo de log reside.|  
|LogDate|Tipo de dados: `datetime`<br /><br /> Tipo de acesso: Somente leitura<br /><br /> Qualificadores: Chave<br /><br /> <br /><br /> A data e a hora em que o evento foi gravado no arquivo de log.|  
|Mensagem|Tipo de dados: `string`<br /><br /> Tipo de acesso: Somente leitura<br /><br /> <br /><br /> A mensagem do evento.|  
|ProcessInfo|Tipo de dados: `string`<br /><br /> Tipo de acesso: Somente leitura<br /><br /> <br /><br /> Informações sobre a SPID (ID do processo do servidor de origem) do evento.|  
  
## <a name="remarks"></a>Remarks  
  
|||  
|-|-|  
|MOF|Sqlmgmproviderxpsp2up.mof|  
|DLL|Sqlmgmprovider.dll|  
|Namespace|\root\Microsoft\SqlServer\ComputerManagement10|  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como recuperar valores para todos os eventos registrados em um arquivo de log especificado. Para executar o exemplo, substitua \< *nome_instância*> com o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como 'Instance1' e substitua 'File_Name' pelo nome do arquivo de log de erros, como 'ERRORLOG.1.'.  
  
```  
on error resume next  
strComputer = "."  
Set objWMIService = GetObject("winmgmts:" _  
    & "{impersonationLevel=impersonate}!\\" _  
    & strComputer & "\root\MICROSOFT\SqlServer\ComputerManagement10")  
set logEvents = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogEvent WHERE InstanceName = '<Instance_Name>' AND FileName = 'File_Name'")  
  
For Each logEvent in logEvents  
WScript.Echo "Instance Name: " & logEvent.InstanceName & vbNewLine _  
    & "Log Date: " & logEvent.LogDate & vbNewLine _  
    & "Log File Name: " & logEvent.FileName & vbNewLine _  
    & "Process Info: " & logEvent.ProcessInfo & vbNewLine _  
    & "Message: " & logEvent.Message & vbNewLine _  
  
Next  
```  
  
## <a name="comments"></a>Comentários  
 Quando *nome_da_instância* ou *FileName* não são fornecidos na instrução WQL, a consulta retornará informações para a instância padrão e atual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo de log. Por exemplo, a instrução WQL a seguir retornará todos os eventos de log do arquivo de log atual (ERRORLOG) na instância padrão (MSSQLSERVER).  
  
```  
"SELECT * FROM SqlErrorLogEvent"  
```  
  
## <a name="security"></a>Segurança  
 Para se conectar a um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo de log por meio do WMI, você deve ter as seguintes permissões em ambos os computadores locais e remotos:  
  
-   Acesso de leitura para o **Root\Microsoft\SqlServer\ComputerManagement10** namespace WMI. Por padrão, todos usuários têm acesso de leitura por meio da permissão Habilitar Conta.  
  
-   Permissão de leitura para a pasta que contém os logs de erros. Por padrão, o erro logs estão localizados no caminho a seguir (onde \< *unidade >* representa a unidade onde você instalou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e \< *InstanceName*> é o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):  
  
     **\<Unidade >: \Program Files\Microsoft SQL Server\MSSQL12** **.\< InstanceName > \mssql\log.**  
  
 Se você se conectar através de um firewall, verifique se uma exceção está definida no firewall para WMI em computadores de destino remotos. Para obter mais informações, consulte [conectar-se ao WMI iniciando remotamente com o Windows Vista](http://go.microsoft.com/fwlink/?LinkId=178848).  
  
## <a name="see-also"></a>Consulte também  
 [Classe SqlErrorLogFile](sqlerrorlogfile-class.md)   
 [Exibir arquivos de log offline](../logs/view-offline-log-files.md)  
  
  
