---
layout: default
title: Tutorial de Deploy
nav_order: 2
permalink: /deploy
---

Tutorial de Deploy
{: .fs-9}

<!--Descrição-->
{: .fs-6 .fw-300  }


## Pré requesitos 

- Repositório clonado em um computador local
- Conta com cartão de credito no [Heroku](https://dashboard.heroku.com/)

Ferramentas necessárias:

- Git
- Heroku

Arquivo de configuração e de ambiente configurados

- config.ini

## Instalações Externas

### Instalação Git
Vá até o endereço `https://git-scm.com/downloads` e faça o download para seu sistema operacional. Em seguida prossiga com a instalação normalmente com as opções padrões.

### Instalação Node.js
Baixe o instalador em `https://nodejs.org/pt-br` e faça o download da versão `LTS  - recomendado para Maioria dos usuarios` e siga a instalação normalmente com as opções padrões.

### Instalação Heroku
Baixe o instalador através de um dos links abaixo:

- Windows 64-bit    `https://cli-assets.heroku.com/heroku-x64.exe` 
- Windows 32-bit    `https://cli-assets.heroku.com/heroku-x86.exe` 

siga a instalação normalmente com as opções padrões.

## Arquivos de Configuração

### Config.ini

No arquivo `config.ini` preencha-o com suas informações. 
E acesse a sua conta do heroku e clique em ``Account settings`` no canto superior direito da tela inicial. Em seguida, vá até a opção ``API-Key `` e clique em `Reveal`. Copie e colar a api-key no seu arquivo ``config.ini``

Exemplo:

```
[heroku]
api_key = api-key-do-heroku

[csa]
nome_csa = laranja-secreta
responsavel_csa = laranja
email = laranja.secreta@gmail.com
```

## Deploy da aplicação

Em uma pasta faça o download do repositorio `https://github.com/AgroMart/api.git` utilizando o git ou descompactando os arquivos
Em seguida execute o arquivo `deploy.exe`.

Aguarde uns instantes e sua aplicação estara disponível.