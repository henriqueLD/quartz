É um algoritmo de e classificação baseado no Teorema de Bayes e na suposição de independência condicional entre as variáveis explicativas, costumando ter alto viés e baixa variância. **Considerado ingênuo (naive) porque assume total independência entre as variáveis**, mesmo que não seja necessariamente verdade nos dados reais.

*Durante a descrição será utilizado um exemplo de classificação de e-mail como "<mark style="background: #ADCCFFA6;">Normal</mark>" ou "<mark style="background: #FF5582A6;">Spam</mark>"*
O primeiro passo é calcular as probabilidades a priori de cada classe com base na frequência que cada classe ocorre nos dados de treinamento:
![[Pasted image 20230716151827.png]]
Também calculamos as probabilidades condicionais de cada valor de cada característica para cada classe, no nosso exemplo são palavras presentes nos e-mail de treino:
![[Pasted image 20230716152356.png]]

Quando uma nova observação surge e temos que fazer a predição com Naive Bayes, o algoritmo utiliza as probabilidades calculadas para calcular a probabilidade posterior de cada classe para aquela observação (gera um Score). A classe com maior Score é selecionada como a classe predita para a informação

Vamos supor que receber um novo e-mail contendo **"Dear friend"** e desejamos utilizar o modelo para classifica-lo como Normal ou Spam, vamos calcular os Scores para cada classe:

$$P(N)*P(Dear|N)*P(Friend|N) = 0.67*0.47*0.29 = 0.09$$
$$P(S)*P(Dear|S)*P(Friend|S) = 0.33*0.29*0.25 = 0.01$$
Como a classe predita é derivada da classe com maior Score calculado, definimos esse novo e-mail como <mark style="background: #ADCCFFA6;">Normal</mark>

O exemplo **"Dear friend"** funciona porque existe, em ambas as classes, observações que apareceram durante os e-mails de treinamento, porém dados discretos faltantes podem se tornar um grande problema bem rápido para o Naive Bayes.

Um exemplo problemático seria classificar um novo e-mail **"Lunch Money Money Money Money"** dados que a probabilidade a priori de observar "Lunch" no Spam é zero:

$$P(N)*P(Lunch|N)*P(Money|N)^4 = 0.67*0.18*0.06^4 = 0.000002$$
$$P(S)*P(Lunch|S)*P(Money|S)^4 = 0.33*0.00*0.57^4 = 0$$
## Como Naive Bayes trata dados faltantes
Normalmente, o algoritmo de Naive Bayes elimina o problema de dados faltantes realizando uma "pseudo contagem" de cada palavra. Não é nada mais do que adicionar uma contagem para **cada palavra em todas as classes**.

Assim podemos recalcular as **probabilidades condicionais** de cada palavra e não corremos o risco de alguma ser zero e impactar o cálculo de qualquer combinação presente no e-mail:
![[Pasted image 20230716155700.png]]

$$P(N)*P(Lunch|N)*P(Money|N)^4 = 0.67*0.19*0.10^4 = 0.00001$$
$$P(S)*P(Lunch|S)*P(Money|S)^4 = 0.33*0.09*0.45^4 = 0.00121$$
Assim classificando o e-mail corretamente como <mark style="background: #FF5582A6;">Spam</mark>

## Utilizando dados contínuos
Quando existe a necessidade de utilizar dados contínuos dentro do Naive Bayes utilizamos na formula  em vez da probabilidade condicional, a verossimilhança da variável considerando as distribuições para cada uma das classes.

*Obs: Probabilidade e Verossimilhança representam informações diferentes em estatística, consultar:[[Probabilidade vs Verossimilhança]]*

Vamos seguir com o exemplo de classificar se uma pessoa vai <mark style="background: #ADCCFFA6;">gostar</mark> ou <mark style="background: #FF5582A6;">não gostar</mark> do filme Troll 2:
![[Pasted image 20230716161544.png]]
$$P(Gostar) = \frac{4}{7}=0.57$$
$$P(N Gostar) = \frac{3}{7}=0.42$$
Surge uma nova observação para predizer, com os seguintes dados: Popcorn = 20g, Soda= 500ml e Candy = 100g

$$(1):P(G)*L(Popcorn=20|G)*L(Soda=500|G)*L(Candy=100|G) = 0.57*0.06*0.004*0.000000001$$
==Para evitar problemas de *Underfloat* quando multiplicamos números muito próximos de zero, uma alternativa é utilizar log natural para transformar toda a fórmula e tornar a multiplicação em adição:==

$$(1):log(0.57*0.06*0.004*0.000000001)$$
$$log(0.57)+log(0.06)+log(0.004)+log(0.000000001) = -124$$
$$(2): P(NG)*L(Popcorn=20|NG)*L(Soda=500|NG)*L(Candy=100|NG)$$
$$log(0.4)*log(0.000000001)*log(0.00008)*log(0.02) = -48$$
Logo classificamos a nova observação como <mark style="background: #FF5582A6;">Não Gosta de Troll 2</mark>

### Vantagens
- Algoritmo de baixa complexidade computacional e pode ser usado em *"real time"*
- Escalável para datasets grandes (performa bem em base com alta dimensionalidade)
- Pouco sensível para features não significantes
- Eficaz em problemas de multiclasses
- Útil para classificar textos, análise de sentimentos, detecção de spam e sistemas de recomendação

### Desvantagem
- Supõe que as variáveis são independentes, o que não é verdade na maioria das vezes
- Mau estimador em probabilidade, suas probabilidades (*predict_proba*) não são tão assertivas
- Os dados de treino devem representar muito bem a população (preenchimento de variável/público todo capturado na base de treino)
#classificação 