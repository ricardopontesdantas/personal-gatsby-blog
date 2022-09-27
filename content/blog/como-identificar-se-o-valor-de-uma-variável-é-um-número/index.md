---
title: Como identificar se o valor de uma variável é um número
date: 2022-09-27T19:58:06.783Z
description: "#php #is_numeric"
---
Podemos identificar se uma variável tem como valor um número ou string numérica utilizando a função nativa do PHP `is_numeric()`. Essa função recebe como parâmetro um valor qualquer e retorna true caso seja um valor numérico como integer, float ou uma string numérica e retorna false caso não se encaixe em nenhum dos três tipos.

```php
echo is_numeric(10);
// 1 (true)

echo is_numeric('10');
// 1 (true)

echo is_numeric(10.5);
// 1 (true)

echo is_numeric('number 10');
// nada é impresso (false)

echo is_numeric('foo');
// nada é impresso (false)

echo is_numeric(true);
// nada é impresso (false)
```