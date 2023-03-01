<h1 align="center">Previsão de vendas da Rossmann </h1>

![image](https://user-images.githubusercontent.com/109559298/221976852-2d8d2538-846e-413c-a335-fb2d31cab8eb.png)

A [Rossmann](https://www.rossmann.de/de/) é uma rede de farmácias da europa com mais de 3.000 unidades físicas distribuídas em 7 países da Europa. As lojas vendem mais de 21.000 produtos e conta com mais de  56.000 funcionários.


O objetivo do projeto é simular um problema de negócio a ser solucionado por um Cientista de Dados. Os dados da Rossmann foram retirados do [Kaggle](https://www.kaggle.com/competitions/rossmann-store-sales/overview) e incluem, principalmente, registros de vendas da empresa. 

Foram seguidas as recomendações da [Comunidade DS](https://comunidadeds.com/) para a realização do projeto.

# 1. Problema de negócio

A rede de farmácias Rossmann precisa iniciar um processo de reformas para atender melhor os consumidores. Para isso, foi solicitada uma previsão de receita da empresa correspondente às próximas 6 semanas, para que o CFO direcione o valor que será investido em cada loja. Sendo assim, do ponto de vista de uma cientista de dados, o problema envolve séries temporais e pode ser resolvido com algoritmos de regressão, auxiliando o CFO na tomada de decisão.

# 2. Descrição dos dados

Colunas | Descrições
-------|----------
Store | ID exclusivo de cada loja
DayOfWeek | Dia da semana em que a venda ocorreu
Date | Data de venda
Sales | Vendas por dia
Customers | Nº de clientes por dia
Open | Indicador para loja aberta: 0 = fechado, 1 = aberto
Promo |Indica a loja está realizando promoção no dia
StateHoliday |Indica um feriado: a = feriado público, b = Páscoa, c = Natal, 0 = nenhum
SchoolHoliday | Indica se a loja foi ou não fechada durante o feriado escolar
StoreType | Diferencia em 4 modelos de lojas diferentes: a, b, c, d
Assortment | Indica o nível de variedade de produtos: a = básico, b = extra, c = estendido
CompetitionDistance | Distância em metros até a loja concorrente mais próxima
CompetitionOpenSinceMonth | Fornece o mês aproximado em que o concorrente mais próximo foi aberto
CompetitionOpenSinceYear' | Fornece o ano aproximado em que o concorrente mais próximo foi aberto
Promo | Indica se a loja está com alguma promoção ativa no dia
Promo2 |Indica se a loja deu continuidade na promoção: 0 = loja não está participando, 1 = loja participando
Promo2SinceWeek | Descreve a semana em que a loja começou a participar da Promo2
Promo2SinceYear | Descreve o ano em que a loja começou a participar da Promo2
PromoInterval | Meses em que a Promo2 ficou ativa

# 3. **Abordagem estratégica**

A abordagem estratégica foi inspirada no CRISP-DM, um modo flexível e adaptável de trabalhar, que pode ser aplicado a diferentes projetos de ciência de dados.A estratégia parte da implementação de 9 passos para entregar resultado o mais rápido possível e permitir melhorar o projeto ao longo do tempo. Os passos seguidos no projeto podem ser acompanhados em mais detalhes [aqui](https://github.com/deborabmfreitas/projeto-rossmann-regressao/blob/main/rossmann_regression.ipynb).

**Problema de negócio**

A rede de farmácias Rossmann precisa iniciar um processo de reformas para atender melhor os consumidores. Para isso, foi solicitada uma previsão de receita da empresa correspondente às próximas 6 semanas, para que o CFO direcione o valor que será investido em cada loja.

**Entendimento do negócio**

Na fase inicial de entendimento do negócio, o objetivo é entender a real necessidade do cliente e os objetivos do projeto. No caso em questão, a tarefa solicitada é a previsão de vendas para as próximas 6 semanas para obter a receita da empresa. Como se trata de uma previsão baseada em dados históricos, o projeto é considerado uma série temporal.

Para resolver o problema, uma opção adequada é a utilização de algoritmos de regressão, que são capazes de modelar relacionamentos entre variáveis e prever valores futuros com base nesses relacionamentos.

**Coleta de dados**

Os dados seriam obtidos no banco de dados da empresa, que seriam extraídos com SQL. No entanto, os dados do atual projeto foram retirados do [Kaggle](https://www.kaggle.com/competitions/rossmann-store-sales/overview).

**Resumo das demais etapas**  

1. Limpeza de dados
2. Exploração dos dados
3. Modelagem dos dados
4. Implementação dos algoritmos de Machine learning
5. Avaliação de performances
6. Tradução para resultados de negócio

# 4. **Algoritmos de Machine learning utilizados**

1. Average Model (baseline)
2. Linear Regression
3. Lasso Regression
4. Random Forest Regression
5. XGBoost Regression 

O XGBoost Regression foi selecionado para gerar os resultados finais.

# 5. **Resultado de negócio**

Com base na previsão dos algoritmos de machine learning, foi possível calcular por meio do erro MAE o melhor e o pior cenário de receita da empresa pelas pelas próximas 6 semanas e o quanto investir em cada loja.


**Demonstração da performance por loja**

Loja | Previsão de receita | Pior cenário | Melhor cenário
------|---------|--------------|----------------
642	  | 112114.585938| 111790.343750| 112438.828125
703   | 107601.835938 |107277.312500 |	107926.359375	
488   | 130716.234375 |	130298.859375	| 131133.609375	


**Performance total**

Cenários| Valores
-------|----------
Previsão	| R$138,714,864.00
Pior cenário | R$134,647,888.00
Melhor cenário | R$142,781,824.00
