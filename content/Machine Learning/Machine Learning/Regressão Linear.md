Tipo de regressão em que os coeficientes podem ser expressos por uma combinação linear de elementos (b0, b1, b2, ...), os quais são justamente os valores que não sabemos.

### Simples
Só temos uma variável independente:
$$Y = \beta_0+\beta_1X$$
### Múltipla
Temos mais de 1 variável independentes para explicar Y
$$Y = \beta_0+\beta_1X_1+\beta_2X_2+...+\beta_nX_n$$
### Polinomial
Formada por uma equação polinomial 
$$Y = \beta_0+\beta_1X+\beta_2X^2+...+\beta_nX^n$$
## Hipóteses consideradas
- **Variáveis Explicativas**:
	- **Linearidade**: a variável resposta y deve estar linearmente correlacionada com as variáveis explicativas "x"
	- **Falta de multicolinearidade**: A multicolinearidade deixa os coeficientes instáveis, modelo não consegue atribuir bons valores para coeficientes de variáveis altamente correlacionadas

- **Erros**:
	* **Normalidade Multivariada**: os erros devem ter uma distribuição normal
	* **Independentes e identicamente distribuídos (iid)**: depois de treinar o modelo, os erros do modelo devem ser variáveis aleatórias independentes (não ter interseção) e devem ser identicamente distribuídas (ter a mesma função de distribuição acumulada). Por definição, uma variável aleatória é uma variável "iid" 
	* **Homocedasticidade**: Os erros devem ter uma variância constante, ou seja, não podem ter um padrão em relação ao eixo x
![[Pasted image 20230717220328.png | center]]
### Principais causas de heterocedasticidade nos resíduos
- Natureza das variáveis: alguns relacionamentos apresentam tendência à heterocedasticidade
- Outliers: um valor extremo na amostra pode inflacionar a variabilidade me um determinado ponto do ajuste
- Falhas na especificação do modelo: omissão de variáveis importantes, explicativas
- Transformação dos dados: utilização de transformações (como proporções, log, etc) pode reduzir a heterocedasticidade
- Em resumo, os erros (resíduos) não devem ser correlacionadas, ter a média zero, variância constante e ter distribuição normal

Obs: para verificar se uma variável possui distribuição normal em uma amostra, podemos fazer o teste de **Shapiro Wilk**

#todo 
completar após ver statquest

#regressão