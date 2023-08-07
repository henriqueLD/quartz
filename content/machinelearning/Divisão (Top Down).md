O algoritmo se inicia com um único cluster, contendo todo o dataset. A observação com maior dissimilaridade (mais distante do cluster a partir de uma determina métrica) é realocado no seu próprio cluster, as observações no cluster antigo que estiverem próximas deste novo cluster serão realocadas nele.

Esse processo se repete até que cada observação se encontre em seu próprio cluster.

#clustering 