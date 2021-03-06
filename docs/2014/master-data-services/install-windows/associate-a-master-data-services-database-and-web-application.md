---
title: Associar um banco de dados do Master Data Services a um aplicativo Web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ccb25672-f71d-4135-b548-f50eb45d8fa5
caps.latest.revision: 8
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 35b5f9712b73bfd26ad2214bd9c48ffc147c8431
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37298536"
---
# <a name="associate-a-master-data-services-database-and-web-application"></a>Associar um banco de dados do Master Data Services a um aplicativo Web
  Associe seu aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] a um banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] para especificar o banco de dados a ser usado em operações da Web.  
  
## <a name="prerequisites"></a>Prerequisites  
  
-   [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] deve estar instalado no computador local. Para obter mais informações, confira [Instalar o Master Data Services](install-master-data-services.md).  
  
-   Deve existir um aplicativo Web local do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]. Para obter mais informações, veja [Criar um aplicativo Web do Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).  
  
-   Deve existir um banco de dados local ou remoto do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]. Para obter mais informações, veja [Criar um banco de dados do Master Data Services](create-a-master-data-services-database.md).  
  
### <a name="to-associate-a-master-data-services-database-and-web-application"></a>Para associar um banco de dados do Master Data Services e um aplicativo Web  
  
1.  Abra o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].  
  
2.  No painel esquerdo, clique em **Configuração da Web**.  
  
3.  Na página **Configuração da Web** , em **Aplicativo Web**, na lista **Site** , selecione o site que contém seu aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .  
  
4.  Na caixa **Aplicativo Web** , selecione o aplicativo Web que hospeda o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].  
  
5.  Em **Aplicativo Associado com Banco de dados**, clique em **Selecionar**. A caixa de diálogo **Conectar ao Banco de Dados** é exibida.  
  
6.  Especifique informações de conexão para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] e clique em **Conectar**.  
  
7.  Na lista **Banco de dados do Master Data Services** , selecione o banco de dados a ser associado ao aplicativo Web e clique em **OK**.  
  
8.  Em **Associar Aplicativo ao Banco de Dados**, verifique se as informações de instância e banco de dados estão corretas e clique em **Aplicar**.  
  
## <a name="next-steps"></a>Próximas etapas  
  
-   O acesso programático a serviços Web do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] é habilitado automaticamente quando o aplicativo Web é criado. Para permitir que desenvolvedores acessem os metadados de serviço para gerar classes de proxy facilmente para o acesso programático, habilite a publicação de metadados. Para obter mais informações, veja [Criar classes proxy do serviço Web do Master Data Manager](../develop/create-master-data-manager-web-service-proxy-classes.md).  
  
-   Adicione usuários e grupos ao [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]. Se nenhum usuário ou grupo tiver recebido autorização de acesso ao [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], você deverá abrir o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] usando as credenciais de administrador do sistema [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md) e [Usuários e grupos &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).  
  
## <a name="see-also"></a>Consulte também  
 [Instalar o Master Data Services](install-master-data-services.md)   
 [Página Configuração da Web &#40;Gerenciador de Configuração do Master Data Services&#41;](../web-configuration-page-master-data-services-configuration-manager.md)  
  
  
