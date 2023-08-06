Representa o oposto do Recall, demonstra a taxa de acerto na classe negativa obtida pelo classificador.
Responde a pergunta: De todos os casos negativos, quantos foram classificados corretamente?
$$ Especificidade = \frac{TN}{TN+FP} $$
$$ FPR = 1 - especificidade $$
**Desvantagens**
- Não mede o desempenho completo do modelo
- Pode ser ilusório em problemas com **desbalanceamento de classes**

**Vantagens**
- Medida direta da capacidade do classificador **evitar falsos positivos**

#classificação 