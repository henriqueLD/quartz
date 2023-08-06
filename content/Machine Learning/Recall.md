Também conhecida como taxa de verdadeiro positivo (TPR), dá maior ênfase para erros por FN (casos incorretamente classificados como negativos).

Responde a pergunta: Dos exemplo positivos, quantos foram classificados corretamente?
$$ Sensibilidade = \frac{TP}{TP+FN} $$
**Desvantagens**
- Não considera erros ao classificar amostras negativas como positivas (falso positivo)

**Vantagens**
- Métrica adequada para problemas onde existe **grave consequência para falsos negativos**
- Ao ser utilizado junto à Precisão, traz um insight valioso quando a **classificação positiva é mais relevante**

#classificação 