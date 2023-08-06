Gradiente descendente é um algoritmo de otimização utilizado para encontrar os mínimos de uma função, especialmente para problemas de machine learning e ajuste de modelos paramétricos.

O gradiente indica em qual direção o valor de uma função cresce/decresce com maior velocidade.

Considere a equação de regressão linear:
$$Y = \beta_0+\beta_1x+\epsilon$$
O método do gradiente descendente tem como objetivo minimizar o erro quadrático médio ([[Mean Squared Error (MSE)|MSE]] - função de custo) de forma iterativa (atualizando todos os parâmetros ao mesmo tempo) e consequentemente, encontrar os melhores valores para os coeficientes da equação (nesse exemplo **B0** e **B1**).

O vetor gradiente tem uma direção e uma magnitude, a cada iteração um novo ponto é definido. Os algoritmos de gradiente descendente multiplicam o gradiente por um escalar conhecido como **taxa de aprendizado** para determinar o próximo ponto.
O valor da taxa de aprendizado é importante, se for muito pequeno pode fazer o algoritmo demorar muito para aprender e se for muito grande pode fazer o algoritmo não convergir.
![[Pasted image 20230721172614.png|center]]

De forma geral, taxas de aprendizados menores requerem um número maior de iterações, dado que pequenas variações são feitas a cada passo.