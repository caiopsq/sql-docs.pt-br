---
title: Propriedades (guia ordem) de protocolos de cliente | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.suite: sql
ms.technology: configuration
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
caps.latest.revision: 18
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 394e659a17fb4a27deac8fd62c342aa11bdac72f
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37987468"
---
# <a name="client-protocols-properties-order-tab"></a>Propriedades de Protocolos de Cliente (guia Ordem)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  Use a página **Ordem** na caixa de diálogo **Propriedades de Protocolos de Cliente** para exibir e habilitar os protocolos de cliente.  
  
 Clique em um protocolo e, em seguida, em **Habilitar** ou **Desabilitar** para mover o protocolo selecionado para a lista **Protocolos Desabilitados** ou **Protocolos Habilitados** .  
  
 Os protocolos são testados na ordem listada, tentando conectar usando o primeiro protocolo da lista, depois o segundo protocolo e assim por diante. Mova protocolos para cima ou para baixo na lista **Protocolos Habilitados**, clicando nos botões de seta para cima e para baixo. Na conexão com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio de um cliente nesse computador, o protocolo **Memória Compartilhada** sempre será tentado primeiro, se habilitado.  
  
> [!NOTE]  
>  Essas configurações não são usadas pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient. A ordem dos protocolos para o .NET SqlClient é primeiro o TCP, e, em seguida, pipes nomeados que não podem ser alterados.  
  
## <a name="options"></a>Opções  
 **Protocolos Desabilitados**  
 Lista os protocolos que são instalados, mas não são usados no momento.  
  
 **Protocolos Habilitados**  
 Lista os protocolos que estão disponíveis para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clientes neste computador.  
  
 **>**  
 Habilita o protocolo realçado na caixa **Protocolos Desabilitados** , movendo-o para a caixa **Protocolos Habilitados** .  
  
 **\<**  
 Desabilita o protocolo realçado na caixa **Protocolos Habilitados** , movendo-o para a caixa **Protocolos Desabilitados** .  
  
 Seta para cima  
 Move o protocolo realçado para cima na lista. Isso permite aumentar a prioridade com que a Biblioteca de Rede tentará usar o protocolo selecionado para conexões.  
  
 Seta para baixo  
 Move o protocolo realçado para baixo na lista. Isso permite diminuir a prioridade com que a Biblioteca de Rede tentará usar o protocolo selecionado para conexões.  
  
 **Habilitar Protocolo de Memória Compartilhada**  
 Habilita o protocolo de memória compartilhada que sempre é tentado primeiro (se habilitado), ao conectar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio de um cliente nesse computador.  
  
> [!NOTE]  
>  Se o protocolo for especificado por meio de um prefixo ou como parte da cadeia de conexão, somente o protocolo especificado será tentado.  
  
## <a name="see-also"></a>Consulte Também  
 [Escolhendo um protocolo de rede](http://msdn.microsoft.com/library/6565fb7d-b076-4447-be90-e10d0dec359a)  
  
  
