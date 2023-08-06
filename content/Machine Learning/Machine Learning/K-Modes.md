Método de agrupamento não hierárquico utilizado para agrupar dados categóricos, já que os anteriores funcionam de maneira eficiente apenas para dataset com valores numéricos.

K-Modes define os clusters com base no número de categorias coincidentes entre os dados (número de atributos categóricos comuns que são compartilhados por dois pontos).

Se baseia no algoritmo do K-means com as seguintes alterações:
1. Utiliza uma medida de dissimilaridade simples para dados categóricos
2. Substitui a média dos clusters pela moda
3. Utiliza método de frequência para atualizar os valores das moda

Obs: Apesar de trabalhar com variáveis categóricas, as mesmas devem estar no formato numérico para entrar no modelo.

#clustering 