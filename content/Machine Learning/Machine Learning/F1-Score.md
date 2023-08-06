Média harmônica entre Precisão e Sensibilidade. Uma boa métrica para ser utilizada em conjunto de dados com classes desbalanceadas.
$$ F1 = 2 *\frac{Precisão *Recall}{Precisão + Recall} $$
Se a precisão ou recall forem baixos, o F1 também será baixo. Ou seja, um modelo com alto F1 é capaz de acertar suas predições (precisão alta) e também recuperar os exemplos da classe de interesse (recall alto).

**Desvantagens**
- Não indicado para problemas onde uma das métricas utilizadas é de maior interesse (precisão ou recall), pois **assume a mesma importância para ambas**
- Não considera as classificações dos TN

**Vantagens**
- Métrica adequada para problemas com **classes balanceadas**
- Combina precisão e recall em uma métrica única
- Pode ser utilizado para comparar modelos classificadores

#classificação 