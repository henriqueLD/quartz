Métrica de avaliação utilizada para pedir a acurácia e a precisão de modelos de regressão probabilística ou até mesmo para problemas de classificação que possuem o output como probabilidade. É equivalente ao erro quadrático médio ([[Mean Squared Error (MSE)|MSE]]) aplicado às probabilidades previstas.

O Brier Score é calculado como a média dos quadrados das diferenças entre as probabilidades previstas pelo modelo e as probabilidades reais.

Seja **y** o valor real e **p** o valor previsto pelo modelo, o Brier Score é dado por:
$$Brier Score = (p-y)^2$$

O Brier Score varia entre 0 e 1, onde 0 representa uma previsão perfeita, e 1 representa a pior previsão possível.

De forma geral, deve ser menor que 0.25

<mark style="background: #FF5582A6;">Deve ser sempre aplicada à regressões probabilísticas</mark>

#regressão 