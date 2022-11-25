---
title: Como configurar o CORS no Node.js
date: 2022-11-25T21:04:03.792Z
description: "#js #nodejs #cors"
---
\**No exemplo descrito estou utilizando o express como framework.*

Para habilitar o CORS para um ou mais domínios ou ainda tornar sua API pública, primeiro precisamos instalar a dependência cors.

`npm i cors`

Após isso basta irmos em nosso arquivo de inicialização do servidor e fazer a devida configuração. Estou levando em consideração que você já tenha instalado o express e tenha sua API funcional.

No primeiro exemplo vamos deixar a API pública para quem quiser obter informações a partir dela.

```javascript
const express = require('express')

const app = express()

app.use(cors())
```

Neste segundo exemplo vamos dar permissão a apenas um domínio.

```javascript
const express = require('express')

const app = express()

app.use(cors({
	origin: 'http://somedomain.com'
}))
```

Nesse terceiro exemplo vamos dar permissão a mais de um domínio. Para isso vamos criar uma lista com esses domínios para depois verificar a partir dessa lista.

```javascript
const express = require('express')

const app = express()

const allowedDomains = [
	'http://somedomain.com',
	'http://blog.somedomain.com',
	'http://loremipsum.com',
]

app.use(cors({
	origin: function(origin, callback) {
		const allowed = allowedDomains.includes(origin)

		callback(null, allowed)
	}
}))
```

Neste último exemplo, a propriedade origin do objeto que passamos para cors() tem uma função como valor. Essa função recebe dois parâmetros: o primeiro é a origem que vamos verificar e o segundo é uma funçãod e callback, que chamamos de callback mesmo. Nessa função criamos uma constante chamada allowed que terá como valor true ou false. Usamos o método includes() para saber se a origem está ou não na lista, e esse método retornará true ou false. Então chamamos o callback() passando null como primeiro argumento e a constante allowed como segundo. O null que passamos é uma mensagem que será retornada para quem fez a requisição, e deixamos null para que seja retornada a mensagem padrão. O segundo argumento, o allowed, se for true é porque a origem tem permissão para obter informações da API, mas caso seja false não terá permissão.