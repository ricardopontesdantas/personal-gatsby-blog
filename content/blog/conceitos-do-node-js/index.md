---
title: Conceitos do Node.js
date: 2022-12-07T09:34:20.657Z
description: Alguns conceitos básicos sobre o Node.js
---
N﻿ode.js é uma plataforma open-source que permite a utilização de Javascript no lado do servidor. Ele é composto pela v8 que é um interpretador JavaScript que a princípio foi criado para acelerar a execução de JavaScript no lado do browser; pela libuv que é uma biblioteca multiplataforma com foco em I/O assíncrono; por um conjunto de módulos.

O﻿ Node.js surgiu a partir da percepção da falta de suporte a processo de I/O assíncrono das linguagens na época (2009).



C﻿aracterísticas do Node.js

* A﻿rquitetura Event Loop
* S﻿ingle thread
* N﻿on-blocking I/O
* M﻿ódulos próprios



Um pouco sobre o Event Loop

O﻿ event loop é como se fosse um escutador de eventos, e ele fica escutando as funções que vão chegando a call stack. A call stack é uma pilha onde ficam as funções que são executadas. No caso do Node.js, uma requisição não bloqueia a outra, então quando temos uma requisição a uma API por exemplo, onde é necessário levar um tempo até que a resposta seja retornada, o event loop remove essa request da fila e leva para uma outra thread para que a fila de funções não pare de ser executada, até que essa resposta fique pronta e o evet loop devolva essa resposta para a fila e ela seja devolvida a quem a solicitou.



G﻿erenciadores de Pacotes do Node.jS

T﻿emos o NPM e o Yarn como gerenciadores de pacotes, que nos permitem instalar bibliotecas externas e também criar e disponibilizar nossos próprios pacotes.



F﻿rameworks

Dentre os mais conhecidos temos o express, o nest, o egg, o adonis, hapi, koa.