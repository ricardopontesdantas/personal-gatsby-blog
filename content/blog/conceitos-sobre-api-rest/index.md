---
title: Conceitos sobre API REST
date: 2022-12-08T09:58:55.938Z
description: Conceitos básicos sobre API REST
---
A﻿PI é o acrônimo para Application Programming Interface, e é um conjunto de regras para que duas ou mais aplicações se comuniquem.

R﻿EST é o acrônimo de REpresentation State Transfer, e é um modelo de arquitetura que possui 6 regras:

* **C﻿lient-Server**

  O﻿ client não precisa conhecer a implementação do server e o server não precisa conhecer a implementação do client. Vale dizer que o client não necessariamente é um front-end, podendo ser um back-end consumindo a API
* **S﻿tateless**

  O server não armazena estado, como uma sessão por exemplo. Então toda vez que uma requisição é feita é preciso que sejam enviadas todas as informações necessárias para que seja processada
* **C﻿ache**

  A﻿ API deve permitir armazenamento em cache. Por default as requisições GET devem ser cacheadas.
* **I﻿nterface uniforme**

  I﻿dentificação dos recursos, representação dos recursos como respostas em JSON por exemplo, mensagens auto-descritivas, HATEOAS (Hypertext As The Engine Of Application State) que é o uso de links das respostas, como links de paginação por exemplo.
* **C﻿amadas**

  C﻿amadas entre o client e o server, como um balanceamento de carga por exemplo.
* **C﻿ódigo sob demanda**

  É﻿ opcional. Permite que as funcionalidades do client sejam estendidas na forma de script. Então ao invés de retornar um JSON como resposta, seria retornado um código executável para o cliente implementar.