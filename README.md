# Projeto Trybe

# Boas vindas ao repositório do projeto de MongoDB Commerce!

---

# Sumário

- [Habilidades](#habilidades)

- [Entregáveis](#entregáveis)
  - [O que deverá ser desenvolvido](#o-que-deverá-ser-desenvolvido)
  - [Desenvolvimento](#desenvolvimento)
  - [Data de entrega](#data-de-entrega)

- [Instruções para entregar seu projeto](#instruções-para-entregar-seu-projeto)
  - [Antes de começar a desenvolver](#antes-de-começar-a-desenvolver)
  - [Durante o desenvolvimento](#durante-o-desenvolvimento)

- [Como Desenvolver](#como-desenvolver)
  - [Análise Estática](#análise-estática)
  - [Instruções para restaurar o banco de dados commerce](#instruções-para-restaurar-o-banco-de-dados-commerce)
  - [Implementações técnicas](#implementações-técnicas)
  - [Linter](#linter)

- [Requisitos do projeto](#requisitos-do-projeto)
  - [1 - Inclua o campo criadoPor em todos os documentos, colocando Ronald McDonald no valor desse campo](#1---inclua-o-campo-criadopor-em-todos-os-documentos-colocando-ronald-mcdonald-no-valor-desse-campo)
  - [2 - Inclua o campo valorUnitario em todos os documentos em que esse campo não existe e atribua a ele o valor 0.00, com o tipo NumberDecimal](#2---inclua-o-campo-valorunitario-em-todos-os-documentos-em-que-esse-campo-não-existe-e-atribua-a-ele-o-valor-0.00-com-o-tipo-numberdecimal)
  - [3 - Adicione o campo avaliacao em todos os documentos da coleção e efetue alterações nesse campo](#3---adicione-o-campo-avaliacao-em-todos-os-documentos-da-coleção-e-efetue-alterações-nesse-campo)
  - [4 - Atribua a data corrente ao campo ultimaModificacao no sanduíche Big Mac](#4---atribua-a-data-corrente-ao-campo-ultimamodificacao-no-sanduíche-big-mac)
  - [5 - Adicione ketchup aos ingredientes para todos os sanduíches menos o McChicken, garantindo que não haja duplicidade nos ingredientes](#5---adicione-ketchup-aos-ingredientes-para-todos-os-sanduíches-menos-o-mcchicken-garantindo-que-não-haja-duplicidade-nos-ingredientes)
  - [6 - Inclua bacon no final da lista de ingredientes dos sanduíches Big Mac e Quarteirão com Queijo](#6---inclua-bacon-no-final-da-lista-de-ingredientes-dos-sanduíches-big-mac-e-quarteirão-com-queijo)
  - [7 - Remova o item cebola de todos os sanduíches](#7---remova-o-item-cebola-de-todos-os-sanduíches)
  - [8 - Remova o primeiro ingrediente do sanduíche Quarteirão com Queijo](#8---remova-o-primeiro-ingrediente-do-sanduíche-quarteirão-com-queijo)
  - [9 - Remova o último ingrediente do sanduíche Cheddar McMelt](#9---remova-o-último-ingrediente-do-sanduíche-cheddar-mcmelt)
  - [10 - Adicione a quantidade de vendas dos sanduíches por dia da semana](#10---adicione-a-quantidade-de-vendas-dos-sanduíches-por-dia-da-semana)
  - [11 - Insira os elementos combo e tasty no _array_ tags de todos os sanduíches e aproveite para deixar os elementos em ordem alfabética ascendente](#11---insira-os-elementos-combo-e-tasty-no-_array_-tags-de-todos-os-sanduíches-e-aproveite-para-deixar-os-elementos-em-ordem-alfabética-ascendente)
  - [12 - Ordene em todos os documentos os elementos do _array_ valoresNutricionais pelo campo percentual de forma descendente](#12---ordene-em-todos-os-documentos-os-elementos-do-_array_-valoresnutricionais-pelo-campo-percentual-de-forma-descendente)
  - [13 - Adicione o elemento muito sódio ao final do _array_ tags nos produtos em que o percentual de sódio seja maior ou igual a 40](#13---adicione-o-elemento-muito-sódio-ao-final-do-_array_-tags-nos-produtos-em-que-o-percentual-de-sódio-seja-maior-ou-igual-a-40)
  - [14 - Adicione o elemento contém sódio ao final do _array_ tags nos produtos em que o percentual de sódio seja maior do que 20 e menor do que 40](#14---adicione-o-elemento-contém-sódio-ao-final-do-_array_-tags-nos-produtos-em-que-o-percentual-de-sódio-seja-maior-do-que-20-e-menor-do-que-40)
  - [15 - Conte quantos produtos contêm Mc no nome, sem considerar letras maiúsculas ou minúsculas](#15---conte-quantos-produtos-contêm-mc-no-nome-sem-considerar-letras-maiúsculas-ou-minúsculas)
  - [16 - Conte quantos produtos têm 4 ingredientes](#16---conte-quantos-produtos-têm-4-ingredientes)
  - [17 - Conte quantos documentos contêm as palavras frango ou hamburguer utilizando o operador $text](#17---conte-quantos-documentos-contêm-as-palavras-frango-ou-hamburguer-utilizando-o-operador-text)
  - [18 - Conte quantos documentos contêm a expressão feito com utilizando o operador $text](#18---conte-quantos-documentos-contêm-a-expressão-feito-com-utilizando-o-operador-text)
  - [19 - Renomeie o campo descricao para descricaoSite em todos os documentos](#19---renomeie-o-campo-descricao-para-descricaosite-em-todos-os-documentos)
  - [20 - Remova o campo curtidas do item Big Mac](#20---remova-o-campo-curtidas-do-item-big-mac)
  - [21 - Retorne o nome dos sanduíches em que o número de curtidas é maior que o número de sanduíches vendidos](#21---retorne-o-nome-dos-sanduíches-em-que-o-número-de-curtidas-é-maior-que-o-número-de-sanduíches-vendidos)
  - [22 - Retorne o nome e a quantidade de vendas (vendidos) dos sanduíches em que o número de vendas é múltiplo de 5](#22---retorne-o-nome-e-a-quantidade-de-vendas-vendidos-dos-sanduíches-em-que-o-número-de-vendas-é-múltiplo-de-5)

- [Depois de terminar o desenvolvimento (opcional)](#depois-de-terminar-o-desenvolvimento-opcional)
- [Revisando um pull request](#revisando-um-pull-request)
- [Avisos Finais](#avisos-finais)

---

# Habilidades
Neste projeto, verificamos se você é capaz de:

  * Utilizar o método `updateOne()` e `updateMany()`

  * Utilizar os operadores `$set`, `$mul`, `$inc`, `$min`, `$max` e `$currentDate`

  * Renomear campos e remover campos

  * Incorporar dados aos documentos através de arrays

  * Utilizar os operadores `$pop`, `$pull` e `$push`
  
  * Utilizar o operador `$addToSet`

  * Utilizar os operadores `$each`, `$slice` e `$sort`

  * Utilizar o operador `$all` para filtrar documentos

  * Utilizar o operador `$elemMatch` para filtrar documentos

  * Utilizar o operador `$size` para filtrar documentos pelo tamanho de arrays

  * Utilizar o operador `$expr` para criar expressões de agregação

  * Utilizar expressões regulares e o operador `$regex` para buscar documentos

  * Utilizar o índice textual e o operador `$text`

  * Utilizar o operador `$mod`

---

# Entregáveis

## O que deverá ser desenvolvido

Hoje você fará um projeto com o codinome _commerce_. Neste projeto, você praticará todos os conceitos de **MongoDB** já ensinados até aqui.

Para este projeto, escolhemos um dataset bem menor do que o **dataFlights**, mas isso não vai impedir que você aplique tudo o que viu até aqui, combinando os conhecimentos deste bloco e do anterior.

A ideia é trabalhar com o banco de dados `commerce`, que contém dados do cardápio do **McDonald's**, como ingredientes, valores nutricionais e dados fictícios de vendas. As instruções de como restaurar o banco podem ser lidas a seguir.

---

## Desenvolvimento

Temos, neste projeto, uma série de desafios com diferentes níveis de complexidade. Cada desafio deve ser resolvido em seu arquivo próprio.

1. Leia a pergunta e crie no diretório `challenges` um arquivo chamado `desafioN.js`, em que N é o número do desafio.

2. O arquivo deve conter apenas o código MQL (_Mongo Query Language_) do desafio resolvido. **Não se esqueça de incluir o ponto e vírgula (";")** no final de suas queries, como no exemplo a seguir:

   ```js
   db.produtos.find();
   ```

   ⚠️ **Restrições** ⚠️:

   - **Não se deve usar aspas simples** para especificar campos e/ou valores. Quando for necessário usar aspas, **use somente aspas duplas**;

   - **Não se deve usar o comando `use commerce`**, haja visto que **os testes já se conectam automaticamente à base `commerce`**.

3. Faça isso até finalizar todos os desafios e depois siga as instruções de como entregar o projeto em [**Instruções para entregar seu projeto**](#instruções-para-entregar-seu-projeto).

4. Para entregar o seu projeto você deverá criar um _Pull Request_ neste repositório. Este _Pull Request_ deverá conter no diretório `challenges` os arquivos `desafio1.js`, `desafio2.js` e assim por diante até o `desafio22.js`, que conterão seu código `MQL` de cada desafio, respectivamente.

### ⚠️ É importante que seus arquivos tenham exatamente estes nomes! ⚠️

Qualquer dúvida, procure a monitoria. Lembre-se que você pode consultar nosso conteúdo sobre [Git & GitHub](https://course.betrybe.com/intro/git/) sempre que precisar!

---

## Data de Entrega

  - Projeto individual.

  - Será um dia de projeto.
  
  - Data de entrega para avaliação final do projeto: `23/09/2021 - 14:00h`.

---

# Como Desenvolver

### Análise Estática

Usaremos o [ESLint](https://eslint.org/) para fazer a análise estática do seu código.

Este projeto já vem com as dependências relacionadas ao _linter_ configuradas no arquivos `package.json`.

Para poder rodar os `ESLint` em um projeto basta executar o comando `npm install` dentro do projeto e depois `npm run lint`. Se a análise do `ESLint` encontrar problemas no seu código, tais problemas serão mostrados no seu terminal. Se não houver problema no seu código, nada será impresso no seu terminal.

Devido ao fato de as configurações das regras do `ESLint` dos projetos de front e back **serem diferentes**, **é preciso executar o `ESLint` em cada projeto**.

Você pode também instalar o plugin do `ESLint` no `VSCode`, bastar ir em extensions e baixar o [plugin `ESLint`](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).

---

### Instruções para restaurar o banco de dados `commerce`

1. Abra o terminal e conecte-se à sua instância local do **MongoDB**. Se você receber uma mensagem de erro com uma mensagem como **_Connection refused_**, tente reiniciar sua instância ([veja como fazer isso aqui](https://app.betrybe.com/course/back-end/introducao-ao-mongodb/mongodb-introducao/d396e5a2-d5c9-4f3a-b723-1a1d3ea06b3d/conteudos/b9646f17-77fc-401e-bab5-421fdc37428e/conectando/f63aa7aa-ac8f-4253-bf76-7fc71e4eac5a?use_case=side_bar)).

2. Agora que você tem certeza de que a sua instância está no ar e que você está conectado a ela, digite `exit`. Você voltará ao terminal para iniciar a importação dos dados.

3. Na raiz do diretório do projeto, execute o seguinte comando que fará a restauração da base de dados `commerce`:
   ```sh
   DBNAME=commerce ./scripts/resetdb.sh assets/produtos
   ```

- A execução desse script criará um banco de dados chamado `commerce` e importará os dados para a coleção `produtos`.

⚠️ Como tanto esse script quanto o script de execução local dos testes (mostrado na [seção seguinte](#implementações-técnicas)), **restauram a base de dados `commerce`**, se atente a salvar seu progresso nos arquivos de desafio! ⚠️

---

### Implementações técnicas

Para executar localmente os testes, é preciso escrever o seguinte no seu terminal, estando na raiz do diretório do projeto:

```sh
./scripts/evaluate.sh
```

Esse script passará por **todos os desafios** e imprimirá um relatório indicando se passou ou não para cada desafio. Como a execução do script **envolve restauração da base de dados `commerce`** de um teste para outro, recomenda-se esperar pela sua execução completa.

Para executar somente o teste de um desafio, execute o comando abaixo, substituindo N pelo númedo do desafio

```sh
./scripts/evaluate.sh desafioN
```

⚠️ Como na avaliação o banco de dados `commerce` é restaurado de um teste para outro, **se atente a fazer uso do banco restaurado na hora de fazer um desafio**. ⚠️

---

### Linter

Para garantir a qualidade do código, vamos utilizar neste projeto o linter ESLint. Assim o código estará alinhado com as boas práticas de desenvolvimento, sendo mais legível e de fácil manutenção! Para rodar o *linter* localmente no projeto, execute o comando abaixo: 

`npm run lint`

⚠ PULL REQUESTS COM ISSUES DE LINTER NÃO SERÃO AVALIADAS. ATENTE-SE PARA RESOLVÊ-LAS ANTES DE FINALIZAR O DESENVOLVIMENTO! ⚠

Aqui encontram-se os requisitos do projeto. Em cada requisito você encontrara uma imagem de um protótipo de como sua aplicação deve ficar. Estilo da página não será avaliado.

---

# Requisitos do projeto

### 1 - Inclua o campo `criadoPor` em todos os documentos, colocando `"Ronald McDonald"` no valor desse campo.

Para isso, escreva no arquivo `desafio1.js` duas queries, **nesta ordem**:

1. Crie uma query que adicione o campo `criadoPor` em todos os documentos, colocando `"Ronald McDonald"` no valor desse campo.

2. Crie uma query que retorne o `nome` e `criadoPor` de todos os produtos.

### 2 - Inclua o campo `valorUnitario` em todos os documentos em que esse campo não existe e atribua a ele o valor `"0.00"`, com o tipo `NumberDecimal`.

Para isso, escreva no arquivo `desafio2.js` duas queries, **nesta ordem**:

1. Crie uma query que adicione o campo `valorUnitario` em todos os documentos em que esse campo não existe e atribua a ele o valor `"0.00"`, com o tipo `NumberDecimal`.

2. Crie uma query que retorne o `nome` e `valorUnitario` de todos os produtos.

### 3 - Adicione o campo `avaliacao` em todos os documentos da coleção e efetue alterações nesse campo.

Para isso, escreva no arquivo `desafio3.js` quatro queries, **nesta ordem**:

1. Crie uma query que inclua o campo `avaliacao` do tipo `NumberInt` e com o valor `0` em todos os documentos da coleção.

2. Crie uma query que incremente o valor do campo `avaliacao` em `5` em todos os sanduíches de carne do tipo `bovino`. Dica: utilize como filtro o campo `tags`.

3. Crie uma query que incremente o valor do campo `avaliacao` em `3` em todos os sanduíches de `ave`.

4. Crie uma query que retorne o `nome` e `avaliacao` de todos os sanduíches.

### 4 - Atribua a data corrente ao campo `ultimaModificacao` no sanduíche `Big Mac`.

Para isso, escreva no arquivo `desafio4.js` duas queries, **nesta ordem**:

1. Crie uma query que atribua a data corrente ao campo `ultimaModificacao` no sanduíche `Big Mac`. Para a data corrente faça uso do tipo `Date`.

2. Crie uma query que retorne o `nome` de todos os documentos em que o campo `ultimaModificacao` existe.

### 5 - Adicione `ketchup` aos `ingredientes` para todos os sanduíches menos o `McChicken`, garantindo que não haja duplicidade nos `ingredientes`.

Para isso, escreva no arquivo `desafio5.js` duas queries, **nesta ordem**:

1. Crie uma query que adicione `ketchup` aos `ingredientes` para todos os sanduíches menos o `McChicken`, garantindo que não haja duplicidade nos `ingredientes`.

2. Crie uma query que retorne o `nome` e `ingredientes` de todos os documentos.

### 6 - Inclua `bacon` no final da lista de `ingredientes` dos sanduíches `Big Mac` e `Quarteirão com Queijo`.

Para isso, escreva no arquivo `desafio6.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a inclusão de `bacon` no final da lista de `ingredientes` dos sanduíches `Big Mac` e `Quarteirão com Queijo`.

2. Crie uma query que retorne o `nome` e `ingredientes` de todos os documentos.

### 7 - Remova o item `cebola` de todos os sanduíches.

Para isso, escreva no arquivo `desafio7.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a remoção do item `cebola` em todos os sanduíches.

2. Crie uma query que retorne o `nome` e `ingredientes` de todos os documentos.

### 8 - Remova o **primeiro** `ingrediente` do sanduíche `Quarteirão com Queijo`.

Para isso, escreva no arquivo `desafio8.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a remoção do **primeiro** `ingrediente` no sanduíche `Quarteirão com Queijo`.

2. Crie uma query que retorne o `nome` e `ingredientes` de todos os documentos.

### 9 - Remova o **último** `ingrediente` do sanduíche `Cheddar McMelt`.

Para isso, escreva no arquivo `desafio9.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a remoção do **último** `ingrediente` no sanduíche `Cheddar McMelt`.

2. Crie uma query que retorne o `nome` e `ingredientes` de todos os documentos.

### 10 - Adicione a quantidade de vendas dos sanduíches por dia da semana.

Para isso, escreva no arquivo `desafio10.js` quatro queries, **nesta ordem**:

1. Crie uma query que inclua um _array_ com sete posições em todos os sanduíches. Cada uma delas representará um dia da semana, e cada posição iniciará em `0`. O _array_ deve se parecer como abaixo:
   ```json
   "vendasPorDia": [0, 0, 0, 0, 0, 0, 0]
   ```

- O primeiro item desse _array_ representa as vendas no **domingo**, o segundo item representa as vendas na **segunda-feira**, e assim até chegar ao último item, que representa as vendas no **sábado**.

2. Crie uma query que incremente as vendas de `Big Mac` às **quartas-feiras** em `60`.

3. Crie uma query que incremente as vendas de todos os sanduíches de carne do tipo `bovino` e `pão` aos **sábados** em `120`.

4. Crie uma query que retorne o `nome` e `vendasPorDia` de todos os documentos.

### 11 - Insira os elementos `combo` e `tasty` no _array_ `tags` de todos os sanduíches e aproveite para deixar os elementos em ordem alfabética ascendente.

Para isso, escreva no arquivo `desafio11.js` duas queries, **nesta ordem**:

1. Crie uma query que faça tanto a inserção dos elementos `combo` e `tasty` no _array_ `tags` de todos os sanduíches quanto a ordenação dos elementos de `tags` em ordem alfabética ascendente.

2. Crie uma query que retorne o `nome` e `tags` de todos os documentos.

### 12 - Ordene em todos os documentos os elementos do _array_ `valoresNutricionais` pelo campo `percentual` de forma descendente.

Para isso, escreva no arquivo `desafio12.js` duas queries, **nesta ordem**:

1. Crie uma query que faça em todos os documentos a ordenação dos elementos do _array_ `valoresNutricionais` pelo campo `percentual` de forma descendente. Dica: mesmo sem adicionar nenhum novo elemento, para essa operação é necessário utilizar também o modificador `$each`.

2. Crie uma query que retorne o `nome` e `valoresNutricionais` de todos os documentos.

### 13 - Adicione o elemento `muito sódio` ao final do _array_ `tags` nos produtos em que o `percentual` de `sódio` seja maior ou igual a `40`.

Para isso, escreva no arquivo `desafio13.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a adição do elemento `muito sódio` ao final do _array_ `tags` nos produtos em que o `percentual` de `sódio` seja maior ou igual a `40`.

2. Crie uma query que retorne o `nome` e `tags` de todos os documentos.

### 14 - Adicione o elemento `contém sódio` ao final do _array_ `tags` nos produtos em que o `percentual` de `sódio` seja maior do que `20` e menor do que `40`.

Para isso, escreva no arquivo `desafio14.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a adição do elemento `contém sódio` ao final do _array_ `tags` nos produtos em que o `percentual` de `sódio` seja maior do que `20` e menor do que `40`.

2. Crie uma query que retorne o `nome` e `tags` de todos os documentos.

### 15 - Conte quantos produtos contêm `Mc` no nome, sem considerar letras maiúsculas ou minúsculas.

### 16 - Conte quantos produtos têm `4` ingredientes.

### 17 - Conte quantos documentos contêm as palavras `frango` ou `hamburguer` utilizando o operador `$text`.

Para isso, escreva no arquivo `desafio17.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a criação de um índice do tipo `text` no campo `descricao` com o idioma padrão `portuguese`.

2. Crie uma query que retorne a quantidade de documentos que contêm as palavras `frango` ou `hamburguer` utilizando o operador `$text`.

### 18 - Conte quantos documentos contêm a **expressão** `feito com` utilizando o operador `$text`.

Para isso, escreva no arquivo `desafio18.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a criação de um índice do tipo `text` no campo `descricao` com o idioma padrão `portuguese`.

2. Crie uma query que retorne a quantidade de documentos que contêm a **expressão** `feito com` utilizando o operador `$text`.

### 19 - Renomeie o campo `descricao` para `descricaoSite` em todos os documentos.

Para isso, escreva no arquivo `desafio19.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a renomeação do campo `descricao` para `descricaoSite` em todos os documentos.

2. Crie uma query que retorne o `nome`, `descricao` e `descricaoSite` de todos os documentos.

### 20 - Remova o campo `curtidas` do item `Big Mac`.

Para isso, escreva no arquivo `desafio20.js` duas queries, **nesta ordem**:

1. Crie uma query que faça a remoção do campo `curtidas` do item `Big Mac`.

2. Crie uma query que retorne o `nome` e `curtidas` de todos os documentos.

### 21 - Retorne o `nome` dos sanduíches em que o número de `curtidas` é maior que o número de sanduíches `vendidos`.

### 22 - Retorne o `nome` e a quantidade de vendas (`vendidos`) dos sanduíches em que o número de vendas é múltiplo de `5`.

---

# Depois de terminar o desenvolvimento (OPCIONAL)

Para sinalizar que o seu projeto está pronto para o _"Code Review"_ dos seus colegas, faça o seguinte:

- Vá até a página **DO SEU** _Pull Request_, adicione a label de _"code-review"_ e marque seus colegas:

  - No menu à direita, clique no _link_ **"Labels"** e escolha a _label_ **code-review**;

  - No menu à direita, clique no _link_ **"Assignees"** e escolha **o seu usuário**;

  - No menu à direita, clique no _link_ **"Reviewers"** e digite `students`, selecione o time `tryber/students-sd-00`.

Caso tenha alguma dúvida, [aqui tem um video explicativo](https://vimeo.com/362189205).

---

# Revisando um pull request

Use o conteúdo sobre [Code Review](https://course.betrybe.com/real-life-engineer/code-review/) para te ajudar a revisar os _Pull Requests_.

\#VQV 🚀

---

### Resultado do projeto
*Item* | | 
--- | :---:
Desempenho | Suficiente
Critério de Avaliação | Padrão
Percentual de cumprimento de requisitos obrigatórios | 100.00%
Percentual de cumprimento de requisitos totais | 100.00%
### Resultado por requisito
*Nome* | *Avaliação*
--- | :---:
22 - Retorne o `nome` e a quantidade de vendas (`vendidos`) dos sanduíches em que o número de vendas é múltiplo de `5`. | :heavy_check_mark:
21 - Retorne o `nome` dos sanduíches em que o número de `curtidas` é maior que o número de sanduíches `vendidos`. | :heavy_check_mark:
20 - Remova o campo `curtidas` do item `Big Mac`. | :heavy_check_mark:
19 - Renomeie o campo `descricao` para `descricaoSite` em todos os documentos. | :heavy_check_mark:
18 - Conte quantos documentos contêm a **expressão** `feito com` utilizando o operador `$text`. | :heavy_check_mark:
17 - Conte quantos documentos contêm as palavras `frango` ou `hamburguer` utilizando o operador `$text`. | :heavy_check_mark:
16 - Conte quantos produtos têm `4` ingredientes. | :heavy_check_mark:
15 - Conte quantos produtos contêm `Mc` no nome, sem considerar letras maiúsculas ou minúsculas. | :heavy_check_mark:
14 - Adicione o elemento `contém sódio` ao final do _array_ `tags` nos produtos em que o `percentual` de `sódio` seja maior do que `20` e menor do que `40`. | :heavy_check_mark:
13 - Adicione o elemento `muito sódio` ao final do _array_ `tags` nos produtos em que o `percentual` de `sódio` seja maior ou igual a `40`. | :heavy_check_mark:
12 - Ordene em todos os documentos os elementos do _array_ `valoresNutricionais` pelo campo `percentual` de forma descendente. | :heavy_check_mark:
11 - Insira os elementos `combo` e `tasty` no _array_ `tags` de todos os sanduíches e aproveite para deixar os elementos em ordem alfabética ascendente. | :heavy_check_mark:
10 - Adicione a quantidade de vendas dos sanduíches por dia da semana. | :heavy_check_mark:
9 - Remova o **último** `ingrediente` do sanduíche `Cheddar McMelt`. | :heavy_check_mark:
8 - Remova o **primeiro** `ingrediente` do sanduíche `Quarteirão com Queijo`. | :heavy_check_mark:
7 - Remova o item `cebola` de todos os sanduíches. | :heavy_check_mark:
6 - Inclua `bacon` no final da lista de `ingredientes` dos sanduíches `Big Mac` e `Quarteirão com Queijo`. | :heavy_check_mark:
5 - Adicione `ketchup` aos `ingredientes` para todos os sanduíches menos o `McChicken`, garantindo que não haja duplicidade nos `ingredientes`. | :heavy_check_mark:
4 - Atribua a data corrente ao campo `ultimaModificacao` no sanduíche `Big Mac`. | :heavy_check_mark:
3 - Adicione o campo `avaliacao` em todos os documentos da coleção e efetue alterações nesse campo. | :heavy_check_mark:
2 - Inclua o campo `valorUnitario` em todos os documentos em que esse campo não existe e atribua a ele o valor `0.00`, com o tipo `NumberDecimal`. | :heavy_check_mark:
1 - Inclua o campo `criadoPor` em todos os documentos, colocando `Ronald McDonald` no valor desse campo. | :heavy_check_mark:
