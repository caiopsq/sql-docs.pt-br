---
title: Mapeamento de tipo de dados em conjuntos de linhas e parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- mapping data types [OLE DB]
- DBTYPE_SQLVARIANT data type
- SQL Server Native Client OLE DB provider, data types
- rowsets [OLE DB], data type mapping
- data types [OLE DB]
- GetColumnInfo function
- parameters [OLE DB]
- SSPROP_ALLOWNATIVEVARIANT property
- GetParameterInfo function
- OLE DB, data types
ms.assetid: 3d831ff8-3b79-4698-b2c1-2b5dd2f8235c
caps.latest.revision: 40
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 77b7718febb0a6b8e8a8575ff776ffb44364b68a
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37422675"
---
# <a name="data-type-mapping-in-rowsets-and-parameters"></a>Mapeamento de tipos de dados em conjuntos de linhas e parâmetros
  Em conjuntos de linhas e como valores de parâmetro, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client representa [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] os dados usando o seguinte OLE DB definidos os tipos de dados, relatados nas funções **icolumnsinfo:: Getcolumninfo** e  **ICommandWithParameters:: Getparameterinfo**.  
  
|Tipo de dados do SQL Server|Tipo de dados OLE DB|  
|--------------------------|----------------------|  
|**bigint**|DBTYPE_I8|  
|**binary**|DBTYPE_BYTES|  
|**bit**|DBTYPE_BOOL|  
|**char**|DBTYPE_STR|  
|**datetime**|DBTYPE_DBTIMESTAMP|  
|**datetime2**|DBTYPE_DBTIME2|  
|**decimal**|DBTYPE_NUMERIC|  
|**float**|DBTYPE_R8|  
|**image**|DBTYPE_BYTES|  
|**int**|DBTYPE_I4|  
|**money**|DBTYPE_CY|  
|**nchar**|DBTYPE_WSTR|  
|**ntext**|DBTYPE_WSTR|  
|**numeric**|DBTYPE_NUMERIC|  
|**nvarchar**|DBTYPE_WSTR|  
|**real**|DBTYPE_R4|  
|**smalldatetime**|DBTYPE_DBTIMESTAMP|  
|**smallint**|DBTYPE_I2|  
|**smallmoney**|DBTYPE_CY|  
|**sql_variant**|DBTYPE_VARIANT, DBTYPE_SQLVARIANT|  
|**sysname**|DBTYPE_WSTR|  
|**text**|DBTYPE_STR|  
|**timestamp**|DBTYPE_BYTES|  
|**tinyint**|DBTYPE_UI1|  
|**UDT**|DBTYPE_UDT|  
|**uniqueidentifier**|DBTYPE_GUID|  
|**varbinary**|DBTYPE_BYTES|  
|**varchar**|DBTYPE_STR|  
|**XML**|DBTYPE_XML|  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client oferece suporte a conversões de dados solicitadas pelo consumidor conforme mostrado na ilustração.  
  
 O **sql_variant** objetos podem conter dados de qualquer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de tipo de dados, exceto o texto, ntext, imagem, varchar (max), nvarchar (max), varbinary (max), xml, timestamp e Microsoft .NET Framework common language runtime (CLR) tipos definidos pelo usuário. Uma instância de dados sql_variant também não pode ter sql_variant como seu tipo de dados base subjacente. Por exemplo, a coluna pode conter **smallint** valores para algumas linhas **float** valores para as outras linhas, e **char**/**nchar**valores no restante.  
  
> [!NOTE]  
>  O **sql_variant** tipo de dados é semelhante ao tipo de dados Variant em Microsoft Visual Basic® e ao DBTYPE_VARIANT, DBTYPE_SQLVARIANT no OLEDB.  
  
 Quando **sql_variant** os dados são buscados como DBTYPE_VARIANT, eles são colocados em uma estrutura VARIANT no buffer. Mas os subtipos na estrutura VARIANT podem não ser mapeados para os subtipos definidos na **sql_variant** tipo de dados. O **sql_variant** dados, em seguida, devem ser buscados como DBTYPE_SQLVARIANT para que todos os subtipos sejam correspondidos.  
  
## <a name="dbtypesqlvariant-data-type"></a>Tipo de dados DBTYPE_SQLVARIANT  
 Para dar suporte a **sql_variant** tipo de dados, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client expõe um tipo de dados específico do provedor denominado DBTYPE_SQLVARIANT. Quando **sql_variant** dados são buscados como DBTYPE_SQLVARIANT, eles são armazenados em uma estrutura SSVARIANT específica do provedor. A estrutura SSVARIANT contém todos os subtipos que correspondem aos subtipos do **sql_variant** tipo de dados.  
  
 A propriedade de sessão SSPROP_ALLOWNATIVEVARIANT também deve ser definida como TRUE.  
  
## <a name="provider-specific-property-sspropallownativevariant"></a>Propriedade específica de provedor SSPROP_ALLOWNATIVEVARIANT  
 Ao buscar dados, você pode especificar explicitamente que tipo de dados deveria ser retornado para uma coluna ou um parâmetro. **IColumnsInfo** também pode ser usado para obter as informações de coluna e usá-lo para fazer a associação. Quando **IColumnsInfo** é usado para obter informações de coluna para fins de associação, se a propriedade for FALSE (valor padrão), de sessão SSPROP_ALLOWNATIVEVARIANT DBTYPE_VARIANT será retornado para **sql_variant**colunas. Se a propriedade SSPROP_ALLOWNATIVEVARIANT for FALSE, não haverá suporte para DBTYPE_SQLVARIANT. Se a propriedade SSPROP_ALLOWNATIVEVARIANT for definida como TRUE, o tipo de coluna será retornado como DBTYPE_SQLVARIANT; nesse caso o buffer armazenará a estrutura SSVARIANT. Ao buscar **sql_variant** dados como DBTYPE_SQLVARIANT, a propriedade de sessão SSPROP_ALLOWNATIVEVARIANT deverá ser definida como TRUE.  
  
 A propriedade SSPROP_ALLOWNATIVEVARIANT faz parte do conjunto de propriedades DBPROPSET_SQLSERVERSESSION específicas de provedor, sendo uma propriedade de sessão.  
  
 DBTYPE_VARIANT se aplica a todos os outros provedores OLE DB.  
  
## <a name="sspropallownativevariant"></a>SSPROP_ALLOWNATIVEVARIANT  
 SSPROP_ALLOWNATIVEVARIANT é uma propriedade de sessão e faz parte do conjunto de propriedades DBPROPSET_SQLSERVERSESSION.  
  
|||  
|-|-|  
|SSPROP_ALLOWNATIVEVARIANT|Tipo: VT_BOOL<br /><br /> Leitura/gravação: leitura/gravação<br /><br /> Padrão: VARIANT_FALSE<br /><br /> Descrição: Determina se os dados buscados são como DBTYPE_VARIANT ou DBTYPE_SQLVARIANT.<br /><br /> VARIANT_TRUE: o tipo de coluna é retornado como DBTYPE_SQLVARIANT e o buffer terá a estrutura SSVARIANT.<br /><br /> VARIANT_FALSE: o tipo de coluna é retornado como DBTYPE_VARIANT e o buffer terá a estrutura VARIANT.|  
  
## <a name="see-also"></a>Consulte também  
 [Tipos de dados &#40;OLE DB&#41;](data-types-ole-db.md)  
  
  
