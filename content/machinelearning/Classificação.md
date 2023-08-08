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

> [!warning] Warning 
>
> Mesmo que [[machinelearning/Regressão Logistica|Regressão Logística]] e [[machinelearning/SVM|SVM]]









[[Técnicas de modelagem - Classificação]]

[[Métricas de avaliação - Classificação]]