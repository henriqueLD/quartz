Quando treinamos um modelo de Machine Learning, sempre teremos um erro de generalização: erro que informa o <mark style="background: #ADCCFFA6;">quão bem o modelo generaliza para dados que não foram usados no treinamento</mark> (dados novos), e esse erro pode ser decomposto em 3 termos:

### Viés
Erro ou diferença entre o previsto e observado (suposições erradas assumidas pelo modelo)

### Variância
Erro devido a sensibilidade excessiva do modelo à pequenas variações nos dados, ou seja, um modelo com alta variância captura ruído aleatório nos dados disponíveis, ao invés dos outputs pretendidos (terá performance ruim para dados não vistos)

### Erro irredutível
Erro devido ao ruídos dos dados, considerados irredutíveis dado a aleatoriedade natural na distribuição "geradora"

A partir desses erros, surgem dois fenômenos no aprendizado de máquina se o modelo se ajusta aos dados de treinamento de maneira inadequada:

## Underfitting
*Underfitting* acontece quando o modelo se ajusta de maneira insuficiente ao dados de treino, ou seja, o modelo não é capaz de aprender os padrões presentes nos dados e/ou **não consegue replicar o comportamento** dos dados pela técnica de escolha (ex: utilizar [[Regressão Linear]] para dados que seguem uma parábola).

Como resultado, o modelo não consegue aprender com precisão as relações entre as variáveis e as classes, resultando em um **desempenho ruim tanto nos dados de treinamento quando nos dados de teste**

<mark style="background: #ADCCFFA6;">Para lidar com underfitting, é necessário utilizar modelos mais complexos, aumentar a quantidade e qualidade dos dados de treinamento e considerar o uso de características mais relevantes para a solução do problema</mark>.

## Overfitting
*Overfitting* acontece quando o modelo se ajusta bem demais aos dados de treinamento, incorporando não apenas os padrões reais, mas também o erro irredutível presente nos dados de treino. O modelo se torna muito complexo e específico ao conjunto de dados apresentado inicialmente, resultando em baixa capacidade de generalização para novos dados de teste.

Em outras palavras, o modelo **decora** os exemplos de treinamento, mas falha em capturar a estrutura geral dos dados para aplicar em uma nova amostra.

Sinais de *overfitting* incluem um desempenho excepcionalmente bom nos dados de treinamento, mas desempenho muito menor em dados de teste não vistos anteriormente. O modelo pode ser tornar muito sensível a pequenas variações nos dados de treino e tende a apresentar alta variância.

<mark style="background: #ADCCFFA6;">Para evitar o overfitting é comum utilizar técnicas de </mark> [[Regularização]]<mark style="background: #ADCCFFA6;">, como a redução de  complexidade do modelo, a adição de termos de penalização (L1/L2) ou o aumento do tamanho do conjunto de treinamento.</mark>
![[Pasted image 20230717210409.png | center]]

A complexidade de um modelo define a flexibilidade para aproximar a previsão da distribuição real dos dados. Quanto <mark style="background: #ADCCFFA6;">mais complexidade</mark> tem o modelo, <mark style="background: #ADCCFFA6;">maior tende a ser sua variância e menor o viés</mark>, por outro lado <mark style="background: #ADCCFFA6;">modelos muito simples possuem viés elevado e baixa variância</mark>:

![[Pasted image 20230717210840.png | center]]
Como o erro do modelo é a soma dos três termos e, **o erro irredutível é constante**, é preciso encontrar um equilíbrio entre viés e variância para garantirmos o melhor desempenho do nosso modelo, e "filosofia" de encontrar as quantidades ótimas de viés e variância é chamada de **trade-off viés-variância**.

![[Pasted image 20230717211153.png | center]]
#conceitos