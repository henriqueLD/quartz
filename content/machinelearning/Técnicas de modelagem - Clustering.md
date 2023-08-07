
## Agrupamento Não Hierárquico
Técnica de aprendizado não supervisionado em que o objetivo é encontrar nos dados uma estrutura de agrupamento natural, agrupando indivíduos com base na similaridade ou distâncias (dissimilaridades).
- **Partição rígida**: Todos os pontos do dataset possuem um cluster, sendo que nenhum cluster fica vazio e não existe intersecção entre eles.
- **Objetivo:** <mark style="background: #ADCCFFA6;">Minimizar distância intra-cluster</mark> (pontos dentro de um mesmo cluster estão pertos um dos outros) e <mark style="background: #ADCCFFA6;">maximizar a distância inter-cluster</mark> (pontos em diferentes cluster estão distantes)

#### Passo a passo geral:
1. Escolher o número **k** de clusters
	1. Pode ser utilizado métodos como cotovelo, silhueta, etc
2. Selecionar os centroides iniciais (não necessariamente pontos presentes no dataset)
		A inicialização pode gerar clusters diferentes (<mark style="background: #FF5582A6;">problema de sensibilidade da inicialização</mark>). Maneira de lidar com esse problema são:
		**Repetição:** Repetir o algoritmo e a inicialização diversas vezes e escolher a clusterização que tiver menor distância intra-cluster e maior distância inter-cluster
		**K++ (K-means ++, K-medians ++, etc):** Técnica inteligente para inicialização dos centroides em que o 1º é escolhido de forma aleatória a partir dos dados e os demais centroides são escolhidos a partir dos pontos restantes com probabilidade proporcional à distância ao quadrado do centroide mais próximo
3. Atribuir para cada ponto o cluster do centroide mais próximo
4. Avaliar e recalcular a nova posição dos centroides de cada cluster
5. Repetir os passos 3 e 4 até atingir a convergência (elementos não trocam mais de grupos após recalculo de centroides)

##### [[K-Means]]

##### [[K-Medians]]

##### [[K-Modes]]

##### [[K-Medoids]]

##### [[K-Prototypes]]

#### Definição do número K de clusters

##### Método do cotovelo
Consiste em traçar uma curva do WCSS (Within-Cluster Sum of Square ou soma do quadrado das distâncias intra-cluster) e o número de clusters. O valor de k a ser escolhido será aquele em que a variação do WCSS torna-se menos discrepante:
![[Pasted image 20230721235857.png|center]]
**Passo a passo:**
1. Realizar a clusterização para diferentes valores de K (ex: 1 até 10)
2. Para cada K, calcular a soma total dos quadrados das distâncias intra-cluster (inercia)
3. Plotar a curva de WCSS contra K
4. O local do **cotovelo** no gráfico indicará o número apropriado de clusters
![[Pasted image 20230722000449.png|center]]

##### Método da Silhueta
Consiste em plotar o valor médio do coeficiente de silhueta para diferentes valores de K. O número ótimo de clusters será aquele que tiver o valor máximo da silhueta:
![[Pasted image 20230722000349.png|center]]
O coeficiente de silhueta mede a qualidade da clusterização, ou seja, ele determina quão bem cada ponto está dentro do seu cluster. Um valor alto indica uma boa clusterização.
![[Pasted image 20230722000506.png|center]]

O coeficiente nos diz se os pontos estão corretamente atribuídos aos seus clusters:
**S(i) próximo de 0:** o ponto encontra-se entre dois clusters
**S(i) próximo de -1:** o ponto teria sido melhor classificado em outro cluster
**S(i) próximo de 1:** o ponto foi agrupado corretamente

## Agrupamento por Densidade
#### [[DBSCAN]]
O algoritmo de clusterização não hierárquico que considera os clusters como regiões de maior/menor densidade, muito útil para distribuições de dados que não seguem um padrão esférico/convexo.

## Agrupamento Hierárquico
Técnica de clusterização que baseia-se no tamanho e distância (medida de dissimilaridade/similaridade) dos dados em um conjunto. 

Para realizar a clusterização é necessário definir a métrica de distância a ser utilizada (euclidiana, manhattan, etc) e um critério de ligação. Essa técnica produz de 1 a N clusters, sendo N o número de observações presentes no dataset, ocorrendo por processo de **aglomeração (bottom up)** ou por **divisão (top down)**.

**Vantagens:** Fácil implementação, produz um dendograma (facilita no entendimento de como a clusterização foi realizada), técnica menos sensível a outliers
**Desvantagens:** As vezes pode ser difícil identificar um número ideal de clusters, mesmo com a ajuda do dendograma. Geralmente requer um maior tempo para o algoritmo terminar de rodar.

##### [[Aglomeração (Bottom Up)]]

##### [[Divisão (Top Down)]]

![[Pasted image 20230722154126.png|center]]

### Critérios de ligação
![[Pasted image 20230722154335.png|center]]

##### Single Linkage
Técnica de **vizinho mais próximo**, é a menor distância entre dois pontos dentro de dois clusters. As vezes pode produzir clusters onde as observações em diferentes clusters estão mais próximas do que as observações dentro de seu próprio cluster.

Esses clusters podem aparecer de forma espalha e no <mark style="background: #FF5582A6;">geral são sensíveis a outliers</mark>.

##### Complete Linkage
Técnica de **vizinho mais distante**, é a maior distância entre dois pontos em dois clusters. Geralmente produz clusters mais compactos do que o método de **single linkage**, mas esses clusters podem acabar ficando muito próximos.

Uma das métricas mais populares e são <mark style="background: #FFB86CA6;">menos sensíveis a outliers</mark>.

##### Average Linkage
A distância entre cada par de pontos em cada cluster é somada e dividida pelo número de pares para ser obter uma distância média. 

Tão popular quanto **complete linkage** porém <mark style="background: #BBFABBA6;">muito menos sensível a outliers</mark>.

![[Pasted image 20230722154935.png|center]]

<mark style="background: #ADCCFFA6;">Dependendo de como os dados estão distribuidos, o critério de ligação escolhido pode alterar muito a agrupamento gerado.</mark>

## Agrupamento por Distribuição Probabilística
#### [[Gaussian Mixture Models (GMM)]]
Algoritmo de clusterização que é mais flexível no formato dos clusters e nos fornece uma medida probabilística de atribuição a um determinado cluster



#todo 
estudar inicialização K++

#clustering 