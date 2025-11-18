# Predição da Qualidade do Vinho com Random Forest

## Visão Geral do Projeto
Este projeto tem como objetivo prever a qualidade de vinhos tintos com base em suas propriedades químicas, utilizando o algoritmo Random Forest. O conjunto de dados utilizado contém diversas características que descrevem a composição química do vinho, e a variável alvo é a pontuação de qualidade do vinho, variando de 0 a 10.

## Conjunto de Dados
O conjunto de dados utilizado neste projeto é o `winequality-red.csv`, que contém as seguintes características:

### Características:
- **Fixed Acidity**: Acidez fixa do vinho.
- **Volatile Acidity**: Nível de acidez volátil.
- **Citric Acid**: Quantidade de ácido cítrico.
- **Residual Sugar**: Teor de açúcar residual.
- **Chlorides**: Nível de cloretos.
- **Free Sulfur Dioxide**: Teor de dióxido de enxofre livre.
- **Total Sulfur Dioxide**: Teor total de dióxido de enxofre.
- **Density**: Densidade do vinho.
- **pH**: Nível de pH.
- **Sulphates**: Teor de sulfatos.
- **Alcohol**: Teor alcoólico.

### Alvo:
- **Quality**: Pontuação sensorial da qualidade do vinho (0 a 10).

## Etapas do Projeto

### 1. Pré-processamento dos Dados
- Verificação dos tipos de dados e checagem de valores ausentes ou duplicados.
- Remoção de linhas duplicadas e confirmação de que não há valores ausentes.

### 2. Análise Exploratória de Dados (EDA)
- Utilização da função `describe()` para identificar outliers e entender a distribuição dos dados.
- Análise do balanceamento da variável alvo `quality`.
- Criação de uma matriz de correlação para identificar as características mais relevantes para a previsão.
- Seleção de `alcohol` (correlação positiva) e `volatile acidity` (correlação negativa) como as características mais importantes.

### 3. Preparação dos Dados
- Divisão do conjunto de dados em características (`X`) e alvo (`y`).
- Divisão adicional dos dados em conjuntos de treino e teste.

### 4. Treinamento e Avaliação do Modelo
- Treinamento de um Classificador Random Forest nos dados de treino.
- Avaliação do modelo utilizando acurácia, relatório de classificação e matriz de confusão.
- Observação de que o modelo teve dificuldades com classes desbalanceadas, apresentando bom desempenho apenas nas classes majoritárias (5 e 6).

### 5. Otimização de Hiperparâmetros
- Utilização do `RandomizedSearchCV` para otimizar hiperparâmetros como `n_estimators`, `max_depth` e `min_samples_split`.
- Treinamento de um novo modelo com os melhores parâmetros encontrados.
- O modelo ajustado apresentou pequenas melhorias na previsão de classes minoritárias, mas manteve uma acurácia geral semelhante.

### 6. Recomendações para Melhorias
- Lidar com o desbalanceamento de classes utilizando técnicas como SMOTE.
- Experimentar outros modelos, como Regressão Logística.
- Tratar outliers para melhorar as correlações entre as características e o desempenho do modelo.

## Resultados
- O modelo Random Forest inicial alcançou uma acurácia de ~55%.
- Após a otimização de hiperparâmetros, o modelo apresentou melhor generalização, prevendo mais classes além das majoritárias.

## Ferramentas e Bibliotecas
- **Python**: Linguagem de programação utilizada.
- **Bibliotecas**:
  - `pandas` para manipulação de dados.
  - `matplotlib` e `seaborn` para visualização de dados.
  - `scikit-learn` para aprendizado de máquina e avaliação.

## Como Executar o Projeto
1. Instale as dependências necessárias utilizando o arquivo `requirements.txt`:
   ```bash
   pip install -r requirements.txt
   ```
2. Abra o Jupyter Notebook `Cientista de Dados Pratique M32.ipynb`.
3. Execute as células sequencialmente para pré-processar os dados, treinar o modelo e avaliar os resultados.

## Estrutura de Arquivos
```
.
├── Cientista de Dados Pratique M32.ipynb  # Jupyter Notebook com o código do projeto
├── requirements.txt                      # Dependências do projeto
├── winequality-red.csv                   # Conjunto de dados utilizado para treino e teste
└── README.md                             # Documentação do projeto
```

## Autor
- **Flaviano Jr**

## Licença
Este projeto é para fins educacionais e não inclui uma licença específica.