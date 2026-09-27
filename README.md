# Apache Spark + PySpark — RDD e Processamento de Dados

> Repositório de estudos práticos sobre **Apache Spark** e **PySpark**, com foco em processamento distribuído, RDDs, transformações, ações e leitura/escrita de diferentes formatos de dados.

Este projeto reúne notebooks desenvolvidos durante meus estudos de **Big Data e processamento de dados com Apache Spark**. A ideia é experimentar, na prática, os principais conceitos da API de RDD e também a integração com **DataFrames, Spark SQL e formatos como CSV e Parquet**.

---

## 📚 Conteúdos estudados

### 1. RDD — Resilient Distributed Dataset

Os notebooks apresentam os primeiros conceitos de RDD, incluindo:

- Criação de RDDs com `parallelize()`
- Número de partições
- Leitura e inspeção de dados
- `first()`, `take()` e `collect()`
- Transformações com `map()`
- Filtragem com `filter()`
- Transformações com `flatMap()`
- Estruturas chave-valor

### 2. Transformações e ações

Prática com operações fundamentais do Spark, explorando a diferença entre **transformações** e **ações**.

Entre os exemplos:

```python
rdd.map(...)
rdd.flatMap(...)
rdd.filter(...)
rdd.reduceByKey(...)
rdd.sortByKey(...)
rdd.count()
rdd.collect()
```

### 3. Word Count

Um dos exercícios clássicos de processamento distribuído:

**Arquivo → palavras → pares (palavra, 1) → agrupamento → contagem**

Exemplo utilizado no notebook:

```python
palavraChaveValor = palavra.map(lambda x: (x, 1))

palavraContar = palavraChaveValor.reduceByKey(
    lambda x, y: x + y
)
```

Também é explorada a gravação do resultado utilizando:

```python
saveAsTextFile()
```

O exercício demonstra um detalhe importante do Spark: a saída pode ser distribuída em múltiplos arquivos, de acordo com as partições do RDD.

---

## 🗂️ Leitura e escrita de dados

Os notebooks também exploram o trabalho com dados estruturados utilizando **SparkSession** e **DataFrames**.

Entre os exemplos estudados:

- Leitura de arquivos CSV
- Definição e inferência de schema
- Conversão e manipulação de tipos
- Visualização de DataFrames
- Leitura e escrita em Parquet
- Persistência de DataFrames
- Criação e consulta de tabelas
- Integração com Spark SQL

Exemplo:

```python
spark = SparkSession.builder.getOrCreate()

df = spark.read.csv("ecommerce_estatistica.csv")
df.show()
```

E também:

```python
videosParquetData = spark.read.parquet(
    "youtube_parquet_data/videos-parquet"
)
```

---

## 🧠 Conceitos principais

| Conceito | Prática no projeto |
|---|---|
| RDD | Criação e manipulação de conjuntos de dados distribuídos |
| Partições | Inspeção e entendimento da distribuição dos dados |
| `map()` | Transformação elemento a elemento |
| `flatMap()` | Transformação e achatamento de coleções |
| `filter()` | Filtragem de dados |
| `reduceByKey()` | Agregação por chave |
| `sortByKey()` | Ordenação de pares chave-valor |
| Actions | Execução e materialização dos resultados |
| DataFrame | Manipulação de dados estruturados |
| Schema | Definição/inferência da estrutura dos dados |
| CSV | Leitura e processamento de arquivos tabulares |
| Parquet | Armazenamento e leitura de dados em formato colunar |
| Spark SQL | Consulta de dados utilizando SQL |
| Persistência | Salvamento de resultados e tabelas |

---

## 📁 Estrutura do repositório

```text
apache-spark-rdd/
│
├── LeituraEscritaDeDados.ipynb
├── leitura_escrita.ipynb
└── README.md
```

### Notebooks

**`LeituraEscritaDeDados.ipynb`**

Notebook principal com uma abordagem mais abrangente dos conceitos de RDD, transformações e ações, processamento de texto, leitura de dados, DataFrames, Parquet e Spark SQL.

**`leitura_escrita.ipynb`**

Notebook complementar voltado aos exercícios de leitura e escrita de dados utilizando PySpark.

---

## 🚀 Como executar

A maneira mais simples de executar os notebooks é utilizando o **Google Colab**.

### Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kleitonfr/apache-spark-rdd/blob/main/LeituraEscritaDeDados.ipynb)

Ou abra diretamente:

- [Leitura e Escrita de Dados](https://colab.research.google.com/github/kleitonfr/apache-spark-rdd/blob/main/LeituraEscritaDeDados.ipynb)
- [Leitura e Escrita](https://colab.research.google.com/github/kleitonfr/apache-spark-rdd/blob/main/leitura_escrita.ipynb)

### Ambiente local

Com Python instalado, o PySpark pode ser instalado com:

```bash
pip install pyspark
```

Depois, basta abrir um dos notebooks utilizando Jupyter Notebook, JupyterLab ou outra ferramenta compatível com arquivos `.ipynb`.

> **Observação:** alguns exercícios utilizam datasets referenciados pelo notebook, como arquivos CSV e diretórios de dados para exemplos com Parquet. Dependendo do ambiente utilizado, esses arquivos podem precisar ser disponibilizados antes da execução.

---

## 🎯 Objetivo

Este repositório faz parte do meu processo de aprendizado em **Big Data, processamento distribuído e engenharia de dados**.

O foco é entender não apenas a sintaxe do PySpark, mas também conceitos importantes por trás do processamento distribuído, como:

- particionamento;
- transformações e ações;
- processamento de grandes volumes de dados;
- operações chave-valor;
- estruturas distribuídas;
- processamento de dados estruturados;
- armazenamento em formatos apropriados para análise.

---

## 🛠️ Tecnologias

- 🐍 **Python**
- ⚡ **Apache Spark**
- 🔥 **PySpark**
- 📊 **Spark DataFrame**
- 🗃️ **Spark SQL**
- 🧩 **RDD**
- 📦 **Parquet**
- 📄 **CSV**
- 📓 **Jupyter Notebook / Google Colab**

---

## 👨‍💻 Autor

**Kleiton Ferreira**

Estudante de **Análise e Desenvolvimento de Sistemas** e desenvolvedor Full Stack, explorando tecnologias relacionadas a **dados, Big Data, processamento distribuído e inteligência artificial**.

---

⭐ Se este repositório foi útil para seus estudos, fique à vontade para acompanhar o projeto e explorar os notebooks.
