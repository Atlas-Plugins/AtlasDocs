---
description: >-
  👋🏻 Olá, seja bem vindo a documentação oficial da Atlas Plugins. Aqui você
  poderá encontrar como utilizar nossas APIs de nossos plugins e outras
  informações.
---

# Página Inicial

## O que seria API?

API (Application Programming Interface) é uma forma de plugins de terceiros acessar informações de nossos plugins através de classes que nós disponibilizamos especificamente para isso.

## O que preciso fazer para utilizar a API de cada plugin da Atlas Plugins?

Para utilizar a API de nossos plugins, tenha certeza que o seu plugin possui o ícone ( \</> ) no seu [Dashboard](https://atlasplugins.com/#/dashboard/plugins) do cliente.

Após isso, siga os passos abaixo:

1. Baixe o arquivo clicando no ícone ( \</> ) e clicando em Baixar.
2. &#x20;Importe a API e o AtlasLicense.jar na Build Path da sua IDE. [(Imagem)](https://image.prntscr.com/image/dQTxdCJkSz2GZpEwrb2byA.png)
3. &#x20;**NÃO** colocar o plugin da API(download abaixo) na pasta plugins.
4. Adicione na sua plugin.yml a opção softdepend: \[AtlasLicense] para que seu plugin inicialize após o AtlasLicense ser inicializado.

Pronto!, agora sua workspace está configurada para a utilização de nossas APIs.
