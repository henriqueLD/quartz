Entropia pode ser definida como o grau de impureza de um conjunto. Se a amostra for completamente **homogênea** com relação as classes de um problema, **a entropia é zero**. Se a amostra for **igualmente dividida entre as classes, tem entropia igual a 1**. 

$$Entropia = -\sum_i P_i * log_2P_i$$
A escolha do atributo para um nó é dada pelo **ganho de informação**, que é definido como a redução na entropia esperada dado cada categoria do atributo.

$$Ganho(A) = Entropia(S) - \sum^{k}_{i=1}P_i*Entropia(A_i)$$
$$
\begin{aligned}
  &Entropia(S): \text{Entropia da amostra no nó pai} \\
  &Entropia(A_i): \text{Entropia na categoria "i" do atributo "A"} \\
  &P_i: \text{Proporção dos dados na categoria "i" do atributo "A" (comparado com o total de amostras)}
\end{aligned}
$$


#classificação 