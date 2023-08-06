
### Intro ~ 15s
Como a marina comentou, a gente sabe que existe oportunidade para reconhecer melhor a renda para alguns públicos específicos e nós atacamos esses pontos dessas maneiras:

#### Teto Select ~ 1m10s
Nós vamos implementar um novo teto para o público select que comprova renda com IR pois hoje os gerentes notam o impacto do cadastro na renda final porém pelos tetos atuais a renda riscos dificilmente se iguala ao valor do comprovante, principalmente para clientes NH21. 

Como no exemplo do cliente select Edson que levou um IR de 87mil na agência para comprovar renda e teve a renda riscos calculada pela nossa política limitada no teto máximo de 39mil.

Para tentarmos tratar esses casos nós vamos flexibilizar para 100mil o teto para esse perfil de público, para garantirmos que caso haja a atualização de renda com um comprovante forte, o cliente possa chegar a um patamar mais alto de renda riscos

#### Santander On ~ 1m15s
O nosso segundo ponto de atenção são os clientes que atualizam renda no santander on e acabam ficando com a renda estagnada até uma nova comprovação de renda ou para os clientes folha 12 meses (após esse periodo nós priorizamos o crédito salário)

Aqui a gente trouxe um exemplo dessa situação pra ilustrar, o Warley que atualizou sua renda pelo aplicativo para 39mil, 7 meses depois passou a receber um crédito salário com valor maior do que o atualizado mas a renda riscos iria se manter no mesmo patamar mais 2 meses até nós priorizarmos o fluxo "normal" da riscos

O nosso ajuste aqui vai ser a partir de 6 meses que o cliente atualizou pelo aplicativo, a política vai olhar suas informações e decidir se existe a possibilidade de aumento de renda com as demais informações internas do cliente, caso exista, ele terá o acréscimo na renda riscos de maneira antecipada.

#### Travas Salário ~ 1m30s
As travas que a gente cita aqui surgem a partir do momento que passamos a usar de forma mais forte o salário dentro da política, e a gente sabe que é uma formação muito boa e de um fluxo seguro porque o salário é uma informação sistêmica sem input do cliente/gerente

Porém notamos que existia uma pequena fragilidade na informação de salário quando notamos o exemplo da maria:

Maria é dona de uma empresa E1 (de pequeno porte) e tem uma conta PF no Santander, porém nós notamos que ela recebia na conta PF, salários de 140mil reais que no ano representariam mais de 50% do faturamento total de uma empresa do porte que ela tem, e com todo esse fluxo duvidoso a gente acaba superestimando o salário na hora de calcular a renda riscos

Para esse problema nós adicionamos valores máximos a serem considerados como crédito salário dependendo do porte da cnpj que paga o cliente, exclusivamente das duas menores classes (E1 e E2), assim nós não prejudicamos o cálculo da renda riscos com o valor do salário inflado

#### Demais políticas ~ 1m
Essas três são as mudanças com motivamação mais especificas, mas não são todas que teremos, seguindo aqui:

A nova **renda premium** é uma informação que vamos o histórico de faturas internas e externas de clientes com perfil premium para garantir um piso de renda mais adequado para esse público

**Conselho profissional** é outra informação que vamos adicionar para reconhecer melhor um perfil de público alta renda que tem cadastro em conselhos profissionais como os de medicina, oab, etc. Definindo novos valores de piso e tetos de rendas.

Vamos substituir a informação do calculo do salário pela revisão que a Ana já apresentou e agora também utilizamos a informação de **renda de servidor público** que compramos da quod como um valor mínimo de salário para os servidores que não são folha