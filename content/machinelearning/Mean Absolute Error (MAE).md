Representa a média do erro absoluto do modelo de regressão, **penaliza mais os erros com maiores magnitudes**, dando menos importância para os erros pequenos.

$$MAE = \frac{1}{n}\sum^{n}_{i=1}|y-\hat{y}|$$
### Vantagens
- Métrica de fácil interpretação, medida sai na mesma escala original dos dados de interesse
- Pouco sensível à outliers

### Desvantagens
- Função da métrica não é diferenciável, não pode ser utilizada como função de custo

#regressão 