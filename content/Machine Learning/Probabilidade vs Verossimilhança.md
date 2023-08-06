Probabilidade e Verossimilhança são termos comumente intercalados durante conversas sobre Machine Learning. Porém no contexto de estatística cada um tem um papel e descreve informações completamente diferentes.

### Probabilidade
Probabilidade é uma medida numérica que quantifica a chance de um evento ocorrer e é derivada a partir de uma distribuição, calculando a **área abaixo da curva entre dois pontos**:
![[Pasted image 20230715180903.png]]
Por exemplo: dada a distribuição de altura de uma população que segue um Normal com média = 155.7 e desvio padrão = 6.6, podemos calcular a **probabilidade de realizar uma medição e observar um valor entre 142.5 e 155.7cm**. 
A área abaixo da curva no exemplo anterior é igual a 0.48, logo a probabilidade de medirmos alguém que possua o altura no intervalo descrito é de 48%.

Analogamente é fácil notar que em **qualquer distribuição contínua** ==a probabilidade de observar um valor especifico é sempre **ZERO**==, pois não conseguimos calcular área de um figura com comprimento 0.

### Likelihood
Likelihood ou Verossimilhança é uma medida estatística que quantifica a plausibilidade de quão bem os parâmetros de um modelo se ajustam aos dados.

Seguindo o exemplo anterior, a verossimilhança é usada para calcular o quão provável é os parâmetros do modelo gerarem exatamente as observações que temos.
![[Pasted image 20230715182357.png]]

Em resumo, a principal diferença entre probabilidade e likelihood é a direção do raciocínio estatístico. A probabilidade é usada para calcular a chance de eventos futuros com base em um modelo conhecido, enquanto a verossimilhança é usada para estimar os parâmetros do modelo com base em dados observados

#conceitos