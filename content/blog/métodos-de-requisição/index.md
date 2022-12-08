---
title: Métodos de Requisição
date: 2022-12-08T10:12:41.970Z
description: Métodos de requisição, códigos de status e parâmetros de requisições
---
O﻿s métodos HTTP mais utilizados no desenvolvimento web são:

* G﻿ET

  U﻿tilizado quando queremos obter informações de um recurso como uma lista de usuários, ou de um recurso com um ID específico por exemplo.
* P﻿OST

  U﻿tilizado quando submetemos um objeto ao servidor, como criar um novo registro num banco de dados.
* P﻿UT

  U﻿tilizado para fazer a atualização completa de um objeto.
* P﻿ATCH

  U﻿tilizado para fazer a atualização parcial de um objeto.
* D﻿ELETE

  U﻿tilizado para fazer a remoção de um objeto da aplicação.



## H﻿TTP Codes

São códigos formados por três dígitos para indicar o status de uma resposta. Vamos ver alguns abaixo:

* 1﻿xx: Informativo apenas, indica que uma solicitação foi feita ou o processo permanece em andamento
* 2﻿xx: Confirmação

  * 2﻿00 Ok: requisição bem sucedida, o retorno de uma requisição com o método GET por exemplo
  * 2﻿01 Created: geralmente utilizado quando submetemos um novo objeto com o método POST
* 3﻿xx: Redirecionamento

  * 3﻿01 Moved Permanently: indica que o recurso solicitado foi movido permanentemente
* 4﻿xx Erro no client

  * 4﻿00 Bad Request: indica que o server não irá atender a requisição por algum erro na request como um erro de sintaxe por exemplo
  * 4﻿01 Unauthorized: indica que a solicitação não foi atendida porque o client não tem as credenciais de autenticação válidas para o recurso
  * 4﻿03 Forbidden: indica que o server entendeu a requisição mas não autorizou devido a uma senha incorreta por exemplo.
  * 4﻿04 Not Found: indica que o server não encontrou o recurso solicitado, como uma rota inexistente.
* 5﻿xx: Erro no server

  * 5﻿00 Internal Server Error: indica que o server encontrou uma condição inesperada que o impediu de responder a requisição.

No desenvolvimento web podemos focar nos códigos 2xx, 4xx e 5xx que são os mais utilizados.



## P﻿arâmetros das requisições

* H﻿eader Params

  P﻿arâmetros enviados no cabeçalho da requisição, como um token de autorização por exemplo.
* Q﻿uery Params

  P﻿arâmetros enviados no fim de uma URL após um '?', como um filtro de paginação. São parâmetros enviados como 'chave=valor' e separados por '&'. Ex.: `minhaapi.com.br/v1/products?page=2&limit10`
* R﻿oute Params

  P﻿arâmetros enviados no meio da rota. Por exemplo, se quero buscar um produto com um ID específico, então posso enviar da seguinte forma: `minhaapi.com.br/v1/products/15`
* B﻿ody Params

  P﻿arâmetros enviados no corpo da requisição