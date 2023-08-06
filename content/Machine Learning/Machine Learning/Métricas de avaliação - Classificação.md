## Introdução
As seguintes métricas servem para quantificar o desempenho e a qualidade das previsões feitas por modelos classificadores. Em resumo são usadas para avaliar quão bem um modelo está solucionando o problema em questão, comparar diferentes modelos e selecionar o mais apropriado para a tarefa

### [[Matriz de confusão]]
Resume a volumetria todos os possíveis resultados de predição modelo de classificação

### [[Acurácia]]
Proporção de classificações corretamente classificadas pelo modelo de classificação

### [[Precision]]
AKA: Precisão
Proporção de observações ==corretamente classificadas como positivas==

### [[Recall]]
AKA: Sensibilidade
Proporção de ==observações positivas classificadas corretamente==

### [[F1-Score]]
Combinação de [[Precision]] e [[Recall]], penalizando sempre pela métrica de menor valor

### [[Specificity]]
AKA: Especificidade
Proporção de ==observações negativas classificadas corretamente==

### [[ROC-AUC]]
Curva criada a partir da TPR([[Recall]]) e FPR(1-[[Specificity]])

### [[Gini]]
Medida de dissimilaridade variando de 0 a 1, onde 1 representa dissimilaridade máxima

### [[Log-Loss]]
Mede a discrepância entre as probabilidades previstas pelo modelo de classificação e as classes reais

#classificação 