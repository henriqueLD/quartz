Técnica utilizada em que múltiplos modelos (normalmente chamados de **modelos fracos**) são treinados para resolver o mesmo problema e são combinados posteriormente para gerar resultados melhores.

Os modelos fracos (ou aprendizes fracos/modelos base) são aqueles utilizados como blocos para a construção de modelo mais complexos. Na maioria dos casos estes modelos não performam tão bem sozinhos pois podem ter um alto viés e/ou alta variância. 

Logo a ideia de **Ensemble** é reduzir viés e/ou variância dos modelos fracos, combinando vários deles com o objetivo de criar um único modelo preditivo forte que atinge melhores performances.

De forma geral, podemos dizer que **Bagging** irá focar principalmente em obter um modelo de ensemble com menos variância do que seus modelos base, enquanto **Boosting** e **Stacking** principalmente irão tentar produzir modelos fortes com menos viés dos que seus modelos base.

## Bagging
Também conhecido como **Bootstrap Aggregating**, essa técnica se baseia na ideia de combinar o resultado de diferentes modelos do mesmo algoritmo que foram ajustados a amostras diferentes do conjunto de dados original. <mark style="background: #ADCCFFA6;">Tal combinação normalmente é feita de forma uniforme, ou seja, o voto de cada modelo possui o mesmo peso.</mark>

Essa técnica funciona por reduzir a variabilidade aleatória e considerar o voto majoritário, especialmente em modelos instáveis como as de arvore de decisão.

No *bagging* <mark style="background: #ADCCFFA6;">várias instâncias do mesmo modelo base são treinadas em paralelo (de forma independente) em diferentes amostragens dos dados</mark> e depois são <mark style="background: #ADCCFFA6;">agregados em um processo "médio"</mark>. Como o objetivo é obter um <mark style="background: #FF5582A6;">modelo com menor variância</mark>, é por esse motivo que o <mark style="background: #FF5582A6;">modelo base escolhido deve ter baixo viés e alta variância</mark>

![[Pasted image 20230717222349.png | center]]

[[Random Forest - Classificação |Random Forest]] é um caso especial de *bagging* com árvore de decisão. Além de cada árvore fazer uma amostragem nos dados, também faz uma amostragem nas variáveis explicativas a serem utilizadas. Dessa forma o modelo dá liberdade para destacar a importância de features diferentes, que em um bagging simples não apareceriam

## Boosting
Ensemble que reamostra os casos com base no erro do modelo. Ao identificar quais exemplos de treinamento um modelo do conjunto ensemble errou, na próxima reamostragem as observações previstas de forma errada terão mais importância, desta forma os erros serão corrigidos em cada iteração. 

Existem vários algoritmos de Boosting, sendo os mais famosos: [[AdaBoost]], [[Gradient Boost]], [[XGBoost]], [[LightGBM]], [[CatBoost]]

Ao contrária do *bagging* que tem como objetivo reduzir a variância, Boosting é uma técnica que <mark style="background: #ADCCFFA6;">consiste em ajustar de forma sequencial vários modelos fraco</mark>s, de forma que uma importância maior é dada para as observações no dataset que tiveram maior erro no modelo anterior da sequência. De forma intuitiva, cada novo modelo irá focar nas observações mais difíceis, dessa forma <mark style="background: #ADCCFFA6;">obtemos no final do processo um modelo forte com menor viés (mesmo assim é possível perceber que o boosting também pode ter o efeito de reduzir a variância)</mark>.

![[Pasted image 20230717223104.png | center]]

## Stacking
Geralmente considera diferentes tipos de modelos fracos (algoritmos diferentes), aprende eles de forma paralela e os combina através do treino de um "meta-modelo", para ter uma predição final baseada na predição dos modelos fracos.

Neste métodos os modelos fracos são ajustados de forma independente e o meta-modelo é treinado em cima das predições obtidas dos modelos fracos.

Assumindo que queremos ajustar um *stacking* composto de "L" modelos fracos, então devemos:
- Dividir a base de treino em duas partes
- Escolher os "L" modelos fracos e ajusta-los em uma das  partes divididas (1ª parte)
- Para cada modelo fraco devemos fazer a predição para as observações contidas na outra parte do dataset (2ª parte)
- Ajuste o meta-modelo na 2ª parte do dataset dividido, usando as predições obtidas pelos modelos fracos como input
![[Pasted image 20230717223749.png | center]]
![[Pasted image 20230717223808.png | center]]

