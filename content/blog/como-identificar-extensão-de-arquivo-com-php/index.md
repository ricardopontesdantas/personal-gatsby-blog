---
title: Como identificar extensão de arquivo com PHP
date: 2022-09-13T13:57:58.817Z
description: "#php #pathinfo"
---
P﻿ara saber a extensão de um arquivo, podemos usar a função `pathinfo()`. Essa função recebe como primeiro parâmetro uma string com o caminho do arquivo, e como segundo parâmetro `PATHINFO_EXTENSION`.

```php
$path = 'c:\documentos\relatorio.pdf';
$extension = pathinfo($path, PATHINFO_EXTENSION);
echo $extension;
// pdf
```

F﻿alando um pouco sobre a função `pathinfo()`, ela pode receber até dois parâmetros: O primeiro é obrigatório que é o caminho do arquivo no formato string, e o segundo é opcional.

C﻿omo opções para esse segundo parâmetro tem o `PATHINFO_DIRNAME`, que no exemplo acima retornaria 'c:\documentos'. Também tem a opção `PATHINFO_BASENAME` que retornaria 'relatorio.pdf'. Uma outra opção é o `PATHINFO_EXTENSION` que foi utilizado no exemplo acima, retornando 'pdf'. E a última opção é o `PATHINFO_FILENAME`, que retornaria 'relatorio'. Caso esse segundo parâmetro não seja informado, todas as informações listadas acima são retornadas num array associativo.