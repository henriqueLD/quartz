Representa a média dos erros (resíduos) elevado ao quadrado, **penaliza mais os erros com maior diferença**, dando menos importância para os erros pequenos.

$$MSE = \frac{1}{n}\sum^{n}_{i=1}(y - \hat{y})^2 = \frac{SSR}{n}$$
### Vantagens
- Função derivável, pode ser utilizada como função de custo

### Desvantagens
- Muito sensível a outliers
- Dificulta a interpretação da métrica pelo resultado ser o quadrado da magnitude real da variável de interesse

#regressão 