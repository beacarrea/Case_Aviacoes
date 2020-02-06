# Case aviação Data Science

## Perguntas baseadas em hipóteses levantadas

- Qual o volume de descontos dado por viação ? E por mês ?

- Os descontos mais utilizados (ou seja, os tickets com desconto mais vendidos) têm alguma relação com o fato de serem [e-tickets](https://www.spedbrasil.com.br/bpe/) ? E tem relação com a disposição do assento entre janela / corredor ?

- Há alguma relação entre variação de preço na rota e variação de vendas na mesma acima do "normal" ?

- Pensando no crescimento de vendas através do desconto, para quais viações você pediria descontos no final de ano e em quais rotas ?



## Dados

A descrição de cada coluna está abaixo:

| Coluna  | Explicação |
| ------------- | ------------- |
| datetime_booking  | Dia e hora que o ticket foi vendido |
| kiosk_printed_flag  | Flag se o ticket foi impresso em um dos quiosques ClickBus  |
| eticket_flag  | Flag se o ticket é do modelo e-ticket (que não necessita ser impresso) |
| dd_seat_number  | Número do assento |
| travel_company  | Viação (ou empresa de ônibus) |
| travel_company_commission  | % de comissão que a ClickBus cobrou da Viação nesse ticket |
| route | Rota (ou viagem, conjunto de origem e destino) |
| unit_ticket_price_success  | Preço do ticket |
| service_class_id  | ID do tipo (classe) do assento |




## Calculo de desconto

Para calcular o desconto, obtive primeiro o valor inteiro do ticket. Ele pode ser obtido calculando o valor de ticket mais comum por mês, rota, viação e classe de serviço. 
O que estiver abaixo de 80% desse valor inteiro é um ticket com desconto.

Considerei os assentos ímpares como lugares na janela e os pares como lugares no corredor dos ônibus.
