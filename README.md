# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Projetos Front-end.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.


### Login

POST /login

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### URL base
https://your-tripping-api.herokuapp.com/


### Pegar todos os usuários:

GET /users

FORMATO DA RESPOSTA
```
 "users": [
    {
      "email": "kenzinho@mail.com",
      "password": "$2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",
      "name": "Kenzinho",
      "imageUrl": "https://static.biologianet.com/2022/06/raposa-vermelha.jpg",
      "age": 38,
      "id": 1
    }
  ]
```

### Pegar todos os posts:

GET /posts

FORMATO DA RESPOSTA
``` 
 "posts": [
    {
      "id": 1,
      "userId": 1,
      "username": "Filipe",
      "country": "Brasil",
      "imageUrl": "https://static.biologianet.com/2022/06/raposa-vermelha.jpg",
      "location": "Rio de Janeiro RJ",
      "places": [
        {
          "id": 1,
          "name": "Primeira parada: Corcovado",
          "image": "https://dhg1h5j42swfq.cloudfront.net/2021/11/23142721/121021_094621_100709999.jpg",
          "description": "O Corcovado é um dos morros da cidade do Rio de Janeiro, célebre no Brasil e no mundo pela sua estátua do Cristo Redentor de 38 metros de altura. O Cristo Redentor é um dos principais símbolos do país e oferece uma privilegiada vista panorâmica da cidade do Rio de Janeiro"
        },
        {
          "id": 1,
          "name": "Primeira parada: Corcovado",
          "image": "https://dhg1h5j42swfq.cloudfront.net/2021/11/23142721/121021_094621_100709999.jpg",
          "description": "O Corcovado é um dos morros da cidade do Rio de Janeiro, célebre no Brasil e no mundo pela sua estátua do Cristo Redentor de 38 metros de altura. O Cristo Redentor é um dos principais símbolos do país e oferece uma privilegiada vista panorâmica da cidade do Rio de Janeiro"
        }
      ]
    }
  ],
```

### Pegar todos os seguidores:

GET /followers/:id

FORMATO DA RESPOSTA
```
“followers”:
[
    {
“followername”: “Fernando”,
“userId”: 1,
“id”: 3
   }
],
```

### Seguir usuário:

POST /followers

FORMATO DA REQUISIÇÃO
```
{
      "username": "julia",
      "userId": 2
}
```

### Criar post

POST /posts

FORMATO DA REQUISIÇÃO
```
{
      "userId": 1,
      "username": "Filipe",
      "country": "Brasil",
      "imageUrl": "https://static.biologianet.com/2022/06/raposa-vermelha.jpg",
      "location": "Rio de Janeiro RJ",
      "places": [
        {
          "id": 1,
          "name": "Primeira parada: Corcovado",
          "image": "https://dhg1h5j42swfq.cloudfront.net/2021/11/23142721/121021_094621_100709999.jpg",
          "description": "O Corcovado é um dos morros da cidade do Rio de Janeiro, célebre no Brasil e no mundo pela sua estátua do Cristo Redentor de 38 metros de altura. O Cristo Redentor é um dos principais símbolos do país e oferece uma privilegiada vista panorâmica da cidade do Rio de Janeiro"
        },
        {
          "id": 2,
          "name": "Primeira parada: Corcovado",
          "image": "https://dhg1h5j42swfq.cloudfront.net/2021/11/23142721/121021_094621_100709999.jpg",
          "description": "O Corcovado é um dos morros da cidade do Rio de Janeiro, célebre no Brasil e no mundo pela sua estátua do Cristo Redentor de 38 metros de altura. O Cristo Redentor é um dos principais símbolos do país e oferece uma privilegiada vista panorâmica da cidade do Rio de Janeiro"
        }
      ]
    }
```





### Editar post

PATCH /posts/:id

FORMATO DA REQUISIÇÃO
```
{
      "userId": 1,
      "username": "Filipe",
      "country": "Brasil",
      "imageUrl": "https://static.biologianet.com/2022/06/raposa-vermelha.jpg",
      "location": "Rio de Janeiro RJ",
      "places": [
        {
          "id": 1,
          "name": "Primeira parada: Corcovado",
          "image": "https://dhg1h5j42swfq.cloudfront.net/2021/11/23142721/121021_094621_100709999.jpg",
          "description": "O Corcovado é um dos morros da cidade do Rio de Janeiro, célebre no Brasil e no mundo pela sua estátua do Cristo Redentor de 38 metros de altura. O Cristo Redentor é um dos principais símbolos do país e oferece uma privilegiada vista panorâmica da cidade do Rio de Janeiro"
        },
        {
          "id": 2,
          "name": "Primeira parada: Corcovado",
          "image": "https://dhg1h5j42swfq.cloudfront.net/2021/11/23142721/121021_094621_100709999.jpg",
          "description": "O Corcovado é um dos morros da cidade do Rio de Janeiro, célebre no Brasil e no mundo pela sua estátua do Cristo Redentor de 38 metros de altura. O Cristo Redentor é um dos principais símbolos do país e oferece uma privilegiada vista panorâmica da cidade do Rio de Janeiro"
        }
      ]
    }
```








### Comentar

POST /comments

FORMATO DA REQUISIÇÃO
```
  {
      "userId": 1,
      "postId": 1,
      "username": "Filipe",
      "content": "Lugar incrível"
    },
```

### Like

POST /likes

FORMATO DA REQUISIÇÃO
```
{
    “userId”: 1,
    “postId”: 1
}
```

### Editar perfil do usuário

PATCH /users/:id

FORMATO DA REQUISIÇÃO
```
 {
      "name": "Kenzinho",
      "imageUrl": "https://static.biologianet.com/2022/06/raposa-vermelha.jpg",	
      "bio": "Olá, sou o Kenzinho e faço viagens anuais pelo Brasil"		
 }
```
