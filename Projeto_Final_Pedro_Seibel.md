<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Implementação de Sistema de SIG e BI, voltado para auxiliar o processo de tomada de decisão e de inteligência territorial, na Gestão do Território.


#### Aluno: [Pedro Iglesias Bessa Seibel](https://github.com/Pedro-Seibel).
#### Orientadora: [Anderson Nascimento](https://github.com/insightds).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->

---

### Resumo

<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->

O objetivo deste estudo é apresentar todos os processos realizados para a implementação de sistema de administração territorial (usando tecnologias de SIG e BI), voltado para auxiliar o processo de tomada de decisão e de inteligência territorial de Institutos de Terras.

### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->

<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->

The objective of this study is to present all the processes carried out for the implementation of a land administration system (using GIS and BI technologies), aimed to assist the decision-making process and territorial intelligence of Land Institutes.

### 1. Introdução

Historicamente, um dos maiores entraves para realizar implementação de políticas públicas, de forma eficiente, é a dificuldade para relacionar as diferentes informações que são necessárias na execução e monitoramento dos projetos. Dentre os entraves citados, os mais recorrentes são a dificuldade na obtenção de dados e falta de interoperabilidade das informações, dificultando o relacionamento dos dados. Com o avanço das tecnologias de Sensoriamento Remoto e Geoprocessamento, a coleta dos dados e seus relacionamentos (mesmo em grande quantidade), se tornou mais rápida, possibilitando análises complexas em territórios extensos (por exemplo, o território nacional). 

O Mercado de Terras é tema de extrema relevância nos debates sobre a política agrária contemporânea, no Brasil e internacionalmente. A execução e o monitoramento de políticas voltadas ao mercado de terras capacitam o Estado a regular o seu maior bem (terra) para suas diversas finalidades, seja econômica, social, ambiental, entre outros fins. A capacidade de bancos e outras instituições financeiras em providenciar recursos para o desenvolvimento do território, é influenciada pelos mercados de terras, o qual requer um eficiente sistema que auxilie na gestão e administração do território.

Nos dias atuais, a obtenção de informações e interoperabilidade entre as mesmas não é um grande problema para a implementação de políticas públicas sobre o Mercado de Terras, no Brasil. O país já possui Planilhas de Preços Referenciais (PPR), além de possuir diversas fontes de dados de Uso e Cobertura do Solo, que podem ser utilizadas nos cruzamentos necessários. A PPR é matriz de dados que relaciona os atributos de uso do solo com o preço da terra (por hectare), o qual é praticado em determinado Mercado Regional de Terras.

O objetivo deste estudo é apresentar os processos realizados para a implementação de Sistema de Administração Territorial (usando tecnologias de SIG e BI), voltado para auxiliar o processo de tomada de decisão e de inteligência territorial dos Institutos de Terras. Para tal, foram demonstrados cruzamentos e análises geoespaciais, realizados com o uso de Sistemas de Informação Geográfica (SIG), que resultaram na implementação de Sistema de Business Intelligence (BI) para análise dos Mercados de Terras. Estas análises foram realizadas com foco nos Mercados Regionais de Terras brasileiros (agrupamento de municípios).

### 2. Modelagem

2.1 Fontes das Informações

Abaixo, o estudo descreve categoria, instituição responsável e locais para realizar o download, dos dados utilizados no sistema para a implementação do Sistema de SIG e BI, voltado para auxiliar processo de tomada de decisão e inteligência territorial, do setor de Mercado de Terras do INCRA. As principais bases de dados utilizadas no sistema em questão, foram os Mercados Regionais de Terras - MRT (INCRA), o Uso e Cobertura do Solo (IBGE), a Planilha de Preços Referenciais da Terra (INCRA), Estados e Municípios (IBGE) e as Áreas Urbanas que possuem mais de 100 mil habitantes (IBGE).

2.1.1 Fonte de Dados da informação de Mercado Regionais de Terras (INCRA);
•	Categoria: Dado público
•	Instituição Responsável: O banco de dados se encontra com o setor de Mercado de Terras do INCRA (Instituto Nacional de Colonização e Reforma Agrária).
•	A informação, formato shapefile, foi realizada com o agrupamento de municípios do IBGE, utilizando como base as informações da Planilha de Preços Referenciais.

2.1.2 Fonte de Dados da informação de Uso e Cobertura do Solo (IBGE);
•	Categoria: Dado público.
•	Instituição Responsável: os dados geográficos e tabulares são disponibilizados publicamente no site do IBGE..
•	Link para download da informação:
	https://www.ibge.gov.br/geociencias/informacoes-ambientais/cobertura-e-uso-da-terra/15831-cobertura-e-uso-da-terra-do-brasil.html?=&t=downloads

2.1.3 Fonte de Dados da informação de Planilha de Preços Referenciais da Terra (INCRA);
•	Categoria: Dado público
•	Instituição Responsável: A tabela contato dados referentes aos preços referenciais de terra, praticados nos MRTs (Mercados Regionais de Terras) se encontra com o setor de Mercado de Terras do INCRA (Instituto Nacional de Colonização e Reforma Agrária).
•	A informação, em formato de planilha, está disponível no site do INCRA, por estado.

2.1.4 Fonte de Dados da informação de Estados e Municípios (IBGE);  
•	Categoria: Dado público.
•	Instituição Responsável: O banco de dados de Municípios e Regiões que foi utilizado no sistema se encontra hospedado no IBGE.
•	Link para download da informação:
	https://www.ibge.gov.br/geociencias/organizacao-do-territorio/malhas-territoriais/15774-malhas.html?=&t=acesso-ao-produto

2.1.5 Fonte de Dados da informação de Áreas Urbanas que possuem mais de 100 mil habitantes (IBGE);
•	Categoria: Dado público.
•	Instituição Responsável: O banco de dados das malhas de Setores Censitários de áreas Urbanas que possuem mais de 100 mil habitantes que foi utilizado no sistema se encontra hospedado no IBGE.
•	Link para download da informação:
	https://www.ibge.gov.br/geociencias/organizacao-do-territorio/tipologias-do-territorio/15789-areas-urbanizadas.html?=&t=downloads

2.2 Modelagem Dimensional de Bancos de Dados

Este capítulo apresenta Modelagem Conceitual do Banco de Dados do Sistema de BI, voltado para auxiliar processo de tomada de decisão e inteligência territorial, do setor de Mercado de Terras, do INCRA. O objetivo do modelo conceitual é criar um sistema coerente de objetos, propriedades e relações, que contenham os requisitos e regras do negócio. Seus principais elementos, que devem constar em todos os modelos conceituais de bancos de dados são:

Entidades – Uma entidade é uma representação de um conjunto de informações sobre determinado conceito do sistema. Toda entidade possui seus atributos, as quais são informações que referenciam entidade. Alguns exemplos de entidades do Sistema BI, voltado para auxiliar processo de tomada de decisão e inteligência territorial do INCRA são os Mercados Regionais de Terras, o Uso e Cobertura do solo, as Planilhas de Preço Referencial da Terra, entre outros.

Relacionamentos – O relacionamento de bancos de dados é associação entre as entidades que foram mencionadas. Existem 3 diferentes tipos de relacionamento utilizados em bancos de dados, são eles “uma para um”, “uma para muitos” e de “muitos para uma”.

Atributos – Os atributos são as informações que caracterizam as entidades e os relacionamentos mencionados. O atributo identifica, qualifica, descreve, quantifica e registra, o estado / situação / ocorrência, de uma entidade. Dentre os atributos usados no Sistema de BI, voltado para auxiliar processo de tomada de decisão e inteligência territorial do INCRA, cabe destacar Código MRT (Mercados Regionais de Terras), Área hectare e Classe de Uso (Uso e Cobertura do Solo), Valores da PPR (Planilhas de Preço Referencial da Terra), entre outros.

 
Figura 1. Modelagem dimensional do banco de dados, do sistema realizado.

![image](https://user-images.githubusercontent.com/114953233/193696470-e7369c3c-d307-4cb7-a5f7-6f9a00631a24.png)

Fonte: Do autor

### 3. Resultados

As principais bases de dados utilizadas no sistema em questão, foram os Mercados Regionais de Terras (INCRA), Uso e Cobertura do Solo (IBGE), Planilha de Preços Referenciais da Terra (INCRA), Estados e Municípios (IBGE) e Áreas Urbanas com mais de 100.000 habitantes (IBGE). O Sistema de Administração Territorial (SAT) contém mapas, gráficos, listas, tabelas e relatórios elaborados para a implementação de Sistema de BI, voltado para auxiliar processo de tomada de decisão e inteligência territorial, dos Institutos de Terras brasileiros.

Figura 2. Exemplo de Dashboard (análise do uso do solo como um todo) implementado no Sistema de BI realizado para auxiliar processo de tomada de decisão dos Institutos de Terras brasileiros.

![image](https://user-images.githubusercontent.com/114953233/193697322-fde53060-b2c0-440f-9f0b-395eda4488c3.png)

Fonte: Do autor

Figura 3. Exemplo de Dashboard de análise da agricultura implementado no Sistema de BI realizado para auxiliar processo de tomada de decisão dos Institutos de Terras brasileiros.

![image](https://user-images.githubusercontent.com/114953233/193697669-2b46182b-14a8-4f48-a2e1-06a44a5d5d8d.png)

Fonte: Do autor


### 4. Conclusões

Ao longo do presente estudo, foi apresentado o relatório contendo a documentação dos processos realizados na implementação do Sistema de SIG e BI, voltado para auxiliar processo de tomada de decisão e de inteligência territorial dos Institutos de Terras brasileiros. Desta forma, o estudo descreveu os processos utilizados no sistema, desde a coleta de dados, modelagem conceitual de banco de dados e relacionamentos espaciais e tabulares, até a implementação dos Dashboards que compões o Sistema de Administração Territorial (SAT), voltado para auxiliar processo de tomada de decisão e de inteligência territorial dos Institutos de Terras brasileiros.

---

Matrícula: 202.190.336

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
