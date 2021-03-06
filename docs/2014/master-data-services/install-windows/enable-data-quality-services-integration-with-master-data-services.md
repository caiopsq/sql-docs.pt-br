---
title: Habilitar a integração do Data Quality Services com Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ab32938d-a80e-4106-80d4-94b2de3d67dc
caps.latest.revision: 4
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 276b17d6e62f9ba45a02d1e3e325a457ff6ee77c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37164817"
---
# <a name="enable-data-quality-services-integration-with-master-data-services"></a>Habilitar a integração do Data Quality Services com Master Data Services
  No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], a funcionalidade correspondente é fornecida pelo DQS (Data Quality Services). Essa funcionalidade deve ser habilitada para ser usada.  
  
## <a name="prerequisites"></a>Prerequisites  
  
-   Um aplicativo Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] e banco de dados devem existir.  
  
-   O recurso Data Quality Services e o Cliente Data Quality devem ser instalados na mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados do MDS. Para obter mais informações, consulte [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).  
  
### <a name="to-enable-data-quality-services-integration"></a>Para habilitar a integração do Data Quality Services  
  
1.  Abra o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].  
  
2.  No painel esquerdo, clique em **Configuração da Web**.  
  
3.  Na página **Configuração da Web** , selecione o site e o aplicativo Web.  
  
4.  Na seção **Habilitar Integração do DQS** , clique em **Habilitar integração com Data Quality Services**.  
  
5.  Na caixa de diálogo de confirmação, clique em **OK**.  
  
## <a name="see-also"></a>Consulte também  
 [Qualidade de dados correspondente no suplemento MDS para Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md)   
 [Suplemento do Master Data Services para Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md)   
 [Instalar o Master Data Services](install-master-data-services.md)  
  
  
