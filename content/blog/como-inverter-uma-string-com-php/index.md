---
title: Como inverter uma string com PHP
date: 2022-09-20T11:49:34.921Z
description: "#php #strrev"
---
Para inverter uma string podemos utilizar a função `strrev()`, que recebe uma string como parâmetro e retorna a mesma string porém invertida. Então caso passemos como argumento a string 'foo', será retornada a string 'oof'.

```
$string = 'foo';
$reversedString = strrev('foo');
echo $reversedString;
// oof
```