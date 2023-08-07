O algoritmo de clusterização não hierárquico que considera os clusters como regiões de maior/menor densidade, muito útil para distribuições de dados que não seguem um padrão esférico/convexo.

Esse algoritmo consegue identificar qualquer formato na distribuição dos dados, verificando primariamente a similaridade entre os pontos.

Não exige que o número de clusters seja definido previamente e pode ser utilizado para detectar quais pontos apresentam características de ruído/outliers. 

Funciona identificando pontos que estão em regiões densas:
**Core**: São os pontos que tiverem pelo menos um número específico de pontos (argumento *MinPts*) dentro do raio (argumento *Eps*). **São pontos localizados no interior de um cluster**.
**Border**: São considerados pontos de fronteiras aqueles que tem um número menos do que o definido pelo MinPts em seu raio, mas está na vizinhança de pelo menos 1 ponto **core**.
**Noise:** São os pontos que não foram classificados como **core** ou **border**.

![[Pasted image 20230722160043.png|center]]

**Passo a passo:**
1. Percorre e marca os pontos como **core**, **border** ou **noise**
2. Desconsiderar os pontos marcados como **noise**
3. Inserir uma aresta entre cada par de objetos de **core** vizinhos
4. Cada componente conectado forma uma cluster
5. Cada border é atribuído ao cluster de um de seus **core** associados

#clustering 