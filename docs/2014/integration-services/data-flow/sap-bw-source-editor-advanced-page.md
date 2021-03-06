---
title: Editor de Origem SAP BW (página Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 44f3c991-9e8f-4126-a9a2-2d9da779fb11
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: e227f0a3c19385f8b6eaedd747dbe63895b19298
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37203996"
---
# <a name="sap-bw-source-editor-advanced-page"></a>Editor de Origem de SAP BW (página Avançado)
  Use a página **Avançado** do **Editor de Fonte SAP BW** para especificar a regra de conversão de cadeia de caracteres e o período de tempo limite, e também para redefinir o status de uma ID de Solicitação específica.  
  
 Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).  
  
> [!IMPORTANT]  
>  A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW. Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.  
  
> [!IMPORTANT]  
>  A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional. Verifique esses requisitos com a SAP.  
  
 **Para abrir a página Gerenciador de Conexões**  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.  
  
2.  Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.  
  
3.  No **Editor de Origem SAP BW**, clique em **Avançado** para abrir a página **Avançada** do editor.  
  
## <a name="options"></a>Opções  
  
> [!NOTE]  
>  Se você não souber todos os valores necessários para configurar a origem, talvez precise perguntar ao administrador do SAP.  
  
 **Conversão da cadeia de caracteres**  
 Especifique a regra para aplicar à conversão de cadeia de caracteres.  
  
|Opção|Description|  
|------------|-----------------|  
|**Conversão automática de cadeia de caracteres**|Converter todas as cadeias de caracteres para `nvarchar` quando o sistema SAP Netweaver BW é um sistema Unicode. Caso contrário, converta todas as cadeias de caracteres para `varchar`.|  
|**Converter cadeias de caracteres em varchar**|Converta todas as cadeias de caracteres para `varchar`.|  
|**Converter cadeias de caracteres em nvarchar**|Converta todas as cadeias de caracteres para `nvarchar`.|  
  
 **Tempo Limite (segundos)**  
 Especifique o número máximo de segundos que a origem deve esperar.  
  
> [!NOTE]  
>  Esta opção só será válida se você tiver selecionado **A – Aguardar Notificação** como o valor de **Modo de Execução** na página do **Gerenciador de Conexões** do editor. Para obter mais informações, consulte [SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md).  
  
 **Request ID**  
 Especifique a ID da Solicitação cujo status você quer redefinir para “V – Verde” quando clicar em **Redefinir**.  
  
 **Redefinir**  
 Permite redefinir o status da ID da solicitação para “V - Verde”, depois de ter solicitado a sua confirmação. Isso pode ser útil quando um problema tiver ocorrido e o sistema SAP Netweaver BW tiver marcado a solicitação com um status amarelo ou vermelho.  
  
## <a name="see-also"></a>Consulte também  
 [Editor de origem SAP BW &#40;página do Gerenciador de Conexão&#41;](sap-bw-source-editor-connection-manager-page.md)   
 [Editor de origem SAP BW &#40;página de colunas&#41;](sap-bw-source-editor-columns-page.md)   
 [Editor de Origem SAP BW &#40;Página Saída de Erro&#41;](sap-bw-source-editor-error-output-page.md)   
 [Ajuda F1 do Microsoft Connector 1.1 para SAP BW](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
