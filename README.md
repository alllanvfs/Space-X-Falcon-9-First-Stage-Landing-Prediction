# Predição de Sucesso de Pouso do Primeiro Estágio do Falcon 9 da SpaceX

![Falcon 9 pousando](https://media.flyingmag.com/flyingmag.com/wp-content/uploads/2016/05/Falcon-9-landing-precision.jpg)
## 📖 Visão Geral do Projeto

Este projeto consiste em um pipeline completo de Ciência de Dados com o objetivo de prever se o primeiro estágio do foguete Falcon 9 da SpaceX pousará com sucesso. A reutilização de foguetes é um fator chave para a redução de custos em lançamentos espaciais, e prever a probabilidade de sucesso de um pouso com base em dados de pré-lançamento é de grande valor comercial.

O processo abrange desde a coleta de dados de múltiplas fontes, passando pela limpeza e análise exploratória, até a preparação de um dataset para treinar e avaliar modelos de Machine Learning.

---

## 📋 Índice

* [Objetivos do Projeto](#-objetivos-do-projeto)
* [Metodologia](#-metodologia)
    * [1. Coleta de Dados](#1-coleta-de-dados)
    * [2. Data Wrangling (Processamento de Dados)](#2-data-wrangling-processamento-de-dados)
    * [3. Análise Exploratória de Dados (EDA)](#3-análise-exploratória-de-dados-eda)
    * [4. Análise Preditiva](#4-análise-preditiva)
* [Principais Resultados da Análise](#-principais-resultados-da-análise)
* [🛠️ Tecnologias Utilizadas](#-tecnologias-utilizadas)

---

## 🎯 Objetivos do Projeto

As principais questões que este projeto busca responder são:

1.  Quais são os fatores chave (local de lançamento, órbita, massa da carga útil, etc.) que mais influenciam o sucesso de um pouso?
2.  Quais configurações de lançamento apresentam a maior taxa de sucesso histórico?
3.  É possível construir um modelo de classificação preciso para prever o resultado de um pouso com base nos parâmetros da missão?

---

## ⚙️ Metodologia

O projeto segue um pipeline de Ciência de Dados bem definido:

### 1. Coleta de Dados

* **API REST da SpaceX:** Os dados primários foram coletados programaticamente da API pública da SpaceX (`v4`), obtendo informações detalhadas sobre lançamentos, foguetes, cargas úteis e locais de lançamento.
* **Web Scraping:** Para complementar e validar os dados de pouso, foi utilizada a técnica de web scraping na página da Wikipedia "List of Falcon 9 and Falcon Heavy launches" com a biblioteca `BeautifulSoup`.

### 2. Data Wrangling (Processamento de Dados)

* **Limpeza e Filtragem:** Foram tratados valores ausentes (ex: `PayloadMass`) e os dados foram filtrados para focar exclusivamente nos lançamentos do foguete Falcon 9.
* **Engenharia de Features:** A variável alvo `Class` foi criada, convertendo os resultados textuais de pouso (ex: "Success (drone ship)") em um formato binário (1 para sucesso, 0 para falha), tornando o problema adequado para um modelo de classificação.

### 3. Análise Exploratória de Dados (EDA)

* **Análise com SQL:** Foram realizadas consultas SQL para extrair insights rápidos e responder a perguntas específicas de negócio, como a taxa de sucesso por local ou a massa média de carga para missões da NASA.
* **Visualização de Dados:** Utilizando `Seaborn` e `Matplotlib`, foram criados gráficos (barras, dispersão) para visualizar a relação entre as variáveis e a taxa de sucesso dos pousos.

### 4. Análise Preditiva

* O dataset final foi preparado para a modelagem de Machine Learning.
* Foram definidos os frameworks para treinar e avaliar diferentes algoritmos de classificação, como:
    * Regressão Logística
    * Support Vector Machine (SVM)
    * Árvore de Decisão
    * K-Nearest Neighbors (KNN)
* A otimização de hiperparâmetros com `GridSearchCV` foi planejada para encontrar a melhor performance para cada modelo.

---

## 📊 Principais Resultados da Análise

A análise exploratória revelou que a taxa de sucesso dos pousos é fortemente influenciada por uma combinação de fatores, incluindo:
* **Local de Lançamento:** Diferentes bases de lançamento apresentam taxas de sucesso distintas.
* **Tipo de Órbita:** Órbitas como GTO (Órbita de Transferência Geoestacionária) historicamente apresentaram maior dificuldade para o sucesso do pouso.
* **Massa da Carga Útil:** Existe uma correlação visível entre a massa da carga e o resultado do pouso.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Bibliotecas de Análise:** Pandas, NumPy
* **Coleta de Dados:** Requests, BeautifulSoup
* **Banco de Dados:** SQLite
* **Visualização:** Matplotlib, Seaborn, Folium
* **Machine Learning:** Scikit-learn
