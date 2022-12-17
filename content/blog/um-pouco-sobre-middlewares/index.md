---
title: Um pouco sobre middlewares
date: 2022-12-17T12:32:08.288Z
description: Conhecendo um pouco sobre middlewares no Node.js
---
*N﻿o exemplo demonstrado abaixo estou utilizando Node.js com o Express.*

U﻿m middleware é basicamente uma função que fica entre a requisição e a resposta que nos permite por exemplo validar os dados vindos na requisição antes que qualquer outra função seja executada.

V﻿amos ver um pequeno exemplo de uma API onde temos algumas rotas que recebem o CPF do cliente no header da requisição e através desse CPF é feita uma validação se o cliente existe ou não na base de dados antes de ser feito qualquer coisa. Ao invés de criamos a validação em todas as rotas, vamos criar um middleware que fará essa validação e as rotas que precisarem desse middleware irão apenas chamá-lo.

*No exemplo abaixo não vamos nos preocupar com arquitetura de pastas, vamos apenas criar o middleware no mesmo arquivos de inicialização do servidor.*

Então já que um middleware é apenas uma função, vamos criá-la. Um middleware recebe três parâmetros: request, response e next.

O request é a requisição, é onde temos as informações que serão validadas, em nosso exemplo será o CPF. O response é a resposta que o middleware poderá devolver caso a request não passe na validação. E o next é a função que faz o middleware dar sequência na requisição, chegando enfim na função que está atrelada a rota.

E﻿ntão abaixo o nosso middleware

```javascript
function verifyIfCustomerExists(request, response, next) {
  const { cpf } = request.headers
  
  const customer = customers.find(customer => customer.cpf === cpf)
  
  if (!customer) {
    response.status(400).json({ error: 'customer not found' })
  }
  
  request.customer = customer
  
  next()
}
```

N﻿o exemplo acima estamos supondo que temos um array de customers e validamos se o CPF vindo na request existe em algum cliente dentro desse array. Caso não exista já devolvemos uma resposta com um status e uma mensagem. Caso contrário precisamos atribuir o cliente encontrado a request novamente, pois a função que será executada a seguir precisa dessa informação. E finalizando, chamamos a função next() para dar sequência e chamar a próxima função, que poderá ser outro middleware ou a função atrelada a rota.

P﻿odemos atribuir um middleware a uma rota de duas maneiras: a primeira é utilizando o `app.use()` passando o nome da função como argumento e então todas as rotas declaradas abaixo passarão por esse middleware automaticamente. A outra maneira é chamando o middleware diretamente na rota. Caso seja necessário chamar mais de um middleware, basta ir separando por vírgula cada um deles.

Vamos ver na prática para entendermos melhor. Abaixo temos uma rota com sua função que apenas retorna uma propriedade de um cliente.

```javascript
app.get('/statements', verifyIfCustomerExists, (request, response) => {
  const { customer } = request // request vinda do middleware
  
  return response.status(200).json(customer.statements)
})
```

E﻿ntão todas as vezes que bater uma requisição nessa rota o middleware será chamado e a validação será feita. Caso não passe na validação o próprio middleware devolve uma resposta negativa a quem fez a requisição. Caso passe na validação damos sequência com o `next()` e então a função seguinte é executada, onde recebemos a request vinda do middleware com os dados que precisamos e aí sim devolvemos a resposta a quem fez a requisição.