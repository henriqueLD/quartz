Boruta é um algoritmo de feature selection desenvolvido em 2010 e desenhado para fazer uma seleção automática de features em um banco de dados. Surgiu originalmente como um módulo no R, porém foi feita uma implantação em Python com mais flexibilidade nos parâmetros.

Resumidamente, o Boruta permuta as features existentes nos bancos de dados (chamadas de **shadow features**) e compara sua importância com as features originais, em teoria **qualquer feature significante** para a solução do problema tende a ser **mais importante do que a melhor shadow feature**.

## Exemplo
A seguir vamos exemplificar o funcionamento do método com um dataset simples, onde queremos **inferir a renda** de uma pessoa a partir da sua **idade**, **altura** e **peso**:

![[Pasted image 20230719225255.png|center]]

### Shadow Features
No Boruta, as features não competem entre si, em vez disso elas são comparadas com uma versão randomizada delas mesmas, as denominadas **shadow features**. No nosso exemplo, será criada a coluna **shadow_age** que representa a permutação das observações de **age**, e analogamente **shadow_height** e **shadow_weight**.

Essas shadow features são agrupadas ao dataset original de features, obtendo agora um novo dataframe *"X_Boruta"*:
![[Pasted image 20230719230722.png|center]]

Próximo passo é ajustar uma [[Random Forest - Classificação|Random Forest]] utilizando **X_Boruta** para predizer **income**.

### Avaliando as features importances
Agora que temos as shadow features e o modelo ajustado, vamos calcular as features importances de cada uma das features no dataset *X_Boruta* e **identificar a maior feature importance obtida entre as shadow features**.

Quando a importance de uma feature é maior do que esse threshold, consideramos um "acerto". A ideia é que **uma feature só é importante se for capaz de explicar melhor a target do que a melhor shadow feature**.
![[Pasted image 20230719231703.png|center]]
Aqui o threshold é 14%, logo apenas 2 features atingiram a expectativa e foram consideradas úteis, **age** e **height**, enquanto **weight** não performou bem. Aparentemente deveríamos desconsiderar a última feature, porém <mark style="background: #ADCCFFA6;">devemos acreditar em apenas uma estimativa?</mark>

### Distribuição Binomial
Como em outros diversos métodos em machine learning, a iteração é uma ferramenta útil e que nos trás muitos benefícios, principalmente para validarmos a feature importance utilizando Boruta.

Se realizarmos o processo de ajuste de modelo e contagem de "acertos" em 20 iterações, obtemos os seguintes resultados:
![[Pasted image 20230719232402.png|center]]

Agora como podemos definir um **critério de decisão?** Vamos partir do pressuposto que não temos a menor ideia se uma feature é significante ou não, qual a probabilidade que devemos mantê-la? **O nível máximo de incerteza é 50%, como jogar uma moeda para tomar essa decisão**. 

Como cada iteração nos retorna um resultado binário (acerto ou não), <mark style="background: #ADCCFFA6;">uma série de n iterações segue uma distribuição binomial</mark> e vamos utilizar essa distribuição para tomar a decisão:

![[Pasted image 20230719233226.png|center]]

Aqui não teremos um critério 100% objetivo para manter ou remover a feature, em vez disso usaremos áreas de aceitação:
**Área de recusa**: representada de <mark style="background: #FF5582A6;">vermelho</mark>, se a distribuição dos acertos de uma feature caírem aqui, consideramos ela não significante e removemos do dataset.
**Área de dúvida**: representada de <mark style="background: #ADCCFFA6;">azul</mark> é a área onde o método é indeciso se devemos manter ou remover a variável, e portanto, *temos a liberdade para tomar a decisão*.
**Área de aceitação:** representada de <mark style="background: #BBFABBA6;">verde</mark>, área onde caem as features consideradas significantemente preditivas para o problema em questão, e devem sempre ser mantidas.

As regiões são definidas selecionando as duas caudas mais extremas da distribuição binomial, onde cada cauda corresponde a aproximadamente 0.5% da distribuição.

Em resumo, após 20 iterações nós podemos tomar decisões com base em estatísticas bem definidas:
1. Para o problema de inferir o **income**, devemos manter **age** como variável preditiva e remover a variável de **weight**
2. O método de Boruta foi indeciso com relação a variável **height** e a escolha fica na nossa mão se devemos ou não manter (se não houver extrema necessidade de redução de custo operacional, é recomendável manter as variáveis na zona de dúvida)

Após a definição das variáveis importante, <mark style="background: #FF5582A6;">não devemos esquecer de desconsiderar completamente as shadow features para o modelo final</mark>.

### Conclusão
Boruta é um método que realiza feature selection de maneira estatisticamente robusta, removendo o processo subjetivo de definir o threshold de corte que é necessário em várias outras técnicas de feature selection.