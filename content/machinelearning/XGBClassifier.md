É um algoritmo derivado do XGBoost(Extreme Gradient Boosting) baseado em [[Ensemble]] de árvores de decisão que utiliza o [[machinelearning/Gradient Boosting|Gradient Boosting]] como estrutura de forma otimizada computacionalmente, aproveitando do paralelismo.

![Benefícios XGBoost|center](notes/images/xgboost.png)

Consegue melhorar o tempo de processamento construindo os modelo base de árvore de forma paralela, além de ter sido projetado para utilizar os recursos do hardware de forma mais eficiente. Além disso, **realiza a poda das árvores durante o processamento, que gera um ganho de performance**.
Utiliza a regularização [[Regularização|L1 (Lasso)]] e [[Regularização|L2 (Ridge)]] para prevenir *overfitting*, admite naturalmente features esparsas, sabendo lidar de forma eficiente com valores nulos. Além disso realiza validação cruzada em cada iteração.

### Vantagens
- Dispensa a necessidade de *feature engineering* (não precisa de normalização/padronização, também pode lidar com valores nulos)
- Pode ser utilizado para determinar *feature importance*
- Pouco sensível a outliers
- Lida bem com datasets muito grandes
- Custo computacional razoável
- Menos propenso a *overfitting*
- Modelo possui boa performance, normalmente aparece nas melhores soluções em sites de competições

### Desvantagem
- Pouca interpretabilidade (modelo black box)
- Pode ocorrer *overfitting* se não houver ajuste adequado dos hiperparâmetros
- Quantidade extensa de hiperparâmetros para serem tunados (requer cuidado nessa etapa)


#todo 
Ver detalhadamente como funciona o gradient boosting


#classificação #xgboost