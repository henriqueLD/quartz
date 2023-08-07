Técnica utilizada em aprendizado de máquina e estatística para avaliar o desempenho de um modelo de forma mais confiável e evitar problemas de *overfitting*.

Para evitar problemas de selecionarmos um subconjunto dos dados para treinamento que podem acabar gerando um modelo que sofra de *underfit* ou *overfit*, o **Cross Validation** nos oferece a possibilidade de utilizar <mark style="background: #FF5582A6;">todos</mark> os dados para treinamento de maneira iterativa e <mark style="background: #ADCCFFA6;">avaliar a performance média do modelo.</mark>

<mark style="background: #FF5582A6;">Obs: Cuidado para não reutilizar os dados para treinamento e teste na mesma iteração para não acontecer Data Leakage.</mark>

Na Cross Validation executamos o processo de modelagem em diferentes subconjuntos dos dados para obtermos várias avaliações de desempenho do modelo.

## Benefícios
Cross-validation nos ajuda a obter uma validação mais assertiva da qualidade do modelo, porém devemos nos <mark style="background: #ADCCFFA6;">perguntar se o ganho gerado com essa técnica compensa o incremento no custo computacional gerado pelo uso de cross-validation</mark>.

Em datasets menores, o processamento adicional de executar cross-validation não será significativo, poucos dados também é a situação onde utilizar apenas a separação de train-test não é muito eficiente, <mark style="background: #ADCCFFA6;">Em resumo quando temos poucos dados, o uso de cross-validation é mais indicado.</mark>

Para datasets maiores o custo computacional extra é mais expressivo, mas no geral se o modelo não demorar muito para realizar o treinamento utilizar o cross-validation é recomendado pois tende a trazer ganhos de modelagem.

### Hold-Out
Forma mais simples de separar os dados. Define-se um percentual para cada conjunto de dados (treino, validação e teste) e cria-se as amostras. Geralmente utilizado quando há bastante dado, suficiente para que as amostram tenham significância estatística para representar a população.
![[image3_11zon_3898fc87c8.jpg|center]]

### K-Fold
Na técnica de K-fold, nós separamos o dataset original em K partes iguais e realizamos cada iteração de experimento em um subconjunto diferentes de folds.
![[1fXzJ.png|center]]

No exemplo, realizamos o treinamento no Experimento 1 usando o primeiro fold para teste e todos os outros para treinamento, então realizamos o segundo treinamento no Experimento 2 analogamente. Repetimos esse processo até que cada fold seja utilizada uma vez como teste, garantindo que usamos 100% dos dados como conjunto de teste em algum momento.

<mark style="background: #ADCCFFA6;">Ao final das K iterações, calcula-se o valor média para a métrica de avaliação, obtendo-se assim uma medida mais confiável sobre a capacidade de predição do modelo</mark>, além disso, podemos realizar uma divisão em k-fold estratificada. 


### Leave-one-out
Caso especifico do **K-Fold, sendo K igual ao número total de dados** N. Nesta abordagem são realizados N cálculos de erro, um para cada dado.
![[image2_11zon_cac3fb4270.jpg|center]]

Apesar de apresentar uma investigação completa sobre a variação do modelo, possui um alto custo computacional, sendo indicado para situações com poucos dados disponíveis.

### Out-of-sample e Out-of-time
**Out-of-sample** são dados não vistos pelo modelo, não foram utilizados no treino e serão utilizados apenas para a previsão

**Out-of-time** é um out-of-time com dados obtidos posteriormente de quando o modelo foi treinado. São amostras de dados de diferentes períodos de tempo

### Times Series Cross-Validation
Para modelos de series temporais, podemos considerar uma técnica de cross-validation que utiliza o tempo de captura dos dados para avaliar diferentes períodos de tempo e no entanto, a generalização do modelo para tempo futuro.

Como a ordem dos dados é de extrema importância para series temporais, o corte entre conjunto de treino e teste deve ser definido conforme a cronologia dos dados:
![[image6_11zon_1664949880.jpg|center]]