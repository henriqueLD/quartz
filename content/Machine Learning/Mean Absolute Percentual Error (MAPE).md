Transformação do [[Mean Absolute Error (MAE)|MAE]] que representa a média do erro percentual absoluto do modelo de regressão, **penalizando mais os erros com maiores magnitudes**, dando menos importância para os erros pequenos.

$$MAPE = \frac{100}{n}\sum^{n}_{i=1}\frac{|y-\hat{y}|}{y}$$
### Vantagens
- Métrica de fácil interpretação, pois representa o percentual de erro que o modelo nos retorna
- Pouco sensível à outliers

### Desvantagens
- Função da métrica não é diferenciável, não pode ser utilizada como função de custo
#regressão 