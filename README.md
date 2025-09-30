# Análise de Dados dos Participantes da 6ª COEDIPI

## 1. Visão Geral do Projeto

Este repositório contém a análise de dados completa referente ao perfil dos participantes da 6ª Conferência Estadual dos Direitos da Pessoa Idosa (COEDIPI) do Rio Grande do Norte. O objetivo deste projeto foi aplicar uma metodologia de ciência de dados para transformar os dados brutos de inscrição em insights estratégicos sobre o perfil demográfico, setorial e geográfico do público do evento.

---

## 2. Estrutura Metodológica

A análise seguiu um rigoroso fluxo de trabalho científico, composto pelas seguintes etapas:

1.  **Pré-processamento e Limpeza de Dados:**
    * Concatenação de múltiplas fontes de dados de inscrição.
    * Padronização de variáveis categóricas para garantir consistência (ex: `Femenino` -> `Feminino`).
    * Unificação de categorias redundantes para evitar duplicidade na análise (ex: `Sem ID` e `Sem Id` -> `Não Identificado`).

2.  **Enriquecimento de Dados:**
    * Criação de uma nova variável `Territorio` a partir do mapeamento dos municípios de origem dos participantes, permitindo uma análise macro-regional.

3.  **Tratamento Estatístico de Dados Ausentes:**
    * Identificação de uma alta taxa de dados geográficos ausentes (~49%).
    * Aplicação de **imputação por distribuição proporcional** para estimar a origem dos participantes não identificados, baseando-se na proporção da amostra conhecida.

4.  **Análise Estatística Descritiva e Bivariada:**
    * **Análise Univariada:** Investigação da frequência e proporção de cada variável individualmente (Perfil por Sexo, Categoria, Representação).
    * **Análise Bivariada:** Exploração da relação entre pares de variáveis através de tabelas de contingência (`pd.crosstab`) para descobrir padrões e correlações (ex: Território vs. Representação).

---

## 3. Principais Insights e Descobertas

A análise revelou diversos padrões significativos sobre o engajamento e a composição do evento:

* **Perfil Geográfico:** A participação demonstrou forte concentração no território **Agreste/Litoral Sul** (estimado em 37%), seguido por **Seridó** (17%) e **Assu/Mossoró** (17%).
* **Dinâmica Setorial por Território:** A relação entre Poder Público e Sociedade Civil não é uniforme no estado. A **Sociedade Civil** predomina na maioria das regiões, mas o território **Mato Grande** se destaca como uma exceção, com **80% de participação do Poder Público**.
* **Perfil de Participação por Setor:** A Sociedade Civil focou em enviar representantes **Titulares (58%)**, enquanto o Poder Público teve uma delegação mais diversificada, com maior proporção de **Convidados (32%)** e **Suplentes (33%)**.

---

## 4. Visualizações Chave

Os gráficos abaixo resumem os principais resultados da análise.

### Gráfico 1: Distribuição Estimada de Participantes por Território
![Distribuição por Território](img/Distribuição%20Estimada%20de%20Participantes%20por%20Território.png)

### Gráfico 2: Proporção de Representação por Território
![Proporção por Território](img/Proporção%20de%20Representação%20(Poder%20Público%20vs.%20Sociedade%20Civil)%20Por%20Território.png)

### Gráfico 3: Composição das Categorias por Setor de Representação
![Composição por Setor](img/Composição%20das%20Categorias%20por%20Tipo%20de%20Representação.png)

### Gráfico 4: Distribuição Percentual Estimada por Território
![Pizza Território](img/Distribuição%20Estimada%20por%20Território%20em%20Porcentagem.png)

---

## 5. Ferramentas e Tecnologias

* **Ambiente de Análise:** Google Colab
* **Linguagem de Programação:** Python 3
* **Bibliotecas Principais:**
    * `pandas` para manipulação e análise de dados.
    * `matplotlib` e `seaborn` para visualização de dados.
    * `gspread` para integração com Google Sheets.
