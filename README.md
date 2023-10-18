# CRUD REST com Fastify e PostgreSQL

Este é um projeto de exemplo que demonstra a criação de uma API RESTful para realizar operações CRUD (Create, Read, Update, Delete) usando JavaScript, Fastify e PostgreSQL. Ele fornece um backend simples para gerenciar entidades em um banco de dados PostgreSQL.

## Pré-requisitos

Antes de começar, certifique-se de ter as seguintes ferramentas instaladas:

- [Node.js](https://nodejs.org/) - O ambiente de execução JavaScript.
- [PostgreSQL](https://www.postgresql.org/) - O banco de dados relacional.
- [Fastify](https://www.fastify.io/) - Um framework web rápido e leve para Node.js.

## Configuração do Banco de Dados

1. Crie um banco de dados PostgreSQL e anote as credenciais de conexão (host, porta, nome do banco de dados, usuário e senha).

2. Configure as credenciais do banco de dados no arquivo `database-postgres.js`.

```javascript
// database-postgres.js

import 'dotenv/config'
import postgres from "postgres";

let { PGHOST, PGDATABASE, PGUSER, PGPASSWORD, ENDPOINT_ID } = process.env;

export class DatabasePostgres {
  constructor() {
    export const sql = postgres({
      user: 'seu_usuario',
      host: 'localhost',
      database: 'sua_base_de_dados',
      password: 'sua_senha',
      port: 5432,
    });
  }
  // ... restante do código
}
```

## Instalação

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/seu-projeto.git
cd seu-projeto
```

2. Instale as dependências:

```bash
npm install
```

3. Execute o aplicativo:

```bash
npm run dev
```

O servidor estará em execução em http://localhost:3333.

## Rotas da API

- `POST /videos`: Cria um novo vídeo.
- `GET /videos`: Retorna uma lista de todos os vídeos.
- `PUT /videos/:id`: Atualiza um vídeo existente pelo ID.
- `DELETE /videos/:id`: Exclui um vídeo pelo ID.

Certifique-se de ajustar o nome das rotas e o modelo de dados de acordo com o seu aplicativo específico.

## Exemplos de Uso

Você pode usar ferramentas como [curl](https://curl.se/) ou [Postman](https://www.postman.com/) para testar as rotas da API.

### Exemplo de Criação de Vídeo

```bash
curl -X POST -H "Content-Type: application/json" -d '{"title": "Novo Vídeo", "description": "Descrição do vídeo", "duration": "02:30"}' http://localhost:3333/videos
```

### Exemplo de Atualização de Vídeo

```bash
curl -X PUT -H "Content-Type: application/json" -d '{"title": "Vídeo Atualizado", "description": "Nova descrição", "duration": "03:00"}' http://localhost:3333/videos/1
```

## Contribuindo

Sinta-se à vontade para contribuir com melhorias para este projeto. Basta criar um fork, fazer as alterações e enviar um pull request.

## Licença

Este projeto está sob a licença [MIT](LICENSE).

---

Certifique-se de personalizar o README com as informações específicas do seu projeto, incluindo o nome, autor, descrição e quaisquer outros detalhes relevantes.