---
layout: default
title: Tutorial de Deploy
nav_order: 2
permalink: /deploy
---

Tutorial de Deploy
{: .fs-9}

<!--Descrição-->

{: .fs-6 .fw-300 }

## Requisitos de instalação

Para poder levantar seu próprio ambiente Agromart primeiro é necessário ter instalado na sua maquina algumas ferramentas.

- A api do Agromart, que pode ser baixada através do link `https://github.com/AgroMart/api.git`
- Conta com cartão de credito no [Heroku](https://dashboard.heroku.com/)

Ferramentas necessárias:

- Git
- Heroku

Arquivo de configuração e de ambiente configurados

- config.ini

## Instalações

### Instalação Git

Vá até o endereço `https://git-scm.com/downloads` e faça o download para seu sistema operacional. Em seguida prossiga com a instalação normalmente com as opções padrões.

### Instalação Heroku

Baixe o instalador através de um dos links abaixo:

- Windows 64-bit `https://cli-assets.heroku.com/heroku-x64.exe`
- Windows 32-bit `https://cli-assets.heroku.com/heroku-x86.exe`

siga a instalação normalmente com as opções padrões.

# Instalação da API Agromart

## Arquivos Agromart

Faça o download da api através do endereço `https://github.com/AgroMart/api.git`.
Na pagina da api Agromart clique em code

<img src="{{ site.baseurl }}/assets/deploy/api-git1.png" class="img-fluid" alt="Pagina do git da api agromart com o botão code selecionado"/>

Em seguida, no menu que apareceu, clique em `Download ZIP`

<img src="{{ site.baseurl }}/assets/deploy/api-git2.png" class="img-fluid" alt="Botão de fazer download em ZIP"/>

Agora basta descompactar os arquivos no local que deseja manter o agromart e seguir com a instalação.

## Arquivos de Configuração

### Config.ini

No arquivo `config.ini` preencha-o com suas informações.
E acesse a sua conta do heroku e clique em `Account settings` no canto superior direito da tela inicial. Em seguida, vá até a opção `API-Key ` e clique em `Reveal`. Copie e cole a api-key no seu arquivo `config.ini` substituindo o valor `INSIRA_AQUI_SUA_API_KEY_DO_HEROKU`

Além disso, troque o valor `NOME_DA_CSA` para o nome de sua csa, com letras minusculas, sem espaços ou acentos.
Adicione tambem seu nome, em letras minusculas, sem espaços ou acentos. e por fim email da csa.

Exemplo:

para uma csa chamada `Laranja secreta`, cujo o responsavel é `Laranja Silva`, e possui a chave de api `aaaa0000bbbbb0000` e email `laranja@secreta.com`
o arquivo `config.ini` iria disso:

```
[heroku]
api_key = INSIRA_AQUI_SUA_API_KEY_DO_HEROKU

[csa]
nome_csa = NOME_DA_CSA
responsavel_csa = RESPONSAVEL_DA_CSA
email = EMAIL_DA_CSA
```

para isso:

```
[heroku]
api_key = aaaa0000bbbbb0000

[csa]
nome_csa = laranja-secreta
responsavel_csa = laranja-silva
email = laranja@secreta.com
```

## Deploy da aplicação

Na pasta em que foram descompactados os arquivos, lembre-se de alterar o arquivo de configuração `config.ini` conforme o necessário. em seguida e execute o arquivo `deploy.exe`.

Aguarde uns instantes e sua aplicação estara disponível.
