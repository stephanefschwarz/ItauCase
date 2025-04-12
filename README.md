<<<<<<< HEAD
Case Seleção - Cientista de Dados NLP
=================

* [1. Introdução](#1-introdução)
    * [1.1. Contexto do case](#11-contexto-do-case)
    * [1.2. Sobre o Dataset](#12-sobre-o-dataset)
      * [1.2.1 Enriquecimento de Dados](#121-enriquecimento-de-dados)
* [2. Tarefa do Cientista](#2-tarefa-do-cientista)
    * [2.1. Requisitos](#21-requisitos)
    * [2.2. Entregáveis](#22-entregáveis)


### 1. Introdução

Este case tem como objetivo avaliar as habilidades do candidato em NLP, em especial, em tarefas de pré-processamento de texto e embeddings de pequenos trechos de texto (Nome Fantasia/Razão Social de Empresas).

#### 1.1. Contexto do case

Imagine que você é um cientista de dados em uma empresa. Seu time está desenvolvendo um sistema de busca de empresas Brasileiras pelo nome fantasia ou razão social. O sistema deverá ser capaz de receber um texto digitado pelo usuário e retornar as empresas mais próximas do texto digitado.

#### 1.2. Sobre o Dataset

Neste case, utilizaremos o dataset `train.parquet` dentro da pasta `dados`. Esta pasta contém um notebook com o racional de como a base do dataset foi construída a partir de [*dados públicos*](https://arquivos.receitafederal.gov.br/dados/cnpj/dados_abertos_cnpj/2025-02/) da Receita Federal de fev/25. Neste repositório há PDFs com a documentação dos dados que foram utilizados para a construção do dataset.

##### 1.2.1 Enriquecimento de Dados

Para simularmos o texto digitado pelo usuário, foi adicionado um campo `user_input` no dataset. Este campo foi gerado usando os `razao_social` ou o `nome_fantasia` da empresa empregando algumas técnicas de distorção de texto (LLMs, ReGex, etc). Exemplos de funções utilizadas para gerar o campo `user_input` estão disponíveis no notebook `mistake_generator.ipynb`.

### 2. Tarefa do Cientista

Seu objetivo é criar/usar um modelo de Embeddings ou outras técnicas de NLP para encontrar as empresas mais próximas do texto digitado pelo usuário. 

#### 2.1. Requisitos

- *Não será permitido o uso de modelos generativos grandes* (GPT-3, GPT-4, Llama, Mistral, modelos pré-treinados da Hugging Face, etc). Uso do APIs *third party* não é permitido para este case.
- **Só será permitido o uso das colunas** `user_input` e/ou `uf` como consta no exemplo de solução no notebook `example_solution.ipynb`.
- As colunas de target de texto constam no mesmo notebook, e estão destacadas no arquivo `conf.yaml`.
- Você pode utilizar modelos pré-treinados de Embeddings (Word2Vec, GloVe, FastText, Bert BiEncoders, CrossEncoders, etc), pode *tunar* algum modelo pré-treinado ou treinar um modelo próprio. Além disso, também pode utilizar técnicas clássicas de NLP (TF-IDF, CountVectorizer, etc).
- Você pode utilizar técnicas de pré-processamento de texto (Tokenização, Stemming, Lematização, etc).
- Você pode utilizar técnicas de similaridade de texto (Cosine Similarity, Jaccard Similarity, etc).
- Você pode utilizar técnicas de classificação de texto (SVM, Random Forest, etc).
- Você poder combinar diversas técnicas para atingir o objetivo.

#### 2.2. Entregáveis

**IMPORTANTE!** Antes de começar o case veja o notebook `example_solution.ipynb` para entender o que é esperado como entrega.

Um repositório no GitHub contendo:
- O código fonte do modelo/técnica utilizado.
- Um notebook/scripts com o passo a passo da solução.
- A performance em **precision** (top 1 e top 5) do modelo/técnica utilizado (um acerto no top 5 é considerado quando a empresa correta está entre as 5 primeiras empresas retornadas pelo modelo).

Por fim, lembre-se de documentar o código e o notebook de forma clara e objetiva, **pois sua técnica/modelo será avaliada em um conjunto de teste que não foi disponibilizado**.

A performance do modelo nos conjuntos de treino e teste será avaliada de acordo com a métrica de **precision** (top 1 e top 5) e isso será um dos principais critérios de avaliação do case.

Boa sorte!
=======
# TO DO

### Preprocessing

Default preprocessing from the user input string respective:

- [ ] Set all text sentence to lower
- [ ] Remove special characters and punctuation
- [ ] Remove extra write space in the beging and end of the sentence
- [ ] Remove word accents

> [!NOTE]
> Below I list a set of preprocessing we can evaluate during inference time, however, I don't believe it will improve the matching processing once it can increase the edit distance (increase the discimilarity) between the original company name and the one provided by the end user, specially in case the user passed the correct name.

- [ ] Deduplicate repeated words
- [ ] Stemming
- [ ] Lemmatization
- [ ] Remove Stop Words

### Searching strategies

#### Distance Metrics
- [ ]  Cosine
- [ ]  Euclidean
- [ ]  Manhattan
- [ ]  Minkowski
- [ ]  SEuclidean
- [ ]  Mahalanobis
- [ ]  Hamming
- [ ]  Canberra
- [ ]  BrayCurtis

#### Embeddings
- [ ] Bag-of-words normalized with TF-IDF
- [ ] Multilingual Dense Embeddings
- [ ] Hashing Vectorizer

#### Techniques
- [ ] Clustering (Leiden, RAC)
- [ ] Knowledge Graph
- [ ] Ranking
- [ ] Edit Distance
- [ ] Contrastive Learning
- [ ] Fuzzy Matching
- [ ] Semantic Search

## Challanges

One of the biggest challanges of this case is to search on two list quickly. We have the razão social and the nome fantasia fields to compare with the input provided by the user. 

We cannot combine both one it can cause an extra effort for the model find the correct match, and by search into both sequentially, will cause an significan increase in the inference time reponse considering in a real world enviroument we will have millions of names to search for. 




>>>>>>> fbad72774aa2c6a9ec3e28c26111bb8c602f6f3e
