# Fake-API Endpoints

## URL base da API é: (https://hamburgueria-fake-api.herokuapp.com)

## POST /register - Criar um novo usuário

{
"username": "usuario "
"email": "user@mail.com",
"password": "123456"
"confirmPassword": "123456"
}

### Caso dê tudo certo, a reposta será assim: STATUS 201

## POST /login - Fazer o login do usuário:

{
"email": "user@mail.com",
"password": "123456"
}

### Caso dê tudo certo, a reposta será assim: STATUS 200

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6IndpbGxAbWFpbC5jb20iLCJpYXQiOjE2MzUxODI5NzcsImV4cCI6MTYzNTE4NjU3Nywic3ViIjoiMiJ9sjs.jNBqpb5DPRqepoX7mLgpkPQtG7j0hRqw1MTVgYfHWeg",
"user": {
"email": "user@mail.com",
"id": 2
}
}

## GET /products - Pegar todos os produtos da API : (

      get("/products")
      .then((res) => console.log(res))
      .catch((err) => console.log(err)))

### Caso dê tudo certo, a reposta será assim: STATUS 200

## GET /cart - Puxar todos os produtos que estão no carrinho: (

      get("cart", {
        headers: {
          Authorization: `Bearer ${token}`,
        },
      }))
      .then((res) => console.log(res))
      .catch((err) => console.log(err))

| Necessário autorização: Authorization: Bearer {token}

### Caso dê tudo certo, a reposta será assim: STATUS 200

[
{
"name": "Mac Kenzie",
"category": "Sanduíches",
"price": 7.99,
"img": "url",
"userId": "1",
"subtotal": 7.99,
"id": 1
},
{
"name": "X-Burguer",
"category": "Sanduíches",
"price": 8.99,
"img": "url",
"userId": "1",
"subtotal": 8.99,
"id": 2
}
]

## POST /cart - Adicionar um novo produto ao carrinho: (

        post("/cart", data, {
          headers: {
            Authorization: `Bearer ${token}`,
          },
        }))
        .then((res) => console.log(res))
        .catch((err) => console.log(err))

| Necessário autorização: Authorization: Bearer {token}

{
"name": "Mac Kenzie",
"category": "Sanduíches",
"price": 7.99,
"img": "url",
"userId": 1
},

### Caso dê tudo certo, a reposta será assim: STATUS 201

{
"name": "Mac Kenzie",
"category": "Sanduíches",
"price": 7.99,
"img": "url",
"userId": 1,
"id": 1
},

## DELETE /cart - Remover um produto do carrinho: (

      delete(`/cart/${id}`, {
        headers: {
          Authorization: `Bearer ${token}`,
        },
      }))
      .then((res) => console.log(res))
      .catch((err) => console.log(err))

### Caso dê tudo certo, a reposta será assim: STATUS 200
