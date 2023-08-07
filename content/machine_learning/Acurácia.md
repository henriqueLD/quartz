Representa a proporção de classificações corretas **(independente da classe)** em relação ao total de amostras observadas
$$ Acurácia = \frac{TP+TN}{TP+TN+FP+FN} $$
**Desvantagens**
- Pode ser ilusório para classificações de problemas com **desbalanceamento de classes** (acurácia elevada mesmo com performance ruim do classificador)
- Atribui o mesmo peso para ambos os erros, (alguns problemas tem maior ganho ao minimizar FP ou FN)

**Vantagens**
- Métrica altamente interpretável
- Pode ser utilizada para comparar dois modelos
- Medida útil para problemas de **classes balanceadas** onde a importância de cada classificação é semelhante (TP, TN)

#classificação 