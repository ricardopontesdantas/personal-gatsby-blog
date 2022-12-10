---
title: Utilizando o Nodemon numa aplicação Node.js
date: 2022-12-10T12:33:34.976Z
description: Conhecendo um pouco da dependência Nodemon
---
Todas as vezes que alteramos nosso projeto em Node.js é necessário parar e iniciar o servidor para que as alterações tenham efeito. Para que não seja necessário fazer esse processo a todo momento podemos instalar o Nodemon que faz com que toda vez que salvarmos o arquivo alterado ele reinicie o servidor automaticamente.

P﻿ara instalar o Nodemon precisamos executar o comando abaixo no terminal, dentro da pasta do projeto

`y﻿arn add nodemon -D`

P﻿assamos a flag `-D` para indicar que se trata de uma dependência de desenvolvimento, ou seja, é uma dependência necessária apenas em ambiente de desenvolvimento, logo não será levada para o ambiente de produção.

A﻿pós a instalação da dependência podemos passar a rodar o projeto utilizando o comando `nodemon` seguido do nome do arquivo que inicializa o servidor. No exemplo abaixo o arquivo é o index.js e ele está dentro da pasta src.

`n﻿odemon src/index.js`

C﻿om o comando acima o servidor já irá iniciar e toda vez que um arquivo for salvo após uma alteração ele irá reiniciar.

P﻿odemos melhorar um pouquinho mais e adicionar um atalho ao comando do Nodemon no arquivo package.json. Então primeiro abrimos o arquivo package.json e antes da seção de dependências criamos uma propriedade de nome `scripts` e atribuímos como valor um objeto que terá uma propriedade que vamos chamar de `dev` que terá como valor o comando do Nodemon. O nome `dev` é apenas uma convenção, poderia ser qualquer outro.

```json
"scripts": {
  "dev": "nodemon src/index.js"
}
```

P﻿odemos ainda fazer de uma outra forma que é indicando na propriedade `main` o arquivo de inicialização do projeto e o nosso script seria apenas `nodemon .`

```json
"main": "src/index.js",
"scripts": {
  "dev": "nodemon ."
}
```

A﻿ partir de agora podemos iniciar o projeto com o comando `yarn dev` caso esteja utilizando o Yarn. Caso esteja utilizando o NPM o comando será `npm run dev`.