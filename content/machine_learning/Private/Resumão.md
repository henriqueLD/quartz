### Viés e Variância
- O que é vies?
- O que é variancia
- Relaciones viés com variância
- Quais são as principais formas de se controlar viés?
- Quais são as principais formas de se controlar variância?

Viés e variância são dois dos conceitos gerais de erros em modelagem, <mark style="background: #ADCCFFA6;">viés é o tipo de erro que ocorre quando o modelo assume suposições incorreta dos dados a partir do conjunto de treino. Um modelo com alto viés está relacionado ao underfit, quando um modelo aprende muito pouco com os dados de treino.</mark>

Por outro lado, <mark style="background: #FF5582A6;">a variância reflete o quão sensível o modelo é em relação à variações dos dados de conjunto de treino. Dizemos que um modelo muito sensível possui alta variância e está relacionado ao problema de overfit, quando o modelo não generaliza bem para novos dados (teste)</mark>.

A relação entre os dois é o famoso trade-off viés e variância, normalmente na modelagem existe uma balança entre reduzir o viés e a variância. Ao passo que um modelo muito simples inicialmente começam a ganhar complexidade e flexibilidade (ao comportamento dos dados), ele tem uma redução no viés porém pode apresentar aumento na variância, indicando perda de performance para novos dados não observados, <mark style="background: #ADCCFFA6;">o objetivo do trade-off é encontrar o ponto de equilíbrio entre a redução do viés e da variância</mark>

Viés alto pode ser controlado usando modelos mais complexos e flexíveis, usando mais features (principalmente se elas apresentarem poder preditivo) e para alguns algoritmos, reduzir a penalização aplicada. Para alta variância, podemos usar modelos mais simples/com menos parâmetros, aumentar a quantidade de dados no treino, utilizar regularizadores (lasso e ridge) e também é possível utilizar técnicas de boosting

### Árvores
- Qual o critério de quebra?
- Como a saída é calculada? 
- Quais são os pontos fortes do algoritmo?
- Quais são os critérios principais de parada?
- Quais são os principais problemas encontrados no algoritmo?
- Qual a forma de regularização de uma árvore?

Árvores de decisão podem ser utilizadas tanto para problemas de regressão quanto pra de classificação e funcionam de maneira minimamente diferentes para cada tipo. É chamada de árvore pois as condições de decisão do modelo são feitas por ramificações criando "visualmente" algo muito parecido com uma raiz de uma árvore.

No geral a ramificação da árvore é feita de maneira que os dados que sobram em cada grupo após a separação sejam mais homogêneos do que antes da quebra, nas árvores de regressão verificamos a "homogeneidade" com métricas como [[MSE]] e [[MAE]], e para as árvores de classificação utilizamos [[Gini]] ou [[Entropia]] para validar as quebras.

Após serem feitas todas as quebras, nós temos folhas no nível mais baixo de cada ramificação que representa a saída do modelo, para regressão utilizamos a média da target dos dados que pertencem a folha e para classificação nós utilizamos a classe mais frequente dentro da folha (caso ela não seja pura).

Pessoal gosta muito da interpretabilidade que as árvores de decisão oferecem e a capacidade de lidar com os dados sem a necessidade de padronização ou tratamentos. Porém se não tomar cuidado com os parâmetros da árvore é bem fácil de acontecer overfitting e o algoritmo tem a tendência de gerar árvores diferentes se os dados de treino forem alterados.

Uma maneira de evitar o overfitting é definir bem os critérios de parada da árvore, que são a profundidade máxima da árvore, o tanto que você quer que ela se ramifique, número mínimo de observações dentro de um nó para que seja possível continuar dividindo e o número mínimo de observações dentro de uma folha do modelo.

Regularizadores de árvore de decisão são basicamente os critérios de parada

### Ensembles
- Quais as principais formas de ensemble?
- Cite um algoritmo de bagging e outro de boosting
- Qual problema o bagging se propõe a resolver?
- Qual problema o boosting se propõe a resolver?
- Quais são os principais parâmetros de uma random forest e quais são seus efeitos?
- Quais são os principais parâmetros de um gradient boosting e quais são seus efeitos?
- Relacione bagging a viés e variância
- Relacione boosting a viés e variância
- Cite duas implementações de boosting e explique suas diferenças

Ensemble são técnicas que vários modelos treinados para resolver um mesmo problema, combinados para ter um melhor poder preditivo. Os principais métodos de ensembles são o bagging e o boosting.

Bagging utiliza várias instâncias do "mesmo modelo" para diferentes subconjuntos dos dados originais (realizado por bootstrap) que no fim são combinados por voto da maioria (classificação) e média/mediana das predições (regressão). No geral bagging tenta tratar o problema de modelos que tendem a ter alta variância com sua combinação, e um exemplo de bagging é a Random Forest (agregação de árvores de decisões)

Boosting busca resolver o problema underfit de modelos fracos "melhorando" o modelo de forma sequencial, em cada iteração o modelo é treinado em um conjunto de dados "ajustado" dando mais importância para os erros passado, ou predizendo o erro gerado pelo modelo anterior. Exemplos de boosting são Gradient Boosting e XGBoost

Principais parâmetros da Random Forest:
- <mark style="background: #ADCCFFA6;">numero de árvores</mark>
- <mark style="background: #ADCCFFA6;">tamanho do subconjunto de features pra ser utilizado em cada árvore</mark>
- <mark style="background: #ADCCFFA6;">metodo de reamostragem das observações para cada árvore</mark>
- profundidade máxima das árvores
- número minimo de amostras (folha/nós)

Principais parâmetros do Gradient Boosting:
- <mark style="background: #ADCCFFA6;">numero de árvores</mark>
- <mark style="background: #ADCCFFA6;">tamanho do subconjunto de features pra ser utilizado em cada árvore</mark>
- <mark style="background: #ADCCFFA6;">learning rate</mark>
- profundidade máxima das arvores
- numero mínimo de amostras (folha/nós)

Tanto Gradient Boosting quanto XGBoost são técnicas de boosting que buscam melhorar um modelo weak learner predizendo os resíduos porém possuem algumas diferenças: O XGBoost possui termos regularizadores, como o gamma e o lambda para diminuir o impacto que observações individuais possuem nas previsões e melhorar a generalização do modelo, além de também possuir um sistema de poda dinamica que não depende de completar a execução da arvore antes de realizar

### Outros Modelos 
Falar de naive bayes

### Métricas de avaliação
- Principais métricas para avaliar um classificador
- Funcionamento / caso de uso / restrições
- Diferenciar métricas de poder e calibração
- Técnicas multiclasse/multilabel
- Principais métricas para avaliar um regressor
- Funcionamento/ caso de uso / restrições

#### As métricas mais comuns pra avaliar classificadores são:
##### Métricas de poder:
- Acuracia: Reflete o percentual de classes que seu modelo acerta, útil pra ter uma ideia inicial do modelo mas péssima quando os dados são muito desbalanceados
- Precisão: Mede a proporção de observações corretamente classificadas como positivas, bom quando queremos controlar os falsos positivos, <mark style="background: #ADCCFFA6;">importante para problemas de recomendação</mark>
- Recall/Sensibilidade: Mede a proporção de observações positivas classificadas corretamente, útil em problemas de saúde/medicina <mark style="background: #ADCCFFA6;">onde não queremos de maneira alguma deixar de classificar um cliente doente corretamente</mark>
- F1-Score: Média harmônica de precisão e recall, penaliza mais os valores extremos, útil quando ambas o custo dos dois erros são semelhantes.
- ROC-AUC: Gráfico entre TPR e FPR, mede quão bem o classificador separa duas classes (quando o valor se aproxima de 1) para vários pontos de corte, boa métrica para avaliar a classificação de um modelo no geral para problemas de classes desbalanceadas
##### Métricas de calibração:
- Log-Loss: Mede a discrepância entre a probabilidade observada pelo modelo e as classes reais através da log-verossimilhança

#### Para avaliar problemas multiclass:
- **Macro Average** das métricas acima: Média simples da soma das métricas dividas pelo número de classes, ex: precisão
$$Macro Avg = \frac{Precisão_{c1}+Precisão_{c2}+Precisão_{c3}}{3}$$
- **Micro Average** das métricas acima: Média considerando toda a soma individual de TP, TN, FP e FN de todas as classes do conjunto de dados, ex: precisao
$$Micro Avg = \frac{\sum_{1,2,3}TruePositive}{\sum_{1,2,3}TruePositive+\sum_{1,2,3}FalsePositive}$$
- **Weighted Average** das métricas acima: Média com pesos atribuídos pela frequência de cada classe no conjunto de dados, ex: precisão
$$Weighted Avg = \frac{Precisão_{c1}*10+Precisão_{c2}*20+Precisão_{c3}*50}{10+20+50}$$

#### Para problemas de múltiplos rótulos pra mesma observação:
- **Jaccard Score** mede a interseção das classificações sobre a união de todas as classificações, <mark style="background: #ADCCFFA6;">para problemas binários é idêntico à acurácia, mas também podemos entender o uso para problemas multiclasse e de multirotulo</mark>


#### As métricas mais comuns pra avaliar regressores são:
- **MSE** representa a média do quadrado dos resíduos, penaliza de maneira mais forte erros maiores porém é sensível a outliers, como é uma função derivável, é muito útil como função de custo
- **RMSE** representa a raiz quadrada do MSE, tem as mesmas vantagens com o adicional de manter o erro na escala original dos dados, aumentando interpretabilidade.
- **MAE** média dos erros absolutos, penaliza de acordo com a magnitude dos erros porém é menos sensível a outliers, como não é derivável possui limitações como função de custo, o ponto positivo é que facilita a interpretabilidade pois mantem a escala original dos dados.
- **R²** representa a porcentagem de ganho de predição ao usar o modelo em comparação à média da feature (diferença entre SSR da média e SSR do ajuste), desvantagem é não levar em conta a quantidade de features, que pode influenciar negativamente a métrica
- **R² Ajustado** é uma adaptação do R² com uma penalização pelo número de features, ou seja, leva em conta a quantidade de explicação fornecida pelas variáveis preditoras, útil para comparar modelos com diferentes número de parâmetros
- 
### Não supervisionado
- Quais são as principais categorias de algoritmos de clusterização
- Cite um algoritmo de cada categoria?
- Explique rapidamente os algoritmos citado


#### Clusterização Hierárquica
Constroi dendogramas para representar os clusters em uma hierarquia, onde em certo ponto de corte todos os pontos podem fazer parte de um mesmo cluster, ou cada ponto ser seu próprio cluster

##### Aglomeração
Na inicialização cada ponto é seu próprio e a cada iteração os  dois clusters mais próximos se unem para formar um novo cluster, esse processo se repete até existir apenas 1 cluster só, contendo todo o dataset

##### Divisão
O algoritmo começa considerando todos os pontos em um único cluster e a cada passo as observações com maior dissimilaridade é realocado em um cluster separado, processo se repete até existir um cluster para cada observação

As medidas utilizadas podem ser **vizinho mais proximo**, **vizinho mais distante** ou **media das distancias** 

#### Clusterização Particionais
Técnicas de agrupamento que divide os dados em um número pre definido de clusters e assim como na hierárquica, no fim do processo cada ponto pertence a apenas um cluster, o objetivo é encontrar a divisão do hiperplano que otimiza a métrica de distância intra-cluster e inter-cluster

##### K-means
estima o centroides do cluster com a media dos pontos - indicado usar distancia euclidiana
##### K-Medoids
estima centroide do cluster com a mediana - indicado usar com distancia de manhattan

#### Clusterização baseado em densidade - DBSCAN
Algoritmo de agrupamento que considera pontos muito próximos em mesmo cluster por densidade, teoricamente consegue identificar qualquer formato na distribuição dos dados olhando a proximidade entre pontos

funciona com os parâmetros de **pontos minimos** e **tamanho do raio** para classificar os pontos do dataset e depois atribuir em algum cluster

#### Clusterização baseado em mistura de modelos
Cluster definido em uma abordagem probabilística, cada modelo representa um cluster e é ajustado aos dados usando expectation-maximization, permitindo medir a incerteza dos agrupamentos gerados.

##### GMM
