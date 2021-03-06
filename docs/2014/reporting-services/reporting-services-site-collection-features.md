---
title: Recursos de coleção do Site do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: e05ae162-a4b2-489d-9853-d6b09414e632
caps.latest.revision: 5
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: eb321258a8dc87a499479d66ced85b95ce643b6d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37294116"
---
# <a name="reporting-services-site-collection-features"></a>Recursos da coleção de sites do Reporting Services
  O modo do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint fornece três recursos de coleção de sites do SharePoint. Os recursos de suportam geral [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reporting ambiente, de modo do SharePoint [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)], um recurso do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] suplemento para [!INCLUDE[SPS2010](../includes/sps2010-md.md)] Enterprise Edition e operações de gerenciamento para [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] em Administração Central do SharePoint.  
  
## <a name="site-collection-features"></a>Recursos da coleção de sites  
 A tabela a seguir descreve os membros da coleção de sites do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].  
  
|Recurso|Description|  
|-------------|-----------------|  
|**Recurso Administração Central do Servidor de Relatório**|Habilita recursos para o gerenciamento da integração com um servidor de relatório do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] . Esse recurso somente é instalado e usado na coleção de sites da Administração Central do SharePoint.<br /><br /> O recurso de integração do servidor de relatório é ativado automaticamente na coleção de sites de Administração Central do SharePoint depois de instalar o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] suplemento para produtos do SharePoint. Em algumas situações, você precisará ativar manualmente o recurso. Para ativar o recurso de servidor do relatório, use as páginas do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] na página Configurações de Site da Administração Central do SharePoint.<br /><br /> O [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] versão e posteriores do suplemento para SharePoint produtos ativarão o recurso de integração do servidor de relatório para todos os conjuntos de sites existentes quando o suplemento está instalado. Além disso, o recurso ficará ativo automaticamente para novas coleções de sites.|  
|**Recurso de Integração do Servidor de Relatório**|Habilita relatórios avançados usando [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<br /><br /> Esse recurso está Ativo por padrão.|  
|**Recurso de Integração do Power View**|Permite a exploração de dados interativa e a apresentação visual em pastas de trabalho PowerPivot e Análise conserta bancos de dados de tabela do Analysis Services.<br /><br /> O recurso pode ser acessado pelos menus de contexto das seguintes fontes de dados:<br /><br /> .rdlx<br /><br /> .rsds<br /><br /> arquivo de conexão .bism<br /><br /> <br /><br /> Se [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] não aparecer nos menus de contexto, verifique se o **Recurso de Integração do Power View** está ativado.<br /><br /> Esse recurso está desativado por padrão.|  
  
## <a name="see-also"></a>Consulte também  
 [Ativar o servidor de relatório e os recursos de integração do Power View no SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md)   
 [Relatórios de configurações de Site de serviços e recursos de Site&#40;modo do SharePoint&#41;](../../2014/reporting-services/reporting-services-site-settings-and-site-features-sharepoint-mode.md)   
 [Ativar o recurso de sincronização de relatório do Servidor de Relatório na Administração Central do SharePoint](../../2014/reporting-services/activate-report-server-file-sync-feature-sharepoint-central-administration.md)  
  
  
