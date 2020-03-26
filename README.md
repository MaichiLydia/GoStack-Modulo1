## Go Stack Bootcamp
- Treinamento imersivo nas tecnologias mais modernas de desenvolvimento web e mobile.

### Aula 1


#### Recursos/rotas, parametros de rota e de query

- Query params -> `?nome=Lydia`
 ```
    const nome = req.query.nome;

    return res.send({ message: `Hello ${nome}` });
 ```
 Resultado ao acessar `http://localhost:3000/teste?nome=Lydia`: 
 ```
 {
    message: "Hello Lydia"
 }
```

- Route params = `/users/1`
```
server.get('/users/:id', (req, res) => {
    const id = req.params.id;

    // ou const { id } = req.params;

    return res.send({ message: `Buscando o usuário ${id}` });
});

```
Resultado ao acessar `http://localhost:3000/users/1`:
```
{
  message: "Buscando o usuário 1"
}
```
- Request body = `{ "name": "Lydia", "email": "mlydiarodrigues@gmail.com" }`

#### Nodemon

Para evitar que a gente tenha que ficar reiniciando com `node index.js` toda vez que atualizarmos alguma parte do código, instalamos uma dependencia em modo de desenvolvimento(não precisaremos disso no nosso código de produção) que já faz esse trabalho.
`yarn add nodemon`
E em seguida adicionamos no `package.json` um comando no script para utilizarmos esse modo de iniciar nossa aplicação:
```
  "scripts": {
    "dev": "nodemon index.js"
  }
```

#### CRUD

| Nome | Descrição |
| ------------- | ----------- |
| Create | Utilizar o método **POST** para inserir um usuário - *Utiliza o `body`*|
| Read | Utilizaar o método **GET** para listar todos os usuários ou, ao passar um parametro, listar um usuário especifico.|
| Update | Utilizar o método **PUT** para editar um usuário para atualizar as informações. - *Utiliza o `body`*|
| Delete | Utilizar o método **DELETE** passando um parametro para apagar um usuário especifico.|


#### Middlewares

Middleware é uma função que recebe parametros, entre eles os mais utilizados são `req` e `res`, intercepta e manipula esses dados.
Tudo que for formas de manipular a requisição e retornar ou não uma resposta.

Nessa parte foram feitos os middlewares: `checkUserInArray`, `checkUserExists`


#### Debugger

Temos a opção de debugar utilizando o VSCode, basta clicar no lado esquerdo e salvar o launch.json, depois disso é possível colcoar breakpoints, criar e observar variáveis.


#### Extras

[Insomnia colletion](./README_FILES/insomnia-collection.json)