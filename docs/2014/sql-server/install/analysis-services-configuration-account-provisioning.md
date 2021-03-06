---
title: Analysis Services - configuração de provisionamento de conta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services configuration
- account provisioning
ms.assetid: 169b1af2-6fe2-467f-8ca4-919f24c620ce
caps.latest.revision: 28
author: heidisteen
ms.author: heidist
manager: craigg
ms.openlocfilehash: f3ab054dad44d7e7c6f43604f21ec771279eb050
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37151887"
---
# <a name="analysis-services-configuration---account-provisioning"></a>Configuração do Analysis Services - Provisionamento de conta
  Use esta página para definir o modo de servidor e para conceder permissões administrativas a usuários ou serviços que requerem acesso irrestrito ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. A Instalação não adiciona automaticamente o Grupo local do Windows BUILTIN\Administradores à função de administrador de servidor [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] da instância que está sendo instalada. Para adicionar o grupo Administradores local à função de administrador do servidor, é necessário especificar explicitamente esse grupo.  
  
 Se você estiver instalando o [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], conceda permissões administrativas aos administradores de farms do SharePoint ou aos administradores de serviços responsáveis por uma implantação do servidor [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] em um farm do [!INCLUDE[SPS2010](../../includes/sps2010-md.md)]. Para obter mais informações sobre [!INCLUDE[ssGeminiMTS](../../includes/ssgeminimts-md.md)] instalação e requisitos de conta de serviço, consulte [instalar recursos de BI do SQL Server com o SharePoint &#40;PowerPivot e Reporting Services&#41;](../../../2014/sql-server/install/install-sql-server-bi-features-sharepoint-powerpivot-reporting-services.md).  
  
## <a name="options"></a>Opções  
 **Modo de servidor** - o modo de servidor especifica o tipo de bancos de dados do Analysis Services que podem ser implantados no servidor. Os modos de servidor são determinados durante a Instalação e não podem ser modificados posteriormente. Cada modo é mutuamente exclusivo, o que significa que você precisará de duas instâncias do Analysis Services, cada uma configurada para um modo diferente, para oferecer suporte às soluções de modelo OLAP e de tabela.  
  
 **Especificar Administradores** – Você deve especificar, pelo menos, um administrador de servidor para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Os usuários ou grupos que você especificar se tornarão membros da função de administrador de servidor da instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que está sendo instalada. Eles devem ser contas de usuário de domínio do Windows no mesmo domínio que o computador no qual você está instalando o software.  
  
> [!NOTE]  
>  O UAC (Controle de Conta de Usuário) é um recurso de segurança do Windows que requer um administrador para aprovar especificamente aplicativos ou ações administrativas para que tenham permissão de execução. Como o UAC é ativado por padrão, será solicitado que você permita operações específicas que exijam privilégios elevados. É possível configurar o UAC para alterar o comportamento padrão ou personalizar o UAC para programas específicos. Para obter mais informações sobre o UAC e sua configuração, consulte o [Guia Passo a Passo do Controle de Conta de Usuário](http://go.microsoft.com/fwlink/?linkid=196350) e [User Account Control (Wikipedia)](http://go.microsoft.com/fwlink/?linkid=196351).  
  
## <a name="see-also"></a>Consulte também  
 [Configurar contas de serviço &#40;Analysis Services&#41;](../../../2014/analysis-services/instances/configure-service-accounts-analysis-services.md)   
 [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md)  
  
  
