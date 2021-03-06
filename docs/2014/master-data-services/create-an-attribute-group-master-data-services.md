---
title: Criar um grupo de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: bd50daa9250f46f17feecb7dfdd16e4998ea47d4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37290852"
---
# <a name="create-an-attribute-group-master-data-services"></a>Criar um grupo de atributo (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie grupos de atributos quando você desejar exibir atributos em guias individuais na grade do **Gerenciador** .  
  
> [!NOTE]  
>  Quando você criar um grupo de atributos, ele será ocultado automaticamente de todos os usuários, exceto daquele que o criou. Para obter mais informações sobre como tornar o grupo visível, consulte [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).  
  
## <a name="prerequisites"></a>Prerequisites  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Administração do Sistema** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).  
  
-   Pelo menos um atributo deve existir. Para obter mais informações, consulte [Criar um atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).  
  
### <a name="to-create-an-attribute-group"></a>Para criar um grupo de atributo  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.  
  
2.  Sobre o **exibição de modelo** página, na barra de menus, aponte para **gerenciar** e clique em **grupos de atributos**.  
  
3.  Na lista **Modelo** , selecione um modelo.  
  
4.  Na lista **Entidade** , selecione uma entidade.  
  
5.  Clique em **Grupos de Folha**, **Grupos Consolidados**ou **Grupos de Coleção** para criar um grupo de atributos de membros folha, membros consolidados ou coleções, respectivamente.  
  
6.  Clique em **adicionar grupo de atributos**.  
  
7.  No **nome do grupo folha** , digite um nome para o grupo. Esse é o nome exibido na guia **Explorer**.  
  
    > [!NOTE]  
    >  Se você selecionou **grupos consolidados** ou **grupos de coleção** na etapa 5, essa caixa está **nome do grupo consolidado** ou **nomedogrupodecoleção**, respectivamente.  
  
8.  Clique em **Salvar grupo**.  
  
9. Expanda a pasta para o grupo.  
  
10. Clique em **Atributos**.  
  
11. Clique em **Editar item selecionado**.  
  
12. Clique nos atributos na **disponível** caixa e clique no **Add** seta. Para adicionar tudo, clique na seta **Adicionar Tudo** .  
  
13. Opcionalmente, clique no **para cima** e **para baixo** setas para alterar a ordem da esquerda para a direita dos atributos.  
  
14. Clique em **Salvar**.  
  
## <a name="next-steps"></a>Próximas etapas  
  
-   [Tornar um grupo de atributos visível para usuários &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a>Consulte também  
 [Grupos de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md)   
 [Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md)   
 [Alterar o nome de um grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)   
 [Excluir um grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)   
 [Permissões de folha &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md)   
 [Consolidados permissões &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
