Algoritmos de clusterização como o K-Means apesar de simples entendimento e fácil explicação, possuem limitações como a falta de flexibilidade no formato dos clusters (considera formatos circulares) e a falta de uma medida probabilística de atribuição, ou seja, um elemento é atribuído apenas a um cluster e não se tem ideia da probabilidade dele pertencer a um outro cluster.

<mark style="background: #ADCCFFA6;">Com o GMM é possível medir a incerteza na atribuição do cluster,</mark> incorporando as distância de cada ponto a todos os centroides, e a <mark style="background: #ADCCFFA6;">forma dos clusters passam a ser elipses</mark>, podendo se ajustar melhor aos dados.

O modelo GMM tenta encontrar uma mistura de distribuições gaussianas de probabilidades multidimensionais que melhor modelem um conjunto de dados de entrada. Como ele trabalha com probabilidades, é possível saber qual a probabilidade de um elemento pertencer a cada cluster.

![[Pasted image 20230722161112.png|center]]

Cada uma das K gaussianas possuem os seguintes parâmetros:
- Uma **média** que define seu centro.
- Uma **matriz de covariância** que define sua largura.
- Uma função de probabilidade que define quão grande a gaussiana será.
![[Pasted image 20230722161411.png|center]]

#clustering 