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
{: .fs-6 .fw-300  }

## Passo a passo

1. Entre na pagina inicial da extensão. 

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/selecionar_plugin.png" class="img-fluid" />

2. Selecione `adicionar um novo Gateway`.

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/selecionar_plataforma.png" class="img-fluid" />

2.1. Você irá precisar do nome da ferramenta, de um token, uma url e um método para esse url oferecido pelo proprio gateway.

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/pagamento_customizado.png" class="img-fluid" />

3. Procure pela documentação de API da ferramenta que deseja usar. Em nosso exemplo vamos usar a [Stripe](https://stripe.com/docs/api).

4. Procure por link de pagamento, checkout pro, ou similares. Em nosso exemplo [payment_links](https://stripe.com/docs/api/payment_links/payment_links/retrieve). 

5. Preencha o formulario com as informações corretas.

<img src="{{ site.baseurl }}/assets/plugin/cadastrar/pagamento_customizado_preenchido.png" class="img-fluid" />

