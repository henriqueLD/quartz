Técnicas utilizadas para evitar *overfitting* e ajudar na seleção de variáveis de **Modelos Lineares Generalizados (GLM)**

## Lasso (L1)
O lasso adiciona uma **penalidade igual ao valor absoluto da magnitude dos coeficientes multiplicados por um lambda**
$$L1 =\sum^{n}_{i=1}(y_i - \sum^{p}_{j=1}X_{ij}\beta_j)^2 + \lambda\sum^{p}_{j=1}|B_j|$$ ou simplificando os termos:
$$L1 = SSR - \lambda*|\text{slope}|$$
![[Pasted image 20230718215505.png | center]] 
**Obs:**
- Se **lambda = 0**, temos a função de custo padrão
- Se **lambda tende a 0**, temos uma aproximação do modelo sem regularizador (pode não tratar o overfitting)
- Se **lambda tende a infinito**, temos uma aproximação de um modelo que despreza qualquer efeito das features, tende ao *underfitting* pois os **coeficientes tenderão a zero**

- Pelo fato de usar o módulo no termo de penalidade, e não elevar ao quadrado, **pode zerar os coeficientes** de variáveis pouco importantes e por conta disso **pode ser utilizado para seleção de variáveis**.
- O lasso adiciona um penalidade aos coeficientes que o modelo enfatiza demais, isso reduz o grau de *overfitting* do modelo.
- Lasso tende a se sair bem quando há poucas features significativas e a magnitude das demais features for próxima de zero.
- <mark style="background: #FF5582A6;">Lasso não lida bem com multicolinearidade</mark>, pois pode eliminar de forma aleatória variáveis correlacionadas, podendo eliminar alguma que seja relevante para o modelo.

## Ridge (L2)
Adiciona uma **penalidade igual ao quadrado da magnitude dos coeficientes multiplicado por um lambda.**
Como no lasso, adiciona uma penalidade aos coeficientes que o modelo enfatiza demais, porém, por elevar ao quadrado **não tem a capacidade de zerar coeficientes e auxiliar no feature selection**

$$L2 =\sum^{n}_{i=1}(y_i - \sum^{p}_{j=1}X_{ij}\beta_j)^2 + \lambda\sum^{p}_{j=1}B^2_j$$
ou simplificando os termos:
$$L2 = SSR - \lambda*\text{slope}^2$$
![[Pasted image 20230718215644.png | center]]
- Interessante para ser usada quando há multicolinearidade e não se pode descartar nenhuma variável
- Quando duas features são correlacionadas e seus coeficientes estão muito desproporcionais, a Ridge faz com que as features correlacionadas tenham coeficientes parecidos.
- Funciona bem se há varias features minimamente importantes.
- Por não eliminar features não importantes, pode ser ruim ao utilizar em bases com muitas features.
![[Pasted image 20230718214432.png | center]]

## Elastic Net
Elastic Net combina as características da Lasso e Ridge. **Ela reduz o impacto de diferentes features ao mesmo tempo que não elimina todas as features.**

$$\text{Elastic Net} =\sum^{n}_{i=1}(y_i - \sum^{p}_{j=1}X_{ij}\beta_j)^2 + \lambda_1\sum^{p}_{j=1}|B_j| + \lambda_2\sum^{p}_{j=1}B^2_j$$
Como funciona sendo a combinação de L1 e L2, é necessário o ajuste de 2 hiperparâmetros, porém oferece um melhor equilíbrio geral no requisito de regularizador.