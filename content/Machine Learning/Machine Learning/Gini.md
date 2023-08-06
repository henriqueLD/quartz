Indica o poder discriminatório do modelo, está relacionado com a curva ROC-AUC
$$Gini = 2*AUC-1$$
![[Pasted image 20230712202438.png]]
Ele varia de 0 a 1, onde 0 representa igualdade perfeita (ou seja, todas as observações têm o mesmo valor) e 1 representa desigualdade máxima (ou seja, uma única observação detém todo o valor)

### Gini como métrica de ganho de informação (Árvore)
Mede o grau de heterogeneidade dos dados, logo pode ser usado para medir a impureza de um **nó**
$$Gini = 1 - \sum^{c}_{i=1}P_{i}^{2}$$
$$\text{onde, } P_{i}^{2}: \text{Frequência relativa de cada classe(c) em cada nó (em probabilidade)}$$
Quando o índice é igual a **zero, indica que o nó é puro**. Por outro lado, quanto mais se aproxima de 1 mais evidências temos de que o nó é **impuro (existem diversas classes dentro da mesma folha)**

Em classificações binárias, utilizar Gini tende a isolar num ramo os registros que representam a classe mais frequente.

#classificação 