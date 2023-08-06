Representa a porcentagem de ganho de predição por usar o modelo, quando comparado apenas a média dos dados.

$$R^2=\frac{SSR(mean)-SSR(fit)}{SSR(mean)}$$
<mark style="background: #ADCCFFA6;">O R² também pode ser calculado com o MSE no lugar do SSR</mark>.

Quanto mais perto o R² se aproximar de 1, melhor o modelo de ajusta ao dados de treinamento em comparação com a média dos valores.

Para verificar o cálculo, vamos seguir com um exemplo que prediz altura com base no peso de uma pessoa:

Começamos calculando a soma do resíduos ao quadrado da média:
![[Pasted image 20230718225252.png|center]]
$$SSR(mean) = (1.2-1.9)^2 +(2.2-1.9)^2 +(1.4-1.9)^2 +(2.7-1.9)^2 +(2.3-1.9)^2 =1.6$$
Em seguida, calculamos a soma dos resíduos ao quadrado do modelo ajustado:
![[Pasted image 20230718225552.png|center]]
$$SSR(fit) = (1.2-1.1)^2 +(2.2-1.8)^2 +(1.4-1.9)^2 +(2.7-2.4)^2 +(2.3-2.5)^2 =0.5$$
Agora temos todos os componentes necessários para o cálculo da métrica:
$$R^2=\frac{SSR(mean)-SSR(fit)}{SSR(mean)}=\frac{1.6-0.5}{1.6}=0.7$$
O R² ser 0.7 indica que tivemos uma **redução de 70% no tamanho dos resíduos** por usar a reta ajustada pelo modelo.

### Relação com Correlação de Pearson
A correlação de Pearson pode ser calculada a partir do R² com a seguinte relação:
$$R^2 = r^2 =\rho^2$$
### R² ajustado



#todo 
R² ajustado
relacionar R² com p-valor

#regressão 