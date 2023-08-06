Métrica que dá ênfase para erros por FP (casos incorretamente classificados como positivos). Responde a pergunta: **Dos exemplos classificados como positivos, quantos são realmente positivos?**
$$ Precisão = \frac{TP}{TP+FP} $$

**Desvantagens**
- Ignora completamente os erros de classificar uma amostra positiva como negativa (falso negativo)

**Vantagens**
- Métrica adequada para problemas onde existe **grave consequência para falsos positivos**
- Ao ser utilizado junto à ==Sensibilidade==, traz um insight valioso quando a **classificação positiva é mais relevante**

#classificação 