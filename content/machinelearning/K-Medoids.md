A ideia desse algoritmo é fazer com que os centroides finais sejam pontos verdadeiros, ou seja, dados que de fato estão presentes no dataset. O principal objetivo é tornar os centroides interpretáveis, assim aumentando a interpretabilidade do cluster.

O passo a passo se difere na atualização dos centroides: <mark style="background: #ADCCFFA6;">ao invés de usar a média/mediana de todos os pontos do cluster, é escolhido o ponto com menor valor de custo (objeto que se encontra mais próximo do centro de gravidade do cluster)</mark>

#clustering