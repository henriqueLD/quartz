Avalia a performance de um classificador para diferentes limiares de classificação, relacionando a Taxa de Falso Positivo (FPR) e a Taxa de Verdadeiro Positivo (TPR)
$$TPR = \frac{TP}{TP+FN}; FPR = \frac{FP}{FP+TN}$$
![[Pasted image 20230712201216.png]]
-  Quanto mais próxima a curva estiver do canto superior esquerdo melhor é a predição do modelo, uma vez que sua TPR = 100% com FPR = 0%
-  Linha tracejada indica qual seria a curva que atribui as classes aleatoriamente
-  Área sob a curva (AUC) pode ser usada como métrica do modelo
-  ==Métrica pouco sensível a problemas de classes desbalanceadas==

#classificação 