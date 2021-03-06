---
title: Visão geral de tipos de dados espaciais | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-spatial
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], understanding
- geography data type [SQL Server], spatial data
- planar spatial data [SQL Server], geometry data type
- spatial data types [SQL Server]
ms.assetid: 1615db50-69de-4778-8be6-4e058c00ccd4
caps.latest.revision: 48
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: d6dbc52caa183352376ae04887ec02088e8459ce
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37162177"
---
# <a name="spatial-data-types-overview"></a>Visão geral de tipos de dados espaciais
  Há dois tipos de dados espaciais. O tipo de dados `geometry` oferece suporte a dados planares ou a dados euclidianos (planisfério). O tipo de dados `geometry` (planar) está de acordo com os Recursos Simples do Open Geospatial Consortium (OGC) para o SQL Specification versão 1.1.0 e compatível com o SQL MM (padrão ISO).  
  
 Além disso, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oferece suporte a `geography` tipo de dados que armazena dados de elipsoidais (Terra redonda), como coordenadas de latitude e longitude GPS.  
  
> [!IMPORTANT]  
>  Para obter uma descrição detalhada e exemplos de recursos espaciais introduzidos no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], incluindo aprimoramentos nos tipos de dados espaciais, baixe o white paper, [New Spatial Features in SQL Server Code-Named "Denali"](http://go.microsoft.com/fwlink/?LinkId=226407)(Novos recursos espaciais no SQL Server codinome "Denali").  
  
##  <a name="objects"></a> Objetos de dados espaciais  
 Os tipos de dados `geometry` e `geography` oferecem suporte a dezesseis objetos de dados espaciais, ou tipos de instâncias. No entanto, apenas onze desses tipos de instâncias *podem ser instanciados*. É possível criar e trabalhar com essas instâncias (ou criar uma instância delas) em um banco de dados. Essas instâncias derivam determinadas propriedades de seus tipos de dados pai que as distingue como `Points`, **LineStrings, CircularStrings**, `CompoundCurves`, `Polygons`, `CurvePolygons` ou como vários `geometry`ou `geography` instâncias em um `GeometryCollection`. O tipo `Geography` tem um tipo de instância adicional, `FullGlobe`.  
  
 A figura a seguir ilustra a `geometry` hierarquia na qual o `geometry` e `geography` baseiam-se os tipos de dados. Os tipos podem ser instanciados de `geometry` e `geography` são indicados em azul.  
  
 ![Hierarquia do tipo geometria](../../database-engine/media/geom-hierarchy.gif "hierarquia do tipo geometry")  
  
 Como a Figura indica, os dez tipos podem ser instanciados do `geometry` e `geography` tipos de dados são `Point`, `MultiPoint`, `LineString`, `CircularString`, `MultiLineString`, `CompoundCurve`, `Polygon`, `CurvePolygon`, `MultiPolygon`, e `GeometryCollection`. Há um tipo adicional do qual se pode criar uma instância para o tipo de dados de geography: `FullGlobe`. O `geometry` e `geography` tipos podem reconhecer uma instância específica desde que ele seja bem-formada, mesmo se a instância não está definida explicitamente. Por exemplo, se você definir um `Point` explicitamente usando o método stpointfromtext (), da instância `geometry` e `geography` reconhecem a instância como um `Point`, desde que a entrada do método esteja bem formada. Se você definir a mesma instância usando o método `STGeomFromText()`, os tipos de dados `geometry` e `geography` a reconhecerão como uma instância de `Point`.  
  
 Os subtipos dos tipos geometry e geography são divididos em tipos simples e de coleção.  Alguns métodos como `STNumCurves()` só funcionam com tipos simples.  
  
 Os tipos simples incluem:  
  
-   [Point](../spatial/point.md)  
  
-   [LineString](../spatial/linestring.md)  
  
-   [CircularString](../spatial/circularstring.md)  
  
-   [CompoundCurve](../spatial/compoundcurve.md)  
  
-   [Polígono](../spatial/polygon.md)  
  
-   [CurvePolygon](../spatial/curvepolygon.md)  
  
 Os tipos de coleção incluem:  
  
-   [MultiPoint](../spatial/multipoint.md)  
  
-   [MultiLineString](../spatial/multilinestring.md)  
  
-   [MultiPolygon](../spatial/multipolygon.md)  
  
-   [GeometryCollection](../spatial/geometrycollection.md)  
  
  
##  <a name="differences"></a> Diferenças entre os tipos de dados de geometria e geografia  
 Os dois tipos de dados espaciais sempre se comportam de maneira muito semelhante, mas há algumas diferenças importantes na maneira como eles são armazenados e manipulados.  
  
### <a name="how-connecting-edges-are-defined"></a>Como bordas de conexão são definidas  
 Os dados definidos para os tipos `LineString` e `Polygon` são somente vértices.  A borda de conexão entre dois vértices em um tipo geometry é uma linha reta.  No entanto, a borda de conexão entre dois vértices em um tipo de geografia é um amplo arco elíptico curto entre os dois vértices.  Uma grande elipse é a interseção do elipsoide com um plano no centro, e um amplo arco elíptico é um segmento de arco na grande elipse.  
  
### <a name="how-circular-arc-segments-are-defined"></a>Como são definidos segmentos de arco circular  
 Os segmentos de arco circular para tipos geometry são definidos no plano de coordenadas cartesianas XY (são ignorados valores Z). Os segmentos de arco circular para tipos geography são definidos por segmentos de curva em uma esfera de referência. Qualquer paralelo na esfera de referência pode ser definido por dois arcos circulares complementares, onde os pontos para ambos os arcos têm um ângulo de latitude constante.  
  
### <a name="measurements-in-spatial-data-types"></a>Medidas em tipos de dados espaciais  
 No sistema planar ou de terra plana, as medidas de distâncias e de áreas são fornecidas na mesma unidade de medida das coordenadas. Usando o `geometry` tipo de dados, a distância entre (2, 2) e (5, 6) é de 5 unidades, independentemente das unidades usadas.  
  
 No sistema elipsoidal ou de terra redonda, as coordenadas são fornecidas em graus de latitude ou de longitude. No entanto, comprimentos e áreas são normalmente medidas em metros e metros quadrados, embora a medida possa depender de identificador de referência espacial (SRID) do `geography` instância. A unidade mais comuns de medida para o `geography` tipo de dados é em metros.  
  
### <a name="orientation-of-spatial-data"></a>Orientação de dados espaciais  
 No sistema de planar, a orientação de anel de um polígono não é um fator importante. Por exemplo, um polígono descrito por ((0, 0), (10, 0), (0, 20), (0, 0)) é o mesmo que um polígono descrito por ((0, 0), (0, 20), (10, 0), (0, 0)). Os Recursos Simples do OGC para SQL Specification não ditam uma ordenação de anel e o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não impõe ordenação de anel.  
  
 Em um sistema elipsoidal, um polígono não tem nenhum significado ou é ambíguo, sem uma orientação. Por exemplo, um anel ao redor do equador descreve o hemisfério norte ou o sul? Se usarmos o `geography` tipo de dados para armazenar a instância espacial, deveremos especificar a orientação do anel e descrever precisamente o local da instância. O interior do polígono em um sistema elipsoidal é definido pela regra à esquerda.  
  
 Quando o nível de compatibilidade for 100 ou abaixo na [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] o `geography` tipo de dados tem as seguintes restrições:  
  
-   Cada instância de `geography` deve se ajustar dentro de um único hemisfério. Nenhum objeto espacial maior do que um hemisfério pode ser armazenado.  
  
-   Qualquer instância de `geography` de uma representação WKT (Well-Known Text) ou WKB (Well-Known Binary) do Open Geospatial Consortium (OGC) que reproduza um objeto maior do que um hemisfério aciona uma `ArgumentException`.  
  
-   O `geography` que requerem a entrada de dois métodos de tipo de dados `geography` instâncias, como stintersection (), stunion (), stdifference () e stsymdifference (), retornarão nulas se os resultados dos métodos não couberem em um único hemisfério. STBuffer() também retornará nulo se a saída ultrapassar um único hemisfério.  
  
 No [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` é um tipo especial de Polígono que abrange o globo inteiro. `FullGlobe` tem uma área, mas nenhuma borda ou vértices.  
  
### <a name="outer-and-inner-rings-not-important-in-geography-data-type"></a>Anéis externos e internos não são importantes no tipo de dados geography  
 Os recursos simples do OGC para SQL Specification discutem anéis externos e internos, mas essa distinção faz pouco sentido para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` de tipo de dados; qualquer anel de um polígono pode ser usado como anel externo.  
  
 Para obter mais informações sobre especificações do OCG, consulte o seguinte:  
  
-   [OGC Specifications, Simple Feature Access Part 1 - Common Architecture](http://go.microsoft.com/fwlink/?LinkId=93627)  
  
-   [OGC Specifications, Simple Feature Access Part 2 – SQL Options](http://go.microsoft.com/fwlink/?LinkId=93628)  
  
  
##  <a name="circular"></a> Segmentos de arco circular  
 Três tipos instanciáveis podem adotar segmentos de arco circular: `CircularString`, `CompoundCurve`, e `CurvePolygon`.  Um segmento de arco circular é definido por três pontos em um plano bidimensional, e o terceiro ponto não pode ser igual ao primeiro.  
  
 As figuras A e B mostram segmentos de arco circular típicos. Observe como cada um dos três pontos se situa no perímetro de um círculo.  
  
 As figuras C e D mostram como um segmento de linha pode ser definido como um segmento de arco circular.  Observe que três pontos ainda são necessários para definir o segmento de arco circular, ao contrário de um segmento de linha normal, que pode ser definido por apenas dois pontos.  
  
 Os métodos que operam em tipos de segmento de arco circular usam segmentos de linha reta para aproximar o arco circular. O número de segmentos de linha usado para aproximar o arco dependerá do comprimento e da curvatura do arco. Podem ser armazenados valores Z para cada um dos tipos de segmento de arco circular; porém, os métodos não usarão os valores Z em seus cálculos.  
  
> [!NOTE]  
>  Se forem fornecidos valores Z para segmentos de arco circular, eles deverão ser iguais para todos os pontos no segmento de arco circular para que o segmento seja aceito para entrada. Por exemplo, `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` é aceito, mas `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` não é.  
  
### <a name="linestring-and-circularstring-comparison"></a>Comparação de LineString e CircularString  
 O diagrama a seguir mostra triângulos isósceles idênticos (o triângulo A usa segmentos de linha para definir o triângulo, e o triângulo B usa segmentos de arco circular para definir o triângulo):  
  
 ![](../../database-engine/media/7e382f76-59da-4b62-80dc-caf93e637c14.png "7e382f76-59da-4b62-80dc-caf93e637c14")  
  
 Este exemplo mostra como armazenar os triângulos Isósceles anteriores usando um `LineString` instância e `CircularString` instância:  
  
```tsql  
DECLARE @g1 geometry;  
DECLARE @g2 geometry;  
SET @g1 = geometry::STGeomFromText('LINESTRING(1 1, 5 1, 3 5, 1 1)', 0);  
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(1 1, 3 1, 5 1, 4 3, 3 5, 2 3, 1 1)', 0);  
IF @g1.STIsValid() = 1 AND @g2.STIsValid() = 1  
  BEGIN  
      SELECT @g1.ToString(), @g2.ToString()  
      SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length]  
  END  
```  
  
 Note que uma instância `CircularString` requer sete pontos para definir o triângulo, mas uma instância `LineString` requer somente quatro pontos para definir o triângulo. O motivo para isso é que uma instância `CircularString` armazena segmentos de arco circular e não segmentos de linha. Portanto, os lados do triângulo armazenados na instância `CircularString` são ABC, CDE e EFA, ao passo que os lados do triângulo armazenados na instância `LineString` são AC, CE e EA.  
  
 Considere o seguinte trecho de código:  
  
```tsql  
SET @g1 = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 4 0)', 0);  
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(0 0, 2 2, 4 0)', 0);  
SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length];  
```  
  
 Esse trecho produzirá os seguintes resultados:  
  
```  
LS LengthCS Length  
5.65685…6.28318…  
```  
  
 A ilustração a seguir mostra como cada tipo é armazenado (linha vermelha mostra `LineString``@g1`azul linha mostra `CircularString``@g2`):  
  
 ![](../../database-engine/media/e52157b5-5160-4a4b-8560-50cdcf905b76.png "e52157b5-5160-4a4b-8560-50cdcf905b76")  
  
 Como a ilustração acima mostra, `CircularString` instâncias usam menos pontos para armazenar limites de curva com maior precisão que `LineString` instâncias. As instâncias `CircularString` são úteis para armazenar limites circulares como um raio de pesquisa de vinte milhas de um ponto específico. Instâncias `LineString` são boas para armazenar limites que são lineares como um quarteirão de cidade.  
  
### <a name="linestring-and-compoundcurve-comparison"></a>Comparação de LineString e CompoundCurve  
 Os exemplos de código a seguir mostram como armazenar a mesma figura usando `LineString` e `CompoundCurve` instâncias:  
  
```tsql  
SET @g = geometry::Parse('LINESTRING(2 2, 4 2, 4 4, 2 4, 2 2)');  
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2), (4 2, 4 4), (4 4, 2 4), (2 4, 2 2))');  
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2, 4 4, 2 4, 2 2))');  
```  
  
 ou em  
  
 Nos exemplos anteriores, uma `LineString` instância ou um `CompoundCurve` instância poderia armazenar a figura.  O exemplo a seguir usa um `CompoundCurve` para armazenar uma fatia de pizza:  
  
```tsql  
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(2 2, 1 3, 0 2),(0 2, 1 0, 2 2))');  
```  
  
 Um `CompoundCurve` instância pode armazenar o segmento de arco circular (2 de 2, 3 1, 0 2) diretamente, enquanto um `LineString` instância precisaria converter a curva em vários segmentos de linha menores.  
  
### <a name="circularstring-and-compoundcurve-comparison"></a>Comparação de CircularString e CompoundCurve  
 O exemplo de código a seguir mostra como a fatia de pizza pode ser armazenada em uma instância `CircularString`:  
  
```tsql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');  
SELECT @g.ToString(), @g.STLength();  
```  
  
 Para armazenar a fatia de pizza usando uma instância `CircularString`, é necessário que três pontos sejam usados para cada segmento de linha.  Se um ponto intermediário não for conhecido, ele deverá ser calculado ou o ponto de extremidade do segmento de linha deverá ser dobrado como mostra o seguinte trecho de código:  
  
```tsql  
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 3 6.3246, 3 6.3246, 0 7, -3 6.3246, 0 0, 0 0)');  
```  
  
 `CompoundCurve` instâncias permitem `LineString` e `CircularString` componentes para que somente dois pontos para os segmentos de linha da fatia de pizza precisam ser conhecidos.  Este exemplo de código mostra como usar um `CompoundCurve` para armazenar a mesma figura:  
  
```tsql  
DECLARE @g geometry;  
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING( 3 6.3246, 0 7, -3 6.3246), (-3 6.3246, 0 0, 3 6.3246))');  
SELECT @g.ToString(), @g.STLength();  
```  
  
### <a name="polygon-and-curvepolygon-comparison"></a>Comparação de Polygon e CurvePolygon  
 `CurvePolygon` as instâncias podem usar `CircularString` e `CompoundCurve` ao definir seus anéis exterior e interior.  `Polygon` instâncias não é possível usar os tipos de segmento de arco circular: `CircularString` e `CompoundCurve`.  
  
  
## <a name="see-also"></a>Consulte também  
 [Dados espaciais &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)   
 [Referência de método de tipo de dados geometry](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql)   
 [Referência de método de tipo de dados geography](/sql/t-sql/spatial-geography/spatial-types-geography)   
 [STNumCurves &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type)   
 [STNumCurves &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type)   
 [STGeomFromText &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)   
 [STGeomFromText &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)  
  
  
