# Previsão de vendas da Rossmann
![image](https://user-images.githubusercontent.com/109559298/221976852-2d8d2538-846e-413c-a335-fb2d31cab8eb.png)

A [Rossmann](https://www.rossmann.de/de/) é uma rede de farmácias da europa com mais de 3.000 unidades físicas distribuídas em 7 países da Europa. As lojas vendem mais de 21.000 produtos e conta com mais de  56.000 funcionários.


O objetivo deste projeto é simular um problema de negócio a ser solucionado por um Cientista de Dados. Os dados da Rossmann foram retirados do [Kaggle](https://www.kaggle.com/competitions/rossmann-store-sales/overview) e incluem, principalmente, registros de vendas da empresa. 

Foram seguidas as recomendações da [Comunidade DS](https://comunidadeds.com/) para a realização do projeto.

# 1. Problema do negócio

A rede de farmácias Rossmann precisa iniciar um processo de reformas para atender melhor os consumidores. Para isso, foi solicitada uma previsão de receita da empresa correspondente às próximas 6 semanas, para que o CFO direcione o valor que será investido em cada loja. Sendo assim, do ponto de vista de uma cientista de dados, o problema envolve séries temporais e pode ser resolvido com algoritmos de regressão, auxiliando o CFO na tomada de decisão.

**Questões de negócio**

1- Qual a previsão de vendas de cada loja nas próximas 6 semanas?

2- Quanto investir financeiramente em cada loja?  

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
