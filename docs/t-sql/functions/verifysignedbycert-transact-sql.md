---
title: VERIFYSIGNEDBYCERT (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VERIFYSIGNEDBYCERT
- VERIFYSIGNEDBYCERT_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- digitally signed data for changes [SQL Server]
- verifying digitally signed data for changes
- testing digitally signed data for changes
- checking digitally signed data for changes
- VERIFYSIGNEDBYCERT
- signatures [SQL Server]
- digital signatures [SQL Server]
ms.assetid: 4e041f33-60c4-4190-91c7-220d51dd6c8f
caps.latest.revision: 41
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 6d4725d6e9e28100333040061eafb54f07db9066
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="verifysignedbycert-transact-sql"></a>VERIFYSIGNEDBYCERT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Testa se dados assinados digitalmente foram alterados desde que foram assinados.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
VerifySignedByCert( Cert_ID , signed_data , signature )  
```  
  
## <a name="arguments"></a>Argumentos  
 *Cert_ID*  
 É a ID de um certificado no banco de dados. *Cert_ID* é **int**.  
  
 *signed_data*  
 É uma variável do tipo **nvarchar**, **char**, **varchar**, ou **nchar** que contém dados que foi assinados com um certificado.  
  
 *assinatura*  
 É a assinatura que foi anexada aos dados assinados. *assinatura* é **varbinary**.  
  
## <a name="return-types"></a>Tipos de retorno  
 **int**  
  
 Retorna 1 quando os dados assinados estão inalterados, caso contrário, retorna 0.  
  
## <a name="remarks"></a>Comentários  
 **VerifySignedBycert** descriptografa a assinatura dos dados usando a chave pública do certificado especificado e compara o valor descriptografado a um hash MD5 computado recentemente dos dados. Se os valores corresponderem, a assinatura será confirmada como válida.  
  
## <a name="permissions"></a>Permissões  
 Exige a permissão VIEW DEFINITION no certificado.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-verifying-that-signed-data-has-not-been-tampered-with"></a>A. Verificando se os dados assinados não foram violados  
 O exemplo a seguir testa se as informações em `Signed_Data` foram alteradas desde que foram assinadas com o certificado chamado `Shipping04`. A assinatura é armazenada em `DataSignature`. O certificado, `Shipping04`, é passado para `Cert_ID`, que retorna a ID do certificado no banco de dados. Se `VerifySignedByCert` retornar 1, a assinatura estará correta. Se `VerifySignedByCert` retornar 0, os dados em `Signed_Data` não serão os que foram usados para gerar `DataSignature`. Neste caso, ou `Signed_Data` foi alterado desde que foi assinado ou `Signed_Data` foi assinado com um certificado diferente.  
  
```  
SELECT Data, VerifySignedByCert( Cert_Id( 'Shipping04' ),  
    Signed_Data, DataSignature ) AS IsSignatureValid  
FROM [AdventureWorks2012].[SignedData04]   
WHERE Description = N'data signed by certificate ''Shipping04''';  
GO  
```  
  
### <a name="b-returning-only-records-that-have-a-valid-signature"></a>B. Retornando somente registros que tenham uma assinatura válida  
 Esta consulta retorna somente os registros que não foram alterados desde que foram assinados com o certificado `Shipping04`.  
  
```  
SELECT Data FROM [AdventureWorks2012].[SignedData04]   
WHERE VerifySignedByCert( Cert_Id( 'Shipping04' ), Data,   
    DataSignature ) = 1   
AND Description = N'data signed by certificate ''Shipping04''';  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [CERT_ID &#40; Transact-SQL &#41;](../../t-sql/functions/cert-id-transact-sql.md)   
 [SIGNBYCERT &#40; Transact-SQL &#41;](../../t-sql/functions/signbycert-transact-sql.md)   
 [CREATE CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)   
 [ALTER CERTIFICATE &#40; Transact-SQL &#41;](../../t-sql/statements/alter-certificate-transact-sql.md)   
 [Remover certificado &#40; Transact-SQL &#41;](../../t-sql/statements/drop-certificate-transact-sql.md)   
 [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/backup-certificate-transact-sql.md)   
 [Hierarquia de criptografia](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  