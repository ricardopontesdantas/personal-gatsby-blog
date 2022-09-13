---
title: Como identificar extensão de arquivo com PHP
date: 2022-09-13T13:57:58.817Z
description: "#php #pathinfo"
---
P﻿ara saber a extensão de um arquivo, podemos usar a função pathinfo(). Essa função recebe como primeiro parâmetro uma string com o caminho do arquivo, e como segundo parâmetro PATHINFO_EXTENSION.

```php
$path = 'c:\documentos\relatorio.pdf';
$extension = pathinfo($path, PATHINFO_EXTENSION);
echo $extension;
// pdf
```

Falando um pouco sobre a função pathinfo(), ela pode receber até dois parâmetros. O primeiro é obrigatório que é o caminho do arquivo e o segundo é opcional.

Como opções para esse segundo parâmetro tem o PATHINFO_DIRNAME, que no exemplo acima retornaria 'c:\documentos'. Tem o PATHINFO_BASENAME que retornaria 'relatorio.pdf'. Tem o PATHINFO_EXTENSION que foi utilizado no exemplo acima, retornando 'pdf'. E finalizando tem o PATHINFO_FILENAME, que retornaria 'relatorio'. Caso o segundo parâmetro não seja informado, todas as informações listadas acima são retornadas num array associativo.