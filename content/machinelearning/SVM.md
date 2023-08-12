Support Vector Machine tem o objetivo de encontrar a **fronteira de decisão** que consiga separar o conjunto de dados em classes. **O SVM busca a linha ou hiperplano que melhor separa os dados**, maximizando a distância entre os pontos e a fronteira.

Para encontrar esse hiperplano o SVM usa um processo de minimização para encontrar os pontos que servirão de suporte para criar o vetor delimitante de fronteira, tais pontos são encontrados de forma a maximizar a distância entre eles e a fronteira.

O SVM em sua formulação original apenas será capaz de modelar problemas de classificação binária, porém técnicas podem ser aplicadas para fazer expansão para problemas multiclasses, além de problemas regressivos. Em sua forma original, é um classificador linear, porém pode ser utilizados em problemas não lineares utilizando o "Kernel Trick".

## Soft Margin

Qualquer variação na posição dos pontos próximos à fronteira pode influenciar de maneira forte a posição do hiperplano. Dessa forma, o **soft margin** tem como objetivo permitir que o SVM cometa uma certa quantidade de erros e mantenha a margem o mais larga possível, para que outros pontos ainda possam ser classificados corretamente **(Pode ser interpretado como um trade-off entre viés e variância)**.
- Ajuda a reduzir o problema de *overfitting*, uma vez que com uma margem mais larga é possível generalizar melhor dados não vistos.
- É feito utilizando o hiperparâmetro "C": decide o trade-off entre maximizar a margem e minimizar os erros. Quando "C" é pequeno, os erros de classificação recebem menos importância e o foco maior é em maximizar a margem, todavia quando "C" é grande, o foco é mais em evitar erros de classificação ao custo de manter a margem mais estreita

## Kernel Trick

Quando os dados não são linearmente separáveis a solução é aumentar a dimensionalidade, de forma que em uma nova projeção os dados sejam linearmente separáveis. O aumento de dimensionalidade é feito utilizando uma função **(kernel)**, a qual mapeia os dados em outro espaço.

O Kernel Trick se refere ao fato do SVM, a partir dos kernels, ser capaz de calcular a relação entre os dados em dimensionalidade aumentada sem que de fato os dados sejam transformados para uma maior dimensão. Fator que torna possível utilizar o Kernel RBF que funciona com dimensionalidade infinita e que as relações sejam calculadas.
![Exemplo Kernel SVM|center](machinelearning/svm_kernel_example.png)
- Os **Kernels** mais utilizados são:
	- RBF (Radial Basis Function), sendo a principal a Gaussiana
	- Polinomial
	- Sigmoide
![Exemplo Kernels SVM|center](machinelearning/svm_kernels_examples.png)

![Exemplo Sigmoid Kernel|center](machinelearning/svm_sigmoid_kernel.png)

### Vantagens
- Boa performance em problemas com alta dimensionalidade (muitas features)
- Ótimo algoritmo quando as classes são separáveis
- Pouco sensível a outliers
- Mais adequado para classificações binárias

### Desvantagem
- Custo computacional elevado para datasets muito grandes (requer bastante processamento para alterar a dimensionalidade)
- Todas as features devem ser numéricas
- Não performa bem quando as classes estão muito sobrepostas
- Requer cuidado para selecionar de forma apropriada os hiperparâmetros (C, Kernel, etc)