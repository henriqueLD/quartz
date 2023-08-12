---
title: "Regressão Logistica"
---
A regressão logística é uma técnica de [[Classificação]] que nos ajuda a estimar uma curva para predizer a probabilidade (entre 0 e 1) de features discretas utilizando variáveis contínuas e/ou discretas, por exemplo se um cliente está insatisfeito ou satisfeito.

O eixo y na regressão logística representa a probabilidade de uma observação pertencer a alguma classe do problema, e a curva de ajuste do modelo(roxo) nos dá a probabilidade predita da pessoa pertencer a uma determinada classificação.

Os parâmetros são estimados **maximizando a função de log verossimilhança** do modelo a partir dos dados de treino. Uma vez que temos os parâmetros definidos determinamos se uma observação faz parte de determinada classe realizando com o auxilio de um corte no valor da probabilidade (geralmente 0.5).
![Fórmula Regressão Logística](notes/images/log_reg_formula.png)

Existe a possibilidade de ajustar o ponto de corte de probabilidade para melhor adequar a predição ao problema em questão, é um método muito utilizado quando utilizamos a [[ROC-AUC]] como métrica de avaliação.

No exemplo abaixo, temos um modelo que infere se uma pessoa gosta do filme Troll 2, com a linha no ponto de corte de 50% de probabilidade.
![Exemplo Regressão Logística](notes/images/log_reg_example.png)
*Normalmente é utilizado a log verossimilhança para evitarmos problemas de erro computacional (Underflow), para em vez de multiplicarmos números muito pequenos, somamos*

Similar à [[Regressão Linear]] também é possível avaliar o desempenho da predição com um **"pseudo" R²** (McFadden's R²) e calculando o **p-valor**, além das métricas usuais para classificação

### Vantagens
- Implementação simples
- Score de probabilidade para as observações (pode ser utilizado no auxílio do problema)
- Fácil interpretabilidade de como a saída do modela foi calculada
- Não é necessário realizar *feature scaling*
- Não é necessário realizar tunning de hiperparâmetros

### Desvantagem
- Baixo desempenho com dados não lineares
- Baixo desempenho com variáveis de baixo poder preditivo (pouca significância) 
- Algoritmo não tão poderoso, normalmente superado por técnicas mais recentes e robustas
* A regressão logística sempre assume podemos atribuir uma curva em "forma de S" para predizer os dados, quando temos correlação com a resposta que oscila durante a distribuição das variáveis descritivas a condição para uso de regressão logística não é satisfeita:
	![Exemplo Viés Regressão Logística](notes/images/log_reg_bad_example.png)
	Para problemas que os dados tem relação mais complexas (não linearidade), podemos seguir com as técnicas de [[SVM]], [[Árvores de decisão - Classificação]] ou [[Rede Neural]] 
* Sensível a outlier nos dados de treinamento, principalmente na determinação dos coeficientes