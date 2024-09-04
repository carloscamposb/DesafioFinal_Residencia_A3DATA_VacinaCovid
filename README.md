# DesafioFinal_Residencia_PortoDigital_VacinaCovid 💙💉

Desafio final desenvolvido para a Residência do Porto Digital na empresa A3Data onde tivemos a oportunidade de trabalhar com construção de DataLake e camadas (Bronze, Silver e Gold) para criação de dashboards e analises.

## O que buscamos entender?
Buscamos entender a relação das vacinas ministradas e dos cidadões que se vacinaram na região metropólitana do Recife. Buscando padrões que podem favorecer novas campanhas de vacinas ou no enfrentamento de novas empidemias   

## Bancos de dados trabalhados
[Visão Geral - Dados abertos Recife](http://dados.recife.pe.gov.br/dataset/relacao-de-pessoas-vacinadas-covid-19) <br>
### Arquivos CSV: 
[Covid-19 2021](http://dados.recife.pe.gov.br/dataset/relacao-de-pessoas-vacinadas-covid-19/resource/a23463f8-58ca-4d91-9757-e0385ac1b061) <br>
[Covid-19 2022](http://dados.recife.pe.gov.br/dataset/relacao-de-pessoas-vacinadas-covid-19/resource/bd3221f6-2cfc-406b-9dc7-90cd1b90e860) <br>
[Covid-19 2023](http://dados.recife.pe.gov.br/dataset/relacao-de-pessoas-vacinadas-covid-19/resource/c32d30d6-71be-4731-ac33-ccca4322e502) <br>

## Tecnologias utilizadas
 🔵 **Java**
 🔵 **Pyspark**
 🔵 **SQL**
 🔵 **DataLake em camadas**
 🔵 **Google Colab**

## Instruções de Uso:
### Preparando o ambiente
* Atualize a lista de pacotes: `apt-get update` 
* instale o `Java 8 JDK headless` usando `apt-get install openjdk-8-jdk-headless -qq > /dev/null`;
* instale o `PySpark` via `pip install -q pyspark`, interface Python para o Apache Spark;
* Define o caminho do Java 8 `(/usr/lib/jvm/java-8-openjdk-amd64)` na variável de ambiente `JAVA_HOME`;
* Importa `SparkSession` e funções `(functions as f)` da biblioteca `pyspark.sql` para manipulação de dados;
* Inicializa uma sessão Spark usando `SparkSession.builder.getOrCreate()`, que cria uma nova sessão ou recupera uma existente;
> Isso configura o ambiente necessário para processar dados com o Spark.

### Camada Bronze 🥉 
### Baixando dados:
* Usa o comando `curl` para baixar os arquivos CSV;
* Os arquivo são salvos localmente com nomes exclusivos (Ex.: vacinados_21.csv, vacinados_22.csv, vacinados_23.csv);
* O comando `!ls -lh vacinados_*.csv` lista os arquivos CSV começando com `"vacinados_"`  para verificar a existência e detalhes dos arquivos baixados;
* Usa `os.listdir('.')` para listar todos os arquivos e diretórios na pasta atual e imprime a lista de arquivos, para verificar se os arquivos estão presentes;
* Organiza a tabela usando o delimitador `;`, define a primeira linha como cabeçalho `(header=True)`, e infere automaticamente os tipos de dados das colunas `(inferSchema=True)`;
* Usa as funções show() e printSchema() para exibir e os dados e verificar o esquema dos DataFrames
*Conta valores brancos e nulos
> Isso ajuda na obtenção de dados para local e organização dos mesmos

### Transformando em parquet:
* Utilizando o `(...).write.parquet(...)` 
* Confirma a criação do parquet com `(os.listdir('.'))`
> O formato Parquet é eficiente para armazenamento e processamento de grandes volumes de dados.

### Camada Silver 🥈 
* Lê os arquivos Parquet armazenados no diretório bronze
* Trata os dados removendo células nulas
* Trata os dados removendo duplicatas
* Aplicações de Joins para análises preliminares

### Camada Gold  🥇
* Realização de analises mais complexas
* Construção de Gráficos   


## Equipe 💙💉

> Bia Nader: (https://github.com/bianader) <br><br>
> Carlos Campos: (https://github.com/carloscamposb) <br><br>
> Lucas Teixeira: (https://github.com/Lukgt) <br><br>
> Ruth Xavier:(https://github.com/xavierruth) 

