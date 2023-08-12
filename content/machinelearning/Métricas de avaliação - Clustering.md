ffComo as técnicas de clustering não são supervisionadas, não há resposta para o cálculo do **erro**, porém existem 3 tipos de critérios que podemos considerar para avaliar os agrupamentos gerados:

## Externos
Avaliam o grau de correspondência entre a estrutura dos grupos (partição ou hierarquia) <mark style="background: #ADCCFFA6;">sob avaliação e informação a priori</mark> na forma de uma solução de agrupamento esperada ou conhecida.

#### Resultado previamente conhecido:
- Reconhecimento visual dos clusters naturais (bases em duas ou três dimensões)
- Opinião de um especialista de domínio
- Bases geradas sinteticamente com distribuições conhecidas (benchmark)
- Bases de classificação sob hipótese que classes são clusters

#### Rand Index
Mede a similaridade entre dois clusters (comparação de pares de objetos).
$$RI = \frac{a+d}{a+b+c+d}$$
**a**: Número de pares que pertencem à mesma classe e ao mesmo cluster
**b**: Número de pares que pertencem à mesma classe e a clusters distintos
**c**: Número de pares que pertencem à classes distintas e mesmo cluster
**d**: Número de pares que pertencem à classes e clusters distintos
**Classes:** Grupos da partição de referência
**Clusters:** Grupos da partição sob avaliação

O Rand Index pode ser interpretado como a porcentagem de decisões corretas feitas pelo algoritmo. Varia de 0 a 1, onde 0 indica que os clusters não se assemelham em nenhum par de pontos e 1 indica que os clusters são idênticos.

#### Limitações
Viés de favorecer a comparação de partições com níveis mais elevados de granularidade (valores mais elevados ao comparar partições com mais grupos), há mesmo peso para objetos agregados (a) e separados (d), sendo que **d** tende a dominar o índice (quanto mais grupos, mais pares pertencem a grupos distintos)

## Internos
Avaliam o grau de compatibilidade enrtre a estrutura de grupos sob avaliação e os dados, usando apenas os próprios dados. 

Como o **WCSS** utilizado no método de cotovelo.

## Relativos
Avaliam qual dentre duas ou mais estruturas de grupos é melhor sob algum aspecto. Tipicamente são critérios internos capazes de quantificar a qualidade relativa. 

Como o critério da largura de Silhueta (**SWC**)

#clustering 