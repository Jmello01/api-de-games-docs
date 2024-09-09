# API de Games
Esta API é utilizada para tal e tal...
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```

[
    {
        "id": 89,
        "title": "The crew 2",
        "year": 2020,
        "price": 85
    },
    {
        "id": 7,
        "title": "Minecraft",
        "year": 2022,
        "price": 35
    },
    {
        "id": 2323,
        "title": "Wacraft",
        "price": "28",
        "year": "2020"
    }
]


```
##### Falha na autenticação! 401
caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```

{
    "err": "Token Inválido"
}

```

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parametros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema.

Exemplo:

```
{
    "email": "joaomellorj@dev.com",
    "password": "flamengo"
}

```

#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJqb2FvbWVsbG9yakBkZXYuY29tIiwiaWF0IjoxNzI1OTAzMjM3LCJleHAiOjE3MjYwNzYwMzd9.GZO0T8B8NSJgt0VS01prFiMSC3qFGxXNkhUgbESbc1U"
}
```
##### Falha na autenticação! 401
caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail inválido.

Exemplo de resposta:
```

{
    {err: "Credenciais inválidas!"}
}

```
