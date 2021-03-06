---
title: SQL Server Machine Learning e R Services (no banco de dados) | Microsoft Docs
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/15/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 05a2a17988912d7066b0d9f6bf398b889a3cd882
ms.sourcegitcommit: c37da15581fb34250d426a8d661f6d0d64f9b54c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39174773"
---
# <a name="sql-server-machine-learning-and-r-services-in-database"></a>SQL Server Machine Learning e R Services (no banco de dados)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Uma instalação no banco de dados do aprendizado de máquina opera dentro do contexto de uma instância do mecanismo de banco de dados do SQL Server, fornecendo suporte de script externo do R e Python para dados residentes em sua instância do SQL Server. Como o aprendizado de máquina é integrado com [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você pode manter a análise próxima aos dados e eliminar os custos e riscos de segurança associados à movimentação de dados.

Como o mecanismo de banco de dados é com várias instâncias, você pode instalar mais de uma instância de análise no banco de dados, ou até mesmo mais e mais recentes versões lado a lado. As opções incluem o [serviços SQL Server 2017 Machine Learning (no banco de dados)](../install/sql-machine-learning-standalone-windows-install.md) com o R e Python, ou [SQL Server 2016 R Services (no banco de dados)](../install/sql-r-standalone-windows-install.md) com apenas R. 

Componentes de aprendizado de máquina também podem ser instalados como instância independente [servidores autônomos](r-server-standalone.md). Em geral, é recomendável que você trate (autônomo) e (no banco de dados) instalações como mutuamente exclusivos para evitar a contenção de recursos, mas se você tiver recursos suficientes, não há nenhuma das proibições contra instalar ambos no mesmo computador físico.

## <a name="choosing-between-in-database-and-standalone-analytics"></a>Escolhendo entre o autônomo e no banco de dados de análise

Noções básicas sobre seus requisitos de desenvolvimento pode ajudá-lo a escolher entre (no banco de dados) e se aproxima de (autônomo). Um servidor autônomo é mais simples de configurar e gerenciar a máxima flexibilidade em como ele é usado, ou se você quiser conectar-se também a uma variedade de fontes de dados fora do SQL Server. 

Análise no banco de dados é projetado para integração profunda com os dados no SQL Server. Você pode escrever consultas do T-SQL que chamam funções do R ou Python e executar o script no SQL Server Management Studio ou qualquer ferramenta ou aplicativo usado para T-SQL inserido ou externo. Se você precisar executar código R ou Python em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], usando procedimentos armazenados ou usando o SQL Server da instância como o [contexto de computação](https://docs.microsoft.com/machine-learning-server/r/concept-what-is-compute-context), você deve instalar a análise no banco de dados. Essa opção fornece segurança máxima de dados e a integração com ferramentas do SQL Server.

Tanto no banco de dados e servidores autônomos podem aliviar as restrições de memória e processamento de software livre R e Python. Ambas as opções incluem os mesmos pacotes e ferramentas, com a capacidade de carregar e processar grandes quantidades de dados em vários núcleos e agregar os resultados em uma única saída consolidada. As funções e os algoritmos são projetados para escala e o utilitário: fornecimento de modelagem estatística, análise preditiva, visualizações de dados e algoritmos em um produto de servidor comercial de aprendizado de máquina de ponta com engenharia e suporte Microsoft. 

## <a name="components-of-an-in-database-installation"></a>Componentes de uma instalação no banco de dados

SQL Server 2016 é apenas o R. O SQL Server 2017 oferece suporte às linguagens R e Python. A tabela a seguir descreve os recursos em cada versão. Com exceção do serviço do Launchpad do SQL Server, essa tabela é idêntica àquele fornecida na [artigo de servidor autônomo](r-server-standalone.md).

| Componente | Description |
|-----------|-------------|
| Serviço do Launchpad do SQL Server | Um serviço que gerencia a comunicação entre os tempos de execução de R e Python externos e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância. |
| Pacotes de R | [RevoScaleR](revoscaler-overview.md) é a biblioteca principal para o R escalonável com funções de manipulação de dados, transformação, visualzation e análise.  <br/>[MicrosoftML (R)](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/microsoftml-package) adiciona algoritmos de aprendizado de máquina para criar modelos personalizados para análise de sentimento, análise de imagem e análise de texto. <br/>[mrsdeploy](operationalization-with-mrsdeploy.md) ofertas da web de implantação do serviço (no SQL Server 2017 somente). <br/>[olapR](how-to-create-mdx-queries-using-olapr.md) é para especificar consultas MDX em R.|
| Microsoft R Open MRO) | [MRO](https://mran.microsoft.com/open) é a distribuição do código-fonte aberto da Microsoft do R. O pacote e o interpretador são incluídos. Sempre use a versão do MRO agrupado em instalação. |
| Ferramentas do R | Janelas do console de R e prompts de comando são ferramentas padrão em uma distribuição de R. Para encontrá-los em \Program files\Microsoft Server\140\R_SERVER\bin\x64 SQL. |
| Exemplos de R e scripts |  Pacotes de R e RevoScaleR do código-fonte aberto incluem conjuntos de dados internos para que você pode criar e executar o script usando os dados previamente instalados. Examine para que eles \Program files\Microsoft SQL Server\140\R_SERVER\library\datasets e \library\RevoScaleR. |
| Pacotes do Python | [revoscalepy](../python/what-is-revoscalepy.md) é a biblioteca principal para o Python e escalonável com funções de manipulação de dados, transformação, visualzation e análise. <br/>[microsoftml (Python)](https://docs.microsoft.com/machine-learning-server/python-reference/microsoftml/microsoftml-package) adiciona algoritmos de aprendizado de máquina para criar modelos personalizados para análise de sentimento, análise de imagem e análise de texto.  |
| Ferramentas do Python | A ferramenta de linha de comando interna do Python é útil para testar ad hoc e tarefas. Encontre a ferramenta em \Program files\Microsoft Server\140\PYTHON_SERVER\python.exe SQL. |
| Anaconda | O anaconda é uma distribuição de software livre de Python e pacotes essenciais. |
| Scripts e exemplos de Python | Assim como acontece com R, Python inclui conjuntos de dados internos e scripts. Encontre os dados revoscalepy em \Program files\Microsoft SQL Server\140\PYTHON_SERVER\lib\site-packages\revoscalepy\data\sample-data. |
| Modelos previamente treinados em R e Python | Modelos previamente treinados são suportados e pode ser usado em um servidor autônomo, mas você não pode instalá-los por meio da instalação do SQL Server. O programa de instalação para o Microsoft Machine Learning Server fornece modelos, que pode ser instalada gratuitamente. Para obter mais informações, consulte [Install pré-treinado modelos de aprendizado de máquina no SQL Server](../install/sql-pretrained-models-install.md). |

## <a name="get-started-step-by-step"></a>Introdução ao passo a passo

Iniciar com a instalação, anexar os binários a ferramenta de desenvolvimento favorita e escrever seu primeiro script.

### <a name="step-1-install-the-software"></a>Etapa 1: Instalar o software

Instale uma dessas versões:

+ [Serviços de Machine Learning do SQL Server 2017 (no banco de dados)](../install/sql-machine-learning-services-windows-install.md)

+ [SQL Server 2016 R Services (no banco de dados) - R somente](../install/sql-r-services-windows-install.md)
 
### <a name="step-2-configure-a-development-tool"></a>Etapa 2: Configurar uma ferramenta de desenvolvimento

Configure suas ferramentas de desenvolvimento para usar os binários do Machine Learning Server. Para obter mais informações sobre o Python, consulte [binários Python Link](https://docs.microsoft.com/machine-learning-server/python/quickstart-python-tools). Para obter instruções sobre como conectar-se no R Studio, consulte [usando diferentes versões do R](https://support.rstudio.com/hc/en-us/articles/200486138-Using-Different-Versions-of-R) e apontar a ferramenta para C:\Program Files\Microsoft SQL Server\140\R_SERVER\bin\x64. Você também pode tentar [ferramentas do R para Visual Studio](https://docs.microsoft.com/visualstudio/rtvs/installation). 

Cientistas de dados geralmente usam R ou Python na estação de trabalho seu próprios laptops ou desenvolvimento, para explorar dados e criar e ajustar modelos de previsão, até que um bom modelo de previsão é obtido. 

Com a análise no banco de dados no SQL Server, não é necessário alterar esse processo. Após a instalação for concluída, você pode executar código R ou Python em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] localmente ou remotamente:

![rsql_keyscenario2](media/rsql-keyscenario2.png) 

+ **Usar o IDE que preferir**. Os componentes do cliente do[!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)] fornece aos cientistas de dados todas as ferramentas necessárias para testes e para desenvolvimento. Essas ferramentas incluem o tempo de execução de R, a biblioteca de kernel de matemática da Intel para melhorar o desempenho de operações padrão de R e um conjunto avançados de pacotes de R que dão suporte à execução do código R no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  

+ **Trabalhar remotamente ou localmente**. Os cientistas de dados podem se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e transferir os dados para o cliente para análise local, como de costume. No entanto, uma solução melhor é usar o **RevoScaleR** ou **revoscalepy** APIs para enviar cálculos para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computador, evitando a movimentação de dados cara e insegura.

+ **Inserir scripts R ou Python em [!INCLUDE[tsql](../../includes/tsql-md.md)] procedimentos armazenados**. Quando seu código totalmente é otimizado, coloque-o em um procedimento armazenado para evitar a movimentação desnecessária de dados e otimizar tarefas de processamento de dados.

### <a name="step-3-write-your-first-script"></a>Etapa 3: Escrever seu primeiro script

Chame funções de R ou Python de dentro do script T-SQL:
  
  + [R: usar o código R no Transact-SQL](../tutorials/rtsql-using-r-code-in-transact-sql-quickstart.md) 
  + [R: análise no banco de dados para desenvolvedores do SQL](../tutorials/sqldev-in-database-r-for-sql-developers.md)
  + [Python: executar o Python usando o T-SQL](../tutorials/run-python-using-t-sql.md)
  + [Python: análise no banco de dados para desenvolvedores do SQL](../tutorials/sqldev-in-database-python-for-sql-developers.md)

Escolha a melhor linguagem para a tarefa. R é melhor para cálculos estatísticos que são difíceis de implementar usando SQL. Para operações baseadas em conjunto em dados, aproveite o poder do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para alcançar desempenho máximo. Use o mecanismo de banco de dados na memória para cálculos muito rápidos nas colunas.

### <a name="step-4-optimize-your-solution"></a>Etapa 4: Otimizar sua solução

Quando o modelo estiver pronto para ser dimensionado nos dados da empresa, o cientista de dados geralmente funciona com o desenvolvedor do DBA ou SQL para otimizar os processos, como:

+ Engenharia de recursos
+ Ingestão de dados e transformação de dados
+ Pontuação

Tradicionalmente, os cientistas de dados usando o R teve problemas com desempenho e dimensionamento, especialmente ao usar um grande conjunto de dados. Isso ocorre porque a implementação de tempo de execução comum é single-threaded e pode acomodar apenas os conjuntos de dados que cabem na memória disponível no computador local. Integração com serviços do SQl Server Machine Learning fornece vários recursos para melhorar o desempenho, com mais dados:

+ **RevoScaleR**: pacote R este contém implementações de algumas das funções R mais populares, remodeladas para oferecer paralelismo e escala. O pacote também inclui funções que aumentam ainda mais o desempenho e a escala enviando por push cálculos para o computador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que geralmente tem muito mais memória e eficiência computacional.

+ **revoscalepy**. Essa biblioteca Python, disponível no SQL Server 2017, implementa funções mais populares do RevoScaleR, como contextos de computação remota e processamento distribuído de muitos algoritmos que oferecem suporte.

**Recursos**

+ [Estudo de caso de desempenho](../../advanced-analytics/r/performance-case-study-r-services.md)
+ [R e otimização de dados](../../advanced-analytics/r/r-and-data-optimization-r-services.md)

### <a name="step-5-deploy-and-consume"></a>Etapa 5: Implantar e consumir

Depois que o script ou o modelo estiver pronto para uso em produção, um desenvolvedor de banco de dados pode incorporar o código ou o modelo em um procedimento armazenado, para que o código R ou Python salvo pode ser chamado a partir de um aplicativo. Armazenar e executar código R do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] traz muitos benefícios: você pode usar a interface conveniente do [!INCLUDE[tsql](../../includes/tsql-md.md)] e todos os cálculos ocorrem no banco de dados, evitando movimentação desnecessária de dados.

![rsql_keyscenario1](media/rsql-keyscenario1.png)

+ **Seguro e extensível**. [!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)] usa uma nova arquitetura de extensibilidade que mantém seu mecanismo de banco de dados seguro e isola as sessões de R e Python. Você também tem controle sobre os usuários que podem executar scripts, e você pode especificar quais bancos de dados podem ser acessados pelo código. Você pode controlar a quantidade de recursos alocados para o tempo de execução, para evitar que cálculos imensos prejudiquem o desempenho geral do servidor.

+ **Agendamento e a auditoria**. Quando os trabalhos de script externo são executados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você pode controlar e auditoria de dados usado por cientistas de dados. Você também pode agendar trabalhos e criar fluxos de trabalho que contêm scripts R ou Python externos, exatamente como você pode agendar qualquer trabalho T-SQL ou procedimento armazenado.

Para aproveitar as vantagens dos recursos de segurança e gerenciamento de recursos no SQL Server, o processo de implantação pode incluir estas tarefas:

+ Convertendo yourcode para uma função que pode ser executados de forma ideal em um procedimento armazenado
+ Configurando a segurança e bloqueio de pacotes usados por uma tarefa específica
+ Habilitar a governança de recursos (requer a Enterprise edition)

**Recursos**

+ [Governança de recursos para R](resource-governance-for-r-services.md)
+ [Gerenciamento de pacotes de R para SQL Server](install-additional-r-packages-on-sql-server.md)

## <a name="see-also"></a>Confira também

 [SQL Server Machine Learning e R Server (autônomo)](sql-server-r-services.md)
