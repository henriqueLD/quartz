Árvores de decisão são algoritmos supervisionados não paramétricos que realizam classificação por meio da construção de uma estrutura em forma de árvore. Cada nó interno da árvore representa uma condição sobre uma ou mais características, enquanto **as folhas** representam as classes finais preditas.

A árvore começa com um **nó raiz**, onde a seleção do atribute é feita com base em algum critério, geralmente **[[Entropia]]** ou **[[Gini]]**. O intuito das separações é obter o máximo de homogeneidade possível nas folhas.

![[Pasted image 20230716175205.png | center]]

Com base no atributo selecionado, os dados de treinamento são divididos em subconjuntos em **nós**, de acordo com os diferentes valores/resposta do atributo selecionado onde cada **nó** representa uma ramificação da árvore.

O processo de seleção de feature e ponto de corte se repete, criando uma estrutura de árvore, até que uma **condição de parada** seja atingida. A condição de parada geralmente reflete um determinado **índice de pureza das folhas** da árvore ou ocorre quando um **limite máximo de profundidade** é atingido, esses termos podem ser definidos nos hiperparâmetros 

![[Pasted image 20230716180257.png | center]]

Após a construção da árvore, uma nova observação é classificada percorrendo **as condições de cada nó até chegar uma folha**, que contém a classe predita pelo modelo.

## **Exemplo**: 
Classificador se uma pessoa gosta ou não gosta do filme Troll 2. partindo dos dados de treino a seguir:
![[Pasted image 20230716185613.png | center]]

Para decidir a raiz da árvore, vamos calcular o **índice de GINI** para de cada uma das duas variáveis categóricas:
![[Pasted image 20230716191329.png | center]]

Para a variável contínua **Age**, devemos ordenar (já está no exemplo), tirar a média entre cada linha e calcular o **índice de GINI** considerando **cada uma dás médias como condição de ramificação no nó** e pegar a condição que retorna o melhor índice:
![[Pasted image 20230716191834.png | center]]

Logo a nossa raiz será a condição **Loves Soda com GINI = 0.214**, devemos seguir com as demais variáveis, em qualquer nó que ainda apresentar impureza, para determinar o resto da ramificação da árvore repetindo o mesmo processo **(Lembrando que o nó resultando da resposta "no" já está puro e não precisamos alterar)**

![[Pasted image 20230716192751.png]]

Com essa nova quebra, utilizando a condição **Age < 12.5 com Gini = 0**, conseguimos ter uma árvore onde todas as folhas são 100% puras, e assim não temos mais pra que continuar ramificando, chegando a seguinte árvore de decisão:

![[Pasted image 20230716193136.png | center]]

## Problema de Overfitting
Por ser um algoritmo de partição recursivo, a árvore estende a sua profundidade até o ponto de classificar perfeitamente os elementos do conjunto de treino, **podendo até mesmo zerar o número de erros**. Desta forma o modelo pode não generalizar para dados não vistos.
Uma forma de reduzir o overfitting é realizando a **poda** da árvore, que pode ser utilizada de duas formas: para o crescimento da árvore mais cedo ou após a árvore já estar completa, geralmente tunando os hiperparâmetros

### Vantagens
- Não é necessário normalizar/padronizar os dados
- Fácil interpretabilidade e de fácil visualização
- Bom para problemas binários ou multiclasses
- Útil para saber descobrir a *feature importance* (seleção de variáveis)
- Features com baixa significância não afetam a predição (porém aumenta o custo computacional)

### Desvantagem
- Fácil de acontecer *overfitting* se não cuidar dos hiperparâmetros
- Sensível aos dados: variação nas amostras podem gerar árvores bem diferentes
#classificação 