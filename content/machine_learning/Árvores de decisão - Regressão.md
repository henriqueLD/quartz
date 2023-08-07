Árvores de decisão são algoritmos supervisionados não paramétricos que realizam a regressão por meio da construção de uma estrutura em forma de árvore. Cada nó interno da árvore representa uma condição sobre uma ou mais características, enquanto **as folhas** representam as classes finais preditas.

A árvore começa com um **nó raiz**, onde a seleção do atribute é feita com base em algum critério, como o [[Mean Squared Error (MSE)|MSE]] ou [[Mean Absolute Error (MAE)|MAE]]. O atributo selecionado é aquele que melhor divide os dados e resulta na maior redução do erro de regressão.

As árvores de regressão tendem a fazer uma boa predição porque cada **folha** se torna um cluster de dados no gráfico e a **predição se torna a média dos pontos que então dentro da folha**:

![[Pasted image 20230719215921.png|center]]

Os pontos de ramificação são definidos testando todas as médias de dois pontos e verificando qual corte reduz com mais eficiência o SSR:

![[Pasted image 20230719221622.png|center]]
No nosso exemplo, Dose < 14.5 foi o ponto escolhido, no nó à esquerda sobraram apenas 6 pontos, na teoria seria possível dividir ainda mais esses dados, <mark style="background: #FF5582A6;">porém seguir com um número tão baixo de pontos faz com que seja muito provável que ocorra overfitting do modelo</mark>.

Uma maneira simples de evitar esse problema é definir um valor mínimo necessário na folha para continuar a ramificação, 20 geralmente é um valor razoável, porém <mark style="background: #ADCCFFA6;">no exemplo usaremos 7 observações como valor mínimo.</mark>

Seguindo o mesmo processo e considerando o critério mínimo de observações definido acima, chegaremos à seguinte árvore:

![[Pasted image 20230719222315.png|center]]

<mark style="background: #ADCCFFA6;">Os ensembles como Random Forest e XGBoost também podem ser utilizados em problemas de regressão</mark>

### Vantagens
- Não é necessário normalizar/padronizar os dados
- Fácil interpretabilidade e de fácil visualização
- Útil para saber descobrir a *feature importance* (seleção de variáveis)
- Features com baixa significância não afetam a predição (porém aumenta o custo computacional)

### Desvantagem
- Fácil de acontecer *overfitting* se não cuidar dos hiperparâmetros
- Sensível aos dados: variação nas amostras podem gerar árvores bem diferentes
- Difícil captura de relações complexas nos dados

#regressão 