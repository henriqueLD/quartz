---
title: "Classificação"
---
Modelos de classificação são métodos de machine learning supervisionados, onde os modelos buscam predizer um rótulo de uma observação de entrada. 

Para classificação, o treino dos modelos é realizado a partir de um conjunto de dados e então avaliamos o desempenho do modelo em um novo conjunto de dados que não foi utilizando durante a etapa de treinamento e então podemos seguir para predições de novas amostras.

![Exemplo Classificação](notes/images/example_classification.png)

Existem quatro principais tarefas de classificação: **binária**, **multi-classe**, **multi-rótulo** e **desbalanceadas**

### Classificação Binária
Em classificação binária temos o interesse de classificar um dado entre duas classes mutuamente exclusivas. Os dados de treino são rotulados de forma binária: 

![Exemplo Classificação Binária](notes/images/example_binary_classification.png)

[[machinelearning/Regressão Logistica|Regressão Logística]] e [[machinelearning/SVM|SVM]] são algoritmos desenhados originalmente para solucionar problemas binários de classificação e tendem a desempenhar quando os dados não possuem um comportamento muito complexo.

Porém os algoritmos mais comumente utilizados hoje em dia também conseguem resolver esses problemas, como: 
- [[machinelearning/Random Forest - Classificação|Random Forest]]
- [[machinelearning/Naive Bayes|Naive Bayes]]
- [[machinelearning/Gradient Boost|Gradient Boosting]]

### Classificação Multiclasse
Para classificação multiclasses, existem pelo **menos três classes mutuamente exclusivas** que temos interesse de rotular uma nova informação, analogamente à classificação binária:

![Exemplo Classificação Multi-Classe](notes/images/example_multiclass_classification.png)

Os algoritmos de citados anteriormente podem ser utilizados para os problemas de classificação multiclasses, pois não são nada mais que uma generalização dos problemas binários.

> [!tip] Dica 
>
> É possível utilizar técnicas como a One-vs-One ou One-vs-Rest para adaptar problemas multiclasses em binários para tornar viável a utilização de [[machinelearning/Regressão Logistica|Regressão Logística]] e [[machinelearning/SVM|SVM]]

#### One-vs-One
Essa técnica consiste em treinar um classificador para cada par de rótulos, se tivermos um problema com 3 rótulos, teremos 3 pares de rótulos e por consequência 3 classificadores, conforme exemplo:

![Exemplo One-vs-One](notes/images/one-vs-one.png)

Onde cada modelo é treinado com um conjunto de dados binário e a predição final é dado pelo **voto majoritário entre todos os classificadores**.

#### One-vs-Rest
Diferente do one-vs-one, aqui consideramos que cada modelo testa cada rótulo contra a combinação dos demais, em geral para **N** rótulos, teremos N classificadores binários.

![Exemplo One-vs-Rest](notes/images/one-vs-rest.png)

As predições de cada modelo geralmente ocorrem de maneira probabilística e a predição final é o modelo do rótulo com maior probabilidade.


[[Técnicas de modelagem - Classificação]]

[[Métricas de avaliação - Classificação]]