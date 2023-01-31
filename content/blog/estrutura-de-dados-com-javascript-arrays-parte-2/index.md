---
title: Estrutura de Dados com JavaScript - Arrays - Parte 2
date: 2023-01-31T16:11:50.029Z
description: Neste post vamos entender como acessar os elementos de um array com
  alguns exemplos
---
## Acessar um ou mais elementos de um array

Para acessar o elemento de um array podemos utilizar a notação de colchetes apontando o índice do elemento desejado. Por exemplo, se temos uma variável `months` que tem como valor `['january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december']` e queremos exibir no console o elemento 'may' então inserimos seu índice entre colchetes, que neste exemplo é 4. Lembrando apenas que arrays são zero-based, ou seja, o elemento inicial será atribuído ao índice zero.

```javascript
let months = ['january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december']
console.log(months[4]) // may
```

Para exibir no console todos os elementos desse array podemos iterar sobre ele.

```javascript
let months = ['january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december']
for(let i = 0; i < months.length; i++) {
 console.log(months[i])
}
// january
// february
// march
// april
// may
// june
// july
// august
// september
// october
// november
// december
```

Um outro exemplo seria mostrar no console quais são os 10 primeiros números da sequência de Fibonacci. Alguns autores iniciam a sequencia com zero e 1, outros com 1 e 1 e outros com 1 e 2. Vamos fazer a nossa sequencia começar com os números 1 e 1 e a partir daí o próximo número será sempre a soma dos dois números anteriores. Então vamos criar um array já com os dois primeiros índices com os valores 1 e 1. Em seguida vamos iterar sobre o array iniciando pelo índice 2 e atribuindo a esse índice os valores dos dois índices anteriores, até que tenhamos 10 elementos no array.

```javascript
const fibonacci = [1, 1]
for(let i = 2; i < 10; i++) {
 fibonacci[i] = fibonacci[i-1] + fibonacci[i-2]
}
console.log(fibonacci) // [1, 1, 2, 3, 5, 8, 13, 21, 34, 55
```