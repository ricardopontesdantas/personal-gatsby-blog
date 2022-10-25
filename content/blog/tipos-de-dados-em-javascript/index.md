---
title: Tipos de dados em JavaScript
date: 2022-10-25T10:58:49.096Z
description: Conhecendo alguns tipos de dados em JavaScript
---
T﻿emos dois grupos de tipos em JavaScript:

* T﻿ipos primitivos
* T﻿ipos derivados/objetos

N﻿o grupo de tipos primitivos temos `string`, `number`, `boolean`, `null`, `undefined`, `symbol` e `bigint`. Os tipos `symbol` e `bigint` são mais recentes na linguagem e não serão exemplificados aqui.

Qualquer texto entre aspas (simples ou duplas) é do tipo `string`.

U﻿m número inteiro ou de ponto flutuante é do tipo `number`. Para ser do tipo `number`, não deve estar entre aspas, caso contrário será uma `string`. N`number`ão há um tipo específico para inteiro ou ponto flutuante. Os dois casos são tipo `number`.

U﻿m valor booleano sempre será `true` ou `false`. Podemos declarar diretamente os valores `true` ou `false` em uma variável ou esse valor booleano poderá ser obtido através de uma operação de comparação, onde por exemplo `1 < 2` resulta em `true` e `1 > 2` resulta em `false`.

O valor `null` sempre será declarado implicitamente a uma variável, onde significa ausência de valor. Ou seja, a variável declarada com o valor `null`, será do tipo `null`.

O valor `undefined` é quando tentamos utilizar uma variável declarada porém não inicializada. Então essa variável será do tipo `undefined`.

V﻿amos ver abaixo alguns exemplos:

```
// number
const age = 25
console.log(age)

// string
const name = 'Ricardo'
console.log(name)

// boolean
const isValid = true
console.log(isValid)

// null
let subtitle = null
console.log(subtitle)

// undefined
let description
console.log(description)
```

N﻿o grupo de tipos derivados/objetos temos os objetos Javascript que incluem funções, arrays e expressões regulares. Todos estes são do tipo `object`.

```
// array
const numbers = [1, 2, 3, 4, 5]

// function
function double(number) {
  return number * 2
}

// expressão regular
const pattern = /\d{2,4}/g
```