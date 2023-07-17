---
layout: default
title: Cadastrar Customizado
grand_parent: Pagamento
parent: Cadastrar Gateway
nav_order: 1
---

Cadastrar Customizado
{: .fs-9}

Como cadastrar outra ferramenta de pagamento além de PayPal, PagSeguro e Mercado Pago
{: .fs-6 .fw-300 }

## Passo a passo

1. Entre na pagina inicial da extensão.

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/selecionar_plugin.png" class="img-fluid" />

2. Selecione `adicionar um novo Gateway`.

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/selecionar_plataforma.png" class="img-fluid" />

2.1. Você irá precisar de um nome para a ferramenta, o qual deve ser um nome diferente dos outros gateways já existentes. Além disso você precisará também de um token, uma url e um método para esse url oferecido pelo proprio gateway.

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/pagamento_customizado.png" class="img-fluid" />

3. Procure pela documentação de API da ferramenta que deseja usar. Em nosso exemplo vamos usar o proprio [Mercado Pago](https://www.mercadopago.com.br/developers/pt/reference) como um gateway genérico.

4. Procure por link de pagamento, checkout pro, ou similares. Em nosso exemplo [checkout-preferences](https://www.mercadopago.com.br/developers/pt/reference/preferences/_checkout_preferences/post).

5. Preencha o formulario com as informações corretas seguindo a tabela abaixo.

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/pagamento_customizado_preenchido.png" class="img-fluid" />

Para pegar as informações do sistema os campos são separados em chaves e valor sendo as chaves, o objeto esperado pela api e o valor o objeto dentro do sistema.

Por exemplo no caso do mercado pago ele espera um conjunto de items com algumas informações obrigatórias.

Então criamos um campo de requisição contendo a chave "items" e no valor colocamos todos os campos necessários comforme a tabela abaixo
e no final temos o seguinte campo chave/valor:

`Items` = `[{"id":"${extrato.itens.index.id}","title":"${extrato.itens.index.produto_avulso.nome||extrato.itens.index.plano.nome}","quantity":"${extrato.itens.index.quantidade}","unit_price":"${extrato.itens.index.valor}"}]`

importante notar que todas as variaveis do sistema se encontram encapsuladas dentro de `${}`, caso não estejam o sistema tratará elas como valores fixos. Álem disso, o `"title":"${extrato.itens.index.produto_avulso.nome||extrato.itens.index.plano.nome}"` usa o conector `||` para indicar que duas variavéis do sistema podem completar aquele valor.

| Local    | Variavél                                   | Descrição                                                    |
| -------- | ------------------------------------------ | ------------------------------------------------------------ |
| extrato  | ${extrato.user.username}                   | Nome do usuário relacionado ao extrato                       |
| extrato  | ${extrato.user.email}                      | E-mail do usuario relacionado ao extrato                     |
| extrato  | ${extrato.loja.nome}                       | Nome da loja relacionada ao extrato                          |
| extrato  | ${extrato.loja.descricao}                  | Descrição da loja relacionada ao extrato                     |
| extrato  | ${extrato.loja.contato}                    | Contato da loja vinculada ao extrato                         |
| extrato  | ${extrato.loja.cnpj}                       | CNPJ da loja vinculada ao extrato                            |
| extrato  | ${extrato.loja.endereco}                   | Endereço da loja vinculada ao extrato                        |
| extrato  | ${extrato.itens.index.id}                  | Id do objeto dentro de itens                                 |
| extrato  | ${extrato.itens.index.quantidade}          | Quantidade de produtos dentro de itens                       |
| extrato  | ${extrato.itens.index.valor}               | Valor do objeto itens dentro de extrato                      |
| extrato  | ${extrato.itens.index.produto_avulso.nome} | Nome do objeto do produto avulso dentro dos itens do extrato |
| extrato  | ${extrato.itens.index.plano.nome}          | Nome do plano dentro dos itens do extrato                    |
| gateway  | ${gateway.nome}                            | Nome do gateway sendo utilizado                              |
| gateway  | ${gateway.client_id}                       | Id do cliente a ser passado para o gateway                   |
| gateway  | ${gateway.client_secret}                   | Chave segredo do cliente a ser passado para o gateway        |
| gateway  | ${gateway.token}                           | Token do cliente a ser passado para o gateway                |
| gateway  | ${gateway.email}                           | Email do cliente a ser passado para o gateway                |
| Especial | ${valorTotal}                              | Valor total dos itens dentro de um extrato                   |
| Especial | ${dataHoje}                                | Data de hoje no formato AAAA-MM-DD                           |
