# Tech4um

O tech4um será um fórum de texto, onde as conversas serão baseadas em canais que os próprios usuários criarem, somente usuários logados poderão acessar os canais para conversar e criar canais.

## 🚀 Começando

Essas instruções permitirão que você obtenha uma cópia do projeto em operação na sua máquina local para fins de desenvolvimento.

Consulte **Instalação** para saber como implantar o projeto.

Documentação do websocekt está no final do arquivo.

### 📋 Pré-requisitos

De que coisas você precisa para instalar o software e como instalá-lo?

```
Node na versão 14.17.6+;
```

### 🔧 Instalação

Para executar o projeto, você precisa instalar o Node.js. Para isso, você pode usar o [Node.js](https://nodejs.org/en/download/) ou o [npm](https://www.npmjs.com/get-npm/).

Irá precisar instalar as dependências do projeto.

```
npm i ou yarn
```

Aṕos isso, você pode executar o projeto.

```
npm rum start ou yarn start

```

Terá o seguinte resultado:


```
> Server started on port 3333

```

## 📦 Desenvolvimento

A documentação da API REST está disponivel pelo postman no link [DOCUMENTAÇÃO](https://documenter.getpostman.com/view/17298396/Uyxkkm8b).

## 🛠️ Construído com

* [Node.js](https://nodejs.org/)
* [Express](https://expressjs.com/)
* [Socket.io](https://socket.io/)

## 🖇️ Socket.io

Para se conectar ao servidor, você precisa usar o [Socket.io](https://socket.io/). É necessario instalar o pacote [socket.io-client](https://www.npmjs.com/package/socket.io-client) no frontend.

Para se conectar ao socket é preciso enviar o token de autenticação do usuário, caso contrário a conexão será encerrada, segue o exemplo da documentação.

~~~
import { io } from "socket.io-client";

const socket = io({
  auth: {
    token: "token-do-úsuario"
  }
});
~~~

### 👇🏻Os eventos disparados para do web socket para o front são:

### message
Evento disparado quando um usuário envia uma mensagem no canal.

~~~
{
    "user": {
        "name": "Ricardo",
        "email": "luis.ricardo@tech4h.com.br",
        "id": "0f6cbcae-bc95-4f06-b02d-0c6598c088dc"
    },
    "message": "mensagem no geral",
    "to": null,
    "timestamp": "2022-05-18T03:23:22.718Z"
}
~~~

### left
Evento disparado quando um usuário sai do canal.
~~~
{
    "name": "Ricardo",
    "email": "luis.ricardo@tech4h.com.br",
    "id": "6e48b2a2-ae3a-460d-89b5-b0f3fe68872f"
}
~~~

### joined
Evento disparado quando um usuário entra no canal.
~~~
{
    "name": "Ricardo",
    "email": "luis.ricardo@tech4h.com.br",
    "id": "6e48b2a2-ae3a-460d-89b5-b0f3fe68872f"
}
~~~

### new-room
Evento disparado quando um usuário cria um novo canal.
~~~
{
    "id": "c6458b3a-ee86-408d-a0e4-b8fcde31b671",
    "name": "real customer",
    "description": "humanized service",
    "by": {
        "name": "Ricardo",
        "email": "luis.ricardo@tech4h.com.br",
        "id": "0f6cbcae-bc95-4f06-b02d-0c6598c088dc"
    }
}
~~~

### delete-room
Evento disparado quando um usuário deleta um canal.
~~~
{
       "id": "c6458b3a-ee86-408d-a0e4-b8fcde31b671"
}
~~~

### ☝🏻Eventos disparados para o backend são:

### join
Evento deve ser disparado quando um usuário entrar no canal. Deve ser passado o id do canal.

### leave
Evento deve ser disparado quando um usuário sair do canal. Deve ser passado o id do canal.

---
⌨️ com ❤️ por [L Ricardo](mailto:luis.ricardo@tech4h.com.br) 😊
```
