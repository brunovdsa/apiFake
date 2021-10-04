# API

Requisitos:
* NodeJS v5.2.0+

## Como executar
Faça o clone/download deste repositório, execute `npm install` e `npx json-server db.json`. A API fica localizada em `http://localhost:3000`.

## Rotas
Todas as requisições de POST para esta API devem conter o header `Content-Type: application/json`.
Esta API contém as seguintes rotas:

* `GET /devs` : lista as ferramentas cadastradas
* `POST /devs` : cria uma nova ferramenta
* `DELETE /devs/:id` : apaga a ferramenta com ID :id

Para filtrar as ferramentas em `GET /devs`, é possível:
* fazer uma busca global utilizando a query string `?q=:busca`;

## Exemplos

### GET /devs

Requisição: 
```javascript
GET /devs
```
Resposta:
```javascript
[
    {
        "id": 1,
        "avatar": "https://avatars.githubusercontent.com/u/57410900?v=4",
        "name": "Bruno de Sá",
        "email": "brunoviniciussouza.sa@gmail.com",
        "city": "Joinville - SC",
        "education": "Desenvolvedor Web",
        "technologies": "React, Angular, Python, CSS, HTML",
        "ghuser": "https://github.com/brunovdsa"
    }
]
```

### GET /devs?q=:busca

Requisição: 
```javascript
GET /devs?q=Bruno
```
Resposta:
```javascript
[
    {
        "id": 1,
        "avatar": "https://avatars.githubusercontent.com/u/57410900?v=4",
        "name": "Bruno de Sá",
        "email": "brunoviniciussouza.sa@gmail.com",
        "city": "Joinville - SC",
        "education": "Desenvolvedor Web",
        "technologies": "React, Angular, Python, CSS, HTML",
        "ghuser": "https://github.com/brunovdsa"
    }
]
```


### POST /devs

Requisição:
```javascript
// POST /devs
// Content-Type: application/json
{
    "title": "hotel",
    "link": "https://github.com/typicode/hotel",
    "description": "Local app manager. Start apps within your browser, developer tool with local .localhost domain and https out of the box.",
    "tags":["node", "organizing", "webapps", "domain", "developer", "https", "proxy"]
}
```

Resposta:
```javascript
{
    "title": "hotel",
    "link": "https://github.com/typicode/hotel",
    "description": "Local app manager. Start apps within your browser, developer tool with local .localhost domain and https out of the box.",
    "tags":["node", "organizing", "webapps", "domain", "developer", "https", "proxy"],
    "id":5
}
```

### DELETE /devs/:id
Requisição:
```javascript
DELETE /devs/5
```

Resposta:
```javascript
// Status: 200 OK
{}
```
