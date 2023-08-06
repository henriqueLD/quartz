Representa a raiz quadrada da média dos erros (resíduos) elevado ao quadrado (raiz do [[Mean Squared Error (MSE)|MSE]]), **penaliza mais os erros com maior diferença**, dando menos importância para os erros pequeno.
$$RMSE = \sqrt{\frac{1}{n}\sum^{n}_{i=1}(y - \hat{y})^2}$$
### Vantagens
- Função derivável, pode ser utilizada como função de custo
- Métrica de fácil interpretação, medida sai na mesma escala original dos dados de interesse
### Desvantagens
- Muito sensível a outliers

#regressão 