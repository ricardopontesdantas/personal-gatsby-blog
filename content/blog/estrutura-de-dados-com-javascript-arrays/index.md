---
title: Estrutura de Dados com JavaScript - Arrays
date: 2023-01-30T17:56:55.897Z
description: Neste post vamos começar a falar sobre arrays, como inicializar um
  array e descobrir o tamanho de um array
---
O A﻿rray é uma estrutura de dados que nos permite armazenar dados de um mesmo tipo. Apesar de o Javascript nos permitir armazenar dados de diferentes tipos isso é incomum de ser visto e não é uma boa prática.

## I﻿nicializar um array

A﻿baixo algumas formas distintas de se inicializar um array.

```javascript
// inicializa um array vazio através do construtor Array e atribui a variável months
let months = new Array()

// inicializa um array de tamanho 12 através do construtor Array e atribui a variável months
months = new Array(12)

// inicializa um array com já com os dados através do construtor Array e atribui a variável months
months = new Array('january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december')

// inicializa um array vazio através dos colchetes e atribui a variável months
months = []

// inicializa um array já com os dados através dos colchetes e atribui a variável months
months = ['january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december']
```

É﻿ mais comum vermos um array sendo inicializado com os colchetes ao invés de se criar uma instância de Array.

## T﻿amanho de um array

P﻿ara sabermos quantos elementos um array possui basta utilizarmos a propriedade `length`.

```javascript
let months = [
  'january', 
  'february', 
  'march', 
  'april', 
  'may', 
  'june', 
  'july', 
  'august', 
  'september', 
  'october', 
  'november', 
  'december'
] 
console.log(months.length) // 12
```

Já um array vazio irá retornar zero.

```javascript
let months = []
console.log(months.length) // 0
```

U﻿tilizar a propriedade length em uma variável que foi apenas declarada irá retornar um erro, pois essa variável por ter sido declarada sem nenhum valor irá retornar undefined, e não podemos chamar qualquer propriedade ou função de undefined.

```javascript
let months
console.log(months.length) // TypeError
```

U﻿tilizar a propriedade length em uma variável que não existe irá retornar um erro que nos diz que a variável não foi definida.

```javascript
console.log(months.length) // ReferenceError
```