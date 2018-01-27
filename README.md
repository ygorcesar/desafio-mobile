
# Desafio Mobile

O desafio consiste em criar uma loja de itens de Star Wars que o usuário é capaz de adicionar os itens desejados em um carrinho de compras e finalizar a compra com uma simulação de transação e-commerce.

O candidato deve dar **fork** neste repositório e após o termino do desenvolvimento, realizar um **pull request** para análise.

Para obter os itens da loja, sua aplicação deverá realizar uma chamada `GET` na URL:

https://private-658512-desafiocajutech.apiary-mock.com/products

A lista de itens deve exibir as seguintes informações:
+ Nome [title]
+ Preço [price]
+ Vendedor [seller]
+ Foto do item [thumbnailHd]

Após o usuário adicionar todos os itens no carrinho, ele deverá finalizar a compra.

###### Simulação E-commerce

Para finalizar a compra sua aplicação deve realizar um `POST` na URL

https://private-658512-desafiocajutech.apiary-mock.com/checkout
com os seguintes atributos:
+ Número do cartão (máximo de 16 números - XXXX XXXX XXXX XXXX)
+ Nome do portador do cartão
+ Vencimento do cartão (MM/yy)
+ CVV (código encontrado na parte traseira do cartão)
+ Valor da transação (total dos itens no carrinho)

``` json
{  
   "card_number":"1234123412341234",
   "value":7990,
   "cvv":789,
   "card_holder_name":"Luke Skywalker",
   "exp_date":"12/24"
}
```

###### Banco de dados
Todas as transações realizadas devem ser salvas em um banco interno com os seguintes campos:


+ Valor
+ Data e hora
+ Últimos 4 dígitos do cartão
+ Nome do portador do cartão

###### Lista de Transações
A aplicação deverá conter uma tela para exibir as transações que foram salvas em seu banco de dados.
