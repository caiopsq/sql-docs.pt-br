---
title: srv_message_handler (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: extended-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- srv_message_handler
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
caps.latest.revision: 31
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: cc13ba63ed8cce3d4a789397c10d3b9062009e7e
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="srvmessagehandler-extended-stored-procedure-api"></a>srv_message_handler (API de procedimento armazenado estendido)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Em vez disso, use a Integração CLR.  
  
 Chama o manipulador de mensagens instalado da API de procedimento armazenado estendido. Em geral, essa função é usada para chamar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de um procedimento armazenado estendido para registrar um erro (definido pelo procedimento armazenado estendido) no arquivo de log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou no log de aplicativos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica. O parâmetro *srvproc* contém informações usadas para gerenciar a comunicação e os dados entre o aplicativo e o cliente.  
  
 *errornum*  
 É um número de erro definido pelo procedimento armazenado estendido. Esse número deve ser de 50.001 a 2.147.483.647.  
  
 *severity*  
 É um valor de severidade padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o erro. Esse número deve ser de 0 por 24.  
  
 *state*  
 É um valor de estado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o erro.  
  
 *oserrnum*  
 É o número de erro do sistema operacional. Este argumento é ignorado.  
  
 *errtext*  
 É a descrição do erro *errornum* do procedimento armazenado estendido.  
  
 *errtextlen*  
 É o tamanho da cadeia de caracteres de erro *errtext* do procedimento armazenado estendido.  
  
 *oserrtext*  
 É a descrição do erro *oserrnum* do sistema operacional. Este argumento é ignorado.  
  
 *oserrtextlen*  
 É o tamanho da cadeia de caracteres de erro *oserrtext* do sistema operacional.  
  
## <a name="returns"></a>Retorna  
 SUCCEED ou FAIL.  
  
## <a name="remarks"></a>Remarks  
 A função **srv_message_handler** permite que um procedimento armazenado estendido seja integrado aos recursos de log de erros centralizado e relatório do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Os alertas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser estabelecidos para eventos de procedimentos armazenados estendidos e o SQL Server Agent fará o monitoramento das condições desses alertas.  
  
 Se a mensagem de erro for mais longa, ela será truncada para 412 bytes.  
  
> [!IMPORTANT]  
>  Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção. Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  