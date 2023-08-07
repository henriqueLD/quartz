Método de agrupamento não hierárquico que utiliza a <mark style="background: #ADCCFFA6;">distância euclidiana</mark> entre os pontos para o cálculo do centróide:
$$d = \sqrt{\sum^{n}_{i=1}(x_i - y_i)^{2}}$$

Ajusta os centroides dos clusters com base nos valores médios, e <mark style="background: #FF5582A6;">por utilizar a média é mais sensível a outliers</mark>.

Os centroides finais podem não ser pontos verdadeiras presentes na base, apenas o valor médios dos pontos presentes no cluster.

Obs: A distância de Minkowski é uma generalização da distância euclidiana e da de Manhattan:
$$d = (\sum^{n}_{i=1}(x_i - y_i)^{p})^{\frac{1}{p}}$$
**Quando P=1** a distância é de Manhattan
**Quando P=2** a distância é a Euclidiana


#clustering 