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
