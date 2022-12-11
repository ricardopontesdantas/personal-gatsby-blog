---
title: Tipos de parâmetros mais utilizados em APIs REST
date: 2022-12-11T10:57:26.164Z
description: Vamos ver os tipos de parâmetros mais utilizados com exemplos em Node.js
---
*Nos exemplos estou utilizando Node.js com Express e os códigos de exemplos são apenas trechos, não o código completo.*

N﻿este post vamos conhecer três dos tipos de parâmetros que são os mais utilizados em APIs REST.

### R﻿oute Params

São parâmetros que recebemos encapsulados na rota, que são divididos por '/'. Utilizamos route params quando queremos identificar um recurso seja para obter, atualizar ou remover. No exemplo abaixo o recurso é `courses` e o route param é `1`, que é o identificador do recurso. No código de exemplo obtemos os route params através de request.params

E﻿xemplo: `http://localhost:3333/courses/1`

```javascript
app.get('/courses/:id', (req, res) => {
  const { id } = request.params
  
  console.log(id) // 1
  
  res.json()
})
```

### Q﻿uery Params

São parâmetros que recebemos na rota logo após a inicialização do '?', que indica que logo após começam os query params, onde podemos enviar um ou mais pares de chave=valor sendo separados por '&'. Podemos utilizar query params para paginação e filtros de busca. No exemplo abaixo o recurso é `courses` e o query params é `page=3&order=asc`. No código de exemplo obtemos os query params através de request.query

E﻿xemplo: `http://localhost:3333/courses?page=3&order=asc`

```javascript
app.get('/courses', (req, res) => {
  const query = request.query
  
  console.log(query) // { page: '3', order: 'asc' }
  
  res.json()
})
```

### B﻿ody Params

São parâmetros que recebemos no corpo da requisição. Utilizamos body params quando queremos criar ou atualizar um recurso. Podemos utilizar alguns formatos diferentes, mas no nosso exemplo utilizamos JSON. Para que o nosso exemplo funcione corretamente ainda precisamos informar ao Express que o formato que será recebido no body é JSON.

N﻿o exemplo abaixo o recurso é `courses` e o route params é `3`, que é o identificador do recurso. O body params não é enviado na rota, e sim no corpo da requisição. No código de exemplo obtemos os body params através de request.body

E﻿xemplo: `http://localhost:3333/courses/3`

J﻿SON enviado no body da requisição: `'{"name":"Curso 4"}’`

```javascript
app.use(express.json())

app.post('/courses', (req, res) => {
  const body = request.body
  
  console.log(body) // { "name": "Curso 4" }
  
  res.json()
})
```