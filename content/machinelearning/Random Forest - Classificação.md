---
title: "Random Forest - Classificação"
---
Random Forest é um algoritmo que realiza o [[Ensemble]] de várias [[Árvores de decisão - Classificação|Árvores de decisão]] para realizar classificação em problemas complexos. Ele utiliza um conjunto de árvores de decisão aleatórias e faz **predição com base em uma votação majoritária das árvores individuais**

Utilizando **Bagging** para criar diferentes conjuntos de treinamento a partir do conjunto de dados original. Cada conjunto de treinamento é obtido através de uma amostragem aleatória com reposição, o que permite que exemplos se repitam ou sejam omitidos em cada conjunto.

Para cada conjunto de treinamento é construída uma [[Árvores de decisão - Classificação|Árvore de decisão]]. Durante a construção o algoritmo seleciona um subconjunto aleatório de features a partir do conjunto total de características. Isso ajuda a reduzir a correção entre as árvores e aumentar a diversidade do conjunto de árvores.

Após a construção de todas árvores, a Random Forest faz a classificação de um exemplo de teste através de uma votação majoritária. Cada árvore dá o seu voto e a classe mais votada é considerada a classe final predita.

Também pode ser utilizada para fornecer uma medida de importância de cada feature, calculando a **redução média do índice Gini** ou do **ganho de informação** ao usar cada característica para dividir os nós das árvores, ajudando a identificar quais são as features mais importantes para o problema

Em resumo Random Forest é muito utilizado por sua capacidade de lidar com dados complexos, grande quantidade de features e tendência de *overfitting*. Ele combina as previsões de várias árvores de decisão (modelos fracos) para **reduzir a variância** e **melhorar a precisão geral** do modelo.

### Vantagens
- Erro reduzido (em comparação a uma árvore de decisão)
- Boa performance em datasets desbalanceados
- Pode trabalhar com conjunto de dados muito grandes
- Lida bem com valores nulos
- Não tem problema tão grande de *overfitting*, pela utilização de várias árvores aleatórias
- Não sensível a outliers
- Útil para extrair o feature importance

### Desvantagem
- Features precisam ter importância para predição, se não pode prejudicar o algoritmo
- Predições das árvores não devem estar correlacionadas
- Abre mão da interpretabilidade/processo de tomada de decisão pela performance
